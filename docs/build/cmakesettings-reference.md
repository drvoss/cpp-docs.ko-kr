---
title: CMakeSettings.json 스키마 참조
ms.date: 11/22/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: f9c864b66df86165090b7d6d6fc9c4fc51d65a5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328889"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json 스키마 참조

::: moniker range="vs-2015"

CMake 프로젝트는 Visual Studio 2017 이상에서 지원됩니다.

::: moniker-end

::: moniker range=">=vs-2017"

**CMakeSettings.json** 파일에는 Visual Studio에서 IntelliSense에 사용하고 지정된 *구성* 및 컴파일러 *환경에*대해 cmake.exe에 전달하는 명령줄 인수를 구성하는 정보가 포함되어 있습니다. 구성은 특정 플랫폼 및 빌드 유형에 적용되는 속성(예: `x86-Debug` 또는 `Linux-Release`)을 지정합니다. 각 구성은 MSVC, GCC 또는 Clang과 같은 컴파일러 도구 집합에 대한 정보를 캡슐화하는 환경을 지정합니다. CMake는 명령줄 인수를 사용하여 프로젝트의 루트 *CMakeCache.txt* 파일 및 기타 프로젝트 파일을 다시 생성합니다. *CMakeLists.txt* 파일에서 값을 재정의할 수 있습니다.

IDE에서 구성을 추가 하거나 제거 한 다음 JSON 파일에서 직접 편집하거나 **CMake 설정 편집기** (Visual Studio 2019 이상)를 사용할 수 있습니다. IDE에서 구성 을 쉽게 전환하여 다양한 프로젝트 파일을 생성할 수 있습니다. 자세한 내용은 [Visual Studio에서 CMake 빌드 설정 사용자 지정을](customize-cmake-settings.md) 참조하십시오.

## <a name="configurations"></a>구성

배열에는 `configurations` CMake 프로젝트에 대한 모든 구성이 포함되어 있습니다. 미리 정의된 구성에 대한 자세한 내용은 [CMake 사전 정의된 구성 참조를](cmake-predefined-configuration-reference.md) 참조하십시오. 파일에 미리 정의된 구성 또는 사용자 지정 구성을 원하는 수에 관계없이 추가할 수 있습니다.

`configuration`에는 다음과 같은 속성이 있습니다.

