---
title: Visual Studio에서 CMake 빌드 설정 사용자 지정
ms.date: 08/20/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: f93997e498502e0e326edfc2b023af9808f86357
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078657"
---
# <a name="customize-cmake-build-settings"></a>CMake 빌드 설정 사용자 지정

::: moniker range="vs-2019"

Visual Studio 2019 이상에서는 **CMake 설정 편집기**를 사용하여 구성을 추가하고 설정을 사용자 지정할 수 있습니다. 편집기는 *Cmakesettings. json* 파일을 수동으로 편집 하는 것 보다 간단한 방법 이지만 파일을 직접 편집 하는 것을 선호 하는 경우 편집기의 오른쪽 위에 있는 **json 편집** 링크를 클릭 하면 됩니다.

편집기를 열려면 주 도구 모음에서 **구성** 드롭다운을 클릭하고 **구성 관리**를 선택합니다.

![CMake 구성 드롭다운](media/vs2019-cmake-manage-configurations.png)

이제 왼쪽에 설치된 구성과 함께 **설정 편집기**가 보입니다.

![CMake 설정 편집기](media/cmake-settings-editor.png)

Visual Studio는 기본적으로 하나의 `x64-Debug` 구성을 제공 합니다. 녹색 더하기 기호를 클릭 하 여 다른 구성을 추가할 수 있습니다. 편집기에 표시 되는 설정은 선택한 구성에 따라 달라질 수 있습니다.

편집기에서 선택 하는 옵션은 *Cmakesettings. json*이라는 파일에 기록 됩니다. 이 파일은 프로젝트를 빌드할 때 CMake로 전달되는 환경 변수 및 명령줄 인수를 제공합니다. Visual Studio는 자동으로 *Cmakelists .txt를* 수정 하지 않습니다. *Cmakesettings. json* 을 사용 하 여 Visual Studio를 통해 빌드를 사용자 지정할 수 있습니다 .이 경우에는 팀의 다른 사용자가 사용 하는 도구와 함께 사용할 수 있도록 cbuild 프로젝트 파일을 그대로 둡니다.

## <a name="cmake-general-settings"></a>CMake 일반 설정

다음 설정은 **일반** 제목 아래에서 사용할 수 있습니다.

### <a name="configuration-name"></a>구성 이름

**name** 설정에 해당합니다. 이 이름은 C++ 구성 드롭다운에 표시 됩니다. `${name}` 매크로를 사용하여 경로 등의 다른 속성 값을 작성할 수 있습니다.

### <a name="configuration-type"></a>구성 유형

