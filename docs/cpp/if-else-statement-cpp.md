---
title: if-else 문 (C++)
ms.date: 07/20/2019
description: C + +에서 if else 문을 사용 하 여 조건부 분기를 제어 합니다.
f1_keywords:
- else_cpp
- if_cpp
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
ms.openlocfilehash: a9256e32c89890635c5473a85b4bb3b56bec26d4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87187571"
---
# <a name="if-else-statement-c"></a>if-else 문 (C++)

조건부 분기를 제어 합니다. *If 블록* 의 문은 *if 식이* 0이 아닌 값 (또는)으로 계산 되는 경우에만 실행 됩니다 **`true`** . *식* 의 값이 0이 아닌 경우 *문 1* 및 블록의 다른 모든 문이 실행 되 고 else 블록 (있는 경우)이 생략 됩니다. *식* 의 값이 0 이면 if 블록을 건너뛰고 else 블록 (있는 경우)을 실행 합니다. 0이 아닌 값으로 계산 되는 식은

- **`true`**
- null이 아닌 포인터
- 0이 아닌 산술 값 또는
- 산술, 부울 또는 포인터 형식으로의 명확한 변환을 정의 하는 클래스 형식입니다. 변환에 대 한 자세한 내용은 [표준 변환](../cpp/standard-conversions.md)을 참조 하세요.

## <a name="syntax"></a>구문

```cpp
if ( expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// C++17 - Visual Studio 2017 version 15.3 and later:
if ( initialization; expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// C++17 - Visual Studio 2017 version 15.3 and later:
if constexpr (expression)
{
    statement1;
    ...
}
else  // optional
{
   statement2;
   ...
}
```

## <a name="example"></a>예제

```cpp
// if_else_statement.cpp
#include <iostream>

using namespace std;

class C
{
    public:
    void do_something(){}
};
void init(C){}
bool is_true() { return true; }
int x = 10;

int main()
{
    if (is_true())
    {
        cout << "b is true!\n";  // executed
    }
    else
    {
        cout << "b is false!\n";
    }

    // no else statement
    if (x == 10)
    {
        x = 0;
    }

    C* c;
    init(c);
    if (c)
    {
        c->do_something();
    }
    else
    {
        cout << "c is null!\n";
    }
}
```

## <a name="if-statement-with-an-initializer"></a><a name="if_with_init"></a>이니셜라이저가 포함 된 if 문

**Visual Studio 2017 버전 15.3 이상** ( [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)과 함께 사용 가능): **`if`** 문에는 명명 된 변수를 선언 하 고 초기화 하는 식이 포함 될 수도 있습니다. If 블록의 범위 내 에서만 변수가 필요한 경우에는이 형식의 if 문을 사용 합니다.

## <a name="example"></a>예제

```cpp
#include <iostream>
#include <mutex>
#include <map>
#include <string>
#include <algorithm>

using namespace std;

map<int, string> m;
mutex mx;
bool shared_flag; // guarded by mx
void unsafe_operation() {}

int main()
{

    if (auto it = m.find(10); it != m.end())
    {
        cout << it->second;
        return 0;
    }

    if (char buf[10]; fgets(buf, 10, stdin))
    {
        m[0] += buf;
    }

    if (lock_guard<mutex> lock(mx); shared_flag)
    {
        unsafe_operation();
        shared_flag = false;
    }

    string s{ "if" };
    if (auto keywords = { "if", "for", "while" }; any_of(keywords.begin(), keywords.end(), [&s](const char* kw) { return s == kw; }))
    {
        cout << "Error! Token must not be a keyword\n";
    }
}
```

모든 형태의 **`if`** 문에서 구조체를 제외한 모든 값을 가질 수 있는 *식은*모든 부작용을 포함 하 여 계산 됩니다. **`if`** *문*중 하나에 [break](../cpp/break-statement-cpp.md), [continue](../cpp/continue-statement-cpp.md)또는 [goto](../cpp/goto-statement-cpp.md)가 포함 되어 있지 않으면 문에서 제어를 프로그램의 다음 문으로 전달 합니다.

**`else`** 문의 절은 `if...else` **`if`** 해당 문이 없는 동일한 범위에서 가장 가까운 이전 문과 연결 되어 **`else`** 있습니다.

## <a name="a-nameif_constexpr-if-constexpr-statements"></a><a name="if_constexpr">constexpr 문

**Visual Studio 2017 버전 15.3 이상** ( [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)과 함께 사용 가능): 함수 템플릿에서 여러 함수 오버 로드를 사용 하지 않고도 컴파일 시간 분기 결정을 내리는 데 **if constexpr** 문을 사용할 수 있습니다. 예를 들어 매개 변수 압축 풀기를 처리 하는 단일 함수를 작성할 수 있습니다 (매개 변수가 없는 오버 로드 필요 없음).

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
    // handle t
    do_something(t);

    // handle r conditionally
    if constexpr (sizeof...(r))
    {
        f(r...);
    }
    else
    {
        g(r...);
    }
}
```

## <a name="see-also"></a>참고 항목

[선택문](../cpp/selection-statements-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[switch 문 (c + +)](../cpp/switch-statement-cpp.md)
