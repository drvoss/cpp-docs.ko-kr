---
title: 비주얼 스튜디오 CMake 프로젝트에서 Clang/LLVM 지원
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ CMake projects
ms.openlocfilehash: 46bfe788c13df3a37dd9cba654d16cfe4c3fe177
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323188"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>비주얼 스튜디오 CMake 프로젝트에서 Clang/LLVM 지원

::: moniker range="<=vs-2017"

Clang 지원은 Visual Studio 2019에서 사용할 수 있습니다.

::: moniker-end

::: moniker range="vs-2019"

Clang이 있는 Visual Studio를 사용하여 Windows 또는 Linux를 대상으로 하는 C++ CMake 프로젝트를 편집하고 디버깅할 수 있습니다.

**Windows**: Visual Studio 2019 버전 16.1에는 Windows를 대상으로 하는 CMake 프로젝트에서 Clang/LLVM을 통한 편집, 빌드 및 디버깅지원이 포함되어 있습니다.

**Linux**: Linux CMake 프로젝트의 경우 특별한 비주얼 스튜디오 지원이 필요하지 않습니다. 배포자의 패키지 관리자를 사용 하 여 Clang를 설치할 수 있습니다., CMakeLists.txt 파일에 적절 한 명령을 추가.

## <a name="install"></a>설치

Visual Studio에서 최상의 IDE 지원을 위해 Windows용 최신 Clang 컴파일러 도구를 사용하는 것이 좋습니다. 아직 없는 경우 Visual Studio 설치 관리자를 열고 **C++** 선택적 구성 요소를 사용하여 데스크톱 개발 중인 **Windows용 C++ Clang 컴파일러를** 선택하여 설치할 수 있습니다. 사용자 지정 Clang 설치를 사용하는 경우 v142 빌드 도구 구성 요소에 **대한 C++ Clang-cl을** 확인합니다.

![Clang 부품 설치](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>새 구성 만들기

CMake 프로젝트에 새 Clang 구성을 추가하려면 다음을 수행하십시오.

1. **솔루션 탐색기에서** CMakeLists.txt를 마우스 오른쪽 단추로 클릭하고 **프로젝트에 대한 CMake 설정을**선택합니다.

1. **구성에서** **구성 추가** 단추를 누릅니다.

   ![구성 추가](media/cmake-add-config-icon.png)

1. 원하는 Clang 구성을 선택한 다음(Windows 및 Linux용으로 별도의 Clang 구성이 제공된다는 점에 유의하십시오)을 선택한 다음 **선택을**누릅니다.

   ![CMake Clang 구성](media/cmake-clang-configuration.png)

1. 이 구성을 수정하려면 **CMake 설정 편집기를**사용합니다. 자세한 내용은 [Visual Studio에서 CMake 빌드 설정 사용자 지정을](customize-cmake-settings.md)참조하십시오.

## <a name="modify-an-existing-configuration-to-use-clang"></a>Clang을 사용하도록 기존 구성 수정

Clang을 사용하도록 기존 구성을 수정하려면 다음 단계를 따르십시오.

1. **솔루션 탐색기에서** CMakeLists.txt를 마우스 오른쪽 단추로 클릭하고 **프로젝트에 대한 CMake 설정을**선택합니다.

1. **일반적으로** 도구 **집합** 드롭다운을 선택하고 원하는 Clang 도구 집합을 선택합니다.

   ![CMake Clang 도구 세트](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>사용자 정의 Clang 위치

기본적으로 Visual Studio는 다음 두 위치에서 Clang을 찾습니다.

- (윈도우) Visual Studio 설치 관리자와 함께 제공되는 Clang/LLVM의 내부적으로 설치된 복사본입니다.
- (윈도우와 리눅스) PATH 환경 변수입니다.

**CMake 설정에서** **CMAKE_C_COMPILER** 및 **CMAKE_CXX_COMPILER** CMake 변수를 설정하여 다른 위치를 지정할 수 있습니다.

![CMake Clang 도구 세트](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Clang 호환성 모드

Windows 구성의 경우 CMake는 기본적으로 [Clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) 모드에서 Clang을 호출하고 표준 라이브러리의 Microsoft 구현과 연결합니다. 기본적으로 **clang-cl.exe는** 에 `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`있습니다.

**CMake 변수 및 캐시**에서 **CMake 설정에서** 이러한 값을 수정할 수 있습니다. **고급 변수 표시를 클릭합니다.** 아래로 스크롤하여 **CMAKE_CXX_COMPILER**찾은 다음 **찾아보기** 단추를 클릭하여 다른 컴파일러 경로를 지정합니다.

## <a name="edit-build-and-debug"></a>편집, 빌드 및 디버그

Clang 구성을 설정한 후 프로젝트를 빌드하고 디버깅할 수 있습니다. Visual Studio는 Clang 컴파일러를 사용하고 있음을 감지하고 IntelliSense, 강조 표시, 탐색 및 기타 편집 기능을 제공합니다. 오류 및 경고가 **출력 창에**표시됩니다.

디버깅 할 때 중단점, 메모리 및 데이터 시각화 및 대부분의 다른 디버깅 기능을 사용할 수 있습니다. Clang 구성에는 편집 및 계속과 같은 일부 컴파일러 종속 기능을 사용할 수 없습니다.

![CMake Clang 디버깅](media/clang-debug-visualize.png)

::: moniker-end
