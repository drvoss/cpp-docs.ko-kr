---
title: 애플리케이션 마법사가 만든 레코드 뷰 코드  (MFC Data Access)
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
ms.openlocfilehash: 69481299980329b98e378f02e090670fa3d7ece2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376029"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>애플리케이션 마법사가 만든 레코드 뷰 코드  (MFC Data Access)

[MFC 응용 프로그램 마법사는](../mfc/reference/database-support-mfc-application-wizard.md) 뷰 `OnInitialUpdate` `OnGetRecordset` 및 멤버 함수를 재정의합니다. 프레임워크는 프레임 창, 문서 및 뷰를 만든 후 `OnInitialUpdate`를 호출하여 뷰를 초기화합니다. `OnInitialUpdate`는 문서에서 레코드 집합에 대한 포인터를 가져옵니다. 기본 클래스 [CView::OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) 함수에 대 한 호출 레코드 집합을 엽니다. 다음 코드는 다음 에 `CRecordView`대한 이 프로세스를 보여 주며 다음 에 대한 프로세스를 보여 주며 다음에 대해 보여 주며 다음 에 대한

```cpp
void CSectionForm::OnInitialUpdate()
{
   m_pSet = &GetDocument()->m_sectionSet;
   CRecordView::OnInitialUpdate();
}
```

레코드 집합이 열리면 레코드를 선택합니다. [CRecordset::Open은](../mfc/reference/crecordset-class.md#open) 첫 번째 레코드를 현재 레코드로 만들고 DDX는 레코드 집합의 필드 데이터 멤버에서 뷰의 해당 양식 컨트롤로 데이터를 이동합니다. RFX에 대한 자세한 내용은 [RFX(레코드 필드 교환)를](../data/odbc/record-field-exchange-rfx.md)참조하십시오. DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. 문서/보기 만들기 프로세스에 대한 자세한 내용은 [클래스 를 사용하여 Windows용 응용 프로그램을 작성합니다.](../mfc/using-the-classes-to-write-applications-for-windows.md)

> [!NOTE]
> 최종 사용자가 레코드 집합에서의 레코드 뷰 컨트롤을 새로 고치는 기능을 제공해야 합니다. 이 기능을 제공하지 않는 경우 사용자가 컨트롤 값을 잘못된 값으로 변경하면 현재 레코드에서 영구적으로 작업이 중지될 수 있습니다. 컨트롤을 새로 고치려면 `CWnd` 멤버 함수 [UpdateData를](../mfc/reference/cwnd-class.md#updatedata) FALSE 매개 변수로 호출합니다.

## <a name="see-also"></a>참고 항목

[레코드 뷰 사용](../data/using-a-record-view-mfc-data-access.md)
