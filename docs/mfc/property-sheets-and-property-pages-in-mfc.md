---
title: MFC의 속성 시트 및 속성 페이지
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
ms.openlocfilehash: 10fb34c79745e672d30dd2d3c3b97d457583f795
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371178"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC의 속성 시트 및 속성 페이지

탭 대화 상자라고도 하는 속성 시트는 속성 페이지가 포함된 대화 상자입니다. 각 속성 페이지는 대화 상자 템플릿 리소스를 기반으로 하며 컨트롤을 포함합니다. 상단에 탭이 있는 페이지에 동봉되어 있습니다. 탭은 페이지의 이름을 지정하고 그 용도를 나타냅니다. 사용자는 속성 시트의 탭을 클릭하여 컨트롤 집합을 선택합니다.

페이지를 사용하여 속성 시트의 컨트롤을 의미 있는 집합으로 그룹화합니다. 포함된 속성 시트에는 일반적으로 자체 컨트롤이 여러 개 있습니다. 이는 모든 페이지에 적용됩니다.

속성 시트는 클래스 [CPropertySheet를](../mfc/reference/cpropertysheet-class.md)기반으로 합니다. 속성 페이지는 클래스 [CPropertyPage를](../mfc/reference/cpropertypage-class.md)기반으로 합니다.

속성 시트는 뷰의 현재 선택과 같은 일부 외부 개체의 특성을 수정하는 데 일반적으로 사용되는 특별한 종류의 대화 상자입니다. 속성 시트에는 포함된 대화 상자, 한 번에 하나씩 표시되는 하나 이상의 속성 페이지, 사용자가 해당 페이지를 선택하기 위해 클릭하는 각 페이지의 맨 위에 있는 탭의 세 가지 주요 부분이 있습니다. 속성 시트는 변경할 설정 이나 옵션의 여러 유사한 그룹이 있는 경우에 유용 합니다. 속성 시트는 쉽게 이해할 수 있는 방식으로 정보를 그룹화합니다.

> [!NOTE]
> 을 사용하여 `CPropertySheet::DoModal`속성 시트를 표시하려고 할 때 시스템에서 첫 번째 예외를 생성할 수 있습니다. 이 예외는 개체를 생성하기 전에 시스템이 개체의 [창 스타일을](../mfc/reference/styles-used-by-mfc.md#window-styles) 변경하려고 하기 때문에 발생합니다. 이 예외에 대한 자세한 정보 및 이를 방지하거나 처리하는 방법에 대한 자세한 내용은 [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[속성 시트](../mfc/property-sheets-mfc.md)
