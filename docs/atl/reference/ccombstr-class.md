---
title: CComBSTR 클래스
ms.date: 11/04/2016
f1_keywords:
- CComBSTR
- ATLBASE/ATL::CComBSTR
- ATLBASE/ATL::CComBSTR::CComBSTR
- ATLBASE/ATL::CComBSTR::Append
- ATLBASE/ATL::CComBSTR::AppendBSTR
- ATLBASE/ATL::CComBSTR::AppendBytes
- ATLBASE/ATL::CComBSTR::ArrayToBSTR
- ATLBASE/ATL::CComBSTR::AssignBSTR
- ATLBASE/ATL::CComBSTR::Attach
- ATLBASE/ATL::CComBSTR::BSTRToArray
- ATLBASE/ATL::CComBSTR::ByteLength
- ATLBASE/ATL::CComBSTR::Copy
- ATLBASE/ATL::CComBSTR::CopyTo
- ATLBASE/ATL::CComBSTR::Detach
- ATLBASE/ATL::CComBSTR::Empty
- ATLBASE/ATL::CComBSTR::Length
- ATLBASE/ATL::CComBSTR::LoadString
- ATLBASE/ATL::CComBSTR::ReadFromStream
- ATLBASE/ATL::CComBSTR::ToLower
- ATLBASE/ATL::CComBSTR::ToUpper
- ATLBASE/ATL::CComBSTR::WriteToStream
- ATLBASE/ATL::CComBSTR::m_str
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
ms.openlocfilehash: c1448a5638b263a87403edf0baca170f0f952e26
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748144"
---
# <a name="ccombstr-class"></a>CComBSTR 클래스

