---
title: 'ODBC: ODBC API 함수 직접 호출'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC API functions [C++], calling
- ODBC [C++], catalog functions
- ODBC API functions [C++]
- APIs [C++], calling
- ODBC classes [C++], vs. ODBC API
- direct ODBC API calls
- catalog functions (ODBC)
- catalog functions (ODBC), calling
- ODBC [C++], API functions
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
ms.openlocfilehash: 208749438f40eef746a638dd12373397c426d454
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368659"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: ODBC API 함수 직접 호출

데이터베이스 클래스는 ODBC보다 [데이터 원본에](../../data/odbc/data-source-odbc.md) 더 간단한 인터페이스를 제공합니다. 따라서 클래스는 모든 ODBC API를 캡슐화하지 않습니다. 클래스의 기능을 벗어난 모든 기능의 경우 ODBC API 함수를 직접 호출해야 합니다. 예를 들어 ODBC 카탈로그 함수(,`::SQLColumns`및 `::SQLProcedures` `::SQLTables`기타)를 직접 호출해야 합니다.

> [!NOTE]
> ODBC 데이터 원본은 이 항목에 설명된 대로 MFC ODBC 클래스 또는 MFC 데이터 액세스 개체(DAO) 클래스를 통해 액세스할 수 있습니다.

ODBC API 함수를 직접 호출하려면 프레임워크 없이 호출하는 경우 와 동일한 단계를 수행해야 합니다. 단계는 다음과 같습니다.

- 호출이 반환하는 결과에 대해 저장소를 할당합니다.

- 함수의 매개 `HDBC` `HSTMT` 변수 서명에 따라 ODBC 또는 핸들을 전달합니다. [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) 매크로를 사용하여 ODBC 핸들을 검색합니다.

   멤버 `CDatabase::m_hdbc` 변수를 `CRecordset::m_hstmt` 사용할 수 있으므로 직접 할당하고 초기화할 필요가 없습니다.

- 아마도 추가 ODBC 함수를 호출하여 주 호출을 준비하거나 후속 조치를 취할 수 있습니다.

- 완료되면 저장소를 할당 합니다.

이러한 단계에 대한 자세한 내용은 MSDN 설명서의 [ODBC(개방형 데이터베이스 연결)](/sql/odbc/microsoft-open-database-connectivity-odbc) SDK를 참조하십시오.

이러한 단계 외에도 함수 반환 값을 확인하고 프로그램이 비동기 호출이 완료될 때까지 기다리지 않는지 확인하는 추가 단계를 수행해야 합니다. AFX_SQL_ASYNC 및 AFX_SQL_SYNC 매크로를 사용하여 이러한 마지막 단계를 단순화할 수 있습니다. 자세한 내용은 *MFC 참조의* [매크로 및 전역을](../../mfc/reference/mfc-macros-and-globals.md) 참조하십시오.

## <a name="see-also"></a>참고 항목

[ODBC 기본 사항](../../data/odbc/odbc-basics.md)
