---
title: 리본 디자이너(MFC)
ms.date: 11/19/2018
f1_keywords:
- vc.editors.ribbon.F1
helpviewer_keywords:
- Ribbon Designer (MFC)
- MFC Ribbon Designer
ms.assetid: 0806dfd6-7d11-471a-99e1-4072852231f9
ms.openlocfilehash: 8b66ff0f19392eb1685f8632a3fc4d9e90094304
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372795"
---
# <a name="ribbon-designer-mfc"></a>리본 디자이너(MFC)

리본 디자이너를 사용하여 MFC 애플리케이션에서 리본을 만들고 사용자 지정할 수 있습니다. 리본은 명령을 논리 그룹으로 구성하는 UI(사용자 인터페이스) 요소입니다. 이러한 그룹은 창 위쪽을 가로지르는 스트립에 별도의 탭으로 나타납니다. 리본은 메뉴 모음 및 도구 모음을 대체합니다. 리본으로 애플리케이션 사용 편의성을 크게 향상시킬 수 있습니다. 자세한 내용은 [리본 을 참조하십시오.](/windows/win32/uxguide/cmd-ribbons) 다음 그림에서는 리본을 보여 줍니다.

![MFC 리본 리소스 컨트롤](../mfc/media/ribbon_no_callouts.png "MFC 리본 리소스 컨트롤")

이전 버전의 Visual Studio에서는 [CMFCRibbonBar 클래스와](../mfc/reference/cmfcribbonbar-class.md)같은 MFC 리본 클래스를 사용하는 코드를 작성하여 리본을 만들어야 했습니다. Visual Studio 2010 이상에서 리본 디자이너는 리본을 작성하는 다른 방법을 제공합니다. 먼저 리소스로 리본을 만들고 사용자 지정합니다. 그런 다음 MFC 애플리케이션의 코드에서 리본 리소스를 로드합니다. 리본 리소스와 MFC 리본 클래스를 함께 사용할 수도 있습니다. 예를 들어 리본 리소스를 만든 다음 런타임에 코드를 사용하여 프로그래밍 방식으로 더 많은 요소를 추가할 수 있습니다.

## <a name="understanding-the-ribbon-designer"></a>리본 디자이너 이해

리본 디자이너는 리소스로 리본을 만들고 저장합니다. 리본 리소스를 만들 때 리본 디자이너는 다음과 같은 세 가지 작업을 수행합니다.

- 프로젝트 리소스 정의 스크립트(*.rc)에 항목을 추가합니다. 다음 예제에서는 IDR_RIBBON 리본 리소스를 식별하는 고유한 이름, RT_RIBBON_XML 리소스 유형이며 ribbon.mfcribbon-ms는 리소스 파일의 이름입니다.

```cpp
    IDR_RIBBON RT_RIBBON_XML      "res\\ribbon.mfcribbon-ms"
```

- resource.h에 명령 ID의 정의를 추가합니다.

```
#define IDR_RIBBON            307
```

- 리본의 단추, 컨트롤 및 특성을 정의하는 XML 코드가 포함되는 리본 리소스 파일(*.mfcribbon-ms)을 만듭니다. 리본 디자이너에서 리본을 변경한 내용은 XML로 리소스 파일에 저장됩니다. 다음 코드 예제에서는 \*.mfcribbon-ms 파일의 내용의 일부를 보여 주며 있습니다.

```
<RIBBON_BAR>
<ELEMENT_NAME>RibbonBar</ELEMENT_NAME>
<IMAGE>
<ID>
<NAME>IDB_BUTTONS</NAME>
<VALUE>113</VALUE>
</ID>
```

