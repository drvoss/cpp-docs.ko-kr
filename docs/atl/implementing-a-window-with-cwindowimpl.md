---
title: CWindowImpl을 통해 창 구현
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
ms.openlocfilehash: e5fdbf15ddd7edc69f0667a9b7e08c7c5e531a5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319457"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>CWindowImpl을 통해 창 구현

창을 구현하려면 에서 `CWindowImpl`클래스를 파생합니다. 파생 클래스에서 메시지 맵과 메시지 처리기 함수를 선언합니다. 이제 다음 세 가지 방법으로 수업을 사용할 수 있습니다.

- [새 Windows 클래스를 기반으로 창 만들기](#_atl_creating_a_window_based_on_a_new_windows_class)

- [기존 Windows 클래스의 수퍼클래스](#_atl_superclassing_an_existing_windows_class)

- [기존 창 하위 클래스](#_atl_subclassing_an_existing_window)

## <a name="creating-a-window-based-on-a-new-windows-class"></a><a name="_atl_creating_a_window_based_on_a_new_windows_class"></a>새 Windows 클래스를 기반으로 창 만들기

`CWindowImpl`에는 Windows 클래스 정보를 선언하는 [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) 매크로가 포함되어 있습니다. 이 매크로는 `GetWndClassInfo` [CWndClassInfo를](../atl/reference/cwndclassinfo-class.md) 사용하여 새 Windows 클래스의 정보를 정의하는 함수를 구현합니다. 호출될 때 `CWindowImpl::Create` 이 Windows 클래스가 등록되고 새 창이 만들어집니다.

> [!NOTE]
> `CWindowImpl`매크로에 `DECLARE_WND_CLASS` NULL을 전달하므로 ATL은 Windows 클래스 이름을 생성합니다. 사용자 고유의 이름을 지정하려면 -derived `CWindowImpl`클래스에서 DECLARE_WND_CLASS 문자열을 전달합니다.

## <a name="example"></a>예제

다음은 새 Windows 클래스를 기반으로 창을 구현하는 클래스의 예입니다.

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

창을 만들려면 메서드의 `CMyWindow` 인스턴스를 만든 `Create` 다음 메서드를 호출합니다.

> [!NOTE]
> 기본 Windows 클래스 정보를 재정의하려면 `GetWndClassInfo` 멤버를 적절한 값으로 `CWndClassInfo` 설정하여 파생 클래스에서 메서드를 구현합니다.

## <a name="superclassing-an-existing-windows-class"></a><a name="_atl_superclassing_an_existing_windows_class"></a>기존 Windows 클래스의 수퍼 클래스 분류

[DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) 매크로를 사용하면 기존 Windows 클래스를 수퍼클래스하는 창을 만들 수 있습니다. -derived 클래스에서 이 매크로를 지정합니다. `CWindowImpl` 다른 ATL 창과 마찬가지로 메시지는 메시지 맵에서 처리됩니다.

DECLARE_WND_SUPERCLASS 사용하면 새 Windows 클래스가 등록됩니다. 이 새 클래스는 지정한 기존 클래스와 동일하지만 창 프로시저를 `CWindowImpl::WindowProc` (또는 이 메서드를 재사용하는 함수)로 바꿉니다.

## <a name="example"></a>예제

다음은 표준 편집 클래스를 수퍼 클래스로 분류하는 클래스의 예입니다.

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

수퍼 클래스 편집 창을 만들려면 의 `CMyEdit` 인스턴스를 만든 `Create` 다음 메서드를 호출합니다.

## <a name="subclassing-an-existing-window"></a><a name="_atl_subclassing_an_existing_window"></a>기존 창 하위 클래스조정

기존 창을 하위 클래스로 사용하려면 `CWindowImpl` 이전 두 사례에서와 같이 클래스를 파생하고 메시지 맵을 선언합니다. 그러나 이미 기존 창을 하위 클래스로 지정하므로 Windows 클래스 정보를 지정하지 않습니다.

호출하는 `Create`대신 `SubclassWindow` 호출하여 하위 클래스를 원하는 기존 창에 핸들을 전달합니다. 창이 하위 클래스가 되면 메시지 `CWindowImpl::WindowProc` 맵으로 메시지를 전달하는 데(또는 이 메서드를 재사용하는 함수)를 사용합니다. 개체에서 하위 클래스창을 분리하려면 을 호출합니다. `UnsubclassWindow` 그러면 창의 원래 창 프로시저가 복원됩니다.

## <a name="see-also"></a>참고 항목

[창 구현](../atl/implementing-a-window.md)
