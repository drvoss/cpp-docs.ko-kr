---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤에 스톡 이벤트 추가'
ms.date: 11/04/2016
f1_keywords:
- EVENT__STOCK_ERROR
- EVENT__STOCK_READYSTATECHANGE
- ReadyStateChange
- EVENT__STOCK_MOUSEMOVE
- EVENT__STOCK_MOUSEUP
- EVENT__STOCK_DBLCLICK
- KeyPress
- EVENT__STOCK_KEYDOWN
- EVENT__STOCK
- EVENT__STOCK_MOUSEDOWN
- EVENT__STOCK_KEYPRESS
- EVENT__STOCK_CLICK
- EVENT__STOCK_KEYUP
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- KeyPress event
- FireDblClick event
- FireMouseDown event
- events [MFC], stock
- FireKeyPress event
- EVENT_STOCK_MOUSEMOVE event
- EVENT_STOCK_CLICK event
- FireClick event
- FireKeyUp event
- FireMouseUp event
- EVENT_STOCK_ERROREVENT event
- EVENT_STOCK_KEYDOWN event
- EVENT_STOCK_MOUSEDOWN event
- EVENT_STOCK_KEYPRESS macro [MFC]
- EVENT_STOCK_KEYUP event
- EVENT_STOCK_DBLCLICK event
- FireError event
- FireKeyDown event
- ReadyStateChange event
- EVENT_STOCK_MOUSEUP event
- FireMouseMove event
- EVENT_STOCK prefix
- EVENT_STOCK_READYSTATECHANGE event
- EVENT_STOCK_KEYPRESS event
ms.assetid: 3eeadc67-4b3d-4444-8caa-53054073988a
ms.openlocfilehash: 79cd4fc572e55c67cc5a2cfe3a00e04f2a4a7850
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364682"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤에 스톡 이벤트 추가

스톡 이벤트는 클래스 [COleControl에](../mfc/reference/colecontrol-class.md)의해 자동으로 발생한다는 점에서 사용자 지정 이벤트와 다릅니다. `COleControl`에는 일반적인 작업으로 인한 이벤트를 발생시키는 미리 정의된 멤버 함수가 포함되어 있습니다. 컨트롤, 키보드 `COleControl` 이벤트 및 마우스 단추 상태의 변경 사항에 대해 한 번 클릭하고 두 번 클릭하는 등 구현된 몇 가지 일반적인 작업에는 다음과 같은 몇 가지 일반적인 작업이 포함됩니다. 스톡 이벤트에 대한 이벤트 맵 항목은 항상 EVENT_STOCK 접두사 앞에 옵니다.

## <a name="stock-events-supported-by-the-add-event-wizard"></a><a name="_core_stock_events_supported_by_classwizard"></a>이벤트 추가 마법사에서 지원하는 스톡 이벤트

클래스는 `COleControl` 다음 표에 나열된 10개의 스톡 이벤트를 제공합니다. [이벤트 마법사 추가를](../ide/add-event-wizard.md)사용하여 컨트롤에서 원하는 이벤트를 지정할 수 있습니다.

### <a name="stock-events"></a>스톡 이벤트

