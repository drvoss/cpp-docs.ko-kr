---
title: Visual Studio에서 Linux CMake 프로젝트 만들기 및 구성
description: Visual Studio에서 Linux CMake 프로젝트를 만들고, 구성, 편집 및 컴파일하는 방법
ms.date: 05/03/2020
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: c12e32801c992f6ba3675327b9ae537890202a4c
ms.sourcegitcommit: 8a01ae145bc65f5bc90d6e47b4a1bdf47b073ee7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82765762"
---
# <a name="create-and-configure-a-linux-cmake-project"></a>Linux CMake 프로젝트 만들기 및 구성

::: moniker range="vs-2015"

Linux 지원은 Visual Studio 2017 이상에서 사용할 수 있습니다. 이러한 버전에 대한 설명서를 보려면 이 문서에 대한 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정하세요. 이 페이지의 목차 맨 위에 있습니다.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="before-you-begin"></a>시작하기 전 주의 사항

먼저 CMake 구성 요소를 비롯한 **C++를 사용한 Linux 개발** 워크로드가 설치되었는지 확인합니다. [Visual Studio에서 C++ Linux 워크로드 설치](download-install-and-setup-the-linux-development-workload.md)를 참조하세요.

Linux 시스템에서 다음이 설치되어 있는지 확인합니다.

- gcc
- gdb
- rsync
- zip
- ninja-build

::: moniker-end

::: moniker range="vs-2019"

Linux에서 CMake 프로젝트를 지원하려면 대상 컴퓨터에 최신 버전의 CMake가 있어야 합니다. 배포의 기본 패키지 관리자가 제공하는 버전이 Visual Studio에 필요한 모든 기능을 지원하기에 충분하지 않을 수 있습니다. Visual Studio 2019는 CMake의 최신 버전이 Linux 시스템에 설치되어 있는지 검색합니다. 아무 버전도 찾지 못하는 경우 Visual Studio는 편집기 창의 맨 위에 정보 표시줄을 표시합니다. [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases)에서 CMake을 설치할 것을 제안합니다.

Visual Studio에서 CMake가 지원되려면 CMake 3.8에 도입된 서버 모드 지원이 필요합니다. Visual Studio 2019에서는 버전 3.14 이상이 권장됩니다.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio에서 CMake가 지원되려면 CMake 3.8에 도입된 서버 모드 지원이 필요합니다. Microsoft 제공 CMake 변형의 경우 [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases)에서 미리 빌드된 최신 이진 파일을 다운로드합니다.

이진 파일은 `~/.vs/cmake`에 설치됩니다. 이진 파일을 배포하면 프로젝트가 자동으로 다시 생성됩니다. *CMakeSettings.json*의 `cmakeExecutable` 필드에 지정된 CMake가 유효하지 않고(존재하지 않거나 지원되지 않는 버전인 경우) 미리 빌드된 이진 파일이 있는 경우 Visual Studio는 `cmakeExecutable`을 무시하고 미리 빌드된 이진 파일을 사용합니다.

:::moniker-end

::: moniker range="vs-2019"

## <a name="create-a-new-linux-cmake-project"></a>새 Linux CMake 프로젝트 만들기

Visual Studio 2019에서 새 Linux CMake 프로젝트를 만들려면

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택하거나 **Ctrl + Shift + N**을 누릅니다.
1. **언어**를 **C++** 로 설정하고 “CMake”를 검색합니다. **다음**을 선택합니다. **이름** 및 **위치**를 입력하고, **만들기**를 선택합니다.

Visual Studio는 실행 파일 이름 및 필요한 최소 CMake 버전만 사용하여 최소한의 *CMakeLists.txt* 파일을 만듭니다. 하지만 이 파일을 원하는 대로 수동으로 편집할 수 있습니다. Visual Studio에서 변경 내용을 덮어쓰지 않습니다. 이 파일에서 CMake 명령줄 인수와 환경 변수를 지정할 수 있습니다. **솔루션 탐색기**에서 루트 *CMakeLists.txt* 파일을 마우스 오른쪽 단추로 클릭하고 **프로젝트에 대한 CMake 설정**을 선택합니다. 디버깅 옵션을 지정하려면 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **디버그 및 시작 설정**을 선택합니다.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="open-a-cmake-project-folder"></a>CMake 프로젝트 폴더 열기

기존 CMake 프로젝트가 포함된 폴더를 열면, Visual Studio는 CMake 캐시의 변수를 사용하여 IntelliSense를 구성하고 자동으로 빌드합니다. 로컬 구성 및 디버깅 설정은 JSON 파일에 저장됩니다. 필요에 따라 이들 파일을 Visual Studio를 사용하는 다른 사용자와 공유할 수 있습니다.

Visual Studio는 *CMakeLists.txt* 파일을 수정하지 않습니다. 동일 프로젝트에서 작업하는 다른 사용자가 기존 도구를 계속 사용할 수 있도록 그대로 남아 있습니다. *CMakeLists.txt* 또는 경우에 따라 *CMakeSettings.json*에 대한 편집 내용을 저장하면, Visual Studio가 캐시를 다시 생성합니다. 그러나 **기존 캐시** 구성을 사용하는 경우에는 Visual Studio에서 캐시를 수정하지 않습니다.

