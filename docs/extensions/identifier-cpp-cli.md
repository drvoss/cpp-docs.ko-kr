---
title: __identifier(C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
ms.openlocfilehash: 0da32aae9a8c2c7f21ee9576e1e1147822314a36
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172180"
---
# <a name="__identifier-ccli"></a>__identifier(C++/CLI)

C++ 키워드를 식별자로 사용할 수 있습니다.

## <a name="all-platforms"></a>모든 플랫폼

### <a name="syntax"></a>구문

```cpp
__identifier(C++_keyword)
```

### <a name="remarks"></a>설명

키워드가 아닌 식별자에 **__identifier** 키워드를 사용할 수 있지만, 스타일상 사용하지 않는 것이 좋습니다.

## <a name="windows-runtime"></a>Windows 런타임

### <a name="requirements"></a>요구 사항

컴파일러 옵션: `/ZW`

### <a name="examples"></a>예

**예제**

다음 예제에서는 C#으로 **template** 클래스를 만들고 DLL로 배포합니다. **template** 클래스를 사용하는 C++/CLI 프로그램에서, **__identifier** 키워드는 **template**이 표준 C++ 키워드라는 팩트를 숨깁니다.

```csharp
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /ZW
#using <identifier_template.dll>
int main() {
   __identifier(template)^ pTemplate = ref new __identifier(template)();
   pTemplate->Run();
}
```

## <a name="common-language-runtime"></a>공용 언어 런타임

### <a name="remarks"></a>설명

**__identifier** 키워드는 `/clr` 컴파일러 옵션에서 유효합니다.

### <a name="requirements"></a>요구 사항

컴파일러 옵션: `/clr`

### <a name="examples"></a>예

다음 예제에서는 C#으로 **template** 클래스를 만들고 DLL로 배포합니다. **template** 클래스를 사용하는 C++/CLI 프로그램에서, **__identifier** 키워드는 **template**이 표준 C++ 키워드라는 팩트를 숨깁니다.

```csharp
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /clr
#using <identifier_template.dll>

int main() {
   __identifier(template) ^pTemplate = gcnew __identifier(template)();
   pTemplate->Run();
}
```

## <a name="see-also"></a>참고 항목

[.NET 및 UWP용 구성 요소 확장](component-extensions-for-runtime-platforms.md)<br/>
[.NET 및 UWP용 구성 요소 확장](component-extensions-for-runtime-platforms.md)
