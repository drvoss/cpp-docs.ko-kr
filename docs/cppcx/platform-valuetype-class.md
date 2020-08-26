---
title: Platform::ValueType 클래스
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: f4ce34fa3f197424833d34bdb866712d412e69c3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846552"
---
# <a name="platformvaluetype-class"></a>Platform::ValueType 클래스

값 형식 인스턴스의 기본 클래스입니다.

## <a name="syntax"></a>구문

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>public 메서드

| 이름 | Description |
|--|--|
| [ValueType:: ToString](#tostring) | 개체의 문자열 표현을 반환합니다. [Platform:: Object](../cppcx/platform-object-class.md)에서 상속 됩니다. |

### <a name="remarks"></a>설명

ValueType 클래스는 값 형식을 생성하는 데 사용됩니다. ValueType은 기본 멤버인 Object에서 파생됩니다. 그러나 컴파일러는 해당 기본 멤버를 ValueType 클래스에서 파생된 값 형식에서 분리합니다. 컴파일러는 값 형식이 boxing될 때 해당 기본 멤버를 다시 연결합니다.

### <a name="requirements"></a>요구 사항

**지원 되는 최소 클라이언트:** Windows 8

**지원 되는 최소 서버:** Windows Server 2012

**네임스페이스:** Platform

**메타 데이터:** platform.object

## <a name="valuetypetostring-method"></a><a name="tostring"></a> ValueType:: ToString 메서드

개체의 문자열 표현을 반환합니다.

### <a name="syntax"></a>구문

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>Return Value

값을 나타내는 Platform:: String입니다.

## <a name="see-also"></a>참고 항목

[Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)
