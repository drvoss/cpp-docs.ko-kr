---
title: C++ 콘솔 앱 프로젝트 빌드 및 실행
description: 비주얼 C++에서 Hello World 콘솔 앱 빌드 및 실행
ms.custom: mvc
ms.date: 04/20/2020
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
ms.openlocfilehash: d1e92e598b370312730a7c4e208b935a264010bf
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749248"
---
# <a name="build-and-run-a-c-console-app-project"></a>C++ 콘솔 앱 프로젝트 빌드 및 실행

C++ 콘솔 앱 프로젝트를 만들고 코드를 입력했습니다. 이제 Visual Studio 내에서 빌드하고 실행할 수 있습니다. 그런 다음 명령줄에서 독립 실행형 앱으로 실행합니다.

## <a name="prerequisites"></a>사전 요구 사항

- 컴퓨터에서 설치되고 실행 중인 C++ 워크로드를 사용하여 데스크톱 개발을 위해 Visual Studio를 설치합니다. 아직 설치되지 않은 경우 [Visual Studio에서 C++ 설치 지원의](vscpp-step-0-installation.md)단계를 따릅니다.

- "안녕하세요, 세상!" 소스 코드를 입력합니다. 아직 이 단계를 수행하지 않은 경우 [C++ 콘솔 앱 프로젝트 만들기의](vscpp-step-1-create.md)단계를 따릅니다.

Visual Studio가 다음과 같으면 앱을 빌드하고 실행할 준비가 된 것입니다.

   ![새 프로젝트를 빌드할 준비가 되었습니다.](media/vscpp-ready-to-build.png "새 프로젝트를 빌드할 준비가 되었습니다.")

## <a name="build-and-run-your-code-in-visual-studio"></a>비주얼 스튜디오에서 코드 빌드 및 실행

1. 프로젝트를 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다. **출력** 창은 빌드 프로세스의 결과를 보여줍니다.

   ![프로젝트 빌드](media/vscpp-build-solution.gif "프로젝트 빌드")

1. 코드를 실행하려면 메뉴 모음에서 **디버그**, **디버깅하지 않고 시작**을 선택합니다.

   ![프로젝트 시작](media/vscpp-start-without-debugging.gif "프로젝트 시작")

   콘솔 창이 열린 다음, 앱을 실행합니다. Visual Studio에서 콘솔 앱을 시작하면 코드를 실행한 다음, "계속하려면 아무 키나 누르세요. . ." 출력을 볼 수 있도록 합니다.

축하합니다! Visual Studio에서 첫 번째 "Hello, world!" 콘솔 앱을 만들었습니다. 키를 눌러서 콘솔 창을 닫고 Visual Studio로 돌아갑니다.

[문제가 발생했습니다.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>명령 창에서 코드 실행

일반적으로 Visual Studio가 아닌 명령 프롬프트에서 콘솔 앱을 실행합니다. 앱이 Visual Studio에 의해 빌드되면 모든 명령 창에서 앱을 실행할 수 있습니다. 명령 프롬프트 창에서 새 앱을 찾고 실행하는 방법은 다음과 같습니다.

1. **솔루션 탐색기에서**HelloWorld 솔루션(HelloWorld 프로젝트가 아님)을 선택하고 마우스 오른쪽 단추를 클릭하여 컨텍스트 메뉴를 엽니다. HelloWorld 솔루션 폴더에서 **파일 탐색기** 창을 열려면 **파일 탐색기에서 폴더 열기를** 선택합니다.

1. 파일 **탐색기** 창에서 디버그 폴더를 엽니다. 이 폴더에는 앱, *HelloWorld.exe*및 기타 디버깅 파일 이 포함되어 있습니다. **Shift** 키를 길게 누를 때 *HelloWorld.exe를* 마우스 오른쪽 단추로 클릭하여 컨텍스트 메뉴를 엽니다. **경로로 복사를** 선택하여 앱의 경로를 클립보드에 복사합니다.

1. 명령 프롬프트 창을 열려면 **Windows+R을** 눌러 **실행** 대화 상자를 엽니다. **열기** 텍스트 상자에 *cmd.exe를* 입력한 다음 **확인을** 선택하여 명령 프롬프트 창을 실행합니다.

1. 명령 프롬프트 창에서 마우스 오른쪽 단추로 클릭하여 앱에 대한 경로를 명령 프롬프트에 붙여넣습니다. Enter를 눌러 앱을 실행합니다.

   ![명령 프롬프트에서 앱 실행](media/vscpp-run-in-cmd.gif "명령 프롬프트에서 앱 실행")

축하합니다, 당신은 구축하고 Visual Studio에서 콘솔 응용 프로그램을 실행했습니다!

[문제가 발생했습니다.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>다음 단계

이 간단한 앱을 빌드하고 실행하면 더 복잡한 프로젝트를 수행할 준비가 된 것입니다. 자세한 내용은 [C++ 데스크톱 개발에 대한 Visual Studio IDE 사용을](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)참조하십시오. 비주얼 스튜디오에서 Microsoft C++의 기능을 자세히 살펴볼 수 있는 자세한 연습이 있습니다.

## <a name="troubleshooting-guide"></a>문제 해결 가이드

첫 번째 C++ 프로젝트를 만들 때 일반적인 문제에 대한 해결책을 보려면 여기를 오십시오.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Visual Studio에서 코드 빌드 및 실행: 문제

소스 코드 편집기의 빨간색 물결선이 아래에 나타나면 빌드에 오류 또는 경고가 있을 수 있습니다. 코드가 맞춤법, 구두점 및 대/소문자에서 예제와 일치하는지 확인합니다.

[돌아 가.](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>명령 창에서 코드 실행: 문제

파일 탐색기에서 표시된 경로가 * \\HelloWorld\\HelloWorld에서*끝나면 HelloWorld *솔루션*대신 HelloWorld *프로젝트를* 열었습니다. 앱을 포함하지 않는 디버그 폴더로 인해 혼동될 수 있습니다. 파일 탐색기의 레벨을 탐색하여 경로의 첫 번째 *HelloWorld인* 솔루션 폴더로 이동합니다. 이 폴더에는 디버그 폴더도 포함되어 있으며 앱도 찾을 수 있습니다.

명령줄에서 솔루션 디버그 폴더로 이동하여 앱을 실행할 수도 있습니다. 앱에 대한 경로를 지정하지 않으면 앱이 다른 디렉터리에서 실행되지 않습니다. 그러나 앱을 다른 디렉터리로 복사하여 거기에서 실행할 수 있습니다. PATH 환경 변수가 지정한 디렉터리로 복사한 다음 어디서나 실행할 수도 있습니다.

바로 가기 메뉴에서 **복사를 경로로** 표시하지 않으면 메뉴를 닫은 다음 **Shift** 키를 다시 열 때 길게 누른다. 이 명령은 편의를 위해서입니다. 파일 탐색기 검색 모음에서 폴더에 대한 경로를 복사하여 **실행** 대화 상자에 붙여넣은 다음 끝에 실행 파일의 이름을 입력할 수도 있습니다. 그것은 단지 조금 더 입력, 하지만 그것은 동일한 결과.

[돌아 가.](#run-your-code-in-a-command-window)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
