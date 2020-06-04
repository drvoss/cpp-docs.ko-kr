---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤에서 데이터 바인딩 사용'
ms.date: 11/19/2018
f1_keywords:
- bindable
- requestedit
- defaultbind
- displaybind
- dispid
helpviewer_keywords:
- MFC ActiveX controls [MFC], data binding
- data binding [MFC], MFC ActiveX controls
- data-bound controls [MFC], MFC ActiveX controls
- controls [MFC], data binding
- bound controls [MFC], MFC ActiveX
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
ms.openlocfilehash: 41ac0180242aea3143a1df2c32dc81fb18cd7dca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370787"
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤에서 데이터 바인딩 사용

ActiveX 컨트롤의 더 강력한 용도 중 하나는 데이터 바인딩으로, 컨트롤의 속성이 데이터베이스의 특정 필드와 바인딩할 수 있습니다. 사용자가 이 바인딩된 속성의 데이터를 수정하면 컨트롤이 데이터베이스에 알것을 지정하고 레코드 필드를 업데이트하도록 요청합니다. 그런 다음 데이터베이스는 요청의 성공 또는 실패에 대한 제어에 대해 통보합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

이 문서에서는 작업의 제어 측면을 다룹니다. 데이터베이스와 데이터 바인딩 상호 작용을 구현하는 것은 제어 컨테이너의 책임입니다. 컨테이너에서 데이터베이스 상호 작용을 관리하는 방법은 이 설명서의 범위를 벗어납니다. 데이터 바인딩에 대한 컨트롤을 준비하는 방법은 이 문서의 나머지 부분에서 설명합니다.

