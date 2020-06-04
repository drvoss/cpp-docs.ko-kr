---
title: OpenMP 절
ms.date: 03/20/2019
f1_keywords:
- OpenMP clauses
- copyin
- copyprivate
- default
- firstprivate
- lastprivate
- nowait
- num_threads
- ordered
- private
- reduction
- schedule
- shared
helpviewer_keywords:
- OpenMP clauses
- copyin OpenMP clause
- copyprivate OpenMP clause
- default OpenMP clause
- defaults, OpenMP clause
- firstprivate OpenMP clause
- if OpenMP clause
- lastprivate OpenMP clause
- nowait OpenMP clause
- num_threads OpenMP clause
- ordered OpenMP clause
- private OpenMP clause
- reduction OpenMP clause
- schedule OpenMP clause
- shared OpenMP clause
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
ms.openlocfilehash: 1c4c7961a173eb47394d03e9aabdd14574e62b08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363894"
---
# <a name="openmp-clauses"></a>OpenMP 절

OpenMP API에 사용되는 절에 대한 링크를 제공합니다.

Visual C++는 다음 OpenMP 절을 지원합니다.

일반적인 특성의 경우:

|절|Description|
|------|-----------|
|[if](#if-openmp)|루프를 병렬 또는 직렬로 실행할지 여부를 지정합니다.|
|[num_threads](#num-threads)|스레드 팀의 스레드 수를 설정합니다.|
|[주문](#ordered-openmp-clauses)|[명령된](openmp-directives.md#ordered-openmp-directives) 지시문을 루프에서 사용할 경우 명령문에 [대해](openmp-directives.md#for-openmp) 병렬로 필요합니다.|
|[schedule](#schedule)|[for](openmp-directives.md#for-openmp) 지시문에 적용됩니다.|
|[Nowait](#nowait)|지시문에서 암시적 장벽을 재정의합니다.|

데이터 공유 특성의 경우:

|절|Description|
|------|-----------|
|[private](#private-openmp)|각 스레드에 변수의 자체 인스턴스가 있어야 합니다.|
|[firstprivate](#firstprivate)|각 스레드에는 변수의 자체 인스턴스가 있어야 하며 병렬 구문 앞에 존재하기 때문에 변수를 변수 값으로 초기화해야 합니다.|
|[lastprivate](#lastprivate)|둘러싸는 컨텍스트의 변수 버전이 최종 반복(for-loop 구문) 또는 마지막 섹션(#pragma 섹션)을 실행하는 스레드중의 개인 버전과 동일하게 설정되도록 지정합니다.|
|[공유](#shared-openmp)|하나 이상의 변수를 모든 스레드 간에 공유해야 한다고 지정합니다.|
|[default](#default-openmp)|병렬 영역에서 범위가 지정되지 않은 변수의 동작을 지정합니다.|
|[reduction](#reduction)|각 스레드에 비공개인 하나 이상의 변수가 병렬 영역의 끝에서 축소 작업의 대상이 되도록 지정합니다.|
|[copyin](#copyin)|스레드가 [스레드개인](openmp-directives.md#threadprivate) 변수에 대해 마스터 스레드의 값에 액세스할 수 있습니다.|
|[copyprivate](#copyprivate)|하나 이상의 변수를 모든 스레드 간에 공유해야 한다고 지정합니다.|

## <a name="copyin"></a><a name="copyin"></a>카피인

스레드가 [스레드개인](openmp-directives.md#threadprivate) 변수에 대해 마스터 스레드의 값에 액세스할 수 있습니다.

```cpp
copyin(var)
```

### <a name="parameters"></a>매개 변수

*Var*<br/>
`threadprivate` 병렬 구문 앞에 있는 것처럼 마스터 스레드에서 변수값으로 초기화될 변수입니다.

### <a name="remarks"></a>설명

`copyin`다음 지시문에 적용됩니다.

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [sections](openmp-directives.md#sections-openmp)

자세한 내용은 [2.7.2.7 카피인을](../../../parallel/openmp/2-7-2-7-copyin.md)참조하십시오.

### <a name="example"></a>예제

사용의 예는 [스레드private을](openmp-directives.md#threadprivate) `copyin`참조하십시오.

## <a name="copyprivate"></a><a name="copyprivate"></a>카피프라이빗

하나 이상의 변수를 모든 스레드 간에 공유해야 한다고 지정합니다.

```cpp
copyprivate(var)
```

### <a name="parameters"></a>매개 변수

*Var*<br/>
공유할 하나 이상의 변수입니다. 두 개 이상의 변수를 지정하면 변수 이름을 쉼표로 구분합니다.

### <a name="remarks"></a>설명

`copyprivate`[는 단일](openmp-directives.md#single) 지시문에 적용됩니다.

자세한 내용은 [2.7.2.8 copyprivate](../../../parallel/openmp/2-7-2-8-copyprivate.md)을 참조하십시오.

### <a name="example"></a>예제

```cpp
// omp_copyprivate.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

float x, y, fGlobal = 1.0;
#pragma omp threadprivate(x, y)

float get_float() {
   fGlobal += 0.001;
   return fGlobal;
}

void use_float(float f, int t) {
   printf_s("Value = %f, thread = %d\n", f, t);
}

void CopyPrivate(float a, float b) {
   #pragma omp single copyprivate(a, b, x, y)
   {
      a = get_float();
      b = get_float();
      x = get_float();
      y = get_float();
    }

   use_float(a, omp_get_thread_num());
   use_float(b, omp_get_thread_num());
   use_float(x, omp_get_thread_num());
   use_float(y, omp_get_thread_num());
}

int main() {
   float a = 9.99, b = 123.456;

   printf_s("call CopyPrivate from a single thread\n");
   CopyPrivate(9.99, 123.456);

   printf_s("call CopyPrivate from a parallel region\n");
   #pragma omp parallel
   {
      CopyPrivate(a, b);
   }
}
```

```Output
call CopyPrivate from a single thread
Value = 1.001000, thread = 0
Value = 1.002000, thread = 0
Value = 1.003000, thread = 0
Value = 1.004000, thread = 0
call CopyPrivate from a parallel region
Value = 1.005000, thread = 0
Value = 1.005000, thread = 1
Value = 1.006000, thread = 0
Value = 1.006000, thread = 1
Value = 1.007000, thread = 0
Value = 1.007000, thread = 1
Value = 1.008000, thread = 0
Value = 1.008000, thread = 1
```

## <a name="default"></a><a name="default-openmp"></a>기본

병렬 영역에서 범위가 지정되지 않은 변수의 동작을 지정합니다.

```cpp
default(shared | none)
```

### <a name="remarks"></a>설명

`shared`이는 절이 `default` 지정되지 않은 경우 적용되며 병렬 영역의 모든 변수는 [공유](#shared-openmp) 절로 지정된 것처럼 처리됩니다. `none`즉, [개인,](#private-openmp) [공유,](#shared-openmp) [축소,](#reduction) [firstprivate](#firstprivate)또는 [lastprivate](#lastprivate) 절로 범위가 조정되지 않은 병렬 영역에서 사용되는 모든 변수는 컴파일러 오류를 발생시게 됩니다.

`default`다음 지시문에 적용됩니다.

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [sections](openmp-directives.md#sections-openmp)

자세한 내용은 [2.7.2.5 기본값](../../../parallel/openmp/2-7-2-5-default.md)을 참조하십시오.

### <a name="example"></a>예제

을 사용하는 `default`예제는 [private을](#private-openmp) 참조하십시오.

## <a name="firstprivate"></a><a name="firstprivate"></a>첫 번째 개인

각 스레드에는 변수의 자체 인스턴스가 있어야 하며 병렬 구문 앞에 존재하기 때문에 변수를 변수 값으로 초기화해야 합니다.

```cpp
firstprivate(var)
```

### <a name="parameters"></a>매개 변수

*Var*<br/>
각 스레드에 인스턴스가 있고 병렬 구문 앞에 존재하기 때문에 변수값으로 초기화되는 변수입니다. 두 개 이상의 변수를 지정하면 변수 이름을 쉼표로 구분합니다.

### <a name="remarks"></a>설명

`firstprivate`다음 지시문에 적용됩니다.

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [sections](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

자세한 내용은 [2.7.2.2 첫 번째 개인](../../../parallel/openmp/2-7-2-2-firstprivate.md)을 참조하십시오.

### <a name="example"></a>예제

을 사용하는 `firstprivate`예제는 개인 의 예제를 [참조하십시오.](#private-openmp)

## <a name="if-openmp"></a><a name="if-openmp"></a>if(OpenMP)

루프를 병렬 또는 직렬로 실행할지 여부를 지정합니다.

```cpp
if(expression)
```

### <a name="parameters"></a>매개 변수

*expression*<br/>
true(비영도)로 평가되는 정수 식은 병렬 영역의 코드가 병렬로 실행되도록 합니다. 식이 false(0)로 평가되면 병렬 영역이 직렬로 실행됩니다(단일 스레드).

### <a name="remarks"></a>설명

`if`다음 지시문에 적용됩니다.

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [sections](openmp-directives.md#sections-openmp)

자세한 내용은 [2.3 병렬 구문](../../../parallel/openmp/2-3-parallel-construct.md)을 참조하십시오.

### <a name="example"></a>예제

```cpp
// omp_if.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void test(int val)
{
    #pragma omp parallel if (val)
    if (omp_in_parallel())
    {
        #pragma omp single
        printf_s("val = %d, parallelized with %d threads\n",
                 val, omp_get_num_threads());
    }
    else
    {
        printf_s("val = %d, serialized\n", val);
    }
}

int main( )
{
    omp_set_num_threads(2);
    test(0);
    test(2);
}
```

```Output
val = 0, serialized
val = 2, parallelized with 2 threads
```

## <a name="lastprivate"></a><a name="lastprivate"></a>라스트 프라이빗

둘러싸는 컨텍스트의 변수 버전이 최종 반복(for-loop 구문) 또는 마지막 섹션(#pragma 섹션)을 실행하는 스레드중의 개인 버전과 동일하게 설정되도록 지정합니다.

```cpp
lastprivate(var)
```

### <a name="parameters"></a>매개 변수

*Var*<br/>
스레드중 의 개인 버전과 동일하게 설정된 변수는 최종 반복(for-loop construct) 또는 마지막 섹션(#pragma 섹션)을 실행합니다.

### <a name="remarks"></a>설명

`lastprivate`다음 지시문에 적용됩니다.

- [for](openmp-directives.md#for-openmp)
- [sections](openmp-directives.md#sections-openmp)

자세한 내용은 [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md)을 참조하십시오.

### <a name="example"></a>예제

절 [schedule](#schedule) 사용의 `lastprivate` 예는 일정을 참조하십시오.

## <a name="nowait"></a><a name="nowait"></a>Nowait

지시문에서 암시적 장벽을 재정의합니다.

```cpp
nowait
```

### <a name="remarks"></a>설명

`nowait`다음 지시문에 적용됩니다.

- [for](openmp-directives.md#for-openmp)
- [sections](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

자세한 내용은 [구문에 대한 2.4.1,](../../../parallel/openmp/2-4-1-for-construct.md) [2.4.2 섹션 생성](../../../parallel/openmp/2-4-2-sections-construct.md)및 [2.4.3 단일 구문 참조.](../../../parallel/openmp/2-4-3-single-construct.md)

### <a name="example"></a>예제

```cpp
// omp_nowait.cpp
// compile with: /openmp /c
#include <stdio.h>

#define SIZE 5

void test(int *a, int *b, int *c, int size)
{
    int i;
    #pragma omp parallel
    {
        #pragma omp for nowait
        for (i = 0; i < size; i++)
            b[i] = a[i] * a[i];

        #pragma omp for nowait
        for (i = 0; i < size; i++)
            c[i] = a[i]/2;
    }
}

int main( )
{
    int a[SIZE], b[SIZE], c[SIZE];
    int i;

    for (i=0; i<SIZE; i++)
        a[i] = i;

    test(a,b,c, SIZE);

    for (i=0; i<SIZE; i++)
        printf_s("%d, %d, %d\n", a[i], b[i], c[i]);
}
```

```Output
0, 0, 0
1, 1, 0
2, 4, 1
3, 9, 1
4, 16, 2
```

## <a name="num_threads"></a><a name="num-threads"></a>num_threads

스레드 팀의 스레드 수를 설정합니다.

```cpp
num_threads(num)
```

### <a name="parameters"></a>매개 변수

*num*<br/>
스레드 수

### <a name="remarks"></a>설명

절은 `num_threads` [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 함수와 동일한 기능을 가합니다.

`num_threads`다음 지시문에 적용됩니다.

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [sections](openmp-directives.md#sections-openmp)

자세한 내용은 [2.3 병렬 구문](../../../parallel/openmp/2-3-parallel-construct.md)을 참조하십시오.

### <a name="example"></a>예제

`num_threads` 절사용 의 예는 [평행을](openmp-directives.md#parallel) 참조하십시오.

## <a name="ordered"></a><a name="ordered-openmp-clauses"></a>주문

[명령된](openmp-directives.md#ordered-openmp-directives) 지시문을 루프에서 사용할 경우 명령문에 [대해](openmp-directives.md#for-openmp) 병렬로 필요합니다.

```cpp
ordered
```

### <a name="remarks"></a>설명

`ordered`[for](openmp-directives.md#for-openmp) 지시문에 적용됩니다.

자세한 내용은 [구문에 대한 2.4.1을](../../../parallel/openmp/2-4-1-for-construct.md)참조하십시오.

### <a name="example"></a>예제

`ordered` 절 사용의 예는 [정렬된](openmp-directives.md#ordered-openmp-directives) 참조를 참조하십시오.

## <a name="private"></a><a name="private-openmp"></a>개인

각 스레드에 변수의 자체 인스턴스가 있어야 합니다.

```cpp
private(var)
```

### <a name="parameters"></a>매개 변수

*Var*<br/>
각 스레드에 인스턴스가 있는 변수입니다.

### <a name="remarks"></a>설명

`private`다음 지시문에 적용됩니다.

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [sections](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

자세한 내용은 [2.7.2.1 개인](../../../parallel/openmp/2-7-2-1-private.md)을 참조하십시오.

### <a name="example"></a>예제

```c
// openmp_private.c
// compile with: /openmp
#include <windows.h>
#include <assert.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SLEEP_THREAD 1
#define NUM_LOOPS 2

enum Types {
   ThreadPrivate,
   Private,
   FirstPrivate,
   LastPrivate,
   Shared,
   MAX_TYPES
};

int nSave[NUM_THREADS][MAX_TYPES][NUM_LOOPS] = {{0}};
int nThreadPrivate;

#pragma omp threadprivate(nThreadPrivate)
#pragma warning(disable:4700)

int main() {
   int nPrivate = NUM_THREADS;
   int nFirstPrivate = NUM_THREADS;
   int nLastPrivate = NUM_THREADS;
   int nShared = NUM_THREADS;
   int nRet = 0;
   int i;
   int j;
   int nLoop = 0;

   nThreadPrivate = NUM_THREADS;
   printf_s("These are the variables before entry "
           "into the parallel region.\n");
   printf_s("nThreadPrivate = %d\n", nThreadPrivate);
   printf_s("      nPrivate = %d\n", nPrivate);
   printf_s(" nFirstPrivate = %d\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d\n", nLastPrivate);
   printf_s("       nShared = %d\n\n", nShared);
   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel copyin(nThreadPrivate) private(nPrivate) shared(nShared) firstprivate(nFirstPrivate)
   {
      #pragma omp for schedule(static) lastprivate(nLastPrivate)
      for (i = 0 ; i < NUM_THREADS ; ++i) {
         for (j = 0 ; j < NUM_LOOPS ; ++j) {
            int nThread = omp_get_thread_num();
            assert(nThread < NUM_THREADS);

            if (nThread == SLEEP_THREAD)
               Sleep(100);
            nSave[nThread][ThreadPrivate][j] = nThreadPrivate;
            nSave[nThread][Private][j] = nPrivate;
            nSave[nThread][Shared][j] = nShared;
            nSave[nThread][FirstPrivate][j] = nFirstPrivate;
            nSave[nThread][LastPrivate][j] = nLastPrivate;
            nThreadPrivate = nThread;
            nPrivate = nThread;
            nShared = nThread;
            nLastPrivate = nThread;
            --nFirstPrivate;
         }
      }
   }

   for (i = 0 ; i < NUM_LOOPS ; ++i) {
      for (j = 0 ; j < NUM_THREADS ; ++j) {
         printf_s("These are the variables at entry of "
                  "loop %d of thread %d.\n", i + 1, j);
         printf_s("nThreadPrivate = %d\n",
                  nSave[j][ThreadPrivate][i]);
         printf_s("      nPrivate = %d\n",
                  nSave[j][Private][i]);
         printf_s(" nFirstPrivate = %d\n",
                  nSave[j][FirstPrivate][i]);
         printf_s("  nLastPrivate = %d\n",
                  nSave[j][LastPrivate][i]);
         printf_s("       nShared = %d\n\n",
                  nSave[j][Shared][i]);
      }
   }

   printf_s("These are the variables after exit from "
            "the parallel region.\n");
   printf_s("nThreadPrivate = %d (The last value in the "
            "master thread)\n", nThreadPrivate);
   printf_s("      nPrivate = %d (The value prior to "
            "entering parallel region)\n", nPrivate);
   printf_s(" nFirstPrivate = %d (The value prior to "
            "entering parallel region)\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d (The value from the "
            "last iteration of the loop)\n", nLastPrivate);
   printf_s("       nShared = %d (The value assigned, "
            "from the delayed thread, %d)\n\n",
            nShared, SLEEP_THREAD);
}
```

```Output
These are the variables before entry into the parallel region.
nThreadPrivate = 4
      nPrivate = 4
nFirstPrivate = 4
  nLastPrivate = 4
       nShared = 4

These are the variables at entry of loop 1 of thread 0.
nThreadPrivate = 4
      nPrivate = 1310720
nFirstPrivate = 4
  nLastPrivate = 1245104
       nShared = 3

These are the variables at entry of loop 1 of thread 1.
nThreadPrivate = 4
      nPrivate = 4488
nFirstPrivate = 4
  nLastPrivate = 19748
       nShared = 0

These are the variables at entry of loop 1 of thread 2.
nThreadPrivate = 4
      nPrivate = -132514848
nFirstPrivate = 4
  nLastPrivate = -513199792
       nShared = 4

These are the variables at entry of loop 1 of thread 3.
nThreadPrivate = 4
      nPrivate = 1206
nFirstPrivate = 4
  nLastPrivate = 1204
       nShared = 2

These are the variables at entry of loop 2 of thread 0.
nThreadPrivate = 0
      nPrivate = 0
nFirstPrivate = 3
  nLastPrivate = 0
       nShared = 0

These are the variables at entry of loop 2 of thread 1.
nThreadPrivate = 1
      nPrivate = 1
nFirstPrivate = 3
  nLastPrivate = 1
       nShared = 1

These are the variables at entry of loop 2 of thread 2.
nThreadPrivate = 2
      nPrivate = 2
nFirstPrivate = 3
  nLastPrivate = 2
       nShared = 2

These are the variables at entry of loop 2 of thread 3.
nThreadPrivate = 3
      nPrivate = 3
nFirstPrivate = 3
  nLastPrivate = 3
       nShared = 3

These are the variables after exit from the parallel region.
nThreadPrivate = 0 (The last value in the master thread)
      nPrivate = 4 (The value prior to entering parallel region)
nFirstPrivate = 4 (The value prior to entering parallel region)
  nLastPrivate = 3 (The value from the last iteration of the loop)
       nShared = 1 (The value assigned, from the delayed thread, 1)
```

## <a name="reduction"></a><a name="reduction"></a>감소

각 스레드에 비공개인 하나 이상의 변수가 병렬 영역의 끝에서 축소 작업의 대상이 되도록 지정합니다.

```cpp
reduction(operation:var)
```

### <a name="parameters"></a>매개 변수

*작업*<br/>
병렬 영역의 끝에 있는 변수 *var에서* 수행할 연산자입니다.

*Var*<br/>
스칼라 감소를 수행할 하나 이상의 변수. 두 개 이상의 변수를 지정하면 변수 이름을 쉼표로 구분합니다.

### <a name="remarks"></a>설명

`reduction`다음 지시문에 적용됩니다.

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [sections](openmp-directives.md#sections-openmp)

자세한 내용은 [2.7.2.6 감소를](../../../parallel/openmp/2-7-2-6-reduction.md)참조하십시오.

### <a name="example"></a>예제

```cpp
// omp_reduction.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SUM_START   1
#define SUM_END     10
#define FUNC_RETS   {1, 1, 1, 1, 1}

int bRets[5] = FUNC_RETS;
int nSumCalc = ((SUM_START + SUM_END) * (SUM_END - SUM_START + 1)) / 2;

int func1( ) {return bRets[0];}
int func2( ) {return bRets[1];}
int func3( ) {return bRets[2];}
int func4( ) {return bRets[3];}
int func5( ) {return bRets[4];}

int main( )
{
    int nRet = 0,
        nCount = 0,
        nSum = 0,
        i,
        bSucceed = 1;

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel reduction(+ : nCount)
    {
        nCount += 1;

        #pragma omp for reduction(+ : nSum)
        for (i = SUM_START ; i <= SUM_END ; ++i)
            nSum += i;

        #pragma omp sections reduction(&& : bSucceed)
        {
            #pragma omp section
            {
                bSucceed = bSucceed && func1( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func2( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func3( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func4( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func5( );
            }
        }
    }

    printf_s("The parallel section was executed %d times "
             "in parallel.\n", nCount);
    printf_s("The sum of the consecutive integers from "
             "%d to %d, is %d\n", 1, 10, nSum);

    if (bSucceed)
        printf_s("All of the functions, func1 through "
                 "func5 succeeded!\n");
    else
        printf_s("One or more of the functions, func1 "
                 "through func5 failed!\n");

    if (nCount != NUM_THREADS)
    {
        printf_s("ERROR: For %d threads, %d were counted!\n",
                 NUM_THREADS, nCount);
        nRet |= 0x1;
   }

    if (nSum != nSumCalc)
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                "but %d was reported!\n",
                SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x10;
    }

    if (bSucceed != (bRets[0] && bRets[1] &&
                     bRets[2] && bRets[3] && bRets[4]))
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                 "but %d was reported!\n",
                 SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x100;
    }
}
```

```Output
The parallel section was executed 4 times in parallel.
The sum of the consecutive integers from 1 to 10, is 55
All of the functions, func1 through func5 succeeded!
```

## <a name="schedule"></a><a name="schedule"></a>일정

[for](openmp-directives.md#for-openmp) 지시문에 적용됩니다.

```cpp
schedule(type[,size])
```

### <a name="parameters"></a>매개 변수

*종류*<br/>
일정의 `dynamic`종류(에 `guided`의한 `runtime`것) `static`

*크기*<br/>
(선택 사항) 반복 크기를 지정합니다. *크기는* 정수여야 합니다. *형식이* `runtime`.입니다.

### <a name="remarks"></a>설명

자세한 내용은 [구문에 대한 2.4.1을](../../../parallel/openmp/2-4-1-for-construct.md)참조하십시오.

### <a name="example"></a>예제

```cpp
// omp_schedule.cpp
// compile with: /openmp
#include <windows.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define STATIC_CHUNK 5
#define DYNAMIC_CHUNK 5
#define NUM_LOOPS 20
#define SLEEP_EVERY_N 3

int main( )
{
    int nStatic1[NUM_LOOPS],
        nStaticN[NUM_LOOPS];
    int nDynamic1[NUM_LOOPS],
        nDynamicN[NUM_LOOPS];
    int nGuided[NUM_LOOPS];

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel
    {
        #pragma omp for schedule(static, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStatic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(static, STATIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStaticN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, DYNAMIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamicN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(guided)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nGuided[i] = omp_get_thread_num( );
        }
    }

    printf_s("------------------------------------------------\n");
    printf_s("| static | static | dynamic | dynamic | guided |\n");
    printf_s("|    1   |    %d   |    1    |    %d    |        |\n",
             STATIC_CHUNK, DYNAMIC_CHUNK);
    printf_s("------------------------------------------------\n");

    for (int i=0; i<NUM_LOOPS; ++i)
    {
        printf_s("|    %d   |    %d   |    %d    |    %d    |"
                 "    %d   |\n",
                 nStatic1[i], nStaticN[i],
                 nDynamic1[i], nDynamicN[i], nGuided[i]);
    }

    printf_s("------------------------------------------------\n");
}
```

```Output
------------------------------------------------
| static | static | dynamic | dynamic | guided |
|    1   |    5   |    1    |    5    |        |
------------------------------------------------
|    0   |    0   |    0    |    2    |    1   |
|    1   |    0   |    3    |    2    |    1   |
|    2   |    0   |    3    |    2    |    1   |
|    3   |    0   |    3    |    2    |    1   |
|    0   |    0   |    2    |    2    |    1   |
|    1   |    1   |    2    |    3    |    3   |
|    2   |    1   |    2    |    3    |    3   |
|    3   |    1   |    0    |    3    |    3   |
|    0   |    1   |    0    |    3    |    3   |
|    1   |    1   |    0    |    3    |    2   |
|    2   |    2   |    1    |    0    |    2   |
|    3   |    2   |    1    |    0    |    2   |
|    0   |    2   |    1    |    0    |    3   |
|    1   |    2   |    2    |    0    |    3   |
|    2   |    2   |    2    |    0    |    0   |
|    3   |    3   |    2    |    1    |    0   |
|    0   |    3   |    3    |    1    |    1   |
|    1   |    3   |    3    |    1    |    1   |
|    2   |    3   |    3    |    1    |    1   |
|    3   |    3   |    0    |    1    |    3   |
------------------------------------------------
```

## <a name="shared"></a><a name="shared-openmp"></a>공유

하나 이상의 변수를 모든 스레드 간에 공유해야 한다고 지정합니다.

```cpp
shared(var)
```

### <a name="parameters"></a>매개 변수

*Var*<br/>
공유할 하나 이상의 변수입니다. 두 개 이상의 변수를 지정하면 변수 이름을 쉼표로 구분합니다.

### <a name="remarks"></a>설명

스레드 간에 변수를 공유하는 또 다른 방법은 [copyprivate](#copyprivate) 절을 사용 하 여 입니다.

`shared`다음 지시문에 적용됩니다.

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [sections](openmp-directives.md#sections-openmp)

자세한 내용은 [공유 2.7.2.4를](../../../parallel/openmp/2-7-2-4-shared.md)참조하십시오.

### <a name="example"></a>예제

을 사용하는 `shared`예제는 [private을](#private-openmp) 참조하십시오.
