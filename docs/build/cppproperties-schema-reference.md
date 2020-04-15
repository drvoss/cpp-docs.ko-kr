---
title: CppProperties.json 참조
ms.date: 08/09/2019
helpviewer_keywords:
- CppProperties.json file [C++]
ms.openlocfilehash: be6db52e1e62244e9f44db8ac86238242ab50ca0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328726"
---
# <a name="cpppropertiesjson-reference"></a>CppProperties.json 참조

CMake를 사용하지 않는 폴더 열기 프로젝트는 *CppProperties.json* 파일에 IntelliSense에 대한 프로젝트 구성 설정을 저장할 수 있습니다. (CMake 프로젝트는 [CMakeSettings.json](customize-cmake-settings.md) 파일을 사용합니다.) 구성은 이름/값 쌍으로 구성되며 #include 경로, 컴파일러 스위치 및 기타 매개 변수를 정의합니다. 열기 폴더 프로젝트에서 구성을 추가하는 방법에 대한 자세한 내용은 [C++에 대한](open-folder-projects-cpp.md) 폴더 열기 프로젝트를 참조하십시오. 다음 섹션에서는 다양한 설정을 요약합니다. 스키마에 대한 전체 설명을 보려면 *cppProperties.json이*열려 있을 때 전체 경로가 코드 편집기 상단에 제공되는 *CppProperties_schema.json으로* 이동합니다.

## <a name="configuration-properties"></a>구성 속성

구성에는 다음 속성 중 하나가 있을 수 있습니다.

|||
|-|-|
|`inheritEnvironments`| 이 구성에 적용되는 환경을 지정합니다.|
|`name`|C++ 구성 드롭다운에 표시되는 구성 이름|
|`includePath`|포함 경로에 지정해야 하는 쉼표로 구분된 폴더 목록(대부분의 컴파일러에 대해 /I에 대한 맵)|
|`defines`|정의해야 하는 매크로 목록(대부분의 컴파일러에서 /D에 매핑됨)|
|`compilerSwitches`|IntelliSense 동작에 영향을 줄 수 있는 하나 이상의 추가 스위치|
|`forcedInclude`|모든 컴파일 단위에 자동으로 포함될 헤더(MSVC에서 /FI에 매핑되거나 clang에서 -include에 매핑됨)|
|`undefines`|정의되지 않은 매크로 목록(MSVC에서 /U에 매핑됨)|
|`intelliSenseMode`|사용할 IntelliSense 엔진. MSVC, gcc 또는 Clang에 대해 미리 정의된 아키텍처별 변형 중 하나를 지정할 수 있습니다.|
|`environments`|명령 프롬프트에서 환경 변수처럼 행동하고 ${env로 액세스하는 사용자 정의 변수\< 집합입니다. 변수>} 매크로.|

### <a name="intellisensemode-values"></a>인텔리센스모드 값

코드 편집기는 입력을 시작할 때 사용 가능한 옵션을 표시합니다.

![폴더 인텔리센스 열기](media/open-folder-intellisense-mode.png "폴더 인텔리센스 열기")

지원되는 값은 다음과 같습니다.

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
- 리눅스 GCC 팔

참고: `msvc-x86` 값및 `msvc-x64` 레거시 이유로만 지원됩니다. 대신 `windows-msvc-*` 변형을 사용합니다.

## <a name="pre-defined-environments"></a>미리 정의된 환경

Visual Studio는 해당 개발자 명령 프롬프트에 매핑되는 Microsoft C++에 대해 미리 정의된 다음 환경을 제공합니다. 이러한 환경 중 하나를 상속하는 경우 이 매크로 구문인 ${env를 사용하여 전역 속성을 `env` 사용하여\< 환경 변수를 참조할 수 있습니다. 변수>}.

|변수 이름|Description|
|-----------|-----------------|
|vsdev|기본 Visual Studio 환경|
|msvc_x86|x86 도구를 사용하여 x86용으로 컴파일|
|msvc_x64|64비트 도구를 사용하여 AMD64용으로 컴파일|
|msvc_arm|x86 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64|x86 도구를 사용하여 ARM64용으로 컴파일|
|msvc_x86_x64|x86 도구를 사용하여 AMD64용으로 컴파일|
|msvc_arm_x64|64비트 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64_x64|64비트 도구를 사용하여 ARM64용으로 컴파일|

Linux 워크로드가 설치되면 원격으로 Linux 및 WSL을 대상으로 지정하는 데 사용할 수 있는 환경은 다음과 같습니다.

|변수 이름|Description|
|-----------|-----------------|
|linux_x86|원격으로 x86 Linux를 대상 지정|
|linux_x64|원격으로 x64 Linux를 대상 지정|
|linux_arm|원격으로 ARM Linux를 대상 지정|

## <a name="user-defined-environments"></a><a name="user_defined_environments"></a>사용자 정의 환경

