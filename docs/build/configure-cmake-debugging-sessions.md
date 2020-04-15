---
title: Visual Studio에서 CMake 디버깅 세션 구성
description: Visual Studio를 사용하여 CMake 디버거 설정을 구성하는 방법을 설명합니다.
ms.date: 04/02/2020
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 8364e5b3dd3316a4ed7e754a104a14373040aa6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328830"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake 디버깅 세션 구성

::: moniker range="vs-2015"

네이티브 CMake 지원은 Visual Studio 2017 이상에서 사용할 수 있습니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end

::: moniker range=">=vs-2017"

실행 가능한 모든 CMake 대상은 **일반** 도구 모음의 **시작 항목** 드롭다운에 표시됩니다. 디버깅 세션을 시작하고 디버거를 시작하려면 하나를 선택합니다.

![CMake 시작 항목 드롭다운](media/cmake-startup-item-dropdown.png "CMake 시작 항목 드롭다운")

솔루션 탐색기에서 디버그 세션을 시작할 수도 있습니다. 먼저 **솔루션 탐색기** 창에서 **CMake 대상 보기로** 전환합니다.

![CMake 대상 보기 단추](media/cmake-targets-view.png  "CMake 대상 보기 메뉴 항목")

그런 다음 실행 을 마우스 오른쪽 단추로 클릭하고 **디버그**를 선택합니다. 이 명령은 활성 구성에 따라 선택한 대상디버깅을 자동으로 시작합니다.

## <a name="customize-debugger-settings"></a>디버거 설정 사용자 지정

프로젝트의 실행 가능한 CMake 대상에 대해 디버거 설정을 사용자 지정할 수 있습니다. 프로젝트 루트의 *`.vs`* 폴더에 있는 *launch.vs.json이라는*구성 파일에서 찾을 수 있습니다. 시작 구성 파일은 디버깅 설정 세부 정보를 구성하고 저장할 수 있으므로 대부분의 디버깅 시나리오에서 유용합니다. 이 파일에는 세 가지 진입점이 있습니다.

- **디버그 메뉴:** 기본 메뉴에서 **디버그 > 디버그 및 시작 설정을 기본** 메뉴에서 선택하여 활성 디버그 대상에 특정한 디버그 구성을 사용자 지정합니다. 디버그 대상이 선택되어 있지 않으면 이 옵션은 회색으로 표시됩니다.

![디버그 메뉴 진입점](media/cmake-debug-menu.png "디버그 메뉴 진입점")

- **대상 보기:** 솔루션 탐색기에서 **대상 보기로** 이동합니다. 그런 다음 디버그 대상을 마우스 오른쪽 단추로 클릭하고 **디버그 구성 추가를** 선택하여 선택한 대상에 특정한 디버그 구성을 사용자 지정합니다.

![대상 뷰 진입점](media/cmake-targets-add-debug-configuration.png "대상 뷰 진입점")

- **루트 CMakeLists.txt:** 루트 *CMakeLists.txt를* 마우스 오른쪽 단추로 클릭하고 **디버그 구성 추가를** 선택하여 **디버거** 선택 대화 상자를 엽니다. 대화 상자를 사용하면 *모든* 유형의 디버그 구성을 추가할 수 있지만 `projectTarget` 속성을 통해 호출할 CMake 대상을 수동으로 지정해야 합니다.

![디버거 대화 상자 선택](media/cmake-select-a-debugger.png "디버거 대화 상자 선택")

*launch.vs.json* 파일을 편집하여 원하는 수의 CMake 대상에 대한 디버그 구성을 만들 수 있습니다. 파일을 저장하면 Visual Studio는 **시작 항목** 드롭다운에서 각 새 구성에 대한 항목을 만듭니다.

## <a name="reference-keys-in-cmakesettingsjson"></a>CMakeSettings.json의 참조 키

*CMakeSettings.json* 파일의 키를 참조하려면 `cmake.` *launch.vs.json에서*키를 준비합니다. 다음 예제에서는 현재 선택된 구성에 대한 *CMakeSettings.json* 파일의 `remoteCopySources` 키 값을 가져오는 간단한 *launch.vs.json* 파일을 보여 주며, 이 파일은 다음과 같은 작업을 수행합니다.

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

*CMakeSettings.json에* 정의된 환경 `${env.VARIABLE_NAME}` **변수는** 구문을 사용하여 launch.vs.json에서도 사용할 수 있습니다. Visual Studio 2019 버전 16.4 이상에서는 *CMakeSettings.json*에서 지정한 환경을 사용하여 디버그 대상이 자동으로 시작됩니다. 환경 변수를 **null로**설정하여 환경 변수를 해제할 수 있습니다.

