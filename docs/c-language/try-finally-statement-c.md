---
title: try-finally 문 (C)
ms.date: 11/04/2016
helpviewer_keywords:
- try-finally keyword [C]
- __finally keyword [C], try-finally statement syntax
- __finally keyword [C]
- structured exception handling, try-finally
ms.assetid: 514400c1-c322-4bf3-9e48-3047240b8a82
ms.openlocfilehash: 61a6a9edd9faaf8afb06bb7bfdc619cddde3e6fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349608"
---
# <a name="try-finally-statement-c"></a>try-finally 문 (C)

**Microsoft 전용**

`try-finally` 문은 코드 블록 실행이 중단될 때 애플리케이션에서 정리 코드가 실행되도록 보장하는 C 언어에 대한 Microsoft 확장입니다. 정리는 메모리 할당 해제, 파일 닫기 및 파일 핸들 해제와 같은 작업으로 구성됩니다. `try-finally` 문은 루틴으로부터 중간에 반환되게 만들 수 있는 오류가 있는지 확인하기 위해 검사가 수행되는 위치가 많은 루틴에 특히 유용합니다.

*try-finally-statement*: **__try**  *compound-statement*

**__finally**  *compound-statement*

`__try` 절 뒤의 복합 문은 보호된 섹션입니다. `__finally` 절 뒤의 복합 문은 종료 처리기입니다. 처리기는 보호된 섹션이 예외(비정상적 종료)로 인해 종료되었는지, 아니면 표준 제어 이동(정상적 종료)으로 인해 종료되었는지에 관계없이 가드되는 섹션이 종료될 때 실행되는 작업 집합을 지정합니다.

제어는 단순한 순차적 실행(제어 이동)에 의해 `__try` 문에 도달합니다. 제어가 `__try` 문에 들어가면 연결된 처리기가 활성화됩니다. 다음과 같이 실행됩니다.

1. 보호된 섹션이 실행됩니다.

1. 종료 처리기가 호출됩니다.

1. 종료 처리기가 완료되면 실행이 `__finally` 문 후에 계속됩니다. 보호된 섹션이 끝나는 방법(예: 보호된 본문 밖의 `goto` 문 또는 `return` 문을 통해)에 관계없이 제어 흐름이 보호된 섹션 밖으로 이동하기 전에 종료 처리기가 실행됩니다.

`__leave` 키워드는 `try-finally` 문 블록 내에서 유효합니다. `__leave`는 `try-finally` 블록의 끝으로 이동하는 효과가 있습니다. 종료 처리기는 즉시 실행됩니다. `goto` 문을 사용하여 동일한 결과를 얻을 수 있지만 `goto` 문은 스택 해제를 초래합니다. `__leave` 문은 스택 해제를 초래하지 않으므로 더 효율적입니다.

`try-finally` 문 또는 `return` 런타임 함수를 사용하여 `longjmp` 문을 종료하는 것은 비정상적 종료로 간주됩니다. `__try` 문 안으로 이동할 수 없지만 이 문 밖으로 이동할 수는 있습니다. 출발 지점과 도착 지점 간에 활성화된 모든 `__finally` 문이 실행되어야 합니다. 이것을 "로컬 해제"라고 합니다.

`try-finally` 문을 실행하는 동안 프로세스가 종료될 경우에는 종료 처리기가 호출되지 않습니다.

> [!NOTE]
> 구조적 예외 처리는 C 및 C++ 소스 파일에서 작동합니다. 특별히 C++용으로 설계되지는 않았습니다. C++ 예외 처리를 사용하여 코드의 이식성이 향상되는지 확인할 수 있습니다. 또한 C++ 예외 처리 메커니즘은 모든 형식의 예외를 처리할 수 있다는 점에서 훨씬 유연합니다.

> [!NOTE]
> C++ 프로그램의 경우 구조적 예외 처리 대신 C++ 예외 처리를 사용해야 합니다. 자세한 내용은 *C++ 언어 참조*의 [예외 처리](../cpp/exception-handling-in-visual-cpp.md)를 참조하세요.

`try-finally` 문이 작동하는 방법을 보려면 [try-except 문](../c-language/try-except-statement-c.md)의 예제를 참조하세요.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[try-finally 문](../cpp/try-finally-statement.md)
