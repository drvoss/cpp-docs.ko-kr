---
title: '연습: MSBuild를 사용하여 Visual C++ 프로젝트 만들기'
ms.date: 05/16/2019
helpviewer_keywords:
- 'msbuild (c++), walkthrough: create a project'
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
ms.openlocfilehash: c93867f3be3b17f703c549aa5c05f3d327934c26
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422717"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>연습: MSBuild를 사용하여 Visual C++ 프로젝트 만들기

이 연습에서는 명령 프롬프트에서 MSBuild를 사용하여 Visual Studio C++ 프로젝트를 빌드하는 방법을 보여줍니다. Visual C++ 콘솔 애플리케이션용 XML 기반 프로젝트 파일 및 C++ 원본 파일을 만드는 방법을 알아봅니다. 프로젝트를 빌드한 후 빌드 프로세스를 사용자 지정하는 방법을 배웁니다.

이 연습에서는 다음 작업을 수행합니다.

- 프로젝트를 위한 C++ 원본 파일 만들기

- XML MSBuild 프로젝트 파일 만들기

- MSBuild를 사용하여 프로젝트 빌드

- MSBuild를 사용하여 프로젝트 사용자 지정

## <a name="prerequisites"></a>사전 요구 사항

이 연습을 진행하려면 먼저 다음 작업을 수행해야 합니다.

- **C++를 사용한 데스크톱 개발** 워크로드가 설치된 Visual Studio 복사본이 필요합니다.

- MSBuild 시스템에 대해 전반적으로 이해합니다.

> [!NOTE]
> Visual Studio IDE를 사용하여 나중에 프로젝트 파일을 편집하려는 경우에는 이 방법을 사용하지 마십시오. .vcxproj 파일을 수동으로 만드는 경우 특히 프로젝트가 프로젝트 항목에 와일드 카드를 사용하면 Visual Studio IDE를 편집하거나 로드하지 못할 수도 있습니다.

> [!NOTE]
> 대부분의 하위 수준 빌드 지침은 `$(VCTargetsPath)`에 저장된 VCTargets 디렉터리에 정의된 **.targets** 및 **.props** 파일에 포함되어 있습니다. Visual Studio 2019 Enterprise Edition에서 이러한 파일에 대한 기본 경로는 C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\MSBuild\Microsoft\VC\v160\Microsoft.Cpp.Common.props입니다.

## <a name="creating-the-c-source-files"></a>C++ 원본 파일 만들기

이 연습에서는 원본 파일 및 헤더 파일이 있는 프로젝트를 만듭니다. 원본 파일 main.cpp에는 콘솔 애플리케이션의 주 함수가 포함되어 있습니다. 헤더 파일 main.h에는 iostream 헤더 파일을 포함하는 코드가 포함되어 있습니다. 이러한 C++ 파일을 Visual Studio 또는 Visual Studio Code와 같은 텍스트 편집기를 사용하여 만들 수 있습니다.

### <a name="to-create-the-c-source-files-for-your-project"></a>프로젝트를 위한 C++ 원본 파일을 만들려면

1. 프로젝트를 위한 디렉터리를 만듭니다.

1. main.cpp라는 파일을 만들고 이 파일에 다음 코드를 추가합니다.

    ```cpp
    // main.cpp : the application source code.
    #include <iostream>
    #include "main.h"
    int main()
    {
       std::cout << "Hello, from MSBuild!\n";
       return 0;
    }
    ```

1. main.h라는 파일을 만들고 이 파일에 다음 코드를 추가합니다.

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>XML MSBuild 프로젝트 파일 만들기

MSBuild 프로젝트 파일은 프로젝트 루트 요소(`<Project>`)를 포함하는 XML 파일입니다. 다음 예제 프로젝트의 `<Project>` 요소에는 자식 요소가 7개 포함되어 있습니다.

- 프로젝트 구성 및 플랫폼, 원본 파일 이름 및 헤더 파일 이름을 지정하는 세 개의 항목 그룹 태그(`<ItemGroup>`).

- Microsoft Visual C++ 설정의 위치를 지정하는 세 개의 가져오기 태그(`<Import>`).

- 프로젝트 설정을 지정하는 하나의 속성 그룹 태그(`<PropertyGroup>`).

### <a name="to-create-the-msbuild-project-file"></a>MSBuild 프로젝트 파일을 만들려면

