---
title: RemoveIUnknown 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
ms.openlocfilehash: cfcdefbb8d7cd12d2ebf99710f595fdd2fc16f76
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213618"
---
# <a name="removeiunknown-class"></a>RemoveIUnknown 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename T>
struct RemoveIUnknown;

template <typename T>
class RemoveIUnknown : public T;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
클래스입니다.

## <a name="remarks"></a>주의

는 `IUnknown`기반 형식에 해당 하는 형식을 만들지만 비가상 `QueryInterface`, `AddRef`및 `Release` 멤버 함수를 사용 합니다.

기본적으로 COM 메서드는 가상 `QueryInterface`, `AddRef`및 `Release` 메서드를 제공 합니다. 그러나 `ComPtr`는 가상 메서드의 오버 헤드가 필요 하지 않습니다. `RemoveIUnknown`는 전용, 비가상 `QueryInterface`, `AddRef`및 `Release` 메서드를 제공 하 여 오버 헤드를 제거 합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 형식 정의

|이름|설명|
|----------|-----------------|
|`ReturnType`|템플릿 매개 변수 *T* 와 동일 하지만 비가상 `IUnknown` 멤버가 있는 형식의 동의어입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`T`

`RemoveIUnknown`

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임 스페이스:** Microsoft:: WRL::D etails

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)
