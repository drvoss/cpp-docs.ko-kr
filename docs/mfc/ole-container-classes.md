---
title: OLE 컨테이너 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
ms.openlocfilehash: 61db5310637d13da2d2cc183f12f8f62aa60e328
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447661"
---
# <a name="ole-container-classes"></a>OLE 컨테이너 클래스

이러한 클래스는 컨테이너 응용 프로그램에서 사용 됩니다. `COleLinkingDoc` 및 `COleDocument`는 모두 `COleClientItem` 개체의 컬렉션을 관리 합니다. 문서에 포함 된 개체에 대 한 링크를 지원 하려는 지 여부에 따라 `CDocument`에서 문서 클래스를 파생 하는 대신 `COleLinkingDoc` 또는 `COleDocument`에서 파생 합니다.

`COleClientItem` 개체를 사용 하 여 문서에서 다른 문서에 포함 되거나 다른 문서에 대 한 링크인 각 OLE 항목을 나타냅니다.

[COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)<br/>
액티브 문서 포함을 지원 합니다.

[COleDocument](../mfc/reference/coledocument-class.md)<br/>
기본 컨테이너 지원 뿐만 아니라 복합 문서 구현에 사용 됩니다. `CDocItem`에서 파생 된 클래스의 컨테이너 역할을 합니다. 이 클래스는 컨테이너 문서에 대 한 기본 클래스로 사용 될 수 있으며 `COleServerDoc`의 기본 클래스입니다.

[COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)<br/>
연결을 위한 인프라를 제공 하는 `COleDocument`에서 파생 된 클래스입니다. 포함 된 개체에 대 한 링크를 지원 하려는 경우 `COleDocument` 대신이 클래스에서 컨테이너 응용 프로그램에 대 한 문서 클래스를 파생 시켜야 합니다.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Rich edit 컨트롤에 있는 OLE 클라이언트 항목의 목록을 유지 관리 합니다. [CRichEditView](../mfc/reference/cricheditview-class.md) 및 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)와 함께 사용 됩니다.

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
`COleClientItem` 및 `COleServerItem`의 추상 기본 클래스입니다. `CDocItem`에서 파생 된 클래스의 개체는 문서 부분을 나타냅니다.

[COleClientItem](../mfc/reference/coleclientitem-class.md)<br/>
포함 되거나 연결 된 OLE 항목에 대 한 클라이언트의 연결을 나타내는 클라이언트 항목 클래스입니다. 이 클래스에서 클라이언트 항목을 파생 시킵니다.

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
`CRichEditView` 및 `CRichEditDoc`와 함께 사용할 경우 rich edit 컨트롤에 저장 된 OLE 항목에 대 한 클라이언트 쪽 액세스를 제공 합니다.

[COleException](../mfc/reference/coleexception-class.md)<br/>
OLE 처리 중 오류로 인해 발생하는 예외입니다. 이 클래스는 컨테이너 및 서버에서 모두 사용됩니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../mfc/class-library-overview.md)
