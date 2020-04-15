---
title: basic_string_view 클래스
ms.date: 04/20/2019
f1_keywords:
- xstring/std::basic_string_view
- xstring/std::basic_string_view::allocator_type
- xstring/std::basic_string_view::const_iterator
- xstring/std::basic_string_view::const_pointer
- xstring/std::basic_string_view::const_reference
- xstring/std::basic_string_view::const_reverse_iterator
- xstring/std::basic_string_view::difference_type
- xstring/std::basic_string_view::iterator
- xstring/std::basic_string_view::npos
- xstring/std::basic_string_view::pointer
- xstring/std::basic_string_view::reference
- xstring/std::basic_string_view::reverse_iterator
- xstring/std::basic_string_view::size_type
- xstring/std::basic_string_view::traits_type
- xstring/std::basic_string_view::value_type
- xstring/std::basic_string_view::append
- xstring/std::basic_string_view::assign
- xstring/std::basic_string_view::at
- xstring/std::basic_string_view::back
- xstring/std::basic_string_view::begin
- xstring/std::basic_string_view::c_str
- xstring/std::basic_string_view::capacity
- xstring/std::basic_string_view::cbegin
- xstring/std::basic_string_view::cend
- xstring/std::basic_string_view::clear
- xstring/std::basic_string_view::compare
- xstring/std::basic_string_view::copy
- xstring/std::basic_string_view::_Copy_s
- xstring/std::basic_string_view::crbegin
- xstring/std::basic_string_view::crend
- xstring/std::basic_string_view::data
- xstring/std::basic_string_view::empty
- xstring/std::basic_string_view::end
- xstring/std::basic_string_view::erase
- xstring/std::basic_string_view::find
- xstring/std::basic_string_view::find_first_not_of
- xstring/std::basic_string_view::find_first_of
- xstring/std::basic_string_view::find_last_not_of
- xstring/std::basic_string_view::find_last_of
- xstring/std::basic_string_view::front
- xstring/std::basic_string_view::get_allocator
- xstring/std::basic_string_view::insert
- xstring/std::basic_string_view::length
- xstring/std::basic_string_view::max_size
- xstring/std::basic_string_view::pop_back
- xstring/std::basic_string_view::push_back
- xstring/std::basic_string_view::rbegin
- xstring/std::basic_string_view::rend
- xstring/std::basic_string_view::remove_prefix
- xstring/std::basic_string_view::remove_suffix
- xstring/std::basic_string_view::replace
- xstring/std::basic_string_view::reserve
- xstring/std::basic_string_view::resize
- xstring/std::basic_string_view::rfind
- xstring/std::basic_string_view::shrink_to_fit
- xstring/std::basic_string_view::size
- xstring/std::basic_string_view::substr
- xstring/std::basic_string_view::swap
helpviewer_keywords:
- std::basic_string_view
- std::basic_string_view, allocator_type
- std::basic_string_view, const_iterator
- std::basic_string_view, const_pointer
- std::basic_string_view, const_reference
- std::basic_string_view, const_reverse_iterator
- std::basic_string_view, difference_type
- std::basic_string_view, iterator
- std::basic_string_view, npos
- std::basic_string_view, pointer
- std::basic_string_view, reference
- std::basic_string_view, reverse_iterator
- std::basic_string_view, size_type
- std::basic_string_view, traits_type
- std::basic_string_view, value_type
- std::basic_string_view, append
- std::basic_string_view, assign
- std::basic_string_view, at
- std::basic_string_view, back
- std::basic_string_view, begin
- std::basic_string_view, c_str
- std::basic_string_view, capacity
- std::basic_string_view, cbegin
- std::basic_string_view, cend
- std::basic_string_view, clear
- std::basic_string_view, compare
- std::basic_string_view, copy
- std::basic_string_view, crbegin
- std::basic_string_view, crend
- std::basic_string_view, data
- std::basic_string_view, empty
- std::basic_string_view, end
- std::basic_string_view, erase
- std::basic_string_view, find
- std::basic_string_view, find_first_not_of
- std::basic_string_view, find_first_of
- std::basic_string_view, find_last_not_of
- std::basic_string_view, find_last_of
- std::basic_string_view, front
- std::basic_string_view, get_allocator
- std::basic_string_view, insert
- std::basic_string_view, length
- std::basic_string_view, max_size
- std::basic_string_view, pop_back
- std::basic_string_view, push_back
- std::basic_string_view, rbegin
- std::basic_string_view, rend
- std::basic_string_view, remove_prefix
- std::basic_string_view, remove_suffix
- std::basic_string_view, replace
- std::basic_string_view, reserve
- std::basic_string_view, resize
- std::basic_string_view, rfind
- std::basic_string_view, shrink_to_fit
- std::basic_string_view, size
- std::basic_string_view, substr
- std::basic_string_view, swap
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
ms.openlocfilehash: ac65dca931f821c717e9c081c8d3479fd0b3bb0e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364899"
---
# <a name="basic_string_view-class"></a>basic_string_view 클래스

