---
title: Visual Studio Ctoprojects의 Clang/LLVM 지원
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ CMake projects
ms.openlocfilehash: a71f9dc98f74247788558d1b7dccf3e117f43072
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77416018"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Visual Studio Ctoprojects의 Clang/LLVM 지원

::: moniker range="<=vs-2017"

Clang 지원은 Visual Studio 2019에서 사용할 수 있습니다.

::: moniker-end

::: moniker range="vs-2019"

Clang와 함께 Visual Studio를 사용 하 여 Windows 또는 C++ Linux를 대상으로 하는 cmake 프로젝트를 편집 하 고 디버그할 수 있습니다.

**Windows**: Visual Studio 2019 버전 16.1에는 windows를 대상으로 하는 cmake 프로젝트에서 CLANG/LLVM를 사용 하 여 편집, 빌드 및 디버깅 하는 기능이 포함 되어 있습니다.

**Linux**: linux cmake 프로젝트의 경우 특별 한 Visual Studio 지원이 필요 하지 않습니다. 배포판의 패키지 관리자를 사용 하 여 Clang을 설치 하 고 CMakeLists .txt 파일에 적절 한 명령을 추가할 수 있습니다.

## <a name="install"></a>Install

Visual Studio에서 최상의 IDE를 지원 하려면 Windows 용 최신 Clang 컴파일러 도구를 사용 하는 것이 좋습니다. 이러한 항목이 아직 없는 경우 Visual Studio 설치 관리자를 열고 선택적 구성 요소 **를 사용 하 여 C++ 데스크톱 개발** 에서  **C++ Windows 용 Clang 컴파일러** 를 선택 하 여 설치할 수 있습니다. 사용자 지정 Clang 설치를 사용 하는 경우  **C++ Clang-cl for v142 build tools** 구성 요소를 확인 합니다.

![Clang 구성 요소 설치](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>새 구성 만들기

CMake 프로젝트에 새 Clang 구성을 추가 하려면 다음을 수행 합니다.

1. **솔루션 탐색기** 에서 CMakeLists .txt를 마우스 오른쪽 단추로 클릭 하 고 **프로젝트에 대 한 csettings 설정**을 선택 합니다.

1. 구성 **아래에서** **구성 추가** 단추를 누릅니다.

   ![구성 추가](media/cmake-add-config-icon.png)

1. 원하는 Clang 구성 (Windows 및 Linux에 대 한 별도의 Clang 구성이 제공 됨)을 선택 하 고 **선택**을 누릅니다.

   ![CMake 구성](media/cmake-clang-configuration.png)

1. 이 구성을 수정 하려면 **Cmake 설정 편집기**를 사용 합니다. 자세한 내용은 [Visual Studio에서 cmake 빌드 설정 사용자 지정](customize-cmake-settings.md)을 참조 하세요.

## <a name="modify-an-existing-configuration-to-use-clang"></a>Clang를 사용 하도록 기존 구성 수정

Clang를 사용 하도록 기존 구성을 수정 하려면 다음 단계를 수행 합니다.

1. **솔루션 탐색기** 에서 CMakeLists .txt를 마우스 오른쪽 단추로 클릭 하 고 **프로젝트에 대 한 csettings 설정**을 선택 합니다.

1. **일반** 에서 **도구 집합** 드롭다운을 선택 하 고 원하는 Clang 도구 집합을 선택 합니다.

   ![CMake 도구 집합](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>사용자 지정 Clang 위치

기본적으로 Visual Studio는 다음 두 위치에서 Clang를 찾습니다.

- Windows Visual Studio 설치 관리자와 함께 제공 되는 Clang/LLVM의 내부적으로 설치 된 복사본입니다.
- (Windows 및 Linux) PATH 환경 변수입니다.

**CMAKE_C_COMPILER** 를 설정 하 고 **cmake 설정에서 cmake**변수를 **CMAKE_CXX_COMPILER** 하 여 다른 위치를 지정할 수 있습니다.

![CMake 도구 집합](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Clang 호환 모드

Windows 구성의 경우 CMake는 기본적으로 [Clang](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) 모드로 실행 되 고 표준 라이브러리의 Microsoft 구현에 연결 된 링크를 호출 합니다. 기본적으로 **clang-cl** 는 `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`에 있습니다.

**Ctovariables 및 cache**의 **cmake 설정** 에서 이러한 값을 수정할 수 있습니다. **고급 변수 표시**를 클릭 합니다. 아래로 스크롤하여 **CMAKE_CXX_COMPILER**를 찾은 다음 **찾아보기** 단추를 클릭 하 여 다른 컴파일러 경로를 지정 합니다.

## <a name="edit-build-and-debug"></a>편집, 빌드 및 디버그

Clang 구성을 설정한 후 프로젝트를 빌드하고 디버그할 수 있습니다. Visual Studio는 Clang 컴파일러를 사용 하 고 있으며 IntelliSense, 강조 표시, 탐색 및 기타 편집 기능을 제공 합니다. 오류 및 경고는 **출력 창**표시 됩니다.

디버깅 하는 경우 중단점, 메모리 및 데이터 시각화 및 대부분의 기타 디버깅 기능을 사용할 수 있습니다. 편집 하며 계속 하기와 같은 일부 컴파일러 종속 기능은 Clang 구성에 사용할 수 없습니다.

![CMake 디버깅](media/clang-debug-visualize.png)

::: moniker-end
