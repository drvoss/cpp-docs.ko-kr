---
title: 컴파일러 경고(수준 3) C4996
description: 컴파일러 경고가 발생 하는 이유를 설명 하 고이에 대해 수행할 작업을 설명 합니다.
ms.date: 11/25/2019
f1_keywords:
- C4996
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
ms.openlocfilehash: 98662dc0b5439c1f8857e4f2ad259793a4d03e41
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "79425042"
---
# <a name="compiler-warning-level-3-c4996"></a>컴파일러 경고(수준 3) C4996

코드에서 사용 *되지*않는 것으로 표시 된 함수, 클래스 멤버, 변수 또는 typedef를 사용 합니다. 기호는 [__declspec (사용 되지 않음)](../../cpp/deprecated-cpp.md) 한정자 또는 c + + 14 [ \[ \[ 사용 되지 않는 \] \] ](../../cpp/attributes.md) 특성을 사용 하 여 사용 되지 않습니다. 실제 C4996 경고 메시지는 `deprecated` 선언의 한정자 또는 특성에 의해 지정 됩니다.

> [!IMPORTANT]
> 이 경고는 항상 기호를 선언 하는 헤더 파일의 작성자 로부터 의도적으로 발생 하는 메시지입니다. 결과를 이해 하지 않고 사용 되지 않는 기호를 사용 하지 마세요.

## <a name="remarks"></a>설명

Visual Studio 라이브러리의 여러 함수, 멤버 함수, 템플릿 함수 및 전역 변수는 *더 이상 사용 되지*않습니다. POSIX 및 Microsoft 전용 함수와 같은 일부는 이제 다른 기본 설정 이름을 사용 하기 때문에 사용 되지 않습니다. 일부 C 런타임 라이브러리 함수는 안전 하지 않으며 변형이 더 안전 하기 때문에 더 이상 사용 되지 않습니다. 다른 항목은 사용 되지 않으므로 더 이상 사용 되지 않습니다. 사용 중단 메시지에는 일반적으로 사용 되지 않는 함수 또는 전역 변수에 대해 제안 되는 대체가 포함 됩니다.

## <a name="turn-off-the-warning"></a>경고 해제

C4996 문제를 해결 하려면 일반적으로 코드를 변경 하는 것이 좋습니다. 대신 제안 된 함수 및 전역 변수를 사용 합니다. 이식성 이유로 기존 함수나 변수를 사용 해야 하는 경우 경고를 해제할 수 있습니다.

특정 코드 줄에 대 한 경고를 해제 하려면 [경고](../../preprocessor/warning.md) pragma를 사용 `#pragma warning(suppress : 4996)` 합니다.

파일 내에서 경고를 해제 하려면 경고 pragma를 사용 `#pragma warning(disable : 4996)` 합니다.

명령줄 빌드에서 경고를 전역적으로 해제 하려면 [/wd4996](../../build/reference/compiler-option-warning-level.md) 명령줄 옵션을 사용 합니다.

Visual Studio IDE에서 전체 프로젝트에 대 한 경고를 해제 하려면 다음을 수행 합니다.

1. 프로젝트에 대 한 **속성 페이지** 대화 상자를 엽니다. 속성 페이지 대화 상자를 사용 하는 방법에 대 한 자세한 내용은 [속성 페이지](../../build/reference/property-pages-visual-cpp.md)를 참조 하세요.

1. **구성 속성**  >  **C/c + +**  >  **고급** 페이지를 선택 합니다.

1. **특정 경고 사용 안 함** 속성을 편집 하 여 추가 `4996` 합니다. **확인** 을 선택 하 여 변경 내용을 적용 합니다.

전처리기 매크로를 사용 하 여 라이브러리에서 사용 되는 사용 중단 경고의 특정 클래스를 해제할 수도 있습니다. 이러한 매크로는 아래에 설명 되어 있습니다.

Visual Studio에서 전처리기 매크로를 정의 하려면 다음을 수행 합니다.

1. 프로젝트에 대 한 **속성 페이지** 대화 상자를 엽니다. 속성 페이지 대화 상자를 사용 하는 방법에 대 한 자세한 내용은 [속성 페이지](../../build/reference/property-pages-visual-cpp.md)를 참조 하세요.

1. **구성 속성 > C/c + + > 전처리기**를 확장 합니다.

1. **전처리기 정의** 속성에서 매크로 이름을 추가 합니다. **확인** 을 선택하여 저장한 다음 프로젝트를 다시 빌드합니다.

