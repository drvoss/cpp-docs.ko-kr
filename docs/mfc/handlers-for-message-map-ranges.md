---
title: 메시지 맵 범위에 대한 처리기
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- handlers [MFC], message-map ranges
- message maps [MFC], message handler functions
- message maps [MFC], ranges
- control-notification messages [MFC]
- command IDs [MFC], message mapping
- message-map ranges [MFC]
- handlers [MFC]
- message handling [MFC], message handler functions
- mappings [MFC], message ranges
- command handling [MFC], command update handlers
- controls [MFC], notifications
- handler functions [MFC], message-map ranges
- handler functions [MFC]
- command update handlers [MFC]
- command routing [MFC], command update handlers
- message ranges [MFC]
- handler functions [MFC], declaring
- message ranges [MFC], mapping
ms.assetid: a271478b-5e1c-46f5-9f29-e5be44b27d08
ms.openlocfilehash: fc33df6957beab6e4e8de3093dfc00cf2651780e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370515"
---
# <a name="handlers-for-message-map-ranges"></a>메시지 맵 범위에 대한 처리기

이 문서에서는 하나의 메시지를 하나의 함수에만 매핑하는 대신 메시지 범위를 단일 메시지 처리기 함수에 매핑하는 방법을 설명합니다.

두 개 이상의 메시지 또는 제어 알림을 정확히 같은 방식으로 처리해야 하는 경우가 있습니다. 이러한 경우 모든 메시지를 단일 처리기 함수에 매핑할 수 있습니다. 메시지 맵 범위를 사용하면 연속된 메시지 범위에 대해 이 작업을 수행할 수 있습니다.

- 명령 아이디의 범위를 다음으로 매핑할 수 있습니다.

  - 명령 처리기 함수입니다.

  - 명령 업데이트 처리기 함수입니다.

- 제어 아이디 범위에 대한 제어 알림 메시지를 메시지 처리기 함수에 매핑할 수 있습니다.

이 문서에서 다루는 주제는 다음과 같습니다.

