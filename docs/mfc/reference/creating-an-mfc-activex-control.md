---
title: MFC ActiveX 컨트롤 만들기
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.activex.project
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
ms.openlocfilehash: 5e0a81d6a01632bcfadccd241f3a485e6d332627
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077453"
---
# <a name="creating-an-mfc-activex-control"></a>MFC ActiveX 컨트롤 만들기

ActiveX 컨트롤 프로그램은 부모 응용 프로그램에 특정 유형의 기능을 제공 하도록 설계 된 모듈식 프로그램입니다. 예를 들어 대화 상자에서 사용할 단추 또는 웹 페이지에서 사용할 도구 모음 등의 컨트롤을 만들 수 있습니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 하지 않아야 하는 레거시 기술입니다. 자세한 내용은 [ActiveX Controls](../activex-controls.md)을 참조 하세요.

Mfc ActiveX 컨트롤을 만드는 가장 쉬운 방법은 [Mfc Activex 컨트롤 마법사](../../mfc/reference/mfc-activex-control-wizard.md)를 사용 하는 것입니다.

### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>MFC ActiveX 컨트롤 마법사를 사용 하 여 MFC ActiveX 컨트롤을 만들려면

1. 도움말 항목의 [Mfc 응용 프로그램 만들기](creating-an-mfc-application.md) 에 설명 된 지침을 따르고 사용 가능한 템플릿 목록에서 **mfc ActiveX 컨트롤** 을 선택 합니다.

1. MFC ActiveX 컨트롤 마법사를 사용 하 여 [응용 프로그램 설정](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [컨트롤 이름](../../mfc/reference/control-names-mfc-activex-control-wizard.md)및 [컨트롤 설정을](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) 정의 합니다.

    > [!NOTE]
    >  마법사의 기본 설정을 그대로 유지하려면 이 단계를 건너 뜁니다.

1. **마침**을 클릭하여 마법사를 닫고 새 프로젝트를 개발 환경에서 엽니다.

프로젝트를 만든 후 **솔루션 탐색기**에서 생성 된 파일을 볼 수 있습니다. 마법사에서 프로젝트용으로 만드는 파일에 대한 자세한 내용은 프로젝트 생성 파일인 ReadMe.txt를 참조하세요. 파일 형식에 대한 자세한 내용은 [Visual Studio C++ 프로젝트용으로 만들어지는 파일 형식](../../build/reference/file-types-created-for-visual-cpp-projects.md)을 참조하세요.

프로젝트를 만든 후에는 코드 마법사를 사용 하 여 [함수](../../ide/add-member-function-wizard.md), [변수](../../ide/add-member-variable-wizard.md), [이벤트](../../ide/add-event-wizard.md), [속성](../../ide/names-add-property-wizard.md)및 [메서드](../../ide/add-method-wizard.md)를 추가할 수 있습니다. ActiveX 컨트롤을 사용자 지정 하는 방법에 대 한 자세한 내용은 [MFC Activex 컨트롤](../../mfc/mfc-activex-controls.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[속성 페이지](../../build/reference/property-pages-visual-cpp.md)
