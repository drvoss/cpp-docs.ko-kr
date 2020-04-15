---
title: HString 클래스
ms.date: 07/15/2019
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
- corewrappers/Microsoft::WRL::Wrappers::HString::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HString::Detach
- corewrappers/Microsoft::WRL::Wrappers::HString::Get
- corewrappers/Microsoft::WRL::Wrappers::HString::GetRawBuffer
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
- corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
- corewrappers/Microsoft::WRL::Wrappers::HString::Release
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
- corewrappers/Microsoft::WRL::Wrappers::HString::~HString
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HString class
- Microsoft::WRL::Wrappers::HString::Attach method
- Microsoft::WRL::Wrappers::HString::CopyTo method
- Microsoft::WRL::Wrappers::HString::Detach method
- Microsoft::WRL::Wrappers::HString::Get method
- Microsoft::WRL::Wrappers::HString::GetAddressOf method
- Microsoft::WRL::Wrappers::HString::HString, constructor
- Microsoft::WRL::Wrappers::HString::IsValid method
- Microsoft::WRL::Wrappers::HString::MakeReference method
- Microsoft::WRL::Wrappers::HString::operator= operator
- Microsoft::WRL::Wrappers::HString::operator== operator
- Microsoft::WRL::Wrappers::HString::operator!= operator
- Microsoft::WRL::Wrappers::HString::operator< operator
- Microsoft::WRL::Wrappers::HString::Release method
- Microsoft::WRL::Wrappers::HString::Set method
- Microsoft::WRL::Wrappers::HString::~HString, destructor
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
ms.openlocfilehash: 625d7b7d6fc001a6fb63144807b5f29d3620485b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371437"
---
# <a name="hstring-class"></a>HString 클래스

RAII 패턴을 사용하여 [HSTRING의](/windows/win32/WinRT/hstring) 수명을 관리하는 도우미 클래스입니다.

## <a name="syntax"></a>구문

```cpp
class HString;
```

## <a name="remarks"></a>설명

