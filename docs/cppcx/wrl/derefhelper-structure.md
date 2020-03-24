---
title: DerefHelper 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 43453d3162de697fa1cfcf0581953c91bbe3934f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214047"
---
# <a name="derefhelper-structure"></a>DerefHelper 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename T>
struct DerefHelper;

template <typename T>
struct DerefHelper<T*>;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
템플릿 매개 변수입니다.

## <a name="remarks"></a>주의

`T*` template 매개 변수에 대 한 역참조 된 포인터를 나타냅니다.

**DerefHelper** 는 `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`와 같은 식에 사용 됩니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 형식 정의

|이름|설명|
|----------|-----------------|
|`DerefType`|역참조 된 템플릿 매개 변수 `T*`의 식별자입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`DerefHelper`

## <a name="requirements"></a>요구 사항

**헤더:** async. h

**네임 스페이스:** Microsoft:: WRL::D etails

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)
