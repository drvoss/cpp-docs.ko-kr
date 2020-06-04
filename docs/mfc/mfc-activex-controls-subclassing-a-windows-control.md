---
title: 'MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱'
ms.date: 09/12/2018
f1_keywords:
- precreatewindow
- IsSubclassed
helpviewer_keywords:
- OnDraw method, MFC ActiveX controls
- subclassing
- DoSuperclassPaint method [MFC]
- subclassing Windows controls
- subclassing, Windows controls
- reflected messages, in ActiveX controls
- PreCreateWindow method, overriding
- MFC ActiveX controls [MFC], subclassed controls
- MFC ActiveX controls [MFC], creating
- IsSubclassed method [MFC]
ms.assetid: 3236d4de-401f-49b7-918d-c84559ecc426
ms.openlocfilehash: ccebbad22be92b84fa2fd84434f788484d332cce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375992"
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱

이 문서에서는 ActiveX 컨트롤을 만들기 위해 일반적인 Windows 컨트롤을 하위 분류하는 프로세스에 대해 설명합니다. 기존 Windows 컨트롤을 하위 분류하는 것은 ActiveX 컨트롤을 개발하는 빠른 방법입니다. 새 컨트롤에는 페인팅 및 마우스 클릭에 응답하는 등 하위 클래스Windows 컨트롤의 기능을 사용할 수 있습니다. MFC ActiveX 컨트롤 샘플 [BUTTON은](../overview/visual-cpp-samples.md) Windows 컨트롤을 하위 분류하는 예입니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

Windows 컨트롤을 하위 클래스로 분류하려면 다음 작업을 완료합니다.

