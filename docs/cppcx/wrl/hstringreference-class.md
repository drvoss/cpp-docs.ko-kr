---
title: HStringReference 클래스
ms.date: 07/15/2019
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::Get
- corewrappers/Microsoft::WRL::Wrappers::GetRawBuffer
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HStringReference class
- Microsoft::WRL::Wrappers::HStringReference::CopyTo method
- Microsoft::WRL::Wrappers::HStringReference::Get method
- Microsoft::WRL::Wrappers::HStringReference::HStringReference, constructor
- Microsoft::WRL::Wrappers::HStringReference::operator= operator
- Microsoft::WRL::Wrappers::HStringReference::operator== operator
- Microsoft::WRL::Wrappers::HStringReference::operator!= operator
- Microsoft::WRL::Wrappers::HStringReference::operator< operator
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
ms.openlocfilehash: fd064f97081fad1a9df9de0865bb7c46ad5b4484
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371419"
---
# <a name="hstringreference-class"></a>HStringReference 클래스

기존 문자열에서 만든 HSTRING을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class HStringReference;
```

## <a name="remarks"></a>설명

새 HSTRING에서 백업 버퍼의 수명은 Windows 런타임에서 관리되지 않습니다. 호출자는 힙 할당을 방지하고 메모리 누수의 위험을 제거하기 위해 스택 프레임에 소스 문자열을 할당합니다. 또한 호출자는 연결된 HSTRING의 수명 동안 소스 문자열이 변경되지 않도록 해야 합니다. 자세한 내용은 [WindowsCreateStringReference 기능을](/windows/win32/api/winstring/nf-winstring-windowscreatestringreference)참조하십시오.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                                    | Description
------------------------------------------------------- | -----------------------------------------------------------
[HString 참조::H문자열 참조](#hstringreference) | `HStringReference` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

멤버                              | Description
----------------------------------- | ------------------------------------------------------------------
[HStringReference::CopyTo](#copyto) | 현재 `HStringReference` 개체를 HSTRING 개체에 복사합니다.
[HString 참조 ::Get](#get)       | 기본 HSTRING 핸들의 값을 검색합니다.
[HString참조::GetRaw버퍼](#getrawbuffer) | 기본 문자열 데이터에 대한 포인터를 검색합니다.

### <a name="public-operators"></a>Public 연산자

속성                                                  | Description
----------------------------------------------------- | ----------------------------------------------------------------------------------------------
[HStringReference::연산자=](#operator-assign)       | 다른 `HStringReference` 개체의 값을 현재 `HStringReference` 개체로 이동합니다.
[HStringReference::연산자==](#operator-equality)    | 두 매개 변수가 같는지 여부를 나타냅니다.
[HStringReference::연산자!=](#operator-inequality)  | 두 매개 변수가 같지 않은지 여부를 나타냅니다.
[HStringReference::연산자&lt;](#operator-less-than) | 첫 번째 매개 변수가 두 번째 매개 변수보다 적은지 여부를 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HStringReference`

## <a name="requirements"></a>요구 사항

**헤더:** 코어래퍼.h

**네임스페이스:** 마이크로소프트::WRL::래퍼

## <a name="hstringreferencecopyto"></a><a name="copyto"></a>HString 참조::복사

현재 `HStringReference` 개체를 HSTRING 개체에 복사합니다.

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

## <a name="hstringreferenceget"></a><a name="get"></a>HString 참조 ::Get

기본 HSTRING 핸들의 값을 검색합니다.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Return Value

기본 HSTRING 핸들의 값입니다.

## <a name="hstringreferencegetrawbuffer"></a><a name="getrawbuffer"></a>HString참조::GetRaw버퍼

기본 문자열 데이터에 대한 포인터를 검색합니다.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>매개 변수

*길이* 데이터 길이를 받는 **int** 변수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

기본 문자열 데이터에 대한 **const** 포인터입니다.

## <a name="hstringreferencehstringreference"></a><a name="hstringreference"></a>HString 참조::H문자열 참조

`HStringReference` 클래스의 새 인스턴스를 초기화합니다.

```cpp
template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest]) throw();

template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest],
                 unsigned int len) throw();

HStringReference(HStringReference&& other) throw();
```

### <a name="parameters"></a>매개 변수

*크기 가장*<br/>
대상 `HStringReference` 버퍼의 크기를 지정하는 템플릿 매개 변수입니다.

*Str*<br/>
와이드 문자 문자열에 대한 참조입니다.

*렌*<br/>
이 작업에 사용할 *str* 매개 변수 버퍼의 최대 길이입니다. *len* 매개 변수를 지정하지 않으면 전체 *str* 매개 변수가 사용됩니다. *렌이* 크기보다 큰 *경우Dest,* *렌은* *크기로 설정Dest*-1.

*다른*<br/>
다른 `HStringReference` 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 매개 `HStringReference` 변수 *str과*크기가 같은 새 개체를 초기화합니다.

두 번째 생성자는 매개 `HStringReference` 변수 *len에*의해 크기 지정하는 새 개체를 초기화합니다.

세 번째 생성자는 새 `HStringReference` 개체를 *다른* 매개 변수의 값으로 초기화한 다음 *다른* 매개 변수를 삭제합니다.

## <a name="hstringreferenceoperator"></a><a name="operator-assign"></a>HStringReference::연산자=

다른 `HStringReference` 개체의 값을 현재 `HStringReference` 개체로 이동합니다.

```cpp
HStringReference& operator=(HStringReference&& other) throw()
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
기존 `HStringReference` 개체입니다.

### <a name="remarks"></a>설명

기존 *다른* 개체의 값이 현재 `HStringReference` 개체에 복사된 다음 *다른* 개체가 소멸됩니다.

## <a name="hstringreferenceoperator"></a><a name="operator-equality"></a>HStringReference::연산자==

두 매개 변수가 같는지 여부를 나타냅니다.

```cpp
inline bool operator==(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 첫 번째 매개 변수입니다. *lhs는* `HStringReference` 개체 또는 HSTRING 핸들일 수 있습니다.

*rhs*<br/>
비교할 두 번째 매개 변수입니다.  *rhs는* `HStringReference` 개체 또는 HSTRING 핸들일 수 있습니다.

### <a name="return-value"></a>Return Value

*lhs* 및 *rhs* 매개 변수가 같으면 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="hstringreferenceoperator"></a><a name="operator-inequality"></a>HStringReference::연산자!=

두 매개 변수가 같지 않은지 여부를 나타냅니다.

```cpp
inline bool operator!=(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 첫 번째 매개 변수입니다. *lhs는* `HStringReference` 개체 또는 HSTRING 핸들일 수 있습니다.

*rhs*<br/>
비교할 두 번째 매개 변수입니다.  *rhs는* `HStringReference` 개체 또는 HSTRING 핸들일 수 있습니다.

### <a name="return-value"></a>Return Value

*lhs* 및 *rhs* 매개 변수가 같지 않은 경우 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="hstringreferenceoperatorlt"></a><a name="operator-less-than"></a>HStringReference::연산자&lt;

첫 번째 매개 변수가 두 번째 매개 변수보다 적은지 여부를 나타냅니다.

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 첫 번째 매개 변수입니다. *lhs는* `HStringReference`에 대한 참조일 수 있습니다.

*rhs*<br/>
비교할 두 번째 매개 변수입니다.  *rhs는* 에 대한 `HStringReference`참조가 될 수 있습니다.

### <a name="return-value"></a>Return Value

*lhs* 매개 변수가 *rhs* 매개 변수보다 적으면 **true입니다.** 그렇지 **않으면, 거짓**.
