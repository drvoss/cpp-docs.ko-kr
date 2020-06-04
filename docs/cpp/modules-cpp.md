---
title: C++에서의 모듈 개요
ms.date: 12/13/2019
helpviewer_keywords:
- modules [C++]
- modules [C++], overview
description: C++20의 모듈은 헤더 파일에 대한 최신 대안을 제공합니다.
ms.openlocfilehash: cd45be1dee888c8caeb65b7ff002ac8fee1ecbe1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370755"
---
# <a name="overview-of-modules-in-c"></a>C++에서의 모듈 개요

C++20은 C++ 라이브러리 및 프로그램의 구성 요소를 구성하기 위한 현대적인 솔루션인 *모듈을 소개합니다.* 모듈은 가져오는 [변환 단위와](https://wikipedia.org/wiki/Translation_unit_(programming)) 독립적으로 컴파일되는 소스 코드 파일 집합입니다. 모듈은 헤더 파일 사용과 관련된 많은 문제를 제거하거나 크게 줄이며 컴파일 시간을 줄일 수 있습니다. 모듈에 선언된 매크로, 전처리기 지시문 및 내보내지 않는 이름은 표시되지 않으므로 모듈을 가져오는 변환 단위의 컴파일에는 영향을 주지 않습니다. 매크로 재정의에 대한 걱정 없이 원하는 순서로 모듈을 가져올 수 있습니다. 가져오기 변환 단위의 선언은 가져온 모듈에서 오버로드 확인 또는 이름 조회에 참여하지 않습니다. 모듈을 한 번 컴파일하면 결과는 내보낸 모든 형식, 함수 및 템플릿을 설명하는 이진 파일에 저장됩니다. 이 파일은 헤더 파일보다 훨씬 빠르게 처리할 수 있으며 프로젝트에서 모듈을 가져오는 모든 곳에서 컴파일러에서 다시 사용할 수 있습니다.

모듈은 헤더 파일과 나란히 사용할 수 있습니다. C++ 소스 파일은 모듈을 가져오고 헤더 파일을 #include 수 있습니다. 경우에 따라 헤더 파일은 전처리기에서 텍스트로 #included 것이 아니라 모듈로 가져올 수 있습니다. 새 프로젝트는 헤더 파일이 아닌 모듈을 가능한 한 많이 사용하는 것이 좋습니다. 활성 개발 중인 대규모 기존 프로젝트의 경우 레거시 헤더를 모듈로 변환하여 컴파일 시간을 의미 있게 줄일 수 있는지 확인하는 것이 좋습니다.

## <a name="enable-modules-in-the-microsoft-c-compiler"></a>Microsoft C++ 컴파일러에서 모듈 사용

Visual Studio 2019 버전 16.2에서 모듈은 Microsoft C++ 컴파일러에서 완전히 구현되지 않습니다. 모듈 기능을 사용하여 단일 파티션 모듈을 만들고 Microsoft에서 제공하는 표준 라이브러리 모듈을 가져올 수 있습니다. 모듈에 대한 지원을 사용하려면 [/experimental:module](../build/reference/experimental-module.md) 및 [/std:c++latest로](../build/reference/std-specify-language-standard-version.md)컴파일합니다. Visual Studio 프로젝트에서 **솔루션 탐색기에서** 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성을**선택합니다. **구성** 드롭다운을 **모든 구성으로**설정한 다음 **구성 속성** > **C/C++** > **언어를** > 선택하면**C++ 모듈(실험적)이 활성화됩니다.**

모듈과 모듈을 사용하는 코드는 동일한 컴파일러 옵션으로 컴파일되어야 합니다.

## <a name="consume-the-c-standard-library-as-modules"></a>C++ 표준 라이브러리를 모듈로 사용

C++20 표준에 의해 지정되지는 않았지만 Microsoft는 C++ 표준 라이브러리를 모듈로 가져올 수 있도록 합니다. C++ 표준 라이브러리를 헤더 파일을 통해 #including 대신 모듈로 가져오면 프로젝트 크기에 따라 컴파일 시간을 단축할 수 있습니다. 라이브러리는 다음 모듈로 구성됩니다.

- std.regex는 헤더 \<정규식> 내용을 제공합니다.
- std.filesystem은 헤더 \<파일 시스템> 내용을 제공합니다.
- std.memory는 헤더 \<메모리>
- std.threading은 헤더 \<원자성>, \<condition_variable>, 향후>, \< \< \<뮤텍스>, shared_mutex> 및 \<스레드>
- std.core는 C++ 표준 라이브러리의 다른 모든 것을 제공합니다.

이러한 모듈을 사용하려면 소스 코드 파일의 맨 위에 가져오기 선언을 추가하기만 하면 됩니다. 다음은 그 예입니다.

```cpp
import std.core;
import std.regex;
```

Microsoft 표준 라이브러리 모듈을 사용하려면 [/EHsc](../build/reference/eh-exception-handling-model.md) 및 [/MD](../build/reference/md-mt-ld-use-run-time-library.md) 옵션을 사용하여 프로그램을 컴파일합니다.

## <a name="basic-example"></a>기본 예제

다음 예제에서는 **Foo.ixx라는**소스 파일에서 간단한 모듈 정의를 보여 주며 있습니다. Visual Studio의 모듈 인터페이스 파일에는 **.ixx** 확장이 필요합니다. 이 예제에서 인터페이스 파일에는 함수 정의와 선언이 포함되어 있습니다. 그러나 정의는 하나 이상의 개별 파일에 배치할 수도 있습니다(이후 예제와 같이). **내보내기 모듈 Foo** 문은 이 파일이 라는 `Foo`모듈의 기본 인터페이스임을 나타냅니다. **내보내기** `f()` 수정자는 다른 프로그램이나 모듈에서 `Foo` 가져올 때 이 함수가 표시된다는 것을 나타냅니다. 모듈은 네임스페이스 `Bar`를 참조합니다.

```cpp
export module Foo;

#define ANSWER 42

namespace Bar
{
   int f_internal() {
        return ANSWER;
      }

   export int f() {
      return f_internal();
   }
}
```

**MyProgram.cpp** 파일은 **가져오기** 선언을 사용하여 `Foo`에서 내보낸 이름에 액세스합니다. 이름은 `Bar` 여기에 표시되지만 모든 멤버는 볼 수 없습니다. 또한 매크로가 `ANSWER` 표시되지 않습니다.

```cpp

import Foo;
import std.core;

using namespace std;

int main()
{
   cout << "The result of f() is " << Bar::f() << endl; // 42
   // int i = Bar::f_internal(); // C2039
   // int j = ANSWER; //C2065
}

```

가져오기 선언은 전역 범위에서만 나타날 수 있습니다.

## <a name="implementing-modules"></a>모듈 구현

이름을 내보내는 단일 인터페이스 파일(.ixx)을 사용하여 모듈을 만들고 모든 함수 및 형식의 구현을 포함할 수 있습니다. .h 및 .cpp 파일이 사용되는 방법과 유사하게 하나 이상의 별도의 구현 파일에 구현을 넣을 수도 있습니다. **내보내기** 키워드는 인터페이스 파일에서만 사용됩니다. 구현 파일은 다른 모듈을 **가져올** 수 있지만 이름을 **내보낼** 수는 없습니다. 구현 파일은 확장명으로 명명될 수 있습니다. 인터페이스 파일과 이를 뒷받침하는 구현 파일 집합은 *모듈 단위라는*특별한 종류의 번역 단위로 처리됩니다. 구현 파일에 선언된 이름은 동일한 모듈 단위 내의 다른 모든 파일에 자동으로 표시됩니다.

더 큰 모듈의 경우 모듈을 *파티션이라는*여러 모듈 단위로 분할할 수 있습니다. 각 파티션은 하나 이상의 구현 파일이 지원하는 인터페이스 파일로 구성됩니다. (Visual Studio 2019 버전 16.2현재 파티션은 아직 완전히 구현되지 않았습니다.)

## <a name="modules-namespaces-and-argument-dependent-lookup"></a>모듈, 네임스페이스 및 인수 종속 조회

모듈의 네임스페이스 규칙은 다른 코드와 동일합니다. 네임스페이스 내의 선언이 내보내는 경우 내보내기되지 않은 멤버를 제외한 둘러싸는 네임스페이스도 암시적으로 내보내게 됩니다. 네임스페이스를 명시적으로 내보낸 경우 해당 네임스페이스 정의 내의 모든 선언이 내보내됩니다.

가져오기 변환 단위에서 오버로드 확인에 대한 인수 종속 조회를 수행할 때 컴파일러는 함수의 인수 형식이 정의된 것과 동일한 변환 단위(모듈 인터페이스 포함)에 선언된 함수를 고려합니다.

### <a name="module-partitions"></a>모듈 파티션

> [!NOTE]
> 이 섹션은 완전성을 위해 제공됩니다. 파티션은 Microsoft C++ 컴파일러에서 아직 구현되지 않았습니다.

모듈은 각각 인터페이스 파일과 0 개 이상의 구현 파일로 구성된 *파티션으로*구성 할 수 있습니다. 모듈 파티션은 전체 모듈의 모든 선언에 대한 소유권을 공유한다는 점을 제외하면 모듈과 유사합니다. 파티션 인터페이스 파일로 내보내는 모든 이름은 기본 인터페이스 파일에서 가져오고 다시 내보내됩니다. 파티션의 이름은 모듈 이름 뒤에 콜론으로 시작해야 합니다. 모든 파티션의 선언은 전체 모듈 내에 표시됩니다. 단일 정의 규칙(ODR) 오류를 방지하기 위해 특별한 예방 조치가 필요하지 않습니다. 한 파티션에서 이름(함수, 클래스 등)을 선언하고 다른 파티션에서 정의할 수 있습니다. 파티션 구현 파일은 다음과 같이 시작됩니다.

```cpp
module Foo:part1
```

파티션 인터페이스 파일은 다음과 같이 시작됩니다.

```cpp
export module Foo:part1
```

다른 파티션의 선언에 액세스하려면 파티션을 가져와야 하지만 모듈 이름이 아닌 파티션 이름만 사용할 수 있습니다.

```cpp
module Foo:part2;
import :part1;
```

기본 인터페이스 단위는 다음과 같이 모듈의 모든 인터페이스 파티션 파일을 가져오고 다시 내보내야 합니다.

```cpp
export import :part1
export import :part2
...
```

기본 인터페이스 단위는 파티션 구현 파일을 가져올 수 있지만 해당 파일은 이름을 내보낼 수 없으므로 내보낼 수 없습니다. 이렇게 하면 모듈이 구현 세부 정보를 모듈 내부에 유지할 수 있습니다.

## <a name="modules-and-header-files"></a>모듈 및 헤더 파일

모듈 선언 앞에 `#include` 지시문을 배치하여 모듈 소스 파일에 헤더 파일을 포함할 수 있습니다. 이러한 파일은 *전역 모듈 조각에*있는 것으로 간주됩니다. 모듈은 명시적으로 포함하는 헤더에 있는 *전역 모듈 조각의* 이름만 볼 수 있습니다. 전역 모듈 조각에는 실제로 사용되는 기호만 포함되어 있습니다.

```cpp
// MyModuleA.cpp

#include "customlib.h"
#include "anotherlib.h"

import std.core;
import MyModuleB;

//... rest of file
```

기존 헤더 파일을 사용하여 가져올 모듈을 제어할 수 있습니다.

```cpp
// MyProgram.h
import std.core;
#ifdef DEBUG_LOGGING
import std.filesystem;
#endif
```

### <a name="imported-header-files"></a>가져온 헤더 파일

> [!NOTE]
> 이 섹션은 정보 전용입니다. 레거시 가져오기는 Microsoft C++ 컴파일러에서 아직 구현되지 않았습니다.

일부 헤더는 **가져오기** 키워드를 사용하여 가져올 수 있도록 충분히 독립적입니다. 가져온 헤더와 가져온 모듈의 주요 차이점은 가져오기 문 직후 가져오기 프로그램에서 헤더의 모든 전처리기 정의가 표시된다는 점입니다. (해당 헤더에 포함된 파일의 전처리기 정의는 표시되지 *않습니다.)*

```cpp
import <vector>
import "myheader.h"
```

## <a name="see-also"></a>참고 항목

[모듈, 가져오기, 내보내기](import-export-module.md)
