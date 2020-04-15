---
title: 최적화에 유용한 정보
ms.date: 05/06/2019
helpviewer_keywords:
- C++, optimization
- optimization, best practices
ms.assetid: f3433148-7255-4ca6-8a4f-7c31aac88508
ms.openlocfilehash: 541114b4cbf7d3d063e48b50ab265b4c95c6237c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328448"
---
# <a name="optimization-best-practices"></a>최적화에 유용한 정보

이 문서에서는 Visual Studio에서 C++ 프로그램을 최적화하기 위한 몇 가지 모범 사례를 설명합니다.

## <a name="compiler-and-linker-options"></a>컴파일러 및 링커 옵션

### <a name="profile-guided-optimization"></a>프로파일 기반 최적화

Visual Studio는 프로파일 기반 최적화(PGO)를 지원합니다. *profile-guided optimization* 이 최적화는 계측된 버전의 응용 프로그램의 교육 실행에서 얻은 프로필 데이터를 사용하여 나중에 응용 프로그램의 최적화를 유도합니다. PGO를 사용하는 것은 시간이 오래 걸릴 수 있으므로 모든 개발자가 사용하는 것은 아니지만 제품의 최종 릴리스 빌드에 PGO를 사용하는 것이 좋습니다. 자세한 내용은 [프로필 기반 최적화](profile-guided-optimizations.md)를 참조하세요.

또한 *전체 프로그램 최적화(링크* 시간 코드 생성으로도 도있음)와 **/O1** 및 **/O2** 최적화가 개선되었습니다. 일반적으로 이러한 옵션 중 하나로 컴파일된 응용 프로그램은 이전 컴파일러로 컴파일된 응용 프로그램보다 빠릅니다.

자세한 내용은 [/GL(전체 프로그램 최적화)](reference/gl-whole-program-optimization.md) 및 [/O1, /O2(크기 최소화, 속도 최대화)를](reference/o1-o2-minimize-size-maximize-speed.md)참조하십시오.

### <a name="which-level-of-optimization-to-use"></a>사용할 최적화 수준

가능한 경우 최종 릴리스 빌드는 프로필 안내 최적화를 통해 컴파일해야 합니다. 계측된 빌드를 실행하기 위한 인프라가 부족하거나 시나리오에 액세스할 수 없는 경우 PGO로 빌드할 수 없는 경우 전체 프로그램 최적화를 사용하여 빌드하는 것이 좋습니다.

**/Gy** 스위치도 매우 유용합니다. 각 기능에 대해 별도의 COMDAT를 생성하여 참조되지 않은 COMDAT 및 COMDAT 폴딩을 제거할 때 링커에 더 많은 유연성을 제공합니다. **/Gy를** 사용하는 유일한 단점은 디버깅 할 때 문제가 발생할 수 있다는 것입니다. 따라서 일반적으로 사용하는 것이 좋습니다. 자세한 내용은 [/Gy(함수 수준 링크 사용)](reference/gy-enable-function-level-linking.md)를 참조하세요.

64비트 환경에서 연결하는 경우 **/OPT:REF, ICF** 링커 옵션을 사용하는 것이 좋습니다. **/OPT:REF** 자세한 내용은 [/OPT(최적화)를](reference/opt-optimizations.md)참조하십시오.

또한 최적화된 릴리스 빌드에서도 디버그 기호를 생성하는 것이 좋습니다. 생성된 코드에는 영향을 주지 않으며 필요한 경우 응용 프로그램을 디버깅하기가 훨씬 쉬워집니다.

### <a name="floating-point-switches"></a>플로팅 포인트 스위치

**/Op** 컴파일러 옵션이 제거되었으며 부동 포인트 최적화를 처리하는 다음 네 가지 컴파일러 옵션이 추가되었습니다.

|||
|-|-|
|**/fp:정밀**|기본 권장 사항이며 대부분의 경우 사용해야 합니다.|
|**/fp:빠릅니다.**|예를 들어 게임에서 성능이 가장 중요한 경우 권장됩니다. 이렇게 하면 성능이 가장 빠릅니다.|
|**/fp:엄격한**|정확한 부동 점 예외 및 IEEE 동작이 필요한 경우 권장됩니다. 이렇게 하면 성능이 가장 느립니다.|
|**/fp:[-] 제외**|**/fp:strict** 또는 **/fp:-정확한/fp:fast와** **/fp:fast**함께 사용할 수 있습니다.|