**configurationType** 설정에 해당합니다. 선택한 생성기의 빌드 구성 형식을 정의합니다. 현재 지원되는 값은 "Debug", "MinSizeRel", "Release" 및 "RelWithDebInfo"입니다. [CMAKE_BUILD_TYPE](https://cmake.org/cmake/help/latest/variable/CMAKE_BUILD_TYPE.html)에 매핑됩니다.

### <a name="toolset"></a>도구 집합

**inheritedEnvironments** 설정에 해당합니다. 선택한 구성을 작성 하는 데 사용 되는 컴파일러 환경을 정의 합니다. 지원되는 값은 구성 형식에 따라 다릅니다. 사용자 지정 환경을 만들려면 설정 편집기의 오른쪽 위 모서리에서 **Json 편집** 링크를 선택 하 고 *cmakesettings. json* 파일을 직접 편집 합니다.

### <a name="cmake-toolchain-file"></a>CMake 도구 체인 파일

[Cmake 파일](https://cmake.org/cmake/help/latest/variable/CMAKE_TOOLCHAIN_FILE.html)의 경로입니다. 이 경로는 Ctoas "-DCMAKE_TOOLCHAIN_FILE = \<filepath >"로 전달 됩니다. 도구 체인 파일은 컴파일러와 도구 체인 유틸리티의 위치 및 기타 대상 플랫폼과 컴파일러 관련 정보를 지정 합니다. 이 설정이 지정 되지 않은 경우 기본적으로 Visual Studio는 [vcpkg 도구 체인 파일](https://github.com/microsoft/vcpkg/blob/master/docs/examples/installing-and-using-packages.md#cmake) 을 사용 합니다.

### <a name="build-root"></a>빌드 루트

**buildRoot**에 해당합니다. [CMAKE_BINARY_DIR](https://cmake.org/cmake/help/v3.15/variable/CMAKE_BINARY_DIR.html)에 매핑되고 cmake cache를 만들 위치를 지정 합니다. 지정 된 폴더가 존재 하지 않는 경우 만들어집니다.

## <a name="command-arguments"></a>명령 인수

다음 설정은 **명령 인수** 제목 아래에서 사용할 수 있습니다.

### <a name="cmake-command-arguments"></a>CMake 명령 인수

**cmakeCommandArgs**에 해당합니다. CMake에 전달 되는 추가 [명령줄 옵션](https://cmake.org/cmake/help/latest/manual/cmake.1.html) 을 지정 합니다.

### <a name="build-command-arguments"></a>빌드 명령 인수

**Buildcommandargs**에 해당 합니다. 기본 빌드 시스템에 전달할 추가 스위치를 지정 합니다. 예를 들어 Ninja 생성기를 사용할 때 `-v`를 전달 하면 Ninja가 명령줄을 출력 합니다.

### <a name="ctest-command-arguments"></a>CTest 명령 인수

**Ctestcommandargs**에 해당 합니다. 테스트를 실행할 때 CTest에 전달할 추가 [명령줄 옵션](https://cmake.org/cmake/help/v3.15/manual/ctest.1.html) 을 지정 합니다.

## <a name="general-settings-for-remote-builds"></a>원격 빌드의 일반 설정

원격 빌드를 사용하는 Linux 같은 구성에는 다음 설정을 사용할 수도 있습니다.

### <a name="rsync-command-arguments"></a>rsync 명령 인수

빠르고 다양 한 파일 복사 도구인 [rsync](https://download.samba.org/pub/rsync/rsync.html)에 전달 되는 추가 명령줄 옵션입니다.

## <a name="cmake-variables-and-cache"></a>CMake 변수 및 캐시

이러한 설정을 사용 하 여 Cmakevariables를 설정 하 고 *Cmakesettings. json*에 저장할 수 있습니다. 빌드 시 cmake에 전달 되 고 *Cmakelists .txt* 파일에 있는 모든 값을 재정의 합니다. CMakeGUI를 사용할 때와 똑같은 방식으로 이 섹션을 사용하여 편집에 사용 가능한 모든 CMake 변수 목록을 볼 수 있습니다. 고급 변수(CMakeGUI당)를 포함하여 편집에 사용 가능한 모든 CMake 변수 목록을 보려면 **저장하고 캐시 생성** 단추를 클릭합니다. 변수 이름을 기준으로 목록을 필터링 할 수 있습니다.

**변수에**해당 합니다. *_Ctoname_=_value_* 로 전달 된 ctovariables의 **이름-** 값 쌍을 포함 합니다. Cmake 프로젝트 빌드 지침에서 cmake 캐시 파일에 직접 변수를 추가 하도록 지정 하는 경우 여기에 추가 하는 것이 좋습니다.

## <a name="advanced-settings"></a>고급 설정

### <a name="cmake-generator"></a>CMake 생성기

**생성기**에 해당 합니다. **C.g** 스위치에 매핑되고 사용할 [cmake 생성기](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html) 를 지정 합니다. 이 속성은 다른 속성 값을 구성할 때 매크로(`${generator}`)로 사용할 수도 있습니다. Visual Studio에서 현재 지원하는 CMake 생성기는 다음과 같습니다.

  - "Ninja"
  - "Unix 메이크파일"
  - "Visual Studio 16 2019"
  - "Visual Studio 16 2019 Win64"
  - "Visual Studio 16 2019 ARM"
  - "Visual Studio 15 2017"
  - "Visual Studio 15 2017 Win64"
  - "Visual Studio 15 2017 ARM"
  - "Visual Studio 14 2015"
  - "Visual Studio 14 2015 Win64"
  - "Visual Studio 14 2015 ARM"
  
Ninja는 유연성 및 함수 대신 빠른 빌드 속도로 설계 되었으므로 기본값으로 설정 됩니다. 그러나 일부 CMake 프로젝트는 Ninja를 사용하여 올바르게 빌드하지 못할 수도 있습니다. 이 경우 Visual Studio 프로젝트를 대신 생성 하도록 CMake 지시할 수 있습니다.

### <a name="intellisense-mode"></a>IntelliSense 모드

IntelliSense 엔진에서 사용 하는 IntelliSense 모드입니다. 모드를 선택 하지 않은 경우 Visual Studio는 지정 된 도구 집합에서 상속 합니다.  

### <a name="install-directory"></a>설치 디렉터리

CMake가 대상으로 설치 하는 디렉터리입니다. [CMAKE_INSTALL_PREFIX](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html)에 매핑됩니다.

### <a name="cmake-executable"></a>CMake 실행 파일

파일 이름 및 확장명을 포함 하 여 CMake 실행 파일의 전체 경로입니다. Visual Studio에서 사용자 지정 버전의 CMake를 사용할 수 있습니다. 원격 빌드의 경우 원격 머신의 CMake 위치를 지정합니다.

원격 빌드를 사용하는 Linux 같은 구성에는 다음 설정을 사용할 수도 있습니다.

### <a name="remote-cmakeliststxt-root"></a>원격 CMakeLists.txt 루트

루트 *Cmakelists .txt* 파일을 포함 하는 원격 컴퓨터의 디렉터리입니다.

### <a name="remote-install-root"></a>원격 설치 루트

CMake가 대상을 설치하는 원격 머신의 디렉터리입니다. [CMAKE_INSTALL_PREFIX](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html)에 매핑됩니다.

### <a name="remote-copy-sources"></a>원본 소스 복사

원본 파일을 원격 컴퓨터에 복사할지 여부를 지정 하 고, rsync 또는 sftp를 사용할지 여부를 지정할 수 있습니다.

## <a name="directly-edit-cmakesettingsjson"></a>CMakeSettings.json 직접 편집

*Cmakesettings. json* 을 직접 편집 하 여 사용자 지정 구성을 만들 수도 있습니다. **설정 편집기**의 오른쪽 위에는 편집할 파일을 여는 **JSON 편집** 단추가 있습니다.

다음 예제는 시작점으로 사용할 수 있는 샘플 구성을 보여줍니다.

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },
```

JSON IntelliSense는 *Cmakesettings. json* 파일을 편집 하는 데 도움이 됩니다.

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

JSON 편집기는 호환 되지 않는 설정을 선택 하는 경우에도 알려줍니다.

파일의 각 속성에 대한 자세한 내용은 [CMakeSettings.json 스키마 참조](cmakesettings-reference.md)를 확인하세요.

::: moniker-end

::: moniker range="<=vs-2017"

Visual Studio 2017은 CMake.exe를 호출하여 지정된 프로젝트에 대한 CMake 캐시를 만드는 방법을 정의하는 몇 가지 CMake 구성을 제공합니다. 새 구성을 추가하려면 도구 모음에서 구성 드롭다운을 클릭하고 **구성 관리**를 선택합니다.

   ![CMake 구성 관리](media/cmake-manage-configurations.png)

미리 정의된 구성 목록에서 다음을 선택할 수 있습니다.

   ![CMake 미리 정의된 구성](media/cmake-configurations.png)

처음으로 구성을 선택 하는 경우 Visual Studio는 프로젝트의 루트 폴더에 *Cmakesettings. json* 파일을 만듭니다. 이 파일은 예를 들어 **정리** 작업 후에 CMake 캐시 파일을 다시 만드는 데 사용됩니다.

추가 구성을 추가 하려면 마우스 오른쪽 단추로 *Cmakesettings. json* 을 클릭 하 고 **구성 추가**를 선택 합니다.

   ![CMake 구성 추가](media/cmake-add-configuration.png "CMake 구성 추가")

**CMake 설정 편집기**를 사용하여 파일을 편집할 수도 있습니다. **솔루션 탐색기** 에서 *cmakesettings. json* 을 마우스 오른쪽 단추로 클릭 하 고 **csettings 설정 편집**을 선택 합니다. 또는 편집기 창 상단의 구성 드롭다운에서 **구성 관리**를 선택합니다.

*Cmakesettings. json* 을 직접 편집 하 여 사용자 지정 구성을 만들 수도 있습니다. 다음 예제는 시작점으로 사용할 수 있는 샘플 구성을 보여줍니다.

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },
```

JSON IntelliSense는 *Cmakesettings. json* 파일을 편집 하는 데 도움이 됩니다.

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

파일의 각 속성에 대한 자세한 내용은 [CMakeSettings.json 스키마 참조](cmakesettings-reference.md)를 확인하세요.

::: moniker-end

## <a name="see-also"></a>참고 항목

[Visual Studio의 CMake 프로젝트](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake 프로젝트 구성](../linux/cmake-linux-project.md)<br/>
[원격 Linux 컴퓨터에 연결](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake 디버깅 세션 구성](configure-cmake-debugging-sessions.md)<br/>
[Linux 프로젝트 배포, 실행 및 디버그](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 미리 정의된 구성 참조](cmake-predefined-configuration-reference.md)
