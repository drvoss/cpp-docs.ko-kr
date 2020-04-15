---
title: 'MFC ActiveX 컨트롤: 사용자 지정 이벤트 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], events [MFC]
- EVENT_CUSTOM prefix [MFC]
- custom events [MFC], adding to ActiveX controls
- EVENT_CUSTOM macro [MFC]
- InCircle method [MFC]
- ClickIn event
- FireClickIn event
- COleControl class [MFC], custom events [MFC]
- Click event, custom events [MFC]
- events [MFC], ActiveX controls
- custom events [MFC]
- FireEvent method, adding custom events
ms.assetid: c584d053-1e34-47aa-958e-37d3e9b85892
ms.openlocfilehash: 8d464e5d7c9731e158e44d66d569fd1555401e17
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364725"
---
# <a name="mfc-activex-controls-adding-custom-events"></a>MFC ActiveX 컨트롤: 사용자 지정 이벤트 추가

사용자 지정 이벤트는 클래스에 `COleControl`의해 자동으로 발생되지 않는다는 점에서 스톡 이벤트와 다릅니다. 사용자 지정 이벤트는 컨트롤 개발자가 결정한 특정 작업을 이벤트로 인식합니다. 사용자 지정 이벤트에 대한 이벤트 맵 항목은 EVENT_CUSTOM 매크로로 표시됩니다. 다음 섹션에서는 ActiveX 컨트롤 마법사를 사용하여 만든 ActiveX 제어 프로젝트에 대한 사용자 지정 이벤트를 구현합니다.

## <a name="adding-a-custom-event-with-the-add-event-wizard"></a><a name="_core_adding_a_custom_event_with_classwizard"></a>이벤트 추가 마법사를 통해 사용자 지정 이벤트 추가

다음 절차는 특정 사용자 지정 이벤트인 ClickIn을 추가합니다. 이 절차를 사용하여 다른 사용자 지정 이벤트를 추가할 수 있습니다. 사용자 지정 이벤트 이름과 해당 매개 변수를 ClickIn 이벤트 이름 및 매개 변수로 대체합니다.

#### <a name="to-add-the-clickin-custom-event-using-the-add-event-wizard"></a>이벤트 추가 마법사를 사용하여 ClickIn 사용자 지정 이벤트를 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. **클래스 보기에서**ActiveX 컨트롤 클래스를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **추가를** 클릭한 다음 **이벤트 추가를**클릭합니다.

   그러면 이벤트 추가 마법사가 열립니다.

1. 이벤트 **이름** 상자에서 먼저 기존 이벤트를 선택한 다음 **사용자 지정** 라디오 단추를 클릭한 다음 *ClickIn*을 입력합니다.

1. 내부 **이름** 상자에 이벤트 의 발생 함수 이름을 입력합니다. 이 예제에서는 이벤트 마법사 추가()에서`FireClickIn`제공하는 기본값을 사용합니다.

1. 매개 변수 이름 및 매개 변수 *OLE_XPOS_PIXELS*유형 컨트롤을 사용하여 *xCoord(OLE_XPOS_PIXELS* 형식)라는 **매개 변수를** **추가합니다.**

1. *yCoord* (유형 *OLE_YPOS_PIXELS)라는*두 번째 매개 변수를 추가합니다.

1. **완료를** 클릭하여 이벤트를 만듭니다.

## <a name="add-event-wizard-changes-for-custom-events"></a><a name="_core_classwizard_changes_for_custom_events"></a>사용자 지정 이벤트에 이벤트 마법사 변경 내용 추가

사용자 지정 이벤트를 추가하면 이벤트 추가 마법사에서 컨트롤 클래스를 변경합니다. H. CPP 및 . IDL 파일. 다음 코드 샘플은 ClickIn 이벤트와 관련이 있습니다.

다음 줄이 헤더에 추가됩니다( H) 컨트롤 클래스의 파일:

