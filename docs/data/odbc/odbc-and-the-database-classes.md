---
title: ODBC 및 데이터베이스 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 6511aab9bb048882fe9c3398dd17f769eb16220c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320058"
---
# <a name="odbc-and-the-database-classes"></a>ODBC 및 데이터베이스 클래스

MFC ODBC 데이터베이스 클래스는 일반적으로 [CDatabase](../../mfc/reference/cdatabase-class.md) 및 [CRecordset](../../mfc/reference/crecordset-class.md) 클래스의 멤버 함수에서 직접 만드는 ODBC API 함수 호출을 캡슐화합니다. 예를 들어 복잡한 ODBC 호출 시퀀스, 저장소 위치에 반환된 레코드 바인딩, 오류 조건 처리 및 기타 작업은 데이터베이스 클래스에서 관리됩니다. 따라서 훨씬 더 간단한 클래스 인터페이스를 사용하여 레코드 집합 개체를 통해 레코드를 조작할 수 있습니다.

> [!NOTE]
> ODBC 데이터 원본은 이 항목에 설명된 대로 MFC ODBC 클래스 또는 MFC 데이터 액세스 개체(DAO) 클래스를 통해 액세스할 수 있습니다.

데이터베이스 클래스는 ODBC 기능을 캡슐화하지만 ODBC API 함수의 일대일 매핑은 제공하지 않습니다. 데이터베이스 클래스는 Microsoft Access 및 Microsoft Visual Basic에서 찾을 수 있는 데이터 액세스 개체를 모델로 한 더 높은 수준의 추상화를 제공합니다. 자세한 내용은 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)를 참조하십시오.

## <a name="see-also"></a>참고 항목