클래스 템플릿은 `basic_string_view<charT>` C++17에 추가되어 함수가 해당 형식에 대해 템플릿화할 필요 없이 다양한 관련없는 문자열 형식을 수용할 수 있는 안전하고 효율적인 방법으로 사용할 수 있습니다. 클래스에는 연속적인 문자 데이터 시퀀스에 대한 소유가 아닌 포인터와 시퀀스의 문자 수를 지정하는 길이가 있습니다. 시퀀스가 null-종료되는지 여부에 대해서는 가정이 이루어지지 않습니다.

표준 라이브러리는 요소 유형에 따라 여러 특수화를 정의합니다.

- `string_view`
- `wstring_view`
- `u16string_view`
- `u32string_view`

이 문서에서 "string_view"이라는 용어는 일반적으로 이러한 형식defs를 나타냅니다.

string_view 문자열 데이터를 읽는 데 필요한 최소 공통 인터페이스를 설명합니다. 기본 데이터에 대한 const 액세스를 제공합니다. `copy` 복사본을 만들지 않습니다(함수 제외). 데이터는 어떤 위치에서도 null 값('\0')을 포함하거나 포함하지 않을 수 있습니다. string_view 개체의 수명을 제어할 수 없습니다. 기본 문자열 데이터가 유효한지 확인하는 것은 호출자의 책임입니다.

형식을 string_view 매개 변수를 허용하는 함수는 함수를 템플릿으로 만들거나 함수를 문자열 형식의 특정 하위 집합으로 제한하지 않고 문자열과 같은 형식으로 작업할 수 있습니다. 유일한 요구 사항은 문자열 형식에서 string_view 암시적 변환이 존재한다는 것입니다. 모든 표준 문자열 형식은 암시적으로 동일한 요소 형식을 포함하는 string_view 변환할 수 있습니다. 즉, a는 `std::string` 변환할 수 `string_view` 있지만 `wstring_view`a로 변환할 수 없습니다.

다음 예제에서는 형식의 `f` `wstring_view`매개 변수를 사용 하는 비 템플릿 함수를 보여 합니다. 형식 `std::wstring`의 인수로 호출할 `wchar_t*`수 `winrt::hstring`있습니다.

```cpp
// compile with: /std:c++17
// string_view that uses elements of wchar_t
void f(wstring_view);

// pass a std::wstring:
const std::wstring& s { L"Hello" };
f(s);

// pass a C-style null-terminated string (string_view is not null-terminated):
const wchar_t* ns = L"Hello";
f(ns);

// pass a C-style character array of len characters (excluding null terminator):
const wchar_t* cs { L"Hello" };
size_t len { 5 };
f({cs,len});

// pass a WinRT string
winrt::hstring hs { L"Hello" };
f(hs);
```

## <a name="syntax"></a>구문

```cpp
template <class CharType, class Traits = char_traits<CharType>>
class basic_string_view;
```

### <a name="parameters"></a>매개 변수

*Chartype*\
string_view 저장된 문자의 유형입니다. C++ 표준 라이브러리는 이 템플릿의 특수화에 대해 다음과 같은 형식을 제공합니다.

