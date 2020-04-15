---
title: 문자열 및 I/O 서식 지정(최신 C++)
description: 형식이 지정된 문자열 I/O에 대한 선택 사항은 최신 C++에서 사용할 수 있습니다.
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: a3fc93b0baf414759eb50c787c4057fb85dcb370
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375781"
---
# <a name="string-and-io-formatting-modern-c"></a>문자열 및 I/O 서식 지정(최신 C++)

C++ [ \<iostream>](../standard-library/iostream.md) 클래스, 함수 및 연산자는 형식이 지정된 문자열 I/O를 지원합니다. 예를 들어 다음 코드는 헥사데피만에서 출력하도록 정수의 서식을 지정하도록 설정하는 `cout` 방법을 보여 주며 있습니다. 첫째, 형식 상태가 전달되면 변경될 때까지 그대로 유지되므로 나중에 `cout`다시 설정하기 위해 현재 상태를 저장합니다. 한 줄의 코드에만 적용되는 것은 아닙니다.

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main()
{
    ios state(nullptr);

    cout << "The answer in decimal is: " << 42 << endl;

    state.copyfmt(cout); // save current formatting
    cout << "In hex: 0x" // now load up a bunch of formatting modifiers
        << hex
        << uppercase
        << setw(8)
        << setfill('0')
        << 42            // the actual value we wanted to print out
        << endl;
    cout.copyfmt(state); // restore previous formatting
}
```

이 방법은 형식안전과 확장이 가능하지만 복잡하고 자세한 내용이기도 합니다.

## <a name="alternative-format-options"></a>대체 형식 옵션

또는 표준이 아니더라도 `Boost.Format` Boost C++ 라이브러리에서 사용할 수 있습니다. [부스트](https://www.boost.org/) 웹사이트에서 모든 부스트 라이브러리를 다운로드할 수 있습니다.

몇 가지 `Boost.Format` 장점은 다음과 같습니다.

- 안전: 형식 안전하며 오류(예: 너무 적거나 너무 많은 항목의 사양)에 대한 예외를 throw합니다.

- 확장 가능: 스트리밍할 수 있는 모든 형식에 대해 작동합니다.

- 편리함: 표준 POSIX 및 유사한 형식 문자열.

안전하고 확장 가능한 C++ `Boost.Format` [ \<iostream>](../standard-library/iostream-programming.md) 시설에 구축되었지만 성능에 최적화되지 는 않습니다. 성능 최적화가 필요한 경우 빠르고 사용하기 쉬운 C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 및 [sprintf를](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)고려하십시오. 그러나 취약점으로부터 확장가능하거나 안전하지는 않습니다. (안전 버전이 존재하지만 약간의 성능 저하가 발생합니다. 자세한 내용은 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) 및 [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l)을](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)참조하십시오.

다음 코드는 일부 부스트 서식 지정 기능을 보여 줍니다.

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>참고 항목

[C++에 다시 오신 것을 환영합니다.](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream>](../standard-library/iostream.md)<br/>
[\<제한>](../standard-library/limits.md)<br/>
[\<요오만>](../standard-library/iomanip.md)
