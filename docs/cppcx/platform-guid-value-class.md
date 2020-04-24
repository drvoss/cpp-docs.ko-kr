---
title: Platform::Guid 값 클래스
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: 7c3b89ff238b1cb5ee9fbb71e83d20f571e656a3
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031539"
---
# <a name="platformguid-value-class"></a>Platform::Guid 값 클래스

Represents a [GUID](/windows/win32/api/guiddef/ns-guiddef-guid type in the Windows Runtime type system.

## <a name="syntax"></a>구문

```cpp
public value struct Guid
```

### <a name="members"></a>멤버

`Platform::Guid`의 `Equals()`에서 `GetHashCode()`의 `ToString()` 이 및 메서드는 [플랫폼 ::Object 클래스](../cppcx/platform-object-class.md)및 [플랫폼::Type 클래스에서](../cppcx/platform-type-class.md)파생된 `GetTypeCode()` 메서드입니다. `Platform::Guid`또한 다음과 같은 회원이 있습니다.

|멤버|Description|
|------------|-----------------|
|[Guid](#ctor)|`Platform::Guid`의 새 인스턴스를 초기화합니다.|
|[연산자==](#operator-equality)|같음 연산자입니다.|
|[연산자!=](#operator-inequality)|같지 않음 연산자입니다.|
|[연산자&lt;](#operator-less)|보다 작음 연산자입니다.|
|[연산자()](#operator-call)|`Platform::Guid` 를 `GUID`로 변환합니다.|

### <a name="remarks"></a>설명

새 `Platform::Guid`를 생성 하려면 [Windows::기초::GuidHelp::CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid) 정적 메서드를 사용 합니다.

### <a name="requirements"></a>요구 사항

**지원되는 최소 클라이언트:** 윈도우 8

**지원되는 최소 서버:** 윈도우 서버 2012

**네임스페이스:** Platform

**메타데이터:** 플랫폼.winmd

## <a name="guidguid-constructors"></a><a name="ctor"></a>Guid::Guid 생성자

`Platform::Guid`의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    unsigned char d,
    unsigned char e,
    unsigned char f,
    unsigned char g,
    unsigned char h,
    unsigned char i,
    unsigned char j,
    unsigned char k );

Guid(GUID m);

Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    Array<unsigned char>^ n );
```

### <a name="parameters"></a>매개 변수

*a.*<br/>
의 처음 4 바이트. `GUID`

*B*<br/>
의 다음 2 바이트. `GUID`

*C*<br/>
의 다음 2 바이트. `GUID`

*D*<br/>
`GUID`의 다음 바이트입니다.

*전자*<br/>
`GUID`의 다음 바이트입니다.

*F*<br/>
`GUID`의 다음 바이트입니다.

*G*<br/>
`GUID`의 다음 바이트입니다.

*H*<br/>
`GUID`의 다음 바이트입니다.

*Ⅰ*<br/>
`GUID`의 다음 바이트입니다.

*J*<br/>
`GUID`의 다음 바이트입니다.

*k*<br/>
`GUID`의 다음 바이트입니다.

*M*<br/>
A는 `GUID` GUID [구조를](/windows/win32/api/guiddef/ns-guiddef-guid)형성한다.

*n*<br/>
의 나머지 8 바이트. `GUID`

## <a name="guidoperator-operator"></a><a name="operator-equality"></a>Guid::연산자== 연산자

두 `Platform::Guid` 인스턴스가 같은지 비교합니다.

### <a name="syntax"></a>구문

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>매개 변수

*guid1*<br/>
비교할 첫 번째 `Platform::Guid`입니다.

*guid2*<br/>
비교할 두 번째 `Platform::Guid`입니다.

### <a name="return-value"></a>Return Value

두 `Platform::Guid` 인스턴스가 같으면 true입니다.

### <a name="remarks"></a>설명

`==` [Windows::Foundation::GuidHelper::정적](/uwp/api/windows.foundation.guidhelper.equals) 메서드와 동일합니다.

## <a name="guidoperator-operator"></a><a name="operator-inequality"></a>Guid::연산자!= 연산자

두 `Platform::Guid` 인스턴스가 다른지 비교합니다.

### <a name="syntax"></a>구문

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>매개 변수

*guid1*<br/>
비교할 첫 번째 `Platform::Guid`입니다.

*guid2*<br/>
비교할 두 번째 `Platform::Guid`입니다.

### <a name="return-value"></a>Return Value

두 `Platform::Guid` 인스턴스가 같지 않은 경우 true입니다.

## <a name="guidoperatorlt-operator"></a><a name="operator-less"></a>Guid::연산자&lt;

순서를 `Platform::Guid` 정할 두 인스턴스를 비교합니다.

### <a name="syntax"></a>구문

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>매개 변수

*guid1*<br/>
비교할 첫 번째 `Platform::Guid`입니다.

*guid2*<br/>
비교할 두 번째 `Platform::Guid`입니다.

### <a name="return-value"></a>Return Value

*guid1이* *guid2*전에 주문된 경우 true입니다. 순서는 각각 `Platform::Guid` 32비트 서명되지 않은 값 4개배열인 것처럼 처리한 후 사전순입니다. 이는 SQL Server 또는 .NET Framework에서 사용하는 순서가 아니며 문자열 표현에 의한 사전 순서와 동일하지도 않습니다.

이 연산자는 `Guid` C++ 표준 라이브러리에서 개체를 보다 쉽게 사용할 수 있도록 제공됩니다.

## <a name="guidoperator-operator"></a><a name="operator-call"></a>Guid::연산자() 연산자

암시적으로 a를 `Platform::Guid` [GUID 구조로](/windows/win32/api/guiddef/ns-guiddef-guid)변환합니다.

### <a name="syntax"></a>구문

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Return Value

[GUID 구조.](/windows/win32/api/guiddef/ns-guiddef-guid)

## <a name="see-also"></a>참조

[Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)