- **문자** 문자의 요소에 대한 [string_view](../standard-library/string-view-typedefs.md#string_view)
- [wstring_view](../standard-library/string-view-typedefs.md#wstring_view), **wchar_t**
- **char16_t** 위한 [u16string_view](../standard-library/string-view-typedefs.md#u16string_view)
- [char32_t](../standard-library/string-view-typedefs.md#u32string_view) **char32_t**대한 u32string_view .

*특성*\
[char_traits](char-traits-struct.md)<*기본값은 char_traits CharType*>.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[basic_string_view](#basic_string_view)|비어 있거나 다른 문자열 개체의 데이터 또는 C 스타일 문자 배열의 전체 또는 일부를 가리키는 string_view 구성합니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|**const_iterator**|**const** 요소를 읽을 수 있는 임의 액세스 이터레이터입니다.|
|**const_pointer**|`using const_pointer = const value_type*;`|
|**const_reference**|`using const_reference = const value_type&;`|
|**const_reverse_iterator**|`using const_reverse_iterator = std::reverse_iterator<const_iterator>;`|
|**difference_type**|`using difference_type = ptrdiff_t;`|
|**반복기**|`using iterator = const_iterator;`|
|**npos**|`static constexpr size_type npos = size_type(-1);`|
|**포인터(pointer)**|`using pointer = value_type*;`|
|**참조**|`using reference = value_type&;`|
|**reverse_iterator**|`using reverse_iterator = const_reverse_iterator;`|
|**size_type**|`using size_type = size_t;`|
|**traits_type**|`using traits_type = Traits;`|
|**Value_type**|`using value_type = CharType;`|

### <a name="member-operators"></a>멤버 연산자

|연산자|Description|
|-|-|
|[연산자 =](#op_eq)|string_view 또는 컨버터블 문자열 개체를 다른 string_view 할당합니다.|
|[연산자\[\]](#op_at)|지정한 인덱스의 요소를 반환합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[에](#at)|지정된 위치에 있는 요소에 const_reference 반환합니다.|
|[뒤로](#back)|마지막 요소에 const_reference 반환합니다.|
|[시작](#begin)|첫 번째 요소를 처리하는 구성요소 이터레이터를 반환합니다. (string_views 변경할 수 없습니다.)|
|[cbegin](#cbegin)|[시작과](#begin)동일합니다.|
|[엔드 (것)엔드](#cend)|마지막 요소를 지나간 구성요소를 가리키는 구성요소 이터레이터를 반환합니다.|
|[copy](#copy)|원본의 인덱싱된 위치에서 대상 문자 배열로 string_view 지정된 수의 문자를 복사합니다. (권장되지 않습니다. 대신 _Copy_s 사용합니다.)|
|[_Copy_s](#_copy_s)|보안 CRT 복사 기능.|
|[비교](#compare)|string_view 지정된 string_view 비교하여 동일한지 또는 다른 string_view 보다 사전적으로 작은지 확인합니다.|
|[crbegin](#crbegin)|[rbegin과](#rbegin)동일합니다.|
|[crend](#crend)|[렌드와](#rend)동일합니다.|
|[데이터](#data)|원시 비소유 포인터를 문자 시퀀스에 반환합니다.|
|[빈](#empty)|string_view 문자가 포함되어 있는지 여부를 테스트합니다.|
|[end](#end)|[cend와](#cend)동일합니다.|
|[찾을](#find)|지정된 문자 시퀀스와 일치하는 하위 문자열의 첫 번째 발생에 대해 순방향방향으로 검색합니다.|
|[find_first_not_of](#find_first_not_of)|지정된 string_view 또는 컨버터블 문자열 개체의 요소가 아닌 첫 번째 문자를 검색합니다.|
|[find_first_of](#find_first_of)|지정된 string_view 또는 컨버터블 문자열 개체의 모든 요소와 일치하는 첫 번째 문자를 검색합니다.|
|[find_last_not_of](#find_last_not_of)|지정된 string_view 또는 컨버터블 문자열 개체의 요소가 아닌 마지막 문자를 검색합니다.|
|[find_last_of](#find_last_of)|지정된 string_view 또는 컨버터블 문자열 개체의 요소인 마지막 문자를 검색합니다.|
|[앞](#front)|첫 번째 요소에 const_reference 반환합니다.|
|[length](#length)|현재 요소 수를 반환합니다.|
|[max_size](#max_size)|string_view 포함할 수 있는 최대 문자 수를 반환합니다.|
|[rbegin](#rbegin)|반전된 string_view 첫 번째 요소를 해결하는 구성요소 이터레이터를 반환합니다.|
|[remove_prefix](#remove_prefix)|지정된 수의 요소로 포인터를 앞으로 이동합니다.|
|[remove_suffix](#remove_suffix)|뒤에서 시작하는 요소의 지정된 수에 의해 뷰의 크기를 줄입니다.|
|[rend](#rend)|반전된 string_view 마지막 요소를 지나가는 요소를 가리키는 구성요소 이터레이터를 반환합니다.|
|[rfind](#rfind)|지정된 문자 시퀀스와 일치하는 하위 문자열의 첫 번째 발생에 대해 역으로 string_view 검색합니다.|
|[크기](#size)|현재 요소 수를 반환합니다.|
|[Substr](#substr)|지정된 인덱스에서 시작하여 지정된 길이의 하위 문자열을 반환합니다.|
|[스왑](#swap)|두 string_views 내용을 교환합니다.|

## <a name="remarks"></a>설명

함수는 [max_size](#max_size) 요소보다 긴 시퀀스를 생성하라는 요청을 받으면 [length_error](../standard-library/length-error-class.md) 형식의 개체를 throw하여 길이 오류를 보고합니다.

## <a name="requirements"></a>요구 사항

[std:c++17](../build/reference/std-specify-language-standard-version.md) 이상

**헤더:** \<string_view>

**네임스페이스:** std

## <a name="basic_string_viewat"></a><a name="at"></a>basic_string_view::에서

지정된 0기반 인덱스에서 문자에 const_reference 반환합니다.

```cpp
constexpr const_reference at(size_type offset) const;
```

### <a name="parameters"></a>매개 변수

*오프셋*\
참조할 요소의 인덱스입니다.

### <a name="return-value"></a>Return Value

매개 변수 인덱스에 의해 지정된 위치에서 문자에 const_reference.

### <a name="remarks"></a>설명

첫 번째 요소는 0의 인덱스를 가지며 다음 요소는 양수 정수에 의해 연속적으로 인덱싱되므로 길이 *n의* string_view *n의* *nth*요소가 n - 1로 인덱싱됩니다. **에서** [연산자와\[](#op_at)달리 잘못된 인덱스에 대한 예외를 throw합니다.

일반적으로 string_view **at** `std::vector` 같은 시퀀스에 대해서는 사용하지 않는 것이 좋습니다. 시퀀스에 전달된 잘못된 인덱스는 개발 중에 검색하고 수정해야 하는 논리 오류입니다. 프로그램이 해당 인덱스가 유효한지 절대적으로 확실하지 않은 경우 at() 호출이 아닌 인덱스를 테스트하고 부주의한 프로그래밍을 방어하기 위해 예외에 의존해야 합니다.

자세한 내용은 [basic_string_view::연산자()를\[ ](#op_at) 참조하십시오.

### <a name="example"></a>예제

```cpp
// basic_string_view_at.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>

int main()
{
    using namespace std;

    const string_view  str1("Hello world");
    string_view::const_reference refStr2 = str1.at(8); // 'r'
}
```

## <a name="basic_string_viewback"></a><a name="back"></a>basic_string_view::뒤로

마지막 요소에 const_reference 반환합니다.

```cpp
constexpr const_reference back() const;
```

### <a name="return-value"></a>Return Value

string_view 마지막 요소에 대한 const_reference.

### <a name="remarks"></a>설명

string_view 비어 있는 경우 예외를 throw합니다.

예를 들어 호출을 `remove_suffix`통해 string_view 수정한 후 이 함수에서 반환되는 요소는 더 이상 기본 데이터의 마지막 요소가 아닙니다.

### <a name="example"></a>예제

C 문자열 리터럴로 구성된 string_view null 종료를 포함하지 않으므로 다음 예제에서는 `back` '\0'이 아닌 'p'를 반환합니다.

```cpp
char c[] = "Help"; // char[5]
string_view sv{ c };
cout << sv.size(); // size() == 4
cout << sv.back() << endl; // p
```

포함된 null은 다른 문자로 처리됩니다.

```cpp
string_view e = "embedded\0nulls"sv;
cout << boolalpha << (e.back() == 's'); // true
```

## <a name="basic_string_viewbasic_string_view"></a><a name="basic_string_view"></a>basic_string_view:basic_string_view

string_view 구성합니다.

```cpp
constexpr basic_string_view() noexcept;
constexpr basic_string_view(const basic_string_view&) noexcept = default;
constexpr basic_string_view(const charT* str);
constexpr basic_string_view(const charT* str, size_type len);
```

### <a name="parameters"></a>매개 변수

*Str*\
문자 값에 대한 포인터입니다.

*렌*\
뷰에 포함할 문자 수입니다.

## <a name="remarks"></a>설명

charT* 매개 변수가 있는 생성자는 입력이 null-종료되지만 종료 null이 string_view 포함되지 않는다고 가정합니다.

리터럴로 string_view 구성할 수도 있습니다. [연산자""sv를](string-view-operators.md#op_sv)참조하십시오.

## <a name="basic_string_viewbegin"></a><a name="begin"></a>basic_string_view::시작

[cbegin과](#cbegin)동일합니다.

```cpp
constexpr const_iterator begin() const noexcept;
```

### <a name="return-value"></a>Return Value

첫 번째 요소를 처리하는 const_iterator 반환합니다.

## <a name="basic_string_viewcbegin"></a><a name="cbegin"></a>basic_string_view::cbegin

범위의 첫 번째 요소를 해결하는 const_iterator 반환합니다.

```cpp
constexpr const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>Return Value

범위의 첫 번째 요소 또는 빈 범위의 끝 바로 너머의 위치를 가리키는 **const** 임의 액세스 거점 `cbegin() == cend()`거점입니다(빈 범위의 경우).

## <a name="basic_string_viewcend"></a><a name="cend"></a>basic_string_view::cend

범위의 마지막 요소 바로 너머의 위치를 해결하는 const_iterator 반환합니다.

```cpp
constexpr const_iterator cend() const noexcept;
```

### <a name="return-value"></a>Return Value

범위의 끝 바로 너머를 가리키는 **const** 임의 액세스 거점 거점입니다.

### <a name="remarks"></a>설명

`cend`에서 반환한 값은 역참조되지 않아야 합니다.

## <a name="basic_string_viewcompare"></a><a name="compare"></a> basic_string_view::compare

지정된 string_view(또는 컨버터블 문자열 유형)과 대/소문자를 구분하여 두 개체가 같는지 또는 한 개체가 다른 개체보다 사전적으로 작은지 확인합니다. string_view> 연산자는 이 멤버 함수를 사용하여 비교를 수행합니다. [ \<](string-view-operators.md)

```cpp
constexpr int compare(basic_string_view strv) const noexcept;
constexpr int compare(size_type pos, size_type num, basic_string_view strv) const;
constexpr int compare(size_type pos, size_type num, basic_string_view strv, size_type offset, size_type num2) const;
constexpr int compare(const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr, size_type num2) const;
```

### <a name="parameters"></a>매개 변수

*스트리브 ()(strv)*\
이 string_view 비교할 string_view.

*Pos*\
이 인덱스는 비교가 시작되는 string_view.

*Num*\
이 string_view 비교할 수 있는 최대 문자 수입니다.

*num2*\
비교할 *strv의* 최대 문자 수입니다.

*오프셋*\
비교가 시작되는 *strv의* 인덱스입니다.

*Ptr*\
이 string_view 비교할 C 문자열입니다.

### <a name="return-value"></a>Return Value

이 string_view *strv* 또는 *ptr보다*작은 경우 음수 값; 두 문자 시퀀스가 같으면 0입니다. 또는 이 string_view *strv* 또는 *ptr보다*큰 경우 양수 값입니다.

### <a name="remarks"></a>설명

멤버 `compare` 함수는 각 문자 시퀀스의 전체 또는 일부의 대/소문자 구분 비교를 수행합니다.

### <a name="example"></a>예제

```cpp
// basic_string_view_compare.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>
#include <string>

using namespace std;

string to_alpha(int result)
{
   if (result < 0) return " less than ";
   else if (result == 0) return " equal to ";
   else return " greater than ";
}

int main()
{
   // The first member function compares
   // two string_views
   string_view sv_A("CAB");
   string_view sv_B("CAB");
   cout << "sv_A is " << sv_A << endl;
   cout << "sv_B is " << sv_B << endl;
   int comp1 = sv_A.compare(sv_B);
   cout << "sv_A is" << to_alpha(comp1) << "sv_B.\n";

   // The second member function compares part of
   // an operand string_view to another string_view
   string_view sv_C("AACAB");
   string_view sv_D("CAB");
   cout << "sv_C is: " << sv_C << endl;
   cout << "sv_D is: " << sv_D << endl;
   int comp2a = sv_C.compare(2, 3, sv_D);
   cout << "The last three characters of sv_C are"
       << to_alpha(comp2a) << "sv_D.\n";

   int comp2b = sv_C.compare(0, 3, sv_D);
   cout << "The first three characters of sv_C are"
       << to_alpha(comp2b) << "sv_D.\n";

   // The third member function compares part of
   // an operand string_view to part of another string_view
   string_view sv_E("AACAB");
   string_view sv_F("DCABD");
   cout << "sv_E: " << sv_E << endl;
   cout << "sv_F is: " << sv_F << endl;
   int comp3a = sv_E.compare(2, 3, sv_F, 1, 3);
   cout << "The three characters from position 2 of sv_E are"
       << to_alpha(comp3a)
       << "the 3 characters of sv_F from position 1.\n";

   // The fourth member function compares
   // an operand string_view to a C string
   string_view sv_G("ABC");
   const char* cs_A = "DEF";
   cout << "sv_G is: " << sv_G << endl;
   cout << "cs_A is: " << cs_A << endl;
   int comp4a = sv_G.compare(cs_A);
   cout << "sv_G is" << to_alpha(comp4a) << "cs_A.\n";

   // The fifth member function compares part of
   // an operand string_view to a C string
   string_view sv_H("AACAB");
   const char* cs_B = "CAB";
   cout << "sv_H is: " << sv_H << endl;
   cout << "cs_B is: " << cs_B << endl;
   int comp5a = sv_H.compare(2, 3, cs_B);
   cout << "The last three characters of sv_H are"
      << to_alpha(comp5a) << "cs_B.\n";

   // The sixth member function compares part of
   // an operand string_view to part of an equal length of
   // a C string
   string_view sv_I("AACAB");
   const char* cs_C = "ACAB";
   cout << "sv_I is: " << sv_I << endl;
   cout << "cs_C: " << cs_C << endl;
   int comp6a = sv_I.compare(1, 3, cs_C, 3);
   cout << "The 3 characters from position 1 of sv_I are"
      << to_alpha(comp6a) << "the first 3 characters of cs_C.\n";
}
```

```Output
sv_A is CAB
sv_B is CAB
sv_A is equal to sv_B.
sv_C is: AACAB
sv_D is: CAB
The last three characters of sv_C are equal to sv_D.
The first three characters of sv_C are less than sv_D.
sv_E: AACAB
sv_F is: DCABD
The three characters from position 2 of sv_E are equal to the 3 characters of sv_F from position 1.
sv_G is: ABC
cs_A is: DEF
sv_G is less than cs_A.
sv_H is: AACAB
cs_B is: CAB
The last three characters of sv_H are equal to cs_B.
sv_I is: AACAB
cs_C: ACAB
The 3 characters from position 1 of sv_I are equal to the first 3 characters of cs_C.
```

## <a name="basic_string_viewcopy"></a><a name="copy"></a>basic_string_view::복사

원본의 인덱싱된 위치에서 대상 문자 배열로 string_view 지정된 수의 문자를 복사합니다. 대신 보안 기능을 [basic_string_view:_Copy_s](#_copy_s) 사용하는 것이 좋습니다.

```cpp
size_type copy(charT* ptr, size_type count, size_type offset = 0) const;
```

### <a name="parameters"></a>매개 변수

*Ptr*\
요소를 복사할 대상 문자 배열입니다.

*횟수*\
원본에서 복사할 문자 수string_view

*오프셋*\
원본의 시작 위치는 복사본을 만들 수 있는 string_view.

### <a name="return-value"></a>Return Value

실제로 복사된 문자 수입니다.

### <a name="remarks"></a>설명

Null 문자는 복사본의 끝에 추가되지 않습니다.

## <a name="basic_string_view_copy_s"></a><a name="_copy_s"></a>basic_string_view:_Copy_s

복사 대신 사용할 CRT 복사 [함수를](#copy)보호합니다.

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>매개 변수

*Dest*\
요소를 복사할 대상 문자 배열입니다.

*dest_size*\
*가장 큰*크기.

_ 소스 문자열에서 복사할 문자 수를 *계산합니다.*

*_Off*\
복사본을 만들 원본 문자열의 시작 위치입니다.

### <a name="return-value"></a>Return Value

실제로 복사된 문자 수입니다.

### <a name="remarks"></a>설명

Null 문자는 복사본의 끝에 추가되지 않습니다.

자세한 내용은 [c-런타임 라이브러리/보안 기능-인-더-crt를](../c-runtime-library/security-features-in-the-crt.md)참조하십시오.

## <a name="basic_string_viewcrbegin"></a><a name="crbegin"></a>basic_string_view::crbegin

반전된 string_view 첫 번째 요소를 해결하는 const_reverse_iterator 반환합니다.

```cpp
constexpr const_reverse_iterator crbegin() const noexcept;
```

### <a name="return-value"></a>Return Value

반전된 string_view 첫 번째 요소를 해결하는 const_reverse_iterator.

## <a name="basic_string_viewcrend"></a><a name="crend"></a>basic_string_view::크렌드

[렌드와](#rend)동일합니다.

```cpp
constexpr const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>Return Value

반전된 string_view 끝을 지나서 해결하는 const_reverse_iterator 반환합니다.

## <a name="basic_string_viewdata"></a><a name="data"></a>basic_string_view::d

string_view 생성하는 데 사용된 개체의 const 문자 시퀀스에 원시 비소유 포인터를 반환합니다.

```cpp
constexpr value_type *data() const noexcept;
```

### <a name="return-value"></a>Return Value

문자 시퀀스의 첫 번째 요소에 대한 포인터-const입니다.

### <a name="remarks"></a>설명

포인터는 문자를 수정할 수 없습니다.

string_view 문자의 시퀀스가 반드시 null-terminated가 아닐 필요는 없습니다. null 문자가 `data` 추가되지 않으므로 반환 형식은 유효한 C 문자열이 아닙니다. null 문자 '\0'은 string_view 형식의 개체에 특별한 의미가 없으며 다른 문자와 마찬가지로 string_view 개체의 일부일 수 있습니다.

## <a name="basic_string_viewempty"></a><a name="empty"></a>basic_string_view::비어 있음

string_view 문자가 포함되어 있는지 여부를 테스트합니다.

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>Return Value

string_view 개체에 문자가 없는 경우 **true입니다.** 문자가 하나 이상 있는 경우 **false입니다.**

### <a name="remarks"></a>설명

멤버 함수는 [크기()](#size)== 0과 같습니다.

## <a name="basic_string_viewend"></a><a name="end"></a>basic_string_view:종료

마지막 요소를 지나가는 const_iterator 가리키는 임의 액세스 const_iterator 반환합니다.

```cpp
constexpr const_iterator end() const noexcept;
```

### <a name="return-value"></a>Return Value

마지막 요소를 지나가는 const_iterator 가리키는 임의 액세스 const_iterator 반환합니다.

### <a name="remarks"></a>설명

`end`const_iterator string_view 끝에 도달했는지 여부를 테스트하는 데 사용됩니다. `end`에서 반환한 값은 역참조되지 않아야 합니다.

## <a name="basic_string_viewfind"></a><a name="find"></a>basic_string_view::찾기

지정된 문자 시퀀스와 일치하는 문자 또는 하위 문자열의 첫 번째 발생에 대해 정방향 방향으로 string_view 검색합니다.

```cpp
constexpr size_type find(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>매개 변수

*Str*\
멤버 함수를 검색하는 string_view.

*chval*\
멤버 함수가 검색할 문자 값입니다.

*오프셋*\
검색을 시작할 인덱스입니다.

*Ptr*\
멤버 함수가 검색하는 C 문자열입니다.

*횟수*\
첫 번째 문자에서 앞으로 계산하는 *ptr의*문자 수입니다.

### <a name="return-value"></a>Return Value

성공하면 검색되는 부분 문자열의 첫 문자 인덱스이고, 그렇지 않으면 `npos`입니다.

## <a name="basic_string_viewfind_first_not_of"></a><a name="find_first_not_of"></a>basic_string_view:find_first_not_of

지정된 string_view 또는 컨버터블 문자열 개체의 요소가 아닌 첫 번째 문자를 검색합니다.

```cpp
constexpr size_type find_first_not_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>매개 변수

*Str*\
멤버 함수를 검색하는 string_view.

*chval*\
멤버 함수가 검색할 문자 값입니다.

*오프셋*\
검색을 시작할 인덱스입니다.

*Ptr*\
멤버 함수가 검색하는 C 문자열입니다.

*횟수*\
멤버 함수가 검색되는 C 문자열의 첫 번째 문자에서 앞으로 계산하는 문자 수입니다.

### <a name="return-value"></a>Return Value

성공하면 검색되는 부분 문자열의 첫 문자 인덱스이고, 그렇지 않으면 `npos`입니다.

## <a name="basic_string_viewfind_first_of"></a><a name="find_first_of"></a>basic_string_view:find_first_of

지정된 string_view 요소와 일치하는 첫 번째 문자를 검색합니다.

```cpp
constexpr size_type find_first_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(const charT* str, size_type offset, size_type count) const;
constexpr size_type find_first_of(const charT* str, size_type offset = 0) const;
```

### <a name="parameters"></a>매개 변수

*chval*\
멤버 함수가 검색할 문자 값입니다.

*오프셋*\
검색을 시작할 인덱스입니다.

*Ptr*\
멤버 함수가 검색하는 C 문자열입니다.

*횟수*\
멤버 함수가 검색되는 C 문자열의 첫 번째 문자에서 앞으로 계산하는 문자 수입니다.

*Str*\
멤버 함수를 검색하는 string_view.

### <a name="return-value"></a>Return Value

성공하면 검색되는 부분 문자열의 첫 문자 인덱스이고, 그렇지 않으면 `npos`입니다.

## <a name="basic_string_viewfind_last_not_of"></a><a name="find_last_not_of"></a>basic_string_view:find_last_not_of

지정된 string_view 요소가 아닌 마지막 문자를 검색합니다.

```cpp
constexpr size_type find_last_not_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>매개 변수

*Str*\
멤버 함수를 검색하는 string_view.

*chval*\
멤버 함수가 검색할 문자 값입니다.

*오프셋*\
검색이 완료되는 인덱스입니다.

*Ptr*\
멤버 함수가 검색하는 C 문자열입니다.

*횟수*\
*첫*번째 문자에서 앞으로 계산하는 문자 수입니다.

### <a name="return-value"></a>Return Value

성공하면 검색되는 부분 문자열의 첫 문자 인덱스이고, 그렇지 않으면 `string_view::npos`입니다.

## <a name="basic_string_viewfind_last_of"></a><a name="find_last_of"></a>basic_string_view:find_last_of

지정된 string_view 요소와 일치하는 마지막 문자를 검색합니다.

```cpp
constexpr size_type find_last_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>매개 변수

*Str*\
멤버 함수를 검색하는 string_view.

*chval*\
멤버 함수가 검색할 문자 값입니다.

*오프셋*\
검색이 완료되는 인덱스입니다.

*Ptr*\
멤버 함수가 검색하는 C 문자열입니다.

*횟수*\
멤버 함수가 검색되는 C 문자열의 첫 번째 문자에서 앞으로 계산하는 문자 수입니다.

### <a name="return-value"></a>Return Value

성공 시 검색되는 부분 문자열의 마지막 문자 인덱스이고, 그렇지 않으면 `npos`입니다.

## <a name="basic_string_viewfront"></a><a name="front"></a>basic_string_view:전면

첫 번째 요소에 const_reference 반환합니다.

```cpp
constexpr const_reference front() const;
```

### <a name="return-value"></a>Return Value

첫 번째 요소에 대한 const_reference.

### <a name="remarks"></a>설명

string_view 비어 있는 경우 예외를 throw합니다.

## <a name="basic_string_viewlength"></a><a name="length"></a> basic_string_view::length

현재 요소 수를 반환합니다.

```cpp
constexpr size_type length() const noexcept;
```

### <a name="remarks"></a>설명

멤버 함수는 [size](#size)와 동일합니다.

## <a name="basic_string_viewmax_size"></a><a name="max_size"></a>basic_string_view:max_size

string_view 포함할 수 있는 최대 문자 수를 반환합니다.

```cpp
constexpr size_type max_size() const noexcept;
```

### <a name="return-value"></a>Return Value

string_view 포함할 수 있는 최대 문자 수입니다.

### <a name="remarks"></a>설명

작업에서 길이가 `max_size()` 보다 큰 string_view를 생성 하는 경우 [length_error](../standard-library/length-error-class.md) 형식의 예외가 throw 됩니다.

## <a name="basic_string_viewoperator"></a><a name="op_eq"></a>basic_string_view::연산자=

string_view 또는 컨버터블 문자열 개체를 다른 string_view 할당합니다.

```cpp
constexpr basic_string_view& operator=(const basic_string_view&) noexcept = default;
```

### <a name="example"></a>예제

```cpp
   string_view s = "Hello";
   string_view s2 = s;
```

## <a name="basic_string_viewoperator"></a><a name="op_at"></a>basic_string_view::연산자[]

지정된 인덱스를 사용하여 캐릭터에 const_reference 제공합니다.

```cpp
constexpr const_reference operator[](size_type offset) const;
```

### <a name="parameters"></a>매개 변수

*오프셋*\
참조할 요소의 인덱스입니다.

### <a name="return-value"></a>Return Value

매개 변수 인덱스에 의해 지정된 위치에서 문자에 const_reference.

### <a name="remarks"></a>설명

첫 번째 요소에는 인덱스가 0이고 다음 요소는 양수 정수에 의해 연속적으로 인덱싱되므로 길이 *n* *n의* string_view *nth* 요소가 n - 1로 인덱싱됩니다.

`operator[]`string_view 요소에 [대한](#at) 읽기 액세스를 제공하는 멤버 함수보다 빠릅니다.

`operator[]`인수로 전달된 인덱스가 유효한지 여부를 확인하지 않습니다. 잘못된 인덱스가 전달되어 `operator[]` 정의되지 않은 동작이 발생합니다.

기본 문자열 데이터가 소유 개체에 의해 수정 되거나 삭제 되는 경우 반환 된 참조가 무효화 될 수 있습니다.

[ITERATOR\_\_DEBUG 수준을 1 또는 2로 설정하여 컴파일할 때 string_view 경계 밖의 요소에 액세스하려고 하면 런타임 오류가 발생합니다. \_](../standard-library/iterator-debug-level.md) 자세한 내용은 [확인된 반복기](../standard-library/checked-iterators.md)를 참조하세요.

## <a name="basic_string_viewrbegin"></a><a name="rbegin"></a>basic_string_view::rbegin

반전된 string_view 첫 번째 요소에 const iterator를 반환합니다.

```cpp
constexpr const_reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>Return Value

역반전 string_view 첫 번째 요소에 임의 액세스 이터레이터를 반환하여 해당 반전 string_view 마지막 요소가 무엇인지 해결합니다.

### <a name="remarks"></a>설명

`rbegin`[string_view](#begin) 함께 사용되는 것처럼 반전된 string_view 함께 사용됩니다. `rbegin`이터레이션을 역초기화하는 데 사용할 수 있습니다.

## <a name="basic_string_viewremove_prefix"></a><a name="remove_prefix"></a> basic_string_view::remove_prefix

지정된 수의 요소로 포인터를 앞으로 이동합니다.

```cpp
constexpr void remove_prefix(size_type n);
```

### <a name="remarks"></a>설명

기본 데이터는 변경되지 않은 상태로 둡수입니다. string_view 포인터를 n 요소로 앞으로 `size` 이동하고 개인 데이터 멤버를 크기 -n으로 설정합니다.

## <a name="basic_string_viewremove_suffix"></a><a name="remove_suffix"></a> basic_string_view::remove_suffix

뒤에서 시작하는 요소의 지정된 수에 의해 뷰의 크기를 줄입니다.

```cpp
constexpr void remove_suffix(size_type n);
```

### <a name="remarks"></a>설명

기본 데이터와 포인터를 변경하지 않습니다. 개인 `size` 데이터 멤버의 크기를 설정합니다 .

## <a name="basic_string_viewrend"></a><a name="rend"></a>basic_string_view::rend

반전된 string_view 마지막 요소를 지나가는 요소를 가리키는 구성요소 이터레이터를 반환합니다.

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>Return Value

반전된 string_view 마지막 요소를 지나가는 요소를 가리키는 const 역방향 랜덤 액세스 거점 거점입니다.

### <a name="remarks"></a>설명

`rend`[string_view](#end) 함께 사용되는 것처럼 반전된 string_view 함께 사용됩니다. `rend`역방향 거역이 string_view 끝에 도달했는지 여부를 테스트하는 데 사용할 수 있습니다. `rend`에서 반환한 값은 역참조되지 않아야 합니다.

## <a name="basic_string_viewrfind"></a><a name="rfind"></a>basic_string_view::rfind

지정된 문자 시퀀스와 일치하는 하위 문자열에 대해 string_view 역으로 검색합니다.

```cpp
constexpr size_type rfind(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type rfind(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type rfind(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type rfind(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>매개 변수

*chval*\
멤버 함수가 검색할 문자 값입니다.

*오프셋*\
검색을 시작할 인덱스입니다.

*Ptr*\
멤버 함수가 검색하는 C 문자열입니다.

*횟수*\
멤버 함수가 검색되는 C 문자열의 첫 번째 문자에서 앞으로 계산하는 문자 수입니다.

*Str*\
멤버 함수를 검색하는 string_view.

### <a name="return-value"></a>Return Value

성공하면 하위 문자열의 첫 번째 문자의 인덱스입니다. 그렇지 `npos`않으면 .

## <a name="basic_string_viewsize"></a><a name="size"></a>basic_string_view::크기

string_view 요소 수를 반환합니다.

```cpp
constexpr size_type size() const noexcept;
```

### <a name="return-value"></a>Return Value

string_view 길이입니다.

### <a name="remarks"></a>설명

string_view 예를 들어 `remove_prefix` `remove_suffix`에 의해, 그 길이를 수정할 수 있습니다. 이렇게 하면 기본 문자열 데이터가 수정되지 않으므로 string_view 크기가 반드시 기본 데이터의 크기는 아닙니다.

## <a name="basic_string_viewsubstr"></a><a name="substr"></a>basic_string_view::서브스트라

지정된 위치에서 지정된 문자 수를 나타내는 string_view 반환합니다.

```cpp
constexpr basic_string_view substr(size_type offset = 0, size_type count = npos) const;
```

### <a name="parameters"></a>매개 변수

*오프셋*\
기본값이 0인 복사가 만들어진 위치에 요소를 찾는 인덱스입니다.

*횟수*\
하위 문자열에 포함할 문자 수(있는 경우)입니다.

### <a name="return-value"></a>Return Value

요소의 지정된 하위 시퀀스를 나타내는 string_view 개체입니다.

## <a name="basic_string_viewswap"></a><a name="swap"></a>basic_string_view::스왑

두 string_views 교환, 즉 기본 문자열 데이터에 대 한 포인터 및 크기 값입니다.

```cpp
constexpr void swap(basic_string_view& sv) noexcept;
```

### <a name="parameters"></a>매개 변수

*Sv*\
string_view 포인터와 크기 값을 대상 string_view 포인터와 교환해야 합니다.

## <a name="see-also"></a>참고 항목

[\<string_view>](../standard-library/string-view.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