Visual Studio의 CMake 지원에 관한 일반적인 내용은 [Visual Studio의 CMake 프로젝트](../build/cmake-projects-in-visual-studio.md)를 참조하세요. 여기서 계속하기 전에 먼저 읽어보세요.

시작하려면 주 메뉴에서 **파일** > **열기** > **폴더**를 선택하거나 [개발자 명령 프롬프트](../build/building-on-the-command-line.md) 창에 `devenv.exe <foldername>`을 입력합니다. 열린 폴더에는 소스 코드와 함께 *CMakeLists.txt* 파일이 있어야 합니다.

다음 예제에서는 간단한 *CMakeLists.txt* 파일과 .cpp 파일을 보여 줍니다.

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

*CMakeLists.txt*:

```txt
cmake_minimum_required(VERSION 3.8)
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Linux 대상 선택

폴더를 여는 즉시 Visual Studio가 *CMakeLists.txt* 파일을 구문 분석하고 **x86-Debug**의 Windows 대상을 지정합니다. 원격 Linux 시스템을 대상으로 지정하려면 프로젝트 설정을 **Linux-Debug** 또는 **Linux-Release**로 변경합니다. 아래의 [Linux용 CMake 설정 구성](#configure_cmake_linux)을 참조하세요.

::: moniker-end

::: moniker range="vs-2019"

Linux용 Windows 하위 시스템을 대상으로 지정하려면 주 도구 모음의 구성 드롭다운에서 **구성 관리**를 클릭합니다. 그런 다음 **구성 추가** 단추를 누르고, GCC를 사용하는 경우 **WSL-Debug** 또는 **WSL-Release**를 선택합니다. Clang/LLVM 도구 집합을 사용하는 경우 Clang 변형을 사용합니다.

**Visual Studio 2019 버전 16.1**이 WSL을 대상으로 하는 경우 소스 또는 헤더를 복사할 필요가 없습니다. Linux 컴파일러가 Windows 파일 시스템의 소스 파일에 직접 액세스할 수 있기 때문입니다. (Windows 10 버전 1903 이상에서 Windows 애플리케이션은 마찬가지로 Linux 헤더 파일에 직접 액세스할 수 있습니다. Visual Studio는이 기능을 아직 활용하지 않습니다.)

::: moniker-end

::: moniker range=">=vs-2017"

원격 대상의 경우 기본적으로 Visual Studio는 **도구** > **옵션** > **플랫폼 간** > **연결 관리자** 아래에 있는 목록에서 첫 번째 원격 시스템을 선택합니다. 원격 연결이 발견되지 않으면 만들라는 메시지가 표시됩니다. 자세한 내용은 [원격 Linux 컴퓨터에 연결](connect-to-your-remote-linux-computer.md)을 참조하세요.

원격 Linux 대상을 지정하면 원격 시스템에 원본이 복사됩니다.

대상을 선택하면 CMake는 프로젝트에 대한 CMake 캐시를 생성하도록 Linux 시스템에서 자동으로 실행됩니다.

![Linux에서 CMake 캐시 생성](media/cmake-linux-1.png "Linux에서 CMake 캐시 생성")

원격 Linux 시스템의 헤더에 IntelliSense 지원을 제공하기 위해 Visual Studio는 Linux 머신에서 로컬 Windows 머신의 디렉터리에 IntelliSense를 자동으로 복사합니다. 자세한 내용은 [원격 헤더를 위한 IntelliSense](configure-a-linux-project.md#remote_intellisense)를 참조하세요.

## <a name="debug-the-cmake-project"></a><a name="debug_cmake_project"></a> CMake 프로젝트 디버그

지정된 대상 시스템에서 코드를 디버그하려면 중단점을 설정합니다. 프로젝트 설정 옆에 있는 도구 모음 메뉴에서 시작 항목으로 CMake 대상을 선택합니다. 그런 다음 도구 모음에서 **&#x23f5; 시작**을 선택하거나 **F5** 키를 누릅니다.

프로그램의 명령줄 인수를 사용자 지정하려면 **솔루션 탐색기**의 맨 위에 있는 **대상 전환** 단추를 누르고 **대상 보기**를 선택합니다. 대상을 마우스 오른쪽 단추로 클릭하고 **디버그 및 시작 설정**을 선택합니다. 이 명령은 프로그램에 대한 정보가 들어 있는 *launch.vs.json* 구성 파일을 열거나 만듭니다 소스 파일의 위치를 지정하려면 다음 예제와 같이 **sourceFileMap** 속성을 파일에 추가합니다.

```json
"MIMode": "gdb",
"externalConsole": true,
"sourceFileMap": {
"c/Users/USER/source/repos/CMAKEPROJECTNAME": "C:\\Users\\USER\\source\\repos\\CMAKEPROJECTNAME"
},
"remoteMachineName": "${debugInfo.remoteMachineName}",
```

추가 인수를 지정하려면 `args` JSON 배열에 추가합니다. 자세한 내용은 [C++용 폴더 열기 프로젝트](../build/open-folder-projects-cpp.md) 및 [CMake 디버깅 세션 구성](../build/configure-cmake-debugging-sessions.md)을 참조하세요.

## <a name="configure-cmake-settings-for-linux"></a><a name="configure_cmake_linux"></a> Linux용 CMake 설정 구성

CMake Linux 프로젝트에 있는 *CMakeSettings.json* 파일은 [CMake 설정 사용자 지정](../build/customize-cmake-settings.md)에 나열된 모든 속성 및 원격 Linux 머신의 빌드 설정을 제어하는 추가 속성도 지정할 수 있습니다.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019의 기본 CMake 설정을 변경하려면 주 도구 모음에서 **구성** 드롭다운을 열고 **구성 관리**를 선택합니다.

![CMake 구성 관리](../build/media/vs2019-cmake-manage-configurations.png "CMake 구성 드롭다운")

이 명령은 루트 프로젝트 폴더의 *CMakeSettings.json* 파일을 편집하는 데 사용할 수 있는 **CMake 설정 편집기**를 엽니다. 편집기에서 **JSON 편집** 단추를 클릭하여 파일을 직접 열 수도 있습니다. 자세한 내용은 [CMake 설정 사용자 지정](../build/customize-cmake-settings.md)을 참조하세요.

Visual Studio 2019 버전 16.1 이상의 기본 Linux-Debug 구성은 다음과 같습니다.

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "configurationType": "Debug",
      "cmakeExecutable": "/usr/bin/cmake",
      "remoteCopySourcesExclusionList": [ ".vs", ".git", "out" ],
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux_x64" ],
      "remoteMachineName": "${defaultRemoteMachineName}",
      "remoteCMakeListsRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/src",
      "remoteBuildRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/out/build/${name}",
      "remoteInstallRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/out/install/${name}",
      "remoteCopySources": true,
      "rsyncCommandArgs": "-t --delete --delete-excluded",
      "remoteCopyBuildOutput": false,
      "remoteCopySourcesMethod": "rsync",
      "addressSanitizerRuntimeFlags": "detect_leaks=0",
      "variables": []
    }
  ]
}
```

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017에서 기본 CMake 설정을 변경하려면 주 메뉴에서 **CMake** > **CMake 설정 변경** > **CMakeLists.txt**를 선택합니다. 또는 **솔루션 탐색기**에서 *CMakeSettings.txt*를 마우스 오른쪽 단추로 클릭하고 **CMake 설정 변경**을 선택합니다. 그러면 Visual Studio가 루트 프로젝트 폴더에 새 *CMakeSettings.json* 파일을 만듭니다. **CMake 설정** 편집기를 사용하여 파일을 열거나 파일을 직접 수정할 수 있습니다. 자세한 내용은 [CMake 설정 사용자 지정](../build/customize-cmake-settings.md)을 참조하세요.

