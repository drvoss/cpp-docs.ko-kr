---
title: DAO 클래스
ms.date: 09/17/2019
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
ms.openlocfilehash: 7ae85cbeb7790cadb8c26dfbdb7a5163dbcd47c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373511"
---
# <a name="dao-classes"></a>DAO 클래스

DAO는 Access 데이터베이스와 함께 사용되며 Office 2013을 통해 지원됩니다. DAO 3.6은 최종 버전이며 더 이상 사용되지 않는 것으로 간주됩니다.

이러한 클래스는 다른 응용 프로그램 프레임워크 클래스와 함께 작동하여 Microsoft Visual Basic 및 Microsoft Access와 동일한 데이터베이스 엔진을 사용하는 DAO(데이터 액세스 개체) 데이터베이스에 쉽게 액세스할 수 있습니다. DAO 클래스는 개방형 데이터베이스 연결(ODBC) 드라이버를 사용할 수 있는 다양한 데이터베이스에도 액세스할 수 있습니다.

DAO 데이터베이스를 사용하는 프로그램에는 최소한 `CDaoDatabase` 개체와 `CDaoRecordset` 개체가 있습니다.

> [!NOTE]
> Visual C++ 환경 및 마법사는 더 이상 DAO를 지원하지 않습니다(DAO 클래스가 포함되어 있지만 여전히 사용할 수 있음). 새 MFC 프로젝트에 ODBC를 사용하는 것이 좋습니다. 기존 응용 프로그램을 유지 관리하는 데만 DAO를 사용해야 합니다.

[CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)<br/>
로그인에서 로그오프까지 암호로 보호된 명명된 데이터베이스 세션을 관리합니다. 대부분의 프로그램은 기본 작업 영역을 사용합니다.

[CDaoDatabase](../mfc/reference/cdaodatabase-class.md)<br/>
데이터에서 작동할 수 있는 데이터베이스에 대한 연결입니다.

[Cdaorecordset](../mfc/reference/cdaorecordset-class.md)<br/>
데이터 소스에서 선택한 레코드 집합을 나타냅니다.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
컨트롤에 데이터베이스 레코드를 표시하는 뷰입니다.

[CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)<br/>
쿼리 정의(일반적으로 데이터베이스에 저장된 쿼리 정의)를 나타냅니다.

[CDaoTableDef](../mfc/reference/cdaotabledef-class.md)<br/>
기본 테이블 또는 연결된 테이블의 저장된 정의를 나타냅니다.

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
DAO 클래스에서 발생하는 예외 조건을 나타냅니다.

[CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)<br/>
DAO 데이터베이스 클래스에서 사용하는 DAO 레코드 필드 교환(DFX) 루틴을 지원합니다. 일반적으로 이 클래스를 직접 사용하지 는 않습니다.

## <a name="related-classes"></a>관련 수업

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
비트맵과 같은 이진 큰 개체(BLOB)에 대한 저장소에 핸들을 캡슐화합니다. `CLongBinary`개체는 데이터베이스 테이블에 저장된 큰 데이터 개체를 관리하는 데 사용됩니다.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
OLE 자동화 유형 **통화에**대한 래퍼는 소수점 앞에 15자리, 후 4자리숫자로 고정소수점 산술 유형입니다.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE 자동화 유형 **DATE에**대한 래퍼입니다. 날짜 및 시간 값을 나타냅니다.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
OLE 자동화 유형 **VARIANT용**래퍼입니다. **VARIANTs의**데이터는 다양한 형식으로 저장할 수 있습니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../mfc/class-library-overview.md)
