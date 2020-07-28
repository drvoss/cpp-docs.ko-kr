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
description: 가져오기 및 내보내기 선언을 사용 하 여에 액세스 하 고 지정 된 모듈에 정의 된 형식과 함수를 게시할 수 있습니다.
ms.openlocfilehash: 5be1618d7e64f6887cf78bd863d428d6710eaf7e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87187194"
---
# <a name="module-import-export"></a>모듈, 가져오기, 내보내기

**모듈**, **가져오기**및 **`export`** 선언은 c + + 20에서 사용할 수 있으며/std: [c + + 최신](../build/reference/std-specify-language-standard-version.md)와 함께 [/proers: module](../build/reference/experimental-module.md) 컴파일러 스위치가 필요 합니다. 자세한 내용은 [c + +의 모듈 개요](modules-cpp.md)를 참조 하세요.

## <a name="module"></a>모듈(module)

모듈 구현 파일의 시작 부분에 **모듈** 선언을 놓고 파일 내용이 명명 된 모듈에 속하도록 지정 합니다.

```cpp
module ModuleA;
```

## <a name="export"></a>내보내기

모듈이 다음과 같은 기본 인터페이스 파일에 대해 **export 모듈** 선언을 사용 **합니다.**

```cpp
export module ModuleA;
```

인터페이스 파일에서 **`export`** 공용 인터페이스의 일부가 되도록 하려는 이름에 한정자를 사용 합니다.

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

내보내지 않는 이름은 모듈을 가져오는 코드에 표시 되지 않습니다.

```cpp
//MyProgram.cpp

import module ModuleA;

int main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

**`export`** 키워드는 모듈 구현 파일에 표시 되지 않을 수 있습니다. **`export`** 이 네임 스페이스 이름에 적용 되 면 네임 스페이스의 모든 이름을 내보냅니다.

## <a name="import"></a>import

모듈의 이름을 프로그램에 표시 하려면 **가져오기** 선언을 사용 합니다. 가져오기 선언은 모듈 선언 후와 #include 지시문 뒤에, 파일의 모든 선언 앞에 나타나야 합니다.

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

**Import** 와 **module** 은 모두 논리 줄의 시작 부분에 표시 되는 경우에만 키워드로 처리 됩니다.

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

**Microsoft 전용**

Microsoft c + +에서 token **import** 및 **module** 은 항상 식별자 이며 매크로에 대 한 인수로 사용 되는 경우 키워드가 아닙니다.

### <a name="example"></a>예제

```cpp
#define foo(…) __VA_ARGS__
foo(
import // Always an identifier, never a keyword
)
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[C++에서의 모듈 개요](modules-cpp.md)
