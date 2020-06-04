---
title: OpenMP 라이브러리 참조
ms.date: 12/02/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: b61eb356b782b3cd17557827734a706e0761a2a8
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810744"
---
# <a name="openmp-library-reference"></a>OpenMP 라이브러리 참조

OpenMP API에서 사용하는 구문에 대한 링크를 제공합니다.

OpenMP 표준의 Visual C++ 구현에는 다음 구문이 포함됩니다.

|생성|설명|
|---------------|-----------------|
|[지시문](openmp-directives.md)|OpenMP API에서 사용되는 지시문에 대한 링크를 제공합니다.|
|[절](openmp-clauses.md)|OpenMP API에서 사용되는 절에 대한 링크를 제공합니다.|
|[함수](openmp-functions.md)|OpenMP API에서 사용되는 함수에 대한 링크를 제공합니다.|
|[환경 변수](openmp-environment-variables.md)|OpenMP API에서 사용되는 환경 변수에 대한 링크를 제공합니다.|

Visual C++ OpenMP 런타임 라이브러리 함수는 다음 라이브러리에 포함 되어 있습니다.

|OpenMP 런타임 라이브러리|특징|
|------------------------------|---------------------|
|VCOMP.LIB|다중 스레드, 동적 링크 (VCOMP140에 대 한 가져오기 라이브러리) DLL).|
|VCOMPD.LIB|다중 스레드, 동적 링크 (VCOMP140D에 대 한 가져오기 라이브러리) DLL) (디버그)|

_Debug가 컴파일에서 정의되어 있고 `#include <omp.h>`가 소스코드에 있는 경우 VCOMPD.LIB가 기본 라이브러리가 되고, 그렇지 않은 경우 VCOMP.LIB가 사용됩니다.

[/NODEFAULTLIB (라이브러리 무시)](../../../build/reference/nodefaultlib-ignore-libraries.md)를 사용하여 기본 라이브러리를 제거하고 원하는 라이브러리와 명시적으로 연결할 수 있습니다.

OpenMP Dll은 Visual C++ 재배포 패키지 디렉터리에 있으며 OpenMP를 사용하는 응용 프로그램과 함께 배포해야 합니다.

## <a name="see-also"></a>참조

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)
