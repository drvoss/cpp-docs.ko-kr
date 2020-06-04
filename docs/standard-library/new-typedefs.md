---
title: '&lt;new&gt; 형식 정의'
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 30bd84a1d69d3d8f24cd36450a18b23b92c3c2c6
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076434"
---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; 형식 정의

## <a name="hardware_constructive_interference_size"></a><a name="hardware_constructive_interference_size"></a>hardware_constructive_interference_size

```cpp
inline constexpr size_t hardware_constructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>주의

이 숫자는 동시 스레드가 임시 위치를 사용 하 여 액세스 한 두 개체가 차지 하는 연속 메모리의 최대 크기입니다. `alignof(max_align_t)`이상 이어야 합니다.

### <a name="example"></a>예제

```cpp
struct together {
    atomic<int> dog;
    int puppy;
};

struct kennel {
    // Other data members...
    alignas(sizeof(together)) together pack;
    // Other data members...
};

static_assert(sizeof(together) <= hardware_constructive_interference_size);
```

## <a name="hardware_destructive_interference_size"></a><a name="hardware_destructive_interference_size"></a>hardware_destructive_interference_size

```cpp
inline constexpr size_t hardware_destructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>주의

이 숫자는 구현에 의해 도입 된 경합으로 인해 추가 성능 저하를 방지 하기 위해 동시에 액세스 한 두 개체 사이의 최소 권장 오프셋입니다. `alignof(max_align_t)`이상 이어야 합니다.

### <a name="example"></a>예제

```cpp
struct keep_apart {
    alignas(hardware_destructive_interference_size) atomic<int> cat;
    alignas(hardware_destructive_interference_size) atomic<int> dog;
};
```

## <a name="new_handler"></a><a name="new_handler"></a>new_handler

이 형식은 새 처리기로 사용하기에 적합한 함수를 가리킵니다.

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>주의

이 형식의 처리기 함수는 추가 저장소에 대 한 요청을 충족 시킬 수 없는 경우 **operator new** 또는 `operator new[]`에 의해 호출 됩니다.

### <a name="example"></a>예제

[를 반환 값으로 사용하는 방법의 예제는 ](../standard-library/new-functions.md#set_new_handler)set_new_handler`new_handler`를 참조하세요.
