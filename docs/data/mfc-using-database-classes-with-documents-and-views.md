---
title: 'MFC: 문서 및 뷰를 이용한 데이터베이스 클래스 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- documents [C++], database applications
- recordsets [C++], documents and views
- CRecordView class, using in database forms
- views [C++], database applications
- forms [C++], database applications
- record views [C++], form-based applications
- document/view architecture [C++], in databases
- database applications [C++], forms
- database classes [C++], MFC
- ODBC recordsets [C++], documents and views
- ODBC [C++], forms
ms.assetid: 83979974-fc63-46ac-b162-e8403a572e2c
ms.openlocfilehash: 9e071e0cc25492073cd74ed517284476b6e49ef8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368898"
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC: 문서 및 뷰를 이용한 데이터베이스 클래스 사용

문서/보기 아키텍처의 유무에 관계없이 MFC 데이터베이스 클래스를 사용할 수 있습니다. 이 항목에서는 문서 및 뷰 작업을 강조합니다. 그것은 설명한다 :

- 문서의 기본 보기로 개체를 `CRecordView` 사용하여 [양식 기반 응용 프로그램을 작성하는 방법.](#_core_writing_a_form.2d.based_application)

- [문서 및 보기에서 레코드 집합 개체를 사용하는 방법.](#_core_using_recordsets_in_documents_and_views)

- [기타 고려 사항](#_core_other_factors).

대안은 [MFC: 문서 및 뷰 없이 데이터베이스 클래스 사용.](../data/mfc-using-database-classes-without-documents-and-views.md)

## <a name="writing-a-form-based-application"></a><a name="_core_writing_a_form.2d.based_application"></a>양식 기반 응용 프로그램 작성

많은 데이터 액세스 응용 프로그램은 양식을 기반으로 합니다. 사용자 인터페이스는 사용자가 데이터를 검사, 입력 또는 편집하는 컨트롤을 포함하는 양식입니다. 신청서를 기반으로 만들려면 클래스를 `CRecordView`사용합니다. MFC 응용 프로그램 마법사를 실행하고 **데이터베이스 지원** 페이지에서 **ODBC** 클라이언트 `CRecordView` 유형을 선택하면 프로젝트가 뷰 클래스에 사용합니다.

양식 기반 응용 프로그램에서 각 레코드 뷰 개체는 `CRecordset` 개체에 대한 포인터를 저장합니다. 프레임워크의 레코드 필드 교환(RFX) 메커니즘은 레코드 집합과 데이터 원본 간에 데이터를 교환합니다. 대화 상자 데이터 교환(DDX) 메커니즘은 레코드 집합 개체의 필드 데이터 멤버와 폼의 컨트롤 간에 데이터를 교환합니다. `CRecordView`또한 레코드에서 양식에 기록하기 위해 탐색하기 위한 기본 명령 처리기 함수도 제공합니다.

응용 프로그램 마법사를 사용하여 양식 기반 응용 프로그램을 만들려면 [양식 기반 MFC 응용 프로그램](../mfc/reference/creating-a-forms-based-mfc-application.md) 및 데이터베이스 [지원, MFC 응용 프로그램 마법사](../mfc/reference/database-support-mfc-application-wizard.md)만들기를 참조하십시오.

양식에 대한 전체 설명은 [레코드 보기](../data/record-views-mfc-data-access.md)를 참조하십시오.

## <a name="using-recordsets-in-documents-and-views"></a><a name="_core_using_recordsets_in_documents_and_views"></a>문서 및 뷰에 레코드 집합 사용

많은 간단한 양식 기반 응용 프로그램에는 문서가 필요하지 않습니다. 응용 프로그램이 더 복잡한 경우 문서를 데이터베이스의 프록시로 사용하여 데이터 원본에 연결하는 개체를 `CDatabase` 저장하려고 할 수 있습니다. 양식 기반 응용 프로그램은 일반적으로 뷰에서 레코드 집합 개체에 대한 포인터를 저장합니다. 다른 종류의 데이터베이스 응용 프로그램은 문서에 `CDatabase` 레코드 집합과 개체를 저장합니다. 다음은 데이터베이스 응용 프로그램에서 문서를 사용할 수 있는 몇 가지 가능성입니다.

- 로컬 컨텍스트에서 레코드 집합에 액세스하는 경우 `CRecordset` 필요에 따라 문서 또는 뷰의 멤버 함수에서 개체를 로컬로 만듭니다.

   함수에서 레코드 집합 개체를 로컬 변수로 선언합니다. NULL을 생성자에게 전달하면 프레임워크가 임시 `CDatabase` 개체를 만들고 열립니다. 또는 개체에 포인터를 전달합니다. `CDatabase` 함수 내에서 레코드 집합을 사용하고 함수가 종료될 때 자동으로 삭제됩니다.

   NULL을 레코드 집합 생성자로 전달하면 프레임워크는 레코드 집합의 `GetDefaultConnect` 멤버 함수에서 `CDatabase` 반환하는 정보를 사용하여 개체를 만들고 엽니다. 마법사가 당신을 `GetDefaultConnect` 위해 구현합니다.

- 문서의 수명 동안 레코드 집합에 액세스하는 경우 문서에 `CRecordset` 하나 이상의 개체를 포함합니다.

   문서를 초기화할 때 또는 필요에 따라 레코드 집합 개체를 생성합니다. 레코드 집합이 이미 존재하거나 생성되어 아직 존재하지 않는 경우 레코드 집합을 여는 경우 레코드 집합에 대한 포인터를 반환하는 함수를 작성할 수 있습니다. 필요에 따라 레코드 집합을 닫고 삭제하고 다시 `Requery` 만들거나 멤버 함수를 호출하여 레코드를 새로 고칩니다.

- 문서의 수명 동안 데이터 원본에 액세스하는 경우 `CDatabase` 개체를 포함하거나 개체에 대한 포인터를 `CDatabase` 저장합니다.

   개체는 `CDatabase` 데이터 원본에 대한 연결을 관리합니다. 개체는 문서를 구성하는 동안 자동으로 생성되며 `Open` 문서를 초기화할 때 해당 멤버 함수를 호출합니다. 문서 멤버 함수에서 레코드 집합 개체를 생성할 때 문서의 `CDatabase` 개체에 대한 포인터를 전달합니다. 이렇게 하면 각 레코드 집합이 데이터 원본과 연결됩니다. 데이터베이스 개체는 일반적으로 문서가 닫히면 소멸됩니다. 레코드 집합 개체는 일반적으로 함수의 범위를 종료할 때 소멸됩니다.

## <a name="other-factors"></a><a name="_core_other_factors"></a>기타 요인

양식 기반 응용 프로그램은 프레임워크의 문서 직렬화 메커니즘에 사용되지 않는 경우가 많으므로 **파일** 메뉴에서 **새로** 시작 및 **열기** 명령을 제거, 비활성화 또는 대체할 수 있습니다. [일련화: 직렬화 대 데이터베이스 입력/출력](../mfc/serialization-serialization-vs-database-input-output.md)문서를 참조하십시오.

프레임워크가 지원할 수 있는 많은 사용자 인터페이스 가능성을 활용할 수도 있습니다. 예를 들어 스플리터 `CRecordView` 창에서 여러 개체를 사용하고, MDI(다른 여러 문서 인터페이스) 자식 창에서 여러 레코드 집합을 여는 등의 방법으로 여러 개체를 사용할 수 있습니다.

뷰에 있는 양식이 구현된 `CRecordView` 양식이든 다른 형식이든 관계없이 뷰에 있는 모든 인쇄를 구현할 수 있습니다. 에서 파생된 클래스는 인쇄를 지원하지 않지만 인쇄를 `OnPrint` 허용하도록 멤버 함수를 재정의할 수 있습니다. `CRecordView` `CFormView` 자세한 내용은 클래스 [CFormView](../mfc/reference/cformview-class.md)를 참조하십시오.

문서와 뷰를 전혀 사용하지 않을 수 있습니다. 이 경우 [MFC: 문서 및 뷰 없이 데이터베이스 클래스 사용.](../data/mfc-using-database-classes-without-documents-and-views.md)

## <a name="see-also"></a>참고 항목

[MFC 데이터베이스 클래스](../data/mfc-database-classes-odbc-and-dao.md)
