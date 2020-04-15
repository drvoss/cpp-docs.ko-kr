---
title: launch.vs.json 스키마 참조(C++)
ms.date: 08/20/2019
helpviewer_keywords:
- launch.vs.json file [C++]
ms.openlocfilehash: ff4713642ab95a9bbc31f1a06236de459e53f9c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323047"
---
# <a name="launchvsjson-schema-reference-c"></a>launch.vs.json 스키마 참조(C++)

*launch.vs.json* 파일을 사용하여 디버깅 매개 변수를 구성합니다. 파일을 만듭니다. **솔루션 탐색기에서** 실행 파일을 마우스 오른쪽 단추로 클릭하고 **디버그 및 시작 설정을**선택합니다. 프로젝트와 가장 밀접하게 일치하는 옵션을 선택한 다음 다음 속성을 사용하여 필요에 따라 구성을 수정합니다. CMake 프로젝트 디버깅에 대한 자세한 내용은 [CMake 디버깅 세션 구성을](/cpp/build/configure-cmake-debugging-sessions)참조하십시오.

## <a name="default-properties"></a>기본 속성

||||
|-|-|-|
|**속성**|**Type**|**설명**|
|`name`|문자열|디버그 대상 드롭다운에서 항목의 이름을 지정합니다.|
|`type`|문자열|프로젝트가 dll 또는 .exe인지 지정합니다(기본값 .exe)|
|`project`|문자열|프로젝트 파일에 대한 상대 경로를 지정합니다.|
|`projectTarget`|문자열|을 작성할 `project`때 호출되는 선택적 대상을 지정합니다. 이는 `projectTarget` 이미 존재해야 하며 **디버그 대상** 드롭다운의 이름과 일치해야 합니다.|
|`debugType`|문자열|코드 유형(기본, 관리 또는 혼합)에 따라 디버깅 모드를 지정합니다. 이 매개 변수가 설정되지 않으면 자동으로 검색됩니다. 허용된 값: "네이티브", "관리", "혼합".|
|`inheritEnvironments`|array|여러 소스에서 상속된 환경 변수 집합을 지정합니다. *CMakeSettings.json* 또는 *CppProperties.json과* 같은 파일에서 일부 변수를 정의하고 디버깅 컨텍스트에 사용할 수 있도록 할 수 있습니다.  **Visual Studio 16.4:** 구문을 사용하여 대상별로 환경 `env.VARIABLE_NAME` 변수를 지정합니다. 변수를 설정 해제하려면 변수를 "null"로 설정합니다.|
|`args`|array|시작된 프로그램에 전달된 명령줄 인수를 지정합니다.|
|`currentDir`|문자열|대상 빌드에 대한 전체 디렉터리 경로를 지정합니다. 이 매개 변수가 설정되지 않으면 자동으로 검색됩니다.|
|`noDebug`|boolean|시작된 프로그램을 디버깅할지 여부를 지정합니다. 이 매개 변수의 `false` 기본값은 지정하지 않은 경우입니다.|
|`stopOnEntry`|boolean|프로세스가 시작되고 디버거가 연결되는 즉시 중단할지 여부를 지정합니다. 이 매개 변수의 `false`기본값은 .|
|`remoteMachine`|문자열|프로그램이 시작되는 원격 컴퓨터의 이름을 지정합니다.|
|`env`|array| 사용자 지정 환경 변수의 키 값 목록을 지정합니다. env:{"myEnv":"myVal"}.|
|`portName`|문자열|실행 중인 프로세스에 연결할 때 포트 이름을 지정합니다.|
|`buildConfigurations`|array| 구성을 적용하기 위해 빌드 모드의 이름을 지정하는 키-값 쌍입니다. 예를 `Debug` 들어, `Release` 또는 선택된 빌드 모드에 따라 사용할 구성.

## <a name="c-linux-properties"></a>C ++ 리눅스 속성

