---
title: 'MFC ActiveX 컨트롤: 스톡 속성 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- BackColor property [MFC]
- properties [MFC], adding stock
- ForeColor property [MFC]
- MFC ActiveX controls [MFC], properties
- foreground colors, ActiveX controls
- foreground colors [MFC]
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
ms.openlocfilehash: 16bdfddf0c028bc6a312767844b38c58c942d56e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364656"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>MFC ActiveX 컨트롤: 스톡 속성 추가

Stock 속성은 클래스에서 `COleControl`이미 구현되어 있다는 점에서 사용자 지정 속성과 다릅니다. `COleControl`에는 컨트롤에 대한 공통 속성을 지원하는 미리 정의된 멤버 함수가 포함되어 있습니다. 일부 일반적인 속성에는 컨트롤의 캡션과 전경 및 배경 색이 포함됩니다. 다른 스톡 속성에 대한 자세한 내용은 이 문서의 후반부 [속성 추가 마법사에서 지원하는 스톡 속성을](#_core_stock_properties_supported_by_classwizard) 참조하십시오. 스톡 속성에 대한 디스패치 맵 항목은 항상 DISP_STOCKPROP 접두어로 고정됩니다.

이 문서에서는 속성 추가 마법사를 사용하여 Stock 속성(이 경우 캡션)을 ActiveX 컨트롤에 추가하는 방법을 설명하고 결과 코드 수정에 대해 설명합니다. 다룰 주제는 다음과 같습니다.

- [속성 추가 마법사를 사용하여 스톡 속성 추가](#_core_using_classwizard_to_add_a_stock_property)

- [스톡 속성에 대한 속성 마법사 변경 내용 추가](#_core_classwizard_changes_for_stock_properties)

- [속성 추가 마법사에서 지원하는 스톡 속성](#_core_stock_properties_supported_by_classwizard)

- [재고 속성 및 알림](#_core_stock_properties_and_notification)

- [색상 속성](#_core_color_properties)

    > [!NOTE]
    >  Visual Basic 사용자 지정 컨트롤에는 일반적으로 위쪽, 왼쪽, 너비, 높이, 정렬, 태그, 이름, TabIndex, TabStop 및 부모와 같은 속성이 있습니다. 그러나 ActiveX 제어 컨테이너는 이러한 제어 속성을 구현해야 하므로 ActiveX 컨트롤은 이러한 속성을 지원하지 않아야 합니다.

## <a name="using-the-add-property-wizard-to-add-a-stock-property"></a><a name="_core_using_classwizard_to_add_a_stock_property"></a>속성 추가 마법사를 사용하여 스톡 속성 추가

속성에 대한 지원이 에서 자동으로 처리되므로 stock 속성을 추가하려면 `COleControl`사용자 지정 속성을 추가하는 것보다 코드가 더 적게 필요합니다. 다음 절차에서는 stock Caption 속성을 ActiveX 컨트롤 프레임워크에 추가하는 방법을 보여 주며 다른 스톡 속성을 추가하는 데도 사용할 수 있습니다. 선택한 스톡 속성 이름을 캡션으로 대체합니다.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용하여 스톡 캡션 속성을 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **속성 추가를** 클릭한 다음 **속성 추가를**클릭합니다.

   그러면 [속성 추가 마법사가](../ide/names-add-property-wizard.md)열립니다.

1. 속성 **이름** 상자에서 **캡션을**클릭합니다.

1. **Finish**를 클릭합니다.

## <a name="add-property-wizard-changes-for-stock-properties"></a><a name="_core_classwizard_changes_for_stock_properties"></a>스톡 속성에 대한 속성 마법사 변경 내용 추가

stock `COleControl` 속성을 지원하므로 속성 추가 마법사는 클래스 선언을 어떤 식으로든 변경하지 않습니다. 디스패치 맵에 속성을 추가합니다. 속성 추가 마법사는 구현에 있는 컨트롤의 디스패치 맵에 다음 줄을 추가합니다. CPP) 파일:

[!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]

다음 줄이 컨트롤의 인터페이스 설명에 추가됩니다( IDL) 파일:

[!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]

이 줄은 Caption 속성에 특정 ID를 할당합니다. 속성은 바인딩할 수 있으며 값을 수정하기 전에 데이터베이스에서 권한을 요청합니다.

이렇게 하면 컨트롤의 사용자가 캡션 속성을 사용할 수 있습니다. stock 속성의 값을 사용하려면 base 클래스의 멤버 변수 `COleControl` 또는 멤버 함수에 액세스합니다. 이러한 멤버 변수 및 멤버 함수에 대한 자세한 내용은 속성 추가 마법사에서 지원하는 다음 섹션인 Stock Properties를 참조하십시오.

## <a name="stock-properties-supported-by-the-add-property-wizard"></a><a name="_core_stock_properties_supported_by_classwizard"></a>속성 추가 마법사에서 지원하는 스톡 속성

클래스는 `COleControl` 9개의 스톡 속성을 제공합니다. 속성 추가 마법사를 사용하여 원하는 속성을 추가할 수 있습니다.

|속성|디스패치 맵 항목|값에 액세스하는 방법|
|--------------|------------------------|-------------------------|
|`Appearance`|DISP_STOCKPROP_APPEARANCE ()|값에 `m_sAppearance`액세스할 수 있습니다.|
|`BackColor`|DISP_STOCKPROP_BACKCOLOR ()|을 호출하여 `GetBackColor`액세스할 수 있는 값입니다.|
|`BorderStyle`|DISP_STOCKPROP_BORDERSTYLE () )|값에 `m_sBorderStyle`액세스할 수 있습니다.|
|`Caption`|DISP_STOCKPROP_CAPTION ()|을 호출하여 `InternalGetText`액세스할 수 있는 값입니다.|
|`Enabled`|DISP_STOCKPROP_ENABLED ()|값에 `m_bEnabled`액세스할 수 있습니다.|
|`Font`|DISP_STOCKPROP_FONT () )|[MFC ActiveX 컨트롤: 글꼴 사용을](../mfc/mfc-activex-controls-using-fonts.md) 위해 사용 하 여 문서를 참조 하십시오.|
|`ForeColor`|DISP_STOCKPROP_FORECOLOR () )|을 호출하여 `GetForeColor`액세스할 수 있는 값입니다.|
|`hWnd`|DISP_STOCKPROP_HWND ()|값에 `m_hWnd`액세스할 수 있습니다.|
|`Text`|DISP_STOCKPROP_TEXT () )|을 호출하여 `InternalGetText`액세스할 수 있는 값입니다. 이 속성은 `Caption`속성 이름을 제외한 와 동일합니다.|
|`ReadyState`|DISP_STOCKPROP_READYSTATE()|`m_lReadyState` 또는`GetReadyState`|

## <a name="stock-properties-and-notification"></a><a name="_core_stock_properties_and_notification"></a>스톡 속성 및 알림

대부분의 스톡 속성에는 재정의할 수 있는 알림 기능이 있습니다. 예를 들어 속성이 `BackColor` 변경될 때마다 `OnBackColorChanged` 함수(컨트롤 클래스의 멤버 함수)가 호출됩니다. 기본 `COleControl`구현(in)이 `InvalidateControl`를 호출합니다. 이 상황에 대 한 응답으로 추가 작업을 수행 하려는 경우이 함수를 재정의 합니다.

## <a name="color-properties"></a><a name="_core_color_properties"></a>색상 속성

컨트롤을 페인팅할 때 스톡 `ForeColor` 및 `BackColor` 속성 또는 사용자 지정 색상 속성을 사용할 수 있습니다. 색상 속성을 사용하려면 [COleControl::TranslateColor](../mfc/reference/colecontrol-class.md#translatecolor) 멤버 함수를 호출합니다. 이 함수의 매개 변수는 색상 속성값과 선택적 팔레트 핸들입니다. 반환 값은 와 `SetTextColor` `CreateSolidBrush`같은 GDI 함수에 전달될 수 있는 **COLORREF** 값입니다.

주식 `ForeColor` 및 `BackColor` 속성에 대한 색상 값은 각각 `GetForeColor` 또는 `GetBackColor` 함수를 호출하여 액세스됩니다.

다음 예제에서는 컨트롤을 페인팅할 때 이러한 두 가지 색상 속성을 사용하는 것을 보여 줍니다. 임시 **COLORREF** `CBrush` 변수와 호출된 개체를 `TranslateColor` `ForeColor` `BackColor` 초기화합니다. 그런 `CBrush` 다음 임시 개체를 사용하여 컨트롤의 사각형을 페인팅하고 속성으로 `ForeColor` 텍스트 색상을 설정합니다.

[!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)<br/>
[콜레컨트롤 클래스](../mfc/reference/colecontrol-class.md)
