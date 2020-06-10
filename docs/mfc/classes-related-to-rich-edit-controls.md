---
title: Rich Edit 컨트롤 관련 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], and CRichEditItem
- CRichEditCtrl class [MFC], related classes
- CRichEditDoc class [MFC], Rich Edit controls
- rich edit controls [MFC], classes related to
- classes [MFC], related to rich edit controls
- rich edit controls [MFC], and CRichEditView
- CRichEditCtrlItem class and CRichEditCtrl
- rich edit controls [MFC], and CRichEditDoc
- CRichEditView class [MFC], and CRichEditCtrl
ms.assetid: 4b31c2cc-6ea1-4146-b7c5-b0b5b419f14d
ms.openlocfilehash: 584649a2bb2d9a118e390aebf9f7411c3123b1a3
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620721"
---
# <a name="classes-related-to-rich-edit-controls"></a>Rich Edit 컨트롤 관련 클래스

[CRichEditView](reference/cricheditview-class.md), [CRichEditDoc](reference/cricheditdoc-class.md)및 [CRichEditCntrItem](reference/cricheditcntritem-class.md) 클래스는 MFC의 문서/뷰 아키텍처 컨텍스트 내에서 rich edit 컨트롤 ([CRichEditCtrl](reference/cricheditctrl-class.md))의 기능을 제공 합니다. `CRichEditView`텍스트의 텍스트와 서식 특성을 유지 합니다. `CRichEditDoc`뷰에 있는 OLE 클라이언트 항목의 목록을 유지 관리 합니다. `CRichEditCntrItem`OLE 클라이언트 항목에 대 한 컨테이너 쪽 액세스를 제공 합니다. 의 내용을 수정 하려면 `CRichEditView` [CRichEditView:: GetRichEditCtrl](reference/cricheditview-class.md#getricheditctrl) 를 사용 하 여 기본 rich edit 컨트롤에 액세스 합니다.

## <a name="see-also"></a>참고 항목

[CRichEditCtrl 사용](using-cricheditctrl.md)<br/>
[컨트롤](controls-mfc.md)