|이벤트|발사 기능|주석|
|-----------|---------------------|--------------|
|그런 다음|**무효 파이어클릭 () )**|컨트롤이 마우스를 캡처할 때 **BUTTONUP(왼쪽,** 가운데 또는 오른쪽) 메시지가 수신되고 컨트롤을 통해 버튼이 해제될 때 발생합니다. 주식 마우스다운 및 MouseUp 이벤트는 이 이벤트 전에 발생합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_CLICK()**|
|Dblclick|**무효 파이어드블클릭 () )**|클릭과 유사하지만 **BUTTONDBLCLK** 메시지가 수신될 때 발생합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_DBLCLICK()**|
|Error|**무효 FireError (코드***코드,* **LPCSTR,** `lpszDescription` **UINT**`nHelpID`=**0)**        |메서드 호출 또는 속성 액세스 범위를 벗어나 ActiveX 컨트롤 내에서 오류가 발생할 때 발생합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_ERROREVENT()**|
|Keydown|**보이드 파이어키다운(짧은,** `nChar` **짧은)**`nShiftState`**)**      |`WM_SYSKEYDOWN` 또는 `WM_KEYDOWN` 메시지가 수신될 때 발생합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_KEYDOWN()**|
|Keypress|**보이드 파이어키프레스 (짧은)** <strong>\*</strong> `pnChar` **)**    |메시지가 수신되면 발생합니다. `WM_CHAR`<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_KEYPRESS()**|
|Keyup|**보이드 파이어키업(짧은,** `nChar` **짧은)**`nShiftState`**)**      |`WM_SYSKEYUP` 또는 `WM_KEYUP` 메시지가 수신될 때 발생합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_KEYUP()**|
|Mousedown|**보이드 파이어마우스다운(짧고** `nButton` **짧고,** `nShiftState` **부동***x,* **플로트***y)***)**          |**BUTTONDOWN(왼쪽,** 가운데 또는 오른쪽)이 수신되면 발생합니다. 이 이벤트가 발생하기 직전에 마우스가 캡처됩니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_MOUSEDOWN()**|
|Mousemove|**보이드 파이어마우스무브 (짧고,** `nButton` `nShiftState` **짧고, 부동***x,* **플로트***y)***)** **, short**          |WM_MOUSEMOVE 메시지가 수신되면 발생합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_MOUSEMOVE()**|
|Mouseup|**보이드 파이어마우스업(짧고** `nButton` `nShiftState` **짧고, 부동***x,* **플로트***y)***)** **, short**          |**BUTTONUP(왼쪽,** 가운데 또는 오른쪽)이 수신되면 발생합니다. 마우스 캡처는 이 이벤트가 발생하기 전에 해제됩니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_MOUSEUP()**|
|준비 상태 변경|**보이드 파이어레디스테이트변경() )**|수신된 데이터의 양으로 인해 컨트롤이 다음 준비 상태로 전환될 때 발생합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_READYSTATECHANGE()**|

## <a name="adding-a-stock-event-using-the-add-event-wizard"></a><a name="_core_adding_a_stock_event_using_classwizard"></a>이벤트 추가 마법사를 사용하여 스톡 이벤트 추가

스톡 이벤트를 추가하려면 기본 클래스에서 실제 이벤트 발생이 자동으로 처리되므로 사용자 `COleControl`지정 이벤트를 추가하는 것보다 작업이 적습니다. 다음 절차는 [MFC ActiveX 컨트롤 마법사를](../mfc/reference/mfc-activex-control-wizard.md)사용하여 개발된 컨트롤에 주식 이벤트를 추가합니다. 키프레스(KeyPress)라고 하는 이벤트는 키를 누르고 컨트롤이 활성화되면 발생합니다. 이 절차는 다른 스톡 이벤트를 추가하는 데도 사용할 수 있습니다. 선택한 스톡 이벤트 이름을 KeyPress로 대체합니다.

#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>이벤트 추가 마법사를 사용하여 KeyPress 스톡 이벤트를 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 보기에서 ActiveX 컨트롤 클래스를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **추가를** 클릭한 다음 **이벤트 추가를**클릭합니다.

   그러면 이벤트 추가 마법사가 열립니다.

1. 이벤트 **이름** 드롭다운 목록에서 을 `KeyPress`선택합니다.

1. **Finish**를 클릭합니다.

## <a name="add-event-wizard-changes-for-stock-events"></a><a name="_core_classwizard_changes_for_stock_events"></a>주식 이벤트에 대한 이벤트 마법사 변경 내용 추가

스톡 이벤트는 컨트롤의 기본 클래스에서 처리되므로 이벤트 추가 마법사는 클래스 선언을 어떤 식으로든 변경하지 않습니다. 컨트롤의 이벤트 맵에 이벤트를 추가하고 에 항목을 만듭니다. IDL 파일입니다. 다음 줄은 컨트롤 클래스 구현에 있는 컨트롤의 이벤트 맵에 추가됩니다. CPP) 파일:

[!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]

이 코드를 추가하면 WM_CHAR 메시지가 수신되고 컨트롤이 활성화되면 KeyPress 이벤트가 발생합니다. KeyPress 이벤트는 제어 코드 내에서 발사 `FireKeyPress`함수(예:)를 호출하여 다른 시간에 발생할 수 있습니다.

이벤트 추가 마법사는 컨트롤의 에 다음 코드 줄을 추가합니다. IDL 파일:

[!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]

이 줄은 KeyPress 이벤트를 표준 디스패치 ID와 연결하며 컨테이너가 KeyPress 이벤트를 예상할 수 있도록 합니다.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)<br/>
[콜레컨트롤 클래스](../mfc/reference/colecontrol-class.md)
