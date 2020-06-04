---
title: 'MFC ActiveX 컨트롤: 스톡 메서드 추가'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
ms.openlocfilehash: ec59ccc0cbd48fc3114eb2dc0833dd3dd65691de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364679"
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC ActiveX 컨트롤: 스톡 메서드 추가

stock 메서드는 [클래스 COleControl에](../mfc/reference/colecontrol-class.md)의해 이미 구현되어 있다는 점에서 사용자 지정 메서드와 다릅니다. 예를 들어 `COleControl` 컨트롤에 대한 새로 고침 메서드를 지원하는 미리 정의된 멤버 함수가 포함되어 있습니다. 이 스톡 메서드의 디스패치 맵 항목은 DISP_STOCKFUNC_REFRESH.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

`COleControl`두 가지 스톡 방법을 지원합니다: DoClick 및 새로 고침. 컨트롤의 사용자가 컨트롤의 모양을 즉시 업데이트하기 위해 새로 고침을 호출합니다. 컨트롤의 Click 이벤트를 발생시키기 위해 DoClick이 호출됩니다.

|메서드|디스패치 맵 항목|주석|
|------------|------------------------|-------------|
|`DoClick`|**DISP_STOCKPROP_DOCLICK () )**|클릭 이벤트를 발생시면 됩니다.|
|`Refresh`|**DISP_STOCKPROP_REFRESH () )**|컨트롤의 모양을 즉시 업데이트합니다.|

## <a name="adding-a-stock-method-using-the-add-method-wizard"></a><a name="_core_adding_a_stock_method_using_classwizard"></a>메서드 추가 마법사를 사용하여 스톡 메서드 추가

스톡 메서드를 추가하는 것은 [메서드 추가 마법사를](../ide/add-method-wizard.md)사용하여 간단합니다. 다음 절차에서는 MFC ActiveX 컨트롤 마법사를 사용하여 만든 컨트롤에 새로 고침 메서드를 추가하는 방법을 보여 줍니다.

#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>메서드 추가 마법사를 사용하여 스톡 새로 고침 메서드를 추가하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 **추가를** 클릭한 다음 **방법 추가**를 클릭합니다.

   그러면 메서드 추가 마법사가 열립니다.

1. 메서드 **이름** 상자에서 **새로 고침을**클릭합니다.

1. **Finish**를 클릭합니다.

## <a name="add-method-wizard-changes-for-stock-methods"></a><a name="_core_classwizard_changes_for_stock_methods"></a>재고 메소드에 대한 메서드 마법사 변경 내용 추가

stock 새로 고침 메서드는 컨트롤의 기본 클래스에서 지원되므로 **메서드 추가 마법사는** 컨트롤의 클래스 선언을 어떤 식으로든 변경하지 않습니다. 컨트롤의 디스패치 맵과 에 메서드에 대한 항목을 추가합니다. IDL 파일입니다. 다음 줄은 구현에 있는 컨트롤의 디스패치 맵에 추가됩니다. CPP) 파일:

[!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]

이렇게 하면 컨트롤의 사용자가 새로 고침 메서드를 사용할 수 있습니다.

다음 줄이 컨트롤의 에 추가됩니다. IDL 파일:

[!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]

이 줄은 새로 고침 메서드에 특정 ID 번호를 할당합니다.

## <a name="see-also"></a>참고 항목

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
