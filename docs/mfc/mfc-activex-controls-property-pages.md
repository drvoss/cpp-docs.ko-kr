---
title: 'MFC ActiveX 컨트롤: 속성 페이지'
ms.date: 11/19/2018
helpviewer_keywords:
- DDP_ functions [MFC]
- MFC ActiveX controls [MFC], properties
- property pages [MFC], MFC ActiveX controls
- DoDataExchange method [MFC]
- OLEIVERB_PROPERTIES
- CPropertyPageDialog class [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 1506f87a-9fd6-4505-8380-0dbc9636230e
ms.openlocfilehash: c31d13e03483f8632f17a526da75ebe8e21bccbf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364575"
---
# <a name="mfc-activex-controls-property-pages"></a>MFC ActiveX 컨트롤: 속성 페이지

속성 페이지를 사용하면 ActiveX 컨트롤 사용자가 ActiveX 컨트롤 속성을 보고 변경할 수 있습니다. 이러한 속성은 컨트롤 속성을 보고 편집하기 위한 사용자 지정된 그래픽 인터페이스를 제공하는 하나 이상의 속성 페이지를 포함하는 컨트롤 속성 대화 상자를 호출하여 액세스됩니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

ActiveX 제어 속성 페이지는 다음 두 가지 방법으로 표시됩니다.

- 컨트롤의 속성 동사 **(OLEIVERB_PROPERTIES)가**호출되면 컨트롤은 컨트롤의 속성 페이지를 포함하는 모달 속성 대화 상자를 엽니다.

- 컨테이너는 선택한 컨트롤의 속성 페이지를 표시하는 자체 모덜리스 대화 상자를 표시할 수 있습니다.

속성 대화 상자(다음 그림에 설명됨)는 현재 속성 페이지를 표시하는 영역, 속성 페이지 간 전환 탭 및 속성 페이지 대화 상자 닫기, 변경 내용 취소 또는 ActiveX 컨트롤에 변경 내용을 즉시 적용하는 등의 일반적인 작업을 수행하는 단추 모음으로 구성됩니다.

![Circ3 속성 대화 상자](../mfc/media/vc373i1.gif "Circ3 속성 대화 상자") <br/>
속성 대화 상자

이 문서에서는 ActiveX 컨트롤에서 속성 페이지를 사용하는 관련 항목을 다룹니다. 여기에는 다음이 포함됩니다.

- [ActiveX 컨트롤에 대한 기본 속성 페이지 구현](#_core_implementing_the_default_property_page)

- [속성 페이지에 컨트롤 추가](#_core_adding_controls_to_a_property_page)

- [DoDataExchange 기능 사용자 지정](#_core_customizing_the_dodataexchange_function)

ActiveX 컨트롤에서 속성 페이지 사용에 대한 자세한 내용은 다음 문서를 참조하십시오.

- [MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

- [MFC ActiveX 컨트롤: 스톡 속성 페이지 사용](../mfc/mfc-activex-controls-using-stock-property-pages.md)

ActiveX 컨트롤이 아닌 MFC 응용 프로그램에서 속성 시트를 사용하는 방법에 대한 자세한 내용은 [속성 시트를](../mfc/property-sheets-mfc.md)참조하십시오.

## <a name="implementing-the-default-property-page"></a><a name="_core_implementing_the_default_property_page"></a>기본 속성 페이지 구현

ActiveX 컨트롤 마법사를 사용하여 제어 프로젝트를 만드는 경우 ActiveX 컨트롤 마법사는 [COlePropertyPage 클래스에서](../mfc/reference/colepropertypage-class.md)파생된 컨트롤에 대한 기본 속성 페이지 클래스를 제공합니다. 처음에는 이 속성 페이지가 비어 있지만 대화 상자 컨트롤이나 컨트롤 집합을 추가할 수 있습니다. ActiveX 컨트롤 마법사는 기본적으로 하나의 속성 페이지 클래스만 생성하므로 클래스 `COlePropertyPage`보기를 사용하여 추가 속성 페이지 클래스(파생)를 만들어야 합니다. 이 절차에 대한 자세한 내용은 [MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가를](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)참조하십시오.

속성 페이지 구현(이 경우 기본값)은 세 단계로 진행됩니다.

#### <a name="to-implement-a-property-page"></a>속성 페이지를 구현하려면

1. 컨트롤 `COlePropertyPage`프로젝트에 -derived 클래스를 추가합니다. 이 경우와 같이 ActiveX 컨트롤 마법사를 사용하여 프로젝트를 만든 경우 기본 속성 페이지 클래스가 이미 있습니다.

1. 대화 상자 편집기를 사용하여 속성 페이지 템플릿에 컨트롤을 추가합니다.

1. -derived `DoDataExchange` 클래스의 함수를 사용자 지정하여 속성 페이지 컨트롤과 ActiveX 컨트롤 간에 값을 교환합니다. `COlePropertyPage`

예를 들어 다음 절차에서는 간단한 컨트롤("샘플")을 사용합니다. 샘플은 ActiveX 컨트롤 마법사를 사용하여 만들어졌으며 스톡 캡션 속성만 포함합니다.

## <a name="adding-controls-to-a-property-page"></a><a name="_core_adding_controls_to_a_property_page"></a>속성 페이지에 컨트롤 추가

#### <a name="to-add-controls-to-a-property-page"></a>속성 페이지에 컨트롤을 추가하려면

1. 제어 프로젝트를 열고 리소스 보기를 엽니다.

1. **대화 상자** 디렉토리 아이콘을 두 번 클릭합니다.

1. IDD_PROPPAGE_SAMPLE 대화 상자를 엽니다.

   ActiveX 컨트롤 마법사는 이 경우 샘플과 같은 대화 상자 ID의 끝에 프로젝트 이름을 더해 주습니다.

1. 도구 상자에서 선택한 컨트롤을 대화 상자 영역으로 끌어 놓습니다.

1. 이 예제에서는 텍스트 레이블 컨트롤 "캡션 :"과 IDC_CAPTION 식별자가 있는 편집 상자 컨트롤로 충분합니다.

1. 도구 모음에 **저장을** 클릭하여 변경 내용을 저장합니다.

사용자 인터페이스가 수정되었으므로 편집 상자를 Caption 속성과 연결해야 합니다. 이 작업은 `CSamplePropPage::DoDataExchange` 함수를 편집하여 다음 섹션에서 수행됩니다.

## <a name="customizing-the-dodataexchange-function"></a><a name="_core_customizing_the_dodataexchange_function"></a>DoDataExchange 기능 사용자 지정

속성 페이지 [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) 함수를 사용하면 속성 페이지 값을 컨트롤의 실제 속성 값과 연결할 수 있습니다. 링크를 설정하려면 해당 속성 페이지 필드를 해당 제어 속성에 매핑해야 합니다.

이러한 매핑은 속성 페이지 **DDP_** 함수를 사용하여 구현됩니다. **DDP_** 함수는 표준 MFC 대화 상자에 사용되는 **DDX_** 함수처럼 작동하지만 한 가지 예외가 있습니다. 멤버 변수에 대한 참조 외에도 **DDP_** 함수는 컨트롤 속성의 이름을 차지합니다. 다음은 속성 페이지에 대한 `DoDataExchange` 함수의 일반적인 항목입니다.

[!code-cpp[NVC_MFC_AxUI#31](../mfc/codesnippet/cpp/mfc-activex-controls-property-pages_1.cpp)]

이 함수는 `DDP_TEXT` 함수를 사용하여 속성 페이지의 *m_caption* 멤버 변수를 캡션과 연결합니다.

속성 페이지 컨트롤을 삽입한 후 위에서 설명한 `DDP_Text` 기능을 사용하여 속성 페이지 컨트롤, IDC_CAPTION 및 실제 제어 속성 캡션 간의 링크를 설정해야 합니다.

[속성 페이지는](../mfc/reference/property-pages-mfc.md) 확인란, 라디오 단추 및 목록 상자와 같은 다른 대화 상자 컨트롤 유형에 사용할 수 있습니다. 아래 표에는 속성 페이지의 전체 **DDP_** 함수 및 그 목적이 나열되어 있습니다.

### <a name="property-page-functions"></a>속성 페이지 기능

|함수 이름|이 함수를 사용하여 연결|
|-------------------|-------------------------------|
|`DDP_CBIndex`|컨트롤 속성이 있는 콤보 상자에서 선택한 문자열의 인덱스입니다.|
|`DDP_CBString`|컨트롤 속성이 있는 콤보 상자에서 선택한 문자열입니다. 선택한 문자열은 속성값과 동일한 문자로 시작할 수 있지만 완전히 일치하지는 않아도 됩니다.|
|`DDP_CBStringExact`|컨트롤 속성이 있는 콤보 상자에서 선택한 문자열입니다. 선택한 문자열과 속성의 문자열 값이 정확히 일치해야 합니다.|
|`DDP_Check`|컨트롤 속성이 있는 확인란입니다.|
|`DDP_LBIndex`|컨트롤 속성이 있는 목록 상자에서 선택한 문자열의 인덱스입니다.|
|`DDP_LBString`|컨트롤 속성이 있는 목록 상자에서 선택한 문자열입니다. 선택한 문자열은 속성값과 동일한 문자로 시작할 수 있지만 완전히 일치하지는 않아도 됩니다.|
|`DDP_LBStringExact`|컨트롤 속성이 있는 목록 상자에서 선택한 문자열입니다. 선택한 문자열과 속성의 문자열 값이 정확히 일치해야 합니다.|
|`DDP_Radio`|컨트롤 속성이 있는 라디오 단추입니다.|
|`DDP_Text`|컨트롤 속성이 있는 텍스트입니다.|

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[COlePropertyPage 클래스](../mfc/reference/colepropertypage-class.md)
