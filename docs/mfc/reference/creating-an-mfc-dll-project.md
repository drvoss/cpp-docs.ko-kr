---
title: MFC DLL 프로젝트 만들기
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.mfcdll.project
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
ms.openlocfilehash: 6367b2a4b85b2c586c5a4420a8be1f80d334b2e4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363956"
---
# <a name="creating-an-mfc-dll-project"></a>MFC DLL 프로젝트 만들기

MFC DLL은 여러 응용 프로그램에서 동시에 사용할 수 있는 함수의 공유 라이브러리 역할을 하는 이진 파일입니다. MFC DLL 프로젝트를 만드는 가장 쉬운 방법은 MFC DLL 마법사를 사용하는 것입니다.

> [!NOTE]
> IDE의 기능 모양은 활성 설정 또는 버전에 따라 달라질 수 있으며 도움말에 설명된 기능과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [시각적 스튜디오 IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하십시오.

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>MFC DLL 마법사를 사용하여 MFC DLL 프로젝트를 만들려면

1. 도움말 항목의 지침을 [따르십시오 MFC 응용 프로그램 만들기하지만](creating-an-mfc-application.md) 사용 가능한 템플릿 목록에서 **MFC 동적 링크 라이브러리** 또는 **MFC DLL을** 선택합니다.

1. [MFC DLL 마법사의](../../mfc/reference/mfc-dll-wizard.md)응용 프로그램 설정 페이지를 사용하여 [응용 프로그램 설정을](../../mfc/reference/application-settings-mfc-dll-wizard.md) 정의합니다.

    > [!NOTE]
    >  마법사의 기본 설정을 그대로 유지하려면 이 단계를 건너 뜁니다.

1. **완료를** 클릭하여 마법사를 닫고 **솔루션 탐색기에서**새 프로젝트를 엽니다.

프로젝트를 만든 후 **솔루션 탐색기**에서 프로젝트 관련 파일을 볼 수 있습니다. 마법사에서 프로젝트용으로 만드는 파일에 대한 자세한 내용은 프로젝트 생성 파일인 ReadMe.txt를 참조하세요. 파일 형식에 대한 자세한 내용은 [Visual Studio C++ 프로젝트용으로 만들어지는 파일 형식](../../build/reference/file-types-created-for-visual-cpp-projects.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[Visual Studio의 C++ 프로젝트 형식](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[코드 마법사에서 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[속성 페이지](../../build/reference/property-pages-visual-cpp.md)