- [COleControl의 IsSubclasscontrol 및 PreCreateWindow 멤버 함수 재정의](#_core_overriding_issubclassedcontrol_and_precreatewindow)

- [OnDraw 멤버 함수 수정](#_core_modifying_the_ondraw_member_function)

- [컨트롤에 반영된 모든 ActiveX 제어 메시지(OCM) 처리](#_core_handling_reflected_window_messages)

   > [!NOTE]
   > 이 작업의 대부분은 **Control 설정** 페이지에서 **부모 창 클래스 선택** 드롭다운 목록을 사용하여 하위 클래스로 분류할 컨트롤을 선택하면 ActiveX 컨트롤 마법사에서 수행됩니다.

## <a name="overriding-issubclassedcontrol-and-precreatewindow"></a><a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a>재의거 초과제어 및 프리미더윈

재정의하고 `PreCreateWindow` `IsSubclassedControl`을 받으려면 컨트롤 클래스 선언의 **보호된** 섹션에 다음 코드 줄을 추가합니다.

[!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]

제어 구현 파일(. CPP) 다음 코드 줄을 추가하여 두 개의 재정의된 함수를 구현합니다.

[!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]

이 예제에서는 Windows 단추 컨트롤이 에 `PreCreateWindow`지정되어 있습니다. 그러나 모든 표준 Windows 컨트롤은 하위 클래스로 분류할 수 있습니다. 표준 Windows 컨트롤에 대한 자세한 내용은 [컨트롤](../mfc/controls-mfc.md)을 참조하십시오.

Windows 컨트롤을 하위 분류할 때 컨트롤의 창을 만드는 데 사용할 특정 창 스타일(WS_) 또는 확장 창 스타일(WS_EX_) 플래그를 지정할 수 있습니다. 및 구조 필드를 수정하여 멤버 함수에서 이러한 매개 `cs.dwExStyle` 변수에 대한 값을 설정할 수 있습니다. `PreCreateWindow` `cs.style` 클래스에 `COleControl`의해 설정된 기본 플래그를 유지하려면 **OR** 작업을 사용하여 이러한 필드를 수정해야 합니다. 예를 들어 컨트롤이 BUTTON 컨트롤을 하위 분류하고 있고 컨트롤이 확인란으로 표시되도록 하려면 return 문 `CSampleCtrl::PreCreateWindow`앞에 의 구현에 다음 코드 줄을 삽입합니다.

[!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]

이 작업은 클래스의 `COleControl` 기본 스타일 플래그(WS_CHILD)를 그대로 유지하면서 BS_CHECKBOX 스타일 플래그를 추가합니다.

## <a name="modifying-the-ondraw-member-function"></a><a name="_core_modifying_the_ondraw_member_function"></a>OnDraw 멤버 함수 수정

하위 클래스 컨트롤이 해당 Windows 컨트롤과 동일한 모양을 유지하도록 `OnDraw` 하려면 컨트롤의 멤버 함수에는 다음 `DoSuperclassPaint` 예제와 같이 멤버 함수에 대한 호출만 포함해야 합니다.

[!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]

에서 `DoSuperclassPaint` 구현된 `COleControl`멤버 함수는 Windows 컨트롤의 창 프로시저를 사용하여 경계 사각형 내에서 지정된 장치 컨텍스트에서 컨트롤을 그립니다. 이렇게 하면 컨트롤이 활성화되지 않은 경우에도 컨트롤이 표시됩니다.

> [!NOTE]
> 멤버 `DoSuperclassPaint` 함수는 장치 컨텍스트를 WM_PAINT 메시지의 *wParam으로* 전달할 수 있는 제어 형식에서만 작동합니다. 여기에는 SCROLLBAR 및 BUTTON과 같은 표준 Windows 컨트롤과 모든 일반적인 컨트롤이 포함됩니다. 이 동작을 지원하지 않는 컨트롤의 경우 비활성 컨트롤을 올바르게 표시하려면 고유한 코드를 제공해야 합니다.

## <a name="handling-reflected-window-messages"></a><a name="_core_handling_reflected_window_messages"></a>반사된 창 메시지 처리

Windows 컨트롤은 일반적으로 특정 창 메시지를 부모 창으로 보냅니다. WM_COMMAND 같은 일부 메시지는 사용자가 작업에 대한 알림을 제공합니다. WM_CTLCOLOR 같은 다른 정보는 부모 창에서 정보를 가져오는 데 사용됩니다. ActiveX 컨트롤은 일반적으로 다른 방법으로 부모 창과 통신합니다. 알림은 이벤트를 실행(이벤트 알림 보내기)을 통해 전달되며, 제어 컨테이너에 대한 정보는 컨테이너의 주변 속성에 액세스하여 가져옵니다. 이러한 통신 기술이 존재하기 때문에 ActiveX 제어 컨테이너는 컨트롤에서 보낸 창 메시지를 처리하지 않습니다.

컨테이너가 하위 클래스 Windows 컨트롤에서 보낸 창 메시지를 `COleControl` 받지 못하도록 하려면 컨트롤의 부모역할을 하는 추가 창을 만듭니다. "리플렉터"라고 하는 이 추가 창은 Windows 컨트롤을 하위 클래스링하고 컨트롤 창과 동일한 크기와 위치를 가지는 ActiveX 컨트롤에 대해서만 만들어집니다. 리플렉터 창은 특정 창 메시지를 가로채서 컨트롤로 다시 보냅니다. 그런 다음 창 프로시저에서 컨트롤은 ActiveX 컨트롤에 적합한 작업(예: 이벤트 발생)을 수행하여 이러한 반사된 메시지를 처리할 수 있습니다. 가로채는 창 메시지 목록과 해당 반사된 메시지목록은 [반사된 창 메시지 아이디를](../mfc/reflected-window-message-ids.md) 참조하십시오.

ActiveX 컨트롤 컨테이너는 메시지 리플렉션 자체를 수행하도록 `COleControl` 설계되어 리플렉터 창을 만들 필요가 없으며 하위 클래스Windows 컨트롤의 런타임 오버헤드를 줄일 수 있습니다. `COleControl`TRUE **값을**가진 MessageReflect 앰비언트 속성을 확인하여 컨테이너가 이 기능을 지원하는지 여부를 검색합니다.

반사된 창 메시지를 처리하려면 컨트롤 메시지 맵에 항목을 추가하고 처리기 함수를 구현합니다. 반영된 메시지는 Windows에서 정의한 표준 메시지 집합의 일부가 아니므로 클래스 뷰는 이러한 메시지 처리기 추가를 지원하지 않습니다. 그러나 처리기를 수동으로 추가하는 것은 어렵지 않습니다.

반사된 창 메시지에 대한 메시지 처리기를 수동으로 추가하려면 다음을 수행합니다.

- 컨트롤 클래스에서 . H 파일, 처리기 함수를 선언합니다. 함수에는 **WPARAM** 및 **LPARAM**형식이 각각 **WPARAM** 있는 LRESULT 및 두 매개 변수의 반환 형식이 있어야 합니다. 다음은 그 예입니다.

   [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]

- 컨트롤 클래스에서 . CPP 파일을 사용하여 메시지 맵에 ON_MESSAGE 항목을 추가합니다. 이 항목의 매개 변수는 메시지 식별자와 처리기 함수의 이름이어야 합니다. 다음은 그 예입니다.

   [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]

- 또한 . CPP 파일, `OnOcmCommand` 반영 된 메시지를 처리하기 위해 멤버 기능을 구현합니다. *wParam* 및 *lParam* 매개 변수는 원래 창 메시지의 매개 변수와 동일합니다.

반사된 메시지가 처리되는 방법의 예는 MFC ActiveX 컨트롤 샘플 [단추를](../overview/visual-cpp-samples.md)참조하십시오. BN_CLICKED 알림 `OnOcmCommand` 코드를 감지하고 `Click` 이벤트를 발생(전송)하여 응답하는 처리기를 보여 줍니다.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