## <a name="launchvsjson-reference"></a>시작 및 json 참조

모든 디버깅 시나리오를 지원하기 위해 많은 *launch.vs.json* 속성이 있습니다. 다음 속성은 원격 및 로컬 모두 모든 디버그 구성에 공통적입니다.

- `projectTarget`: 프로젝트를 빌드할 때 호출할 CMake 대상을 지정합니다. **디버그 메뉴** 또는 **대상 보기에서** *launch.vs.json을* 입력하면 Visual Studio에서 이 속성을 자동으로 채웁니다. 이 값은 **시작 항목** 드롭다운에 나열된 기존 디버그 대상의 이름과 일치해야 합니다.

- `env`: 구문을 사용하여 추가할 추가 환경 변수:

  ```json
  "env": {
        "DEBUG_LOGGING_LEVEL": "trace;info",
        "ENABLE_TRACING": "true"
      }
  ```

- `args`: 명령줄 인수가 디버깅을 위해 프로그램에 전달되었습니다.

## <a name="launchvsjson-reference-for-remote-projects-and-wsl"></a>원격 프로젝트 및 WSL에 대한 Launch.vs.json 참조

Visual Studio 2019 버전 16.6에서는 원격 시스템 `type: cppgdb` 및 WSL에서 디버깅을 단순화하기 위한 새로운 디버그 구성을 추가했습니다. 이전 `type: cppdbg` 디버그 구성은 여전히 지원됩니다.

### <a name="configuration-type-cppgdb"></a>구성 유형`cppgdb`

- `name`: **시작 항목** 드롭다운에서 구성을 식별하는 친숙한 이름입니다.
- `project`: 프로젝트 파일에 대한 상대 경로를 지정합니다. 일반적으로 CMake 프로젝트를 디버깅할 때 이 경로를 변경할 필요가 없습니다.
- `projectTarget`: 프로젝트를 빌드할 때 호출할 CMake 대상을 지정합니다. **디버그 메뉴** 또는 **대상 보기에서** *launch.vs.json을* 입력하면 Visual Studio에서 이 속성을 자동으로 채웁니다. 이 대상 값은 **시작 항목** 드롭다운에 나열된 기존 디버그 대상의 이름과 일치해야 합니다.
- `debuggerConfiguration`: 사용할 디버깅 기본값 집합을 나타냅니다. Visual Studio 2019 버전 16.6에서 유일한 `gdb`유효한 옵션은 . 이전 버전도 `gdbserver`지원합니다.
- `args`: 명령줄 인수가 디버깅되는 프로그램에 시작 시 전달되었습니다.
- `env`: 디버깅 중인 프로그램에 전달된 추가 환경 변수입니다. `{"DISPLAY": "0.0"}`)을 입력합니다.
- `processID`: 리눅스 프로세스 ID에 부착할 수 있습니다. 원격 프로세스에 연결할 때만 사용됩니다. 자세한 내용은 [GDB를 사용하여 프로세스에 연결하는 문제 해결을](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB)참조하십시오.

#### <a name="additional-options-for-the-gdb-configuration"></a>`gdb` 구성에 대한 추가 옵션

- `program`: 기본값 `"${debugInfo.fullTargetPath}"`. 디버깅할 응용 프로그램에 대한 유닉스 경로입니다. 빌드 또는 배포 위치에서 실행 되는 대상 실행 하는 경우 다른 경우에만 필요합니다.
- `remoteMachineName`: 기본값 `"${debugInfo.remoteMachineName}"`. 디버깅할 프로그램을 호스팅하는 원격 시스템의 이름입니다. 빌드 시스템과 다른 경우에만 필요합니다. [연결 관리자](../linux/connect-to-your-remote-linux-computer.md)에 기존 항목이 있어야 합니다. **Ctrl+Space를** 눌러 모든 기존 원격 연결 목록을 봅니다.
- `cwd`: 기본값 `"${debugInfo.defaultWorkingDirectory}"`. 실행되는 원격 시스템의 디렉터리로 가는 유닉스 `program` 경로입니다. 디렉터리가 있어야 합니다.
- `gdbpath`: 기본값 `/usr/bin/gdb`. 디버깅하는 `gdb` 데 사용되는 전체 유닉스 경로입니다. 의 사용자 지정 버전을 `gdb`사용하는 경우에만 필요합니다.
- `preDebugCommand`: Linux 명령을 호출하기 직전에 `gdb`실행합니다. `gdb`명령이 완료될 때까지 시작되지 않습니다. 이 옵션을 사용하여 `gdb`을 실행하기 전에 스크립트를 실행할 수 있습니다.

