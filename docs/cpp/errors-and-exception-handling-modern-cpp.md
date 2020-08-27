---
title: 예외 및 오류 처리에 대 한 최신 c + + 모범 사례
description: 최신 c + +에서 오류 코드에 대 한 특수 프로그래밍 스타일을 지 원하는 방법입니다.
ms.date: 08/24/2020
ms.topic: conceptual
ms.assetid: a6c111d0-24f9-4bbb-997d-3db4569761b7
ms.openlocfilehash: b402c93ea5af3cc7dab418b6dea58446ae300c67
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898372"
---
# <a name="modern-c-best-practices-for-exceptions-and-error-handling"></a>예외 및 오류 처리에 대 한 최신 c + + 모범 사례

최신 c + +에서 대부분의 시나리오에서 논리 오류 및 런타임 오류를 보고 하 고 처리 하는 기본 방법은 예외를 사용 하는 것입니다. 오류를 검색 하는 함수 및 오류를 처리 하는 컨텍스트가 있는 함수 간의 함수 호출이 스택에 여러 개 있을 수 있는 경우에 특히 그렇습니다. 예외는 호출 스택에 정보를 전달 하는 오류를 검색 하는 코드에 대 한 공식적인 잘 정의 된 방법을 제공 합니다.

## <a name="use-exceptions-for-exceptional-code"></a>예외 코드에 대 한 예외 사용

프로그램 오류는 프로그래밍 실수 (예: "인덱스가 범위를 벗어남" 오류)로 인해 발생 하는 논리 오류의 두 범주로 구분 됩니다. 프로그래머의 제어를 벗어난 런타임 오류 (예: "네트워크 서비스를 사용할 수 없음" 오류). C 스타일 프로그래밍 및 COM에서 오류 보고는 특정 함수에 대 한 오류 코드 또는 상태 코드를 나타내는 값을 반환 하거나, 모든 함수 호출 후에 호출자가 선택적으로 검색할 수 있는 전역 변수를 설정 하 여 오류가 보고 되었는지 여부를 확인 하는 방식으로 관리 됩니다. 예를 들어 COM 프로그래밍은 HRESULT 반환 값을 사용 하 여 호출자에 게 오류를 전달 합니다. 및 Win32 API에는 `GetLastError` 호출 스택에서 보고 된 마지막 오류를 검색 하는 함수가 있습니다. 이러한 두 경우 모두 호출자가 코드를 인식 하 고 적절 하 게 응답 해야 합니다. 호출자가 오류 코드를 명시적으로 처리 하지 않으면 프로그램에서 경고 없이 충돌이 발생할 수 있습니다. 또는 잘못 된 데이터를 사용 하 여 계속 실행 하 고 잘못 된 결과를 생성할 수 있습니다.

다음 이유 때문에 최신 c + +에서 예외를 선호 합니다.

- 예외는 호출 하는 코드에서 오류 조건을 인식 하 고 처리 하도록 합니다. 처리 되지 않은 예외로 인해 프로그램 실행이 중지 됩니다.

- 예외는 오류를 처리할 수 있는 호출 스택의 지점으로 이동 합니다. 중간 함수를 사용 하 여 예외를 전파할 수 있습니다. 다른 레이어와 조정할 필요가 없습니다.

- 예외 스택 해제 메커니즘은 잘 정의 된 규칙에 따라 예외가 throw 된 후 범위에 있는 모든 개체를 소멸 시킵니다.

- 예외를 사용 하면 오류를 검색 하는 코드와 오류를 처리 하는 코드를 명확 하 게 구분할 수 있습니다.

다음 단순화 된 예제는 c + +에서 예외를 throw 및 catch 하는 데 필요한 구문을 보여 줍니다.

```cpp
#include <stdexcept>
#include <limits>
#include <iostream>

using namespace std;

void MyFunc(int c)
{
    if (c > numeric_limits< char> ::max())
        throw invalid_argument("MyFunc argument too large.");
    //...
}

int main()
{
    try
    {
        MyFunc(256); //cause an exception to throw
    }

    catch (invalid_argument& e)
    {
        cerr << e.what() << endl;
        return -1;
    }
    //...
    return 0;
}
```

