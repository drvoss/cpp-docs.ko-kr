---
title: C++ 콘솔 앱 프로젝트 만들기
description: Visual C++에서 Hello World 콘솔 앱 만들기
ms.custom: mvc
ms.date: 04/02/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 739da0b6e5400117c0b09a3d4c3335bd44529a25
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314950"
---
# <a name="create-a-c-console-app-project"></a>C++ 콘솔 앱 프로젝트 만들기

C++ 프로그래머의 가장 전형적인 시작은 명령줄에서 실행되는 "Hello, world!" 애플리케이션 만들기 입니다. 이번 세션을 통해 Visual Studio를 통해서 실습해 보겠습니다.

## <a name="prerequisites"></a>전제 조건

- 컴퓨터에서 설치되고 실행 중인 C++ 워크로드를 사용하여 데스크톱 개발을 위해 Visual Studio를 설치합니다. 아직 설치되지 않은 경우 [Visual Studio에서 C++ 지원 설치](vscpp-step-0-installation.md)를 참조하세요.

## <a name="create-your-app-project"></a>앱 프로젝트 만들기

Visual Studio는 *프로젝트*를 사용하여 앱에 대한 코드를 구성하고 *솔루션*을 사용하여 프로젝트를 구성합니다. 프로젝트는 앱을 빌드하는 데 사용되는 모든 옵션, 구성 및 규칙을 포함하고, 프로젝트의 모든 파일과 외부 파일 간의 관계를 관리합니다. 앱을 만들려면 먼저 새 프로젝트 및 솔루션을 만듭니다.

::: moniker range=">=vs-2019"

1. Visual Studio에서 **파일** 메뉴를 선택하고 **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트**를 만듭니다. 대화 상자를 통해 **콘솔 앱** 템플릿을 선택한 후 **다음**을 클릭 합니다.

   ![새 프로젝트를 만듭니다](media/vs2019-choose-console-app.png "만들기는 새 프로젝트 대화 상자를 열려면")

1. **새 프로젝트 구성** 대화 상자에서 입력 **프로젝트 이름** 편집 상자에  *HelloWorld*를 입력 합니다. **만들기**를 선택하여 프로젝트를 만듭니다.

   ![새 프로젝트를 만들고 이름을](media/vs2019-configure-new-project-hello-world.png "이름 및 새 프로젝트를 만들려면")

   Visual Studio 새 프로젝트를 추가 하 고 소스 코드를 편집할 수 있게 만듭니다. 기본적으로 "Hello World" 앱을 사용 하 여 소스 코드는 콘솔 앱 템플릿을 채웁니다.

   ![IDE에서 hello World 프로젝트](media/vs2019-hello-world-code.png "IDE에서 Hello World 프로젝트")

   코드 편집기에서 다음과 같이 표시 하는 경우 다음 단계로 이동 하 여 앱을 빌드할 준비가입니다.

::: moniker-end

::: moniker range="<=vs-2017"

1. Visual Studio의 **파일** 메뉴에서 **새로 만들기 > 프로젝트**를 선택해 **새 프로젝트** 대화상자를 엽니다.

   ![새 프로젝트 대화 상자를 엽니다](media/vscpp-file-new-project.gif "새 프로젝트 대화 상자를 열려면")

1. 에 **새 프로젝트** 대화 상자에서 **설치 됨**, **Visual C++**  아직 선택 되지 않은 경우 다음을 선택 합니다 **빈 프로젝트**템플릿. 에 **이름을** 필드를 입력 합니다 *HelloWorld*합니다. 선택할 **확인** 프로젝트를 만듭니다.

   ![새 프로젝트를 만들고 이름을](media/vscpp-concierge-project-name-callouts.png "이름 및 새 프로젝트를 만들려면")

Visual Studio를 만들고 소스 코드 파일을 추가 하려면 원하는 앱의 종류에 대 한 특수화 준비가 새로 만든 빈 프로젝트를 만듭니다. 다음에 수행 합니다.

