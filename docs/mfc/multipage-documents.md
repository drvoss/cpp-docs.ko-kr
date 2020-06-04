---
title: 다중 페이지 문서
ms.date: 11/19/2018
helpviewer_keywords:
- pagination [MFC]
- overriding [MFC], View class functions for printing
- OnPrepareDC method [MFC]
- CPrintInfo structure [MFC], multipage documents
- OnEndPrinting method [MFC]
- protocols [MFC], printing protocol
- document pages vs. printer pages [MFC]
- printer mode [MFC]
- printing [MFC], multipage documents
- printers [MFC], printer mode
- documents [MFC], printing
- OnPreparePrinting method [MFC]
- OnPrint method [MFC]
- DoPreparePrinting method and pagination [MFC]
- OnDraw method [MFC], printing
- pagination [MFC], printing multipage documents
- printing [MFC], protocol
- pages [MFC], printing
- OnBeginPrinting method [MFC]
- multipage documents [MFC]
- printing [MFC], pagination
- documents [MFC], paginating
ms.assetid: 69626b86-73ac-4b74-b126-9955034835ef
ms.openlocfilehash: 87912c06a40740d25530235ee421c6c8bfa11aab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370731"
---
# <a name="multipage-documents"></a>다중 페이지 문서

이 문서에서는 Windows 인쇄 프로토콜에 대해 설명하고 두 개 이상의 페이지를 포함하는 문서를 인쇄하는 방법을 설명합니다. 이 문서에서는 다음 항목을 다룹니다.

