---
title: set(STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::set
- cliext::set::begin
- cliext::set::clear
- cliext::set::const_iterator
- cliext::set::const_reference
- cliext::set::const_reverse_iterator
- cliext::set::count
- cliext::set::difference_type
- cliext::set::empty
- cliext::set::end
- cliext::set::equal_range
- cliext::set::erase
- cliext::set::find
- cliext::set::generic_container
- cliext::set::generic_iterator
- cliext::set::generic_reverse_iterator
- cliext::set::generic_value
- cliext::set::insert
- cliext::set::iterator
- cliext::set::key_comp
- cliext::set::key_compare
- cliext::set::key_type
- cliext::set::lower_bound
- cliext::set::make_value
- cliext::set::operator=
- cliext::set::rbegin
- cliext::set::reference
- cliext::set::rend
- cliext::set::reverse_iterator
- cliext::set::set
- cliext::set::size
- cliext::set::size_type
- cliext::set::swap
- cliext::set::to_array
- cliext::set::upper_bound
- cliext::set::value_comp
- cliext::set::value_compare
- cliext::set::value_type
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- set class [STL/CLR]
- operator!= (set) member [STL/CLR]
- operator< (set) member [STL/CLR]
- operator<= (set) member [STL/CLR]
- operator== (set) member [STL/CLR]
- operator> (set) member [STL/CLR]
- operator>= (set) member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- count member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- equal_range member [STL/CLR]
- erase member [STL/CLR]
- find member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- operator= member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- set member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
ms.openlocfilehash: 38b0a3278efd10ef5cc989a5fc900bf82d377eae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320313"
---
# <a name="set-stlclr"></a>set(STL/CLR)

템플릿 클래스는 양방향 액세스 권한이 있는 다양한 길이의 요소 시퀀스를 제어하는 개체에 대해 설명합니다. 컨테이너를 `set` 사용하여 요소 시퀀스를 (거의) 균형 잡힌 정렬된 노드 트리로 관리하며 각 노드는 하나의 요소를 저장합니다.

아래 `GValue` 설명에서 는 .와 `GKey` *Key* `Key^`동일합니다.

## <a name="syntax"></a>구문

```cpp
template<typename Key>
    ref class set
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>매개 변수

*키*<br/>
제어되는 시퀀스에 있는 요소의 키 구성 요소 형식입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<클라이펙트/세트>

**네임 스페이스:** 클라이펙스트

## <a name="declarations"></a>선언

|형식 정의|Description|
|---------------------|-----------------|
|[set::const_iterator(STL/CLR)](#const_iterator)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|
|[set::const_reference(STL/CLR)](#const_reference)|요소에 대한 상수 참조의 형식입니다.|
|[set::const_reverse_iterator(STL/CLR)](#const_reverse_iterator)|제어되는 시퀀스에 대한 상수 역방향 반복기의 형식입니다.|
|[set::difference_type(STL/CLR)](#difference_type)|두 요소 사이의 (서명된) 거리의 유형입니다.|
|[set::generic_container(STL/CLR)](#generic_container)|컨테이너에 대한 일반 인터페이스의 형식입니다.|
|[set::generic_iterator(STL/CLR)](#generic_iterator)|컨테이너의 일반 인터페이스에 대한 이터레이터의 형식입니다.|
|[set::generic_reverse_iterator(STL/CLR)](#generic_reverse_iterator)|컨테이너의 일반 인터페이스에 대한 역방향 거역 의 형식입니다.|
|[set::generic_value(STL/CLR)](#generic_value)|컨테이너에 대한 제네릭 인터페이스에 대한 요소의 형식입니다.|
|[set::iterator(STL/CLR)](#iterator)|제어되는 시퀀스에 대한 반복기의 형식입니다.|
|[set::key_compare(STL/CLR)](#key_compare)|두 키에 대한 순서 대리자입니다.|
|[set::key_type(STL/CLR)](#key_type)|정렬 키의 형식입니다.|
|[set::reference(STL/CLR)](#reference)|요소에 대한 참조의 형식입니다.|
|[set::reverse_iterator(STL/CLR)](#reverse_iterator)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|
|[set::size_type(STL/CLR)](#size_type)|두 요소 사이의 a(음수) 거리 유형입니다.|
|[set::value_compare(STL/CLR)](#value_compare)|두 요소 값에 대한 순서 대리자입니다.|
|[set::value_type(STL/CLR)](#value_type)|요소의 형식입니다.|

|멤버 함수|Description|
|---------------------|-----------------|
|[set::begin(STL/CLR)](#begin)|제어되는 시퀀스의 시작을 지정합니다.|
|[set::clear(STL/CLR)](#clear)|모든 요소를 제거합니다.|
|[set::count(STL/CLR)](#count)|지정된 키와 일치하는 요소를 계산합니다.|
|[set::empty(STL/CLR)](#empty)|요소가 있는지 여부를 테스트합니다.|
|[set::end(STL/CLR)](#end)|제어되는 시퀀스의 끝을 지정합니다.|
|[set::equal_range(STL/CLR)](#equal_range)|지정된 키와 일치하는 범위를 찾습니다.|
|[set::erase(STL/CLR)](#erase)|지정된 위치에 있는 요소를 제거합니다.|
|[set::find(STL/CLR)](#find)|지정된 키와 일치하는 요소를 찾습니다.|
|[set::insert(STL/CLR)](#insert)|요소를 추가합니다.|
|[set::key_comp(STL/CLR)](#key_comp)|두 키에 대한 순서 대리자를 복사합니다.|
|[set::lower_bound(STL/CLR)](#lower_bound)|지정된 키와 일치하는 범위의 시작을 찾습니다.|
|[set::make_value(STL/CLR)](#make_value)|값 개체를 생성합니다.|
|[set::rbegin(STL/CLR)](#rbegin)|제어되는 역방향 시퀀스의 시작을 지정합니다.|
|[set::rend(STL/CLR)](#rend)|제어되는 역방향 시퀀스의 끝을 지정합니다.|
|[set::set(STL/CLR)](#set)|컨테이너 개체를 만듭니다.|
|[set::size(STL/CLR)](#size)|요소 수를 계산합니다.|
|[set::swap(STL/CLR)](#swap)|두 컨테이너의 내용을 바꿉니다.|
|[set::to_array(STL/CLR)](#to_array)|제어된 시퀀스를 새 배열로 복사합니다.|
|[set::upper_bound(STL/CLR)](#upper_bound)|지정된 키와 일치하는 범위의 끝을 찾습니다.|
|[set::value_comp(STL/CLR)](#value_comp)|두 요소 값에 대한 순서 대리자를 복사합니다.|

|연산자|Description|
|--------------|-----------------|
|[set::operator=(STL/CLR)](#op_as)|제어되는 시퀀스를 바꿉니다.|
|[연산자!= (세트) (STL / CLR)](#op_neq)|개체가 `set` 다른 `set` 개체와 같지 않은지 확인합니다.|
|[연산자<(세트) (STL/CLR)](#op_lt)|개체가 `set` 다른 `set` 개체보다 작은지 확인합니다.|
|[연산자<= (세트) (STL / CLR)](#op_lteq)|개체가 `set` 다른 `set` 개체보다 적거나 같는지 여부를 결정합니다.|
|[연산자 = (세트) (STL / CLR)](#op_eq)|개체가 `set` 다른 `set` 개체와 동일한지 여부를 결정합니다.|
|[연산자>(세트) (STL/CLR)](#op_gt)|개체가 `set` 다른 `set` 개체보다 큰지 여부를 결정합니다.|
|[operator>= (set)(STL/CLR)](#op_gteq)|개체가 `set` 다른 `set` 개체보다 크거나 같는지 여부를 결정합니다.|

## <a name="interfaces"></a>인터페이스

|인터페이스|Description|
|---------------|-----------------|
|<xref:System.ICloneable>|개체를 복제합니다.|
|<xref:System.Collections.IEnumerable>|요소를 통해 시퀀스합니다.|
|<xref:System.Collections.ICollection>|요소 그룹을 유지 관리합니다.|
|<xref:System.Collections.Generic.IEnumerable%601>|입력된 요소를 통해 시퀀스합니다.|
|<xref:System.Collections.Generic.ICollection%601>|형식이 입력된 요소의 그룹을 유지 관리합니다.|
|아이트리\<키, 가치>|일반 컨테이너를 유지 관리합니다.|

## <a name="remarks"></a>설명

개체는 제어하는 시퀀스에 대해 개별 노드로 할당하고 저장소를 해제합니다. 한 노드의 내용을 다른 노드로 복사하지 않고 노드 간의 링크를 변경하여 정렬된 유지되는 (거의) 균형 잡힌 트리에 요소를 삽입합니다. 즉, 나머지 요소를 방해하지 않고 요소를 자유롭게 삽입하고 제거할 수 있습니다.

개체는 저장된 대리자 개체를 [호출하여](../dotnet/set-key-compare-stl-clr.md)제어하는 시퀀스를 key_compare 정렬합니다. 집합을 생성할 때 저장된 대리자 개체를 지정할 수 있습니다. 대리자 개체를 지정하지 않으면 기본값은 비교 `operator<(key_type, key_type)`입니다. 멤버 함수 [집합::key_comp(STL/CLR)를](../dotnet/set-key-comp-stl-clr.md)`()`호출하여 이 저장된 개체에 액세스합니다.

이러한 대리자 개체는 유형 [집합::key_type(STL/CLR)의](../dotnet/set-key-type-stl-clr.md)키에 대해 엄격한 약한 순서를 적용해야 합니다. 즉, 두 개의 `X` 키와 `Y`다음의 키에 대해 다음과 같은 의미입니다.

`key_comp()(X, Y)`모든 통화에서 동일한 부울 결과를 반환합니다.

true이면 `key_comp()(X, Y)` `key_comp()(Y, X)` 거짓이어야 합니다.

true이면 `key_comp()(X, Y)` `X` 전에 `Y`주문했다고 합니다.

만약 `!key_comp()(X, Y) && !key_comp()(Y, X)` 사실이라면, `X` `Y` 동등한 순서를 가지고 있다고합니다.

제어된 `X` 시퀀스에서 `Y` 앞에 오는 `key_comp()(Y, X)` 모든 요소의 경우 false입니다. (기본 대리자 개체의 경우 키는 값이 줄어들지 않습니다.) 템플릿 클래스 [집합과](../dotnet/set-stl-clr.md)달리 템플릿 `set` 클래스의 개체는 모든 요소에 대한 키가 고유할 필요가 없습니다. (둘 이상의 키는 동일한 순서를 가질 수 있습니다.)

각 요소는 ey와 값 모두역할을 합니다. 시퀀스는 시퀀스의 요소 수의 로그백에 비례하는 여러 작업으로 임의의 요소를 조회, 삽입 및 제거할 수 있는 방식으로 표시됩니다(로그할리믹 시간). 또한, 요소를 삽입할 경우 어떤 반복기도 무효화되지 않으며, 요소를 제거할 경우 제거된 요소를 가리키고 있는 반복기만 무효화됩니다.

집합은 양방향 이터레이터를 지원하므로 제어된 시퀀스에서 요소를 지정하는 이터레이터가 주어진 인접 요소로 단계별로 이동이 가능합니다. 특수 헤드 노드는 [set::end(STL/CLR)에](../dotnet/set-end-stl-clr.md)`()`의해 반환되는 이터레이터에 해당합니다. 이 반복기를 삭제하여 제어된 시퀀스의 마지막 요소에 도달할 수 있습니다(있는 경우). 헤드 노드에 도달하기 위해 세트 거터레이터를 증분할 수 있으며, `end()`그런 다음 에 해당합니다. 그러나 `end()`에서 반환된 이터레이터를 참조할 수는 없습니다.

임의 액세스 이터레이터가 필요한 숫자 위치가 주어진 집합 요소를 직접 참조할 수 없습니다.

집합 iterator는 핸들을 연결된 집합 노드에 저장하고 핸들을 연결된 컨테이너에 저장합니다. 연관된 컨테이너 개체에만 이터레이터를 사용할 수 있습니다. 집합 이터레이터는 연결된 집합 노드가 일부 집합과 연결되어 있는 한 유효합니다. 또한 유효한 이터레이터는 이 거변이 가능하므로 `end()`이 거액이 같지 않은 한 지정한 요소 값에 액세스하거나 변경할 수 있습니다.

요소를 지우거나 제거하면 소멸자가 저장된 값에 대해 호출됩니다. 컨테이너를 파괴하여 모든 요소를 지웁습니다. 따라서 요소 형식이 ref 클래스인 컨테이너는 컨테이너보다 오래 되는 요소가 없음을 보장합니다. 그러나 핸들 컨테이너가 해당 요소를 *파괴하지는* 않습니다.

## <a name="members"></a>멤버

## <a name="setbegin-stlclr"></a><a name="begin"></a>설정::시작(STL/CLR)

제어되는 시퀀스의 시작을 지정합니다.

### <a name="syntax"></a>구문

```cpp
iterator begin();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스의 첫 번째 요소를 지정하거나 빈 시퀀스의 끝 바로 너머에 있는 양방향 이터레이터를 반환합니다. 이를 통해 제어되는 시퀀스의 `current` 시작을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_set_begin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    Myset::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*begin() = a
*++begin() = b
```

## <a name="setclear-stlclr"></a><a name="clear"></a>설정 :: 지우기 (STL / CLR)

모든 요소를 제거합니다.

### <a name="syntax"></a>구문

```cpp
void clear();
```

### <a name="remarks"></a>설명

멤버 함수는 [set::지우기(STL/CLR)](../dotnet/set-erase-stl-clr.md) `(` [set::begin(STL/CLR)](../dotnet/set-begin-stl-clr.md) `(),` [set::end(STL/CLR)를](../dotnet/set-end-stl-clr.md)`())`효과적으로 호출합니다. 제어된 시퀀스가 비어 있는지 확인하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_clear.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

// add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 0
a b
size() = 0
```

## <a name="setconst_iterator-stlclr"></a><a name="const_iterator"></a>설정::const_iterator(STL/CLR)

제어되는 시퀀스에 대한 상수 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>설명

형식은 제어된 시퀀스에 `T2` 대한 일정한 양방향 거처역할을 할 수 있는 지정되지 않은 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_const_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    Myset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setconst_reference-stlclr"></a><a name="const_reference"></a>설정::const_reference(STL/CLR)

요소에 대한 상수 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>설명

형식은 요소에 대한 상수 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_const_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    Myset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myset::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>설정::const_reverse_iterator(STL/CLR)

제어된 시퀀스에 대한 상수 역방향 이터레이터의 유형입니다.

### <a name="syntax"></a>구문

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>설명

형식은 제어된 시퀀스에 `T4` 대한 상수 역방향 거역으로 사용할 수 있는 지정되지 않은 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" reversed
    Myset::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="setcount-stlclr"></a><a name="count"></a>설정::개수(STL/CLR)

지정한 키와 일치하는 요소의 수를 찾습니다.

### <a name="syntax"></a>구문

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>매개 변수

*키*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

멤버 함수는 *키와*동등한 순서를 가진 제어된 시퀀스의 요소 수를 반환합니다. 이를 통해 현재 제어되는 시퀀스에 있는 요소 중 지정된 키와 일치하는 요소의 수를 확인할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_set_count.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
a b c
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="setdifference_type-stlclr"></a><a name="difference_type"></a>세트::difference_type(STL/CLR)

두 요소 사이의 서명된 거리의 유형입니다.

### <a name="syntax"></a>구문

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>설명

형식은 음수 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_difference_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myset::difference_type diff = 0;
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

// compute negative difference
    diff = 0;
    for (Myset::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="setempty-stlclr"></a><a name="empty"></a>설정 ::비어 있음(STL/CLR)

요소가 있는지 여부를 테스트합니다.

### <a name="syntax"></a>구문

```cpp
bool empty();
```

### <a name="remarks"></a>설명

멤버 함수는 빈 제어되는 시퀀스에 대해 true를 반환합니다. [설정::크기(STL/CLR)와](../dotnet/set-size-stl-clr.md)`() == 0`동일합니다. 집합이 비어 있는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_empty.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="setend-stlclr"></a><a name="end"></a>설정::끝(STL/CLR)

제어되는 시퀀스의 끝을 지정합니다.

### <a name="syntax"></a>구문

```cpp
iterator end();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스의 끝 바로 너머를 가리키는 양방향 이터레이터를 반환합니다. 제어된 시퀀스의 끝을 지정하는 이터레이터를 가져오는 데 사용합니다. 제어된 시퀀스의 길이가 변경되면 해당 상태는 변경되지 않습니다.

### <a name="example"></a>예제

```cpp
// cliext_set_end.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last two items
    Myset::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
```

## <a name="setequal_range-stlclr"></a><a name="equal_range"></a>설정::equal_range(STL/CLR)

지정된 키와 일치하는 범위를 찾습니다.

### <a name="syntax"></a>구문

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>매개 변수

*키*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

멤버 함수는 한 쌍의 `cliext::pair<iterator, iterator>(` 이터레이터 [집합::lower_bound(STL/CLR)](../dotnet/set-lower-bound-stl-clr.md) `(key),` [집합::upper_bound/CLR(STL/CLR)을](../dotnet/set-upper-bound-stl-clr.md)`(key))`반환합니다. 이를 사용하여 지정된 키와 일치하는 제어된 시퀀스의 현재 요소 범위를 결정합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_equal_range.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
typedef Myset::pair_iter_iter Pairii;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

// display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("{0} ", *pair1.first);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
equal_range(L'x') empty = True
b
```

## <a name="seterase-stlclr"></a><a name="erase"></a>설정::지우기(STL/CLR)

지정된 위치에 있는 요소를 제거합니다.

### <a name="syntax"></a>구문

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
size_type erase(key_type key)
```

#### <a name="parameters"></a>매개 변수

*첫 번째*<br/>
지울 범위의 시작.

*키*<br/>
지울 키 값입니다.

*마지막*<br/>
지울 범위의 끝입니다.

*어디*<br/>
지울 요소입니다.

### <a name="remarks"></a>설명

첫 번째 멤버 함수는 *위치를*가리키는 제어된 시퀀스의 요소를 제거하고 제거된 요소 또는 [set::end(STL/CLR)](../dotnet/set-end-stl-clr.md) `()` 외에 남아 있는 첫 번째 요소를 지정하는 이터레이터를 반환합니다. 단일 요소를 제거하는 데 사용합니다.

두 번째 멤버 함수는 범위 [,`first`에서 `last`제어된 시퀀스의 요소를 제거하고 제거된 요소 또는 이러한 요소가 없는 `end()` 경우 나머지 첫 번째 요소를 지정하는 이터레이터를 반환합니다. 이 요소를 사용하여 0개 이상의 연속 요소를 제거합니다.

세 번째 멤버 함수는 키에 동일한 순서를 가진 *key*제어된 시퀀스의 모든 요소를 제거하고 제거된 요소 수의 수를 반환합니다. 지정된 키와 일치하는 모든 요소를 제거하고 계산하는 데 사용합니다.

각 요소 지우기는 제어된 시퀀스의 요소 수의 로그릿hm에 비례하는 시간이 걸립니다.

### <a name="example"></a>예제

```cpp
// cliext_set_erase.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

// add elements and display " b c d e"
    c1.insert(L'd');
    c1.insert(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// erase all but end
    Myset::iterator it = c1.end();
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",
        *c1.erase(c1.begin(), --it));
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
erase(begin()) = b
b c d e
erase(begin(), end()-1) = e
size() = 1
```

## <a name="setfind-stlclr"></a><a name="find"></a>설정::찾기(STL/CLR)

지정된 키와 일치하는 요소를 찾습니다.

### <a name="syntax"></a>구문

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>매개 변수

*키*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

제어된 시퀀스에서 하나 이상의 요소가 *키와*동일한 순서를 지정하는 경우 멤버 함수는 이러한 요소 중 하나를 지정하는 이터레이터를 반환합니다. 그렇지 않으면 [set::end(STL/CLR)를](../dotnet/set-end-stl-clr.md)`()`반환합니다. 지정된 키와 일치하는 제어된 시퀀스에서 현재 요소를 찾는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_find.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());
    System::Console::WriteLine("find {0} = {1}",
        L'b', *c1.find(L'b'));
    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
a b c
find A = False
find b = b
find C = False
```

## <a name="setgeneric_container-stlclr"></a><a name="generic_container"></a>설정::generic_container(STL/CLR)

컨테이너에 대한 일반 인터페이스의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::
    ITree<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>설명

형식은 이 템플릿 컨테이너 클래스의 일반 인터페이스를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_generic_container.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    gc1->insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify original and display generic
    c1.insert(L'e');
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c d
a b c d e
```

## <a name="setgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>설정::generic_iterator(STL/CLR)

컨테이너의 일반 인터페이스와 함께 사용할 이터레이터의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>설명

형식은 이 템플릿 컨테이너 클래스의 제네릭 인터페이스와 함께 사용할 수 있는 제네릭 거터레이터를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_generic_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_iterator gcit = gc1->begin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="setgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>설정::generic_reverse_iterator(STL/CLR)

컨테이너의 일반 인터페이스와 함께 사용할 역방향 거역 의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>설명

형식은 이 템플릿 컨테이너 클래스의 제네릭 인터페이스와 함께 사용할 수 있는 제네릭 역방향 거점을 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_reverse_iterator gcit = gc1->rbegin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="setgeneric_value-stlclr"></a><a name="generic_value"></a>설정::generic_value(STL/CLR)

컨테이너의 제네릭 인터페이스와 함께 사용할 요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>설명

형식은 이 템플릿 컨테이너 `GValue` 클래스의 일반 인터페이스와 함께 사용할 저장된 요소 값을 설명하는 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_generic_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_iterator gcit = gc1->begin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="setinsert-stlclr"></a><a name="insert"></a>세트 ::삽입 (STL / CLR)

요소를 추가합니다.

### <a name="syntax"></a>구문

```cpp
cliext::pair<iterator, bool> insert(value_type val);
iterator insert(iterator where, value_type val);
template<typename InIter>
    void insert(InIter first, InIter last);
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);
```

#### <a name="parameters"></a>매개 변수

*첫 번째*<br/>
삽입할 범위의 시작.

*마지막*<br/>
삽입할 범위의 끝입니다.

*오른쪽*<br/>
삽입할 열거형입니다.

*발*<br/>
삽입할 키 값입니다.

*어디*<br/>
삽입 할 컨테이너의 위치 (힌트 만).

### <a name="remarks"></a>설명

각 멤버 함수는 나머지 카페랜드가 지정한 시퀀스를 삽입합니다.

첫 번째 멤버 함수는 값 *val이*있는 요소를 삽입하고 `X`값 쌍을 반환합니다. true이면 `X.second` `X.first` 새로 삽입된 요소를 지정합니다. 그렇지 `X.first` 않으면 이미 존재하고 새 요소가 삽입되지 않은 동일한 순서가 있는 요소를 지정합니다. 단일 요소를 삽입하는 데 사용합니다.

두 번째 멤버 함수는 *값을*가진 요소를 삽입하고 *여기서* 힌트(성능 향상)를 사용하고 새로 삽입된 요소를 지정하는 이터레이터를 반환합니다. 알고 있는 요소에 인접할 수 있는 단일 요소를 삽입하는 데 사용합니다.

세 번째 멤버 함수는`first`시퀀스를 삽입합니다 [ , `last`). 다른 시퀀스에서 복사된 0개 이상의 요소를 삽입하는 데 사용합니다.

네 번째 멤버 함수는 *오른쪽에*지정된 시퀀스를 삽입합니다. 열거자가 설명한 시퀀스를 삽입하는 데 사용합니다.

각 요소 삽입은 제어된 시퀀스의 요소 수의 로그릿hm에 비례하는 시간이 걸립니다. 그러나 삽입 점에 인접한 요소를 지정하는 힌트가 주어지면 상각 된 일정한 시간에 삽입이 발생할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_set_insert.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
typedef Myset::pair_iter_bool Pairib;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value, unique and duplicate
    Pairib pair1 = c1.insert(L'x');
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",
        *pair1.first, pair1.second);

    pair1 = c1.insert(L'b');
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",
        *pair1.first, pair1.second);

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value with hint
    System::Console::WriteLine("insert(begin(), L'y') = {0}",
        *c1.insert(c1.begin(), L'y'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an iterator range
    Myset c2;
    Myset::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an enumeration
    Myset c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
insert(L'x') = [x True]
insert(L'b') = [b False]
a b c x
insert(begin(), L'y') = y
a b c x y
a b c x
a b c x y
```

## <a name="setiterator-stlclr"></a><a name="iterator"></a>설정 ::이터레이터 (STL / CLR)

제어되는 시퀀스에 대한 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>설명

형식은 제어된 시퀀스에 `T1` 대한 양방향 이터레이터 역할을 할 수 있는 지정되지 않은 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    Myset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setkey_comp-stlclr"></a><a name="key_comp"></a>설정::key_comp(STL/CLR)

두 키에 대한 순서 대리자를 복사합니다.

### <a name="syntax"></a>구문

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스를 정렬하는 데 사용되는 순서 대리자를 반환합니다. 이를 통해 두 키를 비교할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_set_key_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

// test a different ordering rule
    Myset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="setkey_compare-stlclr"></a><a name="key_compare"></a>설정::key_compare(STL/CLR)

두 키에 대한 순서 대리자입니다.

### <a name="syntax"></a>구문

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>설명

형식은 주요 인수의 순서를 결정하는 대리자의 동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_set_key_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

// test a different ordering rule
    Myset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="setkey_type-stlclr"></a><a name="key_type"></a>설정::key_type(STL/CLR)

정렬 키의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>설명

형식은 템플릿 매개 변수 *Key의*동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_set_key_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" using key_type
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myset::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setlower_bound-stlclr"></a><a name="lower_bound"></a>설정::lower_bound(STL/CLR)

지정된 키와 일치하는 범위의 시작을 찾습니다.

### <a name="syntax"></a>구문

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>매개 변수

*키*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

멤버 함수는 *키에* `X` 동등한 순서를 가지는 제어된 시퀀스의 첫 번째 요소를 결정합니다. 이러한 요소가 없으면 [set::end(STL/CLR)를](../dotnet/set-end-stl-clr.md)`()`반환합니다. 그렇지 않으면 을 지정하는 이터레이터를 반환합니다. `X` 지정된 키와 일치하는 제어된 시퀀스에서 현재 요소 시퀀스의 시작 부분을 찾는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_lower_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    System::Console::WriteLine("*lower_bound(L'a') = {0}",
        *c1.lower_bound(L'a'));
    System::Console::WriteLine("*lower_bound(L'b') = {0}",
        *c1.lower_bound(L'b'));
    return (0);
    }
