---
title: OLE 관련 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
ms.openlocfilehash: dfcc07b3fbd0c5badce8e397f4d52bc7d8d3028c
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447612"
---
# <a name="ole-related-classes"></a>OLE 관련 클래스

이러한 클래스는 예외부터 파일 입력 및 출력에 이르는 다양 한 서비스를 제공 합니다.

[COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)<br/>
다른 컨테이너에서 요청 하는 경우 항목을 만드는 데 사용 됩니다. 이 클래스는 `COleTemplateServer`을 포함 하 여 더 구체적인 팩터리 형식에 대 한 기본 클래스로 사용 됩니다.

[COleMessageFilter](../mfc/reference/colemessagefilter-class.md)<br/>
OLE 경량 원격 프로시저 호출 (LRPC)을 사용 하 여 동시성을 관리 하는 데 사용 됩니다.

[COleStreamFile](../mfc/reference/colestreamfile-class.md)<br/>
는 COM `IStream` 인터페이스를 사용 하 여 복합 파일에 대 한 `CFile` 액세스를 제공 합니다. 이 클래스 (`CFile`에서 파생)를 사용 하면 MFC 직렬화에서 OLE 구조적 저장소를 사용할 수 있습니다.

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
내부 항목의 이동, 크기 조정 및 다시 방향을 허용 하는 데 사용 됩니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../mfc/class-library-overview.md)
