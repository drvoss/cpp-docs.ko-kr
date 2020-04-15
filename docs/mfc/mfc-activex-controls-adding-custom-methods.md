---
title: 'MFC ActiveX 컨트롤: 사용자 지정 메서드 추가'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
ms.openlocfilehash: 88d486248eab5d980463764db34bf40b05b830dc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364708"
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC ActiveX 컨트롤: 사용자 지정 메서드 추가

사용자 지정 메서드는 에 의해 `COleControl`아직 구현되지 않았다는 점에서 stock 메서드와 다릅니다. 컨트롤에 추가하는 각 사용자 지정 메서드에 대한 구현을 제공해야 합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

ActiveX 컨트롤 사용자는 언제든지 사용자 지정 메서드를 호출하여 제어 관련 작업을 수행할 수 있습니다. 사용자 지정 메서드에 대한 디스패치 맵 항목은 DISP_FUNCTION 양식입니다.

## <a name="adding-a-custom-method-with-the-add-method-wizard"></a><a name="_core_adding_a_custom_method_with_classwizard"></a>메서드 추가 마법사를 사용하여 사용자 지정 메서드 추가

다음 절차에서는 ActiveX 컨트롤의 스켈레톤 코드에 사용자 지정 메서드 PtInCircle을 추가하는 방법을 보여 줍니다. PtInCircle은 컨트롤에 전달된 좌표가 원 내부 또는 외부에 있는지 여부를 결정합니다. 이 동일한 절차를 사용하여 다른 사용자 지정 메서드를 추가할 수도 있습니다. 사용자 지정 메서드 이름과 해당 매개 변수를 PtInCircle 메서드 이름 및 매개 변수로 대체합니다.

> [!NOTE]
> 이 예제에서는 `InCircle` 이벤트 문서의 함수를 사용합니다. 이 함수에 대한 자세한 내용은 [MFC ActiveX 컨트롤: ActiveX 컨트롤에 사용자 지정 이벤트 추가](../mfc/mfc-activex-controls-adding-custom-events.md)문서를 참조하십시오.

#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>메서드 추가 마법사를 사용하여 PtInCircle 사용자 지정 메서드를 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **추가를** 클릭한 다음 **방법 추가**를 클릭합니다.

   그러면 메서드 추가 마법사가 열립니다.

1. 메서드 **이름** 상자에 *PtInCircle*을 입력합니다.

1. 내부 **이름** 상자에 메서드의 내부 함수 이름을 입력하거나 기본값(이 경우 *PtInCircle)을*사용합니다.

1. 반환 **형식** 상자에서 메서드의 반환 형식에 대 한 **VARIANT_BOOL** 클릭 합니다.

1. 매개 **변수 유형** 및 **매개 변수 이름** 컨트롤을 사용하여 *OLE_XPOS_PIXELS* *xCoord(OLE_XPOS_PIXELS* 형식)라는 매개 변수를 추가합니다.

1. 매개 **변수 유형** 및 **매개 변수 이름** 컨트롤을 사용하여 *yCoord(형식* *OLE_YPOS_PIXELS)라는*매개 변수를 추가합니다.

1. **Finish**를 클릭합니다.

## <a name="add-method-wizard-changes-for-custom-methods"></a><a name="_core_classwizard_changes_for_custom_methods"></a>사용자 지정 메서드에 대한 메서드 마법사 변경 내용 추가

사용자 지정 메서드를 추가하면 메서드 추가 마법사에서 컨트롤 클래스 헤더를 일부 변경합니다( H) 및 구현(. CPP) 파일. 다음 줄은 컨트롤 클래스 헤더의 디스패치 맵 선언에 추가됩니다. H) 파일:

[!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]

이 코드는 디스패치 메서드 `PtInCircle`처리기라는 을 선언합니다. 이 함수는 외부 이름을 `PtInCircle`사용하여 컨트롤 사용자가 호출할 수 있습니다.

다음 줄이 컨트롤의 에 추가됩니다. IDL 파일:

[!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]

이 줄은 `PtInCircle` 메서드에 특정 ID 번호, 메서드 마법사 추가 메서드 및 속성 목록에서 메서드의 위치를 할당합니다. 메서드 추가 마법사가 사용자 지정 메서드를 추가하는 데 사용되었기 때문에 이 에 대한 항목이 프로젝트의 에 자동으로 추가되었습니다. IDL 파일입니다.

또한, 다음 줄은, 구현에 위치(. CPP) 컨트롤 클래스의 파일이 컨트롤의 디스패치 맵에 추가됩니다.

[!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]

DISP_FUNCTION `PtInCircle` 매크로는 메서드를 컨트롤의 처리기 `PtInCircle`함수에 매핑하고 반환 형식을 **VARIANT_BOOL**선언하고 **VTS_XPOS_PIXELS** 형식과 **VTS_YPOSPIXELS** 두 매개 `PtInCircle`변수를 로 전달합니다.

마지막으로 메서드 추가 마법사는 컨트롤 `CSampleCtrl::PtInCircle` 구현의 맨 아래에 스텁 함수를 추가합니다. CPP) 파일. 앞서 `PtInCircle` 설명한 대로 작동하려면 다음과 같이 수정해야 합니다.

[!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[클래스 보기 및 개체 브라우저 아이콘](/visualstudio/ide/class-view-and-object-browser-icons)
