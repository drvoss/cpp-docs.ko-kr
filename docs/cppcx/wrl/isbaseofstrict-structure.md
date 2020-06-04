---
title: IsBaseOfStrict 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
ms.openlocfilehash: 71db5a1b52a7d7d5471c15591fb34d954b465d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371361"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>매개 변수

*기본*<br/>
기본 형식입니다.

*파생*<br/>
파생 된 형식입니다.

## <a name="remarks"></a>설명

형식 하나가 다른 형식의 기본 형식인지 테스트합니다.

첫 번째 템플릿은 형식이 **true** 또는 **false를**생성할 수 있는 기본 형식에서 파생되는지 여부를 테스트합니다. 두 번째 템플릿은 형식이 자체에서 파생되는지 여부를 테스트하며, 항상 **false를**생성합니다.

## <a name="members"></a>멤버

### <a name="public-constants"></a>공용 상수

속성                            | Description
------------------------------- | --------------------------------------------------
[이스베이스오브스엄::값](#value) | 한 형식이 다른 형식의 기본인지 여부를 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IsBaseOfStrict`

## <a name="requirements"></a>요구 사항

**헤더:** 내부.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="isbaseofstrictvalue"></a><a name="value"></a>이스베이스오브스엄::값

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>설명

한 형식이 다른 형식의 기본인지 여부를 나타냅니다.

`value`true **true** `Base` 형식이 형식의 `Derived`기본 클래스인 경우 true이며 그렇지 않으면 **false입니다.**
