---
title: 'TN017: 창 개체 제거'
ms.date: 11/04/2016
f1_keywords:
- vc.objects
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
ms.openlocfilehash: 9802669468cbbba89f23b8ac127358d1fc15ec9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370416"
---
# <a name="tn017-destroying-window-objects"></a>TN017: 창 개체 제거

이 노트는 [CWnd::PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) 메서드의 사용에 대해 설명합니다. -derived 개체의 `CWnd`사용자 지정 할당을 수행하려는 경우 이 메서드를 사용합니다. 이 노트에서는 [CWnd::DestroyWindow를](../mfc/reference/cwnd-class.md#destroywindow) 사용하여 **삭제** 연산자 대신 C++ Windows 개체를 삭제해야 하는 이유에 대해서도 설명합니다.

이 항목의 지침을 따르는 경우 정리 문제가 거의 없습니다. 이러한 문제는 삭제/무료 C++ 메모리를 잊어버리는 것, s와 같은 `HWND`시스템 리소스를 해제하는 것을 잊어내거나 개체를 너무 많이 해제하는 등의 문제로 인해 발생할 수 있습니다.

## <a name="the-problem"></a>문제

각 windows 개체(파생된 클래스의 `CWnd`개체)는 C++ 개체와 `HWND`를 모두 나타냅니다. C++ 개체는 응용 프로그램의 힙에 할당되고 `HWND`s는 창 관리자가 시스템 리소스에 할당합니다. 창 개체를 삭제하는 방법에는 여러 가지가 있으므로 시스템 리소스 또는 메모리 누수를 방지하는 규칙 집합을 제공해야 합니다. 또한 이러한 규칙은 개체 및 Windows 핸들이 두 번 이상 소멸되는 것을 방지해야 합니다.

## <a name="destroying-windows"></a>윈도우 파괴

다음은 Windows 개체를 파괴하는 두 가지 허용된 방법입니다.

- 전화 `CWnd::DestroyWindow` 또는 Windows `DestroyWindow`API .

- **삭제** 연산자를 명시적으로 삭제합니다.

첫 번째 경우는 지금까지 가장 일반적입니다. 이 경우는 코드가 직접 호출되지 `DestroyWindow` 않는 경우에도 적용됩니다. 사용자가 프레임 창을 직접 닫으면 이 작업은 WM_CLOSE 메시지를 생성하고 이 메시지에 대한 `DestroyWindow.` 기본 응답은 부모 창이 `DestroyWindow` 소멸될 때 호출하는 것입니다.

두 번째 경우는 Windows 개체에서 **삭제** 연산자의 사용은 드물어야 합니다. 삭제를 **사용하는** 것이 올바른 선택인 경우는 다음과 같습니다.

## <a name="auto-cleanup-with-cwndpostncdestroy"></a>CWnd::P로 자동 정리

시스템이 Windows 창을 파괴하면 창으로 전송된 마지막 Windows 메시지가 WM_NCDESTROY. 해당 `CWnd` 메시지의 기본 처리기는 [CWnd::OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy). `OnNcDestroy`C++ `HWND` 개체에서 분리하고 가상 함수를 `PostNcDestroy`호출합니다. 일부 클래스는 이 함수를 재정의하여 C++ 개체를 삭제합니다.

스택 프레임에 `CWnd::PostNcDestroy` 할당되거나 다른 개체에 포함된 창 개체에 적합한 기본 구현은 아무 작업도 수행하지 않습니다. 다른 개체 없이 힙에 할당되도록 설계된 창 개체에는 적합하지 않습니다. 즉, 다른 C++ 개체에 포함되지 않은 창 개체에는 적합하지 않습니다.

힙에 단독으로 할당되도록 설계된 클래스는 이 `PostNcDestroy` **삭제를**수행하는 메서드를 재정의합니다. 이 명령문은 C++ 개체와 연결된 모든 메모리를 해제합니다. 기본 소멸자가 `CWnd` null이 아닌 `DestroyWindow` *경우 m_hWnd* 호출하더라도 정리 단계에서 핸들이 분리되고 NULL이 null이기 때문에 무한 재귀로 이어지지 않습니다.

> [!NOTE]
> 시스템은 일반적으로 `CWnd::PostNcDestroy` Windows WM_NCDESTROY 메시지를 `HWND` 처리하고 C++ 창 개체가 더 이상 연결되지 않은 후 호출합니다. 또한 시스템은 대부분의 `CWnd::PostNcDestroy` [CWnd::Create](../mfc/reference/cwnd-class.md#create) 호출의 구현에서 오류가 발생하면 호출합니다. 자동 정리 규칙은 이 항목의 후반부에서 설명합니다.

## <a name="auto-cleanup-classes"></a>자동 정리 클래스

다음 클래스는 자동 정리를 위해 설계되지 않았습니다. 일반적으로 다른 C++ 개체 또는 스택에 포함됩니다.

- 모든 표준 Windows`CStatic` `CEdit`컨트롤 `CListBox`( , " 및 등)

- 자식 창(예: `CWnd` 사용자 지정 컨트롤)에서 직접 파생됩니다.

- 스플리터`CSplitterWnd`창 ()

- 기본 컨트롤 막대(에서 `CControlBar`파생된 클래스는 컨트롤 막대 개체에 대해 자동 삭제를 사용하도록 설정하기 위한 [기술 참고 31](../mfc/tn031-control-bars.md) 참조).

- 대화 상자`CDialog`() 스택 프레임에 모달 대화 상자를 위해 설계 되었습니다.

- 을 제외한 `CFindReplaceDialog`모든 표준 대화 상자.

- ClassWizard에서 만든 기본 대화 상자입니다.

다음 클래스는 자동 정리를 위해 설계되었습니다. 일반적으로 힙에 자체적으로 할당됩니다.

- 주 프레임 창(직접 또는 간접적으로 `CFrameWnd`파생).

- 보기 창 (직접 또는 간접적으로 `CView`파생).

이러한 규칙을 중단하려면 파생 클래스의 메서드를 `PostNcDestroy` 재정의해야 합니다. 클래스에 자동 정리를 추가하려면 기본 클래스를 호출한 다음 **이 삭제를**수행합니다. 클래스에서 자동 정리를 제거하려면 `CWnd::PostNcDestroy` 직접 기본 `PostNcDestroy` 클래스의 메서드 대신 직접 호출합니다.

자동 정리 동작을 변경하는 가장 일반적인 용도는 힙에 할당할 수 있는 모덜리스 대화 상자를 만드는 것입니다.

## <a name="when-to-call-delete"></a>삭제 를 호출할 때

C++ 메서드 `DestroyWindow` 또는 전역 `DestroyWindow` API중 하나를 사용하여 Windows 개체를 삭제하는 것이 좋습니다.

MDI 자식 `DestroyWindow` 창을 삭제하려면 전역 API를 호출하지 마십시오. 대신 가상 메서드를 `CWnd::DestroyWindow` 사용해야 합니다.

자동 정리를 수행하지 않는 C++ Window 개체의 경우 **삭제** 연산자사용으로 VTBL이 올바르게 파생된 클래스를 가리키지 않는 경우 `DestroyWindow` `CWnd::~CWnd` 소멸자에서 호출하려고 할 때 메모리 누수가 발생할 수 있습니다. 이 문제는 시스템에서 호출할 적절한 destroy 메서드를 찾을 수 없기 때문에 발생합니다. 삭제 `DestroyWindow` 대신 **delete** 사용하면 이러한 문제를 방지할 수 있습니다. 이는 미묘한 오류일 수 있으므로 디버그 모드로 컴파일하면 위험에 처한 경우 다음과 같은 경고가 생성됩니다.

```
Warning: calling DestroyWindow in CWnd::~CWnd
    OnDestroy or PostNcDestroy in derived class will not be called
```

자동 정리를 수행하는 C++ Windows 개체의 경우 을 `DestroyWindow`호출해야 합니다. **삭제** 연산자를 직접 사용하는 경우 MFC 진단 메모리 할당자는 메모리를 두 번 비웠다는 것을 알려줍니다. 두 번의 발생은 첫 번째 명시적 호출과 의 자동 정리 구현에서 **이를 삭제하는** 간접 호출입니다. `PostNcDestroy`

자동 `DestroyWindow` 정리가 아닌 개체를 호출한 후에도 C++ 개체는 계속 주위에 있지만 *m_hWnd* NULL이 됩니다. 자동 `DestroyWindow` 정리 개체를 호출한 후 C++ 개체는 사라지고 `PostNcDestroy`의 자동 정리 구현에서 C++ delete 연산자가 해제됩니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