#### <a name="deployment-options"></a>배포 옵션

다음 옵션을 사용하여 빌드 컴퓨터(CMakeSettings.json에 정의)를 원격 디버그 컴퓨터와 분리합니다.

- `remoteMachineName`: 원격 디버그 머신. 빌드 컴퓨터와 다른 경우에만 필요합니다. [연결 관리자](../linux/connect-to-your-remote-linux-computer.md)에 기존 항목이 있어야 합니다. **Ctrl+Space를** 눌러 모든 기존 원격 연결 목록을 봅니다.
- `disableDeploy`: 기본값 `false`. 빌드/디버그 분리를 사용할 수 있는지 여부를 나타냅니다. 이 `false`옵션을 사용하면 두 개의 개별 컴퓨터에서 빌드 및 디버그가 발생할 수 있습니다.
- `deployDirectory`: 실행 할 수 있는 `remoteMachineName` 디렉터리로 의한 전체 유닉스 경로가 복사됩니다.
- `deploy`: 고급 배포 설정의 배열입니다. 배포 프로세스를 보다 세밀하게 제어하려는 경우에만 이러한 설정을 구성해야 합니다. 기본적으로 디버깅 프로세스에 필요한 파일만 원격 디버그 컴퓨터에 배포됩니다.
  - `sourceMachine`: 파일 또는 디렉터리가 복사되는 컴퓨터입니다. **Ctrl+Space를** 눌러 연결 관리자에 저장된 모든 원격 연결 목록을 봅니다. WSL을 기본적으로 빌드할 때이 옵션은 무시 됩니다.
  - `targetMachine`: 파일 또는 디렉터리가 복사되는 컴퓨터입니다. **Ctrl+Space를** 눌러 연결 관리자에 저장된 모든 원격 연결 목록을 봅니다.
  - `sourcePath`: 의 `sourceMachine`파일 또는 디렉터리 위치
  - `targetPath`: 의 `targetMachine`파일 또는 디렉터리 위치
  - `deploymentType`: 배포 유형에 대한 설명입니다. `LocalRemote`지원됩니다. `RemoteRemote` `LocalRemote``remoteMachineName` *런치.vs.json에서*지정한 원격 시스템으로 로컬 파일 시스템에서 복사하는 것을 의미합니다. `RemoteRemote`*CMakeSettings.json에* 지정된 원격 빌드 시스템에서 *launch.vs.json에*지정된 다른 원격 시스템으로 복사하는 것을 의미합니다.
  - `executable`: 배포된 파일이 실행 파일인지 여부를 나타냅니다.

### <a name="execute-custom-gdb-commands"></a>사용자 `gdb` 지정 명령 실행