다음 예제에서는 이전 코드 예제를 기반으로 하는 Visual Studio 2017(및 Visual Studio 2019 버전 16.0)의 Linux-Debug 기본 구성을 보여 줍니다.

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "remoteMachineName": "${defaultRemoteMachineName}",
      "configurationType": "Debug",
      "remoteCMakeListsRoot": "/var/tmp/src/${workspaceHash}/${name}",
      "cmakeExecutable": "/usr/local/bin/cmake",
      "buildRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteInstallRoot": "/var/tmp/build/${workspaceHash}/install/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "remoteCopySourcesMethod": "rsync",
      "remoteCopySourcesExclusionList": [".vs", ".git"],
      "rsyncCommandArgs" : "-t --delete --delete-excluded",
      "remoteCopyBuildOutput" : "false",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```

::: moniker-end

::: moniker range=">=vs-2017"

이러한 설정에 대한 자세한 내용은 [CMakeSettings.json 참조](../build/cmakesettings-reference.md)를 참조하세요.

## <a name="optional-settings"></a>선택적 설정

더욱 세부적인 제어를 위해 다음과 같은 선택적 설정을 사용할 수 있습니다.

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

이러한 옵션을 사용하면 빌드하기 전후 및 CMake 생성 전에 Linux 시스템에서 명령을 실행할 수 있습니다. 값은 원격 시스템에서 유효한 모든 명령일 수 있습니다. 출력은 Visual Studio로 다시 파이핑됩니다.

## <a name="see-also"></a>참조

[프로젝트 속성 사용](../build/working-with-project-properties.md)<br/>
[Visual Studio의 CMake 프로젝트](../build/cmake-projects-in-visual-studio.md)<br/>
[원격 Linux 컴퓨터에 연결](connect-to-your-remote-linux-computer.md)<br/>
[CMake 사용자 지정 설정](../build/customize-cmake-settings.md)<br/>
[CMake 디버깅 세션 구성](../build/configure-cmake-debugging-sessions.md)<br/>
[Linux 프로젝트 배포, 실행 및 디버그](deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 미리 정의된 구성 참조](../build/cmake-predefined-configuration-reference.md)

::: moniker-end