C + +의 예외는 c #, Java 등의 언어와 비슷합니다. 블록에서 예외가 **`try`** *throw* 되 면 예외와 일치 하는 형식을 가진 첫 번째 연결 된 블록에 의해 *catch* 됩니다 **`catch`** . 즉, 실행은 **`throw`** 문에서 **`catch`** 문으로 이동 합니다. 사용할 수 있는 catch 블록이 없으면 `std::terminate` 이 호출 되 고 프로그램이 종료 됩니다. C + +에서 모든 형식이 throw 될 수 있습니다. 그러나에서 직접 또는 간접적으로 파생 되는 형식을 throw 하는 것이 좋습니다 `std::exception` . 이전 예제에서 예외 형식는 [`invalid_argument`](../standard-library/invalid-argument-class.md) 헤더 파일의 표준 라이브러리에 정의 되어 [`<stdexcept>`](../standard-library/stdexcept.md) 있습니다. C + +에서는 **`finally`** 예외가 throw 되는 경우 모든 리소스가 해제 되도록 블록을 제공 하거나 요구 하지 않습니다. 스마트 포인터를 사용 하는 RAII (리소스 획득) 초기화는 리소스 정리에 필요한 기능을 제공 합니다. 자세한 내용은 [방법: 예외 안전성을 위한 디자인](how-to-design-for-exception-safety.md)을 참조 하세요. C + + 스택 해제 메커니즘에 대 한 자세한 내용은 [예외 및 스택](exceptions-and-stack-unwinding-in-cpp.md)해제를 참조 하세요.

## <a name="basic-guidelines"></a>기본 지침

강력한 오류 처리는 모든 프로그래밍 언어에서 어렵습니다. 예외는 적절 한 오류 처리를 지 원하는 여러 기능을 제공 하지만 모든 작업을 수행할 수는 없습니다. 예외 메커니즘의 이점을 실현 하려면 코드를 디자인할 때 예외를 염두에 두어야 합니다.