- [메시지 맵 항목 작성](#_core_writing_the_message.2d.map_entry)

- [처리기 함수 선언](#_core_declaring_the_handler_function)

- [명령 아이디 범위의 예](#_core_example_for_a_range_of_command_ids)

- [제어 아이디 범위의 예](#_core_example_for_a_range_of_control_ids)

## <a name="writing-the-message-map-entry"></a><a name="_core_writing_the_message.2d.map_entry"></a>메시지 맵 항목 작성

안에. 다음 예제와 같이 메시지 맵 항목을 추가합니다.

[!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]

메시지 맵 항목은 다음 항목으로 구성됩니다.

- 메시지 맵 범위 매크로:

  - [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)

  - [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)

  - [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)

- 매크로에 대한 매개 변수:

  처음 두 매크로는 세 가지 매개 변수를 사용합니다.

  - 범위를 시작하는 명령 ID

  - 범위를 종료하는 명령 ID

  - 메시지 처리기 함수의 이름

  명령 아이디의 범위는 연속적이어야 합니다.

  세 번째 `ON_CONTROL_RANGE`매크로는 **EN_CHANGE**와 같은 컨트롤 알림 메시지와 같은 추가 첫 번째 매개 변수를 사용합니다.

## <a name="declaring-the-handler-function"></a><a name="_core_declaring_the_handler_function"></a>처리기 함수 선언

에서 처리기 함수 선언을 추가합니다. H 파일. 다음 코드는 아래와 같이 어떻게 보일지 보여줍니다.

[!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_2.h)]

단일 명령에 대한 처리기 함수는 일반적으로 매개 변수를 사용하지 않습니다. 업데이트 처리기 함수를 제외한 메시지 맵 범위에 대한 처리기 함수에는 **UINT**형식의 추가 매개 변수 *인 nID가*필요합니다. 이 매개 변수는 첫 번째 매개 변수입니다. 추가 매개 변수는 사용자가 실제로 선택한 명령을 지정하는 데 필요한 추가 명령 ID를 수용합니다.

처리기 함수 업데이트에 대한 매개 변수 요구 사항에 대한 자세한 내용은 [명령 범위 의 예제를](#_core_example_for_a_range_of_command_ids)참조하십시오.

## <a name="example-for-a-range-of-command-ids"></a><a name="_core_example_for_a_range_of_command_ids"></a>명령 범위 의 예

범위를 사용할 수 있는 경우 한 예는 MFC 샘플 [HIERSVR의](../overview/visual-cpp-samples.md)확대/축소 명령과 같은 명령을 처리하는 예제입니다. 이 명령은 뷰를 확대하여 일반 크기의 25%에서 300% 사이로 배율을 조정합니다. HIERSVR의 뷰 클래스는 범위를 사용하여 다음과 유사한 메시지 맵 항목으로 확대/축소 명령을 처리합니다.

[!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]

메시지 맵 항목을 작성할 때 다음을 지정합니다.

- 연속 된 범위를 시작하고 끝나는 두 개의 명령 아이디입니다.

   여기에 그들은 **ID_VIEW_ZOOM25** **ID_VIEW_ZOOM300**.

- 명령에 대 한 처리기 함수의 이름입니다.

   여기 `OnZoom`있습니다.

함수 선언은 다음과 유사합니다.

[!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_4.h)]

업데이트 처리기 함수의 경우는 비슷하며 더 널리 유용할 수 있습니다. 여러 명령에 대한 처리기를 작성하고 `ON_UPDATE_COMMAND_UI` 동일한 코드를 반복해서 작성하거나 복사하는 것이 일반적입니다. 해결 방법은 매크로를 사용하여 명령 ID범위를 하나의 업데이트 `ON_UPDATE_COMMAND_UI_RANGE` 처리기 함수에 매핑하는 것입니다. 명령 아이디는 연속 범위를 형성해야 합니다. 예를 들어 HIERSVR 샘플의 `OnUpdateZoom` 보기 클래스에서 처리기 및 메시지 `ON_UPDATE_COMMAND_UI_RANGE` 맵 항목을 참조하십시오.

단일 명령에 대한 업데이트 처리기 함수는 일반적으로 형식의 `CCmdUI*`단일 매개 변수 인 *pCmdUI를*사용합니다. 처리기 함수와 달리 메시지 맵 범위에 대한 업데이트 처리기 함수에는 **UINT**형식의 추가 매개 변수 *nID가*필요하지 않습니다. 사용자가 실제로 선택한 명령을 지정하는 데 필요한 명령 ID가 `CCmdUI` 개체에서 찾을 수 있습니다.

## <a name="example-for-a-range-of-control-ids"></a><a name="_core_example_for_a_range_of_control_ids"></a>제어 범위 의 예

또 다른 흥미로운 경우는 컨트롤 아이디 범위에 대한 제어 알림 메시지를 단일 처리기에 매핑하는 것입니다. 사용자가 10개의 단추 중 하나를 클릭할 수 있다고 가정합니다. 10개의 단추를 모두 하나의 처리기에 매핑하려면 메시지 맵 항목은 다음과 같습니다.

[!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]

메시지 맵에 `ON_CONTROL_RANGE` 매크로를 작성할 때 다음을 지정합니다.

- 특정 제어 알림 메시지입니다.

   여기 **BN_CLICKED**.

- 연속된 컨트롤 범위와 연결된 제어 ID 값입니다.

   여기에 **이것들이 IDC_BUTTON1** **IDC_BUTTON10.**

- 메시지 처리기 함수의 이름입니다.

   여기 `OnButtonClicked`있습니다.

처리기 함수를 작성할 때 다음과 같이 추가 **UINT** 매개 변수를 지정합니다.

[!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]

단일 `OnButtonClicked` **BN_CLICKED** 메시지에 대한 처리기는 매개 변수를 사용하지 않습니다. 단추 범위에 대해 동일한 처리기는 하나의 **UINT를**수행합니다. 추가 매개 변수를 사용하면 BN_CLICKED 메시지를 생성하는 특정 컨트롤을 식별할 **수** 있습니다.

예제에 표시된 코드는 일반적으로 전달된 값을 메시지 `int` 범위 내에서 변환하고 이것이 사실임을 어설션합니다. 그런 다음 클릭한 단추에 따라 몇 가지 다른 작업을 수행할 수 있습니다.

## <a name="see-also"></a>참고 항목

[메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)