이 클래스는 [BSTR](/previous-versions/windows/desktop/automat/bstr)s의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CComBSTR
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComBSTR:::CComBSTR](#ccombstr)|생성자입니다.|
|[CComBSTR::~CComBSTR](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComBSTR::부속](#append)|에 문자열을 `m_str`더합니다.|
|[CComBSTR::부속BSTR](#appendbstr)|에 BSTR을 `m_str`더합니다.|
|[CComBSTR::부수바이트](#appendbytes)|에 지정된 바이트 수를 `m_str`더합니다.|
|[CComBSTR::어레이토브STR](#arraytobstr)|safearray에서 각 요소의 첫 번째 문자에서 BSTR을 만들고 `CComBSTR` 개체에 연결합니다.|
|[CComBSTR::할당BSTR](#assignbstr)|에 BSTR을 `m_str`할당합니다.|
|[CComBSTR::연결](#attach)|개체에 BSTR을 `CComBSTR` 연결합니다.|
|[CComBSTR::BSTRToArray](#bstrtoarray)|배열의 각 요소가 `CComBSTR` 개체의 문자인 0기반 1차원 safearray를 만듭니다.|
|[CComBSTR::바이트 길이](#bytelength)|바이트의 `m_str` 길이를 반환합니다.|
|[CComBSTR::복사](#copy)|의 복사본을 `m_str`반환합니다.|
|[CComBSTR::복사](#copyto)|[out] `m_str` 매개 변수를 통해 복사본을 **반환합니다.**|
|[CComBSTR::D에타치](#detach)|개체에서 `m_str` 분리합니다. `CComBSTR`|
|[CComBSTR::비어 있음](#empty)|무료 `m_str`.|
|[CComBSTR ::길이](#length)|의 길이를 `m_str`반환합니다.|
|[CComBSTR::로드스트링](#loadstring)|문자열 리소스를 로드합니다.|
|[CComBSTR::읽기스트림](#readfromstream)|스트림에서 BSTR 개체를 로드합니다.|
|[CComBSTR::더 낮은](#tolower)|문자열을 소문자로 변환합니다.|
|[CComBSTR::토어](#toupper)|문자열을 대문자로 변환합니다.|
|[CComBSTR::쓰기토스트림](#writetostream)|스트림에 `m_str` 저장합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CComBSTR::연산자 BSTR](#operator_bstr)|BSTR에 `CComBSTR` 오브젝트를 투사합니다.|
|[CComBSTR ::연산자!](#operator_not)|NULL인지 여부에 `m_str`따라 TRUE 또는 FALSE를 반환합니다.|
|[CComBSTR::연산자 !=](#operator_neq)|문자열과 `CComBSTR` 비교합니다.|
|[CComBSTR::연산자 &](#operator_amp)|의 주소를 `m_str`반환합니다.|
|[CComBSTR::연산자 +=](#operator_add_eq)|개체에 `CComBSTR` a를 더합니다.|
|[CComBSTR::연산자 <](#operator_lt)|문자열과 `CComBSTR` 비교합니다.|
|[CComBSTR::연산자 =](#operator_eq)|에 값을 할당합니다. `m_str`|
|[CComBSTR::연산자 ==](#operator_eq_eq)|문자열과 `CComBSTR` 비교합니다.|
|[CComBSTR::연산자 >](#operator_gt)|문자열과 `CComBSTR` 비교합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComBSTR::m_str](#m_str)|개체와 연결된 BSTR을 포함합니다. `CComBSTR`|

## <a name="remarks"></a>설명

클래스는 `CComBSTR` 길이 접두사 문자열인 BSTR의 래퍼입니다. 길이는 문자열의 데이터 앞에 있는 메모리 위치에 정수로 저장됩니다.

[BSTR은](/previous-versions/windows/desktop/automat/bstr) 마지막 카운트된 문자 이후에 null-terminated되지만 문자열 내에 포함된 null 문자도 포함될 수 있습니다. 문자열 길이는 첫 번째 null 문자가 아닌 문자 수에 의해 결정됩니다.

> [!NOTE]
> 클래스는 `CComBSTR` ANSI 또는 유니코드 문자열을 인수로 하는 여러 멤버(생성자, 할당 연산자 및 비교 연산자)를 제공합니다. 이러한 함수의 ANSI 버전은 임시 유니코드 문자열이 내부적으로 생성되는 경우가 많기 때문에 유니코드 함수보다 효율이 낮습니다. 효율성을 위해 가능한 경우 유니코드 버전을 사용하십시오.

> [!NOTE]
> Visual Studio .NET에서 구현된 향상된 조회 동작으로 `bstr = L"String2" + bstr;`인해 이전 릴리스에서 컴파일했을 수 있는 `bstr = CStringW(L"String2") + bstr`와 같은 코드는 로 구현되어야 합니다.

사용 `CComBSTR`시 주의 사항 목록은 [CComBSTR을 사용한 프로그래밍을](../../atl/programming-with-ccombstr-atl.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccombstrappend"></a><a name="append"></a>CComBSTR::부속

m_str 위해 *bstrSrc의* *lpsz* 또는 BSTR [멤버를](#m_str)부화합니다.

```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```

### <a name="parameters"></a>매개 변수

*블스트셔 (동음이의)*<br/>
【인】 부속할 `CComBSTR` 개체입니다.

*채널*<br/>
【인】 부속할 문자입니다.

*lpsz*<br/>
【인】 영하로 종료된 문자 문자열을 더할 수 있습니다. LPCSTR 버전을 통해 LPCOLESTR 오버로드 또는 ANSI 문자열을 통해 유니코드 문자열을 전달할 수 있습니다.

*nLen*<br/>
【인】 *lpsz에서* 부속할 문자 수입니다.

### <a name="return-value"></a>Return Value

성공 또는 표준 HRESULT 오류 값에 대한 S_OK.

### <a name="remarks"></a>설명

ANSI 문자열이 추가되기 전에 유니코드로 변환됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

## <a name="ccombstrappendbstr"></a><a name="appendbstr"></a>CComBSTR::부속BSTR

지정된 BSTR을 m_str. [m_str](#m_str)

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
【인】 부속할 BSTR입니다.

### <a name="return-value"></a>Return Value

성공 또는 표준 HRESULT 오류 값에 대한 S_OK.

### <a name="remarks"></a>설명

일반 와이드 문자 문자열을 이 메서드에 전달하지 마십시오. 컴파일러는 오류를 catch할 수 없으며 런타임 오류가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

## <a name="ccombstrappendbytes"></a><a name="appendbytes"></a>CComBSTR::부수바이트

변환하지 않고 지정된 바이트 수를 [m_str](#m_str) 추가합니다.

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>매개 변수

*lpsz*<br/>
【인】 추가할 바이트 배열에 대한 포인터입니다.

*P*<br/>
【인】 부속할 바이트 수입니다.

### <a name="return-value"></a>Return Value

성공 또는 표준 HRESULT 오류 값에 대한 S_OK.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

## <a name="ccombstrarraytobstr"></a><a name="arraytobstr"></a>CComBSTR::어레이토브STR

개체에 보유된 기존 `CComBSTR` 문자열을 해제한 다음 safearray의 각 요소의 첫 번째 문자에서 `CComBSTR` BSTR을 만들고 개체에 연결합니다.

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>매개 변수

*pSrc*<br/>
【인】 문자열을 만드는 데 사용되는 요소를 포함하는 안전 배열입니다.

### <a name="return-value"></a>Return Value

성공 또는 표준 HRESULT 오류 값에 대한 S_OK.

## <a name="ccombstrassignbstr"></a><a name="assignbstr"></a>CComBSTR::할당BSTR

[m_str](#m_str)위해 BSTR을 할당합니다.

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>매개 변수

*블스트셔 (동음이의)*<br/>
【인】 현재 `CComBSTR` 개체에 할당할 BSTR입니다.

### <a name="return-value"></a>Return Value

성공 또는 표준 HRESULT 오류 값에 대한 S_OK.

## <a name="ccombstrattach"></a><a name="attach"></a>CComBSTR::연결

*src에* [m_str](#m_str) 멤버를 설정 하 여 `CComBSTR` 개체에 BSTR을 연결 합니다.

```cpp
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>매개 변수

*src*<br/>
【인】 개체에 연결할 BSTR입니다.

### <a name="remarks"></a>설명

일반 와이드 문자 문자열을 이 메서드에 전달하지 마십시오. 컴파일러는 오류를 catch할 수 없으며 런타임 오류가 발생합니다.

> [!NOTE]
> 이 메서드는 `m_str` NULL이 아닌 경우 어설션합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

## <a name="ccombstrbstrtoarray"></a><a name="bstrtoarray"></a>CComBSTR::BSTRToArray

배열의 각 요소가 `CComBSTR` 개체의 문자인 0기반 1차원 safearray를 만듭니다.

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>매개 변수

*ppArray*<br/>
【아웃】 함수의 결과를 유지하는 데 사용되는 안전 배열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 또는 표준 HRESULT 오류 값에 대한 S_OK.

## <a name="ccombstrbytelength"></a><a name="bytelength"></a>CComBSTR::바이트 길이

종료 null 문자를 제외한 `m_str`바이트 수를 반환합니다.

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>Return Value

[m_str](#m_str) 멤버의 길이입니다.

### <a name="remarks"></a>설명

NULL인 `m_str` 경우 0을 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

## <a name="ccombstrccombstr"></a><a name="ccombstr"></a>CComBSTR:::CComBSTR

생성자입니다. 기본 생성자는 [m_str](#m_str) 멤버를 NULL로 설정합니다.

```
CComBSTR() throw();
CComBSTR(const CComBSTR& src);
CComBSTR(REFGUID  guid);
CComBSTR(int nSize);
CComBSTR(int nSize, LPCOLESTR sz);
CComBSTR(int nSize, LPCSTR sz);
CComBSTR(LPCOLESTR pSrc);
CComBSTR(LPCSTR pSrc);
CComBSTR(CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="parameters"></a>매개 변수

*nSize*<br/>
【인】 *sz에서* 복사할 문자 수 또는 에 대한 `CComBSTR`문자의 초기 크기입니다.

*Sz*<br/>
[in] 복사할 문자열입니다. 유니코드 버전은 LPCOLESTR을 지정합니다. ANSI 버전은 LPCSTR을 지정합니다.

*pSrc*<br/>
[in] 복사할 문자열입니다. 유니코드 버전은 LPCOLESTR을 지정합니다. ANSI 버전은 LPCSTR을 지정합니다.

*src*<br/>
[in] `CComBSTR` 개체입니다.

*guid*<br/>
【인】 구조에 대한 `GUID` 참조입니다.

### <a name="remarks"></a>설명

복사 생성자는 `m_str` *src의*BSTR 멤버의 복사본으로 설정합니다. `REFGUID` 생성자는 GUID를 사용하여 `StringFromGUID2` 문자열로 변환하고 결과를 저장합니다.

다른 생성자는 `m_str`을 지정된 문자열의 복사본으로 설정합니다. *nSize에*대한 값을 전달하면 *nSize* 문자만 복사되고 null 문자종료가 표시됩니다.

`CComBSTR`은 이동 의미 체계를 지원합니다. 이동 생성자(rvalue 참조(`&&`)를 가져오는 생성자)를 사용하면 개체 복사에 대한 오버헤드 없이 인수로 전달한 이전 개체와 동일한 기본 데이터를 사용하는 새 개체를 만들 수 있습니다.

소멸자는 `m_str`에서 가리키는 문자열을 해제합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

## <a name="ccombstrccombstr"></a><a name="dtor"></a>CComBSTR::~CComBSTR

소멸자입니다.

```
~CComBSTR();
```

### <a name="remarks"></a>설명

소멸자는 `m_str`에서 가리키는 문자열을 해제합니다.

## <a name="ccombstrcopy"></a><a name="copy"></a>CComBSTR::복사

`m_str`의 복사본을 할당하고 반환합니다.

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>Return Value

[m_str](#m_str) 멤버의 복사본입니다. NULL인 경우 `m_str` NULL을 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

## <a name="ccombstrcopyto"></a><a name="copyto"></a>CComBSTR::복사

매개 변수를 통해 [m_str](#m_str) 복사본을 할당하고 반환합니다.

```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```

### <a name="parameters"></a>매개 변수

*pbstr*<br/>
【아웃】 이 메서드에 의해 할당된 문자열을 반환하는 BSTR의 주소입니다.

*pvardest*<br/>
【아웃】 이 메서드에 의해 할당된 문자열을 반환하는 VARIANT의 주소입니다.

### <a name="return-value"></a>Return Value

복사본의 성공 또는 실패를 나타내는 표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 메서드를 호출 한 후 *pvarDest가* 가리키는 VARIANT은 VT_BSTR 형식이 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

## <a name="ccombstrdetach"></a><a name="detach"></a>CComBSTR::D에타치

개체에서 [m_str](#m_str) 분리하고 NULL로 설정합니다. `m_str` `CComBSTR`

```
BSTR Detach() throw();
```

### <a name="return-value"></a>Return Value

개체와 연결된 BSTR입니다. `CComBSTR`

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

## <a name="ccombstrempty"></a><a name="empty"></a>CComBSTR::비어 있음

[m_str](#m_str) 멤버를 해제합니다.

```cpp
void Empty() throw();
```

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

## <a name="ccombstrlength"></a><a name="length"></a>CComBSTR ::길이

종료 null 문자를 `m_str`제외한 문자 수를 반환합니다.

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>Return Value

[m_str](#m_str) 멤버의 길이입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

## <a name="ccombstrloadstring"></a><a name="loadstring"></a>CComBSTR::로드스트링

*nID에서* 지정한 문자열 리소스를 로드하고 이 개체에 저장합니다.

```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```

### <a name="parameters"></a>매개 변수

Windows SDK에서 [로드스트링을](/windows/win32/api/winuser/nf-winuser-loadstringw) 참조하십시오.

### <a name="return-value"></a>Return Value

문자열이 성공적으로 로드되면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

### <a name="remarks"></a>설명

첫 번째 함수는 *hInst* 매개 변수를 통해 식별된 모듈에서 리소스를 로드합니다. 두 번째 함수는 이 프로젝트에 사용된 [CComModule-derived](../../atl/reference/ccommodule-class.md)개체와 연결된 리소스 모듈에서 리소스를 로드합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]

## <a name="ccombstrm_str"></a><a name="m_str"></a>CComBSTR::m_str

개체와 연결된 BSTR을 포함합니다. `CComBSTR`

```
BSTR m_str;
```

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

## <a name="ccombstroperator-bstr"></a><a name="operator_bstr"></a>CComBSTR::연산자 BSTR

BSTR에 `CComBSTR` 오브젝트를 투사합니다.

```
operator BSTR() const throw();
```

### <a name="remarks"></a>설명

**BSTR** 매개 `CComBSTR` 변수가 있는 함수에 개체를 전달할 수 있습니다.

### <a name="example"></a>예제

[CComBSTR::m_str](#m_str)에 대한 예제를 참조하십시오.

## <a name="ccombstroperator-"></a><a name="operator_not"></a>CComBSTR ::연산자!

BSTR 문자열이 NULL인지 여부를 확인합니다.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Return Value

[m_str](#m_str) 멤버가 NULL인 경우 TRUE를 반환합니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 연산자는 빈 문자열이 아닌 NULL 값만 확인합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

## <a name="ccombstroperator-"></a><a name="operator_neq"></a>CComBSTR::연산자 !=

[연산자 ==](#operator_eq_eq).

```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```

### <a name="parameters"></a>매개 변수

*블스트셔 (동음이의)*<br/>
[in] `CComBSTR` 개체입니다.

*pszSrc*<br/>
【인】 0-종료된 문자열입니다.

*nNull*<br/>
【인】 NULL이어야 합니다.

### <a name="return-value"></a>Return Value

비교중인 항목이 개체와 같지 않은 `CComBSTR` 경우 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

### <a name="remarks"></a>설명

`CComBSTR`s는 사용자의 기본 로캘의 컨텍스트에서 텍스트로 비교됩니다. 최종 비교 연산자는 포함된 문자열을 NULL과 비교합니다.

## <a name="ccombstroperator-amp"></a><a name="operator_amp"></a>CComBSTR::연산자&amp;

[m_str](#m_str) 멤버에 저장된 BSTR의 주소를 반환합니다.

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>설명

`CComBstr operator &`메모리 누수 식별에 도움이 되는 특별한 어설션이 있습니다. 멤버가 초기화될 `m_str` 때 프로그램이 어설션합니다. 이 어설션은 프로그래머가 `& operator` `m_str` `m_str`을 사용하여 구성원의 첫 번째 할당을 해제하지 않고 멤버에게 새 값을 할당하는 상황을 식별하기 위해 만들어졌습니다. NULL과 같으면 `m_str` 프로그램은 m_str 아직 할당되지 않았다고 가정합니다. 이 경우 프로그램은 어설션하지 않습니다.

이 어설션은 기본적으로 활성화되어 있지 않습니다. 이 어설션을 사용하도록 ATL_CCOMBSTR_ADDRESS_OF_ASSERT 정의합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

## <a name="ccombstroperator-"></a><a name="operator_add_eq"></a>CComBSTR::연산자 +=

개체에 문자열을 `CComBSTR` 더합니다.

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>매개 변수

*블스트셔 (동음이의)*<br/>
【인】 부속할 `CComBSTR` 개체입니다.

*pszSrc*<br/>
【인】 영하 종료 된 문자열을 부호.

### <a name="remarks"></a>설명

`CComBSTR`s는 사용자의 기본 로캘의 컨텍스트에서 텍스트로 비교됩니다. LPCOLESTR 비교는 각 `memcmp` 문자열의 원시 데이터를 사용하여 수행됩니다. LPCSTR 비교는 *pszSrc의* 임시 유니코드 복사본이 만들어지면 동일한 방식으로 수행됩니다. 최종 비교 연산자는 포함된 문자열을 NULL과 비교합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

## <a name="ccombstroperator-lt"></a><a name="operator_lt"></a>CComBSTR::연산자&lt;

문자열과 `CComBSTR` 비교합니다.

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>Return Value

비교중인 항목이 개체보다 적으면 `CComBSTR` TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

### <a name="remarks"></a>설명

비교는 사용자의 기본 로캘을 사용하여 수행됩니다.

## <a name="ccombstroperator-"></a><a name="operator_eq"></a>CComBSTR::연산자 =

[m_str](#m_str) 멤버를 *pSrc* 복사본 또는 *Src의*BSTR 멤버 복사본으로 설정합니다. 이동 할당 연산자는 복사하지 않고 이동합니다. `src`

```
CComBSTR& operator= (const CComBSTR& src);
CComBSTR& operator= (LPCOLESTR pSrc);
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="remarks"></a>설명

*pSrc* 매개 변수는 유니코드 버전에 대한 LPCOLESTR 또는 ANSI 버전의 LPCSTR을 지정합니다.

### <a name="example"></a>예제

[CComBSTR::Copy](#copy)에 대한 예제를 참조하십시오.

## <a name="ccombstroperator-"></a><a name="operator_eq_eq"></a>CComBSTR::연산자 ==

문자열과 `CComBSTR` 비교합니다. `CComBSTR`s는 사용자의 기본 로캘의 컨텍스트에서 텍스트로 비교됩니다.

```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```

### <a name="parameters"></a>매개 변수

*블스트셔 (동음이의)*<br/>
[in] `CComBSTR` 개체입니다.

*pszSrc*<br/>
【인】 0-종료된 문자열입니다.

*nNull*<br/>
【인】 NULL이어야 합니다.

### <a name="return-value"></a>Return Value

비교중인 항목이 개체와 같으면 `CComBSTR` TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

### <a name="remarks"></a>설명

최종 비교 연산자는 포함된 문자열을 NULL과 비교합니다.

## <a name="ccombstroperator-gt"></a><a name="operator_gt"></a>CComBSTR::연산자&gt;

문자열과 `CComBSTR` 비교합니다.

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>Return Value

비교중인 항목이 개체보다 큰 `CComBSTR` 경우 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

### <a name="remarks"></a>설명

비교는 사용자의 기본 로캘을 사용하여 수행됩니다.

## <a name="ccombstrreadfromstream"></a><a name="readfromstream"></a>CComBSTR::읽기스트림

[m_str](#m_str) 멤버를 지정된 스트림에 포함된 BSTR로 설정합니다.

```
HRESULT ReadFromStream(IStream* pStream) throw();
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
【인】 데이터를 포함하는 스트림의 [IStream](/windows/win32/api/objidl/nn-objidl-istream) 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`ReadToStream`현재 위치에서 스트림의 내용을 [WriteToStream](#writetostream)호출에 의해 기록 된 데이터 형식과 호환 되어야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

## <a name="ccombstrtolower"></a><a name="tolower"></a>CComBSTR::더 낮은

포함된 문자열을 소문자로 변환합니다.

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

변환이 수행되는 방법에 대한 자세한 내용은 를 참조하십시오. `CharLowerBuff`

## <a name="ccombstrtoupper"></a><a name="toupper"></a>CComBSTR::토어

포함된 문자열을 대문자로 변환합니다.

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

변환이 수행되는 방법에 대한 자세한 내용은 를 참조하십시오. `CharUpperBuff`

## <a name="ccombstrwritetostream"></a><a name="writetostream"></a>CComBSTR::쓰기토스트림

[m_str](#m_str) 멤버를 스트림에 저장합니다.

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
【인】 스트림의 [IStream](/windows/win32/api/objidl/nn-objidl-istream) 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

[ReadFromStream](#readfromstream) 기능을 사용하여 스트림의 내용에서 BSTR을 다시 만들 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[ATL 및 MFC 문자열 변환 매크로](string-conversion-macros.md)
