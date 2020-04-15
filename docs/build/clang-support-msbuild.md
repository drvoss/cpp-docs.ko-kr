---
title: 비주얼 스튜디오 비주얼 스튜디오 프로젝트에서 Clang/LLVM 지원
ms.date: 08/30/2019
ms.description: Configure a Visual Studio MSBuild project to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ MSBuild projects
ms.openlocfilehash: 8d7d7fec979d3e7b8f665e56094ee1c309e3b686
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323112"
---
# <a name="clangllvm-support-in-visual-studio-projects"></a>비주얼 스튜디오 프로젝트에서 Clang/LLVM 지원

::: moniker range="<=vs-2017"

CMake 및 MSBuild 프로젝트에 대한 Clang 지원은 Visual Studio 2019에서 사용할 수 있습니다.

::: moniker-end

::: moniker range="vs-2019"

Clang과 함께 Visual Studio 2019 버전 16.2를 사용하여 Windows 또는 Linux를 대상으로 하는 C++ Visual Studio 프로젝트(MSBuild)를 편집, 빌드 및 디버깅할 수 있습니다.

## <a name="install"></a>설치

Visual Studio에서 최상의 IDE 지원을 위해 Windows용 최신 Clang 컴파일러 도구를 사용하는 것이 좋습니다. 아직 없는 경우 Visual Studio 설치 관리자를 열고 **C++** 선택적 구성 요소를 사용하여 데스크톱 개발 중인 **Windows용 C++ Clang 도구를** 선택하여 설치할 수 있습니다. 컴퓨터에 기존 Clang 설치를 사용하려면 **v142 빌드 도구에 대해 C++ Clang-cl을 선택합니다.** 선택적 구성 요소입니다. Microsoft C++ 표준 라이브러리에는 현재 최소 Clang 8.0.0이 필요합니다. 번들 버전의 Clang은 표준 라이브러리의 Microsoft 구현에서 업데이트된 최신 상태로 유지하도록 자동으로 업데이트됩니다.

![Clang 부품 설치](media/clang-install-vs2019.png)

## <a name="configure-a-windows-project-to-use-clang-tools"></a>Clang 도구를 사용하도록 Windows 프로젝트 구성

Clang을 사용하도록 Visual Studio 프로젝트를 구성하려면 **솔루션 탐색기에서** 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성을**선택합니다. 일반적으로 먼저 대화 상자 맨 위에 있는 **모든 구성을** 선택해야 합니다. 그런 다음 **일반** > **플랫폼 도구 집합에서** **LLVM (clang-cl)을** 선택한 다음 **확인합니다.**

![Clang 부품 설치](media/clang-msbuild-prop-page.png)

Visual Studio와 함께 제공되는 Clang 도구를 사용하는 경우 추가 단계가 필요하지 않습니다. Windows 프로젝트의 경우 Visual Studio는 기본적으로 [Clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) 모드에서 Clang을 호출하고 표준 라이브러리의 Microsoft 구현과 연결합니다. 기본적으로 **clang-cl.exe는** 에 `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`있습니다.

사용자 지정 Clang 설치를 사용하는 경우 **사용자 지정** > Clang 설치 루트를 첫 번째 디렉터리로 추가하여 프로젝트**속성** > **VC++ DIrectories** > **구성** > 실행 `LLVMInstallDir` 가능한**디렉토리를** 수정하거나 속성 값을 변경할 수 있습니다. 자세한 내용은 [사용자 지정 LLVM 위치 설정을](#custom_llvm_location) 참조하십시오.

## <a name="configure-a-linux-project-to-use-clang-tools"></a>Clang 도구를 사용하도록 Linux 프로젝트 구성

리눅스 프로젝트의 경우 Visual Studio는 Clang GCC 호환 프론트엔드를 사용합니다. 프로젝트 속성과 거의 모든 컴파일러 플래그는 동일합니다.

Clang을 사용하도록 Visual Studio Linux 프로젝트를 구성하려면 다음을 수행하십시오.

1. **솔루션 탐색기에서** 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성을**선택합니다.
1. 일반적으로 먼저 대화 상자 맨 위에 있는 **모든 구성을** 선택해야 합니다.
1. **일반** > **플랫폼 도구 집합에서**Linux용 Windows 서브시스템을 사용하는 경우 **WSL_Clang_1_0** 선택하거나 원격 컴퓨터 또는 VM을 사용하는 경우 **Remote_Clang_1_0.**
1. **확인**을 누릅니다.

![Clang 부품 설치](media/clang-msbuild-prop-page.png)

Linux에서 Visual Studio는 기본적으로 PATH 환경 속성에서 발생하는 첫 번째 Clang 위치를 사용합니다. 사용자 `LLVMInstallDir` 지정 Clang 설치를 사용하는 경우 속성 값을 변경하거나 **프로젝트** > **속성** > **VC++ DIrectories** > **구성** > 속성 실행**방법에서**경로를 대체해야 합니다. 자세한 내용은 [사용자 지정 LLVM 위치 설정을](#custom_llvm_location) 참조하십시오.

## <a name="set-a-custom-llvm-location"></a><a name="custom_llvm_location"></a>사용자 지정 LLVM 위치 설정

*Directory.build.props* 파일을 만들고 해당 파일을 모든 프로젝트의 루트 폴더에 추가하여 하나 이상의 프로젝트에 대한 LLVM에 대한 사용자 지정 경로를 설정할 수 있습니다. 루트 솔루션 폴더에 추가하여 솔루션의 모든 프로젝트에 적용할 수 있습니다. 파일은 다음과 같아야합니다 (그러나 실제 경로를 대체하십시오).

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>c:\MyLLVMRootDir</LLVMInstallDir>
  </PropertyGroup>
</Project>
```

## <a name="set-additional-properties-edit-build-and-debug"></a>추가 속성 설정, 편집, 빌드 및 디버그

Clang 구성을 설정한 후 프로젝트 노드에서 다시 마우스 오른쪽 단추로 클릭하고 **프로젝트 다시로드를**선택합니다. 이제 Clang 도구를 사용하여 프로젝트를 빌드하고 디버깅할 수 있습니다. Visual Studio는 Clang 컴파일러를 사용하고 있음을 감지하고 IntelliSense, 강조 표시, 탐색 및 기타 편집 기능을 제공합니다. 오류 및 경고가 **출력 창에**표시됩니다. Clang 구성에 대한 프로젝트 속성 페이지는 MSVC의 경우와 매우 유사하지만 Clang 구성에는 편집 및 계속과 같은 일부 컴파일러 종속 기능을 사용할 수 없습니다. 속성 페이지에서 사용할 수 없는 Clang 컴파일러 또는 링커 옵션을 설정하려면 **구성 속성** > **C/C++ (또는 Linker)** > **명령줄** > 추가 옵션 아래의 속성 페이지에 수동으로 추가할 수**있습니다.**

디버깅 할 때 중단점, 메모리 및 데이터 시각화 및 대부분의 다른 디버깅 기능을 사용할 수 있습니다.  

![Clang 디버깅](media/clang-debug-msbuild.png)

::: moniker-end
