---
title: OpenMP 환경 변수
ms.date: 03/20/2019
f1_keywords:
- OpenMP environment variables
- OMP_DYNAMIC
- OMP_NESTED
- OMP_NUM_THREADS
- OMP_SCHEDULE
helpviewer_keywords:
- OpenMP environment variables
- OMP_DYNAMIC OpenMP environment variable
- OMP_NESTED OpenMP environment variable
- OMP_NUM_THREADS OpenMP environment variable
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
ms.openlocfilehash: bee9b0fbdf147ee962ff92d0b3b9ff57d4209f84
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363880"
---
# <a name="openmp-environment-variables"></a>OpenMP 환경 변수

OpenMP API에 사용되는 환경 변수에 대한 링크를 제공합니다.

OpenMP 표준의 Visual C++ 구현에는 다음 환경 변수가 포함됩니다. 이러한 환경 변수는 프로그램 시작 시 읽으며 런타임시(예: [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)사용)에서 해당 값에 대한 수정은 무시됩니다.

|환경 변수|Description|
|--------------------|-----------|
|[OMP_SCHEDULE](#omp-schedule)|또는 `parallel for` 지시문에 지정 [schedule](openmp-clauses.md#schedule) 될 때 `schedule(runtime)` 일정 절의 동작을 수정 합니다. `for`|
|[OMP_NUM_THREADS](#omp-num-threads)|[omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 또는 [num_threads](openmp-clauses.md#num-threads)의해 재정의되지 않는 한 병렬 영역에서 최대 스레드 수를 설정합니다.|
|[OMP_DYNAMIC](#omp-dynamic)|OpenMP 런타임이 병렬 영역의 스레드 수를 조정할 수 있는지 여부를 지정합니다.|
|[OMP_NESTED](#omp-nested)|중첩 된 병렬 처리가 사용 가능 하거나 사용 하지 않는 `omp_set_nested`한 중첩 된 병렬 처리가 사용 가능 여부를 지정 합니다.|

## <a name="omp_dynamic"></a><a name="omp-dynamic"></a>OMP_DYNAMIC

OpenMP 런타임이 병렬 영역의 스레드 수를 조정할 수 있는지 여부를 지정합니다.

```cmd
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>설명

환경 `OMP_DYNAMIC` 변수는 [omp_set_dynamic](openmp-functions.md#omp-set-dynamic) 함수에 의해 재정의될 수 있습니다.

OpenMP 표준의 Visual C++ 구현의 기본값은 . `OMP_DYNAMIC=FALSE`

자세한 내용은 [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md)를 참조하십시오.

### <a name="example"></a>예제

다음 명령은 환경 `OMP_DYNAMIC` 변수를 TRUE로 설정합니다.

```cmd
set OMP_DYNAMIC=TRUE
```

다음 명령은 `OMP_DYNAMIC` 환경 변수의 현재 설정을 표시합니다.

```cmd
set OMP_DYNAMIC
```

## <a name="omp_nested"></a><a name="omp-nested"></a>OMP_NESTED

중첩 된 병렬 처리가 사용 가능 하거나 사용 하지 않는 `omp_set_nested`한 중첩 된 병렬 처리가 사용 가능 여부를 지정 합니다.

```cmd
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>설명

환경 `OMP_NESTED` 변수는 [omp_set_nested](openmp-functions.md#omp-set-nested) 함수에 의해 재정의될 수 있습니다.

OpenMP 표준의 Visual C++ 구현의 기본값은 . `OMP_DYNAMIC=FALSE`

자세한 내용은 [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md)를 참조하십시오.

### <a name="example"></a>예제

다음 명령은 환경 `OMP_NESTED` 변수를 TRUE로 설정합니다.

```cmd
set OMP_NESTED=TRUE
```

다음 명령은 `OMP_NESTED` 환경 변수의 현재 설정을 표시합니다.

```cmd
set OMP_NESTED
```

## <a name="omp_num_threads"></a><a name="omp-num-threads"></a>OMP_NUM_THREADS

[omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 또는 [num_threads](openmp-clauses.md#num-threads)의해 재정의되지 않는 한 병렬 영역에서 최대 스레드 수를 설정합니다.

```cmd
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>매개 변수

*num*<br/>
Visual C++ 구현에서 최대 64개의 병렬 영역에서 원하는 최대 스레드 수입니다.

### <a name="remarks"></a>설명

환경 `OMP_NUM_THREADS` 변수는 [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 함수 또는 [num_threads](openmp-clauses.md#num-threads)의해 재정의할 수 있습니다.

OpenMP 표준의 Visual C++ 구현의 기본값은 `num` 하이퍼스레딩 CPU를 포함한 가상 프로세서 의 수입니다.

자세한 내용은 [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md)를 참조하십시오.

### <a name="example"></a>예제

다음 명령은 환경 `OMP_NUM_THREADS` 변수를 `16`다음으로 설정합니다.

```cmd
set OMP_NUM_THREADS=16
```

다음 명령은 `OMP_NUM_THREADS` 환경 변수의 현재 설정을 표시합니다.

```cmd
set OMP_NUM_THREADS
```

## <a name="omp_schedule"></a><a name="omp-schedule"></a>OMP_SCHEDULE

또는 `parallel for` 지시문에 지정 [schedule](openmp-clauses.md#schedule) 될 때 `schedule(runtime)` 일정 절의 동작을 수정 합니다. `for`

```cmd
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>매개 변수

*크기*<br/>
(선택 사항) 반복 크기를 지정합니다. *크기는* 양수 정수여야 합니다. 기본값은 `1` *문자가* 정적인 경우를 제외하고 는 에서입니다. *형식이* `runtime`.입니다.

*종류*<br/>
일정의 `dynamic`종류(에 `guided`의한 `runtime`것) `static`

### <a name="remarks"></a>설명

OpenMP 표준의 Visual C++ 구현의 기본값은 . `OMP_SCHEDULE=static,0`

자세한 내용은 [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md)를 참조하십시오.

### <a name="example"></a>예제

다음 명령은 환경 `OMP_SCHEDULE` 변수를 설정합니다.

```cmd
set OMP_SCHEDULE="guided,2"
```

다음 명령은 `OMP_SCHEDULE` 환경 변수의 현재 설정을 표시합니다.

```cmd
set OMP_SCHEDULE
```
