---
title: ChainInterfaces 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
- implements/Microsoft::WRL::ChainInterfaces::CastToUnknown
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
- implements/Microsoft::WRL::ChainInterfaces::IidCount
- implements/Microsoft::WRL::ChainInterfaces::Verify
helpviewer_keywords:
- Microsoft::WRL::ChainInterfaces structure
- Microsoft::WRL::ChainInterfaces::CanCastTo method
- Microsoft::WRL::ChainInterfaces::CastToUnknown method
- Microsoft::WRL::ChainInterfaces::FillArrayWithIid method
- Microsoft::WRL::ChainInterfaces::IidCount constant
- Microsoft::WRL::ChainInterfaces::Verify method
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
ms.openlocfilehash: dd1af3fb5c1079a40d8248dc71ae4972537aa856
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372658"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces 구조체

인터페이스 ID 집합에 적용할 수 있는 확인 및 초기화 함수를 지정합니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename I0,
    typename I1,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct ChainInterfaces : I0;

template <
    typename DerivedType,
    typename BaseType,
    bool hasImplements,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8,
    typename I9
>
struct ChainInterfaces<
    MixIn<
        DerivedType,
        BaseType,
        hasImplements
    >, I1, I2, I3, I4, I5, I6, I7, I8, I9
>;
```

### <a name="parameters"></a>매개 변수

*I0*<br/>
(필수) 인터페이스 ID 0.

*I1*<br/>
(필수) 인터페이스 ID 1.

*I2*<br/>
(선택 사항) 인터페이스 ID 2.

*I3*<br/>
(선택 사항) 인터페이스 ID 3.

*I4*<br/>
(선택 사항) 인터페이스 ID 4.

*I5*<br/>
(선택 사항) 인터페이스 ID 5.

*I6*<br/>
(선택 사항) 인터페이스 ID 6.

*I7*<br/>
(선택 사항) 인터페이스 ID 7.

*I8*<br/>
(선택 사항) 인터페이스 ID 8.

*I9*<br/>
(선택 사항) 인터페이스 ID 9.

*파생 유형*<br/>
파생 된 형식입니다.

*BaseType*<br/>
파생 형식의 기본 형식입니다.

*hasImplements*<br/>
**true인**경우 구현 치수에서 파생되지 않는 클래스와 함께 [MixIn](mixin-structure.md) 구조를 사용할 수 [없다는](implements-structure.md) 부울 값입니다.

## <a name="members"></a>멤버

### <a name="protected-methods"></a>Protected 메서드

속성                                                   | Description
------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[체인 인터페이스 ::캔 캐스트토](#cancastto)               | 지정된 인터페이스 ID를 `ChainInterface` 템플릿 매개 변수에 의해 정의된 각 특수화에 캐스팅할 수 있는지 여부를 나타냅니다.
[체인 인터페이스::캐스팅알 수 없음](#casttounknown)       | *I0* 템플릿 매개 변수에 의해 정의된 형식의 인터페이스 `IUnknown`포인터를 에 대한 포인터로 캐스팅합니다.
[체인 인터페이스::채우기배열WithIid](#fillarraywithiid) | *I0* 템플릿 매개 변수에 의해 정의된 인터페이스 ID를 지정된 인터페이스 ID 배열의 지정된 위치에 지정한 위치에 저장합니다.
[체인 인터페이스::확인](#verify)                     | 템플릿 매개 변수 *I0에서* *I9을* 통해 정의된 `IUnknown` 각 인터페이스가 및/또는 `IInspectable`에서 상속되고 *I0이* *I1에서* *I9을*통해 상속되는지 확인합니다.

### <a name="protected-constants"></a>보호상수

속성                                   | Description
-------------------------------------- | -----------------------------------------------------------------------------------------------------------------
[체인 인터페이스::이드카운트](#iidcount) | 템플릿 매개 변수 *I0에서* *I9까지*지정된 인터페이스에 포함된 인터페이스 의 총 수입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`I0`

`ChainInterfaces`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="chaininterfacescancastto"></a><a name="cancastto"></a>체인 인터페이스 ::캔 캐스트토

지정된 인터페이스 ID를 기본이 아닌 템플릿 매개 변수에 의해 정의된 각 특수화에 캐스팅할 수 있는지 여부를 나타냅니다.

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*ppv*<br/>
성공적으로 캐스팅된 마지막 인터페이스 ID에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

모든 캐스트 작업이 성공한 경우 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="chaininterfacescasttounknown"></a><a name="casttounknown"></a>체인 인터페이스::캐스팅알 수 없음

*I0* 템플릿 매개 변수에 의해 정의된 형식의 인터페이스 `IUnknown`포인터를 에 대한 포인터로 캐스팅합니다.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Return Value

`IUnknown`에 대한 포인터입니다.

## <a name="chaininterfacesfillarraywithiid"></a><a name="fillarraywithiid"></a>체인 인터페이스::채우기배열WithIid

*I0* 템플릿 매개 변수에 의해 정의된 인터페이스 ID를 지정된 인터페이스 ID 배열의 지정된 위치에 지정한 위치에 저장합니다.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>매개 변수

*index*<br/>
iids 배열에 인덱스 값을 *포인터합니다.*

*아이드 (이드)*<br/>
인터페이스 아이디의 배열입니다.

## <a name="chaininterfacesiidcount"></a><a name="iidcount"></a>체인 인터페이스::이드카운트

템플릿 매개 변수 *I0에서* *I9까지*지정된 인터페이스에 포함된 인터페이스 의 총 수입니다.

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

### <a name="return-value"></a>Return Value

인터페이스 ID의 총 개수입니다.

### <a name="remarks"></a>설명

템플릿 매개 변수 *I0* 및 *I1이* 필요하며 *I2부터* *I9까지의* 매개 변수는 선택 사항입니다. 각 인터페이스의 IID 수는 일반적으로 1입니다.

## <a name="chaininterfacesverify"></a><a name="verify"></a>체인 인터페이스::확인

템플릿 매개 변수 *I0에서* *I9을* 통해 정의된 `IUnknown` 각 인터페이스가 및/또는 `IInspectable`에서 상속되고 *I0이* *I1에서* *I9을*통해 상속되는지 확인합니다.

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

### <a name="remarks"></a>설명

확인 작업이 실패하는 경우 `static_assert`에서 실패를 설명하는 오류 메시지를 내보냅니다.

템플릿 매개 변수 *I0* 및 *I1이* 필요하며 *I2부터* *I9까지의* 매개 변수는 선택 사항입니다.
