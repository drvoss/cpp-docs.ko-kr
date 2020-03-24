---
title: Microsoft::WRL::Wrappers 네임스페이스
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: ece26b3f9928d44a593de830cf8a25c57e4c2d89
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213748"
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers 네임스페이스

개체, 문자열 및 핸들의 수명 관리를 간소화하는 RAII(Resource Acquisition Is Initialization) 래퍼 유형을 정의합니다.

## <a name="syntax"></a>구문

```cpp
namespace Microsoft::WRL::Wrappers;
```

## <a name="members"></a>멤버

### <a name="typedefs"></a>Typedefs

|이름|설명|
|----------|-----------------|
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|

### <a name="classes"></a>클래스

|이름|설명|
|----------|-----------------|
|[CriticalSection 클래스](criticalsection-class.md)|임계 영역 개체를 나타냅니다.|
|[이벤트 클래스(WRL)](event-class-wrl.md)|이벤트를 나타냅니다.|
|[HandleT 클래스](handlet-class.md)|개체에 대한 핸들을 나타냅니다.|
|[HString 클래스](hstring-class.md)|HSTRING 핸들 조작을 지원 합니다.|
|[HStringReference 클래스](hstringreference-class.md)|기존 문자열에서 만들어진 HSTRING을 나타냅니다.|
|[Mutex 클래스](mutex-class.md)|공유 리소스를 단독으로 제어하는 동기화 개체를 나타냅니다.|
|[RoInitializeWrapper 클래스](roinitializewrapper-class.md)|Windows 런타임를 초기화 합니다.|
|[Semaphore 클래스](semaphore-class.md)|제한된 사용자 수를 지원할 수 있는 공유 리소스를 제어하는 동기화 개체를 나타냅니다.|
|[SRWLock 클래스](srwlock-class.md)|슬림 판독기/작성기 잠금을 나타냅니다.|

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임 스페이스:** Microsoft:: WRL:: 래퍼

## <a name="see-also"></a>참고 항목

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)