특정 소스 파일에만 매크로를 정의 하려면 `#define EXAMPLE_MACRO_NAME` 헤더 파일이 포함 된 줄 앞에와 같은 줄을 추가 합니다.

다음은 C4996 경고 및 오류의 일반적인 원인입니다.

## <a name="posix-function-names"></a>POSIX 함수 이름

**이 항목에 대 한 POSIX 이름은 사용 되지 않습니다. 대신 ISO C 및 c + +와 호환 되는 이름 (** *새 이름)* 을 사용 합니다. **자세한 내용은 온라인 도움말을 참조 하십시오.**

Microsoft는 예약 및 전역 구현 정의 이름에 대 한 C99 및 c + + 03 제약 조건을 준수 하도록 CRT에서 일부 POSIX 및 Microsoft 관련 라이브러리 함수 이름을 바꿨습니다. *이름만 사용 되 고 함수 자체는 사용*되지 않습니다. 대부분의 경우 일치 하는 이름을 만들기 위해 함수 이름에 선행 밑줄이 추가 되었습니다. 컴파일러는 원래 함수 이름에 대해 사용 중단 경고를 발생 하 고 기본 설정 이름을 제안 합니다.

이 문제를 해결 하려면 일반적으로 제안 된 함수 이름을 사용 하도록 코드를 변경 하는 것이 좋습니다. 그러나 업데이트 된 이름은 Microsoft 전용입니다. 이식성 이유로 기존 함수 이름을 사용 해야 하는 경우 이러한 경고를 해제할 수 있습니다. 함수는 라이브러리에서 원래 이름으로 계속 사용할 수 있습니다.

이러한 함수에 대 한 사용 중단 경고를 해제 하려면 전처리기 매크로 ** \_ CRT \_ NONSTDC \_ \_ 경고 없음**을 정의 합니다. 옵션을 포함 하 여 명령줄에서이 매크로를 정의할 수 있습니다 `/D_CRT_NONSTDC_NO_WARNINGS` .

## <a name="unsafe-crt-library-functions"></a>Unsafe CRT 라이브러리 함수

**이 함수 또는 변수는 안전 하지 않을 수 있습니다. **대신 *safe 버전* 을 사용 하십시오 **. 사용 중단을 사용 하지 않도록 설정 하려면 \_ CRT \_ 보안 \_ 경고 없음을 사용 \_ 합니다.  자세한 내용은 온라인 도움말을 참조 하십시오.**

Microsoft는 더 안전한 버전을 사용할 수 있기 때문에 일부 CRT 및 c + + 표준 라이브러리 함수 및 전역을 사용 하지 않습니다. 더 이상 사용 되지 않는 함수는 버퍼에 대 한 읽기 또는 쓰기 액세스를 허용 하지 않습니다. 악용 하면 심각한 보안 문제가 발생할 수 있습니다. 컴파일러는 이러한 함수에 대해 사용 중단 경고를 실행하고 기본 설정 함수를 제안합니다.

이 문제를 해결 하려면 함수 또는 변수 *safe 버전* 을 대신 사용 하는 것이 좋습니다. 이식성 또는 이전 버전과의 호환성을 위해 불가능 한 경우도 있습니다. 코드에서 버퍼를 덮어쓰거나 과도 하 게 읽을 수 없는지 신중 하 게 확인 합니다. 그런 다음 경고를 해제할 수 있습니다.

CRT에서 이러한 함수에 대 한 사용 중단 경고를 해제 하려면 ** \_ crt \_ 보안 \_ \_ 경고 없음**을 정의 합니다.

사용 되지 않는 전역 변수에 대 한 경고를 해제 하려면 ** \_ CRT \_ 보안 \_ \_ 경고 없음 \_ 전역**을 정의 합니다.

이러한 사용 되지 않는 함수 및 전역에 대 한 자세한 내용은 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 및 [안전 라이브러리: c + + 표준 라이브러리](../../standard-library/safe-libraries-cpp-standard-library.md)를 참조 하세요.

## <a name="unsafe-standard-library-functions"></a>안전 하지 않은 표준 라이브러리 함수

안전 하지 않을 수 있는 매개 변수를 사용 하 여 __' std::__*function_name*__:: \_ Unchecked \_ iterator:: \_ 사용 중단 ' 호출에서 std:: function_name 호출__*function_name* **-이 호출은 전달 된 값이 올바른지 확인 하기 위해 호출자에 의존 합니다. 이 경고를 사용 하지 않도록 설정 하려면-D \_ SCL \_ 보안 \_ 경고 없음을 사용 \_ 합니다. Visual C++ ' 확인 된 반복기 '를 사용 하는 방법에 대 한 설명서를 참조 하세요** .

