---
title: C++ 콘솔 앱 프로젝트 만들기
description: 비주얼 스튜디오에서 Microsoft C++를 사용하여 Hello World 콘솔 앱을 만듭니다.
ms.custom: mvc
ms.date: 04/20/2020
ms.topic: tutorial
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 07e88da9a8a3712e1d37e319c29fd25aebce8ea7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749304"
---
# <a name="create-a-c-console-app-project"></a>C++ 콘솔 앱 프로젝트 만들기

C++ 프로그래머의 일반적인 시작점은 명령줄에서 실행되는 "Hello, world!" 애플리케이션입니다. 이것이 이 단계에서 Visual Studio에서 만드는 것입니다.

## <a name="prerequisites"></a>사전 요구 사항

- 컴퓨터에서 설치되고 실행 중인 C++ 워크로드를 사용하여 데스크톱 개발을 위해 Visual Studio를 설치합니다. 아직 설치되지 않은 경우 [Visual Studio에서 C++ 지원 설치](vscpp-step-0-installation.md)를 참조하세요.

## <a name="create-your-app-project"></a>앱 프로젝트 만들기

Visual Studio는 *프로젝트*를 사용하여 앱에 대한 코드를 구성하고 *솔루션*을 사용하여 프로젝트를 구성합니다. 프로젝트에는 앱을 빌드하는 데 사용되는 모든 옵션, 구성 및 규칙이 포함됩니다. 그것은 모든 프로젝트의 파일과 외부 파일 사이의 관계를 관리합니다. 앱을 만들려면 먼저 새 프로젝트 및 솔루션을 만듭니다.

::: moniker range=">=vs-2019"

1. Visual Studio에서 **파일** 메뉴를 열고 **새 > 프로젝트를** 선택하여 새 프로젝트 만들기 대화 상자를 **엽니다.** **C++**, **Windows**및 **콘솔** 태그가 있는 **콘솔 앱** 템플릿을 **선택한**다음 다음 을 선택합니다.

   ![새 프로젝트 만들기](media/vs2019-choose-console-app.png "새 프로젝트 만들기 대화 상자 열기")

1. 새 **프로젝트 구성** 대화 상자에서 **프로젝트 이름** 편집 상자에 *HelloWorld를* 입력합니다. 프로젝트를 작성하려면 **만들기를** 선택합니다.

   ![새 프로젝트의 이름 지정 및 작성](media/vs2019-configure-new-project-hello-world.png "새 프로젝트의 이름 지정 및 작성")

   Visual Studio에서 새 프로젝트를 만듭니다. 소스 코드를 추가하고 편집할 준비가 되었습니다. 기본적으로 콘솔 앱 템플릿은 소스 코드를 "Hello World" 앱으로 채웁니다.

   ![IDE의 헬로 월드 프로젝트](media/vs2019-hello-world-code.png "IDE의 헬로 월드 프로젝트")

   편집기에서 코드가 다음과 같으면 다음 단계로 이동하여 앱을 빌드할 준비가 된 것입니다.