![바인딩된 컨트롤을&#45;데이터 개념 다이어그램](../mfc/media/vc374v1.gif "바인딩된 컨트롤을&#45;데이터 개념 다이어그램") <br/>
데이터 바인딩 된 컨트롤의 개념 다이어그램

클래스는 `COleControl` 데이터 바인딩을 쉽게 구현할 수 있도록 하는 두 개의 멤버 함수를 제공합니다. 첫 번째 함수인 [BoundPropertyRequestEdit는](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit)속성 값을 변경할 수 있는 권한을 요청하는 데 사용됩니다. [BoundPropertyChanged](../mfc/reference/colecontrol-class.md#boundpropertychanged)- 두 번째 함수는 속성 값이 성공적으로 변경된 후 호출됩니다.

이 문서는 다음 항목을 설명합니다.

- [바인딩가능한 스톡 속성 만들기](#vchowcreatingbindablestockproperty)

- [바인딩 가능한 Get/Set 메서드 만들기](#vchowcreatingbindablegetsetmethod)

## <a name="creating-a-bindable-stock-property"></a><a name="vchowcreatingbindablestockproperty"></a>바인딩가능한 스톡 속성 만들기

[바인딩 가능한 get/set 메서드를](#vchowcreatingbindablegetsetmethod)원할 가능성이 높지만 데이터 바인딩된 stock 속성을 만들 수 있습니다.

> [!NOTE]
> 스톡 속성에는 `bindable` `requestedit` 기본적으로 및 속성이 있습니다.

#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용하여 바인딩할 수 있는 스톡 속성을 추가하려면

1. [MFC ActiveX 컨트롤 마법사를](../mfc/reference/mfc-activex-control-wizard.md)사용하여 프로젝트를 시작합니다.

1. 컨트롤의 인터페이스 노드를 마우스 오른쪽 단추로 클릭합니다.

   그러면 바로 가기 메뉴가 열립니다.

1. 바로 가기 메뉴에서 **속성 추가를** 클릭한 다음 **속성 추가를**클릭합니다.

1. **속성 이름** 드롭다운 목록에서 항목 중 하나를 선택합니다. 예를 들어 **텍스트**를 선택할 수 있습니다.

   **Text는** 스톡 속성이므로 **바인딩가능하고** **requestedit** 특성이 이미 확인되었습니다.

1. **IDL 특성** 탭에서 다음 확인란을 선택합니다: **displaybind** 및 **defaultbind** 를 클릭하여 프로젝트의 속성 정의에 특성을 추가합니다. IDL 파일입니다. 이러한 특성을 통해 컨트롤을 사용자에게 표시하고 stock 속성을 기본 바인딩 가능한 속성으로 만듭니다.

이 시점에서 컨트롤은 데이터 원본의 데이터를 표시할 수 있지만 사용자는 데이터 필드를 업데이트할 수 없습니다. 컨트롤이 데이터를 업데이트할 수 있도록 하려면 `OnOcmCommand` [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) 함수를 다음과 같이 표시하도록 변경합니다.

[!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

이제 컨트롤을 등록하는 프로젝트를 빌드할 수 있습니다. 대화 상자에 컨트롤을 삽입하면 데이터 **필드** 및 **데이터 원본** 속성이 추가되고 이제 컨트롤에 표시할 데이터 원본 및 필드를 선택할 수 있습니다.

## <a name="creating-a-bindable-getset-method"></a><a name="vchowcreatingbindablegetsetmethod"></a>바인딩 가능한 Get/Set 메서드 만들기

데이터 바인딩된 get/set 메서드 외에도 [바인딩할 수](#vchowcreatingbindablestockproperty)있는 stock 속성을 만들 수도 있습니다.

> [!NOTE]
> 이 절차에서는 Windows 컨트롤을 하위 클래스로 하는 ActiveX 컨트롤 프로젝트가 있다고 가정합니다.

#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>속성 추가 마법사를 사용하여 바인딩할 수 있는 get/set 메서드를 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 설정 **제어** 페이지에서 하위 클래스에 대한 컨트롤의 창 클래스를 선택합니다. 예를 들어 편집 컨트롤을 하위 클래스로 지정할 수 있습니다.

1. 컨트롤의 프로젝트를 로드합니다.

1. 컨트롤의 인터페이스 노드를 마우스 오른쪽 단추로 클릭합니다.

   그러면 바로 가기 메뉴가 열립니다.

1. 바로 가기 메뉴에서 **속성 추가를** 클릭한 다음 **속성 추가를**클릭합니다.

1. 속성 이름 상자에 **속성** 이름을 입력합니다. 이 `MyProp` 예제에 사용합니다.

1. **속성 유형** 드롭다운 목록 상자에서 데이터 유형을 선택합니다. 이 예제에서 **short를** 사용합니다.

1. **구현 형식**에서 **Get/Set 메서드**를 클릭합니다.

1. IDL 특성 탭에서 다음 확인란을 선택합니다: **바인딩 가능,** **requestedit,** **displaybind**및 **defaultbind** 를 클릭하여 프로젝트의 속성 정의에 특성을 추가합니다. IDL 파일입니다. 이러한 특성을 통해 컨트롤을 사용자에게 표시하고 stock 속성을 기본 바인딩 가능한 속성으로 만듭니다.

1. **Finish**를 클릭합니다.

1. 함수본문을 `SetMyProp` 수정하여 다음 코드를 포함합니다.

   [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]

1. `BoundPropertyChanged` 및 `BoundPropertyRequestEdit` 함수에 전달되는 매개 변수는 속성의 디스피드이며, 매개 변수는 에서 속성에 대한 id() 특성에 전달됩니다. IDL 파일입니다.

1. [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) 함수를 수정하여 다음 코드를 포함합니다.

   [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

1. `OnDraw` 다음 코드를 포함되도록 함수를 수정합니다.

   [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]

1. 헤더의 공용 섹션에 컨트롤 클래스에 대한 헤더 파일을 파일로 지정하려면 멤버 변수에 대해 다음 정의(생성자)를 추가합니다.

   [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]

1. 다음 줄을 함수의 마지막 `DoPropExchange` 줄로 만듭니다.

   [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]

1. `OnResetState` 다음 코드를 포함되도록 함수를 수정합니다.

   [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]

1. `GetMyProp` 다음 코드를 포함되도록 함수를 수정합니다.

   [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]

이제 컨트롤을 등록하는 프로젝트를 빌드할 수 있습니다. 대화 상자에 컨트롤을 삽입하면 데이터 **필드** 및 **데이터 원본** 속성이 추가되고 이제 컨트롤에 표시할 데이터 원본 및 필드를 선택할 수 있습니다.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
