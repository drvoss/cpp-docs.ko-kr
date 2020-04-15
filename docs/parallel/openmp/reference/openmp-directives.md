---
title: OpenMP 지시문
ms.date: 03/20/2019
f1_keywords:
- OpenMP directives
- atomic
- barrier
- critical
- flush
- for
- master
- parallel
- section
- single
- threadprivate
helpviewer_keywords:
- OpenMP directives
- atomic OpenMP directive
- barrier OpenMP directive
- critical OpenMP directive
- flush OpenMP directive
- for OpenMP directive
- master OpenMP directive
- ordered OpenMP directive
- parallel OpenMP directive
- sections OpenMP directive
- single OpenMP directive
- threadprivate OpenMP directive
ms.assetid: 0562c263-344c-466d-843e-de830d918940
ms.openlocfilehash: 569419b3422b155afc6e9692efaecd4e5a06f188
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366437"
---
# <a name="openmp-directives"></a>OpenMP 지시문

OpenMP API에 사용되는 지시문에 대한 링크를 제공합니다.

Visual C++는 다음 OpenMP 지시문을 지원합니다.

병렬 작업 공유의 경우:

|지시문|Description|
|---------|-----------|
|[parallel](#parallel)|병렬 영역을 정의 합니다., 병렬로 여러 스레드에 의해 실행 될 코드입니다.|
|[for](#for-openmp)|병렬 영역 내부의 `for` 루프에서 수행된 작업을 스레드 간에 분할합니다.|
|[sections](#sections-openmp)|모든 스레드 간에 분할할 코드 섹션을 식별합니다.|
|[single](#single)|코드 섹션을 마스터 스레드가 아닌 단일 스레드에서 실행되도록 지정할 수 있습니다.|

마스터 및 동기화의 경우:

|지시문|Description|
|---------|-----------|
|[master](#master)|마스터 스레드만 프로그램의 섹션을 실행해야 한다고 지정합니다.|
|[중요](#critical)|코드는 한 번에 하나의 스레드에서만 실행되도록 지정합니다.|
|[장벽](#barrier)|팀의 모든 스레드를 동기화합니다. 모든 스레드가 장벽을 실행할 때까지 모든 스레드가 장벽에서 일시 중지됩니다.|
|[원자성(atomic)](#atomic)|원자적으로 업데이트될 메모리 위치를 지정합니다.|
|[플러시](#flush-openmp)|모든 스레드가 모든 공유 개체에 대해 동일한 메모리 보기를 갖도록 지정합니다.|
|[주문](#ordered-openmp-directives)|병렬화된 `for` 루프 아래의 코드를 순차적 루프처럼 실행해야 한다고 지정합니다.|

데이터 환경의 경우:

|지시문|Description|
|---------|-----------|
|[threadprivate](#threadprivate)|변수가 스레드에 비공개임을 지정합니다.|

## <a name="atomic"></a><a name="atomic"></a>원자

원자적으로 업데이트될 메모리 위치를 지정합니다.

```cpp
#pragma omp atomic
   expression
```

### <a name="parameters"></a>매개 변수

*expression*<br/>
*lvalue가*있는 명령문으로, 두 개 이상의 쓰기로부터 보호하려는 메모리 위치를 보호합니다.

### <a name="remarks"></a>설명

`atomic` 지시문은 절을 지원하지 않습니다.

자세한 내용은 [2.6.4 원자 구문.](../../../parallel/openmp/2-6-4-atomic-construct.md)

### <a name="example"></a>예제

```cpp
// omp_atomic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define MAX 10

int main() {
   int count = 0;
   #pragma omp parallel num_threads(MAX)
   {
      #pragma omp atomic
      count++;
   }
   printf_s("Number of threads: %d\n", count);
}
```

```Output
Number of threads: 10
```

## <a name="barrier"></a><a name="barrier"></a>장벽

팀의 모든 스레드를 동기화합니다. 모든 스레드가 장벽을 실행할 때까지 모든 스레드가 장벽에서 일시 중지됩니다.

```cpp
#pragma omp barrier
```

### <a name="remarks"></a>설명

`barrier` 지시문은 절을 지원하지 않습니다.

자세한 내용은 [2.6.3 장벽 지시문을](../../../parallel/openmp/2-6-3-barrier-directive.md)참조하십시오.

### <a name="example"></a>예제

사용 `barrier`방법에 대한 샘플은 [마스터](#master)를 참조하십시오.

## <a name="critical"></a><a name="critical"></a>중요

코드는 한 번에 하나의 스레드에서만 실행되도록 지정합니다.

```cpp
#pragma omp critical [(name)]
{
   code_block
}
```

### <a name="parameters"></a>매개 변수

*(이름)*<br/>
(선택 사항) 중요한 코드를 식별하는 이름입니다. 이름은 괄호 안에 동봉되어야 합니다.

### <a name="remarks"></a>설명

`critical` 지시문은 절을 지원하지 않습니다.

자세한 내용은 [2.6.2 임계 구문](../../../parallel/openmp/2-6-2-critical-construct.md)을 참조하십시오.

### <a name="example"></a>예제

```cpp
// omp_critical.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>

#define SIZE 10

int main()
{
    int i;
    int max;
    int a[SIZE];

    for (i = 0; i < SIZE; i++)
    {
        a[i] = rand();
        printf_s("%d\n", a[i]);
    }

    max = a[0];
    #pragma omp parallel for num_threads(4)
        for (i = 1; i < SIZE; i++)
        {
            if (a[i] > max)
            {
                #pragma omp critical
                {
                    // compare a[i] and max again because max
                    // could have been changed by another thread after
                    // the comparison outside the critical section
                    if (a[i] > max)
                        max = a[i];
                }
            }
        }

    printf_s("max = %d\n", max);
}
```

```Output
41
18467
6334
26500
19169
15724
11478
29358
26962
24464
max = 29358
```

## <a name="flush"></a><a name="flush-openmp"></a>플러시

모든 스레드가 모든 공유 개체에 대해 동일한 메모리 보기를 갖도록 지정합니다.

```cpp
#pragma omp flush [(var)]
```

### <a name="parameters"></a>매개 변수

*Var*<br/>
(선택 사항) 동기화하려는 개체를 나타내는 변수의 쉼표 로 구분된 목록입니다. *var을* 지정하지 않으면 모든 메모리가 플러시됩니다.

### <a name="remarks"></a>설명

`flush` 지시문은 절을 지원하지 않습니다.

자세한 내용은 [2.6.5 플러시 지시문을](../../../parallel/openmp/2-6-5-flush-directive.md)참조하십시오.

### <a name="example"></a>예제

```cpp
// omp_flush.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void read(int *data) {
   printf_s("read data\n");
   *data = 1;
}

void process(int *data) {
   printf_s("process data\n");
   (*data)++;
}

int main() {
   int data;
   int flag;

   flag = 0;

   #pragma omp parallel sections num_threads(2)
   {
      #pragma omp section
      {
         printf_s("Thread %d: ", omp_get_thread_num( ));
         read(&data);
         #pragma omp flush(data)
         flag = 1;
         #pragma omp flush(flag)
         // Do more work.
      }

      #pragma omp section
      {
         while (!flag) {
            #pragma omp flush(flag)
         }
         #pragma omp flush(data)

         printf_s("Thread %d: ", omp_get_thread_num( ));
         process(&data);
         printf_s("data = %d\n", data);
      }
   }
}
```

```Output
Thread 0: read data
Thread 1: process data
data = 2
```

## <a name="for"></a><a name="for-openmp"></a>에 대 한

병렬 영역 내부의 `for` 루프에서 수행된 작업을 스레드 간에 분할합니다.

```cpp
#pragma omp [parallel] for [clauses]
   for_statement
```

### <a name="parameters"></a>매개 변수

*절*<br/>
(선택 사항) 0 개 이상의 절은 **비고** 섹션을 참조하십시오.

*for_statement*<br/>
`for` 루프입니다. 루프의 `for` 사용자 코드가 인덱스 변수를 변경하면 정의되지 않은 동작이 발생합니다.

### <a name="remarks"></a>설명

이 `for` 지시문은 다음 절을 지원합니다.

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [주문](openmp-clauses.md#ordered-openmp-clauses)
- [schedule](openmp-clauses.md#schedule)
- [Nowait](openmp-clauses.md#nowait)

또한 `parallel` 지정된 경우 `clauses` 를 제외한 `parallel` `for` `nowait`또는 지시문에 의해 허용되는 모든 절이 될 수 있습니다.

자세한 내용은 [구문에 대한 2.4.1을](../../../parallel/openmp/2-4-1-for-construct.md)참조하십시오.

### <a name="example"></a>예제

```cpp
// omp_for.cpp
// compile with: /openmp
#include <stdio.h>
#include <math.h>
#include <omp.h>

#define NUM_THREADS 4
#define NUM_START 1
#define NUM_END 10

int main() {
   int i, nRet = 0, nSum = 0, nStart = NUM_START, nEnd = NUM_END;
   int nThreads = 0, nTmp = nStart + nEnd;
   unsigned uTmp = (unsigned((abs(nStart - nEnd) + 1)) *
                               unsigned(abs(nTmp))) / 2;
   int nSumCalc = uTmp;

   if (nTmp < 0)
      nSumCalc = -nSumCalc;

   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel default(none) private(i) shared(nSum, nThreads, nStart, nEnd)
   {
      #pragma omp master
      nThreads = omp_get_num_threads();

      #pragma omp for
      for (i=nStart; i<=nEnd; ++i) {
            #pragma omp atomic
            nSum += i;
      }
   }

   if  (nThreads == NUM_THREADS) {
      printf_s("%d OpenMP threads were used.\n", NUM_THREADS);
      nRet = 0;
   }
   else {
      printf_s("Expected %d OpenMP threads, but %d were used.\n",
               NUM_THREADS, nThreads);
      nRet = 1;
   }

   if (nSum != nSumCalc) {
      printf_s("The sum of %d through %d should be %d, "
               "but %d was reported!\n",
               NUM_START, NUM_END, nSumCalc, nSum);
      nRet = 1;
   }
   else
      printf_s("The sum of %d through %d is %d\n",
               NUM_START, NUM_END, nSum);
}
```

```Output
4 OpenMP threads were used.
The sum of 1 through 10 is 55
```

## <a name="master"></a><a name="master"></a>마스터

마스터 스레드만 프로그램의 섹션을 실행해야 한다고 지정합니다.

```cpp
#pragma omp master
{
   code_block
}
```

### <a name="remarks"></a>설명

`master` 지시문은 절을 지원하지 않습니다.

[단일](#single) 지시문을 사용하면 코드 섹션을 마스터 스레드가 아닌 단일 스레드에서 실행되도록 지정할 수 있습니다.

자세한 내용은 [2.6.1 마스터 구문](../../../parallel/openmp/2-6-1-master-construct.md)을 참조하십시오.

### <a name="example"></a>예제

```cpp
// omp_master.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>

int main( )
{
    int a[5], i;

    #pragma omp parallel
    {
        // Perform some computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] = i * i;

        // Print intermediate results.
        #pragma omp master
            for (i = 0; i < 5; i++)
                printf_s("a[%d] = %d\n", i, a[i]);

        // Wait.
        #pragma omp barrier

        // Continue with the computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] += i;
    }
}
```

```Output
a[0] = 0
a[1] = 1
a[2] = 4
a[3] = 9
a[4] = 16
```

## <a name="ordered"></a><a name="ordered-openmp-directives"></a>주문

병렬화된 `for` 루프 아래의 코드를 순차적 루프처럼 실행해야 한다고 지정합니다.

```cpp
#pragma omp ordered
   structured-block
```

### <a name="remarks"></a>설명

지시문은 [for](#for-openmp) 또는 `parallel for` `ordered` 시구의 동적 범위 내에 있어야 합니다. `ordered`

`ordered` 지시문은 절을 지원하지 않습니다.

자세한 내용은 [2.6.6 정렬된 구문](../../../parallel/openmp/2-6-6-ordered-construct.md)을 참조하십시오.

### <a name="example"></a>예제

```cpp
// omp_ordered.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

static float a[1000], b[1000], c[1000];

void test(int first, int last)
{
    #pragma omp for schedule(static) ordered
    for (int i = first; i <= last; ++i) {
        // Do something here.
        if (i % 2)
        {
            #pragma omp ordered
            printf_s("test() iteration %d\n", i);
        }
    }
}

void test2(int iter)
{
    #pragma omp ordered
    printf_s("test2() iteration %d\n", iter);
}

int main( )
{
    int i;
    #pragma omp parallel
    {
        test(1, 8);
        #pragma omp for ordered
        for (i = 0 ; i < 5 ; i++)
            test2(i);
    }
}
```

```Output
test() iteration 1
test() iteration 3
test() iteration 5
test() iteration 7
test2() iteration 0
test2() iteration 1
test2() iteration 2
test2() iteration 3
test2() iteration 4
```

## <a name="parallel"></a><a name="parallel"></a>병렬

병렬 영역을 정의 합니다., 병렬로 여러 스레드에 의해 실행 될 코드입니다.

```cpp
#pragma omp parallel [clauses]
{
   code_block
}
```

### <a name="parameters"></a>매개 변수

*절*<br/>
(선택 사항) 0 개 이상의 절은 **비고** 섹션을 참조하십시오.

### <a name="remarks"></a>설명

이 `parallel` 지시문은 다음 절을 지원합니다.

- [if](openmp-clauses.md#if-openmp)
- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [default](openmp-clauses.md#default-openmp)
- [공유](openmp-clauses.md#shared-openmp)
- [copyin](openmp-clauses.md#copyin)
- [reduction](openmp-clauses.md#reduction)
- [num_threads](openmp-clauses.md#num-threads)

`parallel`for [및](#for-openmp) [섹션](#sections-openmp) 지시문과 함께 사용할 수도 있습니다.

자세한 내용은 [2.3 병렬 구문](../../../parallel/openmp/2-3-parallel-construct.md)을 참조하십시오.

### <a name="example"></a>예제

다음 샘플에서는 스레드 수를 설정하고 병렬 영역을 정의하는 방법을 보여 주며 있습니다. 스레드 수는 기본적으로 컴퓨터의 논리 프로세서 수와 동일합니다. 예를 들어 하이퍼스레딩이 활성화된 물리적 프로세서가 하나 있는 컴퓨터가 있는 경우 논리 프로세서 두 개와 스레드 두 개가 있습니다. 출력 순서는 기계마다 다를 수 있습니다.

```cpp
// omp_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(4)
   {
      int i = omp_get_thread_num();
      printf_s("Hello from thread %d\n", i);
   }
}
```

```Output
Hello from thread 0
Hello from thread 1
Hello from thread 2
Hello from thread 3
```

## <a name="sections"></a><a name="sections-openmp"></a>섹션

모든 스레드 간에 분할할 코드 섹션을 식별합니다.

```cpp
#pragma omp [parallel] sections [clauses]
{
   #pragma omp section
   {
      code_block
   }
}
```

### <a name="parameters"></a>매개 변수

*절*<br/>
(선택 사항) 0 개 이상의 절은 **비고** 섹션을 참조하십시오.

### <a name="remarks"></a>설명

지시문에는 `sections` 0개 `section` 이상의 지시문이 포함될 수 있습니다.

이 `sections` 지시문은 다음 절을 지원합니다.

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [Nowait](openmp-clauses.md#nowait)

또한 `parallel` 지정된 경우 `clauses` 를 제외한 `parallel` `sections` `nowait`또는 지시문에 의해 허용되는 모든 절이 될 수 있습니다.

자세한 내용은 [2.4.2 섹션 구성을](../../../parallel/openmp/2-4-2-sections-construct.md)참조하십시오.

### <a name="example"></a>예제

```cpp
// omp_sections.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
    #pragma omp parallel sections num_threads(4)
    {
        printf_s("Hello from thread %d\n", omp_get_thread_num());
        #pragma omp section
        printf_s("Hello from thread %d\n", omp_get_thread_num());
    }
}
```

```Output
Hello from thread 0
Hello from thread 0
```

## <a name="single"></a><a name="single"></a>단일

코드 섹션을 마스터 스레드가 아닌 단일 스레드에서 실행되도록 지정할 수 있습니다.

```cpp
#pragma omp single [clauses]
{
   code_block
}
```

### <a name="parameters"></a>매개 변수

*절*<br/>
(선택 사항) 0 개 이상의 절은 **비고** 섹션을 참조하십시오.

### <a name="remarks"></a>설명

이 `single` 지시문은 다음 절을 지원합니다.

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [copyprivate](openmp-clauses.md#copyprivate)
- [Nowait](openmp-clauses.md#nowait)

[마스터](#master) 지시문을 사용하면 코드 섹션을 마스터 스레드에서만 실행해야 한다고 지정할 수 있습니다.

자세한 내용은 [2.4.3 단일 구문](../../../parallel/openmp/2-4-3-single-construct.md)을 참조하십시오.

### <a name="example"></a>예제

```cpp
// omp_single.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(2)
   {
      #pragma omp single
      // Only a single thread can read the input.
      printf_s("read input\n");

      // Multiple threads in the team compute the results.
      printf_s("compute results\n");

      #pragma omp single
      // Only a single thread can write the output.
      printf_s("write output\n");
    }
}
```

```Output
read input
compute results
compute results
write output
```

## <a name="threadprivate"></a><a name="threadprivate"></a>Threadprivate

변수가 스레드에 비공개임을 지정합니다.

```cpp
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>매개 변수

*Var*<br/>
스레드에 비공개로 만들려는 변수의 쉼표로 구분된 목록입니다. *var은* 전역 또는 네임스페이스 범위의 변수 또는 로컬 정적 변수여야 합니다.

### <a name="remarks"></a>설명

`threadprivate` 지시문은 절을 지원하지 않습니다.

`threadprivate` 지시어는 [__declspec](../../../cpp/declspec.md) 키워드를 사용하는 [thread](../../../cpp/thread.md) 특성을 기반으로 합니다 .`__declspec(thread)`에 대한 제한은 `threadprivate`에 적용됩니다. 예를 들어 `threadprivate` 병렬 영역으로 생성된 스레드 팀의 일부인 스레드뿐만 아니라 프로세스에서 시작된 모든 스레드에 변수가 존재합니다. 이 구현 세부 정보를 알고 있어야 합니다. 사용자 정의 형식에 대 `threadprivate` 한 생성자가 더 자주 호출 된 다음 예상 될 수 있습니다.

프로세스 시작 `threadprivate` 시 정적으로 로드되는 DLL에서 사용할 수 있지만 `threadprivate` [/DELAYLOAD(지연 로드 가져오기)가](../../../build/reference/delayload-delay-load-import.md)로드된 `LoadLibrary`DLL과 같이 [LoadLibrary를](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) 통해 로드되는 DLL에서는 사용할 수 없습니다.

소멸 `threadprivate` *가능한* 형식의 변수는 소멸자가 호출되는 것을 보장하지 않습니다. 다음은 그 예입니다.

```cpp
struct MyType
{
    ~MyType();
};

MyType threaded_var;
#pragma omp threadprivate(threaded_var)
int main()
{
    #pragma omp parallel
    {}
}
```

사용자는 병렬 영역을 구성하는 스레드가 종료되는 시기를 제어할 수 없습니다. 프로세스가 종료될 때 해당 스레드가 있는 경우 프로세스 종료에 대해 스레드에 알리지 않으며 소멸자는 종료되는 `threaded_var` 스레드(여기, 기본 스레드)를 제외한 모든 스레드에서 호출되지 않습니다. 따라서 코드는 `threadprivate` 변수의 적절한 소멸에 의존해서는 안됩니다.

자세한 내용은 [2.7.1 threadprivate 지시문을](../../../parallel/openmp/2-7-1-threadprivate-directive.md)참조하십시오.

### <a name="example"></a>예제

사용 `threadprivate`샘플은 [개인](openmp-clauses.md#private-openmp)을 참조하십시오.