```

```Output
a b c
lower_bound(L'x')==end() = True
*lower_bound(L'a') = a
*lower_bound(L'b') = b
```

## <a name="setmake_value-stlclr"></a><a name="make_value"></a>설정 ::make_value (STL / CLR)

값 개체를 생성합니다.

### <a name="syntax"></a>구문

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>매개 변수

*키*<br/>
사용할 키 값입니다.

### <a name="remarks"></a>설명

멤버 함수는 `value_type` 키가 *키인*개체를 반환합니다. 이 함수를 사용하여 다른 여러 멤버 함수와 함께 사용하기에 적합한 개체를 작성합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_make_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(Myset::make_value(L'a'));
    c1.insert(Myset::make_value(L'b'));
    c1.insert(Myset::make_value(L'c'));

// display contents " a b c"
    for each (Myset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setoperator-stlclr"></a><a name="op_as"></a>설정::연산자= (STL/CLR)

제어되는 시퀀스를 바꿉니다.

### <a name="syntax"></a>구문

```cpp
set<Key>% operator=(set<Key>% right);
```

#### <a name="parameters"></a>매개 변수

*오른쪽*<br/>
복사할 컨테이너입니다.

### <a name="remarks"></a>설명

멤버 연산자는 개체에 *바로* 복사한 다음 을 반환합니다. `*this` 이를 사용하여 제어된 시퀀스를 *오른쪽의*제어된 시퀀스의 복사본으로 바꿉니다.

### <a name="example"></a>예제

```cpp
// cliext_set_operator_as.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (Myset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2 = c1;
// display contents " a b c"
    for each (Myset::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="setrbegin-stlclr"></a><a name="rbegin"></a>설정::rbegin(STL/CLR)

제어되는 역방향 시퀀스의 시작을 지정합니다.

### <a name="syntax"></a>구문

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스의 마지막 요소를 지정하거나 빈 시퀀스의 시작 부분 만 초과하는 역방향 이터레이터를 반환합니다. 따라서 역방향 시퀀스의 `beginning`을 지정합니다. 이를 통해 역순으로 표시된 제어되는 시퀀스의 `current` 시작을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_set_rbegin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items in reversed sequence
    Myset::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
```

## <a name="setreference-stlclr"></a><a name="reference"></a>설정 ::참조 (STL / CLR)

요소에 대한 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>설명

형식은 요소에 대한 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    Myset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myset::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setrend-stlclr"></a><a name="rend"></a>설정 ::렌드 (STL / CLR)

제어되는 역방향 시퀀스의 끝을 지정합니다.

### <a name="syntax"></a>구문

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스의 시작 부분 바로 너머를 가리키는 역방향 이터레이터를 반환합니다. 따라서 역방향 시퀀스의 `end`을 지정합니다. 이를 통해 역순으로 표시된 제어되는 시퀀스의 `current` 끝을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_set_rend.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    Myset::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
```

## <a name="setreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>설정::reverse_iterator(STL/CLR)

제어되는 시퀀스에 대한 반대 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>설명

이 형식은 제어된 시퀀스에 대해 반대 반복기로 사용될 수 있는 지정되지 않은 `T3` 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" reversed
    Myset::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="setset-stlclr"></a><a name="set"></a>설정 ::설정 (STL / CLR)

컨테이너 개체를 만듭니다.

### <a name="syntax"></a>구문

```cpp
set();
explicit set(key_compare^ pred);
set(set<Key>% right);
set(set<Key>^ right);
template<typename InIter>
    setset(InIter first, InIter last);
template<typename InIter>
    set(InIter first, InIter last,
        key_compare^ pred);
set(System::Collections::Generic::IEnumerable<GValue>^ right);
set(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
```

#### <a name="parameters"></a>매개 변수

*첫 번째*<br/>
삽입할 범위의 시작.

*마지막*<br/>
삽입할 범위의 끝입니다.

*Pred*<br/>
제어된 시퀀스에 대한 조건자 정렬.

*오른쪽*<br/>
삽입할 개체 또는 범위입니다.

### <a name="remarks"></a>설명

생성자:

`set();`

기본 정렬 조건자와 `key_compare()`함께 요소가 없는 제어된 시퀀스를 초기화합니다. 기본 정렬 조건자와 함께 빈 초기 제어 시퀀스를 지정하는 데 사용합니다.

생성자:

`explicit set(key_compare^ pred);`

순서 조건자 지정을 사용하여 요소가 없는 제어된 시퀀스를 *초기화합니다.* 지정된 순서 지정 조건자와 함께 빈 초기 제어 시퀀스를 지정하는 데 사용합니다.

생성자:

`set(set<Key>% right);`

은 기본 순서 지정 조건자와 함께`right.begin()`[, `right.end()`시퀀스로 제어된 시퀀스를 초기화합니다. 기본 정렬 조건자와 함께 설정 개체 *오른쪽에*의해 제어 되는 시퀀스의 복사본인 초기 제어 된 시퀀스를 지정 하는 데 사용 합니다.

생성자:

`set(set<Key>^ right);`

은 기본 순서 지정 조건자와 함께`right->begin()`[, `right->end()`시퀀스로 제어된 시퀀스를 초기화합니다. 기본 정렬 조건자와 함께 설정 개체 *오른쪽에*의해 제어 되는 시퀀스의 복사본인 초기 제어 된 시퀀스를 지정 하는 데 사용 합니다.

생성자:

`template<typename InIter> set(InIter first, InIter last);`

은 기본 순서 지정 조건자와 함께`first`[, `last`시퀀스로 제어된 시퀀스를 초기화합니다. 이를 사용하여 제어된 시퀀스를 기본 순서 정렬 조건자와 함께 다른 시퀀스의 복사본으로 만듭니다.

생성자:

`template<typename InIter> set(InIter first, InIter last, key_compare^ pred);`

순서가 지정되는 조건자`first` *지정으로*제어된 시퀀스를 순서 [, ",)로 `last`초기화합니다. 이를 사용하여 지정된 순서 지정을 사용하여 제어된 시퀀스를 다른 시퀀스의 복사본으로 만듭니다.

생성자:

`set(System::Collections::Generic::IEnumerable<Key>^ right);`

기본 정렬 조건자와 함께 열거자 *오른쪽에*의해 지정 된 시퀀스로 제어 된 시퀀스를 초기화 합니다. 제어된 시퀀스를 기본 정렬 조건자와 함께 열거자가 설명한 다른 시퀀스의 복사본으로 만드는 데 사용합니다.

생성자:

`set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

순서 조건자가 미리 정해지도록 열거자 *오른쪽으로*지정한 시퀀스로 *pred*제어된 시퀀스를 초기화합니다. 제어된 시퀀스를 지정된 순서 지정어를 사용하여 열거자가 설명한 다른 시퀀스의 복사본으로 만드는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_construct.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
// construct an empty container
    Myset c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an ordering rule
    Myset c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range
    Myset c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range and an ordering rule
    Myset c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration
    Myset c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration and an ordering rule
    Myset c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct from a generic container
    Myset c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    Myset c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
a b c
size() = 0
c b a
a b c
c b a
a b c
c b a
c b a
a b c
```

## <a name="setsize-stlclr"></a><a name="size"></a>세트 ::크기 (STL / CLR)

요소 수를 계산합니다.

### <a name="syntax"></a>구문

```cpp
size_type size();
```

### <a name="remarks"></a>설명

멤버 함수는 제어되는 시퀀스의 길이를 반환합니다. 이 값을 사용하여 현재 제어된 시퀀스의 요소 수를 결정합니다. 시퀀스의 크기가 0이 아닌지 여부에 관계없이 [설정::empty(STL/CLR)를](../dotnet/set-empty-stl-clr.md)`()`참조하십시오.

### <a name="example"></a>예제

```cpp
// cliext_set_size.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

// add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 3 starting with 3
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="setsize_type-stlclr"></a><a name="size_type"></a>설정::size_type(STL/CLR)

두 요소 사이의 서명된 거리의 유형입니다.

### <a name="syntax"></a>구문

```cpp
typedef int size_type;
```

### <a name="remarks"></a>설명

형식은 음수가 아닌 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_size_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myset::size_type diff = 0;
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="setswap-stlclr"></a><a name="swap"></a>세트 ::스왑 (STL / CLR)

두 컨테이너의 내용을 바꿉니다.

### <a name="syntax"></a>구문

```cpp
void swap(set<Key>% right);
```

#### <a name="parameters"></a>매개 변수

*오른쪽*<br/>
콘텐츠와 바꿀 컨테이너입니다.

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스를 `this` *오른쪽으로*바꿉니다. 일정한 시간에 그렇게하고 예외를 throw하지 않습니다. 두 컨테이너의 내용을 교환하는 빠른 방법으로 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_swap.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    Myset c2;
    c2.insert(L'd');
    c2.insert(L'e');
    c2.insert(L'f');
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
d e f
d e f
a b c
```

## <a name="setto_array-stlclr"></a><a name="to_array"></a>설정::to_array(STL/CLR)

제어된 시퀀스를 새 배열로 복사합니다.

### <a name="syntax"></a>구문

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스를 포함하는 배열을 반환합니다. 이를 사용하여 배열 형식으로 제어된 시퀀스의 복사본을 가져옵니다.

### <a name="example"></a>예제

```cpp
// cliext_set_to_array.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// display the earlier array copy
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c d
a b c
```

## <a name="setupper_bound-stlclr"></a><a name="upper_bound"></a>설정::upper_bound(STL/CLR)

지정된 키와 일치하는 범위의 끝을 찾습니다.

### <a name="syntax"></a>구문

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>매개 변수

*키*<br/>
검색할 키 값입니다.

### <a name="remarks"></a>설명

멤버 함수는 *키에* `X` 동등한 순서를 가지는 제어된 시퀀스의 마지막 요소를 결정합니다. 이러한 요소가 존재하지 않거나 `X` 제어된 시퀀스의 마지막 요소인 경우 [set::end(STL/CLR)를](../dotnet/set-end-stl-clr.md)`()`반환합니다. 그렇지 않으면 첫 번째 요소를 넘어 `X`서 지정 하는 이터레이터를 반환 합니다. 지정된 키와 일치하는 제어된 시퀀스에서 현재 요소 시퀀스의 끝을 찾는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_upper_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    System::Console::WriteLine("*upper_bound(L'a') = {0}",
        *c1.upper_bound(L'a'));
    System::Console::WriteLine("*upper_bound(L'b') = {0}",
        *c1.upper_bound(L'b'));
    return (0);
    }
```

```Output
a b c
upper_bound(L'x')==end() = True
*upper_bound(L'a') = b
*upper_bound(L'b') = c
```

## <a name="setvalue_comp-stlclr"></a><a name="value_comp"></a>설정::value_comp(STL/CLR)

두 요소 값에 대한 순서 대리자를 복사합니다.

### <a name="syntax"></a>구문

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스를 정렬하는 데 사용되는 순서 대리자를 반환합니다. 두 요소 값을 비교하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_value_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="setvalue_compare-stlclr"></a><a name="value_compare"></a>설정::value_compare(STL/CLR)

두 요소 값에 대한 순서 대리자입니다.

### <a name="syntax"></a>구문

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>설명

형식은 해당 값 인수의 순서를 결정하는 대리자의 동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_set_value_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="setvalue_type-stlclr"></a><a name="value_type"></a>설정::value_type(STL/CLR)

요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>설명

이 형식은 `generic_value`의 동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_set_value_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" using value_type
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myset::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operator-set-stlclr"></a><a name="op_neq"></a>연산자!= (세트) (STL / CLR)

동일 비교를 나열하지 않습니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key>
    bool operator!=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 `!(left == right)`함수가 반환합니다. 두 집합이 요소별로 요소를 비교할 때 *왼쪽이* *오른쪽과* 동일하게 정렬되지 않았는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_operator_ne.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] != [a b c] is {0}",
        c1 != c1);
    System::Console::WriteLine("[a b c] != [a b d] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] != [a b c] is False
[a b c] != [a b d] is True
```

## <a name="operatorlt-set-stlclr"></a><a name="op_lt"></a>연산자(세트)&lt; (STL/CLR)

비교보다 적게 나열합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key>
    bool operator<(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수는 true를 반환하는 `i` `!(right[i] < left[i])` 경우 가장 낮은 `left[i] < right[i]`위치에 대해서도 true입니다. 그렇지 않으면 `left->size() < right->size()` 두 집합이 요소별로 요소를 비교할 때 *왼쪽이* *오른쪽* 앞에 정렬되었는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_operator_lt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] < [a b c] is {0}",
        c1 < c1);
    System::Console::WriteLine("[a b c] < [a b d] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] < [a b c] is False
[a b c] < [a b d] is True
```

## <a name="operatorlt-set-stlclr"></a><a name="op_lteq"></a>연산자&lt;= (세트) (STL / CLR)

비교보다 적거나 동일한 비교를 나열합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key>
    bool operator<=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 `!(right < left)`함수가 반환합니다. 두 집합이 요소별로 요소를 비교할 때 *왼쪽이* *오른쪽* 이후에 정렬되지 않았는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_operator_le.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] <= [a b c] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] <= [a b c] is True
[a b d] <= [a b c] is False
```

## <a name="operator-set-stlclr"></a><a name="op_eq"></a>연산자 = (세트) (STL / CLR)

동등한 비교를 나열합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key>
    bool operator==(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수는 *왼쪽* 및 *오른쪽으로* 제어되는 시퀀스의 길이가 같고 `left[i] ==` `right[i]`각 위치에 `i`대해 true를 반환합니다. 두 집합이 요소별로 요소를 비교할 때 *왼쪽이* *오른쪽과* 동일한 순서로 정렬되는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_operator_eq.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] == [a b c] is {0}",
        c1 == c1);
    System::Console::WriteLine("[a b c] == [a b d] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] == [a b c] is True
[a b c] == [a b d] is False
```

## <a name="operatorgt-set-stlclr"></a><a name="op_gt"></a>연산자(세트)&gt; (STL/CLR)

비교보다 큰 목록입니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key>
    bool operator>(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 `right` `<` `left`함수가 반환합니다. 두 집합이 요소별로 요소를 비교할 때 *왼쪽이* *오른쪽* 이후에 정렬되는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_operator_gt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] > [a b c] is {0}",
        c1 > c1);
    System::Console::WriteLine("[a b d] > [a b c] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] > [a b c] is False
[a b d] > [a b c] is True
```

## <a name="operatorgt-set-stlclr"></a><a name="op_gteq"></a>연산자&gt;= (세트) (STL / CLR)

비교보다 크거나 같음나열합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Key>
    bool operator>=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 `!(left < right)`함수가 반환합니다. 두 집합이 요소별로 요소를 비교할 때 *왼쪽이* *오른쪽* 앞에 정렬되지 않았는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_set_operator_ge.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] >= [a b c] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] >= [a b c] is True
[a b c] >= [a b d] is False
```