특정 c + + 표준 라이브러리 템플릿 함수는 매개 변수의 정확성을 검사 하지 않으므로 디버그 빌드에서이 경고가 나타납니다. 함수에서 컨테이너 범위를 확인 하는 데 충분 한 정보를 사용할 수 없기 때문입니다. 또는 반복기가 함수에 잘못 사용 될 수 있기 때문입니다. 이 경고는 프로그램의 심각한 보안 허점의 원인이 될 수 있으므로 이러한 기능을 식별 하는 데 도움이 됩니다. 자세한 내용은 [확인 된 반복기](../../standard-library/checked-iterators.md)를 참조 하세요.

예를 들어이 경고는 일반 배열 대신 요소 포인터를에 전달 하는 경우 디버그 모드에서 나타납니다 `std::copy` . 이 문제를 해결 하려면 적절 하 게 선언 된 배열을 사용 하 여 라이브러리에서 배열 범위를 확인 하 고 범위 검사를 수행할 수 있습니다.

```cpp
// C4996_copyarray.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_copyarray.cpp
#include <algorithm>

void example(char const * const src) {
    char dest[1234];
    char * pdest3 = dest + 3;
    std::copy(src, src + 42, pdest3); // C4996
    std::copy(src, src + 42, dest);   // OK, copy can tell that dest is 1234 elements
}
```

몇 가지 표준 라이브러리 알고리즘이 c + + 14의 "이중 범위" 버전을 포함 하도록 업데이트 되었습니다. 이중 범위 버전을 사용 하는 경우 두 번째 범위는 필요한 범위 검사를 제공 합니다.

```cpp
// C4996_containers.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_containers.cpp
#include <algorithm>

bool example(
    char const * const left,
    const size_t leftSize,
    char const * const right,
    const size_t rightSize)
{
    bool result = false;
    result = std::equal(left, left + leftSize, right); // C4996
    // To fix, try this form instead:
    // result = std::equal(left, left + leftSize, right, right + rightSize); // OK
    return result;
}
```

이 예제에서는 표준 라이브러리를 사용 하 여 반복기 사용을 확인 하는 여러 가지 방법을 보여 주고, 선택 되지 않은 사용이 위험할 수 있습니다.

```cpp
// C4996_standard.cpp
// compile with: cl /EHsc /W4 /MDd C4996_standard.cpp
#include <algorithm>
#include <array>
#include <iostream>
#include <iterator>
#include <numeric>
#include <string>
#include <vector>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    vector<int> v(16);
    iota(v.begin(), v.end(), 0);
    print("v: ", v);

    // OK: vector::iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    vector<int> v2(16);
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });
    print("v2: ", v2);

    // OK: back_insert_iterator is marked as checked in debug mode
    // (i.e. an overrun is impossible)
    vector<int> v3;
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });
    print("v3: ", v3);

    // OK: array::iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    array<int, 16> a4;
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });
    print("a4: ", a4);

    // OK: Raw arrays are checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    // NOTE: This applies only when raw arrays are
    // given to C++ Standard Library algorithms!
    int a5[16];
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });
    print("a5: ", a5);

    // WARNING C4996: Pointers cannot be checked in debug mode
    // (i.e. an overrun triggers undefined behavior)
    int a6[16];
    int * p6 = a6;
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });
    print("a6: ", a6);

    // OK: stdext::checked_array_iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    int a7[16];
    int * p7 = a7;
    transform(v.begin(), v.end(),
        stdext::make_checked_array_iterator(p7, 16),
        [](int n) { return n * 7; });
    print("a7: ", a7);

    // WARNING SILENCED: stdext::unchecked_array_iterator
    // is marked as checked in debug mode, but it performs no checking,
    // so an overrun triggers undefined behavior
    int a8[16];
    int * p8 = a8;
    transform( v.begin(), v.end(),
        stdext::make_unchecked_array_iterator(p8),
        [](int n) { return n * 8; });
    print("a8: ", a8);
}
```

코드에 버퍼 오버런 오류가 발생 하지 않았는지 확인 한 경우이 경고를 해제할 수 있습니다. 이러한 함수에 대 한 경고를 해제 하려면 ** \_ SCL \_ 보안 \_ \_ 경고 없음**을 정의 합니다.

## <a name="checked-iterators-enabled"></a>확인 된 반복기 사용

