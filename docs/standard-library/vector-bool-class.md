---
title: vector&lt;bool&gt; 클래스
ms.date: 11/04/2016
f1_keywords:
- vector<bool>
- vector/std::vector::flip
helpviewer_keywords:
- std::vector [C++], const_pointer
- std::vector [C++], const_reference
- std::vector [C++], pointer
- std::vector [C++], flip
- std::vector [C++], swap
ms.assetid: 8028c8ed-ac9c-4f06-aba1-5de45c00aafb
ms.openlocfilehash: 6c67e3d9ba1b33cb99a7d3afb2522f443003fa38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376088"
---
# <a name="vectorltboolgt-class"></a>vector&lt;bool&gt; 클래스

클래스는 `vector<bool>` **bool**형식의 요소에 대한 [벡터의](../standard-library/vector-class.md) 부분 전문화입니다. 특수화에서 사용되는 기본 형식에 대한 할당자가 있으며 비트당 하나의 **bool** 값을 저장하여 공간 최적화를 제공합니다.

## <a name="syntax"></a>구문

```cpp
template <class Allocator = allocator<bool>>
class vector<bool, Allocator>
```

## <a name="remarks"></a>설명

이 클래스 템플릿 특수화는 이 문서에서 설명하는 차이를 제외하고 벡터처럼 동작합니다.

