---
title: 데이터베이스 애플리케이션을 만드는 작업 시퀀스
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
ms.openlocfilehash: c393269d6af108ee82786e9d59f81aad11428157
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372769"
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>데이터베이스 애플리케이션을 만드는 작업 시퀀스

다음 표에서는 데이터베이스 응용 프로그램을 작성하는 데 있어 역할과 프레임워크의 역할을 보여 줍니다.

> [!NOTE]
> Visual C++ 환경 및 마법사는 DAO를 지원하지 않습니다(DAO 클래스가 포함되어 있지만 여전히 사용할 수 있음). 새 MFC 프로젝트에 ODBC를 사용하는 것이 좋습니다. 기존 응용 프로그램을 유지 관리하는 데만 DAO를 사용해야 합니다.

### <a name="creating-database-applications"></a>데이터베이스 응용 프로그램 만들기

|Task|너 해|프레임워크는|
|----------|------------|------------------------|
|MFC ODBC 또는 DAO 클래스를 사용할지 여부를 결정합니다.|새 MFC 프로젝트에 ODBC를 사용합니다. DAO를 사용하여 기존 응용 프로그램을 유지 관리합니다. 일반적인 내용은 [데이터 액세스 프로그래밍](../data/data-access-programming-mfc-atl.md)문서를 참조하십시오.|프레임워크는 데이터베이스 액세스를 지원하는 클래스를 제공합니다.|
|데이터베이스 옵션을 사용하여 스켈레톤 응용 프로그램을 만듭니다.|MFC 응용 프로그램 마법사를 실행합니다. 데이터베이스 지원 페이지에서 옵션을 선택합니다. 레코드 뷰를 만드는 옵션을 선택하는 경우 다음을 지정합니다.<br /><br />- 데이터 원본 및 테이블 이름 또는 이름<br />- 쿼리 이름 또는 이름.|MFC 응용 프로그램 마법사는 파일을 만들고 필요한 포함을 지정합니다. 지정한 옵션에 따라 파일에 레코드 집합 클래스가 포함될 수 있습니다.|
|데이터베이스 양식 또는 양식을 디자인합니다.|Visual C++ 대화 상자 편집기를 사용하여 레코드 보기 클래스의 대화 상자 템플릿 리소스에 컨트롤을 배치합니다.|MFC 응용 프로그램 마법사는 채울 빈 대화 상자 템플릿 리소스를 만듭니다.|
|필요에 따라 추가 레코드 보기 및 레코드 집합 클래스를 만듭니다.|클래스 보기를 사용하여 클래스및 대화 상자 편집기를 만들어 뷰를 디자인합니다.|클래스 보기는 새 클래스에 대 한 추가 파일을 만듭니다.|
|코드에서 필요에 따라 레코드 집합 개체를 만듭니다. 각 레코드 집합을 사용하여 레코드를 조작합니다...|레코드 집합은 마법사가 있는 [CRecord집합에서](../mfc/reference/crecordset-class.md) 파생된 클래스를 기반으로 합니다.|ODBC는 RFX(레코드 필드 교환)를 사용하여 데이터베이스와 레코드 집합의 필드 데이터 멤버 간에 데이터를 교환합니다. 레코드 뷰를 사용하는 경우 DDX(대화 상자 데이터 교환)는 레코드 집합과 레코드 뷰의 컨트롤 간에 데이터를 교환합니다.|
|... 또는 열려는 각 데이터베이스에 대한 코드에 명시적 [CDatabase를](../mfc/reference/cdatabase-class.md) 만듭니다.|데이터베이스 개체에 레코드 집합 개체를 기반으로 합니다.|데이터베이스 개체는 데이터 원본에 대한 인터페이스를 제공합니다.|
|데이터 열을 레코드 집합에 동적으로 바인딩합니다.|ODBC에서 파생 된 레코드 집합 클래스에 코드를 추가하여 바인딩을 관리합니다. [문서 레코드 집합: 동적으로 바인딩된 데이터 열 (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)을 참조하십시오.||

## <a name="see-also"></a>참고 항목

[프레임워크 구축](../mfc/building-on-the-framework.md)<br/>
[MFC 애플리케이션을 빌드하는 작업 시퀀스](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[OLE 애플리케이션을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[ActiveX 컨트롤을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-activex-controls.md)
