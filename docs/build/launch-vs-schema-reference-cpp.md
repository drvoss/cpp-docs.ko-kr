---
title: launch. vs json 스키마 참조 (C++)
ms.date: 08/20/2019
helpviewer_keywords:
- launch.vs.json file [C++]
ms.openlocfilehash: 5d8f657dda58d581ccc3441a777fdf31470ef25f
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518233"
---
# <a name="launchvsjson-schema-reference-c"></a>launch. vs json 스키마 참조 (C++)

*실행과 json* 파일을 사용 하 여 디버깅 매개 변수를 구성 합니다. 파일을 만듭니다. **솔루션 탐색기** 에서 실행 파일을 마우스 오른쪽 단추로 클릭 하 고 **디버그 및 시작 설정**을 선택 합니다. 프로젝트와 가장 가깝게 일치 하는 옵션을 선택한 후 다음 속성을 사용 하 여 필요에 따라 구성을 수정 합니다. Cmake 프로젝트 디버깅에 대 한 자세한 내용은 [Cmake 디버깅 세션 구성](/cpp/build/configure-cmake-debugging-sessions)을 참조 하세요.

## <a name="default-properties"></a>기본 속성

||||
|-|-|-|
|**Property**|**Type**|**설명**|
|`name`|string|디버그 대상 드롭다운에서 항목의 이름을 지정 합니다.|
|`type`|string|프로젝트가 dll 또는 .exe 인지 여부를 지정 합니다 (기본값은 .exe).|
|`project`|string|프로젝트 파일에 대 한 상대 경로를 지정 합니다.|
|`projectTarget`|string|`project`를 빌드할 때 호출 되는 선택적 대상을 지정 합니다. 이 `projectTarget` 이미 존재 하 고 **디버그 대상** 드롭다운에서 이름과 일치 해야 합니다.|
|`debugType`|string|코드 형식 (네이티브, 관리 또는 혼합)에 따라 디버깅 모드를 지정 합니다. 이 매개 변수를 설정 하지 않으면 자동으로 검색 됩니다. 허용 되는 값: "native", "managed", "mixed".|
|`inheritEnvironments`|배열입니다.|여러 원본에서 상속 되는 환경 변수 집합을 지정 합니다. *Cmakesettings. json* 또는 *cppproperties.json* 와 같은 파일에 일부 변수를 정의 하 고이를 디버그 컨텍스트에 사용할 수 있도록 설정할 수 있습니다.  **Visual Studio 16.4:** : `env.VARIABLE_NAME` 구문을 사용 하 여 대상 별로 환경 변수를 지정 합니다. 변수를 설정 해제 하려면 변수를 "null"로 설정 합니다.|
|`args`|배열입니다.|시작 된 프로그램에 전달 되는 명령줄 인수를 지정 합니다.|
|`currentDir`|string|빌드 대상의 전체 디렉터리 경로를 지정 합니다. 이 매개 변수를 설정 하지 않으면 자동으로 검색 됩니다.|
|`noDebug`|boolean|시작 된 프로그램을 디버그할 지 여부를 지정 합니다. 지정 하지 않으면이 매개 변수의 기본값은 `false`입니다.|
|`stopOnEntry`|boolean|프로세스가 시작 되 고 디버거가 연결 될 때 곧 중단 되는지 여부를 지정 합니다. 이 매개 변수의 기본값은 `false`입니다.|
|`remoteMachine`|string|프로그램이 시작 되는 원격 컴퓨터의 이름을 지정 합니다.|
|`env`|배열입니다.| 사용자 지정 환경 변수의 키-값 목록을 지정 합니다. env: {"myEnv": "Myenv"}.|
|`portName`|string|실행 중인 프로세스에 연결할 때의 포트 이름을 지정 합니다.|
|`buildConfigurations`|배열입니다.| 구성을 적용할 빌드 모드의 이름을 지정 하는 키-값 쌍입니다. 예를 들어 `Debug` 또는 `Release` 선택한 빌드 모드에 따라 사용할 구성입니다.

## <a name="c-linux-properties"></a>C++Linux 속성

