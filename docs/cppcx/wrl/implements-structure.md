---
title: Implements 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
- implements/Microsoft::WRL::Implements::CanCastTo
- implements/Microsoft::WRL::Implements::CastToUnknown
- implements/Microsoft::WRL::Implements::FillArrayWithIid
- implements/Microsoft::WRL::Implements::IidCount
helpviewer_keywords:
- Microsoft::WRL::Implements structure
- Microsoft::WRL::Implements::CanCastTo method
- Microsoft::WRL::Implements::CastToUnknown method
- Microsoft::WRL::Implements::FillArrayWithIid method
- Microsoft::WRL::Implements::IidCount method
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
ms.openlocfilehash: 223f37d7cabbd0b8cd238582773c05d7b9eaabf6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371403"
---
# <a name="implements-structure"></a>Implements 구조체

`QueryInterface` 지정된 `GetIid` 인터페이스에 대한 구현입니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename I0,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct __declspec(novtable) Implements :
    Details::ImplementsHelper<
        RuntimeClassFlags<WinRt>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8, I9
        >::TypeT
    >,
    Details::ImplementsBase;

template <
    int flags,
    typename I0,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8
>
struct __declspec(novtable) Implements<
        RuntimeClassFlags<flags>,
        I0, I1, I2, I3, I4, I5, I6, I7, I8> :
    Details::ImplementsHelper<
        RuntimeClassFlags<flags>,
        typename Details::InterfaceListHelper<
            I0, I1, I2, I3, I4, I5, I6, I7, I8
        >::TypeT
    >,
    Details::ImplementsBase;
```

### <a name="parameters"></a>매개 변수

*I0*<br/>
0번째 인터페이스 ID입니다. 필수 사항입니다.

*I1*<br/>
첫 번째 인터페이스 ID입니다. (선택 사항)

*I2*<br/>
두 번째 인터페이스 ID입니다. (선택 사항)

*I3*<br/>
세 번째 인터페이스 ID입니다. (선택 사항)

*I4*<br/>
네 번째 인터페이스 ID입니다. (선택 사항)

*I5*<br/>
다섯 번째 인터페이스 ID입니다. (선택 사항)

*I6*<br/>
여섯 번째 인터페이스 ID입니다. (선택 사항)

*I7*<br/>
일곱 번째 인터페이스 ID입니다. (선택 사항)

*I8*<br/>
여덟 번째 인터페이스 ID입니다. (선택 사항)

*I9*<br/>
아홉 번째 인터페이스 ID입니다. (선택 사항)

*플래그*<br/>
클래스에 대한 구성 플래그입니다. 런타임클래스플래그 [구조에](runtimeclassflags-structure.md) 지정된 하나 이상의 [런타임클래스유형](runtimeclasstype-enumeration.md) 열거형입니다.

## <a name="remarks"></a>설명

지정된 인터페이스 목록에서 파생되고 `QueryInterface` `GetIid`에 대한 도우미 템플릿을 구현합니다.

I9 인터페이스 *I9* 매개 변수를 통해 `IUnknown`각 `IInspectable` *I0은* 에서 파생되어야 합니다. [ChainInterfaces](chaininterfaces-structure.md) *flags* 매개 변수는 에 대한 `IUnknown` `IInspectable`지원이 생성되는지 또는 에 대해 생성되는지 여부를 결정합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

| 속성        | Description                               |
| ----------- | ----------------------------------------- |
| `ClassFlags`| `RuntimeClassFlags<WinRt>`의 동의어입니다. |

### <a name="protected-methods"></a>Protected 메서드

| 속성                                              | Description                                                                                                   |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [구현::CanCastTo](#cancastto)               | 지정된 인터페이스에 대한 포인터를 가져옵니다.                                                                    |
| [구현::캐스트알 수 없음](#casttounknown)       | 기본 `IUnknown` 인터페이스에 대한 포인터를 가져옵니다.                                                        |
| [구현::채우기배열WithIid](#fillarraywithiid) | 현재 0th 템플릿 매개 변수에 의해 지정된 인터페이스 ID를 지정된 배열 요소에 삽입합니다. |

### <a name="protected-constants"></a>보호상수

| 속성                              | Description                                    |
| --------------------------------- | ---------------------------------------------- |
| [구현::IdCount](#iidcount) | 구현된 인터페이스 아이디 수를 보유합니다. |

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`I0`

`ChainInterfaces`

`I0`

`ImplementsBase`

`ImplementsHelper`

`Implements`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="implementscancastto"></a><a name="cancastto"></a>구현::CanCastTo

지정된 인터페이스에 대한 포인터를 가져옵니다.

```cpp
__forceinline HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID에 대한 참조입니다.

*ppv*<br/>
성공하면 *riid*.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 E_NOINTERFACE 같은 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

쿼리인터페이스 작업을 수행하는 내부 도우미 함수입니다.

## <a name="implementscasttounknown"></a><a name="casttounknown"></a>구현::캐스트알 수 없음

기본 `IUnknown` 인터페이스에 대한 포인터를 가져옵니다.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Return Value

이 작업은 항상 성공하고 `IUnknown` 포인터를 반환합니다.

### <a name="remarks"></a>설명

내부 도우미 기능입니다.

## <a name="implementsfillarraywithiid"></a><a name="fillarraywithiid"></a>구현::채우기배열WithIid

현재 0th 템플릿 매개 변수에 의해 지정된 인터페이스 ID를 지정된 배열 요소에 삽입합니다.

```cpp
__forceinline static void FillArrayWithIid(
   unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>매개 변수

*index*<br/>
이 작업에 대한 시작 배열 요소를 나타내는 0기반 인덱스입니다. 이 작업이 완료되면 *인덱스는* 1씩 증가합니다.

*아이드 (이드)*<br/>
유형 IID의 배열입니다.

### <a name="remarks"></a>설명

내부 도우미 기능입니다.

## <a name="implementsiidcount"></a><a name="iidcount"></a>구현::IdCount

구현된 인터페이스 아이디 수를 보유합니다.

```cpp
static const unsigned long IidCount;
```