- [인쇄 프로토콜](#_core_the_printing_protocol)

- [뷰 클래스 함수 재정의](#_core_overriding_view_class_functions)

- [페이지 매김](#_core_pagination)

- [프린터 페이지 와 문서 페이지](#_core_printer_pages_vs.._document_pages)

- [인쇄 시간 페이지 박리](#_core_print.2d.time_pagination)

## <a name="the-printing-protocol"></a><a name="_core_the_printing_protocol"></a>인쇄 프로토콜

다중 페이지 문서를 인쇄하려면 프레임워크와 뷰가 다음과 같은 방식으로 상호 작용합니다. 먼저 프레임워크는 **인쇄** 대화 상자를 표시하고, 프린터에 대한 장치 컨텍스트를 만들고, [CDC](../mfc/reference/cdc-class.md) 개체의 [StartDoc](../mfc/reference/cdc-class.md#startdoc) 멤버 함수를 호출합니다. 그런 다음 문서의 각 페이지에 대해 프레임워크는 `CDC` 개체의 [StartPage](../mfc/reference/cdc-class.md#startpage) 멤버 함수를 호출하고 뷰 개체에 페이지를 인쇄하도록 지시하고 [EndPage](../mfc/reference/cdc-class.md#endpage) 멤버 함수를 호출합니다. 특정 페이지를 시작하기 전에 프린터 모드를 변경해야 하는 경우 뷰는 새 프린터 모드 정보가 포함된 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 구조를 업데이트하는 [ResetDC를](../mfc/reference/cdc-class.md#resetdc)호출합니다. 전체 문서가 인쇄되면 프레임워크는 [EndDoc](../mfc/reference/cdc-class.md#enddoc) 멤버 함수를 호출합니다.

## <a name="overriding-view-class-functions"></a><a name="_core_overriding_view_class_functions"></a>뷰 클래스 함수 재정의

[CView](../mfc/reference/cview-class.md) 클래스는 인쇄 하는 동안 프레임 워크에 의해 호출 되는 여러 멤버 함수를 정의 합니다. 뷰 클래스에서 이러한 함수를 재정의하면 프레임워크의 인쇄 논리와 뷰 클래스의 인쇄 논리 간의 연결을 제공합니다. 다음 표에는 이러한 멤버 함수가 나열되어 있습니다.

### <a name="cviews-overridable-functions-for-printing"></a>인쇄를 위한 CView의 재정의 가능한 기능

|속성|재정의 이유|
|----------|---------------------------|
|[온Prepare 프린팅](../mfc/reference/cview-class.md#onprepareprinting)|[복사] 대화 상자에 값을 삽입하려면, 특히 문서의 길이|
|[온비인프린팅](../mfc/reference/cview-class.md#onbeginprinting)|글꼴 또는 기타 GDI 리소스를 할당하려면|
|[온PrepareDC](../mfc/reference/cview-class.md#onpreparedc)|지정된 페이지에 대한 장치 컨텍스트의 속성을 조정하거나 인쇄 시간 페이지 설정을 수행하려면|
|[Onprint](../mfc/reference/cview-class.md#onprint)|지정된 페이지를 인쇄하려면|
|[온엔드프린팅](../mfc/reference/cview-class.md#onendprinting)|GDI 리소스 할당 할당|

다른 기능에서도 인쇄 관련 처리를 수행할 수 있지만 이러한 기능은 인쇄 프로세스를 구동하는 기능입니다.

다음 그림은 인쇄 프로세스와 관련된 단계를 보여 주며 `CView`각 인쇄 멤버 함수가 호출되는 위치를 보여 줍니다. 이 문서의 나머지 부분에서는 이러한 단계의 대부분을 자세히 설명합니다. 인쇄 프로세스의 추가 부분은 [GDI 리소스 할당](../mfc/allocating-gdi-resources.md)문서에 설명되어 있습니다.

![루프 프로세스 인쇄](../mfc/media/vc37c71.gif "루프 프로세스 인쇄") <br/>
인쇄 루프

## <a name="pagination"></a><a name="_core_pagination"></a> 페이지 매김

프레임워크는 인쇄 작업에 대한 많은 정보를 [CPrintInfo](../mfc/reference/cprintinfo-structure.md) 구조에 저장합니다. 패기와 `CPrintInfo` 관련된 값 중 몇 가지; 이러한 값은 다음 표에 표시된 대로 액세스할 수 있습니다.

### <a name="page-number-information-stored-in-cprintinfo"></a>CPrintInfo에 저장된 페이지 번호 정보

|멤버 변수 또는<br /><br /> 함수 이름|참조된 페이지 번호|
|-----------------------------------------------|----------------------------|
|`GetMinPage`/`SetMinPage`|문서의 첫 페이지|
|`GetMaxPage`/`SetMaxPage`|문서의 마지막 페이지|
|`GetFromPage`|인쇄할 첫 페이지|
|`GetToPage`|인쇄할 마지막 페이지|
|`m_nCurPage`|현재 인쇄 중인 페이지|

페이지 번호는 1에서 시작, 즉, 첫 번째 페이지는 번호가 1이 아닌 0입니다. 이러한 멤버 및 [CPrintInfo의](../mfc/reference/cprintinfo-structure.md)다른 멤버에 대한 자세한 내용은 *MFC 참조를*참조하십시오.

인쇄 프로세스가 시작될 때 프레임워크는 뷰의 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 멤버 함수를 호출하여 `CPrintInfo` 구조에 대한 포인터를 전달합니다. 응용 프로그램 마법사는 `OnPreparePrinting` DoPreparePrinting 의 또 다른 `CView`멤버 함수인 [DoPreparePrinting](../mfc/reference/cview-class.md#doprepareprinting)호출의 구현을 제공합니다. `DoPreparePrinting`은 프린터 장치 컨텍스트를 만드는 기능입니다.

이 시점에서 응용 프로그램은 문서에 있는 페이지 수를 알 수 없습니다. 문서의 첫 번째 및 마지막 페이지의 숫자에 대해 기본값 1및 0xFFFF를 사용합니다. 문서에 있는 페이지 수를 알고 있는 `OnPreparePrinting` 경우 을 보내기 전에 `CPrintInfo` 구조체에 대해 [SetMaxPage]-brokenlink--(참조/cprintinfo-class.md#setmaxpage)를 재정의하고 호출합니다. `DoPreparePrinting` 이렇게 하면 문서 의 길이를 지정할 수 있습니다.

`DoPreparePrinting`그런 다음 인쇄 대화 상자가 표시됩니다. 반환할 때 `CPrintInfo` 구조에는 사용자가 지정한 값이 포함됩니다. 사용자가 선택한 페이지 범위만 인쇄하려는 경우 인쇄 대화 상자에서 시작 및 종료 페이지 번호를 지정할 수 있습니다. 프레임워크는 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)의 `GetFromPage` `GetToPage` 함수를 사용하여 이러한 값을 검색합니다. 사용자가 페이지 범위를 지정하지 않으면 프레임워크가 `GetMinPage` 호출하고 `GetMaxPage` 반환된 값을 사용하여 전체 문서를 인쇄합니다.

인쇄할 문서의 각 페이지에 대해 프레임워크는 뷰 클래스의 두 멤버 [함수인 OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) 및 [OnPrint를](../mfc/reference/cview-class.md#onprint)호출하고 각 함수에 [CDC](../mfc/reference/cdc-class.md) 개체에 대한 포인터와 `CPrintInfo` 구조체에 대한 포인터의 두 가지 매개 변수를 전달합니다. 프레임워크가 호출될 `OnPrepareDC` `OnPrint`때마다 구조의 *m_nCurPage* 멤버에서 다른 `CPrintInfo` 값을 전달합니다. 이러한 방식으로 프레임워크는 인쇄할 페이지를 뷰에 알려줍니다.

[OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) 멤버 기능은 화면 표시에도 사용됩니다. 드로잉이 수행되기 전에 장치 컨텍스트를 조정합니다. `OnPrepareDC`인쇄에서 비슷한 역할을 하지만 몇 가지 차이점이 있습니다: `CDC` 첫째, 개체는 화면 장치 컨텍스트 대신 프린터 `CPrintInfo` 장치 컨텍스트를 나타내고 두 번째는 개체가 두 번째 매개 변수로 전달됩니다. (이 매개 변수는 화면 표시를 위해 호출될 때 `OnPrepareDC` **NULL입니다.)** 재정의하여 `OnPrepareDC` 인쇄중인 페이지에 따라 장치 컨텍스트를 조정합니다. 예를 들어 뷰포트 원점이와 클리핑 영역을 이동하여 문서의 적절한 부분이 인쇄되도록 할 수 있습니다.

[OnPrint](../mfc/reference/cview-class.md#onprint) 멤버 함수는 페이지의 실제 인쇄를 수행합니다. 기본 [인쇄가 수행되는 방법](../mfc/how-default-printing-is-done.md) 문서에서는 프레임워크가 인쇄를 수행하기 위해 프린터 장치 컨텍스트를 사용하여 [OnDraw를](../mfc/reference/cview-class.md#ondraw) 호출하는 방법을 보여 주며 있습니다. 보다 정확하게 말하면 `OnPrint` 프레임워크는 `CPrintInfo` 구조 및 장치 `OnPrint` 컨텍스트를 사용하여 `OnDraw`장치 컨텍스트를 로 전달합니다. 재재정은 인쇄 중에만 수행해야 하며 화면 표시가 아닌 렌더링을 수행하도록 재정의합니다. `OnPrint` 예를 들어 헤더 또는 바닥글을 인쇄하려면(자세한 내용은 [헤더 및 바닥글](../mfc/headers-and-footers.md) 문서 참조). 그런 `OnDraw` 다음 재정의를 `OnPrint` 호출하여 화면 표시 및 인쇄에 공통적인 렌더링을 수행합니다.

화면 표시와 인쇄 모두에 대한 렌더링을 수행한다는 `OnDraw` 사실은 응용 프로그램이 WYSIWYG라는 것을 의미합니다. 그러나 WYSIWYG 응용 프로그램을 작성하지 않는다고 가정합니다. 예를 들어 인쇄에 굵은 글꼴을 사용하지만 화면에 굵은 텍스트를 나타내는 컨트롤 코드를 표시하는 텍스트 편집기를 고려해 보겠습니다. 이러한 상황에서는 화면 `OnDraw` 표시에 엄격하게 사용합니다. 재정의할 `OnPrint`때 호출을 `OnDraw` 별도의 그리기 함수에 대한 호출로 대체합니다. 이 함수는 화면에 표시되지 않는 속성을 사용하여 문서에 나타나는 방식을 그립니다.

## <a name="printer-pages-vs-document-pages"></a><a name="_core_printer_pages_vs.._document_pages"></a>프린터 페이지 와 문서 페이지

페이지 번호를 참조할 때 프린터의 페이지 개념과 문서의 페이지 개념을 구분해야 하는 경우가 있습니다. 프린터의 관점에서 페이지는 한 장의 용지입니다. 그러나 한 장의 용지가 반드시 문서의 한 페이지와 같지는 않습니다. 예를 들어 시트를 접을 수 있는 뉴스레터를 인쇄하는 경우 한 장의 용지에 문서의 첫 페이지와 마지막 페이지가 나란히 포함될 수 있습니다. 마찬가지로 스프레드시트를 인쇄하는 경우 문서는 페이지로 전혀 구성되지 않습니다. 대신 한 장의 용지에는 1~20열, 6~10열행이 포함될 수 있습니다.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md) 구조의 모든 페이지 번호는 프린터 페이지를 참조합니다. 프레임워크는 `OnPrepareDC` 프린터를 `OnPrint` 통과하는 각 용지에 대해 한 번씩 호출합니다. 문서 길이를 지정하기 위해 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 기능을 재정의할 때 프린터 페이지를 사용해야 합니다. 일대일 대응이 있는 경우(즉, 하나의 프린터 페이지가 하나의 문서 페이지와 같음) 이것은 쉽습니다. 반면에 문서 페이지와 프린터 페이지가 직접 일치하지 않으면 문서 페이지 간에 번역해야 합니다. 예를 들어 스프레드시트를 인쇄하는 것이 좋습니다. 재정의 `OnPreparePrinting`할 때 전체 스프레드시트를 인쇄하는 데 필요한 용지 수를 계산한 다음 `SetMaxPage` 의 `CPrintInfo`멤버 함수를 호출할 때 해당 값을 사용해야 합니다. 마찬가지로 재정의 `OnPrepareDC`할 때는 *m_nCurPage* 특정 시트에 표시되는 행 과 열의 범위로 변환한 다음 그에 따라 뷰포트 원점을 조정해야 합니다.

## <a name="print-time-pagination"></a><a name="_core_print.2d.time_pagination"></a>인쇄 시간 페이지

경우에 따라 뷰 클래스는 문서가 실제로 인쇄될 때까지 문서가 얼마나 걸리는지 미리 알지 못할 수 있습니다. 예를 들어 응용 프로그램이 WYSIWYG가 아니므로 화면의 문서 길이가 인쇄될 때의 길이와 일치하지 않는다고 가정합니다.

이렇게 하면 뷰 클래스에 대한 [OnPreparePrinting를](../mfc/reference/cview-class.md#onprepareprinting) 재정의할 `SetMaxPage` 때 문제가 발생합니다. [CPrintInfo](../mfc/reference/cprintinfo-structure.md) 사용자가 인쇄 대화 상자 사용을 중지할 페이지 번호를 지정하지 않으면 프레임워크에서 인쇄 루프를 중지할 시기를 알 수 없습니다. 인쇄 루프를 중지할 시기를 결정하는 유일한 방법은 문서를 인쇄하고 끝나는 시기를 확인하는 것입니다. 뷰 클래스는 문서가 인쇄되는 동안 문서의 끝을 확인한 다음 끝에 도달하면 프레임워크에 알려야 합니다.

프레임워크는 뷰 클래스의 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) 함수를 사용하여 중지 시기를 알려줍니다. 호출할 `OnPrepareDC`때마다 프레임워크는 *m_bContinuePrinting*라는 `CPrintInfo` 구조의 멤버를 확인합니다. 기본값은 **TRUE입니다.** 그래도 남아 있는 한 프레임워크는 인쇄 루프를 계속합니다. **FALSE로**설정하면 프레임워크가 중지됩니다. 인쇄 시간 페이지 설정을 수행하려면 `OnPrepareDC` 재정의하여 문서의 끝에 도달했는지 확인하고 문서가 있는 경우 **false로** *m_bContinuePrinting* 설정합니다.

집합의 `OnPrepareDC` 기본 구현은 현재 페이지가 1보다 큰 경우 **false로** *m_bContinuePrinting.* 즉, 문서 길이를 지정하지 않은 경우 프레임워크는 문서가 한 페이지 길이라고 가정합니다. 이 것의 한 가지 결과는 의 기본 클래스 버전을 `OnPrepareDC`호출하는 경우주의해야한다는 것입니다. 기본 클래스 버전을 호출한 후 *m_bContinuePrinting* **TRUE라고** 가정하지 마십시오.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [헤더 및 바닥글](../mfc/headers-and-footers.md)

- [GDI 리소스 할당](../mfc/allocating-gdi-resources.md)

## <a name="see-also"></a>참고 항목

[인쇄](../mfc/printing.md)<br/>
[CView 클래스](../mfc/reference/cview-class.md)<br/>
[CDC 클래스](../mfc/reference/cdc-class.md)
