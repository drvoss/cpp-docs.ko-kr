---
title: 활성화(C++)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], activation
- OLE items [MFC], visual editing
- activation [MFC]
- OLE [MFC], in-place activation
- OLE [MFC], activation
- in-place activation, embedded and linked items
- activating objects
- visual editing, activation
- visual editing
- documents [MFC], OLE
- embedded objects [MFC]
- OLE [MFC], editing
- in-place activation
- activation [MFC], embedded OLE items
- OLE activation [MFC]
ms.assetid: ed8357d9-e487-4aaa-aa6b-2edc4de25dfa
ms.openlocfilehash: 9f3fba71002a19a0be0e3429a0faeeefb7c65197
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354175"
---
# <a name="activation-c"></a>활성화(C++)

이 문서에서는 OLE 항목의 시각적 편집에서 활성화의 역할을 설명합니다. 사용자가 컨테이너 문서에 OLE 항목을 포함한 후 사용해야 할 수 있습니다. 이렇게 하려면 사용자가 항목을 두 번 클릭하여 해당 항목을 활성화합니다. 정품 인증에 가장 자주 발생하는 작업은 편집입니다. 편집을 위해 활성화된 많은 현재 OLE 항목으로 인해 현재 프레임 창의 메뉴와 도구 모음이 항목을 만든 서버 응용 프로그램에 속한 항목을 반영하도록 변경됩니다. 내부 활성화라고 하는 이 동작을 사용하면 컨테이너 문서의 창을 벗어나지 않고도 복합 문서에 포함된 항목을 편집할 수 있습니다.

포함된 OLE 항목을 별도의 창에서 편집할 수도 있습니다. 컨테이너 또는 서버 응용 프로그램이 내부 활성화를 지원하지 않는 경우 이 와 같은 일이 발생합니다. 이 경우 사용자가 포함된 항목을 두 번 클릭하면 서버 응용 프로그램이 별도의 창에서 시작되고 포함된 항목이 자체 문서로 나타납니다. 사용자는 이 창에서 항목을 편집합니다. 편집이 완료되면 사용자는 서버 응용 프로그램을 닫고 컨테이너 응용 프로그램으로 돌아갑니다.

또는 사용자는 **편집** 메뉴에서 ** \<개체> 열기** 명령을 통해 "열기 편집"을 선택할 수 있습니다. 그러면 별도의 창에서 개체가 열립니다.

> [!NOTE]
> 별도의 창에서 포함된 항목을 편집하는 것은 OLE 버전 1의 표준 동작이었으며 일부 OLE 응용 프로그램은 이 편집 스타일만 지원할 수 있습니다.

내부 활성화는 문서 작성에 대한 문서 중심 접근 방식을 촉진합니다. 사용자는 응용 프로그램 간에 전환하지 않고 복합 문서를 단일 엔터티로 처리하여 작업할 수 있습니다. 그러나 내부 활성화는 연결된 항목이 아닌 포함된 항목에만 사용됩니다. 연결된 항목은 실제로 다른 위치에 저장되어 있기 때문입니다. 연결된 항목의 편집은 데이터의 실제 컨텍스트, 즉 데이터가 저장되는 위치 내에서 이루어집니다. 연결된 항목을 별도의 창에서 편집하면 데이터가 다른 문서에 속한다는 것을 사용자에게 상기시킵니다.

MFC는 중첩된 내부 활성화를 지원하지 않습니다. 컨테이너/서버 응용 프로그램을 빌드하고 해당 컨테이너/서버가 다른 컨테이너에 내장되어 있고 내부 활성화된 경우 컨테이너 내에 포함된 개체를 내부로 활성화할 수 없습니다.

사용자가 두 번 클릭하면 포함된 항목에 어떤 일이 발생합니까는 항목에 대해 정의된 동사에 따라 다릅니다. 자세한 내용은 [활성화: 동사를](../mfc/activation-verbs.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[OLE](../mfc/ole-in-mfc.md)<br/>
[컨테이너](../mfc/containers.md)<br/>
[서버](../mfc/servers.md)