C4996 `_ITERATOR_DEBUG_LEVEL` 가 1 또는 2로 정의 된 경우 확인 된 반복기를 사용 하지 않는 경우에도 발생할 수 있습니다. 기본적으로 디버그 모드 빌드에 대해 2로 설정 되 고 소매 빌드의 경우 0으로 설정 됩니다. 자세한 내용은 [확인 된 반복기](../../standard-library/checked-iterators.md)를 참조 하세요.

```cpp
// C4996_checked.cpp
// compile with: /EHsc /W4 /MDd C4996_checked.cpp
#define _ITERATOR_DEBUG_LEVEL 2

#include <algorithm>
#include <iterator>

using namespace std;
using namespace stdext;

int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 10, 11, 12 };
    copy(a, a + 3, b + 1);   // C4996
    // try the following line instead:
    // copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK
}
```

## <a name="unsafe-mfc-or-atl-code"></a>Unsafe MFC 또는 ATL 코드

C4996는 보안상의 이유로 더 이상 사용 되지 않는 MFC 또는 ATL 함수를 사용 하는 경우 발생할 수 있습니다.

이 문제를 해결 하려면 업데이트 된 함수를 대신 사용 하도록 코드를 변경 하는 것이 좋습니다.

이러한 경고를 표시 하지 않는 방법에 대 한 자세한 내용은 [_AFX_SECURE_NO_WARNINGS](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings)를 참조 하세요.

## <a name="obsolete-crt-functions-and-variables"></a>사용 되지 않는 CRT 함수 및 변수

**이 함수 또는 변수는 최신 라이브러리 또는 운영 체제 기능으로 대체 되었습니다. 대신 new_item를 사용 하는 것이 좋습니다** *new_item* **. 자세한 내용은 온라인 도움말을 참조 하십시오.**

일부 라이브러리 함수 및 전역 변수는 구식으로 사용되지 않습니다. 이러한 함수 및 변수는 이후 버전의 라이브러리에서 제거될 수도 있습니다. 컴파일러는 이러한 항목에 대해 사용 중단 경고를 실행하고 기본 설정 대체 항목을 제안합니다.

이 문제를 해결 하려면 제안 된 함수 또는 변수를 사용 하도록 코드를 변경 하는 것이 좋습니다.

이러한 항목에 대 한 사용 중단 경고를 해제 하려면 ** \_ CRT \_ 사용 되지 않는 \_ \_ 경고**를 정의 합니다. 자세한 내용은 사용되지 않는 함수 또는 변수에 대한 설명서를 참조하세요.

## <a name="marshaling-errors-in-clr-code"></a>CLR 코드의 마샬링 오류

C4996는 CLR 마샬링 라이브러리를 사용 하는 경우에도 발생할 수 있습니다. 이 경우 C4996는 경고가 아니라 오류입니다. [Marshal_as](../../dotnet/marshal-as.md) 를 사용 하 여 [marshal_context 클래스가](../../dotnet/marshal-context-class.md)필요한 두 데이터 형식 간에 변환 하는 경우 오류가 발생 합니다. 마샬링 라이브러리가 변환을 지원 하지 않는 경우에도이 오류가 발생할 수 있습니다. 마샬링 라이브러리에 대 한 자세한 내용은 [c + +의 마샬링 개요](../../dotnet/overview-of-marshaling-in-cpp.md)를 참조 하세요.

마샬링 라이브러리에는에서로 변환 하기 위한 컨텍스트가 필요 하기 때문에이 예제에서는 C4996를 생성 `System::String` `const char *` 합니다.

```cpp
// C4996_Marshal.cpp
// compile with: /clr
// C4996 expected
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = marshal_as<const char*>( message );
   return 0;
}
```

## <a name="example-user-defined-deprecated-function"></a>예: 사용자 정의 사용 되지 않는 함수

특정 함수를 더 이상 사용 하지 않는 경우 사용자 고유의 코드에서 사용 되지 않는 특성을 사용 하 여 호출자에 게 경고할 수 있습니다. 이 예제에서 C4996는 사용 되지 않는 함수가 선언 되는 줄과 함수가 사용 되는 줄에 대해 각각 하나씩, 두 위치에서 생성 됩니다.

```cpp
// C4996.cpp
// compile with: /W3
// C4996 warning expected
#include <stdio.h>

// #pragma warning(disable : 4996)
void func1(void) {
   printf_s("\nIn func1");
}

[[deprecated]]
void func1(int) {
   printf_s("\nIn func2");
}

int main() {
   func1();
   func1(1);    // C4996
}
```