- `addressSanitizerEnabled`: `true` 주소 소독기 (Windows에서 실험)로 프로그램을 컴파일하는 경우. Linux에서는 최상의 결과를 얻으려면 -fno-omit-frame-포인터 및 컴파일러 최적화 수준 -Os 또는 -Oo로 컴파일합니다.
- `addressSanitizerRuntimeFlags`: ASAN_OPTIONS 환경 변수를 통해 AddressSanitizer에 전달된 런타임 플래그입니다. 형식: flag1=값:flag2=value2.
- `buildCommandArgs`: --빌드 -- 후 CMake로 전달되는 네이티브 빌드 스위치를 지정합니다. 예를 들어 Ninja 생성기를 사용하는 경우 -v를 전달하면 Ninja에서 명령줄을 출력하도록 강제합니다. Ninja 명령에 대한 자세한 정보는 [Ninja 명령줄 인수](#ninja)를 참조하세요.
- `buildRoot`: CMake가 선택한 생성기에 대한 빌드 스크립트를 생성하는 디렉터리를 지정합니다.  **-DCMAKE_BINARY_DIR** 스위치에 매핑하고 *CMakeCache.txt가* 생성될 위치를 지정합니다. 폴더가 없으면 해당 폴더가 만들어집니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다.
- `cacheGenerationCommand`: 명령줄 도구 및 인수(예: *gencache.bat 디버그)를* 지정하여 캐시를 생성합니다. 명령은 사용자가 명시적으로 재생성을 요청하거나 CMakeLists.txt 또는 CMakeSettings.json 파일이 수정될 때 구성에 대해 지정된 환경의 셸에서 실행됩니다.
- `cacheRoot`: CMake 캐시의 경로를 지정합니다. 이 디렉터리에는 기존 *CMakeCache.txt* 파일이 포함되어야 합니다.
- `clangTidyChecks`: 쉼표로 구분된 경고 목록은 clang-tidy로 전달됩니다. 와일드카드가 허용되고 '-' 접두사가 검사를 제거합니다.
- `cmakeCommandArgs`: 프로젝트 파일을 생성하기 위해 호출될 때 CMake에 전달된 추가 명령줄 옵션을 지정합니다.
- `cmakeToolchain`: 도구 체인 파일을 지정합니다. 이는 -DCMAKE_TOOLCHAIN_FILE을 사용하여 CMake에 전달됩니다."
- `codeAnalysisRuleset`: 코드 분석을 실행할 때 사용할 규칙 집합을 지정합니다. 이는 Visual Studio에서 설치한 규칙 집합 파일의 전체 경로 또는 파일 이름이 될 수 있습니다.
- `configurationType`: 선택한 생성기의 빌드 형식 구성을 지정합니다. 다음 중 하나일 수 있습니다.

  - 디버그
  - 해제
  - MinSizeRel
  - RelWithDebInfo
  
- `ctestCommandArgs`: 테스트 실행 시 CTest에 전달되는 추가 명령줄 옵션을 지정합니다."
- `description`: 메뉴에 표시되는 이 구성의 설명입니다.
- `enableClangTidyCodeAnalysis`: 코드 분석을 위해 Clang-Tidy를 사용합니다.
- `enableMicrosoftCodeAnalysis`: 코드 분석을 위해 Microsoft 코드 분석 도구를 사용합니다.
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

Ninja는 유연성과 기능 대신 빠른 속도로 빌드하도록 설계되었으므로 기본값으로 설정됩니다. 그러나 일부 CMake 프로젝트는 Ninja를 사용하여 올바르게 빌드하지 못할 수도 있습니다. 이 경우 CMake에게 Visual Studio 프로젝트를 생성하도록 지시할 수 있습니다.

Visual Studio 2017에서 Visual Studio 생성기를 지정하려면 CMake |을 선택하여 주 메뉴에서 열기 ** CMake 설정 변경**. "닌자"를 삭제하고 "V"를 입력합니다. 이렇게 하면 원하는 생성기를 선택할 수 있도록 IntelliSense가 활성화됩니다.

Visual Studio 2019에서 Visual Studio 생성기를 지정하려면 **솔루션 탐색기에서** *CMakeLists.txt* 파일을 마우스 오른쪽 단추로 클릭하고 **프로젝트에** > 대한 CMake 설정을 **선택합니다.** > **CMake Generator**

활성 구성에서 Visual Studio 생성기를 지정하면 기본적으로 `-m -v:minimal` 인수를 사용하여 MSBuild.exe가 호출됩니다. *CMakeSettings.json* 파일 내에서 빌드를 사용자 지정하려면 `buildCommandArgs` 속성을 통해 빌드 시스템에 전달할 추가 [MSBuild 명령줄 인수를](../build/reference/msbuild-visual-cpp-overview.md) 지정할 수 있습니다.

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

- `name`: 구성 이름을 지정합니다.  미리 정의된 구성에 대한 자세한 내용은 [CMake 사전 정의된 구성 참조를](cmake-predefined-configuration-reference.md) 참조하십시오.
- `wslPath`: 리눅스용 Windows 서브시스템 인스턴스의 런처에 대한 경로입니다.

### <a name="additional-settings-for-cmake-linux-projects"></a>CMake 리눅스 프로젝트에 대 한 추가 설정

- `remoteMachineName`: CMake, 빌드 및 디버거를 호스팅하는 원격 Linux 머신의 이름을 지정합니다. 새 Linux 머신을 추가하기 위해 연결 관리자를 사용합니다. 지원되는 매크로에는 `${defaultRemoteMachineName}`이 포함됩니다.
- `remoteCopySourcesOutputVerbosity`: 원격 머신에 대한 소스 복사 작업의 세부 정보 표시 수준을 지정합니다. ""Normal", "Verbose" 또는 "Diagnostic" 중 하나일 수 있습니다.
- `remoteCopySourcesConcurrentCopies`: 원본을 원격 컴퓨터로 동기화하는 동안 사용되는 동시 복사본 수를 지정합니다(sftp만).
- `remoteCopySourcesMethod`: 원격 머신에 파일을 복사하는 방법을 지정합니다. "rsync" 또는 "sftp"일 수 있습니다.
- `remoteCMakeListsRoot`: CMake 프로젝트를 포함하는 원격 머신의 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다.
- `remoteBuildRoot`: CMake가 선택한 생성기에 대한 빌드 스크립트를 생성하는 원격 머신의 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다.
- `remoteInstallRoot`: CMake가 선택한 생성기에 대한 설치 대상을 생성하는 원격 머신의 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}` 및 `${env.VARIABLE}`이 포함됩니다. 여기서 `VARIABLE`은 시스템, 사용자 또는 세션 수준에서 정의된 환경 변수입니다.
- `remoteCopySources`: `boolean` Visual Studio에서 원본 파일을 원격 컴퓨터에 복사할지 여부를 지정하는 A입니다. 기본값은 true입니다. 파일 동기화를 직접 관리하는 경우 false로 설정합니다.
- `remoteCopyBuildOutput`: `boolean` 원격 시스템에서 빌드 출력을 복사할지 여부를 지정하는 A입니다.
- `remoteCopyAdditionalIncludeDirectories`: IntelliSense를 지원하기 위해 원격 컴퓨터에서 복사할 디렉토리가 추가로 포함되어 있습니다. "/path1;/path2..."로 서식을 지정합니다.
- `remoteCopyExcludeDirectories`: 원격 컴퓨터에서 복사하지 않는 디렉토리를 포함합니다. "/path1;/path2..."로 서식을 지정합니다.
- `remoteCopyUseCompilerDefaults`: 컴파일러의 기본 정의를 사용하고 IntelliSense에 대한 경로를 포함할지 여부를 지정합니다. 사용 되는 컴파일러 gcc 스타일 인수를 지원 하지 않는 경우에만 false 해야 합니다.
- `rsyncCommandArgs`: rsync에 전달되는 추가 명령줄 옵션 세트를 지정합니다.
- `remoteCopySourcesExclusionList`: `array` 소스 파일을 복사할 때 제외할 경로 목록을 지정하는 A': 경로는 파일/디렉터리의 이름또는 복사본의 루트를 기준으로 하는 경로일 수 있습니다. 와일드 카드 \\\"*\\\" 및 \\\"?\\\"은 glob 패턴 일치에 사용할 수 있습니다.
- `cmakeExecutable`: 파일 이름과 확장명이 포함된 CMake 프로그램 실행 파일의 전체 경로를 지정합니다.
- `remotePreGenerateCommand`: *CMakeLists.txt* 파일을 구문 분석하기 위해 CMake를 실행하기 전에 실행할 명령을 지정합니다.
- `remotePrebuildCommand`: 빌드 전 원격 머신에서 실행하는 명령을 지정합니다.
- `remotePostbuildCommand`: 빌드 후 원격 머신에서 실행하는 명령을 지정합니다.
- `variables`: **-D** *_이름_=_값_* 으로 CMake에 전달되는 CMake 변수의 이름 값 쌍이 포함됩니다. CMake 프로젝트 빌드 지침에서 *CMakeCache.txt* 파일에 직접 변수를 추가하는 것을 지정하는 경우 대신 여기에 추가하는 것이 좋습니다. 다음 예제에서는 14.14.26428 MSVC 도구 세트에 대한 이름-값 쌍을 지정하는 방법을 보여줍니다.

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

`"type"`을 정의하지 않으면 기본적으로 형식이 `"STRING"` 가정됩니다.

- `remoteCopyOptimizations`: **비주얼 스튜디오 2019 버전 16.5 이상** 은 원격 대상에 소스 복사본을 제어하기위한 속성입니다. 최적화는 기본적으로 활성화되어 있습니다. `remoteCopyUseOptimizations`, `rsyncSingleDirectoryCommandArgs` 및 `remoteCopySourcesMaxSmallChange`를 포함합니다.

## <a name="environments"></a><a name="environments"></a>환경

*환경은* Visual Studio에서 cmake.exe를 호출하는 데 사용하는 프로세스에서 설정된 환경 변수를 캡슐화합니다. MSVC 프로젝트의 경우 변수는 특정 플랫폼에 대한 [개발자 명령 프롬프트에](building-on-the-command-line.md) 설정된 변수입니다. 예를 들어 `msvc_x64_x64` 환경은 **VS 2017에 대한 개발자 명령 프롬프트** 또는 **VS 2019에 대한 개발자 명령 프롬프트를** **-arch=amd64 -host_arch=amd64** 인수로 실행하는 것과 동일합니다. `env.{<variable_name>}` *CMakeSettings.json의* 구문을 사용하여 개별 환경 변수를 참조할 수 있습니다(예: 폴더에 대한 경로 생성).  미리 정의된 다음 환경이 제공됩니다.

- linux_arm: 타겟 ARM 리눅스 원격으로.
- linux_x64: 대상 x64 리눅스 원격으로.
- linux_x86: 대상 x86 리눅스 원격으로.
- msvc_arm: MSVC 컴파일러를 통해 ARM 창을 대상으로 합니다.
- msvc_arm_x64: 64비트 MSVC 컴파일러를 통해 ARM Windows를 대상으로 합니다.
- msvc_arm64: MSVC 컴파일러를 통해 ARM64 Windows를 대상으로 합니다.
- msvc_arm64_x64: 64비트 MSVC 컴파일러를 통해 ARM64 Windows를 대상으로 합니다.
- msvc_x64: MSVC 컴파일러를 통해 x64 Windows를 대상으로 합니다.
- msvc_x64_x64: 64비트 MSVC 컴파일러를 통해 x64 Windows를 대상으로 합니다.
- msvc_x86: MSVC 컴파일러를 통해 x86 Windows를 대상으로 합니다.
- msvc_x86_x64: 64비트 MSVC 컴파일러를 통해 x86 Windows를 대상으로 합니다.

### <a name="accessing-environment-variables-from-cmakeliststxt"></a>CMakeLists.txt에서 환경 변수 액세스

CMakeLists.txt 파일에서 모든 환경 변수는 구문으로 `$ENV{variable_name}`참조됩니다. 환경에 사용할 수 있는 변수를 보려면 해당 명령 `SET`프롬프트를 열고 입력합니다. 환경 변수의 일부 정보는 CMake 시스템 내성 변수를 통해서도 사용할 수 있지만 환경 변수를 사용하는 것이 더 편리할 수 있습니다. 예를 들어 MSVC 컴파일러 버전 또는 Windows SDK 버전은 환경 변수를 통해 쉽게 검색됩니다.

### <a name="custom-environment-variables"></a>사용자 지정 환경 변수

에서 `CMakeSettings.json`전역또는 배열의 구성별 사용자 지정 환경 `environments` 변수를 정의할 수 있습니다. 사용자 지정 환경은 미리 정의된 환경 대신 사용할 수 있는 속성 집합을 그룹화하거나 미리 정의된 환경을 확장하거나 수정하는 편리한 방법입니다. `environments` 배열의 각 항목은 다음과 같이 구성되어 있습니다.

- `namespace`: `namespace.variable` 형식의 구성에서 해당 변수가 참조될 수 있도록 환경 이름을 지정합니다. 기본 환경 개체가 `env` 호출되고 를 포함한 `%USERPROFILE%`특정 시스템 환경 변수로 채워집니다.
- `environment`: 이 변수 그룹을 고유하게 식별합니다. 그룹이 나중에 `inheritEnvironments` 항목에 상속되도록 허용합니다.
- `groupPriority`: 이러한 변수를 평가할 때 이러한 변수의 우선 순위를 지정하는 정수입니다. 숫자가 높은 항목이 먼저 계산됩니다.
- `inheritEnvironments`: 이 그룹에 의해 상속되는 환경 집합을 지정하는 값의 배열입니다. 이 기능을 사용하면 기본 환경을 상속하고, 실행될 때 CMake.exe에 전달되는 사용자 지정 환경 변수를 만들 수 있습니다.

**비주얼 스튜디오 2019 버전 16.4 이상:** 디버그 대상은 *CMakeSettings.json*에서 지정한 환경과 함께 자동으로 시작됩니다. [launch.vs.json](launch-vs-schema-reference-cpp.md) 및 [tasks.vs.json에서](tasks-vs-json-schema-reference-cpp.md)대상당 또는 작업별로 환경 변수를 재정의하거나 추가할 수 있습니다.

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

## <a name="macros"></a>Macros

다음 매크로는 *CMakeSettings.json에서*사용할 수 있습니다.

- `${workspaceRoot}`– 작업 영역 폴더의 전체 경로
- `${workspaceHash}` - 작업 영역 위치의 해시입니다. 현재 작업 영역에 대한 고유 식별자를 만드는 데 유용합니다(예: 폴더 경로에서 사용).
- `${projectFile}` - 루트 CMakeLists.txt 파일의 전체 경로
- `${projectDir}` - 루트 CMakeLists.txt 파일의 폴더에 대한 전체 경로
- `${thisFile}` – `CMakeSettings.json` 파일의 전체 경로입니다.
- `${name}` - 구성의 이름
- `${generator}` - 이 구성에 사용된 CMake 생성기의 이름

*CMakeSettings.json의* 매크로 및 환경 변수에 대한 모든 참조는 cmake.exe 명령줄로 전달되기 전에 확장됩니다.

## <a name="ninja-command-line-arguments"></a><a name="ninja"></a> Ninja 명령줄 인수

대상이 지정되지 않으면 'default(기본)' 대상을 빌드합니다.

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|옵션|Description|
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