[문제가 발생했습니다.](#create-your-app-project-issues)

::: moniker-end

::: moniker range="<=vs-2017"

1. Visual Studio에서 **파일** 메뉴를 열고 **새 > 프로젝트를** 선택하여 새 프로젝트 대화 상자를 **엽니다.**

   ![새 프로젝트 대화 상자 열기](media/vscpp-file-new-project.gif "새 프로젝트 대화 상자 열기")

1. 새 **프로젝트** 대화 상자에서 **설치> Visual C++를** 선택한 다음 **빈 프로젝트** 템플릿을 선택합니다. **이름** 필드에 *HelloWorld를*입력합니다. 프로젝트를 만들려면 **확인을** 선택합니다.

   ![새 프로젝트의 이름 지정 및 작성](media/vscpp-concierge-project-name-callouts.png "새 프로젝트의 이름 지정 및 작성")

Visual Studio는 빈 새 프로젝트를 만듭니다. 만들려는 앱의 종류를 전문으로 하고 소스 코드 파일을 추가할 준비가 되었습니다. 이 작업은 다음에 수행합니다.

[문제가 발생했습니다.](#create-your-app-project-issues)

## <a name="make-your-project-a-console-app"></a>프로젝트를 콘솔 앱으로 만들기

Visual Studio는 Windows 및 기타 플랫폼에 대한 모든 종류의 앱과 구성 요소를 만들 수 있습니다. **빈 프로젝트** 템플릿은 만드는 앱의 종류에 대해 구체적이지 않습니다. *콘솔 앱은* 콘솔 또는 명령 프롬프트 창에서 실행되는 앱입니다. 하나를 만들려면 Visual Studio에 콘솔 하위 시스템을 사용하도록 앱을 빌드하도록 지시해야 합니다.

1. Visual Studio에서 **프로젝트** 메뉴를 열고 **속성을** 선택하여 **HelloWorld 속성 페이지** 대화 상자를 엽니다.

1. 속성 **페이지** 대화 상자에서 **링커 > 시스템에 > 구성 속성을**선택한 다음 **하위 시스템** 속성 옆에 있는 편집 상자를 선택합니다. 표시되는 드롭다운 메뉴에서 **콘솔(/SUBSYSTEM:CONSOLE)을**선택합니다. **확인**을 선택하여 변경 내용을 저장합니다.

   ![속성 페이지 대화 상자 열기](media/vscpp-properties-linker-subsystem.gif "속성 페이지 대화 상자 열기")

이제 Visual Studio는 콘솔 창에서 실행할 프로젝트를 빌드하는 방법을 알고 있습니다. 다음으로 소스 코드 파일을 추가하고 앱의 코드를 입력합니다.

[문제가 발생했습니다.](#make-your-project-a-console-app-issues)

## <a name="add-a-source-code-file"></a>소스 코드 파일 추가

1. **솔루션 탐색기에서**HelloWorld 프로젝트를 선택합니다. 메뉴 모음에서 **프로젝트**, **새 항목 추가를** 선택하여 새 항목 추가 대화 상자를 **엽니다.**

1. 새 **항목 추가** 대화 상자에서 아직 선택되지 않은 경우 **설치 중인** **시각적 C++를** 선택합니다. 가운데 창에서 **C++ 파일(.cpp)을**선택합니다. **이름을** *HelloWorld.cpp로*변경합니다. **추가를** 선택하여 대화 상자를 닫고 파일을 만듭니다.

   ![HelloWorld.cpp에 대한 소스 파일 추가](media/vscpp-add-new-item.gif "HelloWorld.cpp에 대한 소스 파일 추가")

Visual studio는 빈 새 소스 코드 파일을 만들고 소스 코드를 입력할 준비가 된 편집기 창에서 엽니다.

[문제가 발생했습니다.](#add-a-source-code-file-issues)

## <a name="add-code-to-the-source-file"></a>소스 파일에 코드 추가

1. 이 코드를 HelloWorld.cpp 편집기 창에 복사합니다.

   ```cpp
   #include <iostream>

   int main()
   {
       std::cout << "Hello, world!" << std::endl;
       return 0;
   }
   ```

   코드는 편집기 창에서 다음과 같아야 합니다.

   ![편집기에서 안녕하세요 세계 코드](media/vscpp-hello-world-editor.png "편집기에서 안녕하세요 세계 코드")

편집기에서 코드가 다음과 같으면 다음 단계로 이동하여 앱을 빌드할 준비가 된 것입니다.

[문제가 발생했습니다.](#add-a-source-code-file-issues)

::: moniker-end

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [C++ 프로젝트 빌드 및 실행](vscpp-step-2-build.md)

## <a name="troubleshooting-guide"></a>문제 해결 가이드

첫 번째 C++ 프로젝트를 만들 때 일반적인 문제에 대한 해결책을 보려면 여기를 오십시오.

### <a name="create-your-app-project-issues"></a>앱 프로젝트 만들기: 문제

::: moniker range="vs-2019"

**새 프로젝트** 대화 상자에는 **C++**, **Windows**및 콘솔 태그가 있는 **콘솔** **앱** 템플릿이 표시되어야 합니다. 표시되지 않으면 두 가지 가능한 원인이 있습니다. 목록에서 필터링되거나 설치되지 않을 수 있습니다. 먼저 템플릿 목록 맨 위에 있는 필터 드롭다운을 확인합니다. **C ++**, **윈도우**및 **콘솔로**설정합니다. C++ **콘솔 앱** 템플릿이 나타납니다. 그렇지 않으면 **C++** 워크로드가 있는 데스크톱 개발이 설치되지 않습니다.

**C++를 사용하여 데스크톱 개발을**설치하려면 **새 프로젝트** 대화 상자에서 설치 관리자를 바로 실행할 수 있습니다. 템플릿 목록 하단에 있는 추가 도구 및 기능 링크를 **설치하여** 설치 프로그램을 시작합니다. 사용자 **계정 제어** 대화 상자에서 권한을 요청하는 경우 **예**를 선택합니다. 설치 관리자에서 **C++** 워크로드가 있는 데스크톱 개발이 확인되었는지 확인합니다. 그런 다음 **수정을** 선택하여 Visual Studio 설치를 업데이트합니다.

이름이 같은 다른 프로젝트가 이미 있는 경우 프로젝트의 다른 이름을 선택합니다. 또는 기존 프로젝트를 삭제하고 다시 시도하십시오. 기존 프로젝트를 삭제하려면 파일 탐색기에서 *솔루션 폴더(helloworld.sln* 파일이 포함된 폴더)를 삭제합니다.

[다시 이동합니다.](#create-your-app-project)

::: moniker-end

::: moniker range="vs-2017"

새 **프로젝트** 대화 상자에 **설치**된 아래 **Visual C ++** 항목이 표시 되지 않는 경우 Visual Studio의 복사본에는 C ++ 워크로드가 설치된 **데스크톱 개발이** 없을 수 있습니다. **새 프로젝트** 대화 상자에서 설치 관리자를 바로 실행할 수 있습니다. 개방형 **시각적 스튜디오 설치 관리자** 링크를 선택하여 설치 프로그램을 다시 시작합니다. 사용자 **계정 제어** 대화 상자에서 권한을 요청하는 경우 **예**를 선택합니다. 필요한 경우 설치 관리자를 업데이트합니다. 설치 관리자에서 **C++** 워크로드가 있는 데스크톱 개발이 선택되었는지 확인하고 Visual Studio 설치를 업데이트하려면 **확인을** 선택합니다.

::: moniker-end

::: moniker range="<=vs-2017"

이름이 같은 다른 프로젝트가 이미 있는 경우 프로젝트의 다른 이름을 선택합니다. 또는 기존 프로젝트를 삭제하고 다시 시도하십시오. 기존 프로젝트를 삭제하려면 파일 탐색기에서 *솔루션 폴더(helloworld.sln* 파일이 포함된 폴더)를 삭제합니다.

[다시 이동합니다.](#create-your-app-project)

### <a name="make-your-project-a-console-app-issues"></a>프로젝트를 콘솔 앱으로 만들기: 문제

**구성 속성**아래에 **링커가** 표시되지 않으면 **속성 페이지** 대화 상자를 닫을 수 **있도록 취소를** 선택합니다. 다시 시도하기 전에 **솔루션 탐색기에서** **HelloWorld** 프로젝트를 선택해야 합니다. **솔루션 탐색기에서** **HelloWorld** 솔루션 또는 다른 항목을 선택하지 마십시오.

속성을 선택할 때까지 하위 **시스템** 속성 편집 상자에 드롭다운 컨트롤이 나타나지 않습니다. 편집 상자를 클릭하여 선택합니다. 또는 **탭을** 눌러 **하위 시스템이** 강조 표시될 때까지 대화 상자 컨트롤을 순환할 수 있습니다. 드롭다운 컨트롤을 선택하거나 **Alt+Down을** 눌러 엽니다.

[돌아 가](#make-your-project-a-console-app)

### <a name="add-a-source-code-file-issues"></a>소스 코드 파일 추가: 문제

소스 코드 파일에 다른 이름을 지정하면 괜찮습니다. 그러나 프로젝트에 동일한 코드가 포함된 파일을 두 개 이상 추가하지 마십시오.

헤더 파일과 같이 프로젝트에 잘못된 파일 형식을 추가한 경우 삭제하고 다시 시도하십시오. 파일을 삭제하려면 **솔루션 탐색기**에서 파일을 선택합니다. 그런 다음 **삭제** 키를 누릅니다.

[다시 이동합니다.](#add-a-source-code-file)

### <a name="add-code-to-the-source-file-issues"></a>소스 파일에 코드 추가: 문제

실수로 소스 코드 파일 편집기 창을 닫은 경우 쉽게 다시 열 수 있습니다. 열려면 **솔루션 탐색기** 창에서 HelloWorld.cpp를 두 번 클릭합니다.

소스 코드 편집기의 빨간색 물결선이 아래에 나타나는 경우 코드가 맞춤법, 구두점 및 대/소문자 에서 예제와 일치하는지 확인합니다. 케이스는 C++ 코드에서 중요합니다.

[다시 이동합니다.](#add-code-to-the-source-file)

::: moniker-end

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