||||
|-|-|-|
|**Property**|**Type**|**설명**|
|`program`|string|원격 컴퓨터의 프로그램 실행 파일에 대 한 전체 경로입니다. CMake를 사용 하는 경우이 필드의 값으로 `${debugInfo.fullTargetPath}` 매크로를 사용할 수 있습니다.|
|`processId`|정수|디버거를 연결할 선택적 프로세스 ID입니다.|
|`sourceFileMap`|개체|디버그 엔진에 전달 되는 선택적 소스 파일 매핑입니다. Format: `{ "\<Compiler source location>": "\<Editor source location>" }` 또는 `{ "\<Compiler source location>": { "editorPath": "\<Editor source location>", "useForBreakpoints": true } }`. 예: `{ "/home/user/foo": "C:\\foo" }` 또는 `{ "/home/user/foo": { "editorPath": "c:\\foo", "useForBreakpoints": true } }`. [소스 파일 맵 옵션](#source_file_map_options)을 참조 하세요.|
|`additionalProperties`|string|SourceFileMapOptions 중 하나입니다. 다음을 참조하세요.|
|`MIMode`|string|MIDebugEngine이 연결할 MI 사용 콘솔 디버거의 유형을 나타냅니다. 허용 되는 값은 "gdb", "lldb"입니다.|
|`args`|배열입니다.|프로그램에 전달 된 명령줄 인수입니다.|
|`environment`|배열입니다.|프로그램 환경에 추가할 환경 변수입니다. 예: [{"name": "squid", "value": "clam"}].|
|`targetArchitecture`|string|디버기의 아키텍처입니다. 이 매개 변수를 설정 하지 않으면 자동으로 검색 됩니다. 허용 되는 값은 x86, arm, arm64, mips, x64, amd64, x86_64입니다.|
|`visualizerFile`|string|이 프로세스를 디버그할 때 사용할 natvis 파일입니다. 이 옵션은 GDB 예쁜 인쇄와 호환 되지 않습니다. 이 설정을 사용 하는 경우 "showDisplayString"을 참조 하세요.|
|`showDisplayString`|boolean|VisualizerFile가 지정 되 면 showDisplayString에서 표시 문자열을 사용 하도록 설정 합니다. 이 옵션을 설정 하면 디버깅 하는 동안 성능이 저하 될 수 있습니다.|
|`remoteMachineName`|string|Gdb를 호스팅하는 원격 Linux 컴퓨터와 디버그할 프로그램입니다. 새 Linux 머신을 추가하기 위해 연결 관리자를 사용합니다. CMake를 사용 하는 경우이 필드의 값으로 `${debugInfo.remoteMachineName}` 매크로를 사용할 수 있습니다.|
|`cwd`|string|원격 컴퓨터에 있는 대상의 작업 디렉터리입니다. CMake를 사용 하는 경우이 필드의 값으로 `${debugInfo.defaultWorkingDirectory}` 매크로를 사용할 수 있습니다. *Cmakelists* 파일에 재정의 되지 않은 경우 기본값은 원격 작업 영역 루트입니다.|
|`miDebuggerPath`|string|MI 사용 디버거의 경로 (예: gdb)입니다. 지정 하지 않으면 디버거의 경로가 먼저 검색 됩니다.|
|`miDebuggerServerAddress`|string|연결할 MI 사용 디버거 서버의 네트워크 주소입니다. 예: localhost: 1234|
|`setupCommands`|배열입니다.|기본 디버거를 설정 하기 위해 실행할 하나 이상의 GDB/LLDB 명령입니다. 예를 들어, `"setupCommands": [ { "text": "-enable-pretty-printing", "description": "Enable GDB pretty printing", "ignoreFailures": true }]` 같은 형식입니다. [설치 명령 시작](#launch_setup_commands)을 참조 하세요.|
|`customLaunchSetupCommands`|배열입니다.|제공 된 경우 대상을 시작 하는 데 사용 되는 기본 명령을 다른 명령으로 바꿉니다. 예를 들어 대상 프로세스에 연결 하기 위해 "-target-attach" 일 수 있습니다. 빈 명령 목록에는 launch 명령이 포함 된 것으로 대체 됩니다 .이는 디버거가 명령줄 옵션으로 시작 옵션을 제공 하는 경우에 유용할 수 있습니다. 예를 들어, `"customLaunchSetupCommands": [ { "text": "target-run", "description": "run target", "ignoreFailures": false }]` 같은 형식입니다.|
|`launchCompleteCommand`|string|디버거가 완전히 설정 된 후 실행 하 여 대상 프로세스를 실행 하는 명령입니다. 허용 되는 값은 "exec-run", "exec-continue", "None"입니다. 기본값은 "exec-run"입니다.|
|`debugServerPath`|string|시작할 디버그 서버에 대 한 선택적 전체 경로입니다. 기본값은 null입니다.|
|`debugServerArgs`|string|선택적 디버그 서버 인수입니다. 기본값은 null입니다.|
|`filterStderr`|boolean|서버에서 시작한 패턴에 대해 stderr 스트림을 검색 하 고 디버그 출력에 stderr을 기록 합니다. 기본값은 `false`입니다.|
|`coreDumpPath`|string|지정 된 프로그램의 코어 덤프 파일에 대 한 선택적 전체 경로입니다. 기본값은 null입니다.|
externalConsole|boolean|True 이면 디버기에 대해 콘솔이 시작 됩니다. `false`경우 콘솔이 시작 되지 않습니다. 기본값은 `false`입니다. 참고: 일부 경우에는 기술적인 이유로이 옵션을 무시 합니다.|
|`pipeTransport`|string|이 경우 디버거가 다른 실행 파일을 사용 하 여 원격 컴퓨터에 연결 하 고 Visual Studio와 MI 지원 디버거 (예: gdb) 간에 표준 입력/출력을 릴레이 하는 파이프로 연결 합니다. 허용 되는 값: 하나 이상의 [파이프 전송 옵션](#pipe_transport_options)입니다.|


## <a name="launch_setup_commands"></a>설치 명령 시작

`setupCommands` 속성과 함께 사용 됩니다.

||||
|-|-|-|
|`text`|string|실행할 디버거 명령입니다.|
|`description`|string|명령에 대 한 선택적 설명입니다.|
|`ignoreFailures`|boolean|True 이면 명령의 오류가 무시 됩니다. 기본값은 `false`입니다.|

## <a name = "pipe_transport_options"></a>파이프 전송 옵션

`pipeTransport` 속성과 함께 사용 됩니다.

||||
|-|-|-|
|`pipeCwd`|string|파이프 프로그램의 작업 디렉터리에 대 한 정규화 된 경로입니다.|
|`pipeProgram`|string|실행할 정규화 된 파이프 명령입니다.|
|`pipeArgs`|배열입니다.|연결을 구성 하기 위해 파이프 프로그램에 전달 되는 명령줄 인수입니다.|
|`debuggerPath`|string|대상 컴퓨터에 있는 디버거의 전체 경로 (예:/usr/bin/gdb.)|
|`pipeEnv`|개체|파이프 프로그램에 전달 되는 환경 변수입니다.|
|`quoteArgs`|boolean|개별 인수에 공백이 나 탭과 같은 문자를 포함 하는 경우 따옴표로 묶어야 하나요? `false`경우 디버거 명령이 더 이상 자동으로 따옴표로 묶여 있지 않습니다. 기본값은 `true`입니다.|

## <a name="source_file_map_options"></a>원본 파일 맵 옵션

`sourceFileMap` 속성과 함께 사용 합니다.

||||
|-|-|-|
|`editorPath`|string|편집기에서 찾을 소스 코드의 위치입니다.|
|`useForBreakpoints`|boolean|중단점을 설정 하는 경우이 소스 매핑을 사용 해야 합니다. `false`경우 중단점을 설정 하는 데 파일 이름과 줄 숫자만 사용 됩니다. `true`경우이 소스 매핑을 사용 하는 경우에만 파일의 전체 경로와 줄 번호를 사용 하 여 중단점이 설정 됩니다. 그렇지 않은 경우 중단점을 설정할 때 파일 이름 및 줄 번호를 사용 합니다. 기본값은 `true`입니다.|
