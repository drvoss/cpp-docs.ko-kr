---
title: ImplementsHelper 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
- implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
- implements/Microsoft::WRL::Details::ImplementsHelper::IidCount
helpviewer_keywords:
- Microsoft::WRL::Details::ImplementsHelper structure
- Microsoft::WRL::Details::ImplementsHelper::CanCastTo method
- Microsoft::WRL::Details::ImplementsHelper::CastToUnknown method
- Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid method
- Microsoft::WRL::Details::ImplementsHelper::IidCount constant
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
ms.openlocfilehash: e33842f574df5617fb40c5b3f6bb8324d5ba7c1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371392"
---
# <a name="implementshelper-structure"></a>ImplementsHelper 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename RuntimeClassFlagsT, typename ILst, bool IsDelegateToClass>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>매개 변수

*런타임클래스플래그T*<br/>
하나 이상의 [RuntimeClassType](runtimeclasstype-enumeration.md) 열거형을 지정하는 플래그 필드입니다.

*일스트 (일스트)*<br/>
인터페이스 아이디 목록입니다.

*IsDelegateToClass*<br/>
의 `Implements` 현재 인스턴스가 *ILst의*첫 번째 인터페이스 ID의 기본 클래스인 경우 **true를** 지정합니다. 그렇지 **않으면, 거짓**.

## <a name="remarks"></a>설명

구현 구조를 구현하는 데 도움이 [됩니다.](implements-structure.md)

이 템플릿은 인터페이스 목록을 통과하여 기본 클래스로 추가하고 을 활성화하는 `QueryInterface`데 필요한 정보로 추가합니다.

## <a name="members"></a>멤버

### <a name="protected-methods"></a>Protected 메서드

속성                                                    | Description
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[구현도우미::캔캐스트토](#cancastto)               | 지정된 인터페이스 ID에 대한 포인터를 가져옵니다.
[구현도우미::캐스트알 수 없음](#casttounknown)       | 현재 `Implements` 구조에 대한 `IUnknown` 기본 인터페이스에 대한 포인터를 가져옵니다.
[구현도우미::필어레이와이드](#fillarraywithiid) | 현재 0th 템플릿 매개 변수에 의해 지정된 인터페이스 ID를 지정된 배열 요소에 삽입합니다.
[구현도우미::IdCount](#iidcount)                 | 현재 `Implements` 개체에서 구현된 인터페이스 아이디 수를 보유합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ImplementsHelper`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="implementshelpercancastto"></a><a name="cancastto"></a>구현도우미::캔캐스트토

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);

HRESULT CanCastTo(
   _In_ const IID &iid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID에 대한 참조입니다.

*ppv*<br/>
이 작업이 성공하면 riid 또는 *iid로* 지정된 인터페이스에 대한 *포인터입니다.*

*Iid*<br/>
인터페이스 ID에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

지정된 인터페이스 ID에 대한 포인터를 가져옵니다.

## <a name="implementshelpercasttounknown"></a><a name="casttounknown"></a>구현도우미::캐스트알 수 없음

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Return Value

기본 `IUnknown` 인터페이스에 대한 포인터입니다.

### <a name="remarks"></a>설명

현재 `Implements` 구조에 대한 `IUnknown` 기본 인터페이스에 대한 포인터를 가져옵니다.

## <a name="implementshelperfillarraywithiid"></a><a name="fillarraywithiid"></a>구현도우미::필어레이와이드

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>매개 변수

*index*<br/>
이 작업에 대한 시작 배열 요소를 나타내는 0기반 인덱스입니다. 이 작업이 완료되면 *인덱스는* 1씩 증가합니다.

*아이드 (이드)*<br/>
형식 IID의 배열입니다.

### <a name="remarks"></a>설명

현재 0th 템플릿 매개 변수에 의해 지정된 인터페이스 ID를 지정된 배열 요소에 삽입합니다.

## <a name="implementshelperiidcount"></a><a name="iidcount"></a>구현도우미::IdCount

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>설명

현재 `Implements` 개체에서 구현된 인터페이스 아이디 수를 보유합니다.
