---
title: MFC의 OLE
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
ms.openlocfilehash: 2594531df63bcd62cdaec44fbc3668ea68990922
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366892"
---
# <a name="ole-in-mfc"></a>MFC의 OLE

이 문서에서는 MFC를 사용하는 OLE 프로그래밍의 기본 사항을 설명합니다. MFC는 OLE를 사용하는 프로그램을 작성하는 가장 쉬운 방법을 제공합니다.

- OLE 시각적 편집(내부 활성화)을 사용하려면.

- OLE 컨테이너 또는 서버로 작동합니다.

- 끌어서 놓기 기능을 구현합니다.

- 날짜 및 시간 데이터로 작업합니다.

- 내보낸 DLL 함수 진입점, OLE/COM 인터페이스 진입점 및 창 프로시저 진입점을 포함하여 MFC 모듈의 상태 데이터를 관리합니다.

[자동화](../mfc/automation.md)를 사용할 수도 있습니다.

> [!NOTE]
> OLE라는 용어는 OLE 컨테이너, OLE 서버, OLE 항목, 내부 활성화(또는 시각적 편집), 트래커, 끌어서 놓기 및 메뉴 병합을 포함하여 연결 및 포함과 관련된 기술을 나타냅니다. 활성이라는 용어는 구성 요소 개체 모델(COM) 및 ActiveX 컨트롤과 같은 COM 기반 개체에 적용됩니다. OLE 자동화를 이제 자동화라고 합니다.

## <a name="in-this-section"></a>섹션 내용

[OLE 백그라운드](../mfc/ole-background.md)<br/>
OLE에 대해 설명하고 작동 방식에 대한 개념적 정보를 제공합니다.

[활성화](../mfc/activation-cpp.md)<br/>
OLE 항목 편집에서 활성화의 역할을 설명합니다.

[컨테이너](../mfc/containers.md)<br/>
OLE에서 컨테이너를 사용하는 데 대한 링크를 제공합니다.

[데이터 개체 및 데이터 원본](../mfc/data-objects-and-data-sources-ole.md)<br/>
`COleDataObject` 및 `COleDataSource` 클래스의 사용에 대해 논의하는 항목에 대한 링크를 제공합니다.

[끌어서 놓기](../mfc/drag-and-drop-ole.md)<br/>
OLE를 사용하여 복사 및 붙여넣기를 사용하는 것에 대해 설명합니다.

[올레 메뉴 및 리소스](../mfc/menus-and-resources-ole.md)<br/>
MFC OLE 문서 응용 프로그램에서 메뉴 및 리소스의 사용을 설명합니다.

[등록](../mfc/registration.md)<br/>
서버 설치 및 초기화에 대해 설명합니다.

[서버](../mfc/servers.md)<br/>
컨테이너 응용 프로그램에서 사용할 OLE 항목(또는 구성 요소)을 만드는 방법에 대해 설명합니다.

[추적기](../mfc/trackers.md)<br/>
사용자가 OLE `CRectTracker` 클라이언트 항목과 상호 작용할 수 있도록 그래픽 인터페이스를 제공하는 클래스에 대한 정보를 제공합니다.

## <a name="related-sections"></a>관련 단원

[연결 지점](../mfc/connection-points.md)<br/>
MFC 클래스 `CCmdTarget` 및 `CConnectionPoint`을 사용하여 연결 지점(이전의 OLE 연결 지점)을 구현하는 방법을 설명합니다.

[컨테이너/서버 COM 구성 요소](../mfc/containers-advanced-features.md)<br/>
선택적 고급 기능을 기존 컨테이너 응용 프로그램에 통합하는 데 필요한 단계를 설명합니다.

[구성 요소 개체 모델](/windows/win32/com/the-component-object-model)<br/>
MFC 없이 OLE를 사용하는 것을 설명합니다.

## <a name="see-also"></a>참고 항목

[개념](../mfc/mfc-concepts.md)
