---
title: __assume
ms.date: 09/02/2019
f1_keywords:
- __assume
- _assume
- __assume_cpp
helpviewer_keywords:
- __assume keyword [C++]
ms.assetid: d8565123-b132-44b1-8235-5a8c8bff85a7
ms.openlocfilehash: 06189405703a7cc34f3bd807ec79612394ee899f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368194"
---
# <a name="__assume"></a>__assume

**마이크로소프트 특정**

최적화 프로그램에 힌트를 전달합니다.

## <a name="syntax"></a>구문

```C
__assume(
   expression
)
```

### <a name="parameters"></a>매개 변수

*식*\
true로 평가된다고 간주되는 식입니다.

## <a name="remarks"></a>설명

최적화 프로그램은 키워드가 표시되는 지점에서 `expression`으로 표시되는 조건이 true이며 변수에 할당하는 등의 작업을 통해 `expression`을 수정할 때까지 true로 유지된다고 가정합니다. `__assume`이 최적화 프로그램에 전달하는 힌트를 적절하게 사용하면 최적화 성능을 개선할 수 있습니다.

모순(항상 false로 평가되는 식)으로 작성되는 `__assume` 문은 항상 `__assume(0)`으로 처리됩니다. 코드가 정상적으로 동작하지 않으면 앞에서 설명한 대로 정의한 `expression`이 유효하며 true인지 확인합니다. 올바른 `__assume(0)` 동작에 대한 자세한 내용은 아래의 설명을 참조하세요.

> [!WARNING]
> 프로그램에서는 연결 가능한 경로에 잘못된 `__assume` 문을 포함하지 않아야 합니다. 컴파일러가 잘못된 `__assume` 문에 연결할 수 있는 경우 프로그램이 예측할 수 없으며 위험할 수 있는 동작을 수행할 수 있습니다.

`__assume`은 올바른 내장 함수가 아니며, 함수로 선언할 필요도 없고 `#pragma intrinsic` 지시문에서 사용할 수도 없습니다. 코드는 생성되지 않지만 최적화 프로그램에서 생성하는 코드가 영향을 받습니다.

assert를 복구할 수 없는 경우에만 `__assume` [ASSERT에서](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 사용합니다. 후속 오류 복구 코드가 있는 어설션에서는 `__assume`을 사용하지 마세요. 이렇게 하면 컴파일러가 오류 처리 코드를 최적화하지 않을 수도 있습니다.

`__assume(0)` 문은 특수한 경우입니다. 연결할 수 없는 코드 경로를 나타내려는 경우 `__assume(0)`을 사용합니다. 다음 예제에서는 `__assume(0)`을 사용하여 스위치 문의 기본 사례에 연결할 수 없음을 나타내는 방법을 보여 줍니다. 여기에는 가장 일반적인 `__assume(0)` 사용 방식이 나와 있습니다.

이전 버전과의 호환성을 위해 컴파일러 옵션 [/Za \(Disable 언어 확장)이](../build/reference/za-ze-disable-language-extensions.md) 지정되지 않는 한 **_assume** **__assume** 동의어입니다.

## <a name="requirements"></a>요구 사항

|Intrinsic|Architecture|
|---------------|------------------|
|`__assume`|x86, ARM, x64, ARM64|

## <a name="example"></a>예제

```cpp
// compiler_intrinsics__assume.cpp
#ifdef DEBUG
# define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__) )
#else
# define ASSERT(e)    ( __assume(e) )
#endif

void func1(int i)
{
}

int main(int p)
{
   switch(p){
      case 1:
         func1(1);
         break;
      case 2:
         func1(-1);
         break;
      default:
         __assume(0);
            // This tells the optimizer that the default
            // cannot be reached. As so, it does not have to generate
            // the extra code to check that 'p' has a value
            // not represented by a case arm. This makes the switch
            // run faster.
   }
}
```

`__assume(0)`을 사용하는 경우 기본 사례에 연결할 수 없음을 최적화 프로그램에 알립니다. 예제에서는 `p`에 사용 가능한 입력이 1이나 2뿐이라는 것을 프로그래머가 알고 있음을 보여 줍니다. `p`에 대해 다른 값이 전달되면 프로그램은 유효하지 않은 상태가 되어 예측할 수 없는 동작을 수행합니다.

`__assume(0)` 문으로 인해 컴파일러는 `p`가 case 문에 표시되지 않는 값을 포함하는지 여부를 테스트하는 코드를 생성하지 않습니다. 이 코드가 작동하도록 하려면 `__assume(0)` 문이 기본 사례 본문의 첫 번째 문이어야 합니다.

컴파일러는 `__assume`을 기반으로 코드를 생성하므로 `__assume` 문 내의 식이 런타임에 false이면 해당 코드가 올바르게 실행되지 않을 수 있습니다. 식이 런타임에 항상 true로 평가될지 확실치 않으면 `assert` 함수를 사용하여 코드를 보호할 수 있습니다.

```C
#define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__)), __assume(e) )
```

그러나 이처럼 `assert`를 사용하면 컴파일러가 이 문서 앞부분에서 설명한 기본 사례 최적화를 수행할 수 없습니다. 따라서 다음과 같이 별도의 매크로를 대신 사용할 수 있습니다.

```C
#ifdef DEBUG
# define NODEFAULT   ASSERT(0)
#else
# define NODEFAULT   __assume(0)
#endif

   default:
      NODEFAULT;
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[컴파일러 내장](../intrinsics/compiler-intrinsics.md)\
[키워드](../cpp/keywords-cpp.md)