1. 텍스트 편집기를 사용하여 `myproject.vcxproj`라는 프로젝트 파일을 만든 다음, 다음 루트 `<Project>` 요소를 추가합니다. 루트 `<Project>` 태그 간 다음 절차 단계에 요소를 삽입합니다. (Visual Studio 2017을 사용하는 경우 ToolsVersion=“15.0”을 사용하고, Visual Studio 2019를 사용하는 경우 ToolsVersion=“16.0”을 사용합니다.)

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

1. 다음 두 개의 `<ProjectConfiguration>` 자식 요소를 `<ItemGroup>` 요소에 추가합니다. 자식 요소는 32비트 Windows 운영 체제를 위한 디버그 및 릴리스 구성을 지정합니다.

    ```xml
    <ItemGroup>
      <ProjectConfiguration Include="Debug|Win32">
        <Configuration>Debug</Configuration>
        <Platform>Win32</Platform>
      </ProjectConfiguration>
      <ProjectConfiguration Include="Release|Win32">
        <Configuration>Release</Configuration>
        <Platform>Win32</Platform>
      </ProjectConfiguration>
    </ItemGroup>
    ```

1. 이 프로젝트를 위한 기본 C++ 설정의 경로를 지정하는 다음 `<Import>` 요소를 추가합니다.

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

1. 두 개의 프로젝트 속성을 지정하는 다음 속성 그룹 요소(`<PropertyGroup>`)를 추가합니다. (Visual Studio 2017을 사용하는 경우 v141을 사용하고, Visual Studio 2019를 사용하는 경우 v142를 사용합니다.)

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v142</PlatformToolset>
    </PropertyGroup>
    ```

1. 이 프로젝트를 위한 현재 C++ 설정의 경로를 지정하는 다음 `<Import>` 요소를 추가합니다.

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

1. 다음 `<ClCompile>` 자식 요소를 `<ItemGroup>` 요소에 추가합니다. 자식 요소는 컴파일할 C/C++ 원본 파일의 이름을 지정합니다.

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > `<ClCompile>`은 *빌드 대상*이며, **VCTargets** 디렉터리에 정의되어 있습니다.

1. 다음 `<ClInclude>` 자식 요소를 `<ItemGroup>` 요소에 추가합니다. 자식 요소는 C/C++ 원본 파일에 사용할 헤더 파일의 이름을 지정합니다.

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

1. 이 프로젝트를 위한 대상을 정의하는 파일의 경로를 지정하는 다음 `<Import>` 요소를 추가합니다.

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>전체 프로젝트 파일

다음 코드는 이전 절차에서 만든 전체 프로젝트 파일을 보여줍니다. (Visual Studio 2017의 경우 ToolsVersion=“15.0”을 사용합니다.)

```xml
<Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup>
    <ProjectConfiguration Include="Debug|Win32">
      <Configuration>Debug</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
    <ProjectConfiguration Include="Release|Win32">
      <Configuration>Release</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
  <PropertyGroup>
    <ConfigurationType>Application</ConfigurationType>
    <PlatformToolset>v142</PlatformToolset>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ItemGroup>
    <ClCompile Include="main.cpp" />
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="main.h" />
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
</Project>
```

## <a name="using-msbuild-to-build-your-project"></a>MSBuild를 사용하여 프로젝트 빌드

콘솔 애플리케이션을 빌드하려면 명령 프롬프트에서 다음 명령을 입력합니다.

`msbuild myproject.vcxproj /p:configuration=debug`

MSBuild는 출력 파일에 대한 디렉터리를 만든 다음, 컴파일하고 프로젝트를 연결하여 Myproject.exe 프로그램을 생성합니다. 빌드 프로세스가 완료되면 다음 명령을 사용하여 디버그 폴더에서 애플리케이션을 실행합니다.

`myproject`

애플리케이션에 “Hello, from MSBuild!”가 표시됩니다. 콘솔 창에 표시합니다.

## <a name="customizing-your-project"></a>프로젝트 사용자 지정

MSBuild를 사용하면 미리 정의된 빌드 대상을 실행하고, 사용자 정의 속성을 적용하고, 사용자 지정 도구, 이벤트 및 빌드 단계를 사용할 수 있습니다. 이 섹션에서는 다음 작업을 설명합니다.

- 빌드 대상과 함께 MSBuild 사용

- 빌드 속성과 함께 MSBuild 사용

- 64비트 컴파일러 및 도구와 함께 MSBuild 사용

- 다른 도구 집합과 함께 MSBuild 사용

- MSBuild 사용자 지정 추가

### <a name="using-msbuild-with-build-targets"></a>빌드 대상과 함께 MSBuild 사용

*빌드 대상*은 미리 정의되거나 사용자가 정의한 명령의 명명된 세트로, 빌드하는 동안 실행할 수 있습니다. 대상 명령줄 옵션(`/t`)을 사용하여 빌드 대상을 지정합니다. `myproject` 예제 프로젝트의 경우 미리 정의된 **정리** 대상은 디버그 폴더의 모든 파일을 삭제하고 새 로그 파일을 만듭니다.

명령 프롬프트에서 다음 명령을 입력하여 `myproject`를 정리합니다.

`msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>빌드 속성과 함께 MSBuild 사용

