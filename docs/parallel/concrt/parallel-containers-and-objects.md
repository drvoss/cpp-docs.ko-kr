---
title: 병렬 컨테이너 및 개체
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: f3fb2bb57c8bcf65de0a7f74f2992050d8257429
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363052"
---
# <a name="parallel-containers-and-objects"></a>병렬 컨테이너 및 개체

PPL(병렬 패턴 라이브러리)에는 해당 요소에 대한 스레드 안전 액세스를 제공하는 여러 컨테이너 및 개체가 포함되어 있습니다.

*동시 컨테이너는* 가장 중요한 작업에 동시성 으로 안전한 액세스를 제공합니다. 여기서 동시성 안전은 포인터 또는 이터레이터가 항상 유효하다는 것을 의미합니다. 요소 초기화 또는 특정 순회 순서를 보장하지 않습니다. 이러한 컨테이너의 기능은 C++ 표준 라이브러리에서 제공하는 기능과 유사합니다. 예를 들어 [동시성::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) 클래스는 [std::vector](../../standard-library/vector-class.md) 클래스와 유사하지만 클래스를 `concurrent_vector` 사용하면 요소를 병렬로 부수게 됩니다. 동일한 컨테이너에 대한 읽기 및 쓰기 액세스가 모두 필요한 병렬 코드가 있는 경우 동시 컨테이너를 사용합니다.

*동시 객체는* 구성 요소 간에 동시에 공유됩니다. 동시 객체의 상태를 병렬로 계산하는 프로세스는 동일한 상태를 직렬로 계산하는 다른 프로세스와 동일한 결과를 생성합니다. [동시성::결합 가능한](../../parallel/concrt/reference/combinable-class.md) 클래스는 동시 개체 유형의 한 예입니다. 클래스를 `combinable` 사용하면 계산을 병렬로 수행한 다음 이러한 계산을 최종 결과로 결합할 수 있습니다. 뮤텍스와 같은 동기화 메커니즘을 사용하여 공유 변수 또는 리소스에 대한 액세스를 동기화하는 경우 동시 개체를 사용합니다.

## <a name="sections"></a><a name="top"></a>섹션

이 항목에서는 다음과 같은 병렬 컨테이너 및 개체에 대해 자세히 설명합니다.

동시 컨테이너:

