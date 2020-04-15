---
title: 'MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
ms.openlocfilehash: 02c87c2c5283b7293c2a7ab028ec9a2abbba2b33
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364735"
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가

경우에 따라 ActiveX 컨트롤은 한 속성 페이지에 합리적으로 맞을 수 있는 것보다 더 많은 속성을 갖습니다. 이 경우 ActiveX 컨트롤에 속성 페이지를 추가하여 이러한 속성을 표시할 수 있습니다.

이 문서에서는 이미 하나 이상의 속성 페이지가 있는 ActiveX 컨트롤에 새 속성 페이지를 추가하는 방법을 설명합니다. 스톡 속성 페이지(글꼴, 그림 또는 색상)를 추가하는 방법에 대한 자세한 내용은 [MFC ActiveX 컨트롤: 스톡 속성 페이지 사용](../mfc/mfc-activex-controls-using-stock-property-pages.md)문서를 참조하십시오.

다음 절차에서는 ActiveX 컨트롤 마법사에서 만든 샘플 ActiveX 제어 프레임워크를 사용합니다. 따라서 클래스 이름 및 식별자는 이 예제에 고유합니다.

ActiveX 컨트롤에서 속성 페이지 사용에 대한 자세한 내용은 다음 문서를 참조하십시오.

- [MFC ActiveX 컨트롤: 속성 페이지](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX 컨트롤: 스톡 속성 페이지 사용](../mfc/mfc-activex-controls-using-stock-property-pages.md)

    > [!NOTE]
    >  새 속성 페이지는 ActiveX 컨트롤 속성 페이지의 크기 표준을 준수하는 것이 좋습니다. 스톡 사진 및 색상 속성 페이지는 250x62 대화 상자 단위(DLU)를 측정합니다. 표준 글꼴 속성 페이지는 250x110 DUS입니다. ActiveX 제어 마법사에서 만든 기본 속성 페이지는 250x62 DLU 표준을 사용합니다.

### <a name="to-insert-a-new-property-page-template-into-your-project"></a>프로젝트에 새 속성 페이지 템플릿을 삽입하려면

1. 제어 프로젝트를 열면 프로젝트 작업 영역에서 리소스 보기를 엽니다.

1. 리소스 보기에서 마우스 오른쪽 단추를 클릭하여 바로 가기 메뉴를 열고 **리소스 추가**를 클릭합니다.

1. 대화 **상자** 노드를 확장하고 **IDD_OLE_PROPPAGE_SMALL**선택합니다.

1. **새** 를 클릭하여 프로젝트에 리소스를 추가합니다.

1. 새 속성 페이지 템플릿을 선택하여 **리소스 보기에서** **속성** 창을 새로 고칩니다.

1. **ID** 속성에 대한 새 값을 입력합니다. 이 예제에서는 **IDD_PROPPAGE_NEWPAGE**을 사용합니다.

1. 도구 모음에서 **저장**을 클릭합니다.

### <a name="to-associate-the-new-template-with-a-class"></a>새 템플릿을 클래스와 연결하려면

1. 클래스 뷰를 엽니다.

1. 클래스 보기에서 마우스 오른쪽 단추를 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **추가를** 클릭한 다음 **클래스 추가**를 클릭합니다.

   그러면 [클래스 추가](../ide/add-class-dialog-box.md) 대화 상자가 열립니다.

1. MFC 클래스 템플릿을 두 번 **클릭합니다.**

1. [MFC 클래스 마법사의](../mfc/reference/mfc-add-class-wizard.md) **클래스 이름** 상자에서 새 대화 상자 클래스의 이름을 입력합니다. (이 예제에서는 `CAddtlPropPage`.)

1. 파일 이름을 변경하려면 **을**클릭합니다. 구현 및 헤더 파일의 이름을 입력하거나 기본 이름을 수락합니다.

1. 기본 **클래스** 상자에서 `COlePropertyPage`을 선택합니다.

1. 대화 **상자에서** **IDD_PROPPAGE_NEWPAGE**선택합니다.

1. **완료를** 클릭하여 클래스를 만듭니다.

컨트롤의 사용자가 이 새 속성 페이지에 액세스할 수 있도록 하려면 컨트롤의 속성 페이지 IDs 매크로 섹션(컨트롤 구현 파일에 있음)을 다음과 같은 변경 합니다.

[!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]

BEGIN_PROPPAGEIDS 매크로(속성 페이지 수)의 두 번째 매개 변수를 1에서 2로 늘려야 합니다.

또한 컨트롤 구현 파일을 수정해야 합니다( CPP) 파일은 헤더() H) 새 속성 페이지 클래스의 파일입니다.

다음 단계에서는 형식 이름과 새 속성 페이지에 대한 캡션을 제공하는 두 개의 새 문자열 리소스를 만드는 작업이 포함됩니다.

#### <a name="to-add-new-string-resources-to-a-property-page"></a>속성 페이지에 새 문자열 리소스를 추가하려면

1. 제어 프로젝트를 열고 리소스 보기를 엽니다.

1. **문자열 테이블** 폴더를 두 번 클릭한 다음 문자열을 추가할 기존 문자열 테이블 리소스를 두 번 클릭합니다.

   그러면 창에서 문자열 테이블이 열립니다.

1. 문자열 테이블 끝에 있는 빈 줄을 선택하고 문자열의 텍스트 또는 캡션을 입력합니다( 예: "추가 속성 페이지").

   그러면 **캡션** 및 **ID** 상자가 표시된 **문자열 속성** 페이지가 열립니다. **캡션** 상자에는 입력한 문자열이 포함되어 있습니다.

1. **ID** 상자에서 문자열의 ID를 선택하거나 입력합니다. 완료되면 Enter를 누릅니다.

   이 예제에서는 새 속성 페이지의 형식 이름에 **IDS_SAMPLE_ADDPAGE** 사용합니다.

1. ID의 **경우 IDS_SAMPLE_ADDPPG_CAPTION** 캡션의 "추가 속성 페이지"를 사용하여 3단계와 4단계를 반복합니다.

1. 안에. 새 속성 페이지 클래스의 CPP 파일(이 `CAddtlPropPage`예에서는)은 `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` 다음 예제와 같이 IDS_SAMPLE_ADDPAGE [AfxOleRegisterPropertyPageClass에](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass)의해 전달되도록 수정합니다.

   [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]

1. 다음과 같이 IDS_SAMPLE_ADDPPG_CAPTION `CAddtlPropPage` `COlePropertyPage` 생성자에게 전달되도록 생성자의 생성자 수정:

   [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]

필요한 수정을 한 후 프로젝트를 다시 빌드하고 테스트 컨테이너를 사용하여 새 속성 페이지를 테스트합니다. 테스트 컨테이너에 액세스하는 방법은 [테스트 컨테이너로 속성 및 이벤트 테스트](../mfc/testing-properties-and-events-with-test-container.md) 를 참조하세요.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
