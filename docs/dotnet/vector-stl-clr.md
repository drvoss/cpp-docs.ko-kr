---
title: vector(STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::vector
- cliext::vector::assign
- cliext::vector::at
- cliext::vector::back
- cliext::vector::back_item
- cliext::vector::begin
- cliext::vector::capacity
- cliext::vector::clear
- cliext::vector::const_iterator
- cliext::vector::const_reference
- cliext::vector::const_reverse_iterator
- cliext::vector::difference_type
- cliext::vector::empty
- cliext::vector::end
- cliext::vector::erase
- cliext::vector::front
- cliext::vector::front_item
- cliext::vector::generic_container
- cliext::vector::generic_iterator
- cliext::vector::generic_reverse_iterator
- cliext::vector::generic_value
- cliext::vector::insert
- cliext::vector::iterator
- cliext::vector::operator=
- cliext::vector::operator
- cliext::vector::pop_back
- cliext::vector::push_back
- cliext::vector::rbegin
- cliext::vector::reference
- cliext::vector::rend
- cliext::vector::reserve
- cliext::vector::resize
- cliext::vector::reverse_iterator
- cliext::vector::size
- cliext::vector::size_type
- cliext::vector::swap
- cliext::vector::to_array
- cliext::vector::value_type
- cliext::vector::vector
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> (vector) member [STL/CLR]
- operator>= member [STL/CLR]
- assign member [STL/CLR]
- at member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- capacity member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- erase member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- operator= member [STL/CLR]
- operator member [STL/CLR]
- pop_back member [STL/CLR]
- push_back member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reserve member [STL/CLR]
- resize member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
- vector member [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
ms.openlocfilehash: c6a001797e90bd7381358abb16612926442e8d9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371830"
---
# <a name="vector-stlclr"></a>vector(STL/CLR)

템플릿 클래스는 임의 액세스 권한이 있는 다양한 길이의 요소 시퀀스를 제어하는 개체에 대해 설명합니다. 컨테이너를 `vector` 사용하여 요소 시퀀스를 연속 저장소 블록으로 관리합니다. 블록은 필요에 따라 증가하는 배열로 구현됩니다.

아래 `GValue` 설명에서 후자가 참조 형식이 아니면 *값과* 동일합니다. `Value^`

## <a name="syntax"></a>구문

```cpp
template<typename Value>
    ref class vector
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::IVector<GValue>
    { ..... };
```

### <a name="parameters"></a>매개 변수

*값*<br/>
제어되는 시퀀스의 요소 형식입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<>

**네임 스페이스:** 클라이펙스트

## <a name="declarations"></a>선언

|형식 정의|Description|
|---------------------|-----------------|
|[vector::const_iterator(STL/CLR)](#const_iterator)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|
|[vector::const_reference(STL/CLR)](#const_reference)|요소에 대한 상수 참조의 형식입니다.|
|[vector::const_reverse_iterator(STL/CLR)](#const_reverse_iterator)|제어되는 시퀀스에 대한 상수 역방향 반복기의 형식입니다.|
|[vector::difference_type(STL/CLR)](#difference_type)|두 요소 사이의 부호가 있는 거리의 형식입니다.|
|[vector::generic_container(STL/CLR)](#generic_container)|컨테이너에 대한 일반 인터페이스의 형식입니다.|
|[vector::generic_iterator(STL/CLR)](#generic_iterator)|컨테이너의 일반 인터페이스에 대한 이터레이터의 형식입니다.|
|[vector::generic_reverse_iterator(STL/CLR)](#generic_reverse_iterator)|컨테이너의 일반 인터페이스에 대한 역방향 거역 의 형식입니다.|
|[vector::generic_value(STL/CLR)](#generic_value)|컨테이너에 대한 제네릭 인터페이스에 대한 요소의 형식입니다.|
|[vector::iterator(STL/CLR)](#iterator)|제어되는 시퀀스에 대한 반복기의 형식입니다.|
|[vector::reference(STL/CLR)](#reference)|요소에 대한 참조의 형식입니다.|
|[vector::reverse_iterator(STL/CLR)](#reverse_iterator)|제어되는 시퀀스에 대한 반대 반복기의 형식입니다.|
|[vector::size_type(STL/CLR)](#size_type)|두 요소 사이의 부호가 있는 거리의 형식입니다.|
|[vector::value_type(STL/CLR)](#value_type)|요소의 형식입니다.|

|멤버 함수|Description|
|---------------------|-----------------|
|[vector::assign(STL/CLR)](#assign)|모든 요소를 바꿉니다.|
|[vector::at(STL/CLR)](#at)|지정된 위치에 있는 요소에 액세스합니다.|
|[vector::back(STL/CLR)](#back)|마지막 요소에 액세스합니다.|
|[vector::begin(STL/CLR)](#begin)|제어되는 시퀀스의 시작을 지정합니다.|
|[vector::capacity(STL/CLR)](#capacity)|컨테이너에 할당된 스토리지의 크기를 보고합니다.|
|[vector::clear(STL/CLR)](#clear)|모든 요소를 제거합니다.|
|[vector::empty(STL/CLR)](#empty)|요소가 있는지 여부를 테스트합니다.|
|[vector::end(STL/CLR)](#end)|제어되는 시퀀스의 끝을 지정합니다.|
|[vector::erase(STL/CLR)](#erase)|지정된 위치에 있는 요소를 제거합니다.|
|[vector::front(STL/CLR)](#front)|첫 번째 요소에 액세스합니다.|
|[vector::insert(STL/CLR)](#insert)|지정된 위치에 요소를 추가합니다.|
|[vector::pop_back(STL/CLR)](#pop_back)|마지막 요소를 제거합니다.|
|[vector::push_back(STL/CLR)](#push_back)|새 마지막 요소를 추가합니다.|
|[vector::rbegin(STL/CLR)](#rbegin)|제어되는 역방향 시퀀스의 시작을 지정합니다.|
|[vector::rend(STL/CLR)](#rend)|제어되는 역방향 시퀀스의 끝을 지정합니다.|
|[vector::reserve(STL/CLR)](#reserve)|컨테이너에 대한 최소 성장 용량을 보장합니다.|
|[vector::resize(STL/CLR)](#resize)|요소 수를 변경합니다.|
|[vector::size(STL/CLR)](#size)|요소 수를 계산합니다.|
|[vector::swap(STL/CLR)](#swap)|두 컨테이너의 내용을 바꿉니다.|
|[vector::to_array(STL/CLR)](#to_array)|제어된 시퀀스를 새 배열로 복사합니다.|
|[vector::vector(STL/CLR)](#vector)|컨테이너 개체를 만듭니다.|

|속성|Description|
|--------------|-----------------|
|[vector::back_item(STL/CLR)](#back_item)|마지막 요소에 액세스합니다.|
|[vector::front_item(STL/CLR)](#front_item)|첫 번째 요소에 액세스합니다.|

|연산자|Description|
|--------------|-----------------|
|[vector::operator=(STL/CLR)](#op_as)|제어되는 시퀀스를 바꿉니다.|
|[vector::operator(STL/CLR)](#op)|지정된 위치에 있는 요소에 액세스합니다.|
|[연산자!= (벡터) (STL / CLR)](#op_neq)|개체가 `vector` 다른 `vector` 개체와 같지 않은지 확인합니다.|
|[연산자<(벡터) (STL/CLR)](#op_lt)|개체가 `vector` 다른 `vector` 개체보다 작은지 확인합니다.|
|[연산자<= (벡터) (STL / CLR)](#op_lteq)|개체가 `vector` 다른 `vector` 개체보다 적거나 같는지 여부를 결정합니다.|
|[연산자 = ==(벡터) (STL/CLR)](#op_eq)|개체가 `vector` 다른 `vector` 개체와 동일한지 여부를 결정합니다.|
|[operator> (vector)(STL/CLR)](#op_gt)|개체가 `vector` 다른 `vector` 개체보다 큰지 여부를 결정합니다.|
|[연산자>= (벡터) (STL / CLR)](#op_gteq)|개체가 `vector` 다른 `vector` 개체보다 크거나 같는지 여부를 결정합니다.|

## <a name="interfaces"></a>인터페이스

|인터페이스|Description|
|---------------|-----------------|
|<xref:System.ICloneable>|개체를 복제합니다.|
|<xref:System.Collections.IEnumerable>|요소를 통해 시퀀스합니다.|
|<xref:System.Collections.ICollection>|요소 그룹을 유지 관리합니다.|
|<xref:System.Collections.Generic.IEnumerable%601>|입력된 요소를 통해 시퀀스합니다.|
|<xref:System.Collections.Generic.ICollection%601>|형식이 입력된 요소의 그룹을 유지 관리합니다.|
|<xref:System.Collections.Generic.IList%601>|형식이 지정된 요소의 정렬된 그룹을 유지 관리합니다.|
|IVector<값\>|일반 컨테이너를 유지 관리합니다.|

## <a name="remarks"></a>설명

개체는 필요에 따라 증가하는 *Value* 요소의 저장된 배열을 통해 제어하는 시퀀스에 대한 저장소를 할당하고 해제합니다. 성장은 새 요소를 가하는 비용이 상수 시간을 상각하는 방식으로 발생합니다. 즉, 제어된 시퀀스의 길이가 커짐에 따라 끝부분에 요소를 추가하는 비용은 평균적으로 증가하지 않습니다. 따라서 벡터는 [STL/CLR(템플릿 클래스 스택)에](../dotnet/stack-stl-clr.md)대한 기본 컨테이너에 적합한 후보입니다.

A는 `vector` 임의 액세스 이터레이터를 지원하므로 첫 번째(앞) 요소에 대해 0에서 마지막(뒤로) 요소에 대해 `size() - 1` 계산하는 수치 위치가 지정된 요소를 직접 참조할 수 있습니다. 또한 벡터가 [STL/CLR(템플릿 클래스 priority_queue)에](../dotnet/priority-queue-stl-clr.md)대한 기본 컨테이너에 적합한 후보임을 의미합니다.

벡터 이터레이터는 핸들을 지정하는 요소의 바이어스와 함께 관련 벡터 오브젝트에 저장합니다. 연관된 컨테이너 개체에만 이터레이터를 사용할 수 있습니다. 벡터 요소의 바이어스는 해당 위치와 동일합니다.

요소를 삽입하거나 지워면 지정된 위치에 저장된 요소 값이 변경될 수 있으므로 이터레이터가 지정한 값도 변경될 수 있습니다. (컨테이너는 인서트를 삽입하기 전에 구멍을 만들거나 지우기 후 구멍을 채우기 위해 요소를 위 또는 아래로 복사해야 할 수 있습니다.) 그럼에도 불구하고 벡터 이터레이터는 바이어스가 범위에 `[0, size()]`있는 한 유효합니다. 또한 유효한 이터레이터는 참조할 수 없는 상태로 유지되므로 편향이 `size()`같지 않은 한 지정한 요소 값에 액세스하거나 변경할 수 있습니다.

요소를 지우거나 제거하면 소멸자가 저장된 값에 대해 호출됩니다. 컨테이너를 파괴하여 모든 요소를 지웁습니다. 따라서 요소 형식이 ref 클래스인 컨테이너는 컨테이너보다 오래 되는 요소가 없음을 보장합니다. 그러나 핸들 컨테이너가 해당 요소를 파괴하지는 않습니다.

## <a name="members"></a>멤버

## <a name="vectorassign-stlclr"></a><a name="assign"></a>벡터 ::할당 (STL / CLR)

모든 요소를 바꿉니다.

### <a name="syntax"></a>구문

```cpp
void assign(size_type count, value_type val);
template<typename InIt>
    void assign(InIt first, InIt last);
void assign(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>매개 변수

*count*<br/>
삽입할 요소의 수입니다.

*첫 번째*<br/>
삽입할 범위의 시작.

*마지막*<br/>
삽입할 범위의 끝입니다.

*오른쪽*<br/>
삽입할 열거형입니다.

*발*<br/>
삽입할 요소의 값입니다.

### <a name="remarks"></a>설명

첫 번째 멤버 함수는 제어된 시퀀스를 값 *값 값값의* *카운트* 요소의 반복으로 바꿉니다. 컨테이너를 모두 동일한 값을 가진 요소로 채우는 데 사용합니다.

정수 형식인 경우 `InIt` 두 번째 멤버 함수는 와 `assign((size_type)first, (value_type)last)`동일하게 작동합니다. 그렇지 않으면, 제어된 시퀀스를`first`시퀀스로 대체한다 [ , `last`). 제어된 시퀀스를 다른 시퀀스를 복사하는 데 사용합니다.

세 번째 멤버 함수는 제어된 시퀀스를 열거자 *오른쪽으로*지정된 시퀀스로 바꿉니다. 제어된 시퀀스를 열거자가 설명한 시퀀스의 복사본으로 만드는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_assign.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// assign a repetition of values
    cliext::vector<wchar_t> c2;
    c2.assign(6, L'x');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign an iterator range
    c2.assign(c1.begin(), c1.end() - 1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign an enumeration
    c2.assign(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
x x x x x x
a b
a b c
```

## <a name="vectorat-stlclr"></a><a name="at"></a>벡터 :에서 (STL / CLR)

지정된 위치에 있는 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
reference at(size_type pos);
```

#### <a name="parameters"></a>매개 변수

*Pos*<br/>
액세스할 요소의 위치입니다.

### <a name="remarks"></a>설명

멤버 함수는 위치 *pos에서*제어된 시퀀스의 요소에 대한 참조를 반환합니다. 이 것을 사용하여 위치를 알고 있는 요소를 읽거나 작성합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_at.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" using at
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

// change an entry and redisplay
    c1.at(1) = L'x';
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a x c
```

## <a name="vectorback-stlclr"></a><a name="back"></a>벡터 :뒤 (STL / CLR)

마지막 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
reference back();
```

### <a name="remarks"></a>설명

멤버 함수는 비어 있어야 하는 제어된 시퀀스의 마지막 요소에 대한 참조를 반환합니다. 이 요소는 존재하는 것을 알고 있을 때 마지막 요소에 액세스하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("back() = {0}", c1.back());

// alter last item and reinspect
    c1.back() = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back() = c
a b x
```

## <a name="vectorback_item-stlclr"></a><a name="back_item"></a>벡터 :back_item (STL / CLR)

마지막 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
property value_type back_item;
```

### <a name="remarks"></a>설명

속성은 비어 있어야 하는 제어된 시퀀스의 마지막 요소에 액세스합니다. 마지막 요소가 존재한다는 것을 알고 있을 때 마지막 요소를 읽거나 쓰는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_back_item.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("back_item = {0}", c1.back_item);

// alter last item and reinspect
    c1.back_item = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back_item = c
a b x
```

## <a name="vectorbegin-stlclr"></a><a name="begin"></a>벡터 ::시작 (STL / CLR)

제어되는 시퀀스의 시작을 지정합니다.

### <a name="syntax"></a>구문

```cpp
iterator begin();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스의 첫 번째 요소를 지정하거나 빈 시퀀스의 끝 바로 너머에 있는 임의 액세스 이터레이터를 반환합니다. 이를 통해 제어되는 시퀀스의 `current` 시작을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_begin.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    cliext::vector<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);

// alter first two items and reinspect
    *--it = L'x';
    *++it = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*begin() = a
*++begin() = b
x y c
```

## <a name="vectorcapacity-stlclr"></a><a name="capacity"></a>벡터 ::용량 (STL / CLR)

컨테이너에 할당된 스토리지의 크기를 보고합니다.

### <a name="syntax"></a>구문

```cpp
size_type capacity();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스를 보유하기 위해 현재 할당된 저장소를 반환하며, 값은 [벡터::크기(STL/CLR)만큼](../dotnet/vector-size-stl-clr.md)`()`큽니다. 제어된 시퀀스에 대한 저장소를 다시 할당하기 전에 컨테이너가 얼마나 늘어날 수 있는지 결정하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_capacity.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

// increase capacity
    cliext::vector<wchar_t>::size_type cap = c1.capacity();
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        cap, c1.size() <= cap);
    c1.reserve(cap + 5);
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        c1.capacity(), cap + 5 <= c1.capacity());
    return (0);
    }
```

```Output
a b c
capacity() = 4, ok = True
capacity() = 9, ok = True
```

## <a name="vectorclear-stlclr"></a><a name="clear"></a>벡터 :: 클리어 (STL / CLR)

모든 요소를 제거합니다.

### <a name="syntax"></a>구문

```cpp
void clear();
```

### <a name="remarks"></a>설명

멤버 함수는 [벡터::지우기(STL/CLR)](../dotnet/vector-erase-stl-clr.md) `(` [벡터:::begin(STL/CLR)](../dotnet/vector-begin-stl-clr.md) `(),` [벡터::end(STL/CLR)를](../dotnet/vector-end-stl-clr.md)`())`효과적으로 호출합니다. 제어된 시퀀스가 비어 있는지 확인하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_clear.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

// add elements and clear again
    c1.push_back(L'a');
    c1.push_back(L'b');

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

## <a name="vectorconst_iterator-stlclr"></a><a name="const_iterator"></a>벡터:const_iterator(STL/CLR)

제어되는 시퀀스에 대한 상수 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>설명

형식은 제어된 시퀀스에 `T2` 대한 일정한 임의 액세스 이터레이터 역할을 할 수 있는 지정되지 않은 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_const_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorconst_reference-stlclr"></a><a name="const_reference"></a>벡터 :const_reference (STL / CLR)

요소에 대한 상수 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>설명

형식은 요소에 대한 상수 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_const_reference.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        cliext::vector<wchar_t>::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>벡터::const_reverse_iterator(STL/CLR)

제어된 시퀀스에 대한 상수 역방향 이터레이터의 유형입니다.

### <a name="syntax"></a>구문

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>설명

형식은 제어된 시퀀스에 `T4` 대한 상수 역방향 거역으로 사용할 수 있는 지정되지 않은 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" reversed
    cliext::vector<wchar_t>::const_reverse_iterator crit = c1.rbegin();
    cliext::vector<wchar_t>::const_reverse_iterator crend = c1.rend();
    for (; crit != crend; ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="vectordifference_type-stlclr"></a><a name="difference_type"></a>벡터::difference_type(STL/CLR)

두 요소 사이의 서명된 거리의 유형입니다.

### <a name="syntax"></a>구문

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>설명

형식은 서명된 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_difference_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    cliext::vector<wchar_t>::difference_type diff = 0;
    for (cliext::vector<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it) ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

// compute negative difference
    diff = 0;
    for (cliext::vector<wchar_t>::iterator it = c1.end();
        it != c1.begin(); --it) --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="vectorempty-stlclr"></a><a name="empty"></a>벡터 ::비어 있음 (STL / CLR)

요소가 있는지 여부를 테스트합니다.

### <a name="syntax"></a>구문

```cpp
bool empty();
```

### <a name="remarks"></a>설명

멤버 함수는 빈 제어되는 시퀀스에 대해 true를 반환합니다. [벡터::크기(STL/CLR)와](../dotnet/vector-size-stl-clr.md)`() == 0`동일합니다. 벡터가 비어 있는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_empty.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

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

## <a name="vectorend-stlclr"></a><a name="end"></a>벡터 ::끝 (STL / CLR)

제어되는 시퀀스의 끝을 지정합니다.

### <a name="syntax"></a>구문

```cpp
iterator end();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스의 끝 바로 너머를 가리키는 임의 액세스 이터레이터를 반환합니다. 이를 통해 제어되는 시퀀스의 `current` 끝을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_end.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last two items
    cliext::vector<wchar_t>::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);

// alter first two items and reinspect
    *--it = L'x';
    *++it = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
a x y
```

## <a name="vectorerase-stlclr"></a><a name="erase"></a>벡터 ::지우기 (STL / CLR)

지정된 위치에 있는 요소를 제거합니다.

### <a name="syntax"></a>구문

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
```

#### <a name="parameters"></a>매개 변수

*첫 번째*<br/>
지울 범위의 시작.

*마지막*<br/>
지울 범위의 끝입니다.

*어디*<br/>
지울 요소입니다.

### <a name="remarks"></a>설명

첫 번째 멤버 함수는 *위치를*가리키는 제어된 시퀀스의 요소를 제거합니다. 단일 요소를 제거하는 데 사용합니다.

두 번째 멤버 함수는 [`first`, `last`]의 범위에서 제어되는 시퀀스의 요소를 제거합니다. 이 요소를 사용하여 0개 이상의 연속 요소를 제거합니다.

두 멤버 함수는 제거된 요소 또는 [벡터::end(STL/CLR)](../dotnet/vector-end-stl-clr.md) `()` 외에 남아 있는 첫 번째 요소를 지정하는 이터레이터를 반환합니다.

요소를 지길 때 요소 복사본 수는 지우기 끝과 시퀀스의 끝 사이의 요소 수에 선형입니다. (시퀀스의 양쪽 끝에서 하나 이상의 요소를 지거할 때 요소 복사본이 발생하지 않습니다.)

### <a name="example"></a>예제

```cpp
// cliext_vector_erase.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

// add elements and display " b c d e"
    c1.push_back(L'd');
    c1.push_back(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// erase all but end
    cliext::vector<wchar_t>::iterator it = c1.end();
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

## <a name="vectorfront-stlclr"></a><a name="front"></a>벡터 :전면 (STL / CLR)

첫 번째 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
reference front();
```

### <a name="remarks"></a>설명

멤버 함수는 비어 있어야 하는 제어된 시퀀스의 첫 번째 요소에 대한 참조를 반환합니다. 첫 번째 요소가 존재한다는 것을 알고 있을 때 이를 사용하여 첫 번째 요소를 읽거나 작성합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_front.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first item
    System::Console::WriteLine("front() = {0}", c1.front());

// alter first item and reinspect
    c1.front() = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front() = a
x b c
```

## <a name="vectorfront_item-stlclr"></a><a name="front_item"></a>벡터::front_item (STL/CLR)

첫 번째 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
property value_type front_item;
```

### <a name="remarks"></a>설명

속성은 비어 있어야 하는 제어된 시퀀스의 첫 번째 요소에 액세스합니다. 첫 번째 요소가 존재한다는 것을 알고 있을 때 이를 사용하여 첫 번째 요소를 읽거나 작성합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_front_item.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first item
    System::Console::WriteLine("front_item = {0}", c1.front_item);

// alter first item and reinspect
    c1.front_item = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front_item = a
x b c
```

## <a name="vectorgeneric_container-stlclr"></a><a name="generic_container"></a>벡터::generic_container (STL/CLR)

컨테이너에 대한 일반 인터페이스의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::
    IVector<generic_value>
    generic_container;
```

### <a name="remarks"></a>설명

형식은 이 템플릿 컨테이너 클래스의 일반 인터페이스를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_generic_container.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    gc1->insert(gc1->end(), L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify original and display generic
    c1.push_back(L'e');

    System::Collections::IEnumerator^ enum1 =
        gc1->GetEnumerator();
    while (enum1->MoveNext())
        System::Console::Write("{0} ", enum1->Current);
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

## <a name="vectorgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>벡터:generic_iterator(STL/CLR)

컨테이너의 일반 인터페이스와 함께 사용할 이터레이터의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerRandomAccessIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>설명

형식은 이 템플릿 컨테이너 클래스의 제네릭 인터페이스와 함께 사용할 수 있는 제네릭 거터레이터를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_generic_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a a c
```

## <a name="vectorgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>벡터:generic_reverse_iterator(STL/CLR)

컨테이너의 일반 인터페이스와 함께 사용할 역방향 거역 의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value> generic_reverse_iterator;
```

### <a name="remarks"></a>설명

형식은 이 템플릿 컨테이너 클래스의 제네릭 인터페이스와 함께 사용할 수 있는 제네릭 역방향 거점을 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a c c
```

## <a name="vectorgeneric_value-stlclr"></a><a name="generic_value"></a>벡터::generic_value (STL/CLR)

컨테이너의 제네릭 인터페이스와 함께 사용할 요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>설명

형식은 이 템플릿 컨테이너 `GValue` 클래스의 일반 인터페이스와 함께 사용할 저장된 요소 값을 설명하는 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_generic_value.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a a c
```

## <a name="vectorinsert-stlclr"></a><a name="insert"></a>벡터 ::삽입 (STL / CLR)

지정된 위치에 요소를 추가합니다.

### <a name="syntax"></a>구문

```cpp
iterator insert(iterator where, value_type val);
void insert(iterator where, size_type count, value_type val);
template<typename InIt>
    void insert(iterator where, InIt first, InIt last);
void insert(iterator where,
    System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>매개 변수

*count*<br/>
삽입할 요소의 수입니다.

*첫 번째*<br/>
삽입할 범위의 시작.

*마지막*<br/>
삽입할 범위의 끝입니다.

*오른쪽*<br/>
삽입할 열거형입니다.

*발*<br/>
삽입할 요소의 값입니다.

*어디*<br/>
어디에 컨테이너에 삽입 하기 전에.

### <a name="remarks"></a>설명

각 멤버 함수는 요소가 제어된 시퀀스의 *위치를* 가리키기 전에 나머지 카페랜드에 의해 지정된 시퀀스를 삽입합니다.

첫 번째 멤버 함수는 값 *val이* 있는 요소를 삽입하고 새로 삽입된 요소를 지정하는 이터레이터를 반환합니다. 이를 사용하여 이 요소로 지정한 장소 앞에 단일 요소를 삽입합니다.

두 번째 멤버 함수는 값 *값 값의* *카운트* 요소의 반복을 삽입합니다. 동일한 값의 모든 복사본인 0개 이상의 연속 요소를 삽입하는 데 사용합니다.

`InIt`가 정수 형식이면 세 번째 멤버 함수는 `insert(where, (size_type)first, (value_type)last)`와 동일하게 동작합니다. 그렇지 않으면 시퀀스를`first`삽입합니다 . `last` 다른 시퀀스에서 복사된 0개 이상의 연속 요소를 삽입하는 데 사용합니다.

네 번째 멤버 함수는 *오른쪽에*지정된 시퀀스를 삽입합니다. 열거자가 설명한 시퀀스를 삽입하는 데 사용합니다.

단일 요소를 삽입할 때 요소 복사 수는 삽입 점과 시퀀스의 끝 사이의 요소 수에 선형입니다. (시퀀스의 양쪽 끝에 하나 이상의 요소를 삽입할 때 요소 복사본이 발생하지 않습니다.) 입력 `InIt` 이터레이터인 경우 세 번째 멤버 함수는 시퀀스의 각 요소에 대해 단일 삽입을 효과적으로 수행합니다. 그렇지 않으면 요소를 `N` 삽입할 때 요소 복사 수가 `N` 선형이고 삽입 점과 시퀀스의 끝 사이의 요소 수가 더해지어집니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_insert.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value using iterator
    cliext::vector<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",
        *c1.insert(++it, L'x'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a repetition of values
    cliext::vector<wchar_t> c2;
    c2.insert(c2.begin(), 2, L'y');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an iterator range
    it = c1.end();
    c2.insert(c2.end(), c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an enumeration
    c2.insert(c2.begin(),   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
insert(begin()+1, L'x') = x
a x b c
y y
y y a x b
a x b c y y a x b
```

## <a name="vectoriterator-stlclr"></a><a name="iterator"></a>벡터 ::이터레이터 (STL / CLR)

제어되는 시퀀스에 대한 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>설명

형식은 제어된 시퀀스에 `T1` 대한 임의 액세스 이터레이터 역할을 할 수 있는 지정되지 않은 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    cliext::vector<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();

// alter first element and redisplay
    it = c1.begin();
    *it = L'x';
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
x b c
```

## <a name="vectoroperator-stlclr"></a><a name="op_as"></a>벡터::연산자= (STL/CLR)

제어되는 시퀀스를 바꿉니다.

### <a name="syntax"></a>구문

```cpp
vector<Value>% operator=(vector<Value>% right);
```

#### <a name="parameters"></a>매개 변수

*오른쪽*<br/>
복사할 컨테이너입니다.

### <a name="remarks"></a>설명

멤버 연산자는 개체에 *바로* 복사한 다음 을 반환합니다. `*this` 이를 사용하여 제어된 시퀀스를 *오른쪽의*제어된 시퀀스의 복사본으로 바꿉니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_operator_as.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2 = c1;
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="vectoroperatorstlclr"></a><a name="op"></a>벡터 ::연산자 (STL / CLR)

지정된 위치에 있는 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
reference operator[](size_type pos);
```

#### <a name="parameters"></a>매개 변수

*Pos*<br/>
액세스할 요소의 위치입니다.

### <a name="remarks"></a>설명

멤버 연산자는 위치 *pos에서*요소에 대한 참조를 반환합니다. 이를 사용하여 알고 있는 위치에 있는 요소에 액세스합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_operator_sub.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" using subscripting
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();

// change an entry and redisplay
    c1[1] = L'x';
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a x c
```

## <a name="vectorpop_back-stlclr"></a><a name="pop_back"></a>벡터::pop_back(STL/CLR)

마지막 요소를 제거합니다.

### <a name="syntax"></a>구문

```cpp
void pop_back();
```

### <a name="remarks"></a>설명

멤버 함수는 비어 있어야 하는 제어된 시퀀스의 마지막 요소를 제거합니다. 뒤쪽의 한 요소씩 벡터를 줄이는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_pop_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// pop an element and redisplay
    c1.pop_back();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b
```

## <a name="vectorpush_back-stlclr"></a><a name="push_back"></a>벡터::push_back(STL/CLR)

새 마지막 요소를 추가합니다.

### <a name="syntax"></a>구문

```cpp
void push_back(value_type val);
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스의 끝에 값이 `val` 있는 요소를 삽입합니다. 벡터에 다른 요소를 추가하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_push_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorrbegin-stlclr"></a><a name="rbegin"></a>벡터::rbegin(STL/CLR)

제어되는 역방향 시퀀스의 시작을 지정합니다.

### <a name="syntax"></a>구문

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스의 마지막 요소를 지정하거나 빈 시퀀스의 시작 부분 만 초과하는 역방향 이터레이터를 반환합니다. 따라서 역방향 시퀀스의 `beginning`을 지정합니다. 이를 통해 역순으로 표시된 제어되는 시퀀스의 `current` 시작을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_rbegin.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items in reversed sequence
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);

// alter first two items and reinspect
    *--rit = L'x';
    *++rit = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
a y x
```

## <a name="vectorreference-stlclr"></a><a name="reference"></a>벡터 ::참조 (STL / CLR)

요소에 대한 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>설명

형식은 요소에 대한 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_reference.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    cliext::vector<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::vector<wchar_t>::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();

// modify contents " a b c"
    for (it = c1.begin(); it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::vector<wchar_t>::reference ref = *it;

        ref += (wchar_t)(L'A' - L'a');
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
A B C
```

## <a name="vectorrend-stlclr"></a><a name="rend"></a>벡터 ::rend (STL / CLR)

제어되는 역방향 시퀀스의 끝을 지정합니다.

### <a name="syntax"></a>구문

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스의 시작 부분 바로 너머를 가리키는 역방향 이터레이터를 반환합니다. 따라서 역방향 시퀀스의 `end`을 지정합니다. 이를 통해 역순으로 표시된 제어되는 시퀀스의 `current` 끝을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_rend.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);

// alter first two items and reinspect
    *--rit = L'x';
    *++rit = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
y x c
```

## <a name="vectorreserve-stlclr"></a><a name="reserve"></a>벡터 ::예약 (STL / CLR)

컨테이너에 대한 최소 성장 용량을 보장합니다.

### <a name="syntax"></a>구문

```cpp
void reserve(size_type count);
```

#### <a name="parameters"></a>매개 변수

*count*<br/>
컨테이너의 새 최소 용량입니다.

### <a name="remarks"></a>설명

멤버 함수는 `capacity()` 이제부터 최소 *개수를*반환합니다. 컨테이너가 지정된 크기로 커지기 전까지 제어된 시퀀스에 대한 저장소를 다시 할당할 필요가 없도록 하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_reserve.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

// increase capacity
    cliext::vector<wchar_t>::size_type cap = c1.capacity();
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        cap, c1.size() <= cap);
    c1.reserve(cap + 5);
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        c1.capacity(), cap + 5 <= c1.capacity());
    return (0);
    }
```

```Output
a b c
capacity() = 4, ok = True
capacity() = 9, ok = True
```

## <a name="vectorresize-stlclr"></a><a name="resize"></a>벡터 ::크기 조정 (STL / CLR)

요소 수를 변경합니다.

### <a name="syntax"></a>구문

```cpp
void resize(size_type new_size);
void resize(size_type new_size, value_type val);
```

#### <a name="parameters"></a>매개 변수

*new_size*<br/>
제어 된 시퀀스의 새로운 크기입니다.

*발*<br/>
패딩 요소의 값입니다.

### <a name="remarks"></a>설명

멤버 함수는 모두 [벡터::size(STL/CLR)가](../dotnet/vector-size-stl-clr.md) `()` 이제부터 *new_size*반환되도록 합니다. 제어된 시퀀스를 더 길게 만들어야 하는 경우 첫 `value_type()`번째 멤버 함수는 값을 가진 요소를 적용하고 두 번째 멤버 함수는 값 *값으로*요소를 가합니다. 제어된 시퀀스를 짧게 만들기 위해 두 멤버 함수모두 마지막 요소 [벡터::size(STL/CLR)](../dotnet/vector-size-stl-clr.md) `() -` `new_size` 시간을 효과적으로 지웁니다. 제어된 시퀀스에 현재 제어된 시퀀스를 트리밍하거나 패딩하여 *new_size*크기가 있는지 확인하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_resize.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
// construct an empty container and pad with default values
    cliext::vector<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());
    c1.resize(4);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

// resize to empty
    c1.resize(0);
    System::Console::WriteLine("size() = {0}", c1.size());

// resize and pad
    c1.resize(5, L'x');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
0 0 0 0
size() = 0
x x x x x
```

## <a name="vectorreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>벡터 ::reverse_iterator (STL / CLR)

제어되는 시퀀스에 대한 반대 반복기의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>설명

이 형식은 제어된 시퀀스에 대해 반대 반복기로 사용될 수 있는 지정되지 않은 `T3` 형식의 개체를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" reversed
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();

// alter first element and redisplay
    rit = c1.rbegin();
    *rit = L'x';
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
x b a
```

## <a name="vectorsize-stlclr"></a><a name="size"></a>벡터 :: 크기 (STL / CLR)

요소 수를 계산합니다.

### <a name="syntax"></a>구문

```cpp
size_type size();
```

### <a name="remarks"></a>설명

멤버 함수는 제어되는 시퀀스의 길이를 반환합니다. 이 값을 사용하여 현재 제어된 시퀀스의 요소 수를 결정합니다. 시퀀스의 크기가 영하지 않은지 여부만 신경 쓰는 경우 [vector::empty(STL/CLR)를](../dotnet/vector-empty-stl-clr.md)`()`참조하십시오.

### <a name="example"></a>예제

```cpp
// cliext_vector_size.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

// clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

// add elements and clear again
    c1.push_back(L'a');
    c1.push_back(L'b');
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

## <a name="vectorsize_type-stlclr"></a><a name="size_type"></a>벡터::size_type(STL/CLR)

두 요소 사이의 부호가 있는 거리의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef int size_type;
```

### <a name="remarks"></a>설명

형식은 음수가 아닌 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_size_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    cliext::vector<wchar_t>::size_type diff = c1.end() - c1.begin();
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="vectorswap-stlclr"></a><a name="swap"></a>벡터 ::스왑 (STL / CLR)

두 컨테이너의 내용을 바꿉니다.

### <a name="syntax"></a>구문

```cpp
void swap(vector<Value>% right);
```

#### <a name="parameters"></a>매개 변수

*오른쪽*<br/>
콘텐츠와 바꿀 컨테이너입니다.

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스를 `*this` *오른쪽으로*바꿉니다. 일정한 시간에 그렇게하고 예외를 throw하지 않습니다. 두 컨테이너의 내용을 교환하는 빠른 방법으로 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_swap.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    cliext::vector<wchar_t> c2(5, L'x');
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

## <a name="vectorto_array-stlclr"></a><a name="to_array"></a>벡터::to_array(STL/CLR)

제어된 시퀀스를 새 배열로 복사합니다.

### <a name="syntax"></a>구문

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>설명

멤버 함수는 제어된 시퀀스를 포함하는 배열을 반환합니다. 이를 사용하여 배열 형식으로 제어된 시퀀스의 복사본을 가져옵니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_to_array.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.push_back(L'd');
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

## <a name="vectorvalue_type-stlclr"></a><a name="value_type"></a>벡터::value_type(STL/CLR)

요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>설명

형식은 템플릿 매개 변수 *값의*동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_value_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" using value_type
    for (cliext::vector<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        {   // store element in value_type object
        cliext::vector<wchar_t>::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorvector-stlclr"></a><a name="vector"></a>벡터 :벡터 (STL / CLR)

컨테이너 개체를 만듭니다.

### <a name="syntax"></a>구문

```cpp
vector();
vector(vector<Value>% right);
vector(vector<Value>^ right);
explicit vector(size_type count);
vector(size_type count, value_type val);
template<typename InIt>
    vector(InIt first, InIt last);
vector(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>매개 변수

*count*<br/>
삽입할 요소의 수입니다.

*첫 번째*<br/>
삽입할 범위의 시작.

*마지막*<br/>
삽입할 범위의 끝입니다.

*오른쪽*<br/>
삽입할 개체 또는 범위입니다.

*발*<br/>
삽입할 요소의 값입니다.

### <a name="remarks"></a>설명

생성자:

`vector();`

요소를 지정하지 않고 제어된 시퀀스를 초기화합니다. 빈 초기 제어 시퀀스를 지정하는 데 사용합니다.

생성자:

`vector(vector<Value>% right);`

제어된 시퀀스를 시퀀스로 `right.end()`초기화합니다.`right.begin()` 벡터 개체 *오른쪽에*의해 제어 되는 시퀀스의 복사본인 초기 제어 된 시퀀스를 지정 하는 데 사용 합니다.

생성자:

`vector(vector<Value>^ right);`

제어된 시퀀스를 시퀀스로 `right->end()`초기화합니다.`right->begin()` 이를 사용하여 핸들이 올바른 벡터 오브젝트에 의해 제어되는 시퀀스의 복사본인 초기 제어 시퀀스를 *지정합니다.*

생성자:

`explicit vector(size_type count);`

은 각각 *카운트* 요소로 제어된 `value_type()`시퀀스를 초기화합니다. 이 값을 사용하여 기본값을 가진 모든 요소로 컨테이너를 채웁니다.

생성자:

`vector(size_type count, value_type val);`

은 값 *val을*가진 *카운트* 요소각각으로 제어된 시퀀스를 초기화합니다. 컨테이너를 모두 동일한 값을 가진 요소로 채우는 데 사용합니다.

생성자:

`template<typename InIt>`

`vector(InIt first, InIt last);`

제어된 시퀀스를 시퀀스로 `last`초기화합니다.`first` 제어된 시퀀스를 다른 시퀀스의 복사본으로 만드는 데 사용합니다.

생성자:

`vector(System::Collections::Generic::IEnumerable<Value>^ right);`

열거자 *오른쪽에*의해 지정된 시퀀스로 제어된 시퀀스를 초기화합니다. 제어된 시퀀스를 열거자가 설명하는 다른 시퀀스의 복사본으로 만드는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_construct.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
// construct an empty container
    cliext::vector<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());

// construct with a repetition of default values
    cliext::vector<wchar_t> c2(3);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

// construct with a repetition of values
    cliext::vector<wchar_t> c3(6, L'x');
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range
    cliext::vector<wchar_t>::iterator it = c3.end();
    cliext::vector<wchar_t> c4(c3.begin(), --it);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    cliext::vector<wchar_t> c7(c3);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying a container handle
    cliext::vector<wchar_t> c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
size() = 0
0 0 0
x x x x x x
x x x x x
x x x x x x
x x x x x x
x x x x x x
```

## <a name="operator-vector-stlclr"></a><a name="op_neq"></a>연산자!= (벡터) (STL / CLR)

벡터가 같지 않습니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value>
    bool operator!=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 `!(left == right)`함수가 반환합니다. 두 벡터를 요소별로 비교할 때 *왼쪽이* *오른쪽과* 동일하게 정렬되지 않았는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_operator_ne.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorlt-vector-stlclr"></a><a name="op_lt"></a>연산자(벡터)&lt; (STL/CLR)

비교보다 벡터가 적습니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value>
    bool operator<(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수는 true를 반환하는 `i` `!(right[i] < left[i])` 경우 가장 낮은 `left[i] < right[i]`위치에 대해서도 true입니다. 그렇지 않으면 `left->size() < right->size()` 두 벡터가 요소별로 요소를 비교할 때 *왼쪽이* *오른쪽* 앞에 정렬되어 있는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_operator_lt.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorlt-vector-stlclr"></a><a name="op_lteq"></a>연산자&lt;= (벡터) (STL / CLR)

벡터가 비교보다 적거나 동일합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value>
    bool operator<=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 `!(right < left)`함수가 반환합니다. 두 벡터를 요소별로 비교할 때 *왼쪽이* *오른쪽* 이후에 정렬되지 않았는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_operator_le.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operator-vector-stlclr"></a><a name="op_eq"></a>연산자 = ==(벡터) (STL/CLR)

벡터 와 동일한 비교.

### <a name="syntax"></a>구문

```cpp
template<typename Value>
    bool operator==(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수는 *왼쪽* 및 *오른쪽으로* 제어되는 시퀀스의 길이가 같고 `left[i] ==` `right[i]`각 위치에 `i`대해 true를 반환합니다. 두 벡터를 요소별로 비교할 때 *왼쪽이* *오른쪽과* 동일한 순서로 정렬되는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_operator_eq.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorgt-vector-stlclr"></a><a name="op_gt"></a>연산자(벡터)&gt; (STL/CLR)

비교보다 큰 벡터입니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value>
    bool operator>(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 `right` `<` `left`함수가 반환합니다. 두 벡터를 요소별로 비교할 때 *왼쪽이* *오른쪽* 이후에 정렬되는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_operator_gt.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorgt-vector-stlclr"></a><a name="op_gteq"></a>연산자&gt;= (벡터) (STL / CLR)

벡터가 비교보다 크거나 동일합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value>
    bool operator>=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
비교할 왼쪽 컨테이너입니다.

*오른쪽*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 `!(left < right)`함수가 반환합니다. 두 벡터가 요소별로 요소를 비교할 때 *왼쪽이* *오른쪽* 앞에 정렬되지 않았는지 여부를 테스트하는 데 사용합니다.

### <a name="example"></a>예제

```cpp
// cliext_vector_operator_ge.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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
