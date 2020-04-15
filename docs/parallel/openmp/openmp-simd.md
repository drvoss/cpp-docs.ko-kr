---
title: SIMD 확장
ms.date: 03/20/2019
helpviewer_keywords:
- SIMD
- OpenMP in Visual C++, new features
- explicit parallelization, new features
ms.openlocfilehash: 0a7f1142a3a432628795341f4885b76a5c144990
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366461"
---
# <a name="simd-extension"></a>SIMD 확장

Visual C++는 현재 OpenMP 2.0 표준을 지원하지만 Visual Studio 2019는 이제 SIMD 기능도 제공합니다.

> [!NOTE]
> SIMD를 사용하려면 스위치를 `-openmp:experimental` 사용할 때 추가 OpenMP 기능을 `-openmp` 사용할 수 없는 스위치로 컴파일합니다.
>
> `-openmp:experimental` 모든 OpenMP `-openmp`2.0 기능을 의미하는 스위치 서브섬이 사용에 포함되어 있습니다.

자세한 내용은 [비주얼 스튜디오에서 C++ OpenMP에 대한 SIMD 확장을](https://devblogs.microsoft.com/cppblog/simd-extension-to-c-openmp-in-visual-studio/)참조하십시오.

## <a name="openmp-simd-in-visual-c"></a>비주얼 C++ OpenMP SIMD

OpenMP 4.0 표준에 도입된 OpenMP SIMD는 벡터 친화적 인 루프를 만드는 것을 목표로합니다. 컴파일러는 `simd` 루프 전에 지시문을 사용하여 벡터 종속성을 무시하고 루프를 가능한 한 벡터 친화적으로 만들고 여러 루프 반복을 동시에 실행하려는 사용자의 의도를 존중할 수 있습니다.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Visual C++는 유사한 비OpenMP 루프 `#pragma vector` pragmas를 제공하며 `#pragma ivdep`OpenMP SIMD를 사용하면 컴파일러가 다음과 같이 더 많은 작업을 수행할 수 있습니다.

- 항상 현재 벡터 종속성을 무시할 수 있습니다.
- `/fp:fast`루프 내에서 활성화됩니다.
- 함수 호출이 있는 외부 루프 및 루프는 벡터 친화적입니다.
- 중첩 루프는 하나의 루프로 결합하여 벡터 친화적으로 만들 수 있습니다.
- 거친 그레인 멀티 스레딩 및 세분화된 `#pragma omp for simd` 벡터를 가능하게 하는 하이브리드 가속.  

벡터 친화적인 루프의 경우 벡터 지원 로그 스위치를 사용하지 않는 한 컴파일러는 자동으로 유지됩니다.

```cmd
    cl -O2 -openmp:experimental -Qvec-report:2 mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(96) : info C5001: Omp simd loop vectorized
```

벡터 친화적이지 않은 루프의 경우 컴파일러는 각 메시지를 발행합니다.

```cmd
    cl -O2 -openmp:experimental mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
```

### <a name="clauses"></a>절

OpenMP SIMD 지시문은 벡터 지원을 향상시키기 위해 다음 절을 취할 수도 있습니다.

|지시문|Description|
|---|---|
|`simdlen(length)`|벡터 차선 수를 지정합니다.|
|`safelen(length)`|벡터 종속성 거리를 지정합니다.|
|`linear(list[ : linear-step]`)|루프 유도 변수에서 배열 구독으로의 선형 매핑입니다.|
|`aligned(list[ : alignment])`|데이터 정렬입니다.|
|`private(list)`|데이터 민영화를 지정합니다.|
|`lastprivate(list)`|마지막 반복에서 최종 값으로 데이터 민영화를 지정합니다.|
|`reduction(reduction-identifier:list)`|사용자 지정된 감소 작업을 지정합니다.|
|`collapse(n)`|결합 루프 둥지.|

> [!NOTE]
> 비유효 SIMD 절은 경고와 함께 컴파일러에 의해 구문 분석되고 무시됩니다.
>
> 예를 들어 다음 코드를 사용하면 다음과 같은 경고가 발생합니다.
>
> ```c
>    #pragma omp simd simdlen(8)
>    for (i = 0; i < count; i++)
>    {
>        a[i] = a[i-1] + 1;
>        b[i] = *c + 1;
>        bar(i);
>    }
> ```
>
> ```Output
>    warning C4849: OpenMP 'simdlen' clause ignored in 'simd' directive
> ```

### <a name="example"></a>예제
  
OpenMP SIMD 지시문은 컴파일러가 벡터 친화적인 루프를 만드는 방법을 사용자에게 제공합니다. OpenMP SIMD 지시문으로 루프에 추가하면 여러 루프 반복이 동시에 실행됩니다.

예를 들어 다음 루프는 OpenMP SIMD 지시문으로 추가됩니다. [i]에서 a[i]로 의 역속성이 있기 때문에 루프 반복 간에 완벽한 병렬 처리는 없지만 SIMD 지시문으로 인해 컴파일러는 여전히 첫 번째 문의 연속 반복을 하나의 벡터 명령으로 압축하고 병렬로 실행할 수 있습니다.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

따라서 컴파일러가 각 원래 루프 반복의 순차적 동작을 유지하므로 루프의 다음 변환된 벡터 형식은 **합법적입니다.** 즉, `a[i]` `a[-1]`다음에 `b[i]` 실행되고 마지막으로 `a[i]` `bar` 발생하는 호출이 수행됩니다.

```c
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        b[i:i+3] = *c + 1;
        bar(i);
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

메모리 `*c` 참조를 루프 에서 이동하는 것은 `a[i]` `b[i]` **불법입니다.** 순차적 종속성을 깨뜨리면 하나의 원래 반복 내에서 명령문을 다시 정렬하는 것도 불법입니다. 예를 들어 다음과 같은 변환된 루프는 합법적이지 않습니다.

```c
    c = b;
    t = *c;
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        bar(i);            // illegal to reorder if bar[i] depends on b[i]
        b[i:i+3] = t + 1;  // illegal to move *c out of the loop
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

## <a name="see-also"></a>참고 항목

[/openmp(OpenMP 2.0 지원 사용)](../../build/reference/openmp-enable-openmp-2-0-support.md)<br/>
