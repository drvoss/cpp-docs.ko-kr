---
title: ArgTraits 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
- event/Microsoft::WRL::Details::ArgTraits::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraits structure
- Microsoft::WRL::Details::ArgTraits::args constant
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
ms.openlocfilehash: 16c44d861ebbbc98fa1bffb62a00d1989c0c803c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377166"
---
# <a name="argtraits-structure"></a>ArgTraits 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<typename TMemberFunction>
struct ArgTraits;

template<typename TDelegateInterface>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;

template<typename TDelegateInterface, typename TArg1>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;

template<typename TDelegateInterface, typename TArg1, typename TArg2>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;
```

### <a name="parameters"></a>매개 변수

*T멤버기능*<br/>
메서드 시그니처와 일치할 수 없는 ArgTraits 구조의 형식 이름 매개 변수입니다. `Invoke`

*TDelegateInterface*<br/>
대리자 인터페이스입니다.

*TArg1*<br/>
메서드의 첫 번째 인수의 형식입니다. `Invoke`

*TArg2*<br/>
메서드의 두 번째 인수의 형식입니다. `Invoke`

*타르그3*<br/>
메서드의 세 번째 인수의 형식입니다. `Invoke`

*타르그 4*<br/>
메서드의 네 번째 인수의 형식입니다. `Invoke`

*타르그 5*<br/>
메서드의 다섯 번째 인수의 형식입니다. `Invoke`

*타르그 6*<br/>
메서드의 여섯 번째 인수의 형식입니다. `Invoke`

*타르그7*<br/>
메서드의 일곱 번째 인수의 형식입니다. `Invoke`

*타르그8*<br/>
메서드의 여덟 번째 인수의 형식입니다. `Invoke`

*타르그9*<br/>
메서드의 아홉 번째 인수의 형식입니다. `Invoke`

## <a name="remarks"></a>설명

구조는 `ArgTraits` 지정된 대리자 인터페이스와 지정된 수의 매개 변수가 있는 익명 멤버 함수를 선언합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성       | Description
---------- | ----------------------
`Arg1Type` | TArg1의 형식입니다.
`Arg2Type` | TArg2의 형식입니다.
`Arg3Type` | TArg3의 형식입니다.
`Arg4Type` | TArg4의 형식입니다.
`Arg5Type` | TArg5의 형식입니다.
`Arg6Type` | TArg6의 형식입니다.
`Arg7Type` | TArg7의 형식입니다.
`Arg8Type` | TArg8의 형식입니다.
`Arg9Type` | TArg9의 형식입니다.

### <a name="public-constants"></a>공용 상수

속성                     | Description
------------------------ | ---------------------------------------------------------------------------------------
[아르그해협::아르그](#args) | 대리자 인터페이스의 `Invoke` 메서드에서 매개 변수 수를 유지합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ArgTraits`

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="argtraitsargs"></a><a name="args"></a>아르그해협::아르그

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
static const int args = -1;
```

### <a name="remarks"></a>설명

대리자 인터페이스의 `Invoke` 메서드에서 매개 변수 수를 유지합니다. -1이면 `args` 메서드 시그니처와 `Invoke` 일치하지 않을 수 있습니다.