속성 명령줄 옵션(`/p`)을 사용하면 프로젝트 빌드 파일에서 속성을 재정의할 수 있습니다. `myproject` 예제 프로젝트에서, 릴리스 또는 디버그 빌드 구성이 `Configuration` 속성에서 지정되었습니다. 또한 빌드한 애플리케이션을 실행할 운영 체제가 `Platform` 속성에서 지정되었습니다.

명령 프롬프트에서 다음 명령을 입력하여 32비트 Windows에서 실행할 `myproject` 애플리케이션의 디버그 빌드를 만듭니다.

`msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

`myproject` 예제 프로젝트가 64비트 Windows에 대한 구성을 정의하고, `myplatform`이라는 사용자 지정 운영 체제에 대해 다른 구성을 정의한다고 가정해보겠습니다.

명령 프롬프트에서 다음 명령을 입력하여 64비트 Windows에서 실행되는 릴리스 빌드를 만듭니다.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

명령 프롬프트에서 다음 명령을 입력하여 `myplatform`을 위한 릴리스 빌드를 만듭니다.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>64비트 컴파일러 및 도구와 함께 MSBuild 사용

기본적으로 64비트 Windows에 Visual Studio가 설치되어 있는 경우 64비트 x64 네이티브 및 크로스 도구가 설치됩니다. `PreferredToolArchitecture` 속성을 설정하면 64비트 컴파일러 및 도구를 사용하여 애플리케이션을 빌드하도록 MSBuild를 구성할 수 있습니다. 이 속성은 프로젝트 구성 또는 플랫폼 속성에 영향을 주지 않습니다. 기본적으로, 도구의 32비트 버전이 사용됩니다. 64비트 버전의 컴파일러 및 도구를 지정하려면 Myproject.vcxproj 프로젝트 파일에서 `Microsoft.Cpp.default.props`\<Import /> 요소 뒤에 다음 속성 그룹 요소를 추가합니다.

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

64비트 도구를 사용하여 애플리케이션을 빌드하려면 명령 프롬프트에서 다음 명령을 입력합니다.

`msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>다른 도구 집합과 함께 MSBuild 사용

다른 버전의 Visual C++를 위한 도구 집합과 라이브러리가 설치되어 있는 경우 MSBuild는 현재 Visual C++ 버전 또는 다른 설치된 버전을 위한 애플리케이션을 빌드할 수 있습니다. 예를 들어 Visual Studio 2012를 설치한 경우 Windows XP를 위한 Visual C++ 11.0 도구 집합을 지정하려면 Myproject.vcxproj 프로젝트 파일에서 `Microsoft.Cpp.props`\<Import /> 요소 뒤에 다음 속성 그룹 요소를 추가합니다.

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Visual C++ 11.0 Windows XP 도구 집합을 사용하여 프로젝트를 다시 빌드하려면 다음 명령을 입력합니다.

`msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

### <a name="adding-msbuild-customizations"></a>MSBuild 사용자 지정 추가

MSBuild는 빌드 프로세스를 사용자 지정할 수 있는 다양한 방법을 제공합니다. 다음 항목에는 MSBuild 프로젝트에 사용자 지정 빌드 단계, 도구 및 이벤트를 추가하는 방법을 보여줍니다.

- [방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가](how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가](how-to-add-custom-build-tools-to-msbuild-projects.md)

- [방법: MSBuild 프로젝트에서 빌드 이벤트 사용](how-to-use-build-events-in-msbuild-projects.md)
