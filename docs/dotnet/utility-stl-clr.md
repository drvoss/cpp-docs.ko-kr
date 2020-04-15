---
title: utility(STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/utility>
- cliext::pair
- cliext::pair::pair
- cliext::pair::first
- cliext::pair::first_type
- cliext::pair::second
- cliext::pair::second_type
- cliext::pair::swap
- cliext::make_pair
- cliext::pair::operator=
- cliext::pair::operator==
- cliext::pair::operator>=
- cliext::pair::operator>
- cliext::pair::operator!=
- cliext::pair::operator<=
- cliext::pair::operator<
helpviewer_keywords:
- <utility> header [STL/CLR]
- utility header [STL/CLR]
- <cliext/utility> header [STL/CLR]
- first member [STL/CLR]
- first_type member [STL/CLR]
- second member [STL/CLR]
- second_type member [STL/CLR]
- swap member [STL/CLR]
- make_pair function [STL/CLR]
- pair class [STL/CLR]
- pair member [STL/CLR]
- operator== member [STL/CLR]
- operator= member [STL/CLR]
- operator>= member [STL/CLR]
- operator> member [STL/CLR]
- operator!= member [STL/CLR]
- operator<= member [STL/CLR]
- operator< member [STL/CLR]
ms.assetid: fb48cb75-d5ef-47ce-b526-bf60dc86c552
ms.openlocfilehash: 6d025230abcff42e367a231e616a13f0f8c684f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320278"
---
# <a name="utility-stlclr"></a>utility(STL/CLR)

STL/CLR 헤더를 `<cliext/utility>` 포함하여 템플릿 `pair` 클래스와 여러 지원 템플릿 함수를 정의합니다.

## <a name="syntax"></a>구문

```cpp
#include <utility>
```

## <a name="requirements"></a>요구 사항

**헤더:** \<클라이펙트/유틸리티>

**네임 스페이스:** 클라이펙스트

## <a name="declarations"></a>선언

|클래스|Description|
|-----------|-----------------|
|[pair(STL/CLR)](#pair)|요소 쌍을 래핑합니다.|

|연산자|Description|
|--------------|-----------------|
|[operator== (pair)(STL/CLR)](#op_eq)|동일한 비교를 쌍으로 합니다.|
|[연산자!= (쌍) (STL / CLR)](#op_neq)|쌍은 같지 않습니다 비교.|
|[연산자<(쌍) (STL/CLR)](#op_lt)|비교보다 적게 페어링합니다.|
|[연산자\<= (쌍) (STL / CLR)](#op_lteq)|비교보다 적거나 동일한 쌍을 이수합니다.|
|[연산자>(쌍) (STL/CLR)](#op_gt)|비교보다 큰 쌍을 이수합니다.|
|[연산자>= (쌍) (STL / CLR)](#op_gteq)|비교보다 크거나 같게 쌍을 이수합니다.|

|함수|Description|
|--------------|-----------------|
|[make_pair(STL/CLR)](#make_pair)|값 쌍에서 쌍을 만듭니다.|

## <a name="members"></a>멤버

## <a name="pair-stlclr"></a><a name="pair"></a>쌍(STL/CLR)

템플릿 클래스는 한 쌍의 값을 래핑하는 개체를 설명합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value1,
    typename Value2>
    ref class pair;
```

#### <a name="parameters"></a>매개 변수

*값1*<br/>
첫 번째 래핑된 값의 형식입니다.

*값2*<br/>
두 번째 래핑된 값의 형식입니다.

## <a name="members"></a>멤버

|형식 정의|Description|
|---------------------|-----------------|
|[pair::first_type(STL/CLR)](#first_type)|첫 번째 래핑된 값의 형식입니다.|
|[pair::second_type(STL/CLR)](#second_type)|두 번째 래핑된 값의 형식입니다.|

|멤버 개체|Description|
|-------------------|-----------------|
|[pair::first(STL/CLR)](#first)|첫 번째 저장된 값입니다.|
|[pair::second(STL/CLR)](#second)|두 번째 저장된 값입니다.|

|멤버 함수|Description|
|---------------------|-----------------|
|[pair::pair(STL/CLR)](#pair_pair)|쌍 개체를 생성합니다.|
|[pair::swap(STL/CLR)](#swap)|두 쌍의 내용을 바꿉습니다.|

|연산자|Description|
|--------------|-----------------|
|[pair::operator=(STL/CLR)](#op_as)|저장된 값 쌍을 대체합니다.|

## <a name="remarks"></a>설명

개체는 값 쌍을 저장합니다. 이 템플릿 클래스를 사용하여 두 값을 단일 개체로 결합합니다. 또한 개체(여기에 `cliext::pair` 설명)는 관리되는 형식만 저장합니다. 관리되지 않는 형식 의 `std::pair`쌍을 저장하려면 에서 선언된 `<utility>`을 사용합니다.

## <a name="pairfirst-stlclr"></a><a name="first"></a>쌍 ::첫 번째(STL/CLR)

첫 번째 래핑된 값입니다.

### <a name="syntax"></a>구문

```cpp
Value1 first;
```

### <a name="remarks"></a>설명

개체는 첫 번째 래핑된 값을 저장합니다.

### <a name="example"></a>예제

```cpp
// cliext_pair_first.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairfirst_type-stlclr"></a><a name="first_type"></a>쌍 :: first_type (STL / CLR)

첫 번째 래핑된 값의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Value1 first_type;
```

### <a name="remarks"></a>설명

형식은 템플릿 매개 변수 *Value1의*동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_pair_first_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairoperator-stlclr"></a><a name="op_as"></a>쌍 ::연산자 = (STL / CLR)

저장된 값 쌍을 대체합니다.

### <a name="syntax"></a>구문

```cpp
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>매개 변수

*오른쪽*<br/>
쌍을 이루어 복사합니다.

### <a name="remarks"></a>설명

멤버 연산자는 개체에 *바로* 복사한 다음 을 반환합니다. `*this` 저장된 값 쌍을 *오른쪽에*저장된 값 쌍의 복사본으로 대체하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_pair_operator_as.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

// assign to a new pair
    cliext::pair<wchar_t, int> c2;
    c2 = c1;
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);
    return (0);
    }
```

```Output
[x, 3]
[x, 3]
```

## <a name="pairpair-stlclr"></a><a name="pair_pair"></a>쌍 : :p에어 (STL / CLR)

쌍 개체를 생성합니다.

### <a name="syntax"></a>구문

```cpp
pair();
pair(pair<Coll>% right);
pair(pair<Coll>^ right);
pair(Value1 val1, Value2 val2);
```

#### <a name="parameters"></a>매개 변수

*오른쪽*<br/>
쌍을 이루어 저장합니다.

*1발*<br/>
저장할 첫 번째 값입니다.

*val2*<br/>
저장할 두 번째 값입니다.

### <a name="remarks"></a>설명

생성자:

`pair();`

을 사용해 저장된 쌍을 기본 생성 값으로 초기화합니다.

생성자:

`pair(pair<Value1, Value2>% right);`

저장된 쌍을 `right.` [쌍 ::first(STL/CLR)](../dotnet/pair-first-stl-clr.md) 및 `right.` [쌍::second(STL/CLR)로](../dotnet/pair-second-stl-clr.md)초기화합니다.

`pair(pair<Value1, Value2>^ right);`

저장된 쌍을 `right->` [쌍 ::first(STL/CLR)](../dotnet/pair-first-stl-clr.md) 및 `right>` [쌍::second(STL/CLR)로](../dotnet/pair-second-stl-clr.md)초기화합니다.

생성자:

`pair(Value1 val1, Value2 val2);`

저장된 쌍을 *val1* 및 *val2로*초기화합니다.

### <a name="example"></a>예제

```cpp
// cliext_pair_construct.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
// construct an empty container
    cliext::pair<wchar_t, int> c1;
    System::Console::WriteLine("[{0}, {1}]",
        c1.first == L'\0' ? "\\0" : "??", c1.second);

// construct with a pair of values
    cliext::pair<wchar_t, int> c2(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

// construct by copying another pair
    cliext::pair<wchar_t, int> c3(c2);
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);

// construct by copying a pair handle
    cliext::pair<wchar_t, int> c4(%c3);
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);

    return (0);
    }
```

```Output
[\0, 0]
[x, 3]
[x, 3]
[x, 3]
```

## <a name="pairsecond-stlclr"></a><a name="second"></a>쌍 : 두 번째 (STL / CLR)

두 번째 래핑된 값입니다.

### <a name="syntax"></a>구문

```cpp
Value2 second;
```

### <a name="remarks"></a>설명

개체는 두 번째 래핑된 값을 저장합니다.

### <a name="example"></a>예제

```cpp
// cliext_pair_second.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairsecond_type-stlclr"></a><a name="second_type"></a>쌍::second_type(STL/CLR)

두 번째 래핑된 값의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Value2 second_type;
```

### <a name="remarks"></a>설명

형식은 템플릿 매개 변수 *Value2의*동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_pair_second_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairswap-stlclr"></a><a name="swap"></a>쌍 ::스왑 (STL / CLR)

두 쌍의 내용을 바꿉습니다.

### <a name="syntax"></a>구문

```cpp
void swap(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>매개 변수

*오른쪽*<br/>
페어링하여 내용물로 바꿉을 바꿉입니다.

### <a name="remarks"></a>설명

멤버 함수는 저장된 값 `*this` 쌍을 오른쪽으로 바꿉습니다. *right*

### <a name="example"></a>예제

```cpp
// cliext_pair_swap.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
    {
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    cliext::deque<wchar_t> d2(5, L'x');
    Mycoll c2(%d2);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// swap and redisplay
    c1.swap(c2);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
x x x x x
x x x x x
a b c
```

## <a name="make_pair-stlclr"></a><a name="make_pair"></a>make_pair(STL/CLR)

값 `pair` 쌍에서 a를 만듭니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value1,
    typename Value2>
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);
```

#### <a name="parameters"></a>매개 변수

*값1*<br/>
첫 번째 래핑된 값의 형식입니다.

*값2*<br/>
두 번째 래핑된 값의 형식입니다.

*첫 번째*<br/>
래핑할 첫 번째 값입니다.

*두 번째*<br/>
줄 바꿈할 두 번째 값입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `pair<Value1, Value2>(first, second)`을 반환합니다. 이를 사용하여 한 `pair<Value1, Value2>` 쌍의 값에서 개체를 생성합니다.

### <a name="example"></a>예제

```cpp
// cliext_make_pair.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    c1 = cliext::make_pair(L'y', 4);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    return (0);
    }
```

```Output
[x, 3]
[y, 4]
```

## <a name="operator-pair-stlclr"></a><a name="op_neq"></a>연산자!= (쌍) (STL / CLR)

쌍은 같지 않습니다 비교.

### <a name="syntax"></a>구문

```cpp
template<typename Value1,
    typename Value2>
    bool operator!=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 쌍입니다.

*오른쪽*<br/>
오른쪽 쌍은 비교할 수 있습니다.

### <a name="remarks"></a>설명

연산자 `!(left == right)`함수가 반환합니다. 두 쌍을 요소별로 비교할 때 *왼쪽이* *오른쪽과* 동일하게 정렬되지 않았는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_pair_operator_ne.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] != [x 3] is {0}",
        c1 != c1);
    System::Console::WriteLine("[x 3] != [x 4] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] != [x 3] is False
[x 3] != [x 4] is True
```

## <a name="operatorlt-pair-stlclr"></a><a name="op_lt"></a>연산자(쌍)&lt; (STL/CLR)

비교보다 적게 페어링합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value1,
    typename Value2>
    bool operator<(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 쌍입니다.

*오른쪽*<br/>
오른쪽 쌍은 비교할 수 있습니다.

### <a name="remarks"></a>설명

연산자 `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second`함수가 반환합니다. 두 쌍을 요소별로 비교할 때 *왼쪽이* *오른쪽* 이전 순서인지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_pair_operator_lt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] < [x 3] is {0}",
        c1 < c1);
    System::Console::WriteLine("[x 3] < [x 4] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] < [x 3] is False
[x 3] < [x 4] is True
```

## <a name="operatorlt-pair-stlclr"></a><a name="op_lteq"></a>연산자&lt;= (쌍) (STL / CLR)

비교보다 적거나 동일한 쌍을 이수합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value1,
    typename Value2>
    bool operator<=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 쌍입니다.

*오른쪽*<br/>
오른쪽 쌍은 비교할 수 있습니다.

### <a name="remarks"></a>설명

연산자 `!(right < left)`함수가 반환합니다. 두 쌍을 요소별로 비교할 때 *왼쪽이* *오른쪽* 이후에 정렬되지 않았는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_pair_operator_le.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] <= [x 3] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] <= [x 3] is True
[x 4] <= [x 3] is False
```

## <a name="operator-pair-stlclr"></a><a name="op_eq"></a>연산자 = = (쌍) (STL / CLR)

동일한 비교를 쌍으로 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value1,
    typename Value2>
    bool operator==(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 쌍입니다.

*오른쪽*<br/>
오른쪽 쌍은 비교할 수 있습니다.

### <a name="remarks"></a>설명

연산자 `left.first ==` `right.first &&` `left.second ==` `right.second`함수가 반환합니다. 두 쌍을 요소별로 비교할 때 *왼쪽이* *오른쪽과* 동일한 순서로 정렬되는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_pair_operator_eq.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] == [x 3] is {0}",
        c1 == c1);
    System::Console::WriteLine("[x 3] == [x 4] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] == [x 3] is True
[x 3] == [x 4] is False
```

## <a name="operatorgt-pair-stlclr"></a><a name="op_gt"></a>연산자(쌍)&gt; (STL/CLR)

비교보다 큰 쌍을 이수합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value1,
    typename Value2>
    bool operator>(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 쌍입니다.

*오른쪽*<br/>
오른쪽 쌍은 비교할 수 있습니다.

### <a name="remarks"></a>설명

연산자 `right` `<` `left`함수가 반환합니다. 두 쌍을 요소별로 비교할 때 *왼쪽이* *오른쪽* 이후에 정렬되는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_pair_operator_gt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] > [x 3] is {0}",
        c1 > c1);
    System::Console::WriteLine("[x 4] > [x 3] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] > [x 3] is False
[x 4] > [x 3] is True
```

## <a name="operatorgt-pair-stlclr"></a><a name="op_gteq"></a>연산자&gt;= (쌍) (STL / CLR)

비교보다 크거나 같게 쌍을 이수합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value1,
    typename Value2>
    bool operator>=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 쌍입니다.

*오른쪽*<br/>
오른쪽 쌍은 비교할 수 있습니다.

### <a name="remarks"></a>설명

연산자 `!(left < right)`함수가 반환합니다. 두 쌍을 요소별로 비교할 때 *왼쪽이 오른쪽* 앞에 정렬되지 않았는지 여부를 테스트하는 데 사용합니다. *left*

### <a name="example"></a>예제

```cpp
// cliext_pair_operator_ge.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] >= [x 3] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] >= [x 3] is True
[x 3] >= [x 4] is False
```