||||
|-|-|-|
|**속성**|**Type**|**설명**|
|`program`|문자열|원격 컴퓨터에서 실행 가능한 프로그램 전체 경로입니다. CMake를 사용하는 경우 `${debugInfo.fullTargetPath}` 매크로를 이 필드의 값으로 사용할 수 있습니다.|
|`processId`|integer|디버거를 연결하는 프로세스 ID(옵션)입니다.|
|`sourceFileMap`|object|선택적 소스 파일 매핑이 디버그 엔진에 전달되었습니다. 형식: `{ "\<Compiler source location>": "\<Editor source location>" }` `{ "\<Compiler source location>": { "editorPath": "\<Editor source location>", "useForBreakpoints": true } }`또는 . 예: `{ "/home/user/foo": "C:\\foo" }` 또는 `{ "/home/user/foo": { "editorPath": "c:\\foo", "useForBreakpoints": true } }`. [소스 파일 맵 옵션을](#source_file_map_options)참조하십시오.|
|`additionalProperties`|문자열|소스 파일맵 옵션 중 하나입니다. 다음을 참조하세요.|
|`MIMode`|문자열|MIDebugEngine에 연결할 MI 지원 콘솔 디버거 의 유형을 나타냅니다. 허용된 값은 "gdb", "lldb"입니다.|
|`args`|array|명령줄 인수가 프로그램에 전달되었습니다.|
|`environment`|array|프로그램에 대한 환경에 추가할 환경 변수입니다. 예: [ { "이름": "오징어", "값": "조개" }|
|`targetArchitecture`|문자열|디버그기의 아키텍처입니다. 이 매개 변수가 설정되지 않으면 자동으로 검색됩니다. 허용된 값은 x86, 팔, arm64, 밉, x64, amd64, x86_64.|
|`visualizerFile`|문자열|이 프로세스를 디버깅할 때 사용할 .natvis 파일입니다. 이 옵션은 GDB 예쁜 인쇄와 호환되지 않습니다. 이 설정을 사용하는 경우 "showDisplayString"을 참조하십시오.|
|`showDisplayString`|boolean|시각화 도우미파일이 지정되면 표시문자열표시 문자열이 표시 문자열을 사용하도록 설정합니다. 이 옵션을 켜면 디버깅 중에 성능이 저하될 수 있습니다.|
|`remoteMachineName`|문자열|gdb와 디버깅 프로그램을 호스팅 원격 리눅스 기계. 새 Linux 머신을 추가하기 위해 연결 관리자를 사용합니다. CMake를 사용하는 경우 `${debugInfo.remoteMachineName}` 매크로를 이 필드의 값으로 사용할 수 있습니다.|
|`cwd`|문자열|원격 컴퓨터에서 대상의 작업 디렉토리입니다. CMake를 사용하는 경우 `${debugInfo.defaultWorkingDirectory}` 매크로를 이 필드의 값으로 사용할 수 있습니다. 기본값은 *CMakeLists.txt* 파일에서 재정의되지 않는 한 원격 작업 영역 루트입니다.|
|`miDebuggerPath`|문자열|MI 지원 디버거(예: gdb)에 대한 경로입니다. 지정되지 않은 경우 먼저 PATH에서 디버거를 검색합니다.|
|`miDebuggerServerAddress`|문자열|연결할 MI 지원 디버거 서버의 네트워크 주소입니다. 예: 로컬 호스트:1234.|
|`setupCommands`|array|기본 디버거를 설정하기 위해 하나 이상의 GDB/LLDB 명령을 실행합니다. 예: `"setupCommands": [ { "text": "-enable-pretty-printing", "description": "Enable GDB pretty printing", "ignoreFailures": true }]`. [설치 시작 명령을](#launch_setup_commands)참조하십시오.|
|`customLaunchSetupCommands`|array|제공된 경우 대상을 시작하는 데 사용되는 기본 명령을 다른 명령으로 대체합니다. 예를 들어 대상 프로세스에 연결하기 위해 "대상-연결"일 수 있습니다. 빈 명령 목록은 실행 명령을 아무 것도 대체하지 않습니다. 예: `"customLaunchSetupCommands": [ { "text": "target-run", "description": "run target", "ignoreFailures": false }]`.|
|`launchCompleteCommand`|문자열|디버거가 완전히 설정된 후 실행할 명령으로 대상 프로세스가 실행됩니다. 허용된 값은 "exec-run", "exec-continue", "없음"입니다. 기본값은 "exec-run"입니다.|
|`debugServerPath`|문자열|서버를 디버깅하는 전체 경로(옵션)를 시작합니다. 기본값은 null입니다.|
|`debugServerArgs`|문자열|옵션 디버그 서버 args. 기본값은 null입니다.|
|`filterStderr`|boolean|서버 시작 패턴에 대한 stderr 스트림을 검색하고 출력을 디버깅하기 위해 stderr를 로그 stderr합니다. 기본값은 `false`입니다.|
|`coreDumpPath`|문자열|지정된 프로그램에 대한 코어 덤프 파일에 대한 선택적 전체 경로입니다. 기본값은 null입니다.|
외부 콘솔|boolean|true이면 디버지에 대한 콘솔이 시작됩니다. 콘솔이 시작되지 않은 경우. `false` 기본값은 `false`입니다. 참고: 기술적인 이유로 이 옵션은 무시되는 경우도 있습니다.|
|`pipeTransport`|문자열|이 기능이 있는 경우 디버거가 다른 실행 프로그램을 사용하여 원격 컴퓨터에 연결하도록 지시하여 Visual Studio와 MI 지원 디버거(예: gdb) 간에 표준 입력/출력을 릴레이합니다. 허용된 값: 하나 이상의 [파이프 전송 옵션.](#pipe_transport_options)|

## <a name="launch-setup-commands"></a><a name="launch_setup_commands"></a>설정 명령 실행

`setupCommands` 속성과 함께 사용:

||||
|-|-|-|
|`text`|문자열|실행할 디버거 명령입니다.|
|`description`|문자열|명령에 대한 선택적 설명입니다.|
|`ignoreFailures`|boolean|true이면 명령의 오류를 무시해야 합니다. 기본값은 `false`입니다.|

## <a name="pipe-transport-options"></a><a name = "pipe_transport_options"></a>파이프 전송 옵션

`pipeTransport` 속성과 함께 사용:

||||
|-|-|-|
|`pipeCwd`|문자열|파이프 프로그램의 작업 디렉토리에 대한 정규화된 경로입니다.|
|`pipeProgram`|문자열|실행할 정규화된 파이프 명령입니다.|
|`pipeArgs`|array|연결을 구성하기 위해 파이프 프로그램에 전달된 명령줄 인수입니다.|
|`debuggerPath`|문자열|대상 컴퓨터에서 디버거에 대한 전체 경로(예: /usr/bin/gdb)입니다.|
|`pipeEnv`|object|파이프 프로그램에 전달된 환경 변수입니다.|
|`quoteArgs`|boolean|개별 인수에 문자(예: 공백 또는 탭)가 포함된 경우 따옴표로 지정해야 합니까? 을 `false`선택하면 디버거 명령이 더 이상 자동으로 인용되지 않습니다. 기본값은 `true`입니다.|

## <a name="source-file-map-options"></a><a name="source_file_map_options"></a>소스 파일 맵 옵션

`sourceFileMap` 속성과 함께 사용:

||||
|-|-|-|
|`editorPath`|문자열|편집기에서 찾을 소스 코드의 위치입니다.|
|`useForBreakpoints`|boolean|중단점을 설정할 때 이 소스 매핑을 사용해야 합니다. 파일 `false`이름과 줄 번호만 사용하여 중단점을 설정합니다. 이 `true`소스 매핑을 사용하는 경우에만 파일 및 줄 번호에 대한 전체 경로로 중단점이 설정됩니다. 그렇지 않으면 중단점을 설정할 때 파일 이름과 줄 번호만 사용됩니다. 기본값은 `true`입니다.|
