---
title: Visual Studio에서 CMake 디버깅 세션 구성
description: Visual Studio를 사용 하 여 CMake 디버거 설정을 구성 하는 방법을 설명 합니다.
ms.date: 01/13/2020
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 5e627f02b5245baede6e92268cedfc43957f3abc
ms.sourcegitcommit: 49e4fb3e0300fe86c814130661f1bf68b16e72e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2020
ms.locfileid: "76031330"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake 디버깅 세션 구성

::: moniker range="vs-2015"

네이티브 Ctosupport는 Visual Studio 2017 이상에서 사용할 수 있습니다.

::: moniker-end

::: moniker range=">=vs-2017"

실행 가능한 모든 CMake 대상은 **일반** 도구 모음의 **시작 항목** 드롭다운에 표시됩니다. 디버깅 세션을 시작하려면 하나를 선택하고 디버거를 시작하기만 하면 됩니다.

![CMake 시작 항목 드롭다운](media/cmake-startup-item-dropdown.png "CMake 시작 항목 드롭다운")

솔루션 탐색기에서 디버그 세션을 시작할 수도 있습니다. 먼저 **솔루션 탐색기** 창의 **Cmake 대상 뷰로** 전환 합니다.

![CMake 대상 보기 단추](media/cmake-targets-view.png  "CMake 대상 보기 메뉴 항목")

그런 다음 실행 파일을 마우스 오른쪽 단추로 클릭 하 고 **디버그** 또는 **디버그 및 시작 설정**을 선택 합니다. **디버깅** 은 활성 구성에 따라 선택한 대상의 디버깅을 자동으로 시작 합니다. **디버그 및 시작 설정** 은 *시작. vs json* 파일을 열고 선택한 대상에 대 한 새 디버그 구성을 추가 합니다.

## <a name="customize-debugger-settings"></a>디버거 설정 사용자 지정

프로젝트에서 실행 중인 Ctotarget에 대 한 디버거 설정을 *시작. vs. json*이라는 파일에 사용자 지정할 수 있습니다. 이 파일에는 다음과 같은 세 가지 진입점이 있습니다.

- 주 메뉴에서 **디버그 > 디버그 및 시작 설정** 을 선택 하 여 활성 디버그 대상과 관련 된 디버그 구성을 편집 합니다. 활성 대상이 선택 되지 않은 경우이 옵션은 회색으로 표시 됩니다.

- 솔루션 탐색기에서 **대상 뷰로** 이동 합니다. 그런 다음 디버그 대상을 마우스 오른쪽 단추로 클릭 하 고 **디버그 및 시작 설정을** 선택 하 여 선택한 대상과 관련 된 디버그 구성을 편집 합니다.

- 루트 CMakeLists를 마우스 오른쪽 단추로 클릭 하 고 **디버그 및 시작 설정을** 선택 하 여 **디버거 선택** 대화 상자를 엽니다. 대화 상자에서 디버그 구성을 추가할 수 있지만 `projectTarget` 속성을 통해 호출할 CMake를 수동으로 지정 해야 합니다.

