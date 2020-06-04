---
title: 'ActiveX 컨트롤 컨테이너: ActiveX 컨트롤에서 보낸 이벤트 처리'
ms.date: 09/12/2018
helpviewer_keywords:
- event handlers [MFC], ActiveX controls
- ActiveX control containers [MFC], event sinks
- event handling [MFC], ActiveX controls
- ON_EVENT macro [MFC]
- ActiveX controls [MFC], events [MFC]
- END_EVENTSINK_MAP macro, using
- events [MFC], ActiveX controls
- BEGIN_EVENTSINK_MAP macro
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
ms.openlocfilehash: ae623ee0973e78db3b542646dd6bdec58cc2dfc8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367946"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX 컨트롤 컨테이너: ActiveX 컨트롤에서 보낸 이벤트 처리

이 문서에서는 클래스 보기에서 **속성** 창(클래스 **보기)을**사용하여 ActiveX 컨트롤 컨테이너에 ActiveX 컨트롤에 대한 이벤트 처리기를 설치하는 방법을 설명합니다. 이벤트 처리기는 특정 이벤트의 알림(컨트롤에서)을 수신하고 응답으로 일부 작업을 수행하는 데 사용됩니다. 이 알림을 이벤트를 "실행"이라고 합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

> [!NOTE]
> 이 문서에서는 컨테이너라는 대화 상자 기반 ActiveX 제어 컨테이너 프로젝트와 Circ라는 임베디드 컨트롤을 프로시저 및 코드의 예로 사용합니다.

**속성** 창(클래스 **보기)의**이벤트 단추를 사용하여 ActiveX 컨트롤 컨테이너 응용 프로그램에서 발생할 수 있는 이벤트 맵을 만들 수 있습니다. "이벤트 싱크 맵'이라고 하는 이 맵은 컨트롤 컨테이너 클래스에 이벤트 처리기를 추가할 때 Visual C++에서 만들어지고 유지 관리됩니다. 이벤트 맵 항목으로 구현된 각 이벤트 처리기는 특정 이벤트를 컨테이너 이벤트 처리기 멤버 함수에 매핑합니다. 이 이벤트 처리기 함수는 ActiveX 컨트롤 개체에서 지정된 이벤트를 발생시 호출합니다.

이벤트 싱크 맵에 대한 자세한 내용은 *클래스 라이브러리 참조의* [이벤트 싱크 맵을](../mfc/reference/event-sink-maps.md) 참조하십시오.

## <a name="event-handler-modifications-to-the-project"></a><a name="_core_event_handler_modifications_to_the_project"></a>프로젝트에 대한 이벤트 처리기 수정

**속성** 창을 사용하여 이벤트 처리기를 추가하면 프로젝트에서 이벤트 싱크 맵이 선언되고 정의됩니다. 다음 명령문이 컨트롤에 추가됩니다. CPP 파일은 이벤트 처리기를 처음 추가합니다. 이 코드는 대화 상자 클래스에 대한 이벤트 싱크 맵을 선언합니다(이 `CContainerDlg`경우)

[!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]

**속성** 창을 사용하여 이벤트를 추가하면 이벤트 맵`ON_EVENT`항목()이 이벤트 싱크 맵에 추가되고 이벤트 처리기 함수가 컨테이너의 구현에 추가됩니다. CPP) 파일.

다음 예제에서는 Circ 컨트롤의 `OnClickInCircCtrl` `ClickIn` 이벤트에 대 한 "라는 이벤트 처리기를 선언 합니다.

[!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]

또한 다음 템플릿이 클래스 구현에 `CContainerDlg` 추가됩니다( CPP) 이벤트 처리기 멤버 함수에 대 한 파일:

[!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]

이벤트 싱크 매크로에 대한 자세한 내용은 클래스 *라이브러리 참조의* [이벤트 싱크 맵을](../mfc/reference/event-sink-maps.md) 참조하십시오.

#### <a name="to-create-an-event-handler-function"></a>이벤트 처리기 함수를 만들려면

1. 클래스 보기에서 ActiveX 컨트롤이 포함된 대화 상자 클래스를 선택합니다. 이 예제에서는 `CContainerDlg`을 사용합니다.

1. **속성** 창에서 **이벤트** 단추를 클릭합니다.

1. **속성** 창에서 포함된 ActiveX 컨트롤의 컨트롤 ID를 선택합니다. 이 예제에서는 `IDC_CIRCCTRL1`을 사용합니다.

   **속성** 창에는 포함된 ActiveX 컨트롤에서 발생시킬 수 있는 이벤트 목록이 표시됩니다. 굵게 표시된 모든 멤버 함수에는 이미 처리기 함수가 할당되어 있습니다.

1. 대화 상자 클래스에서 처리할 이벤트를 선택합니다. 이 예제에서는 **을 클릭을 선택합니다.**

1. 오른쪽의 드롭다운 목록 상자에서 ** \<클릭Circctrl1에> 추가를**선택합니다.

1. 클래스 뷰에서 새 처리기 함수를 두 번 클릭하여 구현에서 이벤트 처리기 코드로 이동합니다. CPP) 파일. `CContainerDlg`

## <a name="see-also"></a>참고 항목

[ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)
