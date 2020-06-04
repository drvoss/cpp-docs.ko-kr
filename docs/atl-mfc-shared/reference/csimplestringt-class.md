---
title: C심플스트링T 클래스
ms.date: 10/18/2018
f1_keywords:
- CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::PCXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::PXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::Append
- ATLSIMPSTR/ATL::CSimpleStringT::AppendChar
- ATLSIMPSTR/ATL::CSimpleStringT::CopyChars
- ATLSIMPSTR/ATL::CSimpleStringT::CopyCharsOverlapped
- ATLSIMPSTR/ATL::CSimpleStringT::Empty
- ATLSIMPSTR/ATL::CSimpleStringT::FreeExtra
- ATLSIMPSTR/ATL::CSimpleStringT::GetAllocLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetAt
- ATLSIMPSTR/ATL::CSimpleStringT::GetBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::GetBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetManager
- ATLSIMPSTR/ATL::CSimpleStringT::GetString
- ATLSIMPSTR/ATL::CSimpleStringT::IsEmpty
- ATLSIMPSTR/ATL::CSimpleStringT::LockBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::Preallocate
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::SetAt
- ATLSIMPSTR/ATL::CSimpleStringT::SetManager
- ATLSIMPSTR/ATL::CSimpleStringT::SetString
- ATLSIMPSTR/ATL::CSimpleStringT::StringLength
- ATLSIMPSTR/ATL::CSimpleStringT::Truncate
- ATLSIMPSTR/ATL::CSimpleStringT::UnlockBuffer
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
ms.openlocfilehash: 76d418c4f063d5787209ea72e7c681013eb37801
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747039"
---
# <a name="csimplestringt-class"></a>C심플스트링T 클래스

이 클래스는 `CSimpleStringT` 개체를 나타냅니다.

## <a name="syntax"></a>구문

```
template <typename BaseType>
class CSimpleStringT
```

### <a name="parameters"></a>매개 변수

*BaseType*<br/>
문자열 클래스의 문자 형식입니다. 다음 중 하나일 수 있습니다.

- **char** char(ANSI 문자 문자열의 경우)

- **wchar_t(유니코드** 문자 문자열의 경우).

