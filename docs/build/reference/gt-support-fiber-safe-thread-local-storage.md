---
title: -GT(파이버 안전 스레드 로컬 스토리지 지원)
description: MSVC 컴파일러 옵션/GT는 스레드 로컬 저장소 데이터를 안전 하 게 최적화할 수 있도록 합니다.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
ms.openlocfilehash: 1b1d9f6514cec8c3d247f86be063f2ac3e0dfe72
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180814"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>`/GT`(파이버 안전 스레드 로컬 저장소 지원)

정적 스레드 로컬 저장소, 즉로 할당 된 데이터를 사용 하 여 할당 된 데이터의 파이버 안전을 지원 `__declspec(thread)` 합니다.

## <a name="syntax"></a>구문

> **`/GT`**

## <a name="remarks"></a>설명

로 선언 된 데이터 `__declspec(thread)` 는 TLS (스레드 로컬 저장소) 배열을 통해 참조 됩니다. TLS 배열은 각 스레드에 대해 시스템에서 유지 관리 하는 주소 배열입니다. 이 배열의 각 주소는 스레드 로컬 저장소 데이터의 위치를 제공 합니다.

파이버는 스택 및 레지스터 컨텍스트로 구성 되며 다양 한 스레드에서 예약할 수 있는 경량 개체입니다. 파이버는 모든 스레드에서 실행할 수 있습니다. 파이버는 다른 스레드에서 교체 되 고 나중에 다시 시작 될 수 있으므로 컴파일러는 TLS 배열의 주소를 캐시 하거나 함수 호출에서 공용 하위 식으로 최적화 되어서는 안됩니다 합니다. **`/GT`** 는 이러한 최적화를 방지 합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**  >  **C/c + +**  >  **최적화** 속성 페이지를 선택 합니다.

1. **파이버 안전 최적화 사용** 속성을 수정 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
