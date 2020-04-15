---
title: 비주얼 스튜디오에서 Clang-Tidy 사용
description: Microsoft C++ 코드 분석을 위해 비주얼 스튜디오에서 Clang-Tidy를 사용하는 방법.
ms.date: 02/19/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
author: frozenpandaman
ms.author: efessler
ms.openlocfilehash: ff32f522eaacee67e19aedaa1153b2c68edc98d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355160"
---
# <a name="using-clang-tidy-in-visual-studio"></a>비주얼 스튜디오에서 Clang-Tidy 사용

::: moniker range="<=vs-2017"

Clang-Tidy에 대한 지원은 Visual Studio 2019 버전 16.4 이상이 필요합니다. 이 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end

::: moniker range=">=vs-2019"

코드 분석은 기본적으로 Clang 또는 MSVC 도구 집합을 사용하든 MSBuild 및 CMake 프로젝트 모두에 대해 [Clang-Tidy를](https://clang.llvm.org/extra/clang-tidy/) 지원합니다. Clang-Tidy 검사는 백그라운드 코드 분석의 일부로 실행할 수 있습니다. 편집기 내 경고(물결선)로 표시되고 오류 목록에 표시됩니다.

Clang-Tidy 지원은 Visual Studio 2019 버전 16.4부터 사용할 수 있습니다. Visual Studio 설치 관리자에서 C++ 워크로드를 선택하면 자동으로 포함됩니다.

Clang-Tidy는 MSBuild 및 CMake모두에서 사용할 수 있는 LLVM/clang-cl 도구 집합을 사용할 때 기본 분석 도구입니다. MSVC 도구 집합을 사용하여 표준 코드 분석 환경과 함께 실행하거나 대체할 때 구성할 수 있습니다. clang-cl 도구 집합을 사용하는 경우 Microsoft 코드 분석을 사용할 수 없습니다.

Clang-Tidy는 성공적인 편집 후에 실행됩니다. Clang-Tidy 결과를 얻으려면 소스 코드 오류를 해결해야 할 수 있습니다.

## <a name="msbuild"></a>MSBuild

Clang-Tidy를 코드 분석의 일부로 실행하고 프로젝트 속성 창의 **코드 분석** > **일반** 페이지에서 빌드하도록 구성할 수 있습니다. 도구를 구성하는 옵션은 Clang-Tidy 하위 메뉴에서 찾을 수 있습니다.

자세한 내용은 [C/C++ 프로젝트에 대한 코드 분석 속성 설정 방법을](../code-quality/how-to-set-code-analysis-properties-for-c-cpp-projects.md)참조하십시오.

## <a name="cmake"></a>CMake

CMake 프로젝트에서 는 내에서 `CMakeSettings.json`Clang-Tidy 검사를 구성할 수 있습니다. 열면 CMake 프로젝트 설정 편집기의 오른쪽 상단 모서리에 있는 "JSON 편집"을 클릭합니다. 다음 키가 인식됩니다.

- `enableMicrosoftCodeAnalysis`: 마이크로소프트 코드 분석 가능
- `enableClangTidyCodeAnalysis`: Clang-깔끔한 분석 가능
- `clangTidyChecks`: 쉼표로 분리된 목록으로 지정된 Clang-Tidy 구성, 즉 사용 가능또는 비활성화할 지 확인

"사용" 옵션을 모두 지정하지 않으면 Visual Studio에서 사용된 플랫폼 도구 집합과 일치하는 분석 도구를 선택합니다.

## <a name="warning-display"></a>경고 표시

Clang-Tidy 실행은 오류 목록에 경고가 표시되고 코드의 관련 섹션 아래에 있는 편집기 내 물결선으로 나타납니다. 오류 목록의 "범주" 열을 사용하여 Clang-Tidy 경고를 정렬하고 구성합니다. **도구** > **옵션에서**"코드 분석 스퀴글 사용 안 함" 설정을 전환하여 편집기 내 경고를 구성할 수 있습니다.

## <a name="clang-tidy-configuration"></a>Clang-깔끔한 구성

**Clang-Tidy** 검사 옵션을 통해 Visual Studio 내에서 clang-tidy가 실행되는 검사를 구성할 수 있습니다. 이 입력은 도구의 **--checks** 인수에 제공됩니다. 추가 구성은 사용자 지정 *`.clang-tidy`* 파일에 포함될 수 있습니다. 자세한 내용은 LLVM.org [대한 Clang-Tidy 설명서를](https://clang.llvm.org/extra/clang-tidy/)참조하십시오.

## <a name="see-also"></a>참고 항목

- [MSBuild 프로젝트에 대한 Clang/LLVM 지원](https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/)
- [CMake 프로젝트를 위한 Clang/LLVM 지원](https://devblogs.microsoft.com/cppblog/visual-studio-cmake-support-clang-llvm-cmake-3-14-vcpkg-and-performance-improvements/)

::: moniker-end
