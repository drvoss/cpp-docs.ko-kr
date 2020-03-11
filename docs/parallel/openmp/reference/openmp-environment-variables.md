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
ms.openlocfilehash: 838427320fcb68cedb97b36156fc18002ed962d8
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78882912"
---
# <a name="openmp-environment-variables"></a>OpenMP 환경 변수

OpenMP API에서 사용되는 환경 변수에 대한 링크를 제공합니다.

OpenMP 표준 C++ 의 시각적 구현에는 다음과 같은 환경 변수가 포함 됩니다. 이러한 환경 변수는 프로그램 시작 시에 읽을 수 있으며 해당 값에 대 한 수정 내용은 런타임에 무시 됩니다 (예: [_putenv _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)사용).

|환경 변수|설명|
|--------------------|-----------|
|[OMP_SCHEDULE](#omp-schedule)|`for` 또는 `parallel for` 지시문에 `schedule(runtime)` 지정 된 경우 [schedule](openmp-clauses.md#schedule) 절의 동작을 수정 합니다.|
|[OMP_NUM_THREADS](#omp-num-threads)|[Omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 또는 [num_threads](openmp-clauses.md#num-threads)에 의해 재정의 되지 않는 한 병렬 영역에 있는 최대 스레드 수를 설정 합니다.|
|[OMP_DYNAMIC](#omp-dynamic)|OpenMP 런타임에서 병렬 영역의 스레드 수를 조정할 수 있는지 여부를 지정 합니다.|
|[OMP_NESTED](#omp-nested)|`omp_set_nested`로 중첩 된 병렬 처리를 사용 하거나 사용 하지 않도록 설정 하지 않는 한 중첩 된 병렬 처리를 사용할지 여부를 지정 합니다.|

## <a name="omp-dynamic"></a>OMP_DYNAMIC

OpenMP 런타임에서 병렬 영역의 스레드 수를 조정할 수 있는지 여부를 지정 합니다.

```cmd
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>설명

[Omp_set_dynamic](openmp-functions.md#omp-set-dynamic) 함수를 통해 `OMP_DYNAMIC` 환경 변수를 재정의할 수 있습니다.

OpenMP 표준의 시각적 C++ 구현에서 기본값은 `OMP_DYNAMIC=FALSE`입니다.

자세한 내용은 [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md)를 참조 하세요.

### <a name="example"></a>예제

다음 명령은 `OMP_DYNAMIC` 환경 변수를 TRUE로 설정 합니다.

```cmd
set OMP_DYNAMIC=TRUE
```

다음 명령은 `OMP_DYNAMIC` 환경 변수의 현재 설정을 표시 합니다.

```cmd
set OMP_DYNAMIC
```

## <a name="omp-nested"></a>OMP_NESTED

`omp_set_nested`로 중첩 된 병렬 처리를 사용 하거나 사용 하지 않도록 설정 하지 않는 한 중첩 된 병렬 처리를 사용할지 여부를 지정 합니다.

```cmd
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>설명

[Omp_set_nested](openmp-functions.md#omp-set-nested) 함수를 통해 `OMP_NESTED` 환경 변수를 재정의할 수 있습니다.

OpenMP 표준의 시각적 C++ 구현에서 기본값은 `OMP_DYNAMIC=FALSE`입니다.

자세한 내용은 [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md)를 참조 하세요.

### <a name="example"></a>예제

다음 명령은 `OMP_NESTED` 환경 변수를 TRUE로 설정 합니다.

```cmd
set OMP_NESTED=TRUE
```

다음 명령은 `OMP_NESTED` 환경 변수의 현재 설정을 표시 합니다.

```cmd
set OMP_NESTED
```

## <a name="omp-num-threads"></a>OMP_NUM_THREADS

[Omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 또는 [num_threads](openmp-clauses.md#num-threads)에 의해 재정의 되지 않는 한 병렬 영역에 있는 최대 스레드 수를 설정 합니다.

```cmd
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>매개 변수

*num*<br/>
병렬 영역에 있는 최대 스레드 수입니다. 시각적 C++ 구현에서는 최대 64입니다.

### <a name="remarks"></a>설명

`OMP_NUM_THREADS` 환경 변수는 [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 함수 또는 [num_threads](openmp-clauses.md#num-threads)에서 재정의할 수 있습니다.

OpenMP 표준의 시각적 C++ 구현에서 `num`의 기본값은 하이퍼스레딩을 cpu를 포함 하는 가상 프로세서의 수입니다.

자세한 내용은 [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md)를 참조 하세요.

### <a name="example"></a>예제

다음 명령은 `OMP_NUM_THREADS` 환경 변수를 `16`으로 설정 합니다.

```cmd
set OMP_NUM_THREADS=16
```

다음 명령은 `OMP_NUM_THREADS` 환경 변수의 현재 설정을 표시 합니다.

```cmd
set OMP_NUM_THREADS
```

## <a name="omp-schedule"></a>OMP_SCHEDULE

`for` 또는 `parallel for` 지시문에 `schedule(runtime)` 지정 된 경우 [schedule](openmp-clauses.md#schedule) 절의 동작을 수정 합니다.

```cmd
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>매개 변수

*size*<br/>
필드 반복의 크기를 지정 합니다. *크기* 는 양의 정수 여야 합니다. *형식이* static 인 경우를 제외 하 고 기본값은 `1`입니다. *형식이* `runtime`경우 유효 하지 않습니다.

*type*<br/>
예약의 종류 `dynamic`, `guided`, `runtime`또는 `static`입니다.

### <a name="remarks"></a>설명

OpenMP 표준의 시각적 C++ 구현에서 기본값은 `OMP_SCHEDULE=static,0`입니다.

자세한 내용은 [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md)를 참조 하세요.

### <a name="example"></a>예제

다음 명령은 `OMP_SCHEDULE` 환경 변수를 설정 합니다.

```cmd
set OMP_SCHEDULE="guided,2"
```

다음 명령은 `OMP_SCHEDULE` 환경 변수의 현재 설정을 표시 합니다.

```cmd
set OMP_SCHEDULE
```
