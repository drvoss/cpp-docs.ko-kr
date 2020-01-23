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
ms.openlocfilehash: 7406bf75595bef20775ee1b67c27bd62bff1a932
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518285"
---
# <a name="module-import-export"></a>모듈, 가져오기, 내보내기

**모듈**, **가져오기**및 **내보내기** 선언은 c + + 20에서 사용할 수 있으며/std: [module](../build/reference/experimental-module.md) 컴파일러 스위치와 함께 [/std: C + + 최신](../build/reference/std-specify-language-standard-version.md)이 필요 합니다. 자세한 내용은 [ C++의 모듈 개요 ](modules-cpp.md)를 참조 하세요.

## <a name="module"></a>name

모듈 구현 파일의 시작 부분에 **모듈** 선언을 놓고 파일 내용이 명명 된 모듈에 속하도록 지정 합니다.

```cpp
module ModuleA;
```

## <a name="export"></a>export

모듈이 다음과 같은 기본 인터페이스 파일에 대해 **export 모듈** 선언을 사용 **합니다.**

```cpp
export module ModuleA;
```

인터페이스 파일에서 공용 인터페이스의 일부인 이름에 대해 **내보내기** 한정자를 사용 합니다.

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

**Export** 키워드는 모듈 구현 파일에 표시 되지 않을 수 있습니다. **내보내기가** 네임 스페이스 이름에 적용 되 면 네임 스페이스의 모든 이름을 내보냅니다.

## <a name="import"></a>가져오기

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

## <a name="remarks"></a>주의

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

Microsoft C++에서 토큰 **가져오기** 및 **모듈** 은 매크로에 대 한 인수로 사용 되는 경우 항상 식별자 이며 키워드를 사용 하지 않습니다.

### <a name="example"></a>예

```cpp
#define foo(…) __VA_ARGS__
foo(
import // Always an identifier, never a keyword
)
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[모듈 개요C++](modules-cpp.md)
