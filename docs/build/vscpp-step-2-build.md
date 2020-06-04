---
title: C++ 콘솔 앱 프로젝트 빌드 및 실행
description: Visual C++에서 Hello World 콘솔 앱 빌드 및 실행
ms.custom: mvc
ms.date: 04/20/2020
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
ms.openlocfilehash: d1e92e598b370312730a7c4e208b935a264010bf
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749248"
---
# <a name="build-and-run-a-c-console-app-project"></a>C++ 콘솔 앱 프로젝트 빌드 및 실행

C++ 콘솔 앱 프로젝트를 만들고 코드를 입력했습니다. 이제 Visual Studio에서 빌드하고 실행할 수 있습니다. 그런 다음 명령줄에서 독립 실행형 앱으로 실행합니다.

## <a name="prerequisites"></a>사전 요구 사항

- 컴퓨터에서 설치되고 실행 중인 C++ 워크로드를 사용하여 데스크톱 개발을 위해 Visual Studio를 설치합니다. 아직 설치되지 않은 경우 [Visual Studio에서 C++ 지원 설치](vscpp-step-0-installation.md)의 단계를 따르세요.

- "Hello, World!" 프로젝트를 만들고 소스 코드를 입력합니다. 이 단계를 아직 수행하지 않은 경우 [C++ 콘솔 앱 프로젝트 만들기](vscpp-step-1-create.md)의 단계를 따르세요.

Visual Studio가 다음과 같으면 앱을 빌드하고 실행할 준비가 된 것입니다.

   ![새 프로젝트 빌드 준비 완료](media/vscpp-ready-to-build.png "새 프로젝트 빌드 준비 완료")

## <a name="build-and-run-your-code-in-visual-studio"></a>Visual Studio에서 코드 빌드 및 실행

1. 프로젝트를 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다. **출력** 창은 빌드 프로세스의 결과를 보여줍니다.

   ![프로젝트 빌드](media/vscpp-build-solution.gif "프로젝트 빌드")

1. 코드를 실행하려면 메뉴 모음에서 **디버그**, **디버깅하지 않고 시작**을 선택합니다.

   ![프로젝트 시작](media/vscpp-start-without-debugging.gif "프로젝트 시작")

   콘솔 창이 열린 다음, 앱을 실행합니다. Visual Studio에서 콘솔 앱을 시작하면 코드를 실행한 다음, "계속하려면 아무 키나 누르세요. 을 선택합니다. "를 표시하여 출력을 볼 수 있도록 합니다.

지금까지 Visual Studio에서 첫 번째 "Hello, world!" 콘솔 앱을 만들었습니다. 키를 눌러서 콘솔 창을 닫고 Visual Studio로 돌아갑니다.

[문제가 발생했습니다.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>명령 창에서 코드 실행

일반적으로 Visual Studio가 아닌 명령 프롬프트에서 콘솔 앱을 실행합니다. 앱이 Visual Studio에서 빌드된 후에는 모든 명령 창에서 실행할 수 있습니다. 명령 프롬프트 창에서 새 앱을 찾고 실행하는 방법은 다음과 같습니다.

1. **솔루션 탐색기**에서 HelloWorld 솔루션(HelloWorld 프로젝트가 아님)을 선택하고 마우스 오른쪽 단추를 클릭하여 바로 가기 메뉴를 엽니다. **파일 탐색기에서 폴더 열기**를 선택하여 HelloWorld 솔루션 폴더에서 **파일 탐색기** 창을 엽니다.

1. **파일 탐색기** 창에서 Debug 폴더를 엽니다. 이 폴더에는 앱, *HelloWorld.exe* 및 다른 몇 가지 디버깅 파일이 포함되어 있습니다. **Shift** 키를 누른 상태에서 *HelloWorld.exe*를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다. **경로로 복사**를 선택하여 앱 경로를 클립보드에 복사합니다.

1. 명령 프롬프트 창을 열려면 **Windows + R**을 눌러 **실행** 대화 상자를 엽니다. **열기** 텍스트 상자에 *cmd.exe*를 입력한 다음 **확인**을 선택하여 명령 프롬프트 창을 실행합니다.

1. 명령 프롬프트 창에서 마우스 오른쪽 단추를 클릭하여 앱 경로를 명령 프롬프트에 붙여넣습니다. Enter 키를 눌러 앱을 실행합니다.

   ![명령 프롬프트에서 앱 실행](media/vscpp-run-in-cmd.gif "명령 프롬프트에서 앱 실행")

축하합니다. Visual Studio에서 콘솔 앱을 빌드하고 실행했습니다!

[문제가 발생했습니다.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>다음 단계

이 간단한 앱을 빌드하고 실행했으므로 더 복잡한 프로젝트를 사용할 수 있습니다. 자세한 내용은 [C++ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)을 참조하세요. Visual Studio에서 Microsoft C++의 기능을 탐색하는 자세한 연습이 포함되어 있습니다.

## <a name="troubleshooting-guide"></a>문제 해결 가이드

첫 번째 C++ 프로젝트를 만들 때 발생하는 일반적인 문제에 대한 해결 방법을 제공합니다.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>Visual Studio에서 코드 빌드 및 실행: 문제

소스 코드 편집기의 모든 항목 아래에 빨간색 물결선 표시되면 빌드에 오류 또는 경고가 있을 수 있습니다. 코드가 예제의 철자, 문장 부호 및 대/소문자와 일치하는지 확인합니다.

[돌아가기](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>명령 창에서 코드 실행: 문제

파일 탐색기에 표시된 경로가 *\\HelloWorld\\HelloWorld*로 끝나는 경우 HelloWorld  솔루션 대신 HelloWorld  프로젝트를 연 것입니다. Debug 폴더에 앱이 포함되어 있지 않아 혼란스러울 것입니다. 파일 탐색기에서 한 수준 위로 이동하여 경로에서 첫 번째 솔루션 폴더인 *HelloWorld*를 엽니다. 이 폴더에는 Debug 폴더도 포함되어 있으며, 여기에서 앱을 찾을 수 있습니다.

명령줄에서 솔루션 Debug 폴더로 이동하여 앱을 실행할 수도 있습니다. 앱 경로를 지정하지 않으면 다른 디렉터리에서 앱이 실행되지 않습니다. 그러나 앱을 다른 디렉터리에 복사하고 여기에서 실행할 수 있습니다. 앱을 PATH 환경 변수로 지정된 디렉터리에 복사한 다음 어디서나 실행할 수도 있습니다.

바로 가기 메뉴에서 **경로로 복사**가 표시되지 않으면 메뉴를 닫은 다음 **Shift** 키를 누른 상태에서 다시 엽니다. 이 명령은 편의를 위해서만 사용할 수 있습니다. 파일 탐색기 검색 창에서 폴더 경로를 복사하여 **실행** 대화 상자에 붙여넣고 끝에 실행 파일의 이름을 입력할 수도 있습니다. 입력이 약간 더 많지만 결과는 동일합니다.

[돌아가기](#run-your-code-in-a-command-window)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
