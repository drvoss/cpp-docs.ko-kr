---
title: RuntimeClassFlags 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
ms.openlocfilehash: 9fed5bb31b077288495a78aefcbd8401b3520bb6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367220"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags 구조체

[런타임클래스](runtimeclass-class.md)의 인스턴스에 대한 형식을 포함합니다.

## <a name="syntax"></a>구문

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>매개 변수

*플래그*<br/>
[런타임클래스유형 열거](runtimeclasstype-enumeration.md) 값입니다.

## <a name="members"></a>멤버

### <a name="public-constants"></a>공용 상수

|속성|Description|
|----------|-----------------|
|[RuntimeClassFlags::value 상수](#value-constant)|[런타임클래스유형 열거](runtimeclasstype-enumeration.md) 값을 포함합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`RuntimeClassFlags`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="runtimeclassflagsvalue-constant"></a><a name="value-constant"></a>런타임클래스플래그::값 상수

[런타임클래스유형 열거](runtimeclasstype-enumeration.md) 값을 포함하는 필드입니다.

```cpp
static const unsigned int value = flags;
```
