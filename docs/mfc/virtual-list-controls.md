---
title: 가상 목록 컨트롤
ms.date: 11/04/2016
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
ms.openlocfilehash: 1ade5f404e134cf6de20756dcc5af169fefdec76
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375501"
---
# <a name="virtual-list-controls"></a>가상 목록 컨트롤

가상 목록 컨트롤은 LVS_OWNERDATA 스타일을 가지는 목록 보기 컨트롤입니다. 이 스타일을 사용하면 컨트롤에서 **DWORD까지** 항목 수를 지원할 수 있습니다(기본 항목 수는 **int까지만**확장). 그러나 이 스타일에서 제공하는 가장 큰 장점은 한 번에 메모리에 데이터 항목의 하위 집합만 가질 수 있다는 것입니다. 이렇게 하면 가상 목록 보기 컨트롤이 데이터에 액세스하는 특정 방법이 이미 있는 대규모 정보 데이터베이스와 함께 사용할 수 있습니다.

> [!NOTE]
> `CListCtrl`에서 가상 목록 기능을 제공하는 것 외에도 MFC는 [CListView](../mfc/reference/clistview-class.md) 클래스에서 동일한 기능을 제공합니다.

가상 목록 컨트롤을 개발할 때 알아야 할 몇 가지 호환성 문제가 있습니다. 자세한 내용은 Windows SDK의 목록 보기 컨트롤 항목의 호환성 문제 섹션을 참조하십시오.

## <a name="handling-the-lvn_getdispinfo-notification"></a>LVN_GETDISPINFO 알림 처리

가상 목록 컨트롤은 항목 정보를 거의 유지 관리하지 않습니다. 항목 선택 및 포커스 정보를 제외한 모든 항목 정보는 컨트롤 소유자가 관리합니다. 정보는 LVN_GETDISPINFO 알림 메시지를 통해 프레임워크에 의해 요청됩니다. 요청된 정보를 제공하려면 가상 목록 컨트롤(또는 컨트롤 자체)의 소유자가 이 알림을 처리해야 합니다. 이 작업은 [클래스 마법사를](reference/mfc-class-wizard.md) 사용하여 쉽게 수행할 수 [있습니다(메시지에 함수 매핑](../mfc/reference/mapping-messages-to-functions.md)참조). 결과 코드는 다음과 같은 예제와 같아야 합니다(가상 목록 컨트롤 개체를 소유하고 대화 상자가 알림을 처리하는 위치). `CMyDialog`

[!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]

LVN_GETDISPINFO 알림 메시지의 처리기에서 요청되는 정보 유형을 확인해야 합니다. 사용 가능한 값은

- `LVIF_TEXT`*pszText* 멤버를 입력해야 합니다.

- `LVIF_IMAGE`*iImage* 멤버를 입력해야 합니다.

- `LVIF_INDENT`*idindent* 멤버를 채워야 합니다.

- `LVIF_PARAM`*lParam* 멤버를 입력해야 합니다. (하위 항목에는 존재하지 않습니다.)

- `LVIF_STATE`*상태* 멤버를 입력해야 합니다.

그런 다음 프레임워크에 다시 요청된 정보를 제공해야 합니다.

다음 예제(목록 제어 개체에 대한 알림 처리기 본문에서 가져온 값)는 항목의 텍스트 버퍼 및 이미지에 대한 정보를 제공하여 가능한 한 가지 방법을 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]

## <a name="caching-and-virtual-list-controls"></a>캐싱 및 가상 목록 컨트롤

이러한 유형의 목록 컨트롤은 대용량 데이터 집합을 위한 것이기 때문에 검색 성능을 향상시키기 위해 요청된 항목 데이터를 캐시하는 것이 좋습니다. 프레임워크는 LVN_ODCACHEHINT 알림 메시지를 전송하여 캐시를 최적화하는 데 도움이 되는 캐시 힌트 메커니즘을 제공합니다.

다음 예제는 처리기 함수에 전달된 범위로 캐시를 업데이트합니다.

[!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]

캐시 준비 및 유지 관리에 대한 자세한 내용은 Windows SDK의 목록 보기 컨트롤 항목의 캐시 관리 섹션을 참조하십시오.

## <a name="finding-specific-items"></a>특정 항목 찾기

LVN_ODFINDITEM 알림 메시지는 특정 목록 컨트롤 항목을 찾아야 할 때 가상 목록 컨트롤에서 전송됩니다. 알림 메시지는 목록 보기 컨트롤이 빠른 키 액세스를 받거나 LVM_FINDITEM 메시지를 받을 때 전송됩니다. 검색 정보는 **NMLVFINDITEM** 구조의 구성원인 **LVFINDINFO** 구조의 형태로 전송됩니다. 목록 컨트롤 개체의 `OnChildNotify` 함수를 재정의하고 처리기 의 본문 내부에서 이 메시지를 처리하여 LVN_ODFINDITEM 메시지를 확인합니다. 발견된 경우 적절한 작업을 수행합니다.

목록 보기 컨트롤에서 제공한 정보와 일치하는 항목을 검색할 준비를 해야 합니다. 성공한 경우 항목의 인덱스를 반환하거나 일치하는 항목이 없는 경우 -1을 반환해야 합니다.

## <a name="see-also"></a>참고 항목

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
