---
title: safe_cast(C++/CLI 및 C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
ms.openlocfilehash: 42e141caed720aa29cf918a2bdf69d9a2c4203dc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544641"
---
# <a name="safe_cast-ccli-and-ccx"></a>safe_cast(C++/CLI 및 C++/CX)

**safe_cast** 작업이 성공하면 지정한 식이 지정한 형식으로 반환되고, 실패하면 `InvalidCastException`이 throw됩니다.

## <a name="all-runtimes"></a>모든 런타임

(이 언어 기능에는 모든 런타임에 적용되는 설명이 없습니다.)

### <a name="syntax"></a>구문

```cpp
[default]:: safe_cast< type-id >( expression )
```

## <a name="windows-runtime"></a>Windows 런타임

**safe_cast**를 사용하여 지정한 식의 형식을 변경할 수 있습니다. 변수 또는 매개 변수를 특정 형식을 변환할 수 있다고 확신하는 경우 **try-catch** 블록 없이 **safe_cast**를 사용하여 개발 중에 프로그래밍 오류를 검색할 수 있습니다. 자세한 내용은 [캐스팅(C++/CX)](../cppcx/casting-c-cx.md)을 참조하세요.

### <a name="syntax"></a>구문

```cpp
[default]:: safe_cast< type-id >( expression )
```

### <a name="parameters"></a>매개 변수

*type-id*<br/>
*expression*을 변환할 형식입니다. 참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조입니다.

*expression*<br/>
참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조로 계산되는 식입니다.

### <a name="remarks"></a>주의

*식을* *형식 id*로 지정 된 형식으로 변환할 수 없는 경우에는 **safe_cast** `InvalidCastException` throw 됩니다. `InvalidCastException`를 catch 하려면 [/Eh (예외 처리 모델)](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 지정 하 고 **try/catch** 문을 사용 합니다.

### <a name="requirements"></a>요구 사항

컴파일러 옵션: `/ZW`

### <a name="examples"></a>예

다음 코드 예제에서는 Windows 런타임에서 **safe_cast**를 사용하는 방법을 보여 줍니다.

```cpp
// safe_cast_ZW.cpp
// compile with: /ZW /EHsc

using namespace default;
using namespace Platform;

interface class I1 {};
interface class I2 {};
interface class I3 {};

ref class X : public I1, public I2 {};

int main(Array<String^>^ args) {
   I1^ i1 = ref new X;
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead
   try {
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.
   }
   catch(InvalidCastException^ ic) {
   wprintf(L"Caught expected exception: %s\n", ic->Message);
   }
}
```

```Output
Caught expected exception: InvalidCastException
```

## <a name="common-language-runtime"></a>공용 언어 런타임

**safe_cast**를 사용하여 식의 형식을 변경하고 안정형 MSIL 코드를 생성할 수 있습니다.

### <a name="syntax"></a>구문

```cpp
[cli]:: safe_cast< type-id >( expression )
```

### <a name="parameters"></a>매개 변수

*type-id*<br/>
참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조입니다.

*expression*<br/>
참조 또는 값 형식에 대한 핸들, 값 형식 또는 참조 또는 값 형식에 대한 추적 참조로 계산되는 식입니다.

### <a name="remarks"></a>주의

`safe_cast<`*type-id*`>(`*expression*`)` 식은 피연산자 *expression*을 *type-id* 형식의 개체로 변환합니다.

컴파일러는 [safe_cast](../cpp/static-cast-operator.md)가 허용되는 대부분의 위치에 **static_cast**를 허용합니다.  그러나 **safe_cast**는 안정형 MSIL 생성이 보장되는 반면, **static_cast**는 검증할 수 없는 MSIL을 생성할 수 있습니다.  안정형 코드에 대한 자세한 내용은 [순수형 코드 및 안정형 코드(C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) 및 [Peverify.exe(PEVerify 도구)](/dotnet/framework/tools/peverify-exe-peverify-tool)를 참조하세요.

**static_cast**와 마찬가지로, **safe_cast**는 사용자 정의 변환을 호출합니다.

캐스트에 대한 자세한 내용은 [캐스팅 연산자](../cpp/casting-operators.md)를 참조하세요.

**safe_cast**는 **const_cast**(**const** 캐스팅)를 적용하지 않습니다.

**safe_cast**는 cli 네임스페이스에 있습니다.  자세한 내용은 [Platform, default 및 cli 네임스페이스](platform-default-and-cli-namespaces-cpp-component-extensions.md)를 참조하세요.

**safe_cast**에 대한 자세한 내용은 다음을 참조하세요.

- [/clr을 사용한 C 스타일 캐스트(C++/CLI)](c-style-casts-with-clr-cpp-cli.md)

- [방법: C++/CLI에서 safe_cast 사용](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)

### <a name="requirements"></a>요구 사항

컴파일러 옵션: `/clr`

### <a name="examples"></a>예

컴파일러에서 **static_cast**를 허용하지 않고 **safe_cast**만 허용하는 경우의 예로 관련 없는 인터페이스 형식 간의 캐스트가 있습니다.  **safe_cast**를 사용하면, 컴파일러에서 변환 오류가 발생하지 않고 런타임에 검사를 수행하여 캐스트가 가능한지 확인합니다.

```cpp
// safe_cast.cpp
// compile with: /clr
using namespace System;

interface class I1 {};
interface class I2 {};
interface class I3 {};

ref class X : public I1, public I2 {};

int main() {
   I1^ i1 = gcnew X;
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead
   try {
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type
   }
   catch(InvalidCastException^) {
      Console::WriteLine("Caught expected exception");
   }
}
```

```Output
Caught expected exception
```

## <a name="see-also"></a>참고 항목

[.NET 및 UWP용 구성 요소 확장](component-extensions-for-runtime-platforms.md)