Windows 런타임은 [HSTRING](/windows/win32/WinRT/hstring) 핸들을 통해 문자열에 대한 액세스를 제공합니다. 이 `HString` 클래스는 HSTRING 핸들을 사용하여 단순화할 수 있는 편리한 기능과 연산자도 제공합니다. 이 클래스는 RAII 패턴을 통해 소유한 HSTRING의 수명을 처리할 수 있습니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                | Description
----------------------------------- | -----------------------------------------------------
[HString :: HString](#hstring)        | `HString` 클래스의 새 인스턴스를 초기화합니다.
[HString :~ HString](#tilde-hstring) | 클래스의 현재 인스턴스를 `HString` 삭제합니다.

### <a name="public-methods"></a>Public 메서드

속성                                     | Description
---------------------------------------- | -------------------------------------------------------------------------------------------------------------
[HString :: 연결](#attach)               | 지정된 `HString` 개체를 현재 `HString` 개체와 연결합니다.
[HString::CopyTo](#copyto)               | 현재 `HString` 개체를 HSTRING 개체에 복사합니다.
[HString::D에타치](#detach)               | 지정된 개체를 `HString` 기본 값에서 분리합니다.
[HString :: Get](#get)                     | 기본 HSTRING 핸들의 값을 검색합니다.
[HString::GetAddressOf](#getaddressof)   | 기본 HSTRING 핸들에 대한 포인터를 검색합니다.
[HString :: GetRaw버퍼](#getrawbuffer)   | 기본 문자열 데이터에 대한 포인터를 검색합니다.
[HString::유효합니다.](#isvalid)             | 현재 `HString` 개체가 유효한지 여부를 나타냅니다.
[HString ::확인 참조](#makereference) | 지정된 `HStringReference` 문자열 매개 변수에서 개체를 만듭니다.
[HString::릴리스](#release)             | 기본 문자열 값을 삭제하고 현재 `HString` 개체를 빈 값으로 인티얼합니다.
[HString :: 세트](#set)                     | 현재 `HString` 개체의 값을 지정된 와이드 문자 문자열 `HString` 또는 매개 변수로 설정합니다.

### <a name="public-operators"></a>Public 연산자

속성                                         | Description
-------------------------------------------- | ----------------------------------------------------------------------------
[HString::연산자=](#operator-assign)       | 다른 `HString` 개체의 값을 현재 `HString` 개체로 이동합니다.
[HString::연산자==](#operator-equality)    | 두 매개 변수가 같는지 여부를 나타냅니다.
[HString::연산자!=](#operator-inequality)  | 두 매개 변수가 같지 않은지 여부를 나타냅니다.
[HString::연산자&lt;](#operator-less-than) | 첫 번째 매개 변수가 두 번째 매개 변수보다 적은지 여부를 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HString`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼

## <a name="hstringhstring"></a><a name="tilde-hstring"></a>HString :~ HString

클래스의 현재 인스턴스를 `HString` 삭제합니다.

```cpp
~HString() throw()
```

## <a name="hstringattach"></a><a name="attach"></a>HString :: 연결

지정된 `HString` 개체를 현재 `HString` 개체와 연결합니다.

```cpp
void Attach(
       HSTRING hstr
       ) throw()
```

### <a name="parameters"></a>매개 변수

*hstr*<br/>
기존 `HString` 개체입니다.

## <a name="hstringcopyto"></a><a name="copyto"></a>HString::복사

현재 `HString` 개체를 HSTRING 개체에 복사합니다.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
복사본을 받는 HSTRING입니다.

### <a name="remarks"></a>설명

이 메서드는 WindowsDuplicateString 함수를 [호출합니다.](/windows/win32/api/winstring/nf-winstring-windowsduplicatestring)

## <a name="hstringdetach"></a><a name="detach"></a>HString::D에타치

지정된 개체를 `HString` 기본 값에서 분리합니다.

```cpp
HSTRING Detach() throw()
```

### <a name="return-value"></a>Return Value

분리 `HString` 작업이 시작되기 전의 기본 값입니다.

## <a name="hstringget"></a><a name="get"></a>HString :: Get

기본 HSTRING 핸들의 값을 검색합니다.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Return Value

기본 HSTRING 핸들의 값입니다.

## <a name="hstringgetaddressof"></a><a name="getaddressof"></a>HString::GetAddressOf

기본 HSTRING 핸들에 대한 포인터를 검색합니다.

```cpp
HSTRING* GetAddressOf() throw()
```

### <a name="return-value"></a>Return Value

기본 HSTRING 핸들에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 작업 후에 기본 HSTRING 핸들의 문자열 값이 삭제됩니다.

## <a name="hstringgetrawbuffer"></a><a name="getrawbuffer"></a>HString :: GetRaw버퍼

기본 문자열 데이터에 대한 포인터를 검색합니다.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>매개 변수

*길이* 데이터 길이를 받는 **int** 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

기본 문자열 데이터에 대한 **const** 포인터입니다.

## <a name="hstringhstring"></a><a name="hstring"></a>HString :: HString

`HString` 클래스의 새 인스턴스를 초기화합니다.

```cpp
HString() throw();
HString(HString&& other) throw();
```

### <a name="parameters"></a>매개 변수

*hstr*<br/>
HSTRING 핸들입니다.

*다른*<br/>
기존 `HString` 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 비어 `HString` 있는 새 개체를 초기화합니다.

두 번째 생성자는 새 `HString` 개체를 기존 *다른* 매개 변수의 값으로 초기화한 다음 *다른* 매개 변수를 삭제합니다.

## <a name="hstringisvalid"></a><a name="isvalid"></a>HString::유효합니다.

현재 `HString` 개체가 비어 있는지 여부를 나타냅니다.

```cpp
bool IsValid() const throw()
```

### <a name="parameters"></a>매개 변수

**true** 현재 `HString` 개체가 비어 있지 않은 경우 true입니다. 그렇지 **않으면, 거짓**.

## <a name="hstringmakereference"></a><a name="makereference"></a>HString ::확인 참조

지정된 `HStringReference` 문자열 매개 변수에서 개체를 만듭니다.

```cpp
template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[ sizeDest]);

    template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[sizeDest],
              unsigned int len);
```

### <a name="parameters"></a>매개 변수

*크기 가장*<br/>
대상 `HStringReference` 버퍼의 크기를 지정하는 템플릿 매개 변수입니다.

*Str*<br/>
와이드 문자 문자열에 대한 참조입니다.

*렌*<br/>
이 작업에 사용할 *str* 매개 변수 버퍼의 최대 길이입니다. *len* 매개 변수를 지정하지 않으면 전체 *str* 매개 변수가 사용됩니다.

### <a name="return-value"></a>Return Value

값이 `HStringReference` 지정된 *str* 매개 변수와 동일한 개체입니다.

## <a name="hstringoperator-operator"></a><a name="operator-assign"></a>HString::연산자= 연산자

다른 `HString` 개체의 값을 현재 `HString` 개체로 이동합니다.

```cpp
HString& operator=(HString&& other) throw()
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
기존 `HString` 개체입니다.

### <a name="remarks"></a>설명

기존 *다른* 개체의 값이 현재 `HString` 개체에 복사된 다음 *다른* 개체가 소멸됩니다.

## <a name="hstringoperator-operator"></a><a name="operator-equality"></a>HString::연산자== 연산자

두 매개 변수가 같는지 여부를 나타냅니다.

```cpp
inline bool operator==(
               const HString& lhs,
               const HString& rhs) throw()

inline bool operator==(
                const HString& lhs,
                const HStringReference& rhs) throw()

inline bool operator==(
                const HStringReference& lhs,
                const HString& rhs) throw()

inline bool operator==(
                 const HSTRING& lhs,
                 const HString& rhs) throw()

inline bool operator==(
                 const HString& lhs,
                 const HSTRING& rhs) throw()
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 첫 번째 매개 변수입니다. *lhs는* `HString` 또는 `HStringReference` 개체 또는 HSTRING 핸들일 수 있습니다.

*rhs*<br/>
비교할 두 번째 매개 변수입니다. *rhs는* `HString` 또는 `HStringReference` 개체 또는 HSTRING 핸들일 수 있습니다.

### <a name="return-value"></a>Return Value

*lhs* 및 *rhs* 매개 변수가 같으면 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="hstringoperator-operator"></a><a name="operator-inequality"></a>HString::연산자!= 연산자

두 매개 변수가 같지 않은지 여부를 나타냅니다.

```cpp
inline bool operator!=( const HString& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HStringReference& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HStringReference& rhs) throw()

inline bool operator!=( const HSTRING& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HSTRING& rhs) throw()
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 첫 번째 매개 변수입니다. *lhs는* `HString` 또는 `HStringReference` 개체 또는 HSTRING 핸들일 수 있습니다.

*rhs*<br/>
비교할 두 번째 매개 변수입니다. *rhs는* `HString` 또는 `HStringReference` 개체 또는 HSTRING 핸들일 수 있습니다.

### <a name="return-value"></a>Return Value

*lhs* 및 *rhs* 매개 변수가 같지 않은 경우 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="hstringoperatorlt-operator"></a><a name="operator-less-than"></a>HString::연산자 연산자&lt;

첫 번째 매개 변수가 두 번째 매개 변수보다 적은지 여부를 나타냅니다.

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 첫 번째 매개 변수입니다. *lhs는* `HString`에 대한 참조일 수 있습니다.

*rhs*<br/>
비교할 두 번째 매개 변수입니다. *rhs는* 에 대한 `HString`참조가 될 수 있습니다.

### <a name="return-value"></a>Return Value

*lhs* 매개 변수가 *rhs* 매개 변수보다 적으면 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="hstringrelease"></a><a name="release"></a>HString::릴리스

기본 문자열 값을 삭제하고 현재 `HString` 개체를 빈 값으로 인티얼합니다.

```cpp
void Release() throw()
```

## <a name="hstringset"></a><a name="set"></a>HString :: 세트

현재 `HString` 개체의 값을 지정된 와이드 문자 문자열 `HString` 또는 매개 변수로 설정합니다.

```cpp
HRESULT Set(
          const wchar_t* str) throw();
HRESULT Set(
          const wchar_t* str,
          unsigned int len
           ) throw();
HRESULT Set(
          const HSTRING& hstr
           ) throw();
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
와이드 문자 문자열입니다.

*렌*<br/>
현재 `HString` 개체에 할당된 *str* 매개 변수의 최대 길이입니다.

*hstr*<br/>
기존 `HString` 개체입니다.
