---
title: DontUseNewUseMake 클래스
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
helpviewer_keywords:
- Microsoft::WRL::Details::DontUseNewUseMake class
- Microsoft::WRL::Details::DontUseNewUseMake::operator new operator
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
ms.openlocfilehash: ae67373b4f2f2d4a199b939b06e6f526f1365446
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371547"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>설명

에서 `new` 연산자 `RuntimeClass`사용을 방지합니다. 따라서 [대신 Make 함수를](make-function.md) 사용해야 합니다.

## <a name="members"></a>멤버

### <a name="public-operators"></a>Public 연산자

속성                                             | Description
------------------------------------------------ | ---------------------------------------------------------------------------
[돈트유스뉴유메이크::연산자 새](#operator-new) | 연산자 `new` 에 오버로드되고 `RuntimeClass`에서 사용되지 않도록 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`DontUseNewUseMake`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="dontusenewusemakeoperator-new"></a><a name="operator-new"></a>돈트유스뉴유메이크::연산자 새

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>매개 변수

*__unnamed0*<br/>
할당할 메모리 바이트 수를 지정하는 명명되지 않은 매개 변수입니다.

*배치*<br/>
할당할 형식입니다.

### <a name="return-value"></a>Return Value

연산자 `new`에 오버로드하는 경우 추가 인수를 전달하는 방법을 제공합니다.

### <a name="remarks"></a>설명

연산자 `new` 에 오버로드되고 `RuntimeClass`에서 사용되지 않도록 합니다.
