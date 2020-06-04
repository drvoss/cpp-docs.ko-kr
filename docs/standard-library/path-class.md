---
title: path 클래스
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 669dfd2c8cd8576ebfb6684bab7cf63cdd51babc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372116"
---
# <a name="path-class"></a>path 클래스

**경로** 클래스는 박람회를 `string_type`위해 `myname` 여기에 호출된 형식의 개체를 저장하며 경로 이름으로 사용하기에 적합합니다. `string_type`는 의 동의어 `basic_string<value_type>` `value_type` **wchar_t입니다.** **char**

자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.

## <a name="syntax"></a>구문

```cpp
class path;
```

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[경로](#path)|`path`를 생성합니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[const_iterator](#const_iterator)|`iterator`의 동의어입니다.|
|[반복기](#iterator)|의 `path` 구성 요소를 지정하는 양방향 상수 이터레이터입니다. `myname`|
|[string_type](#string_type)|이 형식은 `basic_string<value_type>`의 동의어입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[추가](#append)|변환된 `mypath`에 지정된 시퀀스를 preferred_separator 삽입합니다.|
|[할당](#assign)|필요에 `mypath` 따라 변환된 지정된 시퀀스로 바꿉니다.|
|[시작](#begin)|경로 `path::iterator` 이름에 첫 번째 경로 요소를 지정하는 경우(있는 경우)를 반환합니다.|
|[c_str](#c_str)|의 첫 번째 문자에 `mypath`대한 포인터를 반환합니다.|
|[명확한](#clear)|를 `mypath.clear()`실행합니다.|
|[비교](#compare)|비교 값을 반환합니다.|
|[Concat](#compare)|필요에 따라 `mypath`변환된 에 지정된 시퀀스를 (구분 기호를 삽입하지 않음)에 보도록 합니다.|
|[빈](#empty)|`mypath.empty()`를 반환합니다.|
|[end](#end)|형식의 `iterator`시퀀스 끝 이터레이터를 반환합니다.|
|[확장](#extension)|의 접미사를 `filename()`반환합니다.|
|[파일](#filename)|myname의 루트 디렉터리 구성 요소(구체적으로는 `empty() path() : *--end()`)를 반환합니다. 구성 요소는 비어 있을 수 있습니다.|
|[generic_string](#generic_string)|슬래시로 변환된 백슬래시와 함께 `this->string<Elem, Traits, Alloc>(al)`를 반환합니다(Windows).|
|[generic_u16string](#generic_u16string)|슬래시로 변환된 백슬래시와 함께 `u16string()`를 반환합니다(Windows).|
|[generic_u32string](#generic_u32string)|슬래시로 변환된 백슬래시와 함께 `u32string()`를 반환합니다(Windows).|
|[generic_u8string](#generic_u8string)|슬래시로 변환된 백슬래시와 함께 `u8string()`를 반환합니다(Windows).|
|[generic_wstring](#generic_wstring)|슬래시로 변환된 백슬래시와 함께 `wstring()`를 반환합니다(Windows).|
|[has_extension](#has_extension)|`!extension().empty()`를 반환합니다.|
|[has_filename](#has_filename)|`!filename().empty()`를 반환합니다.|
|[has_parent_path](#has_parent_path)|`!parent_path().empty()`를 반환합니다.|
|[has_relative_path](#has_relative_path)|`!relative_path().empty()`를 반환합니다.|
|[has_root_directory](#has_root_directory)|`!root_directory().empty()`를 반환합니다.|
|[has_root_name](#has_root_name)|`!root_name().empty()`를 반환합니다.|
|[has_root_path](#has_root_path)|`!root_path().empty()`를 반환합니다.|
|[has_stem](#has_stem)|`!stem().empty()`를 반환합니다.|
|[is_absolute](#is_absolute)|Windows의 경우 함수가 반환됩니다. `has_root_name() && has_root_directory()` POSIX의 경우 함수가 반환됩니다. `has_root_directory()`|
|[is_relative](#is_relative)|`!is_absolute()`를 반환합니다.|
|[make_preferred](#make_preferred)|필요에 따라 각 구분 기호를 preferred_separator 변환합니다.|
|[네이티브](#native)|`myname`를 반환합니다.|
|[parent_path](#parent_path)|의 `myname`상위 경로 구성 요소를 반환합니다.|
|[preferred_separator](#preferred_separator)|상수 개체는 호스트 운영 체제에 따라 경로 구성 요소를 구분하는 기본 문자를 제공합니다. |
|[relative_path](#relative_path)|의 `myname`상대 경로 구성 요소를 반환합니다. |
|[remove_filename](#remove_filename)|파일 이름을 제거합니다.|
|[replace_extension](#replace_extension)|`myname`의 확장을 대체합니다. |
|[replace_filename](#replace_filename)|R 파일 이름을 대체합니다.|
|[root_directory](#root_directory)|의 `myname`루트 디렉터리 구성 요소를 반환합니다. |
|[root_name](#root_name)|의 `myname`루트 이름 구성 요소를 반환합니다. |
|[root_path](#root_path)|의 `myname`루트 경로 구성 요소를 반환합니다.|
|[stem](#stem)|의 `stem` 구성 `myname`요소를 반환합니다.|
|[string](#string)|에 저장된 시퀀스를 변환합니다. `mypath`|
|[스왑](#swap)|를 `swap(mypath, right.mypath)`실행합니다.|
|[u16스트링](#u16string)|저장된 시퀀스를 `mypath` UTF-16으로 변환하고 형식의 `u16string`개체에 저장하여 반환합니다.|
|[u32스트링](#u32string)|저장된 시퀀스를 `mypath` UTF-32로 변환하고 형식의 `u32string`개체에 저장하여 반환합니다.|
|[u8string](#u8string)|에 `mypath` 저장된 시퀀스를 UTF-8로 변환하고 형식의 `u8string`개체에 저장하여 반환합니다.|
|[Value_type](#value_type)|형식은 호스트 운영 체제에서 선호하는 경로 요소를 설명합니다.|
|[스트링](#wstring)|시퀀스에 대해 `mypath` 호스트 시스템에서 선호하는 인코딩으로 저장된 `wchar_t` 시퀀스를 변환하고 형식의 `wstring`개체에 저장된 시퀀스를 반환합니다.|

### <a name="operators"></a>연산자

|연산자|Description|
|-|-|
|[연산자 =](#op_as)|패스의 요소를 다른 패스의 복사본으로 바꿉습니다.|
|[연산자+=](#op_add)|다양한 `concat` 표현식.|
|[연산자/=](#op_divide)|다양한 `append` 표현식.|
|[operator string_type](#op_string)|`myname`를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<파일 시스템>

**네임스페이스:** std::experimental::filesystem

## <a name="pathappend"></a><a name="append"></a>경로:::부속

변환된 순서를 `mypath`필요에 따라 삽입하고 `preferred_separator` 에 지정된 시퀀스를 더합니다.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>매개 변수

*소스*\
지정된 시퀀스입니다.

*첫 번째*\
지정된 시퀀스의 시작입니다.

*마지막*\
지정된 시퀀스의 끝입니다.

## <a name="pathassign"></a><a name="assign"></a>경로::할당

필요에 `mypath` 따라 변환된 지정된 시퀀스로 바꿉니다.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>매개 변수

*소스*\
지정된 시퀀스입니다.

*첫 번째*\
지정된 시퀀스의 시작입니다.

*마지막*\
지정된 시퀀스의 끝입니다.

## <a name="pathbegin"></a><a name="begin"></a>경로::시작

경로 `path::iterator` 이름에 첫 번째 경로 요소를 지정하는 경우(있는 경우)를 반환합니다.

```cpp
iterator begin() const;
```

## <a name="pathc_str"></a><a name="c_str"></a>경로::c_str

의 첫 번째 문자에 `mypath`대한 포인터를 반환합니다.

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="pathclear"></a><a name="clear"></a>경로::지우기

를 `mypath.clear()`실행합니다.

```cpp
void clear() noexcept;
```

## <a name="pathcompare"></a><a name="compare"></a>경로::비교

첫 번째 함수는 `mypath.compare(pval.native())`를 반환합니다. 두 번째 함수는 `mypath.compare(str)`를 반환합니다. 세 번째 `mypath.compare(ptr)`함수가 반환됩니다.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>매개 변수

*Pval*\
비교할 경로입니다.

*Str*\
비교할 문자열입니다.

*Ptr*\
비교할 포인터입니다.

## <a name="pathconcat"></a><a name="concat"></a>경로::concat

필요에 따라 `mypath`변환된 에 지정된 시퀀스를 (구분 기호를 삽입하지 않음)에 보도록 합니다.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>매개 변수

*소스*\
지정된 시퀀스입니다.

*첫 번째*\
지정된 시퀀스의 시작입니다.

*마지막*\
지정된 시퀀스의 끝입니다.

## <a name="pathconst_iterator"></a><a name="const_iterator"></a>경로::const_iterator

`iterator`의 동의어입니다.

```cpp
typedef iterator const_iterator;
```

## <a name="pathempty"></a><a name="empty"></a>경로::비어 있음

`mypath.empty()`를 반환합니다.

```cpp
bool empty() const noexcept;
```

## <a name="pathend"></a><a name="end"></a>경로::끝

형식의 `iterator`시퀀스 끝 이터레이터를 반환합니다.

```cpp
iterator end() const;
```

## <a name="pathextension"></a><a name="extension"></a>경로::확장

의 접미사를 `filename()`반환합니다.

```cpp
path extension() const;
```

### <a name="remarks"></a>설명

`filename() X` 다음과 같은 접미사를 반환합니다.

점이 `X == path(".") || X == path("..")` 없는 `X` 경우 접미사가 비어 있습니다.

그렇지 않은 경우 접미사가 맨 오른쪽 점으로 시작되고 해당 점을 포함합니다.

## <a name="pathfilename"></a><a name="filename"></a>경로::파일 이름

myname의 루트 디렉터리 구성 요소(구체적으로는 `empty() path() : *--end()`)를 반환합니다. 구성 요소는 비어 있을 수 있습니다.

```cpp
path filename() const;
```

## <a name="pathgeneric_string"></a><a name="generic_string"></a>경로::generic_string

슬래시로 변환된 백슬래시와 함께 `this->string<Elem, Traits, Alloc>(al)`를 반환합니다(Windows).

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="pathgeneric_u16string"></a><a name="generic_u16string"></a>경로::generic_u16string

슬래시로 변환된 백슬래시와 함께 `u16string()`를 반환합니다(Windows).

```cpp
u16string generic_u16string() const;
```

## <a name="pathgeneric_u32string"></a><a name="generic_u32string"></a>경로::generic_u32string

슬래시로 변환된 백슬래시와 함께 `u32string()`를 반환합니다(Windows).

```cpp
u32string generic_u32string() const;
```

## <a name="pathgeneric_u8string"></a><a name="generic_u8string"></a>경로::generic_u8string

슬래시로 변환된 백슬래시와 함께 `u8string()`를 반환합니다(Windows).

```cpp
string generic_u8string() const;
```

## <a name="pathgeneric_wstring"></a><a name="generic_wstring"></a>경로::generic_wstring

슬래시로 변환된 백슬래시와 함께 `wstring()`를 반환합니다(Windows).

```cpp
wstring generic_wstring() const;
```

## <a name="pathhas_extension"></a><a name="has_extension"></a>경로::has_extension

`!extension().empty()`를 반환합니다.

```cpp
bool has_extension() const;
```

## <a name="pathhas_filename"></a><a name="has_filename"></a>경로::has_filename

`!filename().empty()`를 반환합니다.

```cpp
bool has_filename() const;
```

## <a name="pathhas_parent_path"></a><a name="has_parent_path"></a>경로::has_parent_path

`!parent_path().empty()`를 반환합니다.

```cpp
bool has_parent_path() const;
```

## <a name="pathhas_relative_path"></a><a name="has_relative_path"></a>경로::has_relative_path

`!relative_path().empty()`를 반환합니다.

```cpp
bool has_relative_path() const;
```

## <a name="pathhas_root_directory"></a><a name="has_root_directory"></a>경로::has_root_directory

`!root_directory().empty()`를 반환합니다.

```cpp
bool has_root_directory() const;
```

## <a name="pathhas_root_name"></a><a name="has_root_name"></a>경로::has_root_name

`!root_name().empty()`를 반환합니다.

```cpp
bool has_root_name() const;
```

## <a name="pathhas_root_path"></a><a name="has_root_path"></a>경로::has_root_path

`!root_path().empty()`를 반환합니다.

```cpp
bool has_root_path() const;
```

## <a name="pathhas_stem"></a><a name="has_stem"></a>경로::has_stem

`!stem().empty()`를 반환합니다.

```cpp
bool has_stem() const;
```

## <a name="pathis_absolute"></a><a name="is_absolute"></a>경로::is_absolute

Windows의 경우 함수가 반환됩니다. `has_root_name() && has_root_directory()` POSIX의 경우 함수가 반환됩니다. `has_root_directory()`

```cpp
bool is_absolute() const;
```

## <a name="pathis_relative"></a><a name="is_relative"></a>경로::is_relative

`!is_absolute()`를 반환합니다.

```cpp
bool is_relative() const;
```

## <a name="pathiterator"></a><a name="iterator"></a>경로::이터레이터

의 경로 구성 요소를 지정하는 양방향 상수 이터레이터입니다. `myname`

```cpp
class iterator
   {
   // bidirectional iterator for path
   typedef bidirectional_iterator_tag iterator_category;
   typedef path_type value_type;
   typedef ptrdiff_t difference_type;
   typedef const value_type *pointer;
   typedef const value_type& reference;
   // ...
   };
```

### <a name="remarks"></a>설명

클래스는 시퀀스의 `path` 구성 요소를 지정하는 양방향 상수 `myname` 이터레이터를 설명합니다.

1. 루트 이름(있는 경우)

1. 루트 디렉터리(있는 경우)

1. 부모의 `path`나머지 디렉터리 요소 ( 있는 경우) 파일 이름으로 끝나는 경우

`pval` 형식의 `path`개체:

1. `path::iterator X = pval.begin()`경로 이름의 첫 `path` 번째 요소를 지정합니다(있는 경우).

1. `X == pval.end()`이는 구성 `X` 요소 시퀀스의 끝부분을 가리키는 경우의 경우와 마찬가지입니다.

1. `*X`현재 구성 요소와 일치하는 문자열을 반환합니다.

1. `++X`는 시퀀스에서 다음 구성 요소(있는 경우)를 지정합니다.

1. `--X`는 시퀀스에서 이전 구성 요소(있는 경우)를 지정합니다.

1. 을 `myname` 변경하면 에서 요소를 지정하는 모든 `myname`이터레이터가 무효화됩니다.

## <a name="pathmake_preferred"></a><a name="make_preferred"></a>경로::make_preferred

각 구분 기호를 필요에 따라 `preferred_separator` 로 변환합니다.

```cpp
path& make_preferred();
```

## <a name="pathnative"></a><a name="native"></a>경로::네이티브

`myname`를 반환합니다.

```cpp
const string_type& native() const noexcept;
```

## <a name="pathoperator"></a><a name="op_as"></a>경로::연산자=

패스의 요소를 다른 패스의 복사본으로 바꿉습니다.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
`path`에 복사할 [경로](../standard-library/path-class.md)입니다.

*소스*\
소스 경로입니다.

### <a name="remarks"></a>설명

첫 번째 멤버 `right.myname` 연산자는 에 복사합니다. `myname` 두 번째 멤버 `right.myname` `myname`연산자는 로 이동합니다. 세 번째 멤버 연산자는 `*this = path(source)`와 동일하게 행동합니다.

## <a name="pathoperator"></a><a name="op_add"></a>경로::연산자+=

다양한 `concat` 표현식.

```cpp
path& operator+=(const path& right);
path& operator+=(const string_type& str);
path& operator+=(const value_type *ptr);
path& operator+=(value_type elem);

template <class Source>
path& operator+=(const Source& source);

template <class Elem>
path& operator+=(Elem elem);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
추가된 경로입니다.

*Str*\
추가된 문자열입니다.

*Ptr*\
추가된 포인터입니다.

*Elem*\
추가된 `value_type` `Elem`또는 .

*소스*\
추가된 소스입니다.

### <a name="remarks"></a>설명

멤버 함수는 다음 해당 식과 동일하게 작동합니다.

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="pathoperator"></a><a name="op_divide"></a>경로::연산자/=

다양한 `append` 표현식.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
추가된 경로입니다.

*소스*\
추가된 소스입니다.

### <a name="remarks"></a>설명

멤버 함수는 다음 해당 식과 동일하게 작동합니다.

1. `append(right);`

1. `append(source);`

## <a name="pathoperator-string_type"></a><a name="op_string"></a>경로::연산자 string_type

`myname`를 반환합니다.

```cpp
operator string_type() const;
```

## <a name="pathparent_path"></a><a name="parent_path"></a>경로::parent_path

의 `myname`상위 경로 구성 요소를 반환합니다.

```cpp
path parent_path() const;
```

### <a name="remarks"></a>설명

특히 제거 `myname` `filename().native()` 후의 접두사와 바로 `myname` 앞에 있는 디렉터리 구분 기호의 부모 경로 구성 요소를 반환합니다. (마찬가지로, `begin() != end()`경우 . `[begin(), --end())` `operator/=` 구성 요소가 비어 있을 수 있습니다.

## <a name="pathpath"></a><a name="path"></a>경로::p

다양한 방법으로 `path` 구성합니다.

```cpp
path();

path(const path& right);
path(path&& right) noexcept;

template <class Source>
path(const Source& source);

template <class Source>
path(const Source& source, const locale& loc);

template <class InIt>
path(InIt first, InIt last);

template <class InIt>
path(InIt first, InIt last, const locale& loc);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
구성된 경로가 복사본이 되는 경로입니다.

*소스*\
생성된 경로가 복사본이 될 소스입니다.

*Loc*\
지정된 로캘입니다.

*첫 번째*\
복사할 첫 번째 요소의 위치입니다.

*마지막*\
복사할 마지막 요소의 위치입니다.

### <a name="remarks"></a>설명

생성자는 모두 다양한 `myname` 방법으로 구성합니다.

그것을 `path()` 위해 `myname()`.

) `path(const path& right` `myname(right.myname)`입니다.

그것을 `path(path&& right)` 위해 `myname(right.myname)`.

그것을 `template<class Source> path(const Source& source)` 위해 `myname(source)`.

이를 `template<class Source> path(const Source& source, const locale& loc)` `myname(source)`위해 `loc`에서 필요한 codecvt 면을 얻습니다.

그것을 `template<class InIt> path(InIt first, InIt last)` 위해 `myname(first, last)`.

이를 `template<class InIt> path(InIt first, InIt last, const locale& loc)` `myname(first, last)`위해 `loc`에서 필요한 codecvt 면을 얻습니다.

## <a name="pathpreferred_separator"></a><a name="preferred_separator"></a>경로::p참조_분리기

상수 개체는 호스트 운영 체제에 따라 경로 구성 요소를 구분하는 기본 문자를 제공합니다.

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume POSIX
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>설명

대부분의 Windows 컨텍스트에서는 L'/'을 대신 사용하여 동일하게 허용됩니다.

## <a name="pathrelative_path"></a><a name="relative_path"></a>경로::relative_path

의 `myname`상대 경로 구성 요소를 반환합니다.

```cpp
path relative_path() const;
```

### <a name="remarks"></a>설명

특히 제거 `myname` `root_path().native()` 후의 접미사와 즉시 `myname` 후속 중복 디렉터리 구분 기호의 상대 경로 구성 요소를 반환합니다. 구성 요소는 비어 있을 수 있습니다.

## <a name="pathremove_filename"></a><a name="remove_filename"></a>경로::remove_filename

파일 이름을 제거합니다.

```cpp
path& remove_filename();
```

## <a name="pathreplace_extension"></a><a name="replace_extension"></a>경로::replace_extension

`myname`의 확장을 대체합니다.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>매개 변수

*뉴 익스트*\
새 확장입니다.

### <a name="remarks"></a>설명

먼저 `myname`에서 접미사를 `extension().native()` 제거합니다. `!newext.empty() && newext[0] != dot` 그런 다음 `dot` (있는 `*path(".").c_str()` `dot` 위치) 다음에 `myname`추가됩니다. 그런 다음 *newext가* 에 `myname`추가됩니다.

## <a name="pathreplace_filename"></a><a name="replace_filename"></a>경로::replace_filename

파일 이름을 바꿉니다.

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>매개 변수

*Pval*\
파일 이름의 경로입니다.

### <a name="remarks"></a>설명

멤버 함수에서 다음을 실행합니다.

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="pathroot_directory"></a><a name="root_directory"></a>경로::root_directory

의 `myname`루트 디렉터리 구성 요소를 반환합니다.

```cpp
path root_directory() const;
```

### <a name="remarks"></a>설명

구성 요소는 비어 있을 수 있습니다.

## <a name="pathroot_name"></a><a name="root_name"></a>경로::root_name

의 `myname`루트 이름 구성 요소를 반환합니다.

```cpp
path root_name() const;
```

### <a name="remarks"></a>설명

구성 요소는 비어 있을 수 있습니다.

## <a name="pathroot_path"></a><a name="root_path"></a>경로::root_path

의 `myname`루트 경로 구성 요소를 반환합니다.

```cpp
path root_path() const;
```

### <a name="remarks"></a>설명

의 루트 경로 `myname`구성 `root_name()`  /  `root_directory`요소를 반환합니다. 구성 요소는 비어 있을 수 있습니다.

## <a name="pathstem"></a><a name="stem"></a>경로 ::stem

의 `stem` 구성 `myname`요소를 반환합니다.

```cpp
path stem() const;
```

### <a name="remarks"></a>설명

특히 `filename().native()` `stem` 후행이 제거된 구성 `extension().native()` 요소를 `myname`반환합니다. 구성 요소는 비어 있을 수 있습니다.

## <a name="pathstring"></a><a name="string"></a>경로::문자열

에 저장된 시퀀스를 변환합니다. `mypath`

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>설명

첫 번째(템플릿) 멤버 함수는 다음과 `mypath` 같은 방식으로 저장된 시퀀스를 변환합니다.

1. `string<char, Traits, Alloc>()`의 경우 `string()`

1. `string<wchar_t, Traits, Alloc>()`의 경우 `wstring()`

1. `string<char16_t, Traits, Alloc>()`의 경우 `u16string()`

1. `string<char32_t, Traits, Alloc>()`의 경우 `u32string()`

두 번째 멤버 함수는 char `mypath` 시퀀스에 대해 호스트 시스템에서 선호하는 **char** 인코딩으로 저장된 시퀀스를 `string`변환하고 형식의 개체에 저장하여 반환합니다.

## <a name="pathstring_type"></a><a name="string_type"></a>경로::string_type

이 형식은 `basic_string<value_type>`의 동의어입니다.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="pathswap"></a><a name="swap"></a>경로::스왑

를 `swap(mypath, right.mypath)`실행합니다.

```cpp
void swap(path& right) noexcept;
```

## <a name="pathu16string"></a><a name="u16string"></a>경로::u16string

저장된 시퀀스를 `mypath` UTF-16으로 변환하고 형식의 `u16string`개체에 저장하여 반환합니다.

```cpp
u16string u16string() const;
```

## <a name="pathu32string"></a><a name="u32string"></a>경로::u32string

저장된 시퀀스를 `mypath` UTF-32로 변환하고 형식의 `u32string`개체에 저장하여 반환합니다.

```cpp
u32string u32string() const;
```

## <a name="pathu8string"></a><a name="u8string"></a>경로::u8string

에 `mypath` 저장된 시퀀스를 UTF-8로 변환하고 형식의 `u8string`개체에 저장하여 반환합니다.

```cpp
string u8string() const;
```

## <a name="pathvalue_type"></a><a name="value_type"></a>경로::value_type

형식은 호스트 `path` 운영 체제에서 선호하는 요소를 설명합니다.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume POSIX
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="pathwstring"></a><a name="wstring"></a>경로::스트링

wchar_t 시퀀스에 `mypath` 대해 호스트 시스템에서 선호하는 인코딩으로 **wchar_t** 저장된 시퀀스를 변환하고 형식의 `wstring`개체에 저장하여 반환합니다.

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)
