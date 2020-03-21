---
title: ATL 속성 페이지 추가
ms.date: 05/09/2019
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
ms.openlocfilehash: 3e27d276e5500c1e32ca7b576b355f14f18a47f6
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075268"
---
# <a name="adding-an-atl-property-page"></a>ATL 속성 페이지 추가

> [!NOTE]
> Visual Studio 2019 이상에서는 ATL 속성 페이지 마법사를 사용할 수 없습니다.

ATL(액티브 템플릿 라이브러리) 속성 페이지를 프로젝트에 추가하려면 프로젝트가 ATL 애플리케이션 또는 ATL 지원이 포함된 MFC 애플리케이션으로 만든 것이어야 합니다. [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)를 사용하여 ATL 애플리케이션을 만들거나, [MFC 애플리케이션에 ATL 개체를 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)하여 MFC 애플리케이션에 대한 ATL 지원을 구현할 수 있습니다.

컨트롤의 속성 페이지를 추가하는 경우 컨트롤에서 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) 인터페이스를 지원해야 합니다. 기본적으로, 이 인터페이스는 [ATL 컨트롤 마법사](../../atl/reference/adding-an-atl-control.md)를 사용하여 [ATL 컨트롤을 만들](../../atl/reference/atl-control-wizard.md) 때 컨트롤 클래스의 파생 목록에 있습니다.

> [!NOTE]
> 컨트롤 클래스의 파생 목록에 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)이 없으면 수동으로 추가해야 합니다.

## <a name="to-add-an-atl-property-page-to-your-project"></a>프로젝트에 ATL 속성 페이지를 추가하려면 다음을 수행합니다.

1. **솔루션 탐색기** 또는 [클래스 뷰](/visualstudio/ide/viewing-the-structure-of-code)에서 ATL 속성 페이지를 추가할 프로젝트의 이름을 마우스 오른쪽 단추로 클릭합니다.

1. 바로 가기 메뉴에서 **추가**를 클릭한 다음, **클래스 추가**를 클릭합니다.

1. [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자의 **템플릿** 창에서 **ATL 속성 페이지**를 클릭한 다음, **열기**를 클릭하여 [ATL 속성 페이지 마법사](../../atl/reference/atl-property-page-wizard.md)를 표시합니다.

컨트롤의 속성 페이지를 만든 후에 컨트롤의 속성 맵에 [PROP_PAGE](property-map-macros.md#prop_page) 항목을 제공해야 합니다.

## <a name="see-also"></a>참고 항목

[속성 페이지](../../atl/atl-com-property-pages.md)<br/>
[ATL COM 개체 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[예: 속성 페이지 구현](../../atl/example-implementing-a-property-page.md)