자세한 내용은 [/fp(부동 소수점 동작 지정)](reference/fp-specify-floating-point-behavior.md)를 참조하세요.

## <a name="optimization-declspecs"></a>최적화 디클루시프

이 섹션에서는 성능 `__declspec(restrict)` 에 도움이 되는 프로그램에서 사용할 수 있는 두 `__declspec(noalias)`가지 디클루스를 살펴보겠습니다.

declspec은 `restrict` 포인터를 반환하는 함수 선언에만 적용할 수 있습니다.`__declspec(restrict) void *malloc(size_t size);`

`restrict` declspec은 aliased 포인터를 반환하는 함수에 사용됩니다. 이 키워드는 현재 프로그램에서 이미 사용 중인 `malloc` 포인터 값을 반환하지 않으므로 C-런타임 라이브러리 구현에 사용됩니다(해제된 후 메모리 사용과 같이 불법적인 작업을 수행하지 않는 한).

declspec은 `restrict` 컴파일러 최적화를 수행하기 위한 추가 정보를 컴파일러에 제공합니다. 컴파일러가 결정하기 가장 어려운 것 중 하나는 다른 포인터를 별칭으로 하는 포인터이며 이 정보를 사용하면 컴파일러에 큰 도움이 됩니다.

이것은 컴파일러가 확인할 것이 아니라 컴파일러에 대한 약속이라는 점을 지적할 필요가 있습니다. 프로그램에서 이 `restrict` 디클루스를 부적절하게 사용하는 경우 프로그램에서 잘못된 동작이 있을 수 있습니다.

자세한 내용은 [제한](../cpp/restrict.md)을 참조하십시오.

`noalias` declspec은 함수에만 적용되며 함수가 반순수 함수임을 나타냅니다. 반순수 함수는 인수의 지역 주민, 인수 및 첫 번째 수준 indirections만 참조하거나 수정하는 함수입니다. 이 디클루펙은 컴파일러에 대한 약속이며 함수가 전역 또는 포인터 인수의 두 번째 수준 간접을 참조하는 경우 컴파일러는 응용 프로그램을 중단하는 코드를 생성할 수 있습니다.

자세한 내용은 [noalias](../cpp/noalias.md)를 참조하세요.

## <a name="optimization-pragmas"></a>최적화 실용성

코드를 최적화하는 데 도움이 되는 몇 가지 유용한 pragmas도 있습니다. 우리가 논의 할 첫 `#pragma optimize`번째 는 다음과 있습니다.

```cpp
#pragma optimize("{opt-list}", on | off)
```

이 pragma를 사용하면 함수별로 지정된 최적화 수준을 설정할 수 있습니다. 이는 지정된 함수를 최적화로 컴파일할 때 응용 프로그램이 충돌하는 드문 경우에 이상적입니다. 단일 함수에 대한 최적화를 해제하는 데 사용할 수 있습니다.

```cpp
#pragma optimize("", off)
int myFunc() {...}
#pragma optimize("", on)
```

자세한 내용은 [최적화](../preprocessor/optimize.md)를 참조하십시오.

인라이닝은 컴파일러가 수행하는 가장 중요한 최적화 중 하나이며 여기에서는 이 동작을 수정하는 데 도움이 되는 몇 가지 pragmas에 대해 설명합니다.

`#pragma inline_recursion`은 응용 프로그램이 재귀 호출을 인라인으로 지정할 지 여부를 지정하는 데 유용합니다. 기본적으로 꺼져 있습니다. 작은 함수의 얕은 재귀의 경우 이 기능을 켤 수 있습니다. 자세한 내용은 [inline_recursion](../preprocessor/inline-recursion.md)을 참조하십시오.

인라이닝의 깊이를 제한하는 또 다른 `#pragma inline_depth`유용한 실용은 . 일반적으로 프로그램 또는 함수의 크기를 제한하려는 경우에 유용합니다. 자세한 내용은 [inline_depth](../preprocessor/inline-depth.md)를 참조하십시오.

## <a name="__restrict-and-__assume"></a>__restrict \_및 _assume

Visual Studio에는 [성능에](../cpp/extension-restrict.md) 도움이 되는 몇 가지 키워드가 있습니다: __restrict 및 [__assume](../intrinsics/assume.md).

