---
title: CMakeSettings.json 스키마 참조
ms.date: 11/22/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: fb7dc81648ae301962b952b0440d8a24b397c0d8
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518207"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json 스키마 참조

::: moniker range="vs-2015"

CMake 프로젝트는 Visual Studio 2017 이상에서 지원 됩니다.

::: moniker-end

::: moniker range=">=vs-2017"

**Cmakesettings. json** 파일에는 Visual Studio에서 IntelliSense에 사용 하는 정보가 포함 되어 있으며, 지정 된 *구성* 및 컴파일러 *환경*에 대해 cmage.exe에 전달 하는 명령줄 인수를 생성 합니다. 구성에서는 특정 플랫폼 및 빌드 형식 (예: `x86-Debug` 또는 `Linux-Release`에 적용 되는 속성을 지정 합니다. 각 구성은 컴파일러 도구 집합에 대 한 정보 (예: MSVC, GCC 또는 Clang)를 캡슐화 하는 환경을 지정 합니다. CMake는 명령줄 인수를 사용 하 여 프로젝트에 대 한 루트 *cmakecache.txt* 파일 및 기타 프로젝트 파일을 다시 생성 합니다. *Cmakelists .txt* 파일에서 값을 재정의할 수 있습니다. 

IDE에서 구성을 추가 하거나 제거한 다음 JSON 파일에서 직접 편집 하거나 **Cmake 설정 편집기** (Visual Studio 2019 이상)를 사용할 수 있습니다. IDE에서 구성 간을 쉽게 전환 하 여 다양 한 프로젝트 파일을 생성할 수 있습니다. 자세한 내용은 [Visual Studio에서 cmake 빌드 설정 사용자 지정](customize-cmake-settings.md) 을 참조 하세요.

## <a name="configurations"></a>구성

`configurations` 배열에는 CMake의 모든 구성이 포함 됩니다. 미리 정의 된 구성에 대 한 자세한 내용은 [미리 정의 된 Cmake 구성 참조](cmake-predefined-configuration-reference.md) 를 참조 하세요. 파일에 미리 정의 된 구성 또는 사용자 지정 구성을 원하는 개수 만큼 추가할 수 있습니다. 

`configuration`에는 다음과 같은 속성이 있습니다.

- `addressSDanitizerEnabled`: `true` Sanitizer (Windows에서 실험적) 주소를 사용 하 여 프로그램을 컴파일합니다. Linux에서 최상의 결과를 위해-fno-프레임 포인터 및 컴파일러 최적화 수준-Os 또는-Oo를 사용 하 여 컴파일합니다.
- `addressSanitizerRuntimeFlags`: ASAN_OPTIONS 환경 변수를 통해 AddressSanitizer에 전달 된 런타임 플래그입니다. Format: 플래그 1 = 값: 플래그 2 = value2
- `buildCommandArgs`: --빌드 -- 후 CMake로 전달되는 네이티브 빌드 스위치를 지정합니다. 예를 들어 Ninja 생성기를 사용하는 경우 -v를 전달하면 Ninja에서 명령줄을 출력하도록 강제합니다. Ninja 명령에 대한 자세한 정보는 [Ninja 명령줄 인수](#ninja)를 참조하세요.
- `buildRoot`: CMake가 선택한 생성기에 대한 빌드 스크립트를 생성하는 디렉터리를 지정합니다.  **-DCMAKE_BINARY_DIR** 스위치에 매핑되고 *cmakecache.txt* 를 만들 위치를 지정 합니다. 폴더가 없으면 해당 폴더가 만들어집니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다.
- `cacheGenerationCommand`: 캐시를 생성 하는 명령줄 도구 및 인수 (예: *gencache debug* )를 지정 합니다. 사용자가 다시 생성을 명시적으로 요청 하는 경우 구성에 대해 지정 된 환경의 셸에서 명령이 실행 되거나 CMakeLists 또는 Cmakelists. json 파일이 수정 됩니다.
- `cacheRoot`: CMake 캐시의 경로를 지정합니다. 이 디렉터리에는 기존 *cmakecache.txt* 파일이 포함 되어 있어야 합니다.
- `clangTidyChecks`: clang에 전달 되는 쉼표로 구분 된 경고 목록입니다. 와일드 카드를 사용할 수 있으며, '-' 접두사는 검사를 제거 합니다.
- `cmakeCommandArgs`: 프로젝트 파일을 생성 하기 위해 호출 될 때 CMake에 전달 되는 추가 명령줄 옵션을 지정 합니다.
- `cmakeToolchain`: 도구 체인 파일을 지정합니다. 이는 -DCMAKE_TOOLCHAIN_FILE을 사용하여 CMake에 전달됩니다."
- `codeAnalysisRuleset`: 코드 분석을 실행할 때 사용할 규칙 집합을 지정합니다. 이는 Visual Studio에서 설치한 규칙 집합 파일의 전체 경로 또는 파일 이름이 될 수 있습니다.
- `configurationType`: 선택한 생성기의 빌드 형식 구성을 지정합니다. 다음 중 하나일 수 있습니다.

  - Debug
  - Release
  - MinSizeRel
  - RelWithDebInfo
  
- `ctestCommandArgs`: 테스트 실행 시 CTest에 전달되는 추가 명령줄 옵션을 지정합니다."
- `description`: 메뉴에 표시되는 이 구성의 설명입니다.
- `enableClangTidyCodeAnalysis`: 코드 분석을 위해 Clang를 사용 합니다.
- `enableMicrosoftCodeAnalysis`: 코드 분석을 위해 Microsoft 코드 분석 도구를 사용 합니다.
- `generator`: 이 구성에 사용할 CMake 생성기를 지정합니다. 다음 중 하나일 수 있습니다.
  
  **Visual Studio 2019만:**
  - Visual Studio 16 2019
  - Visual Studio 16 2019 Win64
  - Visual Studio 16 2019 ARM

  **Visual Studio 2017 이상**:
  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - Unix 메이크파일
  - Ninja

Ninja는 유연성과 기능 대신 빠른 속도로 빌드하도록 설계되었으므로 기본값으로 설정됩니다. 그러나 일부 CMake 프로젝트는 Ninja를 사용하여 올바르게 빌드하지 못할 수도 있습니다. 이 문제가 발생 하는 경우 Visual Studio 프로젝트를 생성 하도록 CMake 지시할 수 있습니다.

Visual Studio 2017에서 Visual Studio 생성기를 지정 하려면 Cmake를 선택 하 여 주 메뉴에서를 엽니다.  **CMake 설정을 변경**합니다. "Ninja"를 삭제 하 고 "V"를 입력 합니다. 이렇게 하면 원하는 생성기를 선택할 수 있도록 IntelliSense가 활성화됩니다.

Visual Studio 2019에서 Visual Studio 생성기를 지정 하려면 **솔루션 탐색기** 의 *cmakelists* 파일을 마우스 오른쪽 단추로 클릭 하 고 **프로젝트의 csettings 설정** 을 선택 하 > **고급 설정** > **cstudio 생성기**를 표시 합니다.

활성 구성에서 Visual Studio 생성기를 지정하면 기본적으로 `-m -v:minimal` 인수를 사용하여 MSBuild.exe가 호출됩니다. 빌드를 사용자 지정 하려면 *Cmakesettings. json* 파일 내에서 `buildCommandArgs` 속성을 통해 빌드 시스템에 전달할 추가 [MSBuild 명령줄 인수](../build/reference/msbuild-visual-cpp-overview.md) 를 지정할 수 있습니다.

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `installRoot`: CMake가 선택한 생성기에 대한 설치 대상을 생성하는 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다.
- `inheritEnvironments`: 이 구성을 사용하는 하나 이상의 컴파일러 환경을 지정합니다. 모든 사용자 지정 환경 또는 미리 정의된 환경 중 하나일 수 있습니다. 자세한 내용은 [환경](#environments)을 참조하세요.
- `intelliSenseMode`: intellisense 정보 컴퓨팅에 사용되는 모드를 지정합니다." 다음 중 하나일 수 있습니다.

  - windows-msvc-x86
  - windows-msvc-x64
  - windows-msvc-arm
  - windows-msvc-arm64
  - android-clang-x86
  - android-clang-x64
  - android-clang-arm
  - android-clang-arm64
  - ios-clang-x86
  - ios-clang-x64
  - ios-clang-arm
  - ios-clang-arm64
  - windows-clang-x86
  - windows-clang-x64
  - windows-clang-arm
  - windows-clang-arm64
  - linux-gcc-x86
  - linux-gcc-x64
  - linux-gcc-arm"

- `name`: 구성 이름을 지정합니다.  미리 정의 된 구성에 대 한 자세한 내용은 [미리 정의 된 Cmake 구성 참조](cmake-predefined-configuration-reference.md) 를 참조 하세요.
- `wslPath`: Linux 용 Windows 하위 시스템 인스턴스의 시작 관리자에 대 한 경로입니다.

### <a name="additional-settings-for-cmake-linux-projects"></a>CMake Linux 프로젝트에 대 한 추가 설정

- `remoteMachineName`: CMake, 빌드 및 디버거를 호스팅하는 원격 Linux 머신의 이름을 지정합니다. 새 Linux 머신을 추가하기 위해 연결 관리자를 사용합니다. 지원되는 매크로에는 `${defaultRemoteMachineName}`이 포함됩니다.
- `remoteCopySourcesOutputVerbosity`: 원격 머신에 대한 소스 복사 작업의 세부 정보 표시 수준을 지정합니다. ""Normal", "Verbose" 또는 "Diagnostic" 중 하나일 수 있습니다.
- `remoteCopySourcesConcurrentCopies`: 원격 컴퓨터에 대 한 원본 동기화 중에 사용 되는 동시 복사본 수를 지정 합니다 (sftp에만 해당).
- `remoteCopySourcesMethod`: 원격 머신에 파일을 복사하는 방법을 지정합니다. "rsync" 또는 "sftp"일 수 있습니다.
- `remoteCMakeListsRoot`: CMake 프로젝트를 포함하는 원격 머신의 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다.
- `remoteBuildRoot`: CMake가 선택한 생성기에 대한 빌드 스크립트를 생성하는 원격 머신의 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다.
- `remoteInstallRoot`: CMake가 선택한 생성기에 대한 설치 대상을 생성하는 원격 머신의 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}` 및 `${env.VARIABLE}`이 포함됩니다. 여기서 `VARIABLE`은 시스템, 사용자 또는 세션 수준에서 정의된 환경 변수입니다.
- `remoteCopySources`: Visual Studio에서 원본 파일을 원격 컴퓨터에 복사할지 여부를 지정 하는 `boolean`입니다. 기본값은 true입니다. 파일 동기화를 직접 관리하는 경우 false로 설정합니다.
- `remoteCopyBuildOutput`: 원격 시스템에서 빌드 출력을 복사할지 여부를 지정 하는 `boolean`입니다.
- `remoteCopyAdditionalIncludeDirectories`: IntelliSense를 지원 하기 위해 원격 컴퓨터에서 복사할 추가 포함 디렉터리입니다. "/Path1;/path2.." 형식으로 지정 합니다.
- `remoteCopyExcludeDirectories`: 원격 컴퓨터에서 복사 하지 않는 디렉터리를 포함 합니다. "/Path1;/path2.." 형식으로 지정 합니다.
- `remoteCopyUseCompilerDefaults`: 컴파일러의 기본값을 사용할지 여부를 지정 하 고 IntelliSense의 경로를 포함 합니다. 에서 컴파일러를 사용 하 여 gcc 스타일 인수를 지원 하지 않는 경우에만 false가 됩니다.
- `rsyncCommandArgs`: rsync에 전달되는 추가 명령줄 옵션 세트를 지정합니다.
- `remoteCopySourcesExclusionList`: 소스 파일을 복사할 때 제외할 경로 목록을 지정 하는 `array`입니다. 경로는 파일/디렉터리의 이름 이거나 복사본의 루트에 상대적인 경로일 수 있습니다. 와일드 카드 \\\"*\\\" 및 \\\"?\\\"은 glob 패턴 일치에 사용할 수 있습니다.
- `cmakeExecutable`: 파일 이름과 확장명이 포함된 CMake 프로그램 실행 파일의 전체 경로를 지정합니다.
- `remotePreGenerateCommand`: *Cmakelists .txt* 파일을 구문 분석 하기 위해 cmake을 실행 하기 전에 실행할 명령을 지정 합니다.
- `remotePrebuildCommand`: 빌드 전 원격 머신에서 실행하는 명령을 지정합니다.
- `remotePostbuildCommand`: 빌드 후 원격 머신에서 실행하는 명령을 지정합니다.
- `variables`: cmake에 **-D** *_이름_=_값_* 으로 전달 되는 cmake 변수의 이름-값 쌍을 포함 합니다. CMake 프로젝트 빌드 지침에서 *cmakecache.txt* 파일에 직접 변수를 추가 하도록 지정 하는 경우 여기에 대신 추가 하는 것이 좋습니다. 다음 예제에서는 14.14.26428 MSVC 도구 세트에 대한 이름-값 쌍을 지정하는 방법을 보여줍니다.

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    }
  ]
```

`"type"`를 정의 하지 않으면 `"STRING"` 형식이 기본적으로 가정 됩니다.
- `remoteCopyOptimizations`: 원격 대상에 대 한 소스 복사를 제어 하기 위한 **Visual Studio 2019 버전 16.5 이상** 속성입니다. 최적화는 기본적으로 사용 하도록 설정 되어 있습니다. `remoteCopyUseOptimizations`, `rsyncSingleDirectoryCommandArgs` 및 `remoteCopySourcesMaxSmallChange`를 포함합니다.

## <a name="environments"></a>에서는

*환경은* Visual Studio에서 cmake를 호출 하는 데 사용 하는 프로세스에 설정 된 환경 변수를 캡슐화 합니다. MSVC 프로젝트의 경우 변수는 특정 플랫폼에 대 한 [개발자 명령 프롬프트](building-on-the-command-line.md) 에서 설정 되는 변수입니다. 예를 들어 `msvc_x64_x64` 환경은 vs **2017에 대 한 개발자 명령 프롬프트** 를 실행 하는 것과 동일 하며, **-아치 = amd64-host_arch = AMD64** 인수와 함께 **vs 2019에 개발자 명령 프롬프트** 합니다. 예를 들어 폴더에 대 한 경로를 생성 하는 등의 개별 환경 변수를 참조 하는 *Cmakesettings* 의 `env.{<variable_name>}` 구문을 사용할 수 있습니다.  다음과 같은 미리 정의 된 환경이 제공 됩니다.

- linux_arm: ARM Linux를 원격으로 대상으로 합니다.
- linux_x64: x64 Linux를 원격으로 대상으로 합니다.
- linux_x86: x86 Linux를 원격으로 대상으로 합니다.
- msvc_arm: MSVC 컴파일러를 사용 하는 ARM Windows를 대상으로 합니다.
- msvc_arm_x64:64 비트 MSVC 컴파일러를 사용 하는 ARM Windows를 대상으로 합니다.
- msvc_arm64: MSVC 컴파일러를 사용 하 여 ARM64 Windows를 대상으로 합니다.
- msvc_arm64_x64:64 비트 MSVC 컴파일러를 사용 하는 ARM64 Windows를 대상으로 합니다.
- msvc_x64: MSVC 컴파일러를 사용 하는 x64 Windows를 대상으로 합니다.
- msvc_x64_x64:64 비트 MSVC 컴파일러를 사용 하는 x64 Windows를 대상으로 합니다.
- msvc_x86: MSVC 컴파일러를 사용 하는 x86 Windows를 대상으로 합니다.
- msvc_x86_x64:64 비트 MSVC 컴파일러를 사용 하는 x86 Windows를 대상으로 합니다.

### <a name="accessing-environment-variables-from-cmakeliststxt"></a>CMakeLists에서 환경 변수에 액세스

CMakeLists .txt 파일에서 모든 환경 변수는 `$ENV{variable_name}`구문에서 참조 됩니다. 환경에 사용할 수 있는 변수를 보려면 해당 명령 프롬프트를 열고 `SET`를 입력 합니다. 환경 변수의 일부 정보는 CMake system 검사 변수를 통해서도 사용할 수 있지만 환경 변수를 사용 하는 것이 더 편리할 수 있습니다. 예를 들어 MSVC 컴파일러 버전 또는 Windows SDK 버전은 환경 변수를 통해 쉽게 검색할 수 있습니다.

### <a name="custom-environment-variables"></a>사용자 지정 환경 변수

`CMakeSettings.json`에서 `environments` 배열에 전역적으로 또는 구성 별로 사용자 지정 환경 변수를 정의할 수 있습니다. 사용자 지정 환경은 미리 정의 된 환경 대신 사용할 수 있는 속성 집합을 그룹화 하거나 미리 정의 된 환경을 확장 하거나 수정 하는 편리한 방법입니다. `environments` 배열의 각 항목은 다음과 같이 구성되어 있습니다.

- `namespace`: `namespace.variable` 형식의 구성에서 해당 변수가 참조될 수 있도록 환경 이름을 지정합니다. 기본 환경 개체는 `env` 이라고 하며 `%USERPROFILE%`를 비롯 한 특정 시스템 환경 변수로 채워집니다.
- `environment`: 이 변수 그룹을 고유하게 식별합니다. 그룹이 나중에 `inheritEnvironments` 항목에 상속되도록 허용합니다.
- `groupPriority`: 변수를 계산할 때 이러한 변수의 우선 순위를 지정 하는 정수입니다. 숫자가 높은 항목이 먼저 계산됩니다.
- `inheritEnvironments`:이 그룹이 상속 하는 환경 집합을 지정 하는 값의 배열입니다. 이 기능을 사용하면 기본 환경을 상속하고, 실행될 때 CMake.exe에 전달되는 사용자 지정 환경 변수를 만들 수 있습니다. 

**Visual Studio 2019 버전 16.4 이상:** 디버그 대상은 *Cmakesettings. json*에서 지정 하는 환경에서 자동으로 시작 됩니다. [시작. json](launch-vs-schema-reference-cpp.md) 및 [작업 및 json](tasks-vs-json-schema-reference-cpp.md)과 비교 하 여 대상이 나 작업 별로 환경 변수를 재정의 하거나 추가할 수 있습니다.

다음 예제에서는 x86-Debug 및 x64-Debug 구성 모두에서 상속된 하나의 **BuildDir** 전역 변수를 정의합니다. 각 구성에서 변수를 사용하여 해당 구성에 대한 **buildRoot** 속성 값을 지정합니다. 또한 각 구성에서 **inheritEnvironments** 속성을 사용하여 해당 구성에만 적용되는 변수를 지정하는 방법도 참조하세요.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

다음 예제에서 x86 디버그 구성은 **BuildDir** 속성에 대한 자체 값을 정의합니다. 이 값은 **BuildRoot**가 `D:\custom-builddir\x86-Debug`로 평가하도록 글로벌 **BuildDir** 속성이 설정한 값을 재정의합니다.

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir"
          // This environment does not specify a namespace, hence by default "env" will be assumed.
          // "namespace" : "name" would require that this variable be referenced with "${name.BuildDir}".
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ],
      // Since this configuration doesn't modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="macros"></a>매크로

*Cmakesettings*에서 다음 매크로를 사용할 수 있습니다. json:

- `${workspaceRoot}` – 작업 영역 폴더의 전체 경로
- `${workspaceHash}` - 작업 영역 위치의 해시입니다. 현재 작업 영역에 대한 고유 식별자를 만드는 데 유용합니다(예: 폴더 경로에서 사용).
- `${projectFile}` - 루트 CMakeLists.txt 파일의 전체 경로
- `${projectDir}` - 루트 CMakeLists.txt 파일의 폴더에 대한 전체 경로
- `${thisFile}` – `CMakeSettings.json` 파일의 전체 경로입니다.
- `${name}` - 구성의 이름
- `${generator}` - 이 구성에 사용된 CMake 생성기의 이름

*Cmakesettings. json* 의 매크로 및 환경 변수에 대 한 모든 참조는 cmage.exe 명령줄로 전달 되기 전에 확장 됩니다.

## <a name="ninja"></a> Ninja 명령줄 인수

대상이 지정되지 않으면 'default(기본)' 대상을 빌드합니다.

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|옵션|설명|
|--------------|------------|
| --version  | Ninja 버전("1.7.1")을 출력합니다.|
|   -C DIR   | 다른 작업을 수행하기 전에 DIR로 변경합니다.|
|   -f FILE  | 입력 빌드 파일을 지정합니다(기본값 = build.ninja)|
|   -j N     | N개의 작업을 병렬로 실행합니다(기본값 = 14, 사용 가능한 CPU에서 파생됨).|
|   -k N     | N개의 작업이 실패할 때까지 계속 수행됩니다(기본값 = 1)|
|   -l N     | 부하 평균이 N보다 큰 경우 새 작업을 시작하지 않습니다.|
|   -n       | 시험 실행을 수행합니다(명령을 실행하지 않고 성공한 것처럼 작동함)|
|   -v       | 빌드하는 동안 모든 명령줄을 표시합니다.|
|   -d MODE  | 디버깅을 사용하도록 설정합니다(-d list를 사용하여 모드를 나열함).|
|   -t TOOL  | 하위 도구를 실행합니다(-t list를 사용하여 하위 도구를 나열함). 최상위 옵션을 종료합니다. 추가 플래그가 도구에 전달됩니다.|
|   -w FLAG  | 경고를 조정합니다(-w list를 사용하여 경고를 표시함).|

::: moniker-end