MFC 응용 프로그램에서 리본 리소스를 사용하려면 [CMFCRibbonBar::LoadFromResource](../mfc/reference/cmfcribbonbar-class.md#loadfromresource)를 호출하여 리소스를 로드합니다.

## <a name="creating-a-ribbon-by-using-the-ribbon-designer"></a>리본 디자이너를 사용하여 리본 만들기

다음은 MFC 프로젝트에 리본 리소스를 추가하는 두 가지 방법입니다.

- MFC 애플리케이션을 만들고 MFC 프로젝트 마법사를 구성하여 리본을 만듭니다. 자세한 내용은 [연습: MFC를 사용하여 리본 응용 프로그램 만들기를](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md)참조하십시오.

- 기존 MFC 프로젝트에서 리본 리소스를 만들고 로드합니다. 자세한 내용은 [연습: MFC 낙서 응용 프로그램 업데이트(1부)를](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)참조하십시오.

프로젝트에 수동으로 코딩된 리본이 이미 있는 경우 MFC에서 기존 리본을 리본 리소스로 변환하는 데 사용할 수 있는 함수를 제공합니다. 자세한 내용은 [사용 방법: 기존 MFC 리본을 리본 리소스로 변환하는](../mfc/how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource.md)방법을 참조하십시오.

> [!NOTE]
> 대화 상자 기반 애플리케이션에서는 리본을 만들 수 없습니다. 자세한 내용은 [응용 프로그램 유형, MFC 응용 프로그램 마법사를](../mfc/reference/application-type-mfc-application-wizard.md)참조하십시오.

## <a name="customizing-ribbons"></a>리본 사용자 지정

리본 디자이너에서 리본을 열려면 리소스 뷰에서 리본 리소스를 두 번 클릭합니다. 디자이너에서 리본의 요소, 애플리케이션 단추 또는 빠른 실행 도구 모음을 추가, 제거 및 사용자 지정할 수 있습니다. 이벤트(예: 단추 클릭 이벤트 및 메뉴 이벤트)를 애플리케이션의 메서드에 연결할 수도 있습니다.

다음 그림에서는 리본 디자이너의 다양한 구성 요소를 보여 줍니다.

![MFC 리본 디자이너](../mfc/media/ribbon_designer.png "MFC 리본 디자이너")

- **도구 상자:** 디자이너 표면으로 드래그할 수 있는 컨트롤을 포함합니다.

- **디자이너 표면:** 리본 리소스의 시각적 표현을 포함합니다.

- ** [클래스 마법사](reference/mfc-class-wizard.md):** 디자이너 표면에서 선택한 항목의 특성을 나열합니다.

- **리소스 보기 창:** 프로젝트에 리본 리소스가 포함된 리소스를 표시합니다.

- **리본 편집기 도구 모음:** 리본을 미리 보고 시각적 테마를 변경할 수 있는 명령이 포함되어 있습니다.

다음 항목에서는 리본 디자이너의 기능을 사용하는 방법에 대해 설명합니다.

- [방법: 애플리케이션 단추 사용자 지정](../mfc/how-to-customize-the-application-button.md)

- [방법: 빠른 실행 도구 모음 사용자 지정](../mfc/how-to-customize-the-quick-access-toolbar.md)

- [방법: 리본 컨트롤 및 이벤트 처리기 추가](../mfc/how-to-add-ribbon-controls-and-event-handlers.md)

- [방법: MFC 애플리케이션에서 리본 리소스 로드](../mfc/how-to-load-a-ribbon-resource-from-an-mfc-application.md)

## <a name="definitions-of-ribbon-elements"></a>리본 요소의 정의

![MFC 리본](../mfc/media/ribbon.png "MFC 리본")

- **응용 프로그램 버튼:** 리본의 왼쪽 위 모서리에 나타나는 단추입니다. 애플리케이션 단추는 파일 메뉴를 대체하고 리본이 최소화되는 경우에도 표시됩니다. 이 단추를 클릭하면 명령 목록이 있는 메뉴가 표시됩니다.

- **빠른 액세스 도구 모음:** 자주 사용하는 명령을 표시하는 작고 사용자 지정 가능한 도구 모음입니다.

- **범주**: 리본 탭의 내용을 나타내는 논리적 그룹입니다.

- **범주 기본 버튼:** 리본이 최소화될 때 리본에 나타나는 단추입니다. 단추를 클릭하면 범주가 메뉴로 다시 나타납니다.

- **패널:** 관련 컨트롤 그룹을 표시하는 리본 막대의 영역입니다. 모든 리본 범주에는 하나 이상의 리본 패널이 있습니다.

- **리본 요소:** 패널의 컨트롤(예: 단추 및 콤보 상자). 리본에서 호스팅할 수 있는 다양한 컨트롤을 보려면 [RibbonGadgets 샘플: 리본 가젯 응용 프로그램을](../overview/visual-cpp-samples.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)<br/>
[리소스 파일 작업](../windows/working-with-resource-files.md)
