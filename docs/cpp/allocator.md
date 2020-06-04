---
title: 할당자
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: 39708e8cfff7f61c3a3f763f87e1a3da36f0d4b1
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077250"
---
# <a name="allocator"></a>할당자

**Microsoft 전용**

**할당자** 선언 지정자를 사용자 지정 메모리 할당 함수에 적용 하 여 ETW(WINDOWS용 이벤트 추적) (ETW)를 통해 할당을 표시할 수 있습니다.

## <a name="syntax"></a>구문

```
   __declspec(allocator)
```

## <a name="remarks"></a>주의

Visual Studio의 네이티브 메모리 프로파일러는 런타임 중 내보낸 할당 ETW 이벤트 데이터를 수집 하는 방식으로 작동 합니다. CRT 및 Windows SDK의 할당자가 해당 할당 데이터를 캡처할 수 있도록 원본 수준에서 주석이 추가되었습니다. 사용자 고유의 할당자를 작성 하는 경우 myMalloc에 대 한 다음 예제 처럼 새로 할당 된 힙 메모리에 대 한 포인터를 반환 하는 모든 함수를 `__declspec(allocator)`으로 데코레이팅 할 수 있습니다.

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

자세한 내용은 [Visual Studio의 메모리 사용 측정](/visualstudio/profiling/memory-usage) 및 [사용자 지정 네이티브 ETW 힙 이벤트](/visualstudio/profiling/custom-native-etw-heap-events)를 참조 하세요.

**Microsoft 전용 종료**
