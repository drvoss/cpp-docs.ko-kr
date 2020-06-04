---
title: Platform::Type 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Type::GetTypeCode
- VCCORLIB/Platform::Type::FullName
helpviewer_keywords:
- Platform::Type Class
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
ms.openlocfilehash: 7463a2518e6ec5cc84f59db05cfaf60e43eb9fde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322087"
---
# <a name="platformtype-class"></a>Platform::Type 클래스

특정 형식에 대한 런타임 정보(문자열 이름 및 형식 코드)를 포함합니다. [Object::GetType을](../cppcx/platform-object-class.md#gettype) 호출하거나 클래스 또는 구조체 이름에 [typeid](../extensions/typeid-cpp-component-extensions.md) 연산자 사용으로 가져옵니다.

## <a name="syntax"></a>구문

```cpp
public ref class Platform::Type :
    Platform::Object, Platform::Details::IEquatable,
    Platform::Details::IPrintable
```

### <a name="remarks"></a>설명

`Type` 클래스는 개체의 런타임 형식을 기반으로 분기하는 `if` 또는 `switch` 문을 사용하여 처리를 지시해야 하는 애플리케이션에서 유용합니다. 형식의 범주를 설명하는 형식 코드는 [Type::GetTypeCode](#gettypecode) 멤버 함수를 사용하여 검색됩니다.

## <a name="public-methods"></a>public 메서드

|||
|-|-|
|[Type::GetTypeCode 메서드](#gettypecode)|개체의 [Platform::TypeCode 열거형](../cppcx/platform-typecode-enumeration.md) 값을 반환합니다.|
|[유형 ::Tostring 방법](#tostring)|메타데이터에 지정된 형식의 이름을 반환합니다.|

## <a name="public-properties"></a>public 속성

|||
|-|-|
|[유형 ::전체 이름](#fullname)|형식의 정규화된 이름을 나타내며 ::(콜론 두 개) 대신 .(점)을 구분 기호로 사용(예: "MyNamespace.MyClass")하는 [Platform::String 클래스](../cppcx/platform-string-class.md)^을 (점) 구분 기호가 아니라 :: (이중 콜론)-예를 `MyNamespace.MyClass`들어 .|

## <a name="conversion-operators"></a>변환 연산자

|||
|-|-|
|[연산자 유형^](../cppcx/operator-type-hat.md)|`Windows::UI::Xaml::Interop::TypeName` 을 `Platform::Type`으로 변환할 수 있습니다.|
|[연산자 Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)|`Platform::Type` 을 `Windows::UI::Xaml::Interop::TypeName`으로 변환할 수 있습니다.|

### <a name="requirements"></a>요구 사항

**지원되는 최소 클라이언트:** 윈도우 8

**지원되는 최소 서버:** 윈도우 서버 2012

**네임스페이스:** Platform

**메타데이터:** 플랫폼.winmd

## <a name="typefullname-property"></a><a name="fullname"></a>유형::전체 이름 속성

양식에서 `Namespace.Type`현재 형식의 정규화된 이름을 검색합니다.

### <a name="syntax"></a>구문

```cpp
String^ FullName();
```

### <a name="return-value"></a>Return Value

형식의 이름입니다.

### <a name="example"></a>예제

```cpp
//  namespace is TestApp
MainPage::MainPage()
{
    InitializeComponent();
    Type^ t = this->GetType();
    auto s = t->FullName; // returns "TestApp.MainPage"
    auto s2 = t->ToString(); //also returns "TestApp.MainPage"
}
```

## <a name="typegettypecode-method"></a><a name="gettypecode"></a>유형 ::GetTypeCode 방법

기본 제공 형식의 숫자 형식 범주를 검색합니다.

### <a name="syntax"></a>구문

```cpp
Platform::TypeCode GetTypeCode();
```

### <a name="return-value"></a>Return Value

Platform::TypeCode 열거형 값의 하나입니다.

### <a name="remarks"></a>설명

`typeid` 속성은 GetTypeCode() 멤버 메서드에 해당합니다.

## <a name="typetostring-method"></a><a name="tostring"></a>유형 ::Tostring 방법

형식의 이름을 검색합니다.

### <a name="syntax"></a>구문

```cpp
Platform::String^ ToString();
```

### <a name="return-value"></a>Return Value

메타데이터에 지정된 형식의 이름입니다.

## <a name="see-also"></a>참고 항목

[Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)
