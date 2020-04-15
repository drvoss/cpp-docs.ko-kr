---
title: 메시지 맵(MFC)
ms.date: 09/07/2019
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
ms.openlocfilehash: 8080becf1a1a153322bfd03cbd7006eaf2ce4e13
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356570"
---
# <a name="message-maps-mfc"></a>메시지 맵(MFC)

참조의 이 섹션에는 모든 [메시지 매핑 매크로](../../mfc/reference/message-map-macros-mfc.md) 및 모든 [CWnd](../../mfc/reference/cwnd-class.md) 메시지 맵 항목과 해당 멤버 함수 프로토타입이 나열됩니다.

|범주|Description|
|--------------|-----------------|
|ON\_명령 메시지 처리기|사용자 `WM_COMMAND` 메뉴 선택 또는 메뉴 액세스 키에서 생성된 메시지를 처리합니다.|
|[자식 창 알림 메시지 처리기](../../mfc/reference/child-window-notification-message-handlers.md)|자식 창에서 알림 메시지를 처리합니다.|
|[WM_ 메시지 처리기](../../mfc/reference/handlers-for-wm-messages.md)|와 `WM_` 같은 `WM_PAINT`메시지를 처리합니다.|
|[사용자 정의 메시지 처리기](../../mfc/reference/user-defined-handlers.md)|사용자 정의 메시지를 처리합니다.|

이 참조에 사용된 용어 및 규칙에 대한 설명은 [메시지 맵 상호 참조 사용 방법을](../../mfc/reference/how-to-use-the-message-map-cross-reference.md)참조하십시오.

Windows는 메시지 지향 운영 체제이므로 Windows 환경에 대한 프로그래밍의 상당 부분은 메시지 처리와 관련이 있습니다. 키 입력 또는 마우스 클릭과 같은 이벤트가 발생할 때마다 응용 프로그램에 메시지가 전송되어 이벤트를 처리해야 합니다.

Microsoft 파운데이션 클래스 라이브러리는 메시지 기반 프로그래밍에 최적화된 프로그래밍 모델을 제공합니다. 이 모델에서 "메시지 맵"은 특정 클래스에 대해 다양한 메시지를 처리할 함수를 지정하는 데 사용됩니다. 메시지 맵에는 어떤 함수에서 처리할 메시지를 지정하는 하나 이상의 매크로가 포함되어 있습니다. 예를 들어 `ON_COMMAND` 매크로가 포함된 메시지 맵은 다음과 같이 보일 수 있습니다.

[!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]

매크로는 `ON_COMMAND` 메뉴, 단추 및 가속기 키에서 생성된 명령 메시지를 처리하는 데 사용됩니다. [매크로를 사용하여](../../mfc/reference/message-map-macros-mfc.md) 다음을 매핑할 수 있습니다.

## <a name="windows-messages"></a>윈도우 메시지

- 알림 제어

- 사용자 정의 메시지

## <a name="command-messages"></a>명령 메시지

- 등록된 사용자 정의 메시지

- 사용자 인터페이스 업데이트 메시지

## <a name="ranges-of-messages"></a>메시지 범위

- 명령

- 처리기 메시지 업데이트

- 알림 제어

메시지 맵 매크로도 중요하지만 일반적으로 직접 사용할 필요는 없습니다. 이는 Class [마법사가](mfc-class-wizard.md) 메시지 처리 기능을 메시지와 연결하는 데 사용할 때 원본 파일에 메시지 맵 항목을 자동으로 생성하기 때문입니다. 메시지 맵 항목을 편집하거나 추가하려는 경우 언제든지 클래스 마법사를 사용할 수 있습니다.

> [!NOTE]
> 클래스 마법사는 메시지 맵 범위를 지원하지 않습니다. 이러한 메시지 맵 항목을 직접 작성해야 합니다.

그러나 메시지 맵은 Microsoft 재단 클래스 라이브러리의 중요한 부분입니다. 당신은 그들이 무엇을 이해해야하며, 문서가 그들을 위해 제공됩니다.

## <a name="see-also"></a>참고 항목

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