- TCHAR(ANSI 및 유니코드 문자 문자열 모두).

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[C심플스트링: :PCXSTR](#pcxstr)|상수 문자열에 대한 포인터입니다.|
|[C심플스트링: :PXSTR](#pxstr)|문자열에 대한 포인터입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C심플스트링::C심플스트링T](#ctor)|다양한 `CSimpleStringT` 방법으로 개체를 생성합니다.|
|[C심플스트링: :~C심플스트링T](#dtor)|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C심플스트링: :부속](#append)|기존 `CSimpleStringT` `CSimpleStringT` 개체에 개체를 추가합니다.|
|[C심플스트링T::부속차](#appendchar)|기존 `CSimpleStringT` 개체에 문자를 추가합니다.|
|[C심플스트링T::카피차](#copychars)|문자 또는 문자를 다른 문자열에 복사합니다.|
|[C심플스트링::카피차스오버랩](#copycharsoverlapped)|버퍼가 겹치는 다른 문자열에 문자 또는 문자를 복사합니다.|
|[C심플스트링: :비어 있음](#empty)|문자열의 길이가 0이 도록 강제로 합니다.|
|[C심플스트링T::프리엑스트라](#freeextra)|문자열 개체에 의해 이전에 할당된 추가 메모리를 해제합니다.|
|[C심플스트링: :GetAlloclength](#getalloclength)|개체의 할당된 길이를 `CSimpleStringT` 검색합니다.|
|[C심플스트링: :GetAt](#getat)|지정된 위치에서 문자를 반환합니다.|
|[C심플스트링: ::GetBuffer](#getbuffer)|에서 문자에 대한 포인터를 `CSimpleStringT`반환합니다.|
|[C심플스트링::GetBufferSetlength](#getbuffersetlength)|`CSimpleStringT`에서 문자에 대 한 포인터를 반환 합니다.|
|[C심플스트링: :Getlength](#getlength)|개체의 문자 수를 `CSimpleStringT` 반환합니다.|
|[C심플스트링::겟매니저](#getmanager)|개체의 메모리 관리자를 `CSimpleStringT` 검색합니다.|
|[C심플스트링: :GetString](#getstring)|문자 문자열을 검색합니다.|
|[C심플스트링::비어 있음](#isempty)|개체에 `CSimpleStringT` 문자가 없는지 여부를 테스트합니다.|
|[C심플스트링::잠금 버퍼](#lockbuffer)|참조 계수를 비활성화하고 버퍼의 문자열을 보호합니다.|
|[C심플스트링: :P재할당](#preallocate)|문자 버퍼에 대한 특정 메모리 양을 할당합니다.|
|[C심플스트링T::릴리스버퍼](#releasebuffer)|에서 반환된 버퍼의 `GetBuffer`컨트롤을 해제합니다.|
|[C심플스트링::릴리즈버퍼세트길이](#releasebuffersetlength)|에서 반환된 버퍼의 `GetBuffer`컨트롤을 해제합니다.|
|[C심플스트링::세팅](#setat)|지정된 위치에 문자를 설정합니다.|
|[C심플스트링::세트매니저](#setmanager)|개체의 메모리 관리자를 설정합니다. `CSimpleStringT`|
|[C심플스트링::세트스트링](#setstring)|개체의 문자열을 `CSimpleStringT` 설정합니다.|
|[C심플스트링::문자열길이](#stringlength)|지정된 문자열의 문자 수를 반환합니다.|
|[C심플스트링T::트렁크](#truncate)|문자열을 지정된 길이로 자합니다.|
|[C심플스트링::잠금 해제 버퍼](#unlockbuffer)|참조 계수를 활성화하고 버퍼에서 문자열을 해제합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C심플스트링::연산자 PCXSTR](#operator_pcxstr)|개체에 저장된 문자에 `CSimpleStringT` C 스타일 문자열로 직접 액세스합니다.|
|[CSimpleStringT::operator\[\]](#operator_at)|지정된 위치에서 문자를 반환합니다. `GetAt`|
|[C심플스트링::연산자 +=](#operator_add_eq)|새 문자열을 기존 문자열의 끝에 연결합니다.|
|[C심플스트링T::연산자 =](#operator_eq)|개체에 새 값을 `CSimpleStringT` 할당합니다.|

### <a name="remarks"></a>설명

`CSimpleStringT`은 Visual C++에서 지원하는 다양한 문자열 클래스의 기본 클래스입니다. 문자열 개체의 메모리 관리 및 기본 버퍼 조작에 대 한 최소한의 지원을 제공 합니다. 고급 문자열 개체에 대한 자세한 내용은 [CStringT 클래스를](../../atl-mfc-shared/reference/cstringt-class.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** 아실프스트스트.h

## <a name="csimplestringtappend"></a><a name="append"></a>C심플스트링: :부속

기존 `CSimpleStringT` `CSimpleStringT` 개체에 개체를 추가합니다.

### <a name="syntax"></a>구문

```cpp
void Append(const CSimpleStringT& strSrc);
void Append(PCXSTR pszSrc, int nLength);
void Append(PCXSTR pszSrc);
```

#### <a name="parameters"></a>매개 변수

*strSrc*<br/>
추가할 `CSimpleStringT` 개체입니다.

*pszSrc*<br/>
추가할 문자를 포함하는 문자열에 대한 포인터입니다.

*nLength*<br/>
추가할 문자 수입니다.

### <a name="remarks"></a>설명

기존 `CSimpleStringT` 개체를 다른 `CSimpleStringT` 개체에 추가하려면 이 메서드를 호출합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::Append`의 사용법을 보여줍니다.

```cpp
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

## <a name="csimplestringtappendchar"></a><a name="appendchar"></a>C심플스트링T::부속차

기존 `CSimpleStringT` 개체에 문자를 추가합니다.

### <a name="syntax"></a>구문

```cpp
void AppendChar(XCHAR ch);
```

#### <a name="parameters"></a>매개 변수

*채널*<br/>
추가할 문자

### <a name="remarks"></a>설명

이 함수를 호출하여 지정된 문자를 기존 `CSimpleStringT` 개체의 끝에 추가합니다.

## <a name="csimplestringtcopychars"></a><a name="copychars"></a>C심플스트링T::카피차

캐릭터 또는 문자를 개체에 `CSimpleStringT` 복사합니다.

### <a name="syntax"></a>구문

```
static void CopyChars(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>매개 변수

*pchDest*<br/>
문자 문자열에 대한 포인터입니다.

*pchSrc*<br/>
복사할 문자를 포함하는 문자열에 대한 포인터입니다.

*nChars*<br/>
복사할 *pchSrc* 문자 의 수입니다.

### <a name="remarks"></a>설명

*pchSrc에서 pchDest* 문자열로 *pchDest* 문자를 복사하려면 이 메서드를 호출합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::CopyChars`의 사용법을 보여줍니다.

```cpp
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```

## <a name="csimplestringtcopycharsoverlapped"></a><a name="copycharsoverlapped"></a>C심플스트링::카피차스오버랩

캐릭터 또는 문자를 개체에 `CSimpleStringT` 복사합니다.

### <a name="syntax"></a>구문

```
static void CopyCharsOverlapped(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>매개 변수

*pchDest*<br/>
문자 문자열에 대한 포인터입니다.

*pchSrc*<br/>
복사할 문자를 포함하는 문자열에 대한 포인터입니다.

*nChars*<br/>
복사할 *pchSrc* 문자 의 수입니다.

### <a name="remarks"></a>설명

*pchSrc에서 pchDest* 문자열로 *pchDest* 문자를 복사하려면 이 메서드를 호출합니다. 와 `CopyChars` `CopyCharsOverlapped` 달리 겹칠 수 있는 문자 버퍼에서 복사하는 안전한 메서드를 제공합니다.

### <a name="example"></a>예제

[CSimpleStringT::CopyChars](#copychars)에 대한 `CSimpleStringT::SetString` 예제 또는 소스 코드(atlsimpstr.h에 있음)를 참조하십시오.

## <a name="csimplestringtcsimplestringt"></a><a name="ctor"></a>C심플스트링::C심플스트링T

`CSimpleStringT` 개체를 생성합니다.

### <a name="syntax"></a>구문

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr);
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr);
CSimpleStringT(const CSimpleStringT& strSrc);
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw();
```

#### <a name="parameters"></a>매개 변수

*strSrc*<br/>
이 `CSimpleStringT` `CSimpleStringT` 개체에 복사할 기존 개체입니다.

*pchSrc*<br/>
길이 *nLength의*문자 배열에 대한 포인터, null이 종료되지 않음.

*pszSrc*<br/>
이 `CSimpleStringT` 개체에 복사할 null 종료된 문자열입니다.

*nLength*<br/>
의 문자 `pch`수입니다.

*pStringMgr*<br/>
개체의 메모리 관리자에 `CSimpleStringT` 대한 포인터입니다. 및 메모리 `IAtlStringMgr` 관리에 대한 `CSimpleStringT`자세한 내용은 [메모리 관리 및 CStringT](../memory-management-with-cstringt.md)를 참조하십시오.

### <a name="remarks"></a>설명

새 `CSimpleStringT` 개체를 생성합니다. 생성자는 입력 데이터를 새 할당된 저장소에 복사하므로 메모리 예외가 발생할 수 있습니다.

### <a name="example"></a>예제

다음 예제에서는 ATL `CSimpleStringT::CSimpleStringT` **typedef를** `CSimpleString`사용 하 여 사용 하 여 사용 하 여 보여 줍니다. `CSimpleString`는 클래스 템플릿의 `CSimpleStringT`일반적으로 사용되는 전문 분야입니다.

```cpp
CSimpleString s1(pMgr);
// Empty string
CSimpleString s2(_T("cat"), pMgr);
// From a C string literal

CSimpleString s3(s2);
// Copy constructor
CSimpleString s4(s2 + _T(" ") + s3);

// From a string expression
CSimpleString s5(_T("xxxxxx"), 6, pMgr);
// s5 = "xxxxxx"
```

## <a name="csimplestringtempty"></a><a name="empty"></a>C심플스트링: :비어 있음

이 `CSimpleStringT` 개체를 빈 문자열로 만들고 메모리를 적절하게 해제합니다.

### <a name="syntax"></a>구문

```cpp
void Empty() throw();
```

### <a name="remarks"></a>설명

자세한 내용은 [문자열: CString 예외 정리](../cstring-exception-cleanup.md)를 참조하십시오.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::Empty`의 사용법을 보여줍니다.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtfreeextra"></a><a name="freeextra"></a>C심플스트링T::프리엑스트라

문자열에 의해 이전에 할당되었지만 더 이상 필요하지 않은 추가 메모리를 해제합니다.

### <a name="syntax"></a>구문

```cpp
void FreeExtra();
```

### <a name="remarks"></a>설명

이렇게 하면 문자열 개체에서 사용하는 메모리 오버헤드가 줄어듭니다. 메서드는 [버퍼를 GetLength에서](#getlength)반환하는 정확한 길이로 재할당합니다.

### <a name="example"></a>예제

```cpp
CAtlString basestr;
IAtlStringMgr* pMgr;

pMgr= basestr.GetManager();
ASSERT(pMgr != NULL);

// Create a CSimpleString with 28 characters
CSimpleString str(_T("Many sports are fun to play."), 28, pMgr);
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// Assigning a smaller string won't cause CSimpleString to free its
// memory, because it assumes the string will grow again anyway.
str = _T("Soccer is best!");
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// This call forces CSimpleString to release the extra
// memory it doesn't need.
str.FreeExtra();
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());
```

### <a name="remarks"></a>설명

이 예제의 출력은 다음과 같습니다.

```Output
Alloc length is 1031, String length is 1024
Alloc length is 1031, String length is 15
Alloc length is 15, String length is 15
```

## <a name="csimplestringtgetalloclength"></a><a name="getalloclength"></a>C심플스트링: :GetAlloclength

개체의 할당된 길이를 `CSimpleStringT` 검색합니다.

### <a name="syntax"></a>구문

```
int GetAllocLength() const throw();
```

### <a name="return-value"></a>Return Value

이 개체에 할당된 문자 수입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 이 `CSimpleStringT` 개체에 할당된 문자 수를 확인합니다. 이 함수를 호출하는 예제는 [FreeExtra를](#freeextra) 참조하십시오.

## <a name="csimplestringtgetat"></a><a name="getat"></a>C심플스트링: :GetAt

개체에서 한 `CSimpleStringT` 문자를 반환합니다.

### <a name="syntax"></a>구문

```
XCHAR GetAt(int iChar) const;
```

#### <a name="parameters"></a>매개 변수

*아이차 (iChar)*<br/>
개체에 있는 문자의 0 `CSimpleStringT` 기반 인덱스입니다. *iChar* 매개 변수는 0보다 크거나 같아야 하며 [GetLength에서](#getlength)반환하는 값보다 적어야 합니다. 그렇지 `GetAt` 않으면 예외가 생성됩니다.

### <a name="return-value"></a>Return Value

문자열의 지정된 위치에 있는 문자를 포함하는 A입니다. `XCHAR`

### <a name="remarks"></a>설명

*iChar에서*지정한 한 문자를 반환하려면 이 메서드를 호출합니다. 오버로드된 하위**스크립트([]**) 연산자는 `GetAt`에 대한 편리한 별칭입니다. null 종단은 을 사용하여 `GetAt`예외를 생성하지 않고 주소를 지정할 수 있습니다. 그러나 에 의해 `GetLength`계산 되지 않습니다 및 반환 된 값은 0입니다.

### <a name="example"></a>예제

다음 예제에서는 을 사용하는 `CSimpleStringT::GetAt`방법을 보여 줍니다.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

## <a name="csimplestringtgetbuffer"></a><a name="getbuffer"></a>C심플스트링: ::GetBuffer

개체에 대한 내부 문자 버퍼에 대한 포인터를 반환합니다. `CSimpleStringT`

### <a name="syntax"></a>구문

```
PXSTR GetBuffer(int nMinBufferLength);
PXSTR GetBuffer();
```

#### <a name="parameters"></a>매개 변수

*n최소버퍼길이*<br/>
문자 버퍼가 보유할 수 있는 최소 문자 수입니다. 이 값에는 null 터미네이터에 대한 공간이 포함되지 않습니다.

*nMinBufferLength가* 현재 버퍼의 길이보다 큰 `GetBuffer` 경우 현재 버퍼를 파괴하고 요청된 크기의 버퍼로 바꾸고 개체 참조 수를 0으로 재설정합니다. 이전에 이 버퍼에서 [LockBuffer를](#lockbuffer) 호출한 경우 버퍼 잠금을 잃게 됩니다.

### <a name="return-value"></a>Return Value

개체의 (null-종료 된) 문자 버퍼에 대 한 `PXSTR` 포인터입니다.

### <a name="remarks"></a>설명

개체의 버퍼 내용을 반환 하려면이 `CSimpleStringT` 메서드를 호출 합니다. 반환된 `PXSTR` 내용은 상수가 아니므로 `CSimpleStringT` 내용을 직접 수정할 수 있습니다.

반환된 `GetBuffer` 포인터를 사용하여 문자열 내용을 변경하는 경우 다른 `CSimpleStringT` 멤버 메서드를 사용하기 전에 [ReleaseBuffer를](#releasebuffer) 호출해야 합니다.

추가 `CSimpleStringT` 작업으로 `GetBuffer` 인해 버퍼가 다시 `ReleaseBuffer` 할당될 수 있으므로 `CSimpleStringT` 호출 후 반환되는 주소가 유효하지 않을 수 있습니다. 의 길이를 변경하지 않으면 버퍼가 다시 할당되지 `CSimpleStringT`않습니다.

개체가 소멸되면 버퍼 메모리가 `CSimpleStringT` 자동으로 해제됩니다.

문자열 길이를 직접 추적하는 경우 null 문자 종료를 더해서는 안 됩니다. 그러나 을 통해 `ReleaseBuffer`버퍼를 해제할 때 최종 문자열 길이를 지정해야 합니다. 종료 null 문자를 더하는 경우 길이에 대해 -1(기본값)을 전달해야 합니다. `ReleaseBuffer`그런 다음 버퍼 길이를 결정합니다.

`GetBuffer` 요청을 충족하기에 메모리가 부족한 경우 이 메서드는 CMemoryException*을 throw합니다.

### <a name="example"></a>예제

```cpp
CSimpleString s(_T("abcd"), pMgr);
LPTSTR pBuffer = s.GetBuffer(10);
int sizeOfBuffer = s.GetAllocLength();

// Directly access CSimpleString buffer
_tcscpy_s(pBuffer, sizeOfBuffer, _T("Hello"));
ASSERT(_tcscmp(s, _T("Hello")) == 0);
s.ReleaseBuffer();
```

## <a name="csimplestringtgetbuffersetlength"></a><a name="getbuffersetlength"></a>C심플스트링::GetBufferSetlength

개체에 대 한 내부 문자 `CSimpleStringT` 버퍼에 대 한 포인터를 반환, 잘리기 또는 *nLength에*지정 된 길이 정확 하 게 일치 하는 데 필요한 경우 길이 증가.

### <a name="syntax"></a>구문

```
PXSTR GetBufferSetLength(int nLength);
```

#### <a name="parameters"></a>매개 변수

*nLength*<br/>
문자 버퍼의 `CSimpleStringT` 정확한 크기입니다.

### <a name="return-value"></a>Return Value

개체의 (null-종료 된) 문자 버퍼에 대 한 `PXSTR` 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 개체의 내부 버퍼의 지정된 길이를 검색합니다. `CSimpleStringT` 반환 `PXSTR` 된 포인터는 **const** 되지 않으므로 `CSimpleStringT` 내용을 직접 수정할 수 있습니다.

[GetBufferSetLength에서](#getbuffersetlength) 반환된 포인터를 사용하여 문자열 내용을 변경하는 `ReleaseBuffer` 경우 다른 `CsimpleStringT` `CSimpleStringT` 메서드를 사용하기 전에 내부 상태를 업데이트하도록 요청합니다.

추가 `CSimpleStringT` 작업으로 `GetBufferSetLength` 인해 버퍼가 다시 `ReleaseBuffer` 할당될 수 있으므로 `CSimpleStringT` 호출 후 반환되는 주소가 유효하지 않을 수 있습니다. 의 길이를 변경하지 않으면 버퍼가 다시 할당되지 `CSimpleStringT`않습니다.

개체가 소멸되면 버퍼 메모리가 `CSimpleStringT` 자동으로 해제됩니다.

문자열 길이를 직접 추적하는 경우 null 문자 종료를 더하지 마십시오. 을 사용하여 `ReleaseBuffer`버퍼를 해제할 때 최종 문자열 길이를 지정해야 합니다. 호출할 `ReleaseBuffer`때 종료 null 문자를 추가했다면 `ReleaseBuffer`길이에 `ReleaseBuffer` 대해 -1(기본값)을 전달하고 버퍼에서 `strlen` 해당 길이를 결정합니다.

참조 계수에 대한 자세한 내용은 다음 문서를 참조하십시오.

- Windows SDK에서 [참조 계수를 통해 개체 수명 관리](/windows/win32/com/managing-object-lifetimes-through-reference-counting)

- Windows SDK에서 [참조 계수를 구현합니다.](/windows/win32/com/implementing-reference-counting)

- Windows SDK에서 [참조 수를 관리하기 위한 규칙입니다.](/windows/win32/com/rules-for-managing-reference-counts)

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::GetBufferSetLength`의 사용법을 보여줍니다.

```cpp
CSimpleString str(pMgr);
LPTSTR pstr = str.GetBufferSetLength(3);
pstr[0] = _T('C');
pstr[1] = _T('u');
pstr[2] = _T('p');

// No need for trailing zero or call to ReleaseBuffer()
// because GetBufferSetLength() set it for us.

str += _T(" soccer is best!");
ASSERT(_tcscmp(str, _T("Cup soccer is best!")) == 0);
```

## <a name="csimplestringtgetlength"></a><a name="getlength"></a>C심플스트링: :Getlength

개체의 문자 수를 `CSimpleStringT` 반환합니다.

### <a name="syntax"></a>구문

```
int GetLength() const throw();
```

### <a name="return-value"></a>Return Value

문자열의 문자 수입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 개체의 문자 수를 반환합니다. 개수에는 null 터미네이터가 포함되지 않습니다.

멀티바이트 문자 집합(MBCS)의 `GetLength` 경우 각 8비트 문자를 계산합니다. 즉, 한 다바이트 문자의 리드 및 트레일 바이트는 2바이트로 계산됩니다. 이 함수를 호출하는 예제는 [FreeExtra를](#freeextra) 참조하십시오.

## <a name="csimplestringtgetmanager"></a><a name="getmanager"></a>C심플스트링::겟매니저

개체의 메모리 관리자를 `CSimpleStringT` 검색합니다.

### <a name="syntax"></a>구문

```
IAtlStringMgr* GetManager() const throw();
```

### <a name="return-value"></a>Return Value

개체에 대한 메모리 관리자에 대한 포인터입니다. `CSimpleStringT`

### <a name="remarks"></a>설명

이 메서드를 호출하여 개체에서 `CSimpleStringT` 사용하는 메모리 관리자를 검색합니다. 메모리 관리자 및 문자열 개체에 대한 자세한 내용은 [메모리 관리 및 CStringT](../memory-management-with-cstringt.md)를 참조하십시오.

## <a name="csimplestringtgetstring"></a><a name="getstring"></a>C심플스트링: :GetString

문자 문자열을 검색합니다.

### <a name="syntax"></a>구문

```
PCXSTR GetString() const throw();
```

### <a name="return-value"></a>Return Value

null 종료 된 문자 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 개체와 `CSimpleStringT` 연결된 문자열을 검색합니다.

> [!NOTE]
> 반환된 `PCXSTR` 포인터는 **const이며** `CSimpleStringT` 내용을 직접 수정할 수 없습니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::GetString`의 사용법을 보여줍니다.

```cpp
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

## <a name="csimplestringtisempty"></a><a name="isempty"></a>C심플스트링::비어 있음

빈 `CSimpleStringT` 조건에 대한 개체를 테스트합니다.

### <a name="syntax"></a>구문

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Return Value

개체의 길이가 0인 경우 TRUE를 `CSimpleStringT` 반환합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드를 호출하여 개체에 빈 문자열이 포함되어 있는지 확인합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::IsEmpty`의 사용법을 보여줍니다.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

## <a name="csimplestringtlockbuffer"></a><a name="lockbuffer"></a>C심플스트링::잠금 버퍼

참조 계수를 비활성화하고 버퍼의 문자열을 보호합니다.

### <a name="syntax"></a>구문

```
PXSTR LockBuffer();
```

### <a name="return-value"></a>Return Value

`CSimpleStringT` 개체 또는 null 종료 된 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 개체의 버퍼를 잠급전고. `CSimpleStringT` 호출하면 `LockBuffer`참조 개수에 대해 -1이 있는 문자열의 복사본을 만듭니다. 참조 개수 값이 -1이면 버퍼의 문자열은 "잠긴" 상태로 간주됩니다. 잠긴 상태에서 문자열은 다음 두 가지 방법으로 보호됩니다.

- 해당 문자열이 잠긴 문자열에 할당된 경우에도 다른 문자열은 잠긴 문자열의 데이터에 대한 참조를 얻을 수 없습니다.

- 잠긴 문자열은 다른 문자열이 잠긴 문자열에 복사된 경우에도 다른 문자열을 참조하지 않습니다.

버퍼에서 문자열을 잠그면 버퍼에 대한 문자열의 단독 보류가 그대로 유지되도록 합니다.

`LockBuffer`완료 된 후 1로 참조 수를 재설정 하는 [UnlockBuffer를](#unlockbuffer) 호출 합니다.

> [!NOTE]
> 잠긴 버퍼에서 [GetBuffer를](#getbuffer) 호출하고 매개 `GetBuffer` `nMinBufferLength` 변수를 현재 버퍼의 길이보다 큰 것으로 설정하면 버퍼 잠금이 손실됩니다. 현재 버퍼를 `GetBuffer` 삭제하고 요청된 크기의 버퍼로 대체하고 참조 수를 0으로 재설정하는 이러한 호출입니다.

참조 계수에 대한 자세한 내용은 다음 문서를 참조하십시오.

- Windows SDK에서 [참조 계수를 통해 개체 수명 관리](/windows/win32/com/managing-object-lifetimes-through-reference-counting)

- Windows SDK에서 [참조 계수 구현](/windows/win32/com/implementing-reference-counting)

- Windows SDK에서 [참조 개수 관리 규칙](/windows/win32/com/rules-for-managing-reference-counts)

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::LockBuffer`의 사용법을 보여줍니다.

```cpp
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```

## <a name="csimplestringtoperator"></a><a name="operator_at"></a>C심플스트링::연산자\[\]

이 함수를 호출하여 문자 배열의 단일 문자에 액세스합니다.

### <a name="syntax"></a>구문

```
XCHAR operator[](int iChar) const;
```

#### <a name="parameters"></a>매개 변수

*아이차 (iChar)*<br/>
문자열에 있는 문자의 0 기반 인덱스입니다.

### <a name="remarks"></a>설명

오버로드된 하위**스크립트([]**) 연산자는 *iChar에서*0기반 인덱스로 지정된 단일 문자를 반환합니다. 이 연산자는 [GetAt](#getat) 멤버 함수를 편리하게 대체할 수 있습니다.

> [!NOTE]
> **[]**) 연산자에서 문자값을 가져올 수는 있지만 `CSimpleStringT` `CSimpleStringT`이 연산자는 에서 문자값을 변경할 수는 없지만.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::operator []`의 사용법을 보여줍니다.

```cpp
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="csimplestringtoperator-"></a><a name="operator_at"></a>C심플스트링::연산자\[\]

이 함수를 호출하여 문자 배열의 단일 문자에 액세스합니다.

### <a name="syntax"></a>구문

```
XCHAR operator[](int iChar) const;
```

### <a name="parameters"></a>매개 변수

*아이차 (iChar)*<br/>
문자열에 있는 문자의 0 기반 인덱스입니다.

### <a name="remarks"></a>설명

오버로드된 하위**스크립트([]**) 연산자는 *iChar에서*0기반 인덱스로 지정된 단일 문자를 반환합니다. 이 연산자는 [GetAt](#getat) 멤버 함수를 편리하게 대체할 수 있습니다.

> [!NOTE]
> **[]**) 연산자에서 문자값을 가져올 수는 있지만 `CSimpleStringT` `CSimpleStringT`이 연산자는 에서 문자값을 변경할 수는 없지만.

## <a name="csimplestringtoperator-"></a><a name="operator_add_eq"></a>C심플스트링::연산자 +=

새 문자열 또는 문자를 기존 문자열의 끝에 조인합니다.

### <a name="syntax"></a>구문

```
CSimpleStringT& operator +=(PCXSTR pszSrc);
CSimpleStringT& operator +=(const CSimpleStringT& strSrc);
template<int t_nSize>
CSimpleStringT& operator+=(const CStaticString< XCHAR, t_nSize >& strSrc);
CSimpleStringT& operator +=(char ch);
CSimpleStringT& operator +=(unsigned char ch);
CSimpleStringT& operator +=(wchar_t ch);
```

#### <a name="parameters"></a>매개 변수

*pszSrc*<br/>
null 종료 된 문자열에 대 한 포인터입니다.

*strSrc*<br/>
기존 `CSimpleStringT` 개체에 대한 포인터입니다.

*채널*<br/>
추가할 문자입니다.

### <a name="remarks"></a>설명

연산자는 다른 `CSimpleStringT` 개체 또는 문자를 수락합니다. 이 `CSimpleStringT` 개체에 추가된 문자에 대해 새 저장소가 할당될 수 있으므로 이 연결 연산자를 사용할 때마다 메모리 예외가 발생할 수 있습니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::operator +=`의 사용법을 보여줍니다.

```cpp
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

## <a name="csimplestringtoperator-"></a><a name="operator_eq"></a>C심플스트링T::연산자 =

개체에 새 값을 `CSimpleStringT` 할당합니다.

### <a name="syntax"></a>구문

```
CSimpleStringT& operator =(PCXSTR pszSrc);
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```

#### <a name="parameters"></a>매개 변수

*pszSrc*<br/>
null 종료 된 문자열에 대 한 포인터입니다.

*strSrc*<br/>
기존 `CSimpleStringT` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

대상 문자열(왼쪽)이 새 데이터를 저장할 수 있을 만큼 이미 큰 경우 새 메모리 할당이 수행되지 않습니다. 새 저장소가 결과 `CSimpleStringT` 개체를 보유하도록 할당되기 때문에 할당 연산자를 사용할 때마다 메모리 예외가 발생할 수 있습니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::operator =`의 사용법을 보여줍니다.

```cpp
CSimpleString s1(pMgr), s2(pMgr);
// Empty CSimpleStringT objects

s1 = _T("cat");
// s1 = "cat"
ASSERT(_tcscmp(s1, _T("cat")) == 0);

s2 = s1;               // s1 and s2 each = "cat"
ASSERT(_tcscmp(s2, _T("cat")) == 0);

s1 = _T("the ") + s1;
// Or expressions
ASSERT(_tcscmp(s1, _T("the cat")) == 0);

s1 = _T("x");
// Or just individual characters
ASSERT(_tcscmp(s1, _T("x")) == 0);
```

## <a name="csimplestringtoperator-pcxstr"></a><a name="operator_pcxstr"></a>C심플스트링::연산자 PCXSTR

개체에 저장된 문자에 `CSimpleStringT` C 스타일 문자열로 직접 액세스합니다.

### <a name="syntax"></a>구문

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Return Value

문자열의 데이터에 대한 문자 포인터입니다.

### <a name="remarks"></a>설명

문자는 복사되지 않습니다. 포인터만 반환됩니다. 이 연산자에 주의하십시오. 문자 포인터를 `CString` 얻은 후 개체를 변경하면 포인터를 무효화하는 메모리재할당이 발생할 수 있습니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::operator PCXSTR`의 사용법을 보여줍니다.

```cpp
// If the prototype of a function is known to the compiler,
// the PCXSTR cast operator may be invoked implicitly.

CSimpleString strSports(L"Soccer is Best!", pMgr);
WCHAR sz[1024];

wcscpy_s(sz, strSports);

// If the prototype isn't known or is a va_arg prototype,
// you must invoke the cast operator explicitly. For example,
// the va_arg part of a call to swprintf_s() needs the cast:

swprintf_s(sz, 1024, L"I think that %s!\n", (PCWSTR)strSports);

// While the format parameter is known to be an PCXSTR and
// therefore doesn't need the cast:

swprintf_s(sz, 1024, strSports);

// Note that some situations are ambiguous. This line will
// put the address of the strSports object to stdout:

wcout << strSports;

// while this line will put the content of the string out:

wcout << (PCWSTR)strSports;
```

## <a name="csimplestringtpcxstr"></a><a name="pcxstr"></a>C심플스트링: :PCXSTR

상수 문자열에 대한 포인터입니다.

### <a name="syntax"></a>구문

```
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;
```

## <a name="csimplestringtpreallocate"></a><a name="preallocate"></a>C심플스트링: :P재할당

개체에 대해 특정 바이트 양을 `CSimpleStringT` 할당합니다.

### <a name="syntax"></a>구문

```cpp
void Preallocate( int nLength);
```

#### <a name="parameters"></a>매개 변수

*nLength*<br/>
문자 버퍼의 `CSimpleStringT` 정확한 크기입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 개체에 대한 `CSimpleStringT` 특정 버퍼 크기를 할당합니다.

`CSimpleStringT`은 문자 버퍼에 대한 공간을 할당할 수 없는 경우 STATUS_NO_MEMORY 예외를 생성합니다. 기본적으로 메모리 할당은 WIN32 API 함수 `HeapAlloc` `HeapReAlloc`또는 에 의해 수행됩니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::Preallocate`의 사용법을 보여줍니다.

```cpp
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```

## <a name="csimplestringtpxstr"></a><a name="pxstr"></a>C심플스트링: :PXSTR

문자열에 대한 포인터입니다.

### <a name="syntax"></a>구문

```
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;
```

## <a name="csimplestringtreleasebuffer"></a><a name="releasebuffer"></a>C심플스트링T::릴리스버퍼

[GetBuffer](#getbuffer)에 의해 할당된 버퍼의 제어를 해제합니다.

### <a name="syntax"></a>구문

```cpp
void ReleaseBuffer(int nNewLength = -1);
```

#### <a name="parameters"></a>매개 변수

*nNewLength*<br/>
null 터미네이터를 계산하지 않고 문자열의 새 길이입니다. 문자열이 null로 종료된 경우 -1 기본값은 `CSimpleStringT` 크기를 문자열의 현재 길이로 설정합니다.

### <a name="remarks"></a>설명

문자열 개체의 버퍼를 다시 할당하거나 해제하려면 이 메서드를 호출합니다. 버퍼의 문자열이 null로 종료되었다는 것을 알고 있는 경우 *nNewLength* 인수를 생략할 수 있습니다. 문자열이 null이 종료되지 않은 경우 *nNewLength를* 사용하여 길이를 지정합니다. [GetBuffer에서](#getbuffer) 반환하는 주소는 호출 `ReleaseBuffer` 또는 다른 `CSimpleStringT` 작업 이후에 유효하지 않습니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::ReleaseBuffer`의 사용법을 보여줍니다.

```cpp
const int bufferSize = 1024;
CSimpleString s(_T("abc"), pMgr);
LPTSTR p = s.GetBuffer(bufferSize);
_tcscpy_s(p, bufferSize, _T("abc"));

// use the buffer directly
ASSERT(s.GetLength() == 3);

// String length = 3
s.ReleaseBuffer();

// Surplus memory released, p is now invalid.
ASSERT(s.GetLength() == 3);

// Length still 3
```

## <a name="csimplestringtreleasebuffersetlength"></a><a name="releasebuffersetlength"></a>C심플스트링::릴리즈버퍼세트길이

[GetBuffer](#getbuffer)에 의해 할당된 버퍼의 제어를 해제합니다.

### <a name="syntax"></a>구문

```cpp
void ReleaseBufferSetLength(int nNewLength);
```

#### <a name="parameters"></a>매개 변수

*nNewLength*<br/>
릴리즈되는 문자열의 길이

### <a name="remarks"></a>설명

이 함수는 문자열 개체에 대한 유효한 길이를 전달해야 한다는 점을 제외하면 [ReleaseBuffer와](#releasebuffer) 기능적으로 유사합니다.

## <a name="csimplestringtsetat"></a><a name="setat"></a>C심플스트링::세팅

개체에서 단일 문자를 `CSimpleStringT` 설정합니다.

### <a name="syntax"></a>구문

```cpp
void SetAt(int iChar, XCHAR ch);
```

#### <a name="parameters"></a>매개 변수

*아이차 (iChar)*<br/>
개체에 있는 문자의 0 `CSimpleStringT` 기반 인덱스입니다. *iChar* 매개 변수는 0보다 크거나 같아야 하며 [GetLength에서](#getlength)반환하는 값보다 적어야 합니다.

*채널*<br/>
새 문자입니다.

### <a name="remarks"></a>설명

*iChar에*있는 문자를 덮어쓰려면 이 메서드를 호출합니다. *iChar가* 기존 문자열의 경계를 초과하면 이 메서드는 문자열을 확대하지 않습니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::SetAt`의 사용법을 보여줍니다.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

## <a name="csimplestringtsetmanager"></a><a name="setmanager"></a>C심플스트링::세트매니저

개체의 메모리 관리자를 `CSimpleStringT` 지정합니다.

### <a name="syntax"></a>구문

```cpp
void SetManager(IAtlStringMgr* pStringMgr);
```

#### <a name="parameters"></a>매개 변수

*pStringMgr*<br/>
새 메모리 관리자에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 개체에서 사용하는 `CSimpleStringT` 새 메모리 관리자를 지정합니다. 메모리 관리자 및 문자열 개체에 대한 자세한 내용은 [메모리 관리 및 CStringT](../memory-management-with-cstringt.md)를 참조하십시오.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::SetManager`의 사용법을 보여줍니다.

```cpp
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

## <a name="csimplestringtsetstring"></a><a name="setstring"></a>C심플스트링::세트스트링

개체의 문자열을 `CSimpleStringT` 설정합니다.

### <a name="syntax"></a>구문

```cpp
void SetString(PCXSTR pszSrc, int nLength);
void SetString(PCXSTR pszSrc);
```

#### <a name="parameters"></a>매개 변수

*pszSrc*<br/>
null 종료 된 문자열에 대 한 포인터입니다.

*nLength*<br/>
*pszSrc의*문자 수입니다.

### <a name="remarks"></a>설명

문자열을 개체에 `CSimpleStringT` 복사합니다. `SetString`버퍼의 이전 문자열 데이터를 덮어씁니다.

두 버전 `SetString` 모두 *pszSrc가* null 포인터인지 확인하고 E_INVALIDARG 오류를 throw합니다.

하나의 매개 변수 `SetString` 버전의 *pszSrc는* null 종료 된 문자열을 가리킵니다.

또한 두 매개 `SetString` 변수 버전의 *pszSrc는* null 종료 문자열이 될 것으로 예상합니다. null 터미네이터가 먼저 발생하지 않는 한 *nLength를* 문자열 길이로 사용합니다.

또한 두 매개 `SetString` 변수 버전의 *pszSrc가* 의 현재 버퍼의 위치를 가리키는지 여부를 확인합니다. `CSimpleStringT` 이 특별한 경우 `SetString` 문자열 데이터를 버퍼로 다시 복사할 때 문자열 데이터를 덮어쓰지 않는 메모리 복사 함수를 사용합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::SetString`의 사용법을 보여줍니다.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```

## <a name="csimplestringtstringlength"></a><a name="stringlength"></a>C심플스트링::문자열길이

지정된 문자열의 문자 수를 반환합니다.

### <a name="syntax"></a>구문

```
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```

#### <a name="parameters"></a>매개 변수

*psz*<br/>
null 종료 된 문자열에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

*psz의*문자 수; 널 터미네이터를 세지 않습니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 *psz로*가리키는 문자열의 문자 수를 검색합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::StringLength`의 사용법을 보여줍니다.

```cpp
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
```

## <a name="csimplestringttruncate"></a><a name="truncate"></a>C심플스트링T::트렁크

문자열을 새 길이로 자회합니다.

### <a name="syntax"></a>구문

```cpp
void Truncate(int nNewLength);
```

#### <a name="parameters"></a>매개 변수

*nNewLength*<br/>
문자열의 새 길이입니다.

### <a name="remarks"></a>설명

문자열의 내용을 새 길이로 트렁킨하려면 이 메서드를 호출합니다.

> [!NOTE]
> 이는 할당된 버퍼 길이에 영향을 주지 않습니다. 현재 버퍼를 줄이거나 늘리려면 [FreeExtra](#freeextra) 및 [Preallocate](#preallocate)를 참조하십시오.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::Truncate`의 사용법을 보여줍니다.

```cpp
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
```

## <a name="csimplestringtunlockbuffer"></a><a name="unlockbuffer"></a>C심플스트링::잠금 해제 버퍼

개체의 버퍼잠금을 `CSimpleStringT` 해제합니다.

### <a name="syntax"></a>구문

```cpp
void UnlockBuffer() throw();
```

### <a name="remarks"></a>설명

문자열의 참조 수를 1로 재설정하려면 이 메서드를 호출합니다.

`CSimpleStringT` 소멸자가 호출될 때 `UnlockBuffer` 버퍼가 잠기지 않도록 하기 위해 소멸자가 자동으로 호출됩니다. 이 방법의 예는 [LockBuffer](#lockbuffer)를 참조하십시오.

## <a name="csimplestringtcsimplestringt"></a><a name="dtor"></a>C심플스트링: :~C심플스트링T

`CSimpleStringT` 개체를 제거합니다.

### <a name="syntax"></a>구문

```
~CSimpleStringT() throw();
```

### <a name="remarks"></a>설명

이 메서드를 호출하여 개체를 삭제합니다. `CSimpleStringT`

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
