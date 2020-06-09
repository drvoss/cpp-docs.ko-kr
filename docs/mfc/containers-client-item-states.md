---
title: '컨테이너: 클라이언트 항목 상태'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client-item states
- states, OLE container client-item
- lifetime, lifetime states and OLE container client items
- client items and OLE containers
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
ms.openlocfilehash: 927211ccec35d8ec26e2f76b971c59b80248ab96
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625985"
---
# <a name="containers-client-item-states"></a>컨테이너: 클라이언트 항목 상태

이 문서에서는 클라이언트 항목이 수명 동안 통과 하는 다양 한 상태를 설명 합니다.

클라이언트 항목은 생성, 활성화, 수정 및 저장 될 때 여러 상태를 통과 합니다. 항목의 상태가 변경 될 때마다 프레임 워크는 **OLE_CHANGED_STATE** 알림을 사용 하 여 [COleClientItem:: OnChange](reference/coleclientitem-class.md#onchange) 를 호출 합니다. 두 번째 매개 변수는 열거형의 값입니다 `COleClientItem::ItemState` . 다음 중 하나일 수 있습니다.

- *COleClientItem:: emptyState*

- *COleClientItem:: loadedState*

- *COleClientItem:: openState*

- *COleClientItem:: activeState*

- *COleClientItem:: activeUIState*

비어 있는 상태에서는 클라이언트 항목이 아직 완전히 항목이 아닙니다. 메모리가 할당 되었지만 아직 OLE 항목의 데이터를 사용 하 여 초기화 되지 않았습니다. **새** 에 대 한 호출을 통해 만들어진 클라이언트 항목의 상태 이며, 일반적으로 2 단계 만들기의 두 번째 단계를 거치지 않았습니다.

두 번째 단계에서는 또는 다른 xxxx 함수를 호출 하 여 수행 된 `COleClientItem::CreateFromFile` `CreateFrom` *xxxx* 항목이 완전히 만들어집니다. OLE 데이터 (파일 또는 클립보드와 같은 다른 원본)가 파생 개체와 연결 되어 있습니다 `COleClientItem` . 이제 항목이 로드 된 상태입니다.

항목이 컨테이너의 문서에서 열린 대신 서버 창에서 열린 경우에는 열기 (또는 완전히 열림) 상태에 있습니다. 이 상태에서는 항목이 다른 곳에서 활성 상태임을 나타내기 위해 컨테이너 창의 항목 표현에 대 한 교차 해치를 일반적으로 그립니다.

항목이 활성화 된 후에는 일반적으로 활성 상태를 통해서만 잠시 전달 됩니다. 그런 다음 서버에서 메뉴, 도구 모음 및 기타 사용자 인터페이스 구성 요소를 컨테이너의 항목과 병합 한 UI 활성 상태를 입력 합니다. 이러한 사용자 인터페이스 구성 요소가 있으면 UI 활성 상태와 활성 상태를 구분 합니다. 그렇지 않으면 활성 상태는 UI 활성 상태와 비슷합니다. 서버에서 실행 취소를 지 원하는 경우 서버는 로드 됨 또는 열림 상태에 도달할 때까지 OLE 항목의 실행 취소 상태 정보를 유지 해야 합니다.

## <a name="see-also"></a>참고 항목

[컨테이너](containers.md)<br/>
[활성화](activation-cpp.md)<br/>
[컨테이너: 클라이언트 항목 알림](containers-client-item-notifications.md)<br/>
[추적기](trackers.md)<br/>
[CRectTracker 클래스](reference/crecttracker-class.md)
