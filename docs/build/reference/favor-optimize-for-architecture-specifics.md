---
title: /favor(아키텍처에 맞게 최적화)
ms.date: 11/04/2016
f1_keywords:
- /favor
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
ms.openlocfilehash: b914d3e6e7a2865ec610249ff51d320d7890adcb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292824"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor(아키텍처에 맞게 최적화)

**/favor:** `option`은 AMD 및 Intel 아키텍처에서 마이크로 아키텍처나 특정 아키텍처에 최적화된 코드를 생성합니다.

## <a name="syntax"></a>구문

> **/favor:** {0}**blend** | **ATOM** | **AMD64** | **INTEL64**}

## <a name="remarks"></a>설명

**/favor:blend**<br/>
(x86 및 x64) AMD 및 Intel 아키텍처의 마이크로 아키텍처 사양에 맞게 최적화된 코드를 생성합니다. **/favor:blend**는 특정 프로세서에서 최상의 성능을 제공하지 못할 수도 있지만 광범위한 x86 및 x64 프로세서에서 최상의 성능을 제공하도록 설계되었습니다. 기본적으로 **/favor:blend**가 적용됩니다.

**/favor:ATOM**<br/>
(x86 및 x64) Intel Atom 프로세서 및 Intel Centrino Atom 프로세서 기술 사양에 맞게 최적화된 코드를 생성합니다. **/favor:ATOM**을 사용하여 생성된 코드는 Intel 프로세서를 위한 Intel SSSE3, SSE3, SSE2 및 SSE 명령도 생성할 수 있습니다.

**/favor:AMD64**<br/>
(x64 전용) AMD Opteron 및 64비트 확장을 지원하는 Athlon 프로세서를 위해 생성된 코드를 최적화합니다. 최적화된 코드는 모든 x64 호환 플랫폼에서 실행할 수 있습니다. **/favor:AMD64**를 사용하여 생성된 코드는 Intel64를 지원하는 Intel 프로세서에서는 성능 저하를 야기할 수 있습니다.

**/favor:INTEL64**<br/>
(x64 전용) Intel64를 지원하는 Intel 프로세서에 대해 생성된 코드를 최적화하며 일반적으로 해당 플랫폼에서 더 나은 성능을 제공합니다. 결과 코드는 모든 x64 플랫폼에서 실행할 수 있습니다. **/favor:INTEL64**로 생성된 코드는 AMD Opteron 및 64비트 확장을 지원하는 Athlon 프로세서에서 성능 저하를 야기할 수 있습니다.

> [!NOTE]
> Intel64 아키텍처는 이전에 Extended Memory 64 Technology로 알려져 있었으며 해당 컴파일러 옵션은 **/favor:EM64T** 였습니다.

x64 아키텍처를 대상으로 하는 프로그래밍 방법에 대한 정보는 [x64 소프트웨어 규칙](../x64-software-conventions.md)을 참조합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 선택합니다.

1. **명령줄** 속성 페이지를 선택합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
