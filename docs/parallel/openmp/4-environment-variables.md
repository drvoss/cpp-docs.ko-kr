---
title: 4. 환경 변수
ms.date: 01/16/2019
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: e93c59654c17ed6dbfb7483ac2dce716ce24b52a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370260"
---
# <a name="4-environment-variables"></a>4. 환경 변수

이 장에서는 병렬 코드 실행을 제어하는 OpenMP C 및 C++ API 환경 변수(또는 유사한 플랫폼별 메커니즘)에 대해 설명합니다.  환경 변수의 이름은 대문자여야 합니다. 할당된 값은 대/소문자를 구분하지 않으며 선행 및 후행 공백이 있을 수 있습니다.  프로그램이 시작된 후의 값 수정은 무시됩니다.

환경 변수는 다음과 같습니다.

- [OMP_SCHEDULE](#41-omp_schedule) 런타임 일정 유형 및 청크 크기를 설정합니다.
- [OMP_NUM_THREADS](#42-omp_num_threads) 실행 하는 동안 사용할 스레드 수를 설정 합니다.
- [OMP_DYNAMIC](#43-omp_dynamic) 스레드 수의 동적 조정을 활성화하거나 사용하지 않도록 설정합니다.
- [OMP_NESTED](#44-omp_nested) 중첩된 병렬 처리기능을 사용하거나 사용하지 않도록 설정합니다.

이 장의 예제에서는 이러한 변수가 유닉스 C 셸(csh) 환경에서 어떻게 설정될 수 있는지 보여 줍니다. Korn 셸 및 DOS 환경에서 작업은 비슷합니다.

csh:  
`setenv OMP_SCHEDULE "dynamic"`

Ksh:  
`export OMP_SCHEDULE="dynamic"`

Dos:  
`set OMP_SCHEDULE="dynamic"`

## <a name="41-omp_schedule"></a><a name="41-omp_schedule"></a>4.1 OMP_SCHEDULE

`OMP_SCHEDULE`스케줄 `for` 유형이 `parallel for` `runtime`있는 및 지시문에만 적용됩니다. 이러한 모든 루프에 대한 일정 유형 및 청크 크기는 런타임에 설정할 수 있습니다. 이 환경 변수를 인식된 모든 일정 유형과 선택적 *chunk_size*설정합니다.

`runtime`에 `for` `OMP_SCHEDULE` `parallel for` 대한 및 기타 일정 유형이 있는 지시문은 무시됩니다. 이 환경 변수의 기본값은 구현 정의입니다. 선택적 *chunk_size* 설정된 경우 값은 양수여야 합니다. *chunk_size* 설정되지 않은 경우 일정이 있는 경우를 제외하고 `static`1의 값이 가정됩니다. `static` 일람표의 경우 기본 청크 크기는 루프 반복 공간으로 루프에 적용된 스레드 수로 구분됩니다.

예제:

```csh
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

### <a name="cross-references"></a>상호 참조

- [지시문에 대 한](2-directives.md#241-for-construct)
- 지시문에 [대한 병렬](2-directives.md#251-parallel-for-construct)

## <a name="42-omp_num_threads"></a><a name="42-omp_num_threads"></a>4.2 OMP_NUM_THREADS

환경 `OMP_NUM_THREADS` 변수는 실행 중에 사용할 스레드의 기본 수를 설정합니다. `OMP_NUM_THREADS`라이브러리 루틴을 호출하여 해당 번호가 `omp_set_num_threads` 명시적으로 변경되면 무시됩니다. `parallel` 지시문에 명시적 `num_threads` 절이 있는 경우 무시됩니다.

환경 변수의 `OMP_NUM_THREADS` 값은 양수 정수여야 합니다. 그 효과는 스레드 수의 동적 조정이 활성화되어 있는지 여부에 따라 달라집니다. `OMP_NUM_THREADS` 환경 변수와 스레드의 동적 조정 간의 상호 작용에 대한 포괄적인 규칙 집합은 [섹션 2.3을](2-directives.md#23-parallel-construct)참조하십시오.

사용할 스레드 수는 다음과 같은 경우 구현 정의됩니다.

- 환경 `OMP_NUM_THREADS` 변수가 지정되지 않은 경우
- 지정된 값이 양수 정수가 아니거나
- 값이 시스템에서 지원할 수 있는 최대 스레드 수보다 큽합니다.

예제:

```csh
setenv OMP_NUM_THREADS 16
```

### <a name="cross-references"></a>상호 참조

- [num_threads](2-directives.md#23-parallel-construct) 절
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) 기능
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) 기능

## <a name="43-omp_dynamic"></a><a name="43-omp_dynamic"></a>4.3 OMP_DYNAMIC

환경 `OMP_DYNAMIC` 변수는 병렬 영역 실행에 사용할 수 있는 스레드 수를 동적 조정을 사용하거나 사용하지 않도록 설정합니다. `OMP_DYNAMIC`동적 조정이 명시적으로 활성화되거나 라이브러리 `omp_set_dynamic` 루틴을 호출하여 비활성화되면 무시됩니다. 해당 값은 `TRUE` `FALSE`또는 값이어야 합니다.

로 설정된 경우 `OMP_DYNAMIC` 병렬 영역을 실행하는 데 사용되는 스레드 수를 런타임 환경에 의해 조정하여 시스템 리소스를 가장 잘 사용할 수 있습니다. `TRUE`  로 설정된 경우 `OMP_DYNAMIC` 동적 조정이 비활성화됩니다. `FALSE` 기본 조건은 구현 정의입니다.

예제:

```csh
setenv OMP_DYNAMIC TRUE
```

### <a name="cross-references"></a>상호 참조

- [병렬 영역](2-directives.md#23-parallel-construct)
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) 기능

## <a name="44-omp_nested"></a><a name="44-omp_nested"></a>4.4 OMP_NESTED

환경 `OMP_NESTED` 변수는 라이브러리 루틴을 호출하여 중첩된 병렬 처리가 활성화되거나 비활성화되지 않는 한 중첩된 병렬 처리를 `omp_set_nested` 활성화하거나 사용하지 않도록 설정합니다. 로 설정된 경우 `OMP_NESTED` 중첩된 병렬 처리가 활성화됩니다. `TRUE` 로 설정된 경우 `OMP_NESTED` 중첩된 병렬 처리는 비활성화됩니다. `FALSE` 기본값은 `FALSE`입니다.

예제:

```csh
setenv OMP_NESTED TRUE
```

### <a name="cross-reference"></a>상호 참조

- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) 기능