선택적으로 `environments` 속성을 사용하여 *CppProperties.json의* 변수 집합을 전역적으로 또는 구성당 정의할 수 있습니다. 이러한 변수는 Open Folder 프로젝트의 컨텍스트에서 환경 변수처럼 행동하며 ${env를 통해\< 액세스할 수 있습니다. 변수>} *구문에서 tasks.vs.json* 및 *launch.vs.json* 다음에 정의 된 후. 그러나 Visual Studio에서 내부적으로 사용하는 명령 프롬프트에서 실제 환경 변수로 반드시 설정되지는 않습니다.

**비주얼 스튜디오 2019 버전 16.4 이상:** *CppProperties.json에* 정의된 구성별 변수는 설정하지 `inheritEnvironments`않고도 디버그 대상 및 작업에 의해 자동으로 선택됩니다. 디버그 대상은 *CppProperties.json*에서 지정한 환경과 함께 자동으로 시작됩니다.

**비주얼 스튜디오 2019 버전 16.3 이전:** 환경을 사용할 때 환경이 `inheritsEnvironments` 동일한 구성의 일부로 정의된 경우에도 속성에 지정해야 합니다. 속성은 `environment` 환경의 이름을 지정합니다. 다음 예제에서는 MSYS2 설치에서 GCC에 대한 IntelliSense를 사용하도록 설정하기 위한 샘플 구성을 보여 주며 있습니다. 구성이 `mingw_64` 환경을 정의하고 상속하는 방법과 속성이 `includePath` `INCLUDE` 변수에 액세스하는 방법을 설명합니다.

```json
"configurations": [
    {

      "inheritEnvironments": [
        "mingw_64"
      ],
      "name": "Mingw64",
      "includePath ,": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**",
      ],
      "intelliSenseMode": "linux-gcc-x64",
      "environments": [
        {
          "MINGW64_ROOT": "C:\\msys64\\mingw64",
          "BIN_ROOT": "${env.MINGW64_ROOT}\\bin",
          "FLAVOR": "x86_64-w64-mingw32",
          "TOOLSET_VERSION": "9.1.0",
          "PATH": "${env.MINGW64_ROOT}\\bin;${env.MINGW64_ROOT}\\..\\usr\\local\\bin;${env.MINGW64_ROOT}\\..\\usr\\bin;${env.MINGW64_ROOT}\\..\\bin;${env.PATH}",
          "INCLUDE": "${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION};${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\tr1;${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\${env.FLAVOR};",
          "environment": "mingw_64"
        }
      ]
    }
  ]
```

구성 내에서 **환경** 속성을 정의하면 동일한 이름의 전역 변수를 재정의합니다.

## <a name="built-in-macros"></a>기본 제공 매크로

*CppProperties.json*내부에 다음과 같은 기본 제공 매크로에 액세스할 수 있습니다.

|||
|-|-|
|`${workspaceRoot}`| 작업 영역 폴더에 대한 전체 경로|
|`${projectRoot}`| *CppProperties.json이* 배치된 폴더에 대한 전체 경로|
|`${env.vsInstallDir}`| Visual Studio의 실행 중인 인스턴스가 설치된 폴더에 대한 전체 경로|

### <a name="example"></a>예제

프로젝트에 포함 폴더가 있고 Windows SDK의 *windows.h* 및 기타 공통 헤더도 포함된 경우 다음과 같은 내용으로 *CppProperties.json* 구성 파일을 업데이트할 수 있습니다.

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\ucrt",
        "${env.NETFXSDKDir}\include\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\shared",
        "${env.VCToolsInstallDir}\include"
      ]
    }
  ]
}
```

> [!Note]
> `%WindowsSdkDir%` 및 `%VCToolsInstallDir%`은 글로벌 환경 변수로 설정되지 않으므로 devenv.exe는 이러한 변수를 정의하는 개발자 명령 프롬프트에서 시작해야 합니다. (Windows 시작 메뉴에 "개발자" 입력)

## <a name="troubleshoot-intellisense-errors"></a>IntelliSense 오류 문제 해결

예상하는 IntelliSense가 표시되지 않으면 **도구** > **옵션** > **텍스트 편집기** > **C/C++** > **고급으로** 이동하여 **로깅을** **true로**설정하여 문제를 해결할 수 있습니다. 시작하려면 **로깅 수준을** 5로 설정하고 필터를 8로 **로깅해** 보십시오.

![진단 로깅](media/diagnostic-logging.png)

출력은 **출력 창에** 파이프되며 출력 표시를 선택할 때 **표시됩니다: Visual C++ Log**. 출력에는 무엇보다도 IntelliSense가 사용하려고하는 실제 경로 목록이 포함되어 있습니다. 경로가 *CppProperties.json의*경로와 일치하지 않으면 폴더를 닫고 캐시된 브라우징 데이터가 포함된 *.vs* 하위 폴더를 삭제해 보십시오.

include 경로 누락으로 인한 IntelliSense 오류 문제를 해결하려면, **오류 목록**을 열고, 출력을 "IntelliSense 전용" 및 E1696 오류 코드("소스 파일을 열 수 없습니다. ...")로 필터링합니다.