Visual Studio는 기본 디버거와 직접 상호 작용하는 사용자 지정 `gdb` 명령 실행을 지원합니다. 자세한 내용은 [사용자 지정 `gdb` lldb 명령 실행](https://github.com/microsoft/MIEngine/wiki/Executing-custom-gdb-lldb-commands)을 참조하십시오.

### <a name="enable-logging"></a>로깅 사용

MIEngine 로깅을 사용하여 전송되는 `gdb`명령, `gdb` 반환되는 출력 및 각 명령의 소요 시간을 확인합니다. [자세히](https://github.com/microsoft/MIEngine/wiki/Logging)

### <a name="configuration-type-cppdbg"></a>구성 유형`cppdbg`

`cppdbg` 구성 유형을 사용하여 원격 시스템 또는 WSL에서 디버깅할 때 다음 옵션을 사용할 수 있습니다. Visual Studio 2019 버전 16.6 이상에서는 구성 유형을 `cppgdb` 권장합니다.

- `name`: **시작 항목** 드롭다운에서 구성을 식별하는 친숙한 이름입니다.

- `project`: 프로젝트 파일에 대한 상대 경로를 지정합니다. 일반적으로 CMake 프로젝트를 디버깅할 때 이 값을 변경할 필요가 없습니다.

- `projectTarget`: 프로젝트를 빌드할 때 호출할 CMake 대상을 지정합니다. **디버그 메뉴** 또는 **대상 보기에서** *launch.vs.json을* 입력하면 Visual Studio에서 이 속성을 자동으로 채웁니다. 이 값은 **시작 항목** 드롭다운에 나열된 기존 디버그 대상의 이름과 일치해야 합니다.

- `args`: 명령줄 인수가 디버깅되는 프로그램에 시작 시 전달되었습니다.

- `processID`: 리눅스 프로세스 ID에 부착할 수 있습니다. 원격 프로세스에 연결할 때만 사용됩니다. 자세한 내용은 [GDB를 사용하여 프로세스에 연결하는 문제 해결을](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB)참조하십시오.

- `program`: 기본값 `"${debugInfo.fullTargetPath}"`. 디버깅할 응용 프로그램에 대한 유닉스 경로입니다. 빌드 또는 배포 위치에서 실행 되는 대상 실행 하는 경우 다른 경우에만 필요합니다.

- `remoteMachineName`: 기본값 `"${debugInfo.remoteMachineName}"`. 디버깅할 프로그램을 호스팅하는 원격 시스템의 이름입니다. 빌드 시스템과 다른 경우에만 필요합니다. [연결 관리자](../linux/connect-to-your-remote-linux-computer.md)에 기존 항목이 있어야 합니다. **Ctrl+Space를** 눌러 모든 기존 원격 연결 목록을 봅니다.

- `cwd`: 기본값 `"${debugInfo.defaultWorkingDirectory}"`. 실행되는 원격 시스템의 디렉터리로 의전체 `program` 유닉스 경로입니다. 디렉터리가 있어야 합니다.

- `environment`: 디버깅 중인 프로그램에 전달된 추가 환경 변수입니다. 예를 들면 다음과 같습니다.

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

- `pipeArgs`: 연결을 구성하기 위해 파이프 프로그램에 전달된 명령줄 인수의 배열입니다. 파이프 프로그램은 Visual Studio와. `gdb` CMake 프로젝트를 디버깅할 때 대부분의 이 배열을 **사용자 지정할 필요가 없습니다.** 원격 시스템에서 `${debuggerCommand}`시작되는 `gdb` 은 에서 는 예외입니다. 다음으로 수정할 수 있습니다.

  - Linux 시스템에서 환경 변수 DISPLAY값을 내보냅니다. 다음 예제에서 이 값은 `:1`은

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

  - 을 실행하기 전에 `gdb`스크립트를 실행합니다. 스크립트에서 실행 권한이 설정되어 있는지 확인합니다.

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

- `stopOnEntry`: 프로세스가 시작되는 즉시 중단 여부를 지정하는 부울입니다. 기본값은 false입니다.

- `visualizerFile`: 이 프로세스를 디버깅할 때 사용할 [.natvis 파일입니다.](/visualstudio/debugger/create-custom-views-of-native-objects) 이 옵션은 예쁜 `gdb` 인쇄와 호환되지 않습니다. 또한 `showDisplayString` 이 속성을 설정할 때 설정합니다.

- `showDisplayString`: 를 지정할 때 표시 `visualizerFile` 문자열을 활성화하는 부울입니다. 이 옵션을 `true` 설정하면 디버깅 중에 성능이 저하될 수 있습니다.

- `setupCommands`: 하나 `gdb` 이상의 명령을 실행하여 기본 디버거를 설정합니다.

- `miDebuggerPath`: 에 대한 `gdb`전체 경로. 지정되지 않은 경우 Visual Studio는 먼저 PATH에서 디버거를 검색합니다.

- 마지막으로 `cppgdb` 구성 유형에 대해 정의된 모든 배포 옵션을 구성 `cppdbg` 유형에서도 사용할 수 있습니다.

### <a name="debug-using-gdbserver"></a>사용 디버그`gdbserver`

을 사용하여 `gdbserver` `cppdbg` 디버깅하도록 구성을 구성할 수 있습니다. 에 대한 자세한 내용과 샘플 시작 구성은 Microsoft C++ 팀 블로그 포스트 [디버깅 Linux `gdbserver`CMake 프로젝트에서 ](https://devblogs.microsoft.com/cppblog/debugging-linux-cmake-projects-with-gdbserver/)찾을 수 있습니다.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="see-also"></a>참고 항목

[비주얼 스튜디오에서 CMake 프로젝트](cmake-projects-in-visual-studio.md)\
[Linux CMake 프로젝트 구성](../linux/cmake-linux-project.md)\
[원격 리눅스 컴퓨터에 연결](../linux/connect-to-your-remote-linux-computer.md)\
[CMake 빌드 설정 사용자 지정](customize-cmake-settings.md)\
[CMake 디버깅 세션 구성](configure-cmake-debugging-sessions.md)\
[Linux 프로젝트를 배포, 실행 및 디버깅](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake 미리 정의된 구성 참조](cmake-predefined-configuration-reference.md)

::: moniker-end