[문제가 발생했습니다.](#create-your-app-project-issues)

## <a name="make-your-project-a-console-app"></a>콘솔 앱 프로젝트 만들기

Visual Studio는 Windows 및 기타 플랫폼에 대 한 모든 종류의 앱 및 구성 요소를 만들 수 있습니다. 합니다 **빈 프로젝트** 템플릿을 만들면 어떤 종류의 앱에 대 한 특정 되지 않습니다. 만들려는 *콘솔 앱*하나씩 콘솔 또는 명령 프롬프트 창에서 실행 되는 콘솔 하위 시스템을 사용 하려면 앱을 빌드하려면 Visual Studio를 지시 해야 합니다.

1. Visual Studio에서 엽니다는 **프로젝트** 메뉴 선택 **속성** 열려는 합니다 **HelloWorld 속성 페이지** 대화 합니다.

1. 에 **속성 페이지** 대화 상자 아래에 있는 **구성 속성**를 선택 **링커**, **시스템**, 선택한 후 편집 상자 옆에 합니다 **하위 시스템** 속성입니다. 표시 되는 드롭다운 메뉴에서 선택 **콘솔 (/ /SUBSYSTEM: CONSOLE)** 합니다. **확인**을 선택하여 변경 내용을 저장합니다.

   ![속성 페이지 대화 상자를 엽니다](media/vscpp-properties-linker-subsystem.gif "속성 페이지 대화 상자를 열려면")

Visual Studio는 이제 콘솔 창에서 실행 하 여 프로젝트를 빌드할 알고 있습니다. 다음으로, 소스 코드 파일을 추가 하 고 앱에 대 한 코드를 입력 합니다.

[문제가 발생했습니다.](#make-your-project-a-console-app-issues)

## <a name="add-a-source-code-file"></a>소스 코드 파일을 추가 합니다.

1. **솔루션 탐색기**, HelloWorld 프로젝트를 선택 합니다. 메뉴 모음에서 선택 **프로젝트**, **새 항목 추가** 열려는 합니다 **새 항목 추가** 대화 합니다.

1. 에 **새 항목 추가** 대화 상자에서 **Visual C++**  아래 **설치 됨** 아직 선택 하지 않은 경우. 가운데 창에서 선택  **C++ 파일 (.cpp)** 합니다. 변경 된 **이름을** 하 *HelloWorld.cpp*합니다. 선택할 **추가** 파일을 만들고 대화 상자를 닫습니다.

   ![HelloWorld.cpp에 대 한 소스 파일을 추가](media/vscpp-add-new-item.gif "HelloWorld.cpp에 대 한 원본 파일을 추가 합니다.")

Visual studio 새 비어 있는 소스 코드 파일을 만들고 소스 코드를 입력 하 고 편집기 창에서 열립니다.

[문제가 발생했습니다.](#add-a-source-code-file-issues)

## <a name="add-code-to-the-source-file"></a>소스 파일에 코드 추가

1. HelloWorld.cpp 편집기 창에이 코드를 복사 합니다.

   ```cpp
   #include <iostream>

   int main()
   {
       std::cout << "Hello, world!" << std::endl;
       return 0;
   }
   ```

   코드는 편집기 창에서 다음과 같이 표시 됩니다.

   ![Hello World 코드 편집기에서](media/vscpp-hello-world-editor.png "Hello World 코드 편집기에서")

코드 편집기에서 다음과 같이 표시 하는 경우 다음 단계로 이동 하 여 앱을 빌드할 준비가입니다.

[문제가 발생했습니다.](#add-a-source-code-file-issues)

::: moniker-end

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [빌드 및 실행을 C++ 프로젝트](vscpp-step-2-build.md)

::: moniker range="<=vs-2017"

## <a name="troubleshooting-guide"></a>문제 해결 가이드

여기로 솔루션에 대 한 일반적인 문제를 처음 만들 때 C++ 프로젝트입니다.

### <a name="create-your-app-project-issues"></a>앱 프로젝트 문제 만들기

경우는 **새 프로젝트** 대화 상자에 표시 하지 않습니다는 **Visual C++**  아래 항목 **설치 됨**, Visual Studio의 사본의 없을 가능성이 많습니다 합니다 **데스크톱 사용 하 여 개발 C++**  워크 로드가 설치 되어 있습니다. 오른쪽에서 설치 관리자를 실행할 수 있습니다 합니다 **새 프로젝트** 대화 합니다. 선택 된 **Visual Studio 설치 관리자 열기** 링크 설치 관리자를 다시 시작 합니다. 경우는 **사용자 계정 컨트롤** 권한을 요청 하는 대화 상자, 선택 **예**합니다. 설치 관리자에서 있는지 확인 합니다 **를 사용한 데스크톱 개발 C++**  작업을 선택 하면 선택한 **확인** Visual Studio 설치를 업데이트 합니다.

동일한 이름의 다른 프로젝트에 이미 있으면 프로젝트에 대해 다른 이름을 선택 하거나 기존 프로젝트를 삭제 하 고 다시 시도 합니다. 기존 프로젝트를 삭제 하려면 파일 탐색기에서 솔루션 폴더 (helloworld.sln 파일이 있는 폴더)를 삭제 합니다.

[돌아가서](#create-your-app-project)합니다.

### <a name="make-your-project-a-console-app-issues"></a>프로젝트는 콘솔 앱 문제 확인

표시 되지 않는 경우 **링커** 아래에 나열 된 **구성 속성**, 선택 **취소** 닫으려면를 **속성 페이지** 대화 차례로 있는지 확인 합니다 **HelloWorld** 에서 프로젝트를 선택한 **솔루션 탐색기**, 없습니다 솔루션 또는 다른 파일 또는 폴더를 다시 시도 하기 전에 합니다.

Dropdown 컨트롤이 나타나지 않습니다 합니다 **하위 시스템** 속성 속성을 선택할 때까지 상자를 편집 합니다. 포인터를 사용 하 여 선택할 수 있습니다 또는 탭 간에 전환 될 때까지 대화 상자 컨트롤을 누르면 **하위 시스템** 강조 표시 됩니다. 드롭다운 컨트롤을 선택 하거나 열려는 Alt + 아래쪽 화살표를 누릅니다.

[돌아 가](#make-your-project-a-console-app)

### <a name="add-a-source-code-file-issues"></a>소스 코드 파일 문제를 추가 합니다.

소스 코드 파일에 다른 이름을 지정 하는 경우에 것이 좋습니다. 그러나 프로젝트에 동일한 코드를 포함 하는 소스 코드 파일을 여러 개를 추가 하지 마세요.

프로젝트에 잘못 된 종류의 파일을 추가한 경우 예를 들어, 헤더 파일을 삭제 다시 시도 합니다. 파일을 삭제 하려면 **솔루션 탐색기** 를 Delete 키를 누릅니다.

[돌아가서](#add-a-source-code-file)합니다.

### <a name="add-code-to-the-source-file-issues"></a>원본 파일 문제에 코드 추가

소스 코드 파일 편집기 창 다시 열어서를 실수로 닫은 경우 두 번 클릭에 HelloWorld.cpp 합니다 **솔루션 탐색기** 창입니다.

빨간색 물결선 소스 코드 편집기에서 모든 항목에서 표시 하는 경우 코드 사례, 맞춤법 및 문장 부호에 예제와 일치 하는지 확인 합니다. 경우에 중요 한 C++ 코드입니다.

[돌아가서](#add-code-to-the-source-file)합니다.

::: moniker-end

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