- Assert를 사용 하 여 발생 하지 않아야 하는 오류를 확인 합니다. 예외를 사용 하 여 발생할 수 있는 오류를 확인 합니다 (예: 공용 함수의 매개 변수에 대 한 입력 유효성 검사 오류). 자세한 내용은 [예외 및 어설션](#exceptions_versus_assertions) 단원을 참조 하세요.

- 오류를 처리 하는 코드가 하나 이상의 중간 함수 호출로 오류를 검색 하는 코드와 분리 된 경우 예외를 사용 합니다. 오류를 처리 하는 코드가이를 검색 하는 코드와 긴밀 하 게 연결 되는 경우 성능에 중요 한 루프에 대신 오류 코드를 사용할지 여부를 고려 합니다.

- 예외를 throw 하거나 전파 하는 모든 함수에 대해, 강력한 보장, 기본 보장 또는 nothrow (noexcept) 보장의 세 가지 예외 보장 중 하나를 제공 합니다. 자세한 내용은 [방법: 예외 안전성을 위한 디자인](how-to-design-for-exception-safety.md)을 참조 하세요.

- 값으로 예외를 Throw 하 고 참조로 catch 합니다. 처리할 수 없는 항목은 catch 하지 마세요.

- C + + 11에서 사용 되지 않는 예외 사양을 사용 하지 마세요. 자세한 내용은 [예외 사양 및 `noexcept` ](#exception_specifications_and_noexcept) 섹션을 참조 하세요.

- 적용 될 때 표준 라이브러리 예외 유형을 사용 합니다. [ `exception` 클래스](../standard-library/exception-class.md) 계층 구조에서 사용자 지정 예외 형식을 파생 시킵니다.

- 소멸자 또는 메모리 할당 취소 함수에서 예외를 이스케이프 하는 것을 허용 하지 않습니다.

## <a name="exceptions-and-performance"></a>예외 및 성능

예외가 throw 되지 않는 경우 예외 메커니즘에는 최소한의 성능 비용이 있습니다. 예외가 throw 되 면 스택 순회 및 해제 비용이 함수 호출 비용과 거의 비슷합니다. 블록을 입력 한 후 호출 스택을 추적 하려면 추가 데이터 구조가 필요 **`try`** 하며, 예외가 throw 되는 경우 스택을 해제 하려면 추가 지침이 필요 합니다. 그러나 대부분의 시나리오에서 성능 및 메모리 공간의 비용은 중요 하지 않습니다. 성능에 대 한 예외의 부작용은 메모리 제한 시스템에만 중요 한 영향을 미칠 수 있습니다. 또는 성능이 중요 한 루프에서 오류가 정기적으로 발생 하 고이를 처리 하는 코드와이를 보고 하는 코드 간에 긴밀 하 게 결합 됩니다. 어떤 경우 든, 프로 파일링 및 측정 없이 예외의 실제 비용을 알 수 없습니다. 드문 경우 지만 비용이 중요 한 경우에도 잘 설계 된 예외 정책에서 제공 하는 향상 된 정확성, 쉬운 관리 용이성 및 기타 이점에 대해이를 비교할 수 있습니다.

## <a name="exceptions-versus-assertions"></a><a name="exceptions_versus_assertions"></a> 예외 및 어설션

예외와 어설션은 프로그램에서 런타임 오류를 검색 하는 두 가지 고유한 메커니즘입니다. 문을 사용 하 여 `assert` 개발 중에 조건을 테스트할 경우 모든 코드가 올바르면 true가 되어서는 안 됩니다. 예외를 사용 하 여 이러한 오류를 처리할 필요가 없습니다. 오류는 코드에서 수정 해야 하는 항목이 있음을 나타냅니다. 프로그램이 런타임에 복구 해야 하는 조건을 나타내지는 않습니다. 는 `assert` 디버거에서 프로그램 상태를 검사할 수 있도록 문에서 실행을 중지 합니다. 예외는 첫 번째 적절 한 catch 처리기에서 실행을 계속 합니다. 코드가 올바른 경우에도 (예: "파일을 찾을 수 없음" 또는 "메모리가 부족 합니다.") 예외를 사용 하 여 런타임 시 발생할 수 있는 오류 조건을 확인 합니다. 복구에서 로그에 메시지를 출력 하 고 프로그램을 종료 하는 경우에도 예외는 이러한 조건을 처리할 수 있습니다. 예외를 사용 하 여 항상 public 함수에 대 한 인수를 확인 합니다. 함수에 오류가 없는 경우에도 사용자가 함수에 전달할 수 있는 인수에 대 한 완전 한 제어 권한이 없을 수 있습니다.

## <a name="c-exceptions-versus-windows-seh-exceptions"></a>C + + 예외 및 Windows SEH 예외

C 및 c + + 프로그램은 Windows 운영 체제에서 SEH (구조적 예외 처리) 메커니즘을 사용할 수 있습니다. Seh의 개념은 c + + 예외의 경우와 유사 합니다. 단, SEH **`__try`** 는 **`__except`** 및 대신, 및 구문을 사용 합니다 **`__finally`** **`try`** **`catch`** . Microsoft c + + 컴파일러 (MSVC)에서 c + + 예외는 SEH에 대해 구현 됩니다. 그러나 c + + 코드를 작성 하는 경우 c + + 예외 구문을 사용 합니다.

SEH에 대 한 자세한 내용은 [구조적 예외 처리 (C/c + +)](structured-exception-handling-c-cpp.md)를 참조 하세요.

## <a name="exception-specifications-and-noexcept"></a><a name="exception_specifications_and_noexcept"></a> 예외 사양 및 `noexcept`

예외 사양은 함수에서 throw 될 수 있는 예외를 지정 하는 방법으로 c + +에서 도입 되었습니다. 그러나 예외 사양은 실제로 문제를 증명 하 고 c + + 11 초안 표준에서 더 이상 사용 되지 않습니다. 을 제외 하 고 예외 사양을 사용 하지 않는 것이 좋습니다 .이는 **`throw`** `throw()` 함수에서 이스케이프할 예외를 허용 하지 않음을 나타냅니다. 사용 되지 않는 형식의 예외 사양을 사용 해야 하는 경우 `throw( type-name )` MSVC 지원이 제한 됩니다. 자세한 내용은 [예외 사양 (throw)](exception-specifications-throw-cpp.md)을 참조 하세요. **`noexcept`** 이 지정자는 대신 c + + 11에 도입 되었습니다 `throw()` .

## <a name="see-also"></a>참조

[방법: 예외 코드와 비 예외 코드 간 인터페이스](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)<br/>
[C + + 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C + + 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)
