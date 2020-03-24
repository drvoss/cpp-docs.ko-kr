---
title: 폼에서 데이터의 표시와 조작
ms.date: 11/04/2016
helpviewer_keywords:
- forms [C++], displaying data
- displaying data [C++], forms
- ODBC [C++], forms
- record views [C++], displaying data
- data [MFC]
- data [MFC], displaying in a form
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
ms.openlocfilehash: 6b663fabd0c87d9a2773e6f5a2796bcc8f57ce29
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213254"
---
# <a name="displaying-and-manipulating-data-in-a-form"></a>폼에서 데이터의 표시와 조작

많은 데이터 액세스 응용 프로그램은 폼의 필드를 이용하여 데이터를 선택하고 표시합니다. 데이터베이스 클래스 [CRecordView](../../mfc/reference/crecordview-class.md) 는 레코드 집합 개체에 직접 연결 된 [CFormView](../../mfc/reference/cformview-class.md) 개체를 제공 합니다. 레코드 뷰는 [DDX (dialog data exchange)](../../mfc/dialog-data-exchange-and-validation.md) 를 사용 하 여 현재 레코드의 필드 값을 레코드 집합에서 폼의 컨트롤로 이동 하 고 업데이트 된 정보를 레코드 집합으로 다시 이동 합니다. 그런 다음 레코드 집합은 레코드 필드 교환(RFX)을 사용하여 자체 필드 데이터 멤버와 데이터 소스에 있는 테이블의 해당 열 사이로 데이터를 이동시킵니다.

Mfc 응용 프로그램 마법사를 사용 하거나 ( [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)에 설명 된 대로) **클래스를 추가** 하 여 뷰 클래스와 연결 된 레코드 집합 클래스를 함께 만들 수 있습니다.

레코드 뷰 및 해당 레코드 집합은 문서를 닫을 때 삭제됩니다. 레코드 뷰에 대 한 자세한 내용은 [레코드 뷰](../../data/record-views-mfc-data-access.md)를 참조 하세요. RFX에 대 한 자세한 내용은 [rfx (레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)를 참조 하세요.

## <a name="see-also"></a>참고 항목

[ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)
