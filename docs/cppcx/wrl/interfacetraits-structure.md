---
title: InterfaceTraits 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
- implements/Microsoft::WRL::Details::InterfaceTraits::IidCount
- implements/Microsoft::WRL::Details::InterfaceTraits::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::InterfaceTraits structure
- Microsoft::WRL::Details::InterfaceTraits::CanCastTo method
- Microsoft::WRL::Details::InterfaceTraits::CastToBase method
- Microsoft::WRL::Details::InterfaceTraits::CastToUnknown method
- Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid method
- Microsoft::WRL::Details::InterfaceTraits::IidCount constant
- Microsoft::WRL::Details::InterfaceTraits::Verify method
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
ms.openlocfilehash: 17f743a38af3ddc600a55e38905d19868d076a22
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371365"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<typename I0>
struct __declspec(novtable) InterfaceTraits;

template<typename CloakedType>
struct __declspec(novtable) InterfaceTraits<
    CloakedIid<CloakedType>
>;

template<>
struct __declspec(novtable) InterfaceTraits<Nil>;
```

### <a name="parameters"></a>매개 변수

*I0*<br/>
인터페이스의 이름입니다.

*은폐 유형*<br/>
`RuntimeClass` `Implements` 및 `ChainInterfaces`에 대 한 지원 되는 인터페이스 아이 디 들 목록에 없는 인터페이스입니다.

## <a name="remarks"></a>설명

인터페이스의 일반적인 특성을 구현합니다.

두 번째 템플릿은 은폐된 인터페이스에 대한 전문화입니다. 세 번째 템플릿은 Nil 매개 변수에 대한 전문화입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a><a name="public-typedefs"></a>공용 유형 defs

속성   | Description
------ | ------------------------------------------
`Base` | *I0* 템플릿 매개 변수의 동의어입니다.

### <a name="public-methods"></a>Public 메서드

속성                                                   | Description
------------------------------------------------------ | ----------------------------------------------------------------------------------------
[인터페이스 특성 ::캔 캐스트토](#cancastto)               | 지정된 포인터를 `Base`에 대한 포인터에 캐스팅할 수 있는지 여부를 나타냅니다.
[인터페이스특, 인터페이스: 캐스팅토베이스](#casttobase)             | 지정된 포인터를 에 대한 `Base`포인터로 캐스팅합니다.
[인터페이스특성::캐스팅알 수 없음](#casttounknown)       | 지정된 포인터를 에 대한 `IUnknown`포인터로 캐스팅합니다.
[인터페이스특성::필어레이와이드](#fillarraywithiid) | 인덱스 인수에서 지정한 배열 요소에 인터페이스 `Base` ID를 할당합니다.
[인터페이스특성::확인](#verify)                     | 제대로 파생된 것을 `Base` 확인합니다.

### <a name="public-constants"></a>공용 상수

속성                                   | Description
-------------------------------------- | ---------------------------------------------------------------------------------------
[인터페이스특성::이드카운트](#iidcount) | 현재 `InterfaceTraits` 개체와 연결된 인터페이스 아이디 수를 보유합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`InterfaceTraits`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="interfacetraitscancastto"></a><a name="cancastto"></a>인터페이스 특성 ::캔 캐스트토

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>매개 변수

*Ptr*<br/>
형식에 대한 포인터의 이름입니다.

*riid*<br/>
의 `Base`인터페이스 ID입니다.

*ppv*<br/>
이 작업이 성공하면 *ppv는* 에 의해 `Base`지정된 인터페이스를 가리킵니다. 그렇지 않으면 *ppv가* `nullptr`로 설정됩니다.

### <a name="return-value"></a>Return Value

이 작업이 성공하고 *pTR이* 포인터에 `Base`캐스팅된 경우 **true입니다.** 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

지정된 포인터를 `Base`에 대한 포인터에 캐스팅할 수 있는지 여부를 나타냅니다.

자세한 `Base`내용은 [공용 Typedefs](#public-typedefs) 섹션을 참조하십시오.

## <a name="interfacetraitscasttobase"></a><a name="casttobase"></a>인터페이스특, 인터페이스: 캐스팅토베이스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
매개 변수 *ptr의*유형 .

*Ptr*<br/>
*T*형에 대한 포인터 .

### <a name="return-value"></a>Return Value

`Base`에 대한 포인터입니다.

### <a name="remarks"></a>설명

지정된 포인터를 에 대한 `Base`포인터로 캐스팅합니다.

자세한 `Base`내용은 [공용 Typedefs](#public-typedefs) 섹션을 참조하십시오.

## <a name="interfacetraitscasttounknown"></a><a name="casttounknown"></a>인터페이스특성::캐스팅알 수 없음

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
매개 변수 *ptr의*유형 .

*Ptr*<br/>
*T를*입력하는 포인터 .

### <a name="return-value"></a>Return Value

파생되는 `Base` IUnknown에 대한 포인터입니다.

### <a name="remarks"></a>설명

지정된 포인터를 에 대한 `IUnknown`포인터로 캐스팅합니다.

자세한 `Base`내용은 [공용 Typedefs](#public-typedefs) 섹션을 참조하십시오.

## <a name="interfacetraitsfillarraywithiid"></a><a name="fillarraywithiid"></a>인터페이스특성::필어레이와이드

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>매개 변수

*index*<br/>
0기반 인덱스 값을 포함하는 필드에 대한 포인터입니다.

*아이드 (이드)*<br/>
인터페이스 아이디의 배열입니다.

### <a name="remarks"></a>설명

인덱스 인수에서 지정한 배열 요소에 인터페이스 `Base` ID를 할당합니다.

이 API의 이름과 는 달리 하나의 배열 요소만 수정됩니다. 전체 배열이 아닙니다.

자세한 `Base`내용은 [공용 Typedefs](#public-typedefs) 섹션을 참조하십시오.

## <a name="interfacetraitsiidcount"></a><a name="iidcount"></a>인터페이스특성::이드카운트

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
static const unsigned long IidCount = 1;
```

### <a name="remarks"></a>설명

현재 `InterfaceTraits` 개체와 연결된 인터페이스 아이디 수를 보유합니다.

## <a name="interfacetraitsverify"></a><a name="verify"></a>인터페이스특성::확인

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
__forceinline static void Verify();
```

### <a name="remarks"></a>설명

제대로 파생된 것을 `Base` 확인합니다.

자세한 `Base`내용은 [공용 Typedefs](#public-typedefs) 섹션을 참조하십시오.
