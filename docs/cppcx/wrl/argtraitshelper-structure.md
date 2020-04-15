---
title: ArgTraitsHelper 구조체
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraitsHelper structure
- Microsoft::WRL::Details::ArgTraitsHelper::args constant
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
ms.openlocfilehash: 4acbd9fa660f29bbaf209282ff0e90f43621574d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360774"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>매개 변수

*TDelegateInterface*<br/>
대리자 인터페이스입니다.

## <a name="remarks"></a>설명

대리자 인수의 일반적인 특성을 정의하는 데 도움이 됩니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

속성         | Description
------------ | ------------------------------------------------------
`methodType` | `decltype(&TDelegateInterface::Invoke)`의 동의어입니다.
`Traits`     | `ArgTraits<methodType>`의 동의어입니다.

### <a name="public-constants"></a>공용 상수

속성                           | Description
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[아르그트레이어헬어::아르그](#args) | [ArgTraits::args](#args) 대리자 인터페이스의 `Invoke` 메서드에 매개 변수 의 수를 유지 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ArgTraitsHelper`

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="argtraitshelperargs"></a><a name="args"></a>아르그트레이어헬어::아르그

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>설명

대리자 인터페이스의 `ArgTraitsHelper::args` `Invoke` 메서드에서 매개 변수 수를 유지하는 데 도움이 됩니다.
