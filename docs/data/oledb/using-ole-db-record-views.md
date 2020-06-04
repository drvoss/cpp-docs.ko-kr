---
title: OLE DB 레코드 뷰 사용
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
ms.openlocfilehash: 83f4d64252ab5c2b80d62419ea448c1ffd0cdd69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375186"
---
# <a name="using-ole-db-record-views"></a>OLE DB 레코드 뷰 사용

MFC 응용 프로그램에서 OLE DB 행 집합 데이터를 표시하려는 경우, MFC 클래스 [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)를 사용해야 합니다. `COleDBRecordView`에서 만든 레코드 뷰 개체를 사용하면 데이터베이스 레코드를 MFC 컨트롤에 표시할 수 있습니다. 레코드 뷰는 `CRowset` 템플릿 클래스에서 만든 OLE DB 행 집합 개체에 직접 연결된 대화 상자 형태의 뷰입니다. 행 집합 개체에 대한 핸들을 구하는 것은 다음과 같이 간단합니다.

```cpp
COleDBRecordView myRecordView;
...
// CProductAccessor is a user record class
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();
```

뷰는 대화 상자의 컨트롤에 `CRowset` 개체의 필드를 표시합니다. `COleDBRecordView` 개체에서는 DDX(대화 상자 데이터 교환) 및 `CRowset`에 내장된 탐색 기능(`MoveFirst`, `MoveNext`, `MovePrev` 및 `MoveLast`)을 사용하여 폼의 컨트롤과 행 집합의 필드 사이에 데이터 이동을 자동화합니다. `COleDBRecordView`는 레코드 뷰가 사용자 인터페이스를 업데이트할 수 있도록 행 집합에서 사용자의 위치를 추적하고, 다른 레코드로 이동하기 전에 현재 레코드를 업데이트하는 [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) 메서드도 지원합니다.

DDX 함수를 `COleDbRecordView`와 사용하여 데이터베이스 레코드 집합의 데이터를 직접 가져와서 대화 상자 컨트롤에 표시할 수 있습니다. `DDX_Text` 같은 **DDX_Field**<strong>\*</strong> * 함수가 아닌 `DDX_FieldText` 같은 **DDX_**<strong>\*</strong> * 메서드를 `COleDbRecordView`와 함께 사용해야 합니다.

## <a name="see-also"></a>참고자료

[접근자 사용](../../data/oledb/using-accessors.md)<br/>
[COleDBRecordView 클래스](../../mfc/reference/coledbrecordview-class.md)<br/>
