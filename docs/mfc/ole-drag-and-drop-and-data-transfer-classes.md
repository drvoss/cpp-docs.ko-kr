---
title: OLE 끌어서 놓기 및 데이터 전송 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
ms.openlocfilehash: 7e01b6d5a7d14e0af4ca760e6e601e91359c8ab1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447618"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE 끌어서 놓기 및 데이터 전송 클래스

이러한 클래스는 OLE 데이터 전송에 사용 됩니다. 클립보드를 사용 하거나 끌어서 놓기를 사용 하 여 응용 프로그램 간에 데이터를 전송할 수 있습니다.

[COleDropSource](../mfc/reference/coledropsource-class.md)<br/>
시작부터 끝까지 끌어서 놓기 작업을 제어 합니다. 이 클래스는 끌기 작업이 시작 되는 시기와 종료 될 때를 결정 합니다. 또한 끌어서 놓기 작업 중에 커서 피드백을 표시 합니다.

[COleDataSource](../mfc/reference/coledatasource-class.md)<br/>
응용 프로그램에서 데이터 전송을 위한 데이터를 제공할 때 사용 됩니다. `COleDataSource` 개체 지향 클립보드 개체로 볼 수 있습니다.

[COleDropTarget](../mfc/reference/coledroptarget-class.md)<br/>
끌어서 놓기 작업의 대상을 나타냅니다. `COleDropTarget` 개체는 화면에 있는 창에 해당 합니다. 삭제 된 데이터를 수락할지 여부를 결정 하 고 실제 drop 작업을 구현 합니다.

[COleDataObject](../mfc/reference/coledataobject-class.md)<br/>
`COleDataSource`받는 사람 측으로 사용 됩니다. `COleDataObject` 개체는 `COleDataSource` 개체에 의해 저장 된 데이터에 대 한 액세스를 제공 합니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../mfc/class-library-overview.md)
