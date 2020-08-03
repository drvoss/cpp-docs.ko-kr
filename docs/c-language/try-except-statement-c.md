---
title: try-except 문 (C)
ms.date: 11/04/2016
helpviewer_keywords:
- try-except keyword [C]
- structured exception handling, try-except
- try-catch keyword [C]
- __try keyword [C]
- __except keyword [C]
- __except keyword [C], in try-except
- try-catch keyword [C], try-except keyword [C]
ms.assetid: f76db9d1-fc78-417f-b71f-18e545fc01c3
ms.openlocfilehash: 77b6bea8c7793522f5e1fa47e09a9b4a7e5c0f10
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218782"
---
# <a name="try-except-statement-c"></a>try-except 문 (C)

**Microsoft 전용**

**try-except** 문은 정상적으로 실행을 종료시키는 이벤트가 발생하는 경우 애플리케이션이 프로그램의 제어를 얻을 수 있도록 하는 C 언어에 대한 Microsoft 확장입니다. 이러한 이벤트를 예외라고 하고 예외를 처리하는 메커니즘은 구조적 예외 처리라고 합니다.

예외는 하드웨어 또는 소프트웨어 기반일 수 있습니다. 애플리케이션을 하드웨어 또는 소프트웨어 예외로부터 완전히 복구할 수 없더라도 구조적 예외 처리를 통해 오류 정보를 표시하고 애플리케이션의 내부 상태를 트래핑하여 문제를 진단하는 데 도움이 되도록 합니다. 이것은 쉽게 재현할 수 없는 간헐적인 문제에 특히 유용합니다.

## <a name="syntax"></a>구문

*try-except-statement*: **__try**  *compound-statement*

**__except (**  *expression*  **)**  *compound-statement*

`__try` 절 뒤의 복합 문은 보호된 섹션입니다. **`__except`** 절 뒤에 오는 복합 문은 예외 처리기입니다. 처리기는 보호된 섹션을 실행하는 동안 예외가 발생하는 경우 수행할 일련의 작업을 지정합니다. 다음과 같이 실행됩니다.

1. 보호된 섹션이 실행됩니다.

1. 보호된 섹션을 실행하는 동안 예외가 발생하지 않는 경우 **`__except`** 절 다음의 문에서 실행이 계속됩니다.

1. 보호된 섹션의 실행 중이나 보호된 섹션에서 호출하는 루틴에서 예외가 발생하는 경우 **`__except`** 식이 계산되고 반환된 값에 따라 예외 처리 방식이 결정됩니다. 다음과 같은 세 가지 값이 있습니다.

   `EXCEPTION_CONTINUE_SEARCH` 예외가 인식되지 않습니다. **try-except** 문을 포함하는 처리기를 먼저 검색한 후, 그 다음으로 우선 순위가 높은 처리기를 검색하는 순으로 처리기 스택을 계속 검색합니다.

   `EXCEPTION_CONTINUE_EXECUTION` 예외가 인식되지만 무시됩니다. 예외가 발생한 지점에서 계속 실행합니다.

   `EXCEPTION_EXECUTE_HANDLER` 예외가 인식됩니다. **`__except`** 복합 문을 실행하여 예외 처리기로 제어를 전달한 다음 실행이 발생한 지점에서 실행을 계속합니다.

**`__except`** 식은 C 식으로 계산되므로 단일 값, 조건식 연산자 또는 쉼표 연산자로 제한됩니다. 더 광범위한 처리가 필요한 경우 식은 위에 나열된 세 값 중 하나를 반환하는 루틴을 호출할 수 있습니다.

> [!NOTE]
> 구조적 예외 처리는 C 및 C++ 소스 파일에서 작동합니다. 특별히 C++용으로 설계되지는 않았습니다. C++ 예외 처리를 사용하여 코드의 이식성이 향상되는지 확인할 수 있습니다. 또한 C++ 예외 처리 메커니즘은 모든 형식의 예외를 처리할 수 있다는 점에서 훨씬 유연합니다.

> [!NOTE]
> C++ 프로그램의 경우 구조적 예외 처리 대신 C++ 예외 처리를 사용해야 합니다. 자세한 내용은 *C++ 언어 참조*의 [예외 처리](../cpp/exception-handling-in-visual-cpp.md)를 참조하세요.

애플리케이션의 각 루틴에는 자체 예외 처리기가 있을 수 있습니다. **`__except`** 식은 `__try` 본문의 범위에서 실행됩니다. 즉, 이 범위에서 선언된 모든 지역 변수에 액세스할 수 있습니다.

**`__leave** keyword is valid within a **try-except** statement block. The effect of **`__leave**는 **try-except** 블록의 끝으로 이동하는 것입니다. 예외 처리기의 끝 다음에 실행이 다시 시작됩니다. **`goto`** 문을 사용하여 동일한 결과를 얻을 수 있지만 **`goto`** 문은 스택 해제를 초래합니다. **`__leave** 문은 스택 해제를 초래하지 않으므로 더 효율적입니다.

`longjmp` 런타임 함수를 사용하여 **try-except** 문을 종료하는 것은 비정상 종료로 간주됩니다. `__try` 문 안으로 이동할 수 없지만 이 문 밖으로 이동할 수는 있습니다. **try-except** 문을 실행하는 도중에 프로세스가 강제로 종료되는 경우 예외 처리기가 호출되지 않습니다.

## <a name="example"></a>예제

다음은 예외 처리기와 종료 처리기의 예제입니다. 종료 처리기에 대한 자세한 내용은 [try-finally 문](../c-language/try-finally-statement-c.md)을 참조하세요.

```
.
.
.
puts("hello");
__try{
   puts("in try");
   __try{
      puts("in try");
      RAISE_AN_EXCEPTION();
   }__finally{
      puts("in finally");
   }
}__except( puts("in filter"), EXCEPTION_EXECUTE_HANDLER ){
   puts("in except");
}
puts("world");
```

다음은 예제에서 출력된 결과이며 오른쪽에 주석이 추가되어 있습니다.

```
hello
in try              /* fall into try                     */
in try              /* fall into nested try                */
in filter           /* execute filter; returns 1 so accept  */
in finally          /* unwind nested finally                */
in except           /* transfer control to selected handler */
world               /* flow out of handler                  */
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[try-except 문](../cpp/try-except-statement.md)
