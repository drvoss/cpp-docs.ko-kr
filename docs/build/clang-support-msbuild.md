---
title: Visual Studio Visual Studio 프로젝트의 Clang/LLVM 지원
ms.date: 08/30/2019
ms.description: Configure a Visual Studio MSBuild project to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ MSBuild projects
ms.openlocfilehash: 819f96bf2fd949f80ae72ca878ba7eb9cb1bffcc
ms.sourcegitcommit: c3283062ce4e382aec7f11626d358a37caf8cdbb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2020
ms.locfileid: "75914356"
---
# <a name="clangllvm-support-in-visual-studio-projects"></a>Visual Studio 프로젝트의 Clang/LLVM 지원

::: moniker range="<=vs-2017"

CMake 및 MSBuild 프로젝트 모두에 대 한 지원은 Visual Studio 2019에서 사용할 수 있습니다.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 버전 16.2을 사용 하 여 Windows 또는 Linux를 대상으로 하는 C++ visual studio 프로젝트 (MSBuild)를 편집, 빌드 및 디버그할 수 있습니다.

## <a name="install"></a>설치

Visual Studio에서 최상의 IDE를 지원 하려면 Windows 용 최신 Clang 컴파일러 도구를 사용 하는 것이 좋습니다. 이러한 항목이 아직 없는 경우 Visual Studio 설치 관리자를 열고 선택적 구성 요소 **를 사용 하 C++ 여 데스크톱 개발** 에서  **C++ Clang tools for Windows를** 선택 하 여 설치할 수 있습니다. 컴퓨터에서 기존 Clang 설치를 사용 하려는 경우  **C++ Clang-cl for v142 build tools를 선택 합니다.** 선택적 구성 요소입니다. Microsoft C++ Standard Library에는 현재 Clang 8.0.0 이상이 필요 합니다. Clang의 번들 버전은 Microsoft의 표준 라이브러리 구현에서 업데이트를 최신 상태로 유지 하도록 자동으로 업데이트 됩니다. 

![Clang 구성 요소 설치](media/clang-install-vs2019.png)

## <a name="configure-a-windows-project-to-use-clang-tools"></a>Clang tools를 사용 하도록 Windows 프로젝트 구성

Clang를 사용 하도록 Visual Studio 프로젝트를 구성 하려면 **솔루션 탐색기** 에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다. 일반적으로 대화 상자 위쪽의 **모든 구성** 을 먼저 선택 해야 합니다. 그런 다음 **일반** > **플랫폼 도구 집합**에서 **LLVM (clang)** 를 선택 하 고 **확인**을 선택 합니다.

![Clang 구성 요소 설치](media/clang-msbuild-prop-page.png)

Visual Studio와 함께 제공 되는 Clang 도구를 사용 하는 경우 추가 단계가 필요 하지 않습니다. Windows 프로젝트의 경우 Visual Studio는 기본적으로 Clang 모드에서 Clang를 호출 하 고 표준 라이브러리의 Microsoft 구현에 대 한 링크를 [제공](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) 합니다. 기본적으로 **clang-cl** 는 `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`에 있습니다.

사용자 지정 Clang 설치를 사용 하는 경우 사용자 지정 Clang 설치 루트를 첫 번째 디렉터리로 추가 하거나 `LLVMInstallDir` 속성의 값을 변경 하 여 **실행 가능한 디렉터리** > **구성 속성** 에 대 한 **프로젝트** >  ** >  > ** **속성** 을 수정할 수 있습니다. 자세한 내용은 [사용자 지정 LLVM 위치 설정을](#custom_llvm_location) 참조 하세요.

## <a name="configure-a-linux-project-to-use-clang-tools"></a>Clang 도구를 사용 하도록 Linux 프로젝트 구성

Linux 프로젝트의 경우 Visual Studio는 Clang GCC 호환 프런트 엔드를 사용 합니다. 프로젝트 속성 및 거의 모든 컴파일러 플래그가 동일 합니다.

Clang를 사용 하도록 Visual Studio Linux 프로젝트를 구성 하려면:

1. **솔루션 탐색기** 에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다. 
1. 일반적으로 대화 상자 위쪽의 **모든 구성** 을 먼저 선택 해야 합니다. 
1. **일반** > **플랫폼 도구 집합**에서 Linux 용 Windows 하위 시스템을 사용 하는 경우 **WSL_Clang_1_0** 를 선택 하 고, 원격 컴퓨터 또는 VM을 사용 하는 경우 **Remote_Clang_1_0** 을 선택 합니다.
1. **확인**을 누릅니다.

![Clang 구성 요소 설치](media/clang-msbuild-prop-page.png)

Linux에서 Visual Studio는 기본적으로 PATH 환경 속성에서 발견 된 첫 번째 Clang 위치를 사용 합니다. 사용자 지정 Clang 설치를 사용 하는 경우에는 `LLVMInstallDir` 속성의 값을 변경 하거나 **프로젝트** > **속성** > **VC + + 디렉터리** > **구성 속성** > **실행 가능 디렉터리로**경로를 대체 해야 합니다. 자세한 내용은 [사용자 지정 LLVM 위치 설정을](#custom_llvm_location) 참조 하세요.

## <a name="custom_llvm_location"></a>사용자 지정 LLVM 위치 설정

LLVM 파일을 만들고 해당 파일을 프로젝트의 루트 폴더에 추가 하 여 하나 이상의 프로젝트에 대해 사용자 지정 경로를 설정할 수 *있습니다.* 루트 솔루션 폴더에 추가 하 여 솔루션의 모든 프로젝트에 적용할 수 있습니다. 파일은 다음과 같이 표시 됩니다 (그러나 실제 경로로 대체).

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>c:\MyLLVMRootDir</LLVMInstallDir>
  </PropertyGroup>
</Project>
```

## <a name="set-additional-properties-edit-build-and-debug"></a>추가 속성 설정, 편집, 빌드 및 디버그

Clang 구성을 설정한 후 프로젝트 노드를 다시 마우스 오른쪽 단추로 클릭 하 고 **프로젝트 다시 로드**를 선택 합니다. 이제 Clang 도구를 사용 하 여 프로젝트를 빌드하고 디버그할 수 있습니다. Visual Studio는 Clang 컴파일러를 사용 하 고 있으며 IntelliSense, 강조 표시, 탐색 및 기타 편집 기능을 제공 합니다. 오류 및 경고는 **출력 창**표시 됩니다. Clang 구성에 대 한 프로젝트 속성 페이지는 MSVC의 경우와 매우 유사 하지만, 편집 하며 계속 하기와 같은 일부 컴파일러 종속 기능은 Clang 구성에 사용할 수 없습니다. 속성 페이지에서 사용할 수 없는 Clang 컴파일러 또는 링커 옵션을 설정 하려면 **추가 옵션** > **구성 속성** > **C++ C/(또는 링커)**  > **명령줄** 의 속성 페이지에서 수동으로 추가할 수 있습니다.

디버깅 하는 경우 중단점, 메모리 및 데이터 시각화 및 대부분의 기타 디버깅 기능을 사용할 수 있습니다.  

![Clang 디버깅](media/clang-debug-msbuild.png)

::: moniker-end
