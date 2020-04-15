---
title: MFC에서 사용할 수 있는 파생된 뷰 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
ms.openlocfilehash: 12b31074e4fcc2ed6a83e3669e1044f5b9caedab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373496"
---
# <a name="derived-view-classes-available-in-mfc"></a>MFC에서 사용할 수 있는 파생된 뷰 클래스

다음 표에서는 MFC의 뷰 클래스와 서로의 관계를 보여 주었습니다. 뷰 클래스의 기능은 뷰 클래스가 파생되는 MFC 뷰 클래스에 따라 다릅니다.

### <a name="view-classes"></a>수업 보기

|클래스|Description|
|-----------|-----------------|
|[CView](../mfc/reference/cview-class.md)|모든 뷰의 기본 클래스입니다.|
|[CCtrlView](../mfc/reference/cctrlview-class.md)|의 `CTreeView`기본 `CListView`클래스 `CEditView`. `CRichEditView` 이러한 클래스를 사용하면 표시된 Windows 공통 컨트롤을 사용하여 문서/뷰 아키텍처를 사용할 수 있습니다.|
|[CEditView](../mfc/reference/ceditview-class.md)|Windows 편집 상자 컨트롤을 기반으로 하는 간단한 보기입니다. 텍스트를 입력하고 편집할 수 있으며 간단한 텍스트 편집기 응용 프로그램의 기초로 사용할 수 있습니다. `CRichEditView`도 참조하세요.|
|[CRichEditView](../mfc/reference/cricheditview-class.md)|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) 개체를 포함하는 뷰입니다. 이 클래스는 `CEditView`과 유사하지만 `CEditView` `CRichEditView` 와 는 달리 서식이 지정된 텍스트를 처리합니다.|
|[CListView](../mfc/reference/clistview-class.md)|[CListCtrl](../mfc/reference/clistctrl-class.md) 개체를 포함하는 보기입니다.|
|[CTreeView](../mfc/reference/ctreeview-class.md)|시각적 C++의 솔루션 탐색기 창과 유사한 뷰에 대해 [CTreeCtrl](../mfc/reference/ctreectrl-class.md) 개체가 포함된 보기입니다.|
|[CScrollView](../mfc/reference/cscrollview-class.md)|의 `CFormView`기본 `CRecordView`클래스 `CDaoRecordView`입니다. 뷰의 내용을 스크롤하는 구현합니다.|
|[CFormView](../mfc/reference/cformview-class.md)|폼 보기, 컨트롤을 포함 하는 보기입니다. 양식 기반 응용 프로그램은 하나 이상의 양식 인터페이스를 제공합니다.|
|[CHtmlView](../mfc/reference/chtmlview-class.md)|응용 프로그램의 사용자가 월드 와이드 웹의 사이트뿐만 아니라 로컬 파일 시스템 및 네트워크의 폴더를 탐색할 수 있는 웹 브라우저 보기입니다. 웹 브라우저 보기는 활성 문서 컨테이너로도 작동할 수 있습니다.|
|[CRecordView](../mfc/reference/crecordview-class.md)|컨트롤에 ODBC 데이터베이스 레코드를 표시하는 양식 보기입니다. 프로젝트에서 ODBC 지원을 선택하면 뷰의 기본 클래스가 `CRecordView`됩니다. 뷰가 `CRowset` 객체에 연결됩니다.|
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|컨트롤에 DAO 데이터베이스 레코드를 표시하는 양식 보기입니다. 프로젝트에서 DAO 지원을 선택하면 뷰의 기본 클래스가 `CDaoRecordView`입니다. 뷰가 `CDaoRecordset` 객체에 연결됩니다.|
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|컨트롤에 OLE DB 레코드를 표시하는 양식 보기입니다. 프로젝트에서 OLE DB 지원을 선택하면 뷰의 기본 클래스가 `COleDBRecordView`입니다. 뷰가 `CRowset` 객체에 연결됩니다.|

> [!NOTE]
> MFC 버전 4.0을 `CEditView` 현재 `CCtrlView`에서 파생됩니다.

응용 프로그램에서 이러한 클래스를 사용하려면 응용 프로그램의 뷰 클래스를 파생합니다. 관련 정보는 [스크롤 및 크기 조정 뷰를](../mfc/scrolling-and-scaling-views.md)참조하십시오. 데이터베이스 클래스에 대한 자세한 내용은 [개요: 데이터베이스 프로그래밍](../data/data-access-programming-mfc-atl.md)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[뷰 사용](../mfc/using-views.md)
