---
title: C++에서의 모듈 개요
ms.date: 12/13/2019
helpviewer_keywords:
- modules [C++]
- modules [C++], overview
description: C + + 20의 모듈은 헤더 파일에 대 한 최신 대안을 제공 합니다.
ms.openlocfilehash: fe5beee92ed257cca8143fa95f8f59bc9308fd5d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233680"
---
# <a name="overview-of-modules-in-c"></a>C++에서의 모듈 개요

C + + 20에는 c + + 라이브러리 및 프로그램을 구성 요소화 하는 최신 솔루션인 *모듈이*도입 되었습니다. 모듈은 해당 파일을 가져오는 [변환 단위](https://wikipedia.org/wiki/Translation_unit_(programming)) 와 별개로 컴파일되는 소스 코드 파일의 집합입니다. 모듈은 헤더 파일 사용과 관련 된 많은 문제를 제거 하거나 크게 줄이고 잠재적으로 컴파일 시간을 단축 하기도 합니다. 모듈에 선언 된 매크로, 전처리기 지시문 및 내보내지 않는 이름은 표시 되지 않으므로 모듈을 가져오는 변환 단위를 컴파일할 때 영향을 주지 않습니다. 매크로 재정의 고려 하지 않고 모듈을 순서에 관계 없이 가져올 수 있습니다. 가져오는 변환 단위의 선언은 가져온 모듈의 오버 로드 확인 또는 이름 조회에 참여 하지 않습니다. 모듈을 한 번 컴파일한 후에는 내보낸 모든 형식, 함수 및 템플릿을 설명 하는 이진 파일에 결과가 저장 됩니다. 이 파일은 헤더 파일 보다 훨씬 빠르게 처리 될 수 있으며, 프로젝트에서 모듈을 가져오는 모든 위치에서 컴파일러에 의해 다시 사용 될 수 있습니다.

모듈은 헤더 파일과 나란히 함께 사용할 수 있습니다. C + + 소스 파일은 모듈을 가져올 수 있으며 헤더 파일을 #include 수도 있습니다. 경우에 따라 전처리기에서 #included 하는 것이 아니라 모듈로 헤더 파일을 가져올 수 있습니다. 새 프로젝트는 헤더 파일이 아닌 모듈을 가능한 한 많이 사용 하는 것이 좋습니다. 활성 개발 중인 대규모 기존 프로젝트의 경우에는 레거시 헤더를 모듈로 변환 하 여 컴파일 시간에 대 한 의미 있는 감소를 확인 하는 것이 좋습니다.

## <a name="enable-modules-in-the-microsoft-c-compiler"></a>Microsoft c + + 컴파일러에서 모듈 사용

Visual Studio 2019 버전 16.2에서는 모듈이 Microsoft c + + 컴파일러에서 완전히 구현 되지 않았습니다. 모듈 기능을 사용 하 여 단일 파티션 모듈을 만들고 Microsoft에서 제공 하는 표준 라이브러리 모듈을 가져올 수 있습니다. 모듈에 대 한 지원을 사용 하도록 설정 하려면 [/o실험적: module](../build/reference/experimental-module.md) 및 [/std: c + + 최신](../build/reference/std-specify-language-standard-version.md)으로 컴파일합니다. Visual Studio 프로젝트에서 **솔루션 탐색기** 의 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다. **구성** 드롭다운을 **모든 구성**으로 설정 하 고 **구성 속성**  >  **c/c + +**  >  **언어**  >  **사용 c + + 모듈 (실험적)** 을 선택 합니다.

모듈 및 모듈을 사용 하는 코드는 동일한 컴파일러 옵션을 사용 하 여 컴파일해야 합니다.

## <a name="consume-the-c-standard-library-as-modules"></a>C + + 표준 라이브러리를 모듈로 사용

C + + 20 standard로 지정 되지 않았지만, Microsoft에서는 c + + 표준 라이브러리의 구현을 모듈로 가져올 수 있습니다. 헤더 파일을 통해 #including 하지 않고 c + + 표준 라이브러리를 모듈로 가져오면 프로젝트 크기에 따라 컴파일 시간을 단축할 수 있습니다. 라이브러리는 다음 모듈에 대해이를 위한 것입니다.

- 표준 regex는 헤더의 콘텐츠를 제공 합니다.\<regex>
- 표준 파일 시스템은 헤더의 내용을 제공 합니다.\<filesystem>
- std. memory는 헤더의 내용을 제공 합니다.\<memory>
- std. 스레딩은 헤더,,,, \<atomic> \<condition_variable> \<future> \<mutex> \<shared_mutex> 및의 내용을 제공 합니다.\<thread>
- 표준 core는 c + + 표준 라이브러리의 모든 항목을 제공 합니다.

이러한 모듈을 사용 하려면 소스 코드 파일의 맨 위에 가져오기 선언을 추가 하기만 하면 됩니다. 예를 들면 다음과 같습니다.

```cpp
import std.core;
import std.regex;
```

Microsoft Standard Library 모듈을 사용 하려면 [/ehsc](../build/reference/eh-exception-handling-model.md) 및 [/md](../build/reference/md-mt-ld-use-run-time-library.md) 옵션으로 프로그램을 컴파일합니다.

## <a name="basic-example"></a>기본 예제

다음 예제에서는 **Foo. ixx**라는 소스 파일의 간단한 모듈 정의를 보여 줍니다. Visual Studio의 모듈 인터페이스 파일에는 **. ixx** 확장이 필요 합니다. 이 예제에서 인터페이스 파일에는 선언 뿐만 아니라 함수 정의가 포함 되어 있습니다. 그러나이 정의는 이후 예제에서 볼 수 있듯이 하나 이상의 개별 파일에도 배치 될 수 있습니다. **Export Module Foo** 문은이 파일이 호출 된 모듈의 기본 인터페이스 임을 나타냅니다 `Foo` . **`export`** 의 한정자는 `f()` `Foo` 를 다른 프로그램 또는 모듈에서 가져올 때이 함수를 볼 수 있음을 나타냅니다. 모듈은 네임 스페이스를 참조 합니다 `Bar` .

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

**Myprogram. .cpp** 파일은 **가져오기** 선언을 사용 하 여에서 내보낸 이름에 액세스 합니다 `Foo` . 여기에는 이름이 `Bar` 표시 되지만 모든 멤버는 표시 되지 않습니다. 또한 매크로는 `ANSWER` 표시 되지 않습니다.

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

가져오기 선언은 전역 범위에만 나타날 수 있습니다.

## <a name="implementing-modules"></a>모듈 구현

이름을 내보내고 모든 함수 및 형식의 구현을 포함 하는 단일 인터페이스 파일 (. ixx)을 사용 하 여 모듈을 만들 수 있습니다. 또한 .h 및 .cpp 파일을 사용 하는 방법과 유사 하 게 하나 이상의 개별 구현 파일에 구현을 배치할 수 있습니다. **`export`** 키워드는 인터페이스 파일에만 사용 됩니다. 구현 파일은 다른 모듈을 **가져올** 수 있지만 이름을 지정할 수는 없습니다 **`export`** . 구현 파일의 이름은 모든 확장명을 사용 하 여 지정할 수 있습니다. 인터페이스 파일 및 해당 파일을 반환 하는 구현 파일 집합은 *모듈 단위*라는 특수 한 종류의 변환 단위로 처리 됩니다. 모든 구현 파일에서 선언 된 이름은 같은 모듈 단위 내의 다른 모든 파일에 자동으로 표시 됩니다.

큰 모듈의 경우 모듈을 *파티션*이라는 여러 모듈 단위로 분할할 수 있습니다. 각 파티션은 하나 이상의 구현 파일에 의해 지원 되는 인터페이스 파일로 구성 됩니다. (Visual Studio 2019 버전 16.2에서 파티션은 아직 완전히 구현 되지 않았습니다.)

## <a name="modules-namespaces-and-argument-dependent-lookup"></a>모듈, 네임 스페이스 및 인수 종속 조회

모듈의 네임 스페이스에 대 한 규칙은 다른 코드의 경우와 동일 합니다. 네임 스페이스 내에서 선언을 내보내는 경우에는 바깥쪽 네임 스페이스 (내보낼 수 없는 멤버 제외)도 암시적으로 내보내집니다. 네임 스페이스를 명시적으로 내보내는 경우 해당 네임 스페이스 정의의 모든 선언을 내보냅니다.

가져오기 변환 단위에서 오버 로드 확인에 대 한 인수 종속 조회를 수행 하는 경우 컴파일러는 함수 인수의 형식이 정의 된 것과 같은 변환 단위 (모듈 인터페이스 포함)에서 선언 된 함수를 고려 합니다.

### <a name="module-partitions"></a>모듈 파티션

> [!NOTE]
> 이 섹션은 완전성을 위해 제공 됩니다. 파티션은 Microsoft c + + 컴파일러에서 아직 구현 되지 않았습니다.

모듈은 각각 인터페이스 파일과 0 개 이상의 구현 파일로 구성 된 *파티션으로*구성 될 수 있습니다. 모듈 파티션은 전체 모듈에 있는 모든 선언의 소유권을 공유 한다는 점을 제외 하 고 모듈과 유사 합니다. 파티션 인터페이스 파일에 의해 내보내지는 모든 이름이 주 인터페이스 파일에 의해 가져와 다시 내보내집니다. 파티션의 이름은 모듈 이름 다음에 콜론으로 시작 해야 합니다. 모든 파티션에 있는 선언은 전체 모듈 내에서 볼 수 있습니다. ODR (단일 정의 규칙) 오류를 방지 하기 위해 특별 한 예방 조치는 필요 하지 않습니다. 한 파티션에서 이름 (함수, 클래스 등)을 선언 하 고 다른 파티션에서 정의할 수 있습니다. 파티션 구현 파일은 다음과 같이 시작 됩니다.

```cpp
module Foo:part1
```

그리고 파티션 인터페이스 파일은 다음과 같이 시작 됩니다.

```cpp
export module Foo:part1
```

다른 파티션의 선언에 액세스 하려면 파티션이 가져와야 합니다. 그러나 모듈 이름이 아니라 파티션 이름만 사용할 수 있습니다.

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

기본 인터페이스 단위는 파티션 구현 파일을 가져올 수 있지만 이러한 파일은 모든 이름을 내보낼 수 없기 때문에 내보낼 수 없습니다. 이를 통해 모듈은 모듈의 내부 구현 세부 정보를 유지할 수 있습니다.

## <a name="modules-and-header-files"></a>모듈 및 헤더 파일

모듈 선언 앞에 지시문을 추가 하 여 모듈 소스 파일에 헤더 파일을 포함할 수 있습니다 `#include` . 이러한 파일은 *전역 모듈 조각*에 있는 것으로 간주 됩니다. 모듈은 명시적으로 포함 된 헤더에 있는 *전역 모듈 조각의* 이름만 볼 수 있습니다. 전역 모듈 조각은 실제로 사용 되는 기호만 포함 합니다.

```cpp
// MyModuleA.cpp

#include "customlib.h"
#include "anotherlib.h"

import std.core;
import MyModuleB;

//... rest of file
```

기존 헤더 파일을 사용 하 여 가져올 모듈을 제어할 수 있습니다.

```cpp
// MyProgram.h
import std.core;
#ifdef DEBUG_LOGGING
import std.filesystem;
#endif
```

### <a name="imported-header-files"></a>가져온 헤더 파일

> [!NOTE]
> 이 섹션은 정보 제공용입니다. 레거시 가져오기는 Microsoft c + + 컴파일러에서 아직 구현 되지 않았습니다.

일부 헤더는 가져오기 키워드를 사용 하 여 **가져올** 수 있는 충분 한 자체 포함 되어 있습니다. 가져온 헤더와 가져온 모듈의 주요 차이점은 헤더의 모든 전처리기 정의가 import 문 바로 뒤의 가져오기 프로그램에 표시 된다는 것입니다. (해당 헤더에 포함 된 모든 파일의 전처리기 정의는 표시 *되지 않습니다* .)

```cpp
import <vector>
import "myheader.h"
```

## <a name="see-also"></a>참고 항목

[모듈, 가져오기, 내보내기](import-export-module.md)
