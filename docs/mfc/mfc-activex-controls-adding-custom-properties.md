---
title: 'MFC ActiveX 컨트롤: 사용자 지정 속성 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
ms.openlocfilehash: 00f7a879582bca562ce626fe224206094fd19bc7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364697"
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC ActiveX 컨트롤: 사용자 지정 속성 추가

사용자 지정 속성은 클래스에서 아직 구현되지 않은 `COleControl` 사용자 지정 속성의 스톡 속성과 다릅니다. 사용자 지정 속성은 컨트롤을 사용하여 프로그래머에게 ActiveX 컨트롤의 특정 상태 또는 모양을 노출하는 데 사용됩니다.

이 문서에서는 속성 추가 마법사를 사용하여 ActiveX 컨트롤에 사용자 지정 속성을 추가하는 방법을 설명하고 결과 코드 수정에 대해 설명합니다. 다룰 주제는 다음과 같습니다.

- [속성 추가 마법사를 사용하여 사용자 지정 속성 추가](#_core_using_classwizard_to_add_a_custom_property)

- [사용자 지정 속성에 대한 속성 마법사 변경 내용 추가](#_core_classwizard_changes_for_custom_properties)

사용자 지정 속성은 멤버 변수, 알림이 있는 멤버 변수, 메서드 받기/설정 및 매개 변수화의 네 가지 구현으로 제공됩니다.

- 멤버 변수 구현

   이 구현은 control 클래스의 멤버 변수로 속성의 상태를 나타냅니다. 속성 값이 변경되는 시기를 아는 것이 중요하지 않은 경우 멤버 변수 구현을 사용합니다. 세 가지 유형 중에서 이 구현은 속성에 대한 최소한의 지원 코드를 만듭니다. 멤버 변수 구현을 위한 디스패치 맵 항목 매크로가 [DISP_PROPERTY.](../mfc/reference/dispatch-maps.md#disp_property)

- 알림 구현을 가진 멤버 변수

   이 구현은 멤버 변수와 속성 추가 마법사에서 만든 알림 함수로 구성됩니다. 속성 값이 변경된 후 알림 함수는 프레임워크에서 자동으로 호출됩니다. 속성 값이 변경된 후 알림을 받아야 하는 경우 알림 구현과 함께 멤버 변수를 사용합니다. 이 구현에는 함수 호출이 필요하기 때문에 더 많은 시간이 필요합니다. 이 구현에 대한 디스패치 맵 항목 매크로는 [DISP_PROPERTY_NOTIFY.](../mfc/reference/dispatch-maps.md#disp_property_notify)

- 메서드 받기/설정 구현

   이 구현은 컨트롤 클래스의 멤버 함수 쌍으로 구성됩니다. Get/Set Method 구현은 컨트롤의 사용자가 속성의 현재 값을 요청하고 컨트롤의 사용자가 속성을 변경하도록 요청할 때 멤버 설정 함수를 자동으로 호출합니다. 런타임 동안 속성 값을 계산하거나, 실제 속성을 변경하기 전에 컨트롤의 사용자가 전달한 값의 유효성을 검사하거나, 읽기 또는 쓰기 전용 속성 형식을 구현해야 하는 경우 이 구현을 사용합니다. 이 구현에 대한 디스패치 맵 항목 매크로는 [DISP_PROPERTY_EX.](../mfc/reference/dispatch-maps.md#disp_property_ex) 다음 섹션에서는 [속성 추가 마법사를 사용하여 사용자 지정 속성을 추가하고](#_core_using_classwizard_to_add_a_custom_property)CircleOffset 사용자 지정 속성을 사용하여 이 구현을 보여 줍니다.

- 매개 변수화된 구현

   매개 변수화된 구현은 속성 추가 마법사에서 지원됩니다. 매개 변수화된 속성(속성 배열이라고도 함)을 사용하여 컨트롤의 단일 속성을 통해 값 집합에 액세스할 수 있습니다. 이 구현에 대한 디스패치 맵 항목 매크로는 DISP_PROPERTY_PARAM. 이 형식 구현에 대한 자세한 내용은 ActiveX 컨트롤: 고급 항목 문서에서 [매개 변수화된 속성 구현을](../mfc/mfc-activex-controls-advanced-topics.md) 참조하십시오.

## <a name="using-the-add-property-wizard-to-add-a-custom-property"></a><a name="_core_using_classwizard_to_add_a_custom_property"></a>속성 추가 마법사를 사용하여 사용자 지정 속성 추가

다음 절차에서는 메서드 받기/집합 구현을 사용하는 사용자 지정 속성인 CircleOffset을 추가하는 방법을 보여 줍니다. CircleOffset 사용자 지정 속성을 사용하면 컨트롤의 사용자가 컨트롤의 경계 사각형 의 중심에서 원을 오프셋할 수 있습니다. Get/Set 메서드 이외의 구현으로 사용자 지정 속성을 추가하는 절차는 매우 유사합니다.

이 동일한 절차를 사용하여 원하는 다른 사용자 지정 속성을 추가할 수도 있습니다. 사용자 지정 속성 이름을 CircleOffset 속성 이름 및 매개 변수로 대체합니다.

#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용하여 CircleOffset 사용자 지정 속성을 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **속성 추가를** 클릭한 다음 **속성 추가를**클릭합니다.

   그러면 [속성 추가 마법사가](../ide/names-add-property-wizard.md)열립니다.

1. 속성 **이름** 상자에 *CircleOffset을*입력합니다.

1. **구현 형식**에서 **Get/Set 메서드**를 클릭합니다.

1. 속성 **유형** 상자에서 **짧은**을 선택합니다.

1. 함수 받기 및 설정에 대해 고유한 이름을 입력하거나 기본 이름을 수락합니다.

1. **Finish**를 클릭합니다.

## <a name="add-property-wizard-changes-for-custom-properties"></a><a name="_core_classwizard_changes_for_custom_properties"></a>사용자 지정 속성에 대한 속성 마법사 변경 내용 추가

CircleOffset 사용자 지정 속성을 추가하면 속성 추가 마법사가 헤더를 변경합니다() H) 및 구현(. CPP) 제어 클래스의 파일입니다.

다음 줄이 에 추가됩니다. H 파일은 라는 `GetCircleOffset` 두 `SetCircleOffset`개의 함수를 선언하고 :

[!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]

다음 줄이 컨트롤의 에 추가됩니다. IDL 파일:

[!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]

이 줄은 속성 추가 마법사의 메서드 및 속성 목록에서 메서드의 위치에서 가져온 특정 ID 번호를 CircleOffset 속성에 할당합니다.

또한 다음 줄이 디스패치 맵에 추가됩니다(에서. 컨트롤 클래스의 CPP 파일)을 사용하여 CircleOffset 속성을 컨트롤의 두 처리기 함수에 매핑합니다.

[!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]

마지막으로 `GetCircleOffset` 및 `SetCircleOffset` 함수의 구현이 컨트롤의 끝에 추가됩니다. CPP 파일. 대부분의 경우 속성 값을 반환하도록 Get 함수를 수정합니다. Set 함수에는 일반적으로 속성이 변경되기 전이나 후에 실행되어야 하는 코드가 포함됩니다.

[!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]

속성 추가 마법사는 [SetModifiedFlag](../mfc/reference/colecontrol-class.md#setmodifiedflag), Setfunction 함수의 본문에 호출을 자동으로 추가합니다. 이 함수를 호출하면 컨트롤이 수정된 것으로 표시됩니다. 컨트롤이 수정된 경우 컨테이너가 저장될 때 새 상태가 저장됩니다. 이 함수는 컨트롤의 영구 상태의 일부로 저장된 속성이 값을 변경할 때마다 호출되어야 합니다.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)<br/>
[콜레컨트롤 클래스](../mfc/reference/colecontrol-class.md)
