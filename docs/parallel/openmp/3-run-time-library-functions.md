---
title: 3. 런타임 라이브러리 함수
ms.date: 05/13/2019
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
ms.openlocfilehash: 767c006b0a2d81af4d1f8f2e23f84d7847326f31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370279"
---
# <a name="3-run-time-library-functions"></a>3. 런타임 라이브러리 기능

이 섹션에서는 OpenMP C 및 C++ 런타임 라이브러리 함수에 대해 설명합니다. >헤더 ** \<omp.h는** 병렬 실행 환경을 제어하고 쿼리하는 데 사용할 수 있는 여러 함수와 데이터에 대한 액세스를 동기화하는 데 사용할 수 있는 잠금 함수의 두 가지 형식을 선언합니다.

형식은 `omp_lock_t` 잠금을 사용할 수 있거나 스레드가 잠금을 소유하는 것을 나타내는 개체 형식입니다. 이러한 잠금을 단순 *잠금이라고*합니다.

형식은 `omp_nest_lock_t` 잠금을 사용할 수 있는 개체 형식 또는 잠금을 소유 하는 스레드의 ID와 *중첩 수를* 모두 나타내는 개체 형식입니다(아래에 설명). 이러한 잠금을 *중첩 가능한 잠금이라고*합니다.

라이브러리 함수는 "C" 연결이 있는 외부 함수입니다.

이 장의 설명은 다음 항목으로 나뉩니다.

