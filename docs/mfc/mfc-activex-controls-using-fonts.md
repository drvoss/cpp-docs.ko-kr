---
title: 'MFC ActiveX 컨트롤: 글꼴 사용'
ms.date: 11/19/2018
f1_keywords:
- OnFontChanged
- HeadingFont
- InternalFont
helpviewer_keywords:
- notifications [MFC], MFC ActiveX controls fonts
- OnDraw method, MFC ActiveX controls
- InternalFont method [MFC]
- SetFont method [MFC]
- OnFontChanged method [MFC]
- IPropertyNotifySink class [MFC]
- MFC ActiveX controls [MFC], fonts
- Stock Font property [MFC]
- HeadingFont property [MFC]
- GetFont method [MFC]
- SelectStockFont method [MFC]
- fonts [MFC], ActiveX controls
ms.assetid: 7c51d602-3f5a-481d-84d1-a5d8a3a71761
ms.openlocfilehash: c336ec6c29b5478655ca8f19f71378a2b446ac64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358266"
---
# <a name="mfc-activex-controls-using-fonts"></a>MFC ActiveX 컨트롤: 글꼴 사용

ActiveX 컨트롤에 텍스트가 표시되는 경우 컨트롤 사용자가 글꼴 속성을 변경하여 텍스트 모양을 변경하도록 허용할 수 있습니다. 글꼴 속성은 글꼴 개체로 구현되며 스톡 또는 사용자 지정의 두 가지 유형 중 하나가 될 수 있습니다. 스톡 Font 속성은 속성 추가 마법사를 사용하여 추가할 수 있는 미리 구현된 글꼴 속성입니다. 사용자 지정 Font 속성은 미리 구현되지 않으며 컨트롤 개발자는 속성의 동작 및 사용을 결정합니다.

이 문서는 다음 항목을 설명합니다.

