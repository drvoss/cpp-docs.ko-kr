---
title: Concurrency 네임스페이스 열거형(AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
ms.openlocfilehash: 2467db27ad36dfcda31dfb5bb45067ada5470d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376327"
---
# <a name="concurrency-namespace-enums-amp"></a>Concurrency 네임스페이스 열거형(AMP)

|||
|-|-|
|[access_type 열거형](#access_type)|[queuing_mode 열거](#queuing_mode)|

## <a name="access_type-enumeration"></a><a name="access_type"></a>access_type 열거

데이터에 대한 다양한 유형의 액세스를 나타내는 데 사용되는 열거 유형입니다.

```cpp
enum access_type;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`access_type_auto`|가속기에 가장 `access_type` 적합한 것을 자동으로 선택합니다.|
|`access_type_none`|전용. 할당은 CPU가 아닌 가속기에서만 액세스할 수 있습니다.|
|`access_type_read`|공유. 할당은 가속기에서 액세스할 수 있으며 CPU에서 읽을 수 있습니다.|
|`access_type_read_write`|공유. 할당은 가속기에서 액세스할 수 있으며 CPU에서 쓰기 가 가능합니다.|
|`access_type_write`|공유. 할당은 가속기에서 액세스할 수 있으며 CPU에서 읽을 수 있고 쓰기가 가능합니다.|

## <a name="queuing_mode-enumeration"></a><a name="queuing_mode"></a>queuing_mode 열거

가속기에서 지원되는 큐 모드는 지정합니다.

```cpp
enum queuing_mode;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`queuing_mode_immediate`|[parallel_for_each 함수(C++AMP)와](concurrency-namespace-functions-amp.md#parallel_for_each)같은 모든 명령이 호출자에게 반환되는 즉시 해당 가속기 장치로 전송되도록 지정하는 큐 모드입니다.|
|`queuing_mode_automatic`|[accelerator_view](accelerator-view-class.md) 개체에 해당하는 명령 큐에서 큐에 대기할 명령을 지정하는 큐 모드입니다. [accelerator_view 명령:::flush가](accelerator-view-class.md#flush) 호출될 때 명령이 장치에 전송됩니다.|

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