*Cmakesettings. json* 파일의 모든 키를 참조 하려면 해당 파일 앞에 `cmake.` *시작 및 json*을 입력 합니다. 다음 예제에서는 현재 선택한 구성에 대 한 *Cmakesettings. json* 파일의 `remoteCopySources` 키 값을 가져오는 간단한 *시작 및 json* 파일을 보여 줍니다.

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```

*시작 및 json* 파일을 저장 하면 Visual Studio가 **시작 항목** 드롭다운에서 새 이름에 대 한 항목을 만듭니다. 모든 수의 CMake 대상에 대해 여러 디버그 구성을 만들도록 *launch 및 json* 파일을 편집할 수 있습니다.

## <a name="launchvsjson-reference"></a>시작. json 참조 비교

모든 디버깅 시나리오를 지원 하기 위한 여러 가지 *시작 및 json* 속성이 있습니다. 다음 속성은 원격 및 로컬의 모든 디버그 구성에 공통적입니다.

- `projectTarget`: 프로젝트를 빌드할 때 호출할 Ctotarget을 지정 합니다. **디버그 > 디버그 및 $ {activeDebugTarget} 또는 대상 보기에 대 한 시작 설정에서 시작과** *json* 을 입력 하는 경우 Visual Studio에서이 속성을 autopopulates.

- `program`: 원격 시스템의 프로그램 실행 파일에 대 한 전체 경로입니다. 여기 `${debugInfo.fullTargetPath}` 매크로를 사용할 수 있습니다.

- `args`: 디버그할 프로그램에 전달 된 명령줄 인수입니다.

## <a name="launchvsjson-reference-for-remote-linux-projects"></a>원격 Linux 프로젝트에 대 한 시작 및 json 참조

다음 속성은 **원격 디버그 구성**에만 적용 됩니다. [사용자 지정 gdb 명령을 실행](https://github.com/microsoft/MIEngine/wiki/Executing-custom-gdb-lldb-commands) 하 여 기본 디버거로 명령을 직접 전송 하 고, [miengine 로깅을 사용](https://github.com/microsoft/MIEngine/wiki/Logging) 하 여 gdb로 전송 되는 명령, 출력 gdb에서 반환 하는 항목 및 각 명령에 걸리는 시간을 확인할 수도 있습니다.

- `cwd`: 원격 컴퓨터에서 종속성 및 기타 파일을 찾기 위한 현재 작업 디렉터리입니다. `${debugInfo.defaultWorkingDirectory}` 매크로를 사용할 수 있습니다. *Cmakelists*를 재정의 하지 않는 한 기본값은 원격 작업 영역 루트입니다. 이 속성은 원격 구성에만 사용 됩니다. `currentDir`는 로컬 프로젝트에 대해 시작 하는 앱의 현재 디렉터리를 설정 하는 데 사용 됩니다.

- `environment`:이 구문을 사용 하 여 프로그램 환경에 추가할 추가 환경 변수:

```json
  "environment": [
      {
        "name": "ENV1",
        "value": "envvalue1"
      },
      {
        "name": "ENV2",
        "value": "envvalue2"
      }
    ]