**bool** 형식을 처리하는 작업은 컨테이너 저장소의 값에 해당합니다. `allocator_traits::construct`는 이러한 값을 만드는 데 사용되지 않습니다.

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[const_pointer](#const_pointer)|`const_iterator`의 부울 요소에 대한 상수 포인터로 사용할 수 있는 `vector<bool>`에 대한 typedef입니다.|
|[const_reference](#const_reference)|**bool에**대한 형식 def . 초기화 이후에는 원래 값으로의 업데이트를 따르지 않습니다.|
|[포인터(pointer)](#pointer)|`iterator`의 부울 요소에 대한 포인터로 사용할 수 있는 `vector<bool>`에 대한 typedef입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[flip](#flip)|`vector<bool>`의 모든 비트를 반대로 바꿉니다.|
|[스왑](#swap)|두 `vector<bool>`의 요소를 교환합니다.|
|[operator&#91;&#93;](#op_at)|지정된 위치에서 `vector<bool>` 요소에 대한 시뮬레이션 참조를 반환합니다.|
|`at`|프록시 클래스 [vector\<bool>::reference](#reference_class)를 사용한다는 점을 제외하면 특수화되지 않은 [vector](../standard-library/vector-class.md)::at 함수와 동일하게 작동합니다. [operator&#91;&#93;](#op_at)도 참조하세요.|
|`front`|프록시 클래스 [vector\<bool>::reference](#reference_class)를 사용한다는 점을 제외하면 특수화되지 않은 [vector](../standard-library/vector-class.md)::front 함수와 동일하게 작동합니다. [operator&#91;&#93;](#op_at)도 참조하세요.|
|`back`|프록시 클래스 [vector\<bool>::reference](#reference_class)를 사용한다는 점을 제외하면 특수화되지 않은 [vector](../standard-library/vector-class.md)::back 함수와 동일하게 작동합니다. [operator&#91;&#93;](#op_at)도 참조하세요.|

### <a name="proxy-class"></a>프록시 클래스

|||
|-|-|
|[vector\<bool> reference 클래스](#reference_class)|`bool&` 동작을 시뮬레이션하기 위해 프록시 역할을 하며, 해당 개체가 `vector<bool>` 개체 내 요소(단일 비트)에 대한 참조를 제공할 수 있는 클래스입니다.|

## <a name="requirements"></a>요구 사항

**헤더** \<: 벡터>

**네임스페이스:** std

## <a name="vectorboolconst_pointer"></a><a name="const_pointer"></a>벡터\<bool>::const_pointer

`vector<bool>` 개체에 포함된 시퀀스의 부울 요소에 대해 고정 포인터로 사용할 수 있는 개체를 설명하는 형식입니다.

```cpp
typedef const_iterator const_pointer;
```

## <a name="vectorboolconst_reference"></a><a name="const_reference"></a>벡터\<불>:const_reference

`vector<bool>` 개체에 포함된 시퀀스의 부울 요소에 대해 고정 참조로 사용할 수 있는 개체를 설명하는 형식입니다.

```cpp
typedef bool const_reference;
```

### <a name="remarks"></a>설명

자세한 내용과 코드 예제는 [vector&lt;bool&gt;::reference::operator=](#reference_operator_eq)를 참조하세요.

## <a name="vectorboolflip"></a><a name="flip"></a>벡터\<bool>::뒤집기

`vector<bool>`의 모든 비트를 반대로 바꿉니다.

```cpp
void flip();
```

### <a name="example"></a>예제

```cpp
// vector_bool_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha; // format output for subsequent code

    vector<bool> vb = { true, false, false, true, true };
    cout << "The vector is:" << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vb.flip();

    cout << "The flipped vector is:" << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}
```

## <a name="vectorbooloperator"></a><a name="op_at"></a>벡터\<bool>::연산자[]

지정된 위치에서 `vector<bool>` 요소에 대한 시뮬레이션 참조를 반환합니다.

```cpp
vector<bool>::reference operator[](size_type Pos);

vector&<bool&>::const_reference operator[](size_type Pos) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|-|-|
|*Pos*|`vector<bool>` 요소의 위치입니다.|

### <a name="return-value"></a>Return Value

인덱싱된 요소의 값이 포함된 [vector\<bool>::reference](#reference_class) 또는 [vector\<bool>::const_reference](#const_reference) 개체입니다.

지정된 위치가 컨테이너의 크기보다 크거나 같을 경우 결과가 정의되지 않습니다.

### <a name="remarks"></a>설명

_ITERATOR_DEBUG_LEVEL 집합으로 컴파일하는 경우 벡터의 경계 외부의 요소에 액세스하려고 하면 런타임 오류가 발생합니다.  자세한 내용은 [확인된 반복기](../standard-library/checked-iterators.md)를 참조하세요.

### <a name="example"></a>예제

이 코드 예제에서는 주석이 있는 두 가지 일반적인 코딩 실수의 `vector<bool>::operator[]` 올바른 사용과 두 가지 일반적인 코딩 실수를 보여 주십니다. 이러한 실수는 반환하는 `vector<bool>::reference` `vector<bool>::operator[]` 개체의 주소를 사용할 수 없기 때문에 오류를 일으킵니다.

```cpp
// cl.exe /EHsc /nologo /W4 /MTd
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;
    vector<bool> vb;

    vb.push_back(true);
    vb.push_back(false);

    //    bool* pb = &vb[1]; // conversion error - do not use
    //    bool& refb = vb[1];   // conversion error - do not use
    bool hold = vb[1];
    cout << "The second element of vb is " << vb[1] << endl;
    cout << "The held value from the second element of vb is " << hold << endl;

    // Note this doesn't modify hold.
    vb[1] = true;
    cout << "The second element of vb is " << vb[1] << endl;
    cout << "The held value from the second element of vb is " << hold << endl;
}
```

## <a name="vectorboolpointer"></a><a name="pointer"></a>벡터\<불>::p

`vector<bool>` 개체에 포함된 시퀀스의 부울 요소에 대해 포인터로 사용할 수 있는 개체를 설명하는 형식입니다.

```cpp
typedef iterator pointer;
```

## <a name="vectorboolreference-class"></a><a name="reference_class"></a>벡터\<bool>::참조 클래스

`vector<bool>::reference` 클래스는 [vector\<bool> 클래스](../standard-library/vector-bool-class.md)에서 `bool&`을 시뮬레이션하도록 제공되는 프록시 클래스입니다.

### <a name="remarks"></a>설명

C++는 기본적으로 비트에 직접 참조를 허용하지 않으므로 시뮬레이션된 참조가 필요하지 않습니다. `vector<bool>`는 요소당 1비트만 사용하며, 이 프록시 클래스만 사용하여 참조할 수 있습니다. 하지만, 특정 할당은 유효하지 않으므로 참조 시뮬레이션이 완전하지 않습니다. 예를 들어 `vector<bool>::reference` 개체의 주소를 확인할 수 없으므로 [vector\<bool>::operator&#91;&#93;](#op_at)를 사용하는 다음 코드는 올바르지 않습니다.

```cpp
vector<bool> vb;
//...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

### <a name="vectorboolreferenceflip"></a><a name="reference_flip"></a>벡터\<bool>::참조::뒤집기

참조된 [vector\<bool>](../standard-library/vector-bool-class.md) 요소의 부울 값을 반전합니다.

```cpp
void flip();
```

#### <a name="example"></a>예제

```cpp
// vector_bool_ref_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    cout << "The vector is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vector<bool>::reference vbref = vb.front();
    vbref.flip();

    cout << "The vector with first element flipped is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}
```

```Output
The vector is:
    true false false true true
The vector with first element flipped is:
    false false false true true
```

### <a name="vectorboolreferenceoperator-bool"></a><a name="reference_operator_bool"></a>벡터\<bool>::참조::연산자 bool

`vector<bool>::reference` **bool로**암시적 변환을 제공합니다.

```cpp
operator bool() const;
```

#### <a name="return-value"></a>Return Value

vector\<bool> 개체의 요소 부울 값

#### <a name="remarks"></a>설명

`vector<bool>` 개체는 이 연산자로 수정할 수 없습니다.

### <a name="vectorboolreferenceoperator"></a><a name="reference_operator_eq"></a>벡터\<bool>::참조::연산자=

비트에 부울 값을 할당하거나 참조된 요소에 저장된 값을 비트에 할당합니다.

```cpp
reference& operator=(const reference& Right);
reference& operator=(bool Val);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
해당 값을 비트에 할당할 요소 참조입니다.

*발*\
비트에 할당될 부울 값입니다.

#### <a name="example"></a>예제

```cpp
// vector_bool_ref_op_assign.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
#include <string>

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
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    print("The vector is: ", vb);

    // Invoke vector<bool>::reference::operator=()
    vector<bool>::reference refelem1 = vb[0];
    vector<bool>::reference refelem2 = vb[1];
    vector<bool>::reference refelem3 = vb[2];

    bool b1 = refelem1;
    bool b2 = refelem2;
    bool b3 = refelem3;
    cout << "The original value of the 1st element stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element stored in a bool: " << b3 << endl;
    cout << endl;

    refelem2 = refelem1;

    print("The vector after assigning refelem1 to refelem2 is now: ", vb);

    refelem3 = true;

    print("The vector after assigning false to refelem1 is now: ", vb);

    // The initial values are still stored in the bool variables and remained unchanged
    cout << "The original value of the 1st element still stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element still stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element still stored in a bool: " << b3 << endl;
    cout << endl;
}
```

```Output
The vector is: true false false true true
The original value of the 1st element stored in a bool: true
The original value of the 2nd element stored in a bool: false
The original value of the 3rd element stored in a bool: false

The vector after assigning refelem1 to refelem2 is now: true true false true true
The vector after assigning false to refelem1 is now: true true true true true
The original value of the 1st element still stored in a bool: true
The original value of the 2nd element still stored in a bool: false
The original value of the 3rd element still stored in a bool: false
```

## <a name="vectorboolswap"></a><a name="swap"></a>벡터\<bool>::swap

프록시 클래스 [vector\<bool>::reference](#reference_class)를 사용하여 부울 벡터(`vector<bool>`)의 두 요소를 교환하는 정적 구성원 함수입니다.

```cpp
static void swap(
    reference Left,
    reference Right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
*오른쪽* 요소와 교환할 요소입니다.

*오른쪽*\
*왼쪽* 요소와 교환할 요소입니다.

### <a name="remarks"></a>설명

이 오버로드는 `vector<bool>`의 특정 프록시 요구 사항을 지원합니다. [vector](../standard-library/vector-class.md)::swap에는 `vector<bool>::swap()`의 단일 인수 오버로드와 동일한 기능이 있습니다.

## <a name="see-also"></a>참고 항목

[C++ 표준 라이브러리의 나사 안전](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)