[!code-cpp[NVC_MFC_AxUI#7](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_1.h)]

이 코드는 클릭인 이벤트와 이벤트 추가 마법사를 사용하여 정의한 매개 변수를 사용하여 `FireClickIn` [COleControl::FireEvent를](../mfc/reference/colecontrol-class.md#fireevent) 호출하는 인라인 함수를 선언합니다.

또한, 다음 줄은 구현에 있는 컨트롤에 대한 이벤트 맵에 추가된다( CPP) 컨트롤 클래스의 파일:

[!code-cpp[NVC_MFC_AxUI#8](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_2.cpp)]

이 코드는 이벤트 클릭인 을 `FireClickIn`인라인 함수에 매핑하여 이벤트 마법사 추가를 사용하여 정의한 매개 변수를 전달합니다.

마지막으로 컨트롤의 에 다음 줄이 추가됩니다. IDL 파일:

[!code-cpp[NVC_MFC_AxUI#9](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_3.idl)]

이 줄은 이벤트 마법사 추가 이벤트 목록에서 이벤트의 위치에서 가져온 특정 ID 번호를 ClickIn 이벤트에 할당합니다. 이벤트 목록의 항목을 사용하면 컨테이너가 이벤트를 예측할 수 있습니다. 예를 들어 이벤트가 발생했을 때 실행할 처리기 코드를 제공할 수 있습니다.

## <a name="calling-fireclickin"></a><a name="_core_calling_fireclickin"></a>호출 파이어클릭인

이벤트 추가 마법사를 사용하여 ClickIn 사용자 지정 이벤트를 추가한 후 이 이벤트가 발생할 시기를 결정해야 합니다. 적절한 작업이 발생할 `FireClickIn` 때 호출하여 이 작업을 수행합니다. 이 설명의 경우 컨트롤은 `InCircle` `WM_LBUTTONDOWN` 사용자가 원형 또는 타원형 영역 내에서 클릭할 때 메시지 처리기 내부의 함수를 사용하여 ClickIn 이벤트를 발생시킵니다. 다음 절차는 처리기를 추가합니다. `WM_LBUTTONDOWN`

#### <a name="to-add-a-message-handler-with-the-add-event-wizard"></a>이벤트 추가 마법사를 사용하여 메시지 처리기를 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. **클래스 보기에서**ActiveX 컨트롤 클래스를 선택합니다.

1. **속성** 창에는 ActiveX 컨트롤에서 처리할 수 있는 메시지 목록이 표시됩니다. 굵게 표시된 모든 메시지에는 이미 처리기 함수가 할당되어 있습니다.

1. 처리할 메시지를 선택합니다. 이 예제에서는 `WM_LBUTTONDOWN`을 선택합니다.

1. 오른쪽의 드롭다운 목록 상자에서 ** \<> OnLButtonDown 추가를**선택합니다.

1. **클래스 뷰에서** 새 처리기 함수를 두 번 클릭하여 구현에서 메시지 처리기 코드로 이동합니다. CPP) ActiveX 컨트롤의 파일입니다.

다음 코드 샘플은 `InCircle` 컨트롤 창 내에서 왼쪽 마우스 단추를 클릭할 때마다 함수를 호출합니다. 이 샘플은 [Circ 샘플](../overview/visual-cpp-samples.md) `OnLButtonDown`요약의 `WM_LBUTTONDOWN` handler 함수 에서 찾을 수 있습니다.

[!code-cpp[NVC_MFC_AxUI#10](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_4.cpp)]

> [!NOTE]
> 이벤트 추가 마법사에서 마우스 단추 작업에 대한 메시지 처리기를 만들면 기본 클래스의 동일한 메시지 처리기에 대한 호출이 자동으로 추가됩니다. 이 호출을 제거하지 마십시오. 컨트롤에서 스톡 마우스 메시지를 사용하는 경우 기본 클래스의 메시지 처리기를 호출하여 마우스 캡처가 제대로 처리되도록 해야 합니다.

다음 예제에서는 컨트롤 내의 원형 또는 타원형 영역 내에서 클릭이 발생하는 경우에만 이벤트가 발생합니다. 이 동작을 수행하려면 컨트롤의 구현에 `InCircle` 함수를 배치할 수 있습니다. CPP) 파일:

[!code-cpp[NVC_MFC_AxUI#11](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_5.cpp)]

또한 컨트롤의 헤더에 함수의 `InCircle` 다음 선언을 추가해야 합니다. H) 파일:

[!code-cpp[NVC_MFC_AxUI#12](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_6.h)]

## <a name="custom-events-with-stock-names"></a><a name="_core_custom_events_with_stock_names"></a>주식 이름이 있는 사용자 지정 이벤트

스톡 이벤트와 이름이 같은 사용자 지정 이벤트를 만들 수 있지만 동일한 컨트롤에서 둘 다 구현할 수는 없습니다. 예를 들어 주식 이벤트가 일반적으로 발생할 때 발생하지 않는 Click이라는 사용자 지정 이벤트를 만들 수 있습니다. 그런 다음 언제든지 클릭 이벤트를 실행 함수를 호출하여 발생시킬 수 있습니다.

다음 절차에서 사용자 지정 Click 이벤트가 추가됩니다.

#### <a name="to-add-a-custom-event-that-uses-a-stock-event-name"></a>주식 이벤트 이름을 사용하는 사용자 지정 이벤트를 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. **클래스 보기에서**ActiveX 컨트롤 클래스를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **추가를** 클릭한 다음 **이벤트 추가를**클릭합니다.

   그러면 이벤트 추가 마법사가 열립니다.

1. 이벤트 **이름** 드롭다운 목록에서 스톡 이벤트 이름을 선택합니다. 이 예제에서는 **을 클릭을 선택합니다.**

1. **이벤트 유형의**경우 사용자 지정 을 **선택합니다.**

1. **완료를** 클릭하여 이벤트를 만듭니다.

1. 코드의 적절한 장소에서 호출합니다. `FireClick`

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)<br/>
[콜레컨트롤 클래스](../mfc/reference/colecontrol-class.md)