```

- `pipeArgs`: 연결을 구성 하기 위해 파이프 프로그램에 전달 되는 명령줄 인수입니다. 파이프 프로그램은 Visual Studio와 gdb 간에 표준 입력/출력을 릴레이 하는 데 사용 됩니다. `${debuggerCommand}` 명령은 원격 시스템에서 gdb를 시작 하 고 다음과 같이 수정할 수 있습니다.

  - Linux 시스템에 표시 되는 환경 변수 값을 내보냅니다. 다음 예제에서이 값은 `:1`입니다.

  ```json
  "pipeArgs": [
      "/s",
      "${debugInfo.remoteMachineId}",
      "/p",
      "${debugInfo.parentProcessId}",
      "/c",
      "export DISPLAY=:1;${debuggerCommand}",
      "--tty=${debugInfo.tty}"
    ],
  ```

  - Gdb를 실행 하기 전에 스크립트를 실행 합니다. 스크립트에 실행 권한이 설정 되어 있는지 확인 합니다.

    ```json
    "pipeArgs": [
        "/s",
        "${debugInfo.remoteMachineId}",
        "/p",
        "${debugInfo.parentProcessId}",
        "/c",
        "/path/to/script.sh;${debuggerCommand}",
        "--tty=${debugInfo.tty}"
      ],
    ```

- `stopOnEntry`: 프로세스가 시작 되는 즉시 중단할지 여부를 지정 하는 부울입니다. 기본값은 false입니다.

- `visualizerFile`:이 프로세스를 디버그할 때 사용할 [natvis 파일](/visualstudio/debugger/create-custom-views-of-native-objects) 입니다. 이 옵션은 gdb 예쁜 인쇄와 호환 되지 않습니다. 또한이 속성을 설정할 때 `showDisplayString` 설정 합니다.

- `showDisplayString`: `visualizerFile` 지정 된 경우 표시 문자열을 사용 하도록 설정 하는 부울입니다. 이 옵션을 `true`로 설정 하면 디버깅 하는 동안 성능이 저하 될 수 있습니다.

- `setupCommands`: 기본 디버거를 설정 하기 위해 실행할 하나 이상의 gdb 명령입니다.

- `externalConsole`: 디버기에 대해 콘솔이 시작 되는지 여부를 지정 하는 부울입니다.

- `miDebuggerPath`: gdb에 대 한 전체 경로입니다. 지정 하지 않으면 Visual Studio에서 디버거를 위해 먼저 경로를 검색 합니다.

::: moniker-end

::: moniker range="vs-2017"

- `remoteMachineName`: gdb를 호스트 하는 원격 Linux 시스템과 디버그할 프로그램입니다.

::: moniker-end

::: moniker range="vs-2019"

다음 속성을 사용 하 여 원격 **디버그 시스템과** **원격 빌드 시스템** 을 분리할 수 있습니다. 자세한 내용은 [빌드 및 디버깅을 위해 다른 컴퓨터 지정](../linux/deploy-run-and-debug-your-linux-project.md#cmake-projects)을 참조 하세요.

- `remoteMachineName`: gdb를 호스트 하는 원격 Linux 시스템과 디버그할 프로그램입니다. 이 항목은 *Cmakesettings. json*에 지정 된 빌드에 사용 된 원격 Linux 시스템과 일치할 필요가 없습니다. **Ctrl + Space** 를 눌러 [연결 관리자](../linux/connect-to-your-remote-linux-computer.md)에 저장 된 모든 원격 연결 목록을 표시 합니다.

- `disableDeploy`: 빌드/디버그 분리를 사용 하지 않도록 설정할지 여부를 나타냅니다. 사용 하도록 설정 하면이 기능을 사용 하 여 두 개의 개별 컴퓨터에서 빌드 및 디버그를 수행할 수 있습니다.

- `deployDirectory`: 원격 디버그 컴퓨터에서 실행 파일을 복사할 원격 디버그 컴퓨터의 디렉터리 (`remoteMachineName`로 지정 됨)입니다.

- `deploy`: 고급 배포 설정의 배열입니다. 배포 프로세스를 보다 세부적으로 제어 하려는 경우에만 이러한 설정을 구성 해야 합니다. 기본적으로 프로세스에서 디버그하는 데 필요한 파일만 원격 디버깅 머신에 배포됩니다.

  - `sourceMachine`: 파일이 나 디렉터리가 복사 될 컴퓨터입니다. **Ctrl + Space** 를 눌러 연결 관리자에 저장 된 모든 원격 연결 목록을 표시 합니다.

  - `targetMachine`: 파일이 나 디렉터리가 복사 될 컴퓨터입니다. **Ctrl + Space** 를 눌러 연결 관리자에 저장 된 모든 원격 연결 목록을 표시 합니다.

  - `sourcePath`: `sourceMachine`의 파일 또는 디렉터리 위치입니다.

  - `targetPath`: `targetMachine`의 파일 또는 디렉터리 위치입니다.

  - `deploymentType`: 배포 유형에 대 한 설명입니다. `LocalRemote` 및 `RemoteRemote` 지원 됩니다. `LocalRemote`은 로컬 파일 시스템에서 시작 `remoteMachineName`에 지정 된 원격 시스템으로 복사를 의미 합니다. *및 json*. `RemoteRemote`는 *Cmakesettings. json* 에 지정 된 원격 빌드 시스템에서 *시작 및 json*에 지정 된 다른 원격 시스템으로 복사를 의미 합니다.

  - `executable`: 배포 된 파일이 실행 파일 인지 여부를 나타냅니다.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="attach-to-a-remote-process"></a>원격 프로세스에 연결

디버거를 연결할 프로세스 ID로 `processId`을 설정 하 여 Linux 시스템에서 실행 되는 프로세스에 연결할 수 있습니다. 자세한 내용은 [GDB를 사용 하 여 프로세스에 연결 문제 해결](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB)을 참조 하세요.

::: moniker-end

::: moniker range="vs-2019"

## <a name="debug-on-linux-using-gdbserver"></a>Gdbserver를 사용 하 여 Linux에서 디버그

Visual Studio 2019 버전 16.5 Preview 1 이상은 gdbserver를 사용 하 여 CMake 프로젝트의 원격 디버깅을 지원 합니다. 자세한 내용은 [gdbserver를 사용 하 여 Linux cmake 프로젝트 디버그](https://devblogs.microsoft.com/cppblog/debugging-linux-cmake-projects-with-gdbserver/)를 참조 하세요.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="see-also"></a>참조

[Visual Studio의 cmake 프로젝트](cmake-projects-in-visual-studio.md)\
[Linux CMake 프로젝트 구성](../linux/cmake-linux-project.md)\
\ [원격 Linux 컴퓨터에 연결](../linux/connect-to-your-remote-linux-computer.md)
[Cmake 빌드 설정 사용자 지정](customize-cmake-settings.md)\
[Cmake 디버깅 세션\ 구성](configure-cmake-debugging-sessions.md)
[Linux 프로젝트 배포, 실행 및 디버그](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake 미리 정의된 구성 참조](cmake-predefined-configuration-reference.md)

::: moniker-end