- [concurrent_vector 클래스](#vector)

  - [concurrent_vector 벡터의 차이](#vector-differences)

  - [동시성 안전 운영](#vector-safety)

  - [예외 안전](#vector-exceptions)

- [concurrent_queue 클래스](#queue)

  - [concurrent_queue 큐의 차이점](#queue-differences)

  - [동시성 안전 운영](#queue-safety)

  - [이터레이터 지원](#queue-iterators)

- [concurrent_unordered_map 클래스](#unordered_map)

  - [concurrent_unordered_map unordered_map 차이](#map-differences)

  - [동시성 안전 운영](#map-safety)

- [concurrent_unordered_multimap 클래스](#unordered_multimap)

- [concurrent_unordered_set 클래스](#unordered_set)

- [concurrent_unordered_multiset 클래스](#unordered_multiset)

동시 객체:

- [combinable 클래스](#combinable)

  - [방법 및 기능](#combinable-features)

  - [예](#combinable-examples)

## <a name="concurrent_vector-class"></a><a name="vector"></a>concurrent_vector 클래스

[동시성::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) 클래스는 [std::vector](../../standard-library/vector-class.md) 클래스와 마찬가지로 해당 요소에 임의로 액세스할 수 있는 시퀀스 컨테이너 클래스입니다. 클래스는 `concurrent_vector` 동시성 으로 안전한 부가 및 요소 액세스 작업을 활성화합니다. 부속 작업은 기존 포인터 또는 이터레이터를 무효화하지 않습니다. 이터레이터 액세스 및 통과 작업도 동시성으로 안전합니다. 여기서 동시성 안전은 포인터 또는 이터레이터가 항상 유효하다는 것을 의미합니다. 요소 초기화 또는 특정 순회 순서를 보장하지 않습니다.

### <a name="differences-between-concurrent_vector-and-vector"></a><a name="vector-differences"></a>concurrent_vector 벡터의 차이

클래스는 `concurrent_vector` 클래스와 `vector` 매우 유사합니다. `concurrent_vector` 개체에 대한 부속, 요소 액세스 및 이터레이터 액세스 작업의 복잡성은 `vector` 개체와 동일합니다. 다음 사항은 다음과 `concurrent_vector` 다른 `vector`점을 보여 줍니다.

- `concurrent_vector` 개체에 대한 부호, 요소 액세스, 이터레이터 액세스 및 이터레이터 통과 작업은 동시성으로 안전합니다.

- `concurrent_vector` 객체의 끝에만 요소를 추가할 수 있습니다. 클래스는 `concurrent_vector` 메서드를 `insert` 제공하지 않습니다.

- 객체에 `concurrent_vector` 부속할 때 [이동 의미 체계를](../../cpp/rvalue-reference-declarator-amp-amp.md) 사용하지 않습니다.

- 클래스는 `concurrent_vector` 또는 `erase` `pop_back` 메서드를 제공하지 않습니다. 마찬가지로 `vector`에 [있는](reference/concurrent-vector-class.md#clear) 명확한 메서드를 사용하여 `concurrent_vector` 개체에서 모든 요소를 제거합니다.

- 클래스는 `concurrent_vector` 해당 요소를 메모리에 연속적으로 저장하지 않습니다. 따라서 배열을 `concurrent_vector` 사용할 수 있는 모든 방법으로 클래스를 사용할 수 없습니다. 예를 들어 `v` 형식이라는 `concurrent_vector`변수의 경우 `&v[0]+2` 식은 정의되지 않은 동작을 생성합니다.

- 클래스는 `concurrent_vector` [grow_by](reference/concurrent-vector-class.md#grow_by) 및 [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) 메서드를 정의합니다. 이러한 메서드는 동시성 안전성을 제외하면 [크기 조정](reference/concurrent-vector-class.md#resize) 메서드와 유사합니다.

- 객체는 `concurrent_vector` 객체에 요소를 더하거나 크기를 조정할 때 해당 요소를 재배치하지 않습니다. 이렇게 하면 기존 포인터와 반복기는 동시 작업 중에 유효하게 유지됩니다.

- 런타임은 형식에 `concurrent_vector` `bool`대한 특수 버전을 정의하지 않습니다.

### <a name="concurrency-safe-operations"></a><a name="vector-safety"></a>동시성 안전 운영

`concurrent_vector` 개체의 크기를 추가하거나 늘리거나 `concurrent_vector` 개체의 요소에 액세스하는 모든 메서드는 동시성으로 안전합니다. 여기서 동시성 안전은 포인터 또는 이터레이터가 항상 유효하다는 것을 의미합니다. 요소 초기화 또는 특정 순회 순서를 보장하지 않습니다. 이 규칙의 예외는 `resize` 메서드입니다.

다음 표에서는 동시성으로 안전한 일반적인 메서드및 연산자가 보여 주며, 이 에 대한 일반적인 `concurrent_vector` 메서드와 연산자는 다음과 같습니다.

||||
|-|-|-|
|[에](reference/concurrent-vector-class.md#at)|[end](reference/concurrent-vector-class.md#end)|[operator&#91;&#93;](reference/concurrent-vector-class.md#operator_at)|
|[시작](reference/concurrent-vector-class.md#begin)|[앞](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|
|[뒤로](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|
|[용량](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|
|[빈](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[크기](reference/concurrent-vector-class.md#size)|

예를 들어 `reserve`런타임이 C++ 표준 라이브러리와의 호환성을 위해 제공하는 작업은 동시성으로 안전하지 않습니다. 다음 표에서는 동시성으로 안전하지 않은 일반적인 메서드 및 연산자가 보여 주어 도표입니다.

|||
|-|-|
|[할당](reference/concurrent-vector-class.md#assign)|[예약](reference/concurrent-vector-class.md#reserve)|
|[명확한](reference/concurrent-vector-class.md#clear)|[크기 조정](reference/concurrent-vector-class.md#resize)|
|[연산자 =](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

기존 요소의 값을 수정하는 작업은 동시성으로 안전하지 않습니다. [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) 개체와 같은 동기화 개체를 사용하여 동시 읽기 및 쓰기 작업을 동일한 데이터 요소에 동기화합니다. 동기화 개체에 대한 자세한 내용은 [동기화 데이터 구조를](../../parallel/concrt/synchronization-data-structures.md)참조하십시오.

을 사용하는 `concurrent_vector`데 사용하는 `vector` 기존 코드를 변환하면 동시 연산으로 인해 응용 프로그램의 동작이 변경될 수 있습니다. 예를 들어 `concurrent_vector` 개체에서 두 작업을 동시에 수행하는 다음 프로그램을 생각해 보십시오. 첫 번째 작업은 개체에 `concurrent_vector` 추가 요소를 추가합니다. 두 번째 작업은 동일한 개체의 모든 요소의 합계를 계산합니다.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

메서드는 `end` 동시성 으로 안전 하지만 [push_back](reference/concurrent-vector-class.md#push_back) 메서드에 대 한 동시 호출 `end` 변경 에 의해 반환 되는 값을 발생 합니다. 이터레이터가 통과하는 요소 의 수는 확정되지 않습니다. 따라서 이 프로그램은 실행할 때마다 다른 결과를 생성할 수 있습니다. 요소 형식이 간단하지 않은 경우 경합 조건과 `push_back` `end` 호출 사이에 경합 조건이 존재할 수 있습니다. 메서드는 `end` 할당되었지만 완전히 초기화되지 않은 요소를 반환할 수 있습니다.

### <a name="exception-safety"></a><a name="vector-exceptions"></a>예외 안전

증가 또는 할당 작업이 예외를 Throw하면 `concurrent_vector` 개체의 상태가 잘못됩니다. 달리 명시되지 `concurrent_vector` 않는 한 잘못된 상태에 있는 개체의 동작은 정의되지 않습니다. 그러나 소멸자는 개체가 잘못된 상태에 있더라도 개체가 할당하는 메모리를 항상 해제합니다.

벡터 요소의 데이터 형식은 `T`다음 요구 사항을 충족해야 합니다. 그렇지 않으면 클래스의 `concurrent_vector` 동작이 정의되지 않습니다.

- 소멸자는 던져서는 안됩니다.

- 기본 또는 복사 생성자가 throw되면 키워드를 사용하여 `virtual` 소멸자가 선언되지 않아야 하며 초기화되지 않은 메모리가 없는 경우 올바르게 작동해야 합니다.

【[맨 위](#top)】

## <a name="concurrent_queue-class"></a><a name="queue"></a>concurrent_queue 클래스

[동시성::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) 클래스는 [std::queue](../../standard-library/queue-class.md) 클래스와 마찬가지로 앞뒤 요소에 액세스할 수 있습니다. 클래스는 `concurrent_queue` 동시성 안전 큐 및 큐 제거 작업을 활성화합니다. 여기서 동시성 안전은 포인터 또는 이터레이터가 항상 유효하다는 것을 의미합니다. 요소 초기화 또는 특정 순회 순서를 보장하지 않습니다. 또한 `concurrent_queue` 클래스는 동시성으로 안전하지 않은 이터레이터 지원을 제공합니다.

### <a name="differences-between-concurrent_queue-and-queue"></a><a name="queue-differences"></a>concurrent_queue 큐의 차이점

클래스는 `concurrent_queue` 클래스와 `queue` 매우 유사합니다. 다음 사항은 다음과 `concurrent_queue` 다른 `queue`점을 보여 줍니다.

- `concurrent_queue` 개체의 큐 및 큐 제거 작업은 동시성으로 안전합니다.

- 클래스는 `concurrent_queue` 동시성으로 안전하지 않은 이터레이터 지원을 제공합니다.

- 클래스는 `concurrent_queue` 또는 `front` `pop` 메서드를 제공하지 않습니다. 클래스는 `concurrent_queue` [try_pop](reference/concurrent-queue-class.md#try_pop) 메서드를 정의하여 이러한 메서드를 대체합니다.

- 클래스는 `concurrent_queue` 메서드를 `back` 제공하지 않습니다. 따라서 큐의 끝을 참조할 수 없습니다.

- 클래스는 `concurrent_queue` 메서드 대신 [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) `size` 메서드를 제공합니다. 이 `unsafe_size` 메서드는 동시성으로 안전하지 않습니다.

### <a name="concurrency-safe-operations"></a><a name="queue-safety"></a>동시성 안전 운영

개체에서 큐에 큐 또는 큐해제하는 `concurrent_queue` 모든 메서드는 동시성으로 안전합니다. 여기서 동시성 안전은 포인터 또는 이터레이터가 항상 유효하다는 것을 의미합니다. 요소 초기화 또는 특정 순회 순서를 보장하지 않습니다.

다음 표에서는 동시성으로 안전한 일반적인 메서드및 연산자가 보여 주며, 이 에 대한 일반적인 `concurrent_queue` 메서드와 연산자는 다음과 같습니다.

|||
|-|-|
|[빈](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

메서드는 `empty` 동시성 으로 안전하지만 동시 작업으로 인해 `empty` 메서드가 반환되기 전에 큐가 커지거나 축소될 수 있습니다.

다음 표에서는 동시성으로 안전하지 않은 일반적인 메서드 및 연산자가 보여 주어 도표입니다.

|||
|-|-|
|[명확한](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

### <a name="iterator-support"></a><a name="queue-iterators"></a>이터레이터 지원

는 `concurrent_queue` 동시성 안전하지 않은 이터레이터를 제공합니다. 이러한 이터레이터는 디버깅에만 사용하는 것이 좋습니다.

이터레이터는 `concurrent_queue` 정방향에서만 요소를 통과합니다. 다음 표에서는 각 이터레이터가 지원하는 연산자가 표시됩니다.

|연산자|Description|
|--------------|-----------------|
|`operator++`|큐의 다음 항목으로 이동합니다. 이 연산자는 사전 증분 및 사후 증분 시맨틱을 모두 제공하기 위해 오버로드됩니다.|
|`operator*`|현재 항목에 대한 참조를 검색합니다.|
|`operator->`|현재 항목에 대한 포인터를 검색합니다.|

【[맨 위](#top)】

## <a name="concurrent_unordered_map-class"></a><a name="unordered_map"></a>concurrent_unordered_map 클래스

[동시성 ::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) 클래스는 [std:unordered_map](../../standard-library/unordered-map-class.md) 클래스와 마찬가지로 [std::pair\<const Key, Ty>](../../standard-library/pair-structure.md):p 다양한 길이의 요소 시퀀스를 제어하는 연관 컨테이너 클래스입니다. 순서가 지정되지 않은 맵을 키 및 값 쌍을 추가하거나 키로 값을 조회할 수 있는 사전으로 생각하면 됩니다. 이 클래스는 공유 컨테이너에 동시에 액세스하거나, 삽입하거나, 업데이트해야 하는 여러 스레드 또는 작업이 있는 경우에 유용합니다.

다음 예제에서는 을 사용하기 `concurrent_unordered_map`위한 기본 구조를 보여 주며 있습니다. 이 예제에서는 ['a', 'i]범위에 문자 키를 삽입합니다. 작업 순서가 결정되지 않으므로 각 키의 최종 값도 결정되지 않습니다. 그러나 삽입을 병렬로 수행하는 것이 안전합니다.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

맵을 수행하고 `concurrent_unordered_map` 병렬로 작업을 줄이는 데 사용하는 예제의 경우 [병렬로 맵 수행 및 작업 줄이기 방법을](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)참조하세요.

### <a name="differences-between-concurrent_unordered_map-and-unordered_map"></a><a name="map-differences"></a>concurrent_unordered_map unordered_map 차이

클래스는 `concurrent_unordered_map` 클래스와 `unordered_map` 매우 유사합니다. 다음 사항은 다음과 `concurrent_unordered_map` 다른 `unordered_map`점을 보여 줍니다.

- 의 `erase` `bucket`및 `bucket_count` `bucket_size` 메서드는 각각 `unsafe_erase` `unsafe_bucket`" `unsafe_bucket_count`및 `unsafe_bucket_size`. `unsafe_` 명명 규칙은 이러한 메서드가 동시성으로 안전하지 않음을 나타냅니다. 동시성 안전에 대한 자세한 내용은 [동시성 안전 작업을](#map-safety)참조하십시오.

- 삽입 작업은 기존 포인터 나 이터레이터를 무효화하지 않으며 맵에 이미 있는 항목의 순서를 변경하지도 않습니다. 삽입 및 다각측량 작업이 동시에 발생할 수 있습니다.

- `concurrent_unordered_map`정방향 반복만 지원합니다.

- 삽입은 `equal_range`에서 반환되는 이터레이터를 무효화하거나 업데이트하지 않습니다. 삽입은 범위의 끝에 같지 않은 항목을 추가할 수 있습니다. 시작 이터레이터는 동일한 항목을 가리킵니다.

교착 상태를 방지하려면 메모리 `concurrent_unordered_map` 할당자, 해시 함수 또는 기타 사용자 정의 코드를 호출할 때 잠금을 보유하는 메서드가 없습니다. 또한 해시 함수가 항상 동일한 값에 동일한 키를 평가하도록 해야 합니다. 최상의 해시 함수는 해시 코드 공간에 키를 균일하게 분산시다.

### <a name="concurrency-safe-operations"></a><a name="map-safety"></a>동시성 안전 운영

클래스는 `concurrent_unordered_map` 동시성 으로 안전한 삽입 및 요소 액세스 작업을 활성화합니다. 삽입 작업은 기존 포인터 또는 이터레이터를 무효화하지 않습니다. 이터레이터 액세스 및 통과 작업도 동시성으로 안전합니다. 여기서 동시성 안전은 포인터 또는 이터레이터가 항상 유효하다는 것을 의미합니다. 요소 초기화 또는 특정 순회 순서를 보장하지 않습니다. 다음 표에서는 동시성으로 안전한 일반적으로 사용되는 `concurrent_unordered_map` 메서드 및 연산자도 보여 주실 수 있습니다.

|||||
|-|-|-|-|
|[에](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[operator&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[삽입](reference/concurrent-unordered-map-class.md#insert)|`size`|

메서드를 `count` 동시에 실행 중인 스레드에서 안전하게 호출할 수 있지만 새 값이 동시에 컨테이너에 삽입되는 경우 다른 스레드가 다른 결과를 받을 수 있습니다.

다음 표에서는 동시성으로 안전하지 않은 일반적으로 사용되는 메서드 및 연산자도 보여 주며, 이 방법은 다음과 같습니다.

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[연산자 =](reference/concurrent-unordered-map-class.md#operator_eq)

이러한 메서드 외에도 시작하는 모든 `unsafe_` 메서드도 동시성으로 안전하지 않습니다.

【[맨 위](#top)】

## <a name="concurrent_unordered_multimap-class"></a><a name="unordered_multimap"></a>concurrent_unordered_multimap 클래스

[동시성::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) 클래스는 여러 `concurrent_unordered_map` 값이 동일한 키에 매핑할 수 있다는 점을 제외하면 클래스와 매우 유사합니다. 또한 다음과 같은 `concurrent_unordered_map` 방법과 다릅니다.

- [concurrent_unordered_multimap::insert](reference/concurrent-unordered-multimap-class.md#insert) 메서드 대신 이터레이터를 `std::pair<iterator, bool>`반환합니다.

- 클래스는 `concurrent_unordered_multimap` `at` 메서드를 `operator[]` 제공하지 않습니다.

다음 예제에서는 을 사용하기 `concurrent_unordered_multimap`위한 기본 구조를 보여 주며 있습니다. 이 예제에서는 ['a', 'i]범위에 문자 키를 삽입합니다. `concurrent_unordered_multimap`키에 여러 값을 가질 수 있습니다.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

【[맨 위](#top)】

## <a name="concurrent_unordered_set-class"></a><a name="unordered_set"></a>concurrent_unordered_set 클래스

[동시성::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) 클래스는 키 `concurrent_unordered_map` 및 값 쌍 대신 값을 관리한다는 점을 제외하면 클래스와 매우 유사합니다. 클래스는 `concurrent_unordered_set` `at` 메서드를 `operator[]` 제공하지 않습니다.

다음 예제에서는 을 사용하기 `concurrent_unordered_set`위한 기본 구조를 보여 주며 있습니다. 이 예제에서는 ['a', 'i]범위에 문자 값을 삽입합니다. 삽입을 병렬로 수행하는 것이 안전합니다.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

【[맨 위](#top)】

## <a name="concurrent_unordered_multiset-class"></a><a name="unordered_multiset"></a>concurrent_unordered_multiset 클래스

[동시 ::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) 클래스는 중복 `concurrent_unordered_set` 값을 허용한다는 점을 제외하면 클래스와 매우 유사합니다. 또한 다음과 같은 `concurrent_unordered_set` 방법과 다릅니다.

- [concurrent_unordered_multiset::insert](reference/concurrent-unordered-multiset-class.md#insert) 메서드대신 이터레이터를 `std::pair<iterator, bool>`반환합니다.

- 클래스는 `concurrent_unordered_multiset` `at` 메서드를 `operator[]` 제공하지 않습니다.

다음 예제에서는 을 사용하기 `concurrent_unordered_multiset`위한 기본 구조를 보여 주며 있습니다. 이 예제에서는 ['a', 'i]범위에 문자 값을 삽입합니다. `concurrent_unordered_multiset`값을 여러 번 수행할 수 있습니다.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

【[맨 위](#top)】

## <a name="combinable-class"></a><a name="combinable"></a>조합 가능한 클래스

[동시성::결합 가능한](../../parallel/concrt/reference/combinable-class.md) 클래스는 재사용 가능한 스레드 로컬 저장소를 제공하여 세분화된 계산을 수행한 다음 이러한 계산을 최종 결과로 병합할 수 있습니다. `combinable` 개체는 환산(reduction) 변수로 간주될 수 있습니다.

이 `combinable` 클래스는 여러 스레드 또는 작업 간에 공유되는 리소스가 있는 경우에 유용합니다. 이 `combinable` 클래스는 잠금 이없는 방식으로 공유 리소스에 대한 액세스를 제공하여 공유 상태를 제거하는 데 도움이 됩니다. 따라서 이 클래스는 여러 스레드의 공유 데이터에 대한 액세스를 동기화하기 위해 뮤텍스와 같은 동기화 메커니즘을 사용하는 대신 사용할 수 있습니다.

### <a name="methods-and-features"></a><a name="combinable-features"></a>방법 및 기능

다음 표에서는 클래스의 몇 가지 `combinable` 중요한 메서드를 보여 주며 있습니다. 모든 클래스 메서드에 `combinable` 대한 자세한 내용은 [결합 가능한 클래스](../../parallel/concrt/reference/combinable-class.md)를 참조하십시오.

|메서드|Description|
|------------|-----------------|
|[로컬](reference/combinable-class.md#local)|현재 스레드 컨텍스트와 연결된 로컬 변수에 대한 참조를 검색합니다.|
|[명확한](reference/combinable-class.md#clear)|개체에서 모든 스레드 로컬 변수를 `combinable` 제거합니다.|
|[결합](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|제공된 결합 함수를 사용하여 모든 스레드 로컬 계산 집합에서 최종 값을 생성합니다.|

클래스는 `combinable` 최종 병합된 결과에서 매개 변수화되는 템플릿 클래스입니다. 기본 생성자 호출 하는 `T` 경우 기본 생성자와 복사 생성자가 있어야 합니다. `T` 템플릿 매개 변수 형식에 기본 생성자가 없는 경우 초기화 함수를 매개 변수로 사용 하는 생성자의 오버로드 된 버전을 호출 합니다.

`combinable` [결합](reference/combinable-class.md#combine) 또는 combine_each 메서드를 호출한 후 개체에 추가 데이터를 저장할 수 [있습니다.](reference/combinable-class.md#combine_each) 및 `combine` `combine_each` 메서드를 여러 번 호출할 수도 있습니다. `combinable` 개체의 로컬 값이 변경되지 않으면 `combine` `combine_each` 및 메서드가 호출될 때마다 동일한 결과를 생성합니다.

### <a name="examples"></a><a name="combinable-examples"></a>예제

`combinable` 클래스를 사용하는 방법에 대한 예제는 다음 항목을 참조하십시오.

- [방법: combinable을 사용하여 성능 개선](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [방법: combinable을 사용하여 집합 결합](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

【[맨 위](#top)】

## <a name="related-topics"></a>관련 항목

[방법: 병렬 컨테이너를 사용하여 효율성 향상](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
병렬 컨테이너를 사용하여 데이터를 병렬로 효율적으로 저장하고 액세스하는 방법을 보여 주시면 됩니다.

[방법: combinable을 사용하여 성능 개선](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
클래스를 `combinable` 사용하여 공유 상태를 제거하고 성능을 향상시키는 방법을 보여 주는 방법을 보여 주시킵니다.

[방법: combinable을 사용하여 집합 결합](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
함수를 `combine` 사용하여 스레드 로컬 데이터 집합을 병합하는 방법을 보여 주며

[PPL(병렬 패턴 라이브러리)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
동시 응용 프로그램 개발을 위한 확장성과 사용 편의성을 촉진하는 필수 프로그래밍 모델을 제공하는 PPL에 대해 설명합니다.

## <a name="reference"></a>참조

[concurrent_vector 클래스](../../parallel/concrt/reference/concurrent-vector-class.md)

[concurrent_queue 클래스](../../parallel/concrt/reference/concurrent-queue-class.md)

[concurrent_unordered_map 클래스](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[concurrent_unordered_multimap 클래스](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[concurrent_unordered_set 클래스](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[concurrent_unordered_multiset 클래스](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[combinable 클래스](../../parallel/concrt/reference/combinable-class.md)
