---
title: 열거형(C++/CX)
ms.date: 12/30/2016
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
ms.openlocfilehash: be11d8d8f38a92fbe4be00eed53dd5226bab0b59
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821755"
---
# <a name="enums-ccx"></a>열거형(C++/CX)

C++/CX는 표준 C++ `scoped  enum`와 유사한 `public enum class` 키워드를 지원 합니다. `public enum class` 키워드를 사용하여 선언된 열거자를 사용할 경우 열거형 식별자를 사용하여 각 열거자 값의 범위를 지정해야 합니다.

### <a name="remarks"></a>주의

`public enum class` 과 같은 액세스 지정자가 없는 `public`는 표준 C++ [범위 지정 열거형](../cpp/enumerations-cpp.md)으로 처리됩니다.

`public enum class` 또는 `public enum struct` 선언에는 모든 정수 형식의 기본 형식이 있을 수 있습니다. 단, Windows 런타임 자체에는 해당 형식이 int32 또는 uint32 인 경우에는 플래그 열거형의 경우 uint32입니다. 다음 구문에서는 `public enum class` 또는 `public enum struct`부분을 설명합니다.

이 예제에서는 public enum 클래스를 정의하는 방법을 보여 줍니다.

[!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]

다음 예제에서는 클래스를 사용하는 방법을 보여 줍니다.

[!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]

### <a name="examples"></a>예

다음 예제에서는 열거형을 선언하는 방법을 보여 줍니다.

[!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]

다음 예제에서는 해당 숫자로 캐스팅하고 비교를 수행하는 방법을 보여 줍니다. 열거자 `One` 의 사용은 `Enum1` 열거형 식별자로 범위가 지정되고, 열거자 `First` 는 `Enum2`로 범위가 지정됩니다.

[!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]

## <a name="see-also"></a>참조

[형식 시스템](../cppcx/type-system-c-cx.md)<br/>
[C++/CX 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)