- [실행 환경 기능](#31-execution-environment-functions)
- [잠금 기능](#32-lock-functions)
- [타이밍 루틴](#33-timing-routines)

## <a name="31-execution-environment-functions"></a>3.1 실행 환경 기능

이 섹션에서 설명하는 함수는 스레드, 프로세서 및 병렬 환경에 영향을 미치고 모니터링합니다.

- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_get_max_threads](#313-omp_get_max_threads-function)
- [omp_get_thread_num](#314-omp_get_thread_num-function)
- [omp_get_num_procs](#315-omp_get_num_procs-function)
- [omp_in_parallel](#316-omp_in_parallel-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [omp_get_dynamic](#318-omp_get_dynamic-function)
- [omp_set_nested](#319-omp_set_nested-function)
- [omp_get_nested](#3110-omp_get_nested-function)

### <a name="311-omp_set_num_threads-function"></a><a name="311-omp_set_num_threads-function"></a>3.1.1 omp_set_num_threads 기능

함수는 `omp_set_num_threads` `num_threads` 절을 지정하지 않는 이후 병렬 영역에 사용할 기본 스레드 수를 설정합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_set_num_threads(int num_threads);
```

*num_threads* 매개 변수값은 양수 정수여야 합니다. 그 효과는 스레드 수의 동적 조정이 활성화되어 있는지 여부에 따라 달라집니다. `omp_set_num_threads` 함수와 스레드의 동적 조정 간의 상호 작용에 대한 포괄적인 규칙 집합은 [섹션 2.3을](2-directives.md#23-parallel-construct)참조하십시오.

이 함수는 함수가 0을 반환하는 프로그램의 일부에서 호출될 때 위에서 설명한 `omp_in_parallel` 효과가 있습니다. `omp_in_parallel` 함수가 zero가 아닌 값을 반환하는 프로그램의 일부에서 호출되는 경우 이 함수의 동작은 정의되지 않습니다.

이 호출은 환경 `OMP_NUM_THREADS` 변수보다 우선합니다. 호출하거나 `omp_set_num_threads` 환경 변수를 설정하여 설정할 수 있는 스레드 수의 기본값은 `num_threads` 절을 지정하여 `parallel` 단일 지시문에서 명시적으로 재정의할 수 있습니다. `OMP_NUM_THREADS`

자세한 내용은 [omp_set_dynamic](#317-omp_set_dynamic-function)를 참조하십시오.

#### <a name="cross-references"></a>상호 참조

- [omp_set_dynamic](#317-omp_set_dynamic-function) 기능
- [omp_get_dynamic](#318-omp_get_dynamic-function) 기능
- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads) 환경 변수
- [num_threads](2-directives.md#23-parallel-construct) 절

### <a name="312-omp_get_num_threads-function"></a><a name="312-omp_get_num_threads-function"></a>3.1.2 omp_get_num_threads 기능

함수는 `omp_get_num_threads` 현재 팀에서 호출되는 병렬 영역을 실행하는 스레드 수를 반환합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_num_threads(void);
```

절, `num_threads` `omp_set_num_threads` 함수 및 `OMP_NUM_THREADS` 환경 변수는 팀의 스레드 수를 제어합니다.

사용자가 스레드 수를 명시적으로 설정하지 않은 경우 기본값은 구현 정의입니다. 이 함수는 가장 가까운 `parallel` 둘러싸는 지시문에 바인딩됩니다. 프로그램의 직렬 부분 또는 직렬화된 중첩된 병렬 영역에서 호출된 경우 이 함수는 1을 반환합니다.

자세한 내용은 [omp_set_dynamic](#317-omp_set_dynamic-function)를 참조하십시오.

#### <a name="cross-references"></a>상호 참조

- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads)
- [num_threads](2-directives.md#23-parallel-construct)
- [parallel](2-directives.md#23-parallel-construct)

### <a name="313-omp_get_max_threads-function"></a><a name="313-omp_get_max_threads-function"></a>3.1.3 omp_get_max_threads 기능

함수는 `omp_get_max_threads` `num_threads` 절이 없는 병렬 영역이 코드의 해당 지점에서 볼 수 있는 경우 팀을 구성하는 데 사용되는 스레드 수만큼 적어도 큰 정수를 반환합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_max_threads(void);
```

다음은 다음의 `omp_get_max_threads`값에 대한 하한을 표현합니다.

> *다음 팀을 위해 사용되는 스레드* <= `omp_get_max_threads`

다른 병렬 영역이 절을 `num_threads` 사용하여 특정 수의 스레드를 요청하는 경우 결과의 하한에 대한 보증이 더 `omp_get_max_threads` 이상 보유되지 않습니다.

`omp_get_max_threads` 함수의 반환 값을 사용하여 다음 병렬 영역에서 형성된 팀의 모든 스레드에 대해 충분한 저장소를 동적으로 할당할 수 있습니다.

#### <a name="cross-references"></a>상호 참조

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [num_threads](2-directives.md#23-parallel-construct)

### <a name="314-omp_get_thread_num-function"></a><a name="314-omp_get_thread_num-function"></a>3.1.4 omp_get_thread_num 기능

함수는 `omp_get_thread_num` 함수를 실행하는 스레드의 팀 내에서 스레드 번호를 반환합니다. 스레드 번호는 0에서 `omp_get_num_threads()`-1 사이이며 포함됩니다. 팀의 마스터 스레드는 스레드 0입니다.

형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_thread_num(void);
```

직렬 영역에서 호출된 `omp_get_thread_num` 경우 0을 반환합니다. 직렬화된 중첩된 병렬 영역 내에서 호출되는 경우 이 함수는 0을 반환합니다.

#### <a name="cross-references"></a>상호 참조

- [omp_get_num_threads](#312-omp_get_num_threads-function) 기능

### <a name="315-omp_get_num_procs-function"></a><a name="315-omp_get_num_procs-function"></a>3.1.5 omp_get_num_procs 기능

이 `omp_get_num_procs` 함수는 함수가 호출될 때 프로그램에서 사용할 수 있는 프로세서 수를 반환합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_num_procs(void);
```

### <a name="316-omp_in_parallel-function"></a><a name="316-omp_in_parallel-function"></a>3.1.6 omp_in_parallel 기능

함수는 `omp_in_parallel` 병렬로 실행되는 병렬 영역의 동적 범위 내에서 호출되는 경우 비영값을 반환합니다. 그렇지 않으면 0을 반환합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_in_parallel(void);
```

이 함수는 직렬화된 중첩 영역을 포함하여 병렬로 실행되는 영역 내에서 호출될 때 비영값을 반환합니다.

### <a name="317-omp_set_dynamic-function"></a><a name="317-omp_set_dynamic-function"></a>3.1.7 omp_set_dynamic 기능

이 `omp_set_dynamic` 함수는 병렬 영역 실행에 사용할 수 있는 스레드 수를 동적으로 조정하거나 비활성화합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_set_dynamic(int dynamic_threads);
```

*dynamic_threads* 0이 아닌 값으로 평가되는 경우, 다가오는 병렬 영역을 실행하는 데 사용되는 스레드 수는 런타임 환경에 의해 자동으로 조정되어 시스템 리소스를 가장 잘 사용할 수 있습니다. 결과적으로 사용자가 지정한 스레드 수는 최대 스레드 수입니다. 병렬 영역을 실행하는 팀의 스레드 수는 해당 병렬 영역의 기간 동안 고정된 상태로 `omp_get_num_threads` 유지되며 함수에 의해 보고됩니다.

*dynamic_threads* 0으로 평가하면 동적 조정이 비활성화됩니다.

이 함수는 함수가 0을 반환하는 프로그램의 일부에서 호출될 때 위에서 설명한 `omp_in_parallel` 효과가 있습니다. `omp_in_parallel` 함수가 zero가 아닌 값을 반환하는 프로그램의 일부에서 호출되는 경우 이 함수의 동작은 정의되지 않습니다.

환경 변수보다 `omp_set_dynamic` 우선 순위가 `OMP_DYNAMIC` 있는 호출입니다.

스레드의 동적 조정의 기본값은 구현 정의입니다. 따라서 올바른 실행을 위해 특정 수의 스레드에 의존하는 사용자 코드는 동적 스레드를 명시적으로 사용하지 않도록 설정해야 합니다. 구현은 스레드 수를 동적으로 조정할 수 있는 기능을 제공할 필요는 없지만 모든 플랫폼에서 이식성을 지원하는 인터페이스를 제공해야 합니다.

#### <a name="microsoft-specific"></a>Microsoft 전용

의 현재 `omp_get_dynamic` `omp_set_dynamic` 지원은 다음과 같습니다.

입력 매개 `omp_set_dynamic` 변수는 스레딩 정책에 영향을 주지 않으며 스레드 수를 변경하지 않습니다. `omp_get_num_threads`항상 사용자 정의 번호(설정된 경우)를 반환하거나 기본 스레드 번호를 반환합니다. 현재 Microsoft 구현에서는 `omp_set_dynamic(0)` 동적 스레딩을 해제하여 다음 병렬 영역에 대해 기존 스레드 집합을 다시 사용할 수 있습니다. `omp_set_dynamic(1)`기존 스레드 집합을 삭제하고 다가오는 병렬 영역에 대한 새 집합을 만들어 동적 스레딩을 켭니다. 새 집합의 스레드 수는 이전 집합과 동일하며 `omp_get_num_threads`의 반환 값을 기반으로 합니다. 따라서 최상의 성능을 위해 `omp_set_dynamic(0)` 기존 스레드를 재사용하는 데 사용합니다.

#### <a name="cross-references"></a>상호 참조

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="318-omp_get_dynamic-function"></a><a name="318-omp_get_dynamic-function"></a>3.1.8 omp_get_dynamic 기능

스레드의 동적 조정이 활성화된 경우 함수는 `omp_get_dynamic` 0이 아닌 값을 반환하고 그렇지 않으면 0을 반환합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_dynamic(void);
```

구현에서 스레드 수의 동적 조정을 구현하지 않는 경우 이 함수는 항상 0을 반환합니다. 자세한 내용은 [omp_set_dynamic](#317-omp_set_dynamic-function)를 참조하십시오.

#### <a name="cross-references"></a>상호 참조

- 동적 스레드 조정에 대한 설명은 [omp_set_dynamic](#317-omp_set_dynamic-function)를 참조하십시오.

### <a name="319-omp_set_nested-function"></a><a name="319-omp_set_nested-function"></a>3.1.9 omp_set_nested 기능

이 `omp_set_nested` 함수는 중첩된 병렬 처리기능을 활성화하거나 사용하지 않도록 설정합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_set_nested(int nested);
```

*중첩이* 0으로 평가되는 경우 중첩된 병렬 처리는 기본값인 비활성화되고 중첩된 병렬 영역은 현재 스레드에 의해 직렬화되고 실행됩니다. 그렇지 않으면 중첩된 병렬 처리가 활성화되고 중첩된 병렬 영역이 추가 스레드를 배포하여 중첩된 팀을 구성할 수 있습니다.

이 함수는 함수가 0을 반환하는 프로그램의 일부에서 호출될 때 위에서 설명한 `omp_in_parallel` 효과가 있습니다. `omp_in_parallel` 함수가 zero가 아닌 값을 반환하는 프로그램의 일부에서 호출되는 경우 이 함수의 동작은 정의되지 않습니다.

이 호출은 환경 `OMP_NESTED` 변수보다 우선합니다.

중첩된 병렬 처리가 활성화되면 중첩된 병렬 영역을 실행하는 데 사용되는 스레드 수가 구현 정의됩니다. 따라서 OpenMP 호환 구현은 중첩병렬 처리가 활성화된 경우에도 중첩된 병렬 영역을 직렬화할 수 있습니다.

#### <a name="cross-references"></a>상호 참조

- [OMP_NESTED](4-environment-variables.md#44-omp_nested)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="3110-omp_get_nested-function"></a><a name="3110-omp_get_nested-function"></a>3.1.10 omp_get_nested 기능

중첩된 `omp_get_nested` 병렬 처리가 활성화된 경우 함수는 0이 아닌 값을 반환하고 비활성화된 경우 0을 반환합니다. 중첩된 병렬 처리에 대한 자세한 내용은 [omp_set_nested](#319-omp_set_nested-function)를 참조하십시오. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_nested(void);
```

구현이 중첩 된 병렬 성을 구현 하지 않는 경우이 함수는 항상 0을 반환 합니다.

## <a name="32-lock-functions"></a>3.2 잠금 기능

이 섹션에서 설명하는 함수는 동기화에 사용되는 잠금을 조작합니다.

다음 함수의 경우 lock 변수에는 `omp_lock_t`type이 있어야 합니다. 이 변수는 이러한 함수를 통해서만 액세스해야 합니다. 모든 잠금 함수에는 `omp_lock_t` 입력할 포인터가 있는 인수가 필요합니다.

- [omp_init_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) 함수는 간단한 잠금을 초기화합니다.
- [omp_destroy_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) 기능은 간단한 잠금을 제거합니다.
- [omp_set_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) 함수는 간단한 잠금을 사용할 수 있게 될 때까지 기다립니다.
- [omp_unset_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) 함수는 간단한 잠금을 해제합니다.
- [omp_test_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) 함수는 간단한 잠금을 테스트합니다.

다음 함수의 경우 lock 변수에는 `omp_nest_lock_t`type이 있어야 합니다.  이 변수는 이러한 함수를 통해서만 액세스해야 합니다. 모든 중첩 가능한 잠금 함수에는 `omp_nest_lock_t` 입력할 포인터가 있는 인수가 필요합니다.

- [omp_init_nest_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) 함수는 중첩 가능한 잠금을 초기화합니다.
- [omp_destroy_nest_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) 함수는 중첩 가능한 잠금을 제거합니다.
- [omp_set_nest_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) 함수는 중첩 가능한 잠금을 사용할 수 있을 때까지 기다립니다.
- [omp_unset_nest_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) 함수는 중첩 가능한 잠금을 해제합니다.
- [omp_test_nest_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) 함수는 중첩 가능한 잠금을 테스트합니다.

OpenMP 잠금 함수는 항상 잠금 변수의 최신 값을 읽고 업데이트하는 방식으로 잠금 변수에 액세스합니다. 따라서 OpenMP 프로그램에 명시적 `flush` 지시문을 포함하여 잠금 변수의 값이 다른 스레드 간에 일관되도록 할 필요는 없습니다. (다른 변수의 값을 `flush` 일관되게 만들기 위해 지시문이 필요할 수 있습니다.)

### <a name="321-omp_init_lock-and-omp_init_nest_lock-functions"></a><a name="321-omp_init_lock-and-omp_init_nest_lock-functions"></a>3.2.1 omp_init_lock 및 omp_init_nest_lock 기능

이러한 함수는 잠금을 초기화하는 유일한 수단을 제공합니다. 각 함수는 다가오는 호출에서 사용할 매개 변수 *잠금과* 연결된 잠금을 초기화합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

초기 상태가 잠금 해제됩니다(즉, 어떤 스레드도 잠금을 소유하지 않습니다). 중첩 가능한 잠금의 경우 초기 중첩 수는 0입니다. 이미 초기화 된 잠금 변수를 사용하여 이러한 루틴 중 하나를 호출하는 것은 규격이 아닙니다.

### <a name="322-omp_destroy_lock-and-omp_destroy_nest_lock-functions"></a><a name="322-omp_destroy_lock-and-omp_destroy_nest_lock-functions"></a>3.2.2 omp_destroy_lock 및 omp_destroy_nest_lock 기능

이러한 함수는 가리키는 잠금 변수 *잠금이* 초기화되지 않았는지 확인합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

초기화되지 않았거나 잠금해제된 잠금 변수를 사용하여 이러한 루틴 중 하나를 호출하는 것은 규격이 아닙니다.

### <a name="323-omp_set_lock-and-omp_set_nest_lock-functions"></a><a name="323-omp_set_lock-and-omp_set_nest_lock-functions"></a>3.2.3 omp_set_lock 및 omp_set_nest_lock 기능

이러한 각 함수는 지정된 잠금을 사용할 수 있게 될 때까지 함수를 실행하는 스레드를 차단한 다음 잠금을 설정합니다. 잠금 이 해제된 경우 간단한 잠금 장치를 사용할 수 있습니다. 중첩 가능한 잠금은 잠금이 해제되어 있거나 함수를 실행하는 스레드가 이미 소유하고 있는 경우 사용할 수 있습니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

간단한 잠금을 위해 함수에 `omp_set_lock` 대한 인수는 초기화된 잠금 변수를 가리커야 합니다. 잠금을 의 소유권은 함수를 실행하는 스레드에 부여됩니다.

중첩 가능한 잠금의 경우 `omp_set_nest_lock` 함수에 대한 인수는 초기화된 잠금 변수를 가리커야 합니다. 중첩 수는 증가되고 스레드에 잠금의 소유권이 부여되거나 유지됩니다.

### <a name="324-omp_unset_lock-and-omp_unset_nest_lock-functions"></a><a name="324-omp_unset_lock-and-omp_unset_nest_lock-functions"></a>3.2.4 omp_unset_lock 및 omp_unset_nest_lock 기능

이러한 함수는 잠금의 소유권을 해제하는 수단을 제공합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_unset_lock(omp_lock_t *lock);
void omp_unset_nest_lock(omp_nest_lock_t *lock);
```

이러한 각 함수에 대한 인수는 함수를 실행하는 스레드가 소유한 초기화된 잠금 변수를 가리커야 합니다. 스레드가 해당 잠금을 소유하지 않는 경우 동작이 정의되지 않습니다.

간단한 잠금을 위해 `omp_unset_lock` 함수는 잠금 소유권에서 함수를 실행하는 스레드를 해제합니다.

중첩 가능한 잠금의 `omp_unset_nest_lock` 경우 함수는 중첩 수를 줄이고 결과 수가 0이면 잠금 소유권에서 함수를 실행하는 스레드를 해제합니다.

### <a name="325-omp_test_lock-and-omp_test_nest_lock-functions"></a><a name="325-omp_test_lock-and-omp_test_nest_lock-functions"></a>3.2.5 omp_test_lock 및 omp_test_nest_lock 기능

이러한 함수는 잠금을 설정하려고 시도하지만 스레드의 실행을 차단하지는 않습니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

인수는 초기화된 잠금 변수를 가리커야 합니다. 이러한 함수는 스레드 실행을 차단하지 않는다는 `omp_set_nest_lock`점을 제외하고는 잠금과 동일한 방식으로 `omp_set_lock` 잠금을 설정하려고 시도합니다.

간단한 잠금의 경우 `omp_test_lock` 잠금이 성공적으로 설정된 경우 함수는 zero가 아닌 값을 반환합니다. 그렇지 않으면 0을 반환합니다.

중첩 가능한 잠금의 `omp_test_nest_lock` 경우 잠금이 성공적으로 설정된 경우 함수는 새 중첩 수를 반환합니다. 그렇지 않으면 0을 반환합니다.

## <a name="33-timing-routines"></a>3.3 타이밍 루틴

이 섹션에 설명된 기능은 휴대용 월 클럭 타이머를 지원합니다.

- [omp_get_wtime](#331-omp_get_wtime-function) 함수는 경과된 월 클럭 시간을 반환합니다.
- [omp_get_wtick](#332-omp_get_wtick-function) 함수는 연속된 클럭 틱 사이에 초를 반환합니다.

### <a name="331-omp_get_wtime-function"></a><a name="331-omp_get_wtime-function"></a>3.3.1 omp_get_wtime 기능

이 `omp_get_wtime` 함수는 일부 "과거의 시간"이기 때문에 경과된 벽 클럭 시간과 동일한 이중 정밀도 부동 점 값을 초 단위로 반환합니다.  실제 "과거의 시간"은 임의적이지만 응용 프로그램 실행 중에 변경되지 않도록 보장됩니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
double omp_get_wtime(void);
```

함수는 다음 예제와 같이 경과 시간을 측정하는 데 사용될 것으로 예상됩니다.

```cpp
double start;
double end;
start = omp_get_wtime();
... work to be timed ...
end = omp_get_wtime();
printf_s("Work took %f sec. time.\n", end-start);
```

반환되는 시간은 "스레드당 시간"으로, 응용 프로그램에 참여하는 모든 스레드에서 전역적으로 일관되지 않아도 됩니다.

### <a name="332-omp_get_wtick-function"></a><a name="332-omp_get_wtick-function"></a>3.3.2 omp_get_wtick 기능

함수는 `omp_get_wtick` 연속된 클럭 틱 사이의 초 수와 동일한 이중 정밀도 부동 소수점 값을 반환합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
double omp_get_wtick(void);
```
