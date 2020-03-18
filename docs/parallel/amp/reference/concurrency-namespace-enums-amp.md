---
title: Concurrency 네임스페이스 열거형(AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
ms.openlocfilehash: a4feb2f98fc288fa79c0f9d81e4ed882027eddf8
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424976"
---
# <a name="concurrency-namespace-enums-amp"></a>Concurrency 네임스페이스 열거형(AMP)

|||
|-|-|
|[access_type 열거형](#access_type)|[queuing_mode 열거형](#queuing_mode)|

## <a name="access_type"></a>access_type 열거형

데이터에 대 한 다양 한 형식의 액세스를 나타내는 데 사용 되는 열거형 형식입니다.

```cpp
enum access_type;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`access_type_auto`|액셀러레이터 키에 대 한 가장 적합 한 `access_type`를 자동으로 선택 합니다.|
|`access_type_none`|Dip. 할당은 CPU가 아닌 가속기 에서만 액세스할 수 있습니다.|
|`access_type_read`|공유할. 할당은 가속기에서 액세스할 수 있으며 CPU에서 읽을 수 있습니다.|
|`access_type_read_write`|공유할. 할당은 가속기에서 액세스할 수 있으며 CPU에서 쓸 수 있습니다.|
|`access_type_write`|공유할. 이 할당은 가속기에서 액세스할 수 있으며 CPU에서 읽고 쓸 수 있습니다.|

## <a name="queuing_mode"></a>queuing_mode 열거형

가속기에서 지원 되는 큐 모드를 지정 합니다.

```cpp
enum queuing_mode;
```

### <a name="values"></a>값

|속성|Description|
|----------|-----------------|
|`queuing_mode_immediate`|[Parallel_for_each 함수 (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)와 같은 모든 명령이 호출자에 게 반환 되는 즉시 해당 액셀러레이터 장치로 전송 되도록 지정 하는 큐 모드입니다.|
|`queuing_mode_automatic`|명령이 [accelerator_view](accelerator-view-class.md) 개체에 해당 하는 명령 큐에 대기 하도록 지정 하는 큐 모드입니다. [Accelerator_view:: flush](accelerator-view-class.md#flush) 가 호출 되 면 장치에 명령이 전송 됩니다.|

## <a name="see-also"></a>참고 항목

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