첫째, `__restrict` 주목해야하며 `__declspec(restrict)` 두 가지 다른 것입니다. 그들은 다소 관련이 있지만, 그들의 의미는 다르다. `__restrict`는 형식 한정자, `volatile`또는 `const` 에 대해서만 포인터 형식에 만 사용할 수 있습니다.

수정된 `__restrict` 포인터를 *__restrict 포인터라고*합니다. __restrict 포인터는 _restrict 포인터를 통해서만 액세스할 \_수 있는 포인터입니다. 즉, \_다른 포인터를 사용하여 _restrict 포인터가 가리키는 데이터에 액세스할 수 없습니다.

`__restrict`Microsoft C++ 최적화 프로그램에 대한 강력한 도구가 될 수 있지만 세심한 주의를 기울여 사용할 수 있습니다. 잘못 사용하면 최적화 프로그램이 응용 프로그램을 중단하는 최적화를 수행할 수 있습니다.

키워드는 `__restrict` 이전 버전에서 **/Oa** 스위치를 대체합니다.

를 `__assume`사용하여 개발자는 컴파일러에게 일부 변수의 값에 대해 가정하도록 지시할 수 있습니다.

예를 `__assume(a < 5);` 들어 최적화 프로그램은 해당 코드 줄에서 `a` 변수가 5보다 적다는 것을 알려줍니다. 다시 이것은 컴파일러에 대한 약속입니다. 실제로 `a` 프로그램의 이 시점에서 6이면 컴파일러가 최적화 된 후 프로그램의 동작이 예상과 다를 수 있습니다. `__assume`은 명령문 및/또는 조건식 을 전환하기 전에 가장 유용합니다.

`__assume`에 몇 가지 제한 사항이 있습니다. 첫째, `__restrict`처럼 그것은 단지 제안, 그래서 컴파일러는 그것을 무시 하 고 무료. 또한 `__assume` 현재상수에 대한 변수 부등분만 작동합니다. 예를 들어 가정(< b)과 같은 기호 부등가를 전파하지 않습니다.

## <a name="intrinsic-support"></a>본질적인 지원

본질적인 함수는 컴파일러가 호출에 대한 본질적인 지식을 가지고 있는 함수 호출이며 라이브러리에서 함수를 호출하는 대신 해당 함수에 대한 코드를 내보릅니다. 헤더 파일 \<intrin.h> 지원 되는 각 하드웨어 플랫폼에 대 한 사용 가능한 모든 내장.

내장 함수는 프로그래머가 어셈블리를 사용하지 않고도 코드를 심층으로 진행할 수 있는 기능을 제공합니다. 내장 함수를 사용하면 다음과 같은 몇 가지 이점이 있습니다.

- 코드의 이식성이 더 높습니다. 여러 가지 내장 함수는 여러 CPU 아키텍처에서 사용할 수 있습니다.

- 코드는 여전히 C/C++로 작성되므로 코드를 읽기가 더 쉽습니다.

- 코드는 컴파일러 최적화의 이점을 얻습니다. 컴파일러가 향상되면 내장 함수에 대한 코드 생성이 향상됩니다.

자세한 내용은 [컴파일러 내장 함수를](../intrinsics/compiler-intrinsics.md)참조하십시오.

## <a name="exceptions"></a>예외

예외를 사용하는 것과 관련된 성능 저하가 있습니다. 컴파일러가 특정 최적화를 수행하지 못하도록 하는 try 블록을 사용할 때 몇 가지 제한 사항이 도입됩니다. x86 플랫폼에서는 코드 실행 중에 생성해야 하는 추가 상태 정보로 인해 try 블록에서 추가 성능 저하가 발생합니다. 64비트 플랫폼에서 시도 블록은 성능이 크게 저하되지 않지만 예외가 throw되면 처리기를 찾고 스택을 해제하는 프로세스가 비용이 많이 들 수 있습니다.

따라서 try/catch 블록이 실제로 필요하지 않은 코드에 도입되지 않도록 하는 것이 좋습니다. 예외를 사용해야 하는 경우 가능하면 동기 예외를 사용합니다. 자세한 내용은 [Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)을 참조하세요.

마지막으로 예외적인 경우에만 예외를 throw합니다. 일반 제어 흐름에 예외를 사용하면 성능이 저하될 수 있습니다.

## <a name="see-also"></a>참고 항목

- [코드 최적화](optimizing-your-code.md)
