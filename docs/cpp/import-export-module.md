---
title: 모듈, 가져오기, 내보내기
ms.date: 12/12/2019
f1_keywords:
- module_cpp
- import_cpp
- export_cpp
helpviewer_keywords:
- modules [C++]
- modules [C++], import
- modules [C++], export
description: 가져오기 및 내보내기 선언을 사용하여 지정된 모듈에 정의된 형식 및 함수에 액세스하고 게시합니다.
ms.openlocfilehash: a765e9a406660d3c945ef3d70754178b0648458c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374112"
---
# <a name="module-import-export"></a>모듈, 가져오기, 내보내기

**모듈,** **가져오기**및 **내보내기** 선언은 C++20에서 사용할 수 있으며 [/std:c++latest와](../build/reference/std-specify-language-standard-version.md)함께 [/experimental:module](../build/reference/experimental-module.md) 컴파일러 스위치가 필요합니다. 자세한 내용은 [C++의 모듈 개요를](modules-cpp.md)참조하십시오.

## <a name="module"></a>module

모듈 구현 파일의 시작 부분에 **모듈** 선언을 배치하여 파일 내용이 명명된 모듈에 속하도록 지정합니다.

```cpp
module ModuleA;
```

## <a name="export"></a>내보내기

**.ixx**확장이 있어야 하는 모듈의 기본 인터페이스 파일에 **내보내기 모듈** 선언을 사용합니다.

```cpp
export module ModuleA;
```

인터페이스 파일에서 공용 인터페이스의 일부로 사용 되 려는 이름에 **내보내기** 수정자를 사용 합니다.

```cpp
// ModuleA.ixx

export module ModuleA;

namespace Bar
{
   export int f();
   export double d();
   double internal_f(); // not exported
}
```

내보내지 지 않는 이름은 모듈을 가져오는 코드에 표시되지 않습니다.

```cpp
//MyProgram.cpp

import module ModuleA;

int main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

**내보내기** 키워드는 모듈 구현 파일에 나타나지 않을 수 있습니다. **내보내기가** 네임스페이스 이름에 적용되면 네임스페이스의 모든 이름이 내보내됩니다.

## <a name="import"></a>수입

**가져오기** 선언을 사용하여 모듈의 이름을 프로그램에 표시합니다. 가져오기 선언은 모듈 선언 및 #include 지시문 이후에 나타나야 하지만 파일의 모든 선언 앞에 나타납니다.

```cpp
module ModuleA;

#include "custom-lib.h"
import std.core;
import std.regex;
import ModuleB;

// begin declarations here:
template <class T>
class Baz
{...};
```

## <a name="remarks"></a>설명

**가져오기와** **모듈은** 논리적 줄의 시작 부분에 나타날 때만 키워드로 처리됩니다.

```cpp

// OK:
module ;
module module-name
import :
import <
import "
import module-name
export module ;
export module module-name
export import :
export import <
export import "
export import module-name

// Error:
int i; module ;
```

**마이크로소프트 특정**

Microsoft C++에서 토큰 **가져오기** 및 **모듈은** 항상 식별자이며 매크로에 대한 인수로 사용될 때 는 절대 로키키워드가 아닙니다.

### <a name="example"></a>예제

```cpp
#define foo(…) __VA_ARGS__
foo(
import // Always an identifier, never a keyword
)
```

**끝 마이크로 소프트 특정**

## <a name="see-also"></a>참고 항목

[C++에서의 모듈 개요](modules-cpp.md)