- [스톡 글꼴 속성 사용](#_core_using_the_stock_font_property)

- [컨트롤에서 사용자 지정 글꼴 속성 사용](#_core_implementing_a_custom_font_property)

## <a name="using-the-stock-font-property"></a><a name="_core_using_the_stock_font_property"></a>스톡 글꼴 속성 사용

스톡 글꼴 속성은 [클래스 COleControl에](../mfc/reference/colecontrol-class.md)의해 미리 구현됩니다. 또한 표준 Font 속성 페이지도 사용할 수 있으므로 사용자는 이름, 크기 및 스타일과 같은 글꼴 개체의 다양한 속성을 변경할 수 있습니다.

[의 GetFont,](../mfc/reference/colecontrol-class.md#getfont) [SetFont](../mfc/reference/colecontrol-class.md#setfont)및 [내부GetFont](../mfc/reference/colecontrol-class.md#internalgetfont) 함수를 통해 `COleControl`글꼴 개체에 액세스합니다. 컨트롤 사용자는 다른 Get/Set `GetFont` 속성과 동일한 방식으로 및 `SetFont` 기능을 통해 글꼴 개체에 액세스합니다. 컨트롤 내에서 글꼴 개체에 액세스해야 하는 `InternalGetFont` 경우 이 함수를 사용합니다.

[MFC ActiveX 컨트롤에서](../mfc/mfc-activex-controls-properties.md)설명한 대로 속성, 속성 [추가](../ide/names-add-property-wizard.md)마법사를 사용하면 쉽게 스톡 속성을 추가할 수 있습니다. Font 속성을 선택하면 속성 추가 마법사가 컨트롤의 디스패치 맵에 스톡 글꼴 항목을 자동으로 삽입합니다.

#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용하여 스톡 Font 속성을 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **속성 추가를** 클릭한 다음 **속성 추가를**클릭합니다.

   그러면 속성 추가 마법사가 열립니다.

1. 속성 **이름** 상자에서 **글꼴**을 클릭합니다.

1. **Finish**를 클릭합니다.

속성 추가 마법사는 컨트롤 클래스 구현 파일에 있는 컨트롤의 디스패치 맵에 다음 줄을 추가합니다.

[!code-cpp[NVC_MFC_AxFont#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]

또한 속성 추가 마법사는 컨트롤에 다음 줄을 추가합니다. IDL 파일:

[!code-cpp[NVC_MFC_AxFont#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]

스톡 캡션 속성은 스톡 Font 속성 정보를 사용하여 그릴 수 있는 텍스트 속성의 예입니다. 컨트롤에 스톡 캡션 속성을 추가하면 스톡 Font 속성에 사용되는 것과 유사한 단계가 사용됩니다.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용하여 스톡 캡션 속성을 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **속성 추가를** 클릭한 다음 **속성 추가를**클릭합니다.

   그러면 속성 추가 마법사가 열립니다.

1. 속성 **이름** 상자에서 **캡션을**클릭합니다.

1. **Finish**를 클릭합니다.

속성 추가 마법사는 컨트롤 클래스 구현 파일에 있는 컨트롤의 디스패치 맵에 다음 줄을 추가합니다.

[!code-cpp[NVC_MFC_AxFont#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]

## <a name="modifying-the-ondraw-function"></a><a name="_core_modifying_the_ondraw_function"></a>OnDraw 함수 수정

기본 구현은 `OnDraw` 컨트롤에 표시되는 모든 텍스트에 대해 Windows 시스템 글꼴을 사용합니다. 즉, 장치 컨텍스트에 `OnDraw` 글꼴 개체를 선택 하 여 코드를 수정 해야 합니다. 이렇게 하려면 [COleControl::SelectStockFont를](../mfc/reference/colecontrol-class.md#selectstockfont) 호출하고 다음 예제와 같이 컨트롤의 장치 컨텍스트를 전달합니다.

[!code-cpp[NVC_MFC_AxFont#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]

글꼴 `OnDraw` 개체를 사용하도록 함수를 수정한 후 컨트롤 내의 모든 텍스트는 컨트롤의 스톡 Font 속성의 특성으로 표시됩니다.

## <a name="using-custom-font-properties-in-your-control"></a><a name="_core_using_custom_font_properties_in_your_control"></a>컨트롤에서 사용자 지정 글꼴 속성 사용

Stock Font 속성 외에도 ActiveX 컨트롤에는 사용자 지정 Font 속성이 있을 수 있습니다. 사용자 지정 글꼴 속성을 추가하려면 다음을 수행해야 합니다.

- 속성 추가 마법사를 사용하여 사용자 지정 Font 속성을 구현합니다.

- [글꼴 알림 처리](#_core_processing_font_notifications).

- [새 글꼴 알림 인터페이스 구현](#_core_implementing_a_new_font_notification_interface).

### <a name="implementing-a-custom-font-property"></a><a name="_core_implementing_a_custom_font_property"></a>사용자 지정 글꼴 속성 구현

사용자 지정 Font 속성을 구현하려면 속성 추가 마법사를 사용하여 속성을 추가한 다음 코드를 일부 수정합니다. 다음 섹션에서는 샘플 컨트롤에 `HeadingFont` 사용자 지정 속성을 추가하는 방법을 설명합니다.

##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용하여 사용자 지정 Font 속성을 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **속성 추가를** 클릭한 다음 **속성 추가를**클릭합니다.

   그러면 속성 추가 마법사가 열립니다.

1. 속성 **이름** 상자에 속성의 이름을 입력합니다. 이 예제에서는 **제목 글꼴을**사용합니다.

1. **구현 형식**에서 **Get/Set 메서드**를 클릭합니다.

1. 속성 **유형** 상자에서 속성 유형에 대한 **IDispatch를** <strong>\*</strong> 선택합니다.

1. **Finish**를 클릭합니다.

속성 추가 마법사는 `HeadingFont` `CSampleCtrl` 클래스 및 샘플에 사용자 지정 속성을 추가하는 코드를 만듭니다. IDL 파일입니다. Get/Set 속성 유형이기 때문에 `HeadingFont` 속성 추가 마법사는 `CSampleCtrl` DISP_PROPERTY_EX_ID[DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex) 매크로 항목을 포함하도록 클래스의 디스패치 맵을 수정합니다.

[!code-cpp[NVC_MFC_AxFont#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]

DISP_PROPERTY_EX 매크로는 `HeadingFont` 속성 이름을 해당 `CSampleCtrl` 클래스 Get 및 `GetHeadingFont` `SetHeadingFont`Set 메서드 및 및 . 속성 값의 형식도 지정됩니다. 이 경우 VT_FONT.

속성 추가 마법사는 컨트롤 헤더 파일에 도 선언을 추가합니다( H) `GetHeadingFont` 및 `SetHeadingFont` 함수에 대해 제어 구현 파일에 해당 함수 템플릿을 추가합니다(. CPP:

[!code-cpp[NVC_MFC_AxFont#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]

마지막으로 속성 추가 마법사는 컨트롤을 수정합니다. `HeadingFont` 속성에 대한 항목을 추가하여 IDL 파일:

[!code-cpp[NVC_MFC_AxFont#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]

### <a name="modifications-to-the-control-code"></a>제어 코드 수정

컨트롤에 `HeadingFont` 속성을 추가한 후 새 속성을 완전히 지원하려면 컨트롤 헤더 및 구현 파일을 일부 변경해야 합니다.

제어 헤더 파일(. H) 보호된 멤버 변수의 다음 선언을 추가합니다.

[!code-cpp[NVC_MFC_AxFont#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]

제어 구현 파일(. CPP) 다음을 수행합니다.

- 컨트롤 생성자에서 *m_fontHeading* 초기화합니다.

   [!code-cpp[NVC_MFC_AxFont#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]

- 글꼴의 기본 속성을 포함하는 정적 FONTDESC 구조를 선언합니다.

   [!code-cpp[NVC_MFC_AxFont#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]

- 컨트롤 `DoPropExchange` 멤버 함수에서 `PX_Font` 함수에 호출을 추가합니다. 이렇게 하면 사용자 지정 Font 속성에 대한 초기화 및 지속성이 제공됩니다.

   [!code-cpp[NVC_MFC_AxFont#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]

- 컨트롤 `GetHeadingFont` 멤버 함수 구현을 완료합니다.

   [!code-cpp[NVC_MFC_AxFont#12](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]

- 컨트롤 `SetHeadingFont` 멤버 함수 구현을 완료합니다.

   [!code-cpp[NVC_MFC_AxFont#13](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]

- 컨트롤 `OnDraw` 멤버 함수를 수정하여 이전에 선택한 글꼴을 보유할 변수를 정의합니다.

   [!code-cpp[NVC_MFC_AxFont#14](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]

- 컨트롤 `OnDraw` 멤버 함수를 수정하여 글꼴을 사용할 위치에 다음 줄을 추가하여 사용자 지정 글꼴을 장치 컨텍스트에 선택합니다.

   [!code-cpp[NVC_MFC_AxFont#15](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]

- 컨트롤 `OnDraw` 멤버 함수를 수정하여 글꼴을 사용한 후 다음 줄을 추가하여 이전 글꼴을 장치 컨텍스트로 다시 선택합니다.

   [!code-cpp[NVC_MFC_AxFont#16](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]

사용자 지정 Font 속성이 구현된 후 컨트롤 사용자가 컨트롤의 현재 글꼴을 변경할 수 있도록 표준 Font 속성 페이지를 구현해야 합니다. 표준 Font 속성 페이지의 속성 페이지 ID를 추가하려면 BEGIN_PROPPAGEIDS 매크로 다음에 다음 줄을 삽입합니다.

[!code-cpp[NVC_MFC_AxFont#17](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]

또한 BEGIN_PROPPAGEIDS 매크로의 개수 매개 변수를 하나씩 증가시켜야 합니다. 다음 줄에서는 이 작업을 보여 줍니다.

[!code-cpp[NVC_MFC_AxFont#18](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]

이러한 변경이 이루어진 후 전체 프로젝트를 다시 빌드하여 추가 기능을 통합합니다.

### <a name="processing-font-notifications"></a><a name="_core_processing_font_notifications"></a>글꼴 알림 처리

대부분의 경우 컨트롤은 글꼴 개체의 특성이 수정된 시기를 알아야 합니다. 각 글꼴 개체는 `IFontNotification` 에 의해 `COleControl`구현된 인터페이스의 멤버 함수를 호출하여 변경될 때 알림을 제공할 수 있습니다.

컨트롤이 stock Font 속성을 사용하는 경우 해당 `OnFontChanged` 알림은 `COleControl`의 멤버 함수에 의해 처리됩니다. 사용자 지정 글꼴 속성을 추가할 때 동일한 구현을 사용하도록 할 수 있습니다. 이전 섹션의 예제에서는 *m_fontHeading* 멤버 변수를 초기화할 때 *&m_xFontNotification* 전달하여 이 작업을 수행했습니다.

![여러 글꼴 개체 인터페이스 구현](../mfc/media/vc373q1.gif "여러 글꼴 개체 인터페이스 구현") <br/>
여러 글꼴 개체 인터페이스 구현

위의 그림의 실선은 두 글꼴 개체가 `IFontNotification`의 동일한 구현을 사용하고 있음을 보여 줍니다. 변경된 글꼴을 구분하려는 경우 문제가 발생할 수 있습니다.

컨트롤의 글꼴 개체 알림을 구분하는 한 가지 방법은 컨트롤의 각 글꼴 개체에 대해 `IFontNotification` 인터페이스의 별도의 구현을 만드는 것입니다. 이 기술을 사용하면 최근에 수정된 글꼴을 사용하는 문자열 또는 문자열만 업데이트하여 그리기 코드를 최적화할 수 있습니다. 다음 섹션에서는 두 번째 Font 속성에 대해 별도의 알림 인터페이스를 구현하는 데 필요한 단계를 보여 줍니다. 두 번째 font 속성은 `HeadingFont` 이전 섹션에 추가된 속성으로 가정합니다.

### <a name="implementing-a-new-font-notification-interface"></a><a name="_core_implementing_a_new_font_notification_interface"></a>새 글꼴 알림 인터페이스 구현

둘 이상의 글꼴 알림을 구분하려면 컨트롤에 사용되는 각 글꼴에 대해 새 알림 인터페이스를 구현해야 합니다. 다음 섹션에서는 컨트롤 헤더 및 구현 파일을 수정하여 새 글꼴 알림 인터페이스를 구현하는 방법을 설명합니다.

### <a name="additions-to-the-header-file"></a>헤더 파일에 추가

제어 헤더 파일(. H) 클래스 선언에 다음 줄을 추가합니다.

[!code-cpp[NVC_MFC_AxFont#19](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]

`IPropertyNotifySink` 이렇게 하면 . `HeadingFontNotify` 이 새 인터페이스에는 `OnChanged`.라는 메서드가 포함되어 있습니다.

### <a name="additions-to-the-implementation-file"></a>구현 파일에 추가

컨트롤 생성자에서 제목 글꼴을 초기화하는 코드에서 *m_xFontNotification* &*m_xHeadingFontNotify*&변경합니다. 다음 코드를 추가합니다.

[!code-cpp[NVC_MFC_AxFont#20](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]

`AddRef` 인터페이스의 `Release` `IPropertyNotifySink` 메서드는 ActiveX 컨트롤 개체에 대한 참조 수를 추적합니다. 컨트롤이 인터페이스 포인터에 대한 액세스를 가져오면 컨트롤은 참조 수를 증가하도록 호출합니다. `AddRef` 컨트롤이 포인터로 완료되면 전역 메모리 `Release`블록을 해제하기 위해 `GlobalFree` 호출될 수 있는 것과 거의 동일한 방식으로 호출됩니다. 이 인터페이스에 대한 참조 수가 0으로 이동하면 인터페이스 구현을 해제할 수 있습니다. 이 예제에서 `QueryInterface` 함수는 특정 개체의 인터페이스에 대한 포인터를 `IPropertyNotifySink` 반환합니다. 이 기능을 사용하면 ActiveX 컨트롤이 개체를 쿼리하여 지원하는 인터페이스를 결정할 수 있습니다.

프로젝트에 이러한 변경사항이 변경된 후 프로젝트를 다시 빌드하고 테스트 컨테이너를 사용하여 인터페이스를 테스트합니다. 테스트 컨테이너에 액세스하는 방법은 [테스트 컨테이너로 속성 및 이벤트 테스트](../mfc/testing-properties-and-events-with-test-container.md) 를 참조하세요.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: ActiveX 컨트롤에서 그림 사용하기](../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)<br/>
[MFC ActiveX 컨트롤: 스톡 속성 페이지 사용](../mfc/mfc-activex-controls-using-stock-property-pages.md)
