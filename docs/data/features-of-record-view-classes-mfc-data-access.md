---
title: 레코드 뷰 클래스의 기능  (MFC Data Access)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
ms.openlocfilehash: 62597a3eb3f7a7e779ca57c9781565176df568d4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213436"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>레코드 뷰 클래스의 기능  (MFC Data Access)

[CFormView](../mfc/reference/cformview-class.md)클래스를 사용 하 여 폼 기반 데이터 액세스 프로그래밍을 수행할 수 있지만 일반적으로 [CRecordView](../mfc/reference/crecordview-class.md) 는에서 파생 하는 것이 더 좋은 클래스입니다. `CFormView` 기능 외에도 다음을 `CRecordView`.

- 양식 컨트롤과 연결 된 레코드 집합 개체 간의 DDX (대화 상자 데이터 교환)를 제공 합니다.

- 연결 된 레코드 집합 개체의 레코드를 탐색 하기 위해 먼저 이동, 다음으로 이동, 이전으로 이동 및 마지막으로 이동 명령을 처리 합니다.

- 사용자가 다른 레코드로 이동할 때 현재 레코드에 대 한 변경 내용을 업데이트 합니다.

탐색에 대 한 자세한 내용은 [레코드 뷰: 레코드 뷰에서 탐색 지원](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[레코드 뷰(MFC Data Access)](../data/record-views-mfc-data-access.md)<br/>
[ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)
