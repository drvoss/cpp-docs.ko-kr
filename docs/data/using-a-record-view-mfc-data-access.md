---
title: 레코드 뷰 사용  (MFC Data Access)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
ms.openlocfilehash: 611ddfd755eec84d4f2572a50c18802f988c5c3d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209029"
---
# <a name="using-a-record-view--mfc-data-access"></a>레코드 뷰 사용  (MFC Data Access)

이 항목에서는 마법사가 자동으로 작성하는 레코드 뷰의 기본 코드를 사용자 지정하는 일반적인 방법을 설명합니다. 일반적으로 레코드를 [정렬](../data/odbc/recordset-sorting-records-odbc.md) 하는 [필터](../data/odbc/recordset-filtering-records-odbc.md) 또는 [매개 변수](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 사용 하 여 레코드 선택을 제한 하려면 SQL 문을 사용자 지정 합니다.

`CRecordView`를 사용 하는 것은 [CFormView](../mfc/reference/cformview-class.md)를 사용 하는 것과 거의 같습니다. 기본적인 방식은 레코드 뷰를 사용하여 단일 레코드 집합의 레코드를 표시하고 필요에 따라 업데이트하는 것입니다. 그 외에도 [레코드 뷰: 두 번째 레코드 집합에서 목록 상자 채우기](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)의 설명에 따라 다른 레코드 집합을 사용 하는 것이 좋습니다.

## <a name="see-also"></a>참고 항목

[레코드 뷰(MFC Data Access)](../data/record-views-mfc-data-access.md)<br/>
[ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)
