---
title: CStringT 클래스
ms.date: 03/27/2019
f1_keywords:
- CStringT
- ATLSTR/ATL::CStringT
- ATLSTR/ATL::CStringT::CStringT
- ATLSTR/ATL::CStringT::AllocSysString
- ATLSTR/ATL::CStringT::AnsiToOem
- ATLSTR/ATL::CStringT::AppendFormat
- ATLSTR/ATL::CStringT::Collate
- ATLSTR/ATL::CStringT::CollateNoCase
- ATLSTR/ATL::CStringT::Compare
- ATLSTR/ATL::CStringT::CompareNoCase
- ATLSTR/ATL::CStringT::Delete
- ATLSTR/ATL::CStringT::Find
- ATLSTR/ATL::CStringT::FindOneOf
- ATLSTR/ATL::CStringT::Format
- ATLSTR/ATL::CStringT::FormatMessage
- ATLSTR/ATL::CStringT::FormatMessageV
- ATLSTR/ATL::CStringT::FormatV
- ATLSTR/ATL::CStringT::GetEnvironmentVariable
- ATLSTR/ATL::CStringT::Insert
- ATLSTR/ATL::CStringT::Left
- ATLSTR/ATL::CStringT::LoadString
- ATLSTR/ATL::CStringT::MakeLower
- ATLSTR/ATL::CStringT::MakeReverse
- ATLSTR/ATL::CStringT::MakeUpper
- ATLSTR/ATL::CStringT::Mid
- ATLSTR/ATL::CStringT::OemToAnsi
- ATLSTR/ATL::CStringT::Remove
- ATLSTR/ATL::CStringT::Replace
- ATLSTR/ATL::CStringT::ReverseFind
- ATLSTR/ATL::CStringT::Right
- ATLSTR/ATL::CStringT::SetSysString
- ATLSTR/ATL::CStringT::SpanExcluding
- ATLSTR/ATL::CStringT::SpanIncluding
- ATLSTR/ATL::CStringT::Tokenize
- ATLSTR/ATL::CStringT::Trim
- ATLSTR/ATL::CStringT::TrimLeft
- ATLSTR/ATL::CStringT::TrimRight
- CSTRINGT/CStringT
- CSTRINGT/CStringT::CStringT
- CSTRINGT/CStringT::AllocSysString
- CSTRINGT/CStringT::AnsiToOem
- CSTRINGT/CStringT::AppendFormat
- CSTRINGT/CStringT::Collate
- CSTRINGT/CStringT::CollateNoCase
- CSTRINGT/CStringT::Compare
- CSTRINGT/CStringT::CompareNoCase
- CSTRINGT/CStringT::Delete
- CSTRINGT/CStringT::Find
- CSTRINGT/CStringT::FindOneOf
- CSTRINGT/CStringT::Format
- CSTRINGT/CStringT::FormatMessage
- CSTRINGT/CStringT::FormatMessageV
- CSTRINGT/CStringT::FormatV
- CSTRINGT/CStringT::GetEnvironmentVariable
- CSTRINGT/CStringT::Insert
- CSTRINGT/CStringT::Left
- CSTRINGT/CStringT::LoadString
- CSTRINGT/CStringT::MakeLower
- CSTRINGT/CStringT::MakeReverse
- CSTRINGT/CStringT::MakeUpper
- CSTRINGT/CStringT::Mid
- CSTRINGT/CStringT::OemToAnsi
- CSTRINGT/CStringT::Remove
- CSTRINGT/CStringT::Replace
- CSTRINGT/CStringT::ReverseFind
- CSTRINGT/CStringT::Right
- CSTRINGT/CStringT::SetSysString
- CSTRINGT/CStringT::SpanExcluding
- CSTRINGT/CStringT::SpanIncluding
- CSTRINGT/CStringT::Tokenize
- CSTRINGT/CStringT::Trim
- CSTRINGT/CStringT::TrimLeft
- CSTRINGT/CStringT::TrimRight
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
ms.openlocfilehash: 8fcce4c426cd99785d34dc080f238cc78cdfee36
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746704"
---
# <a name="cstringt-class"></a>CStringT 클래스

이 클래스는 `CStringT` 개체를 나타냅니다.

## <a name="syntax"></a>구문

```
template<typename BaseType, class StringTraits>
class CStringT :
    public CSimpleStringT<BaseType,
        _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>::c_bIsMFCDLLTraits>
```

#### <a name="parameters"></a>매개 변수

*BaseType*<br/>
문자열 클래스의 문자 형식입니다. 다음 중 하나일 수 있습니다.

- **char** char(ANSI 문자 문자열의 경우)

- **wchar_t(유니코드** 문자 문자열의 경우).

- TCHAR(ANSI 및 유니코드 문자 문자열 모두).

*StringTraits*<br/>
문자열 클래스에 CRT(런타임) 라이브러리 지원이 필요한지 및 문자열 리소스가 있는 위치를 결정합니다. 다음 중 하나일 수 있습니다.

- **StrTraitATL wchar_t<< &#124;** **차** **&#124;, ChTraitsCRT 는 &#124;** 문자 &#124; char ** > >** &#124; wchar_t wchar_t<<. **char**

   클래스는 CRT 지원이 필요하며 응용 프로그램의 모듈 클래스의 `m_hInstResource` 구성원)이 지정한 모듈의 리소스 문자열을 검색합니다.

- **StrTraitATL< wchar_t** wchar_t &#124; **문자** &#124; **차, ChtraitsOS< wchar_t &#124;** **문자** &#124; **차 > >**

   클래스는 CRT 지원이 필요하지 않으며(응용 프로그램의 모듈 클래스의 `m_hInstResource` 구성원)이 지정한 모듈의 리소스 문자열을 검색합니다.

- **StrTraitMFC** wchar_t< &#124; **char** **&#124; TCHAR, ChTraitsCRT< wchar_t &#124;** &#124; **문자** &#124; &#124; **차 > >**

   클래스는 표준 MFC 검색 알고리즘을 사용하여 CRT 지원과 리소스 문자열을 검색해야 합니다.

- **StrTraitMFC< 는** wchar_t &#124; **char** **&#124; TCHAR, ChtraitsOS< wchar_t &#124;** &#124; **char** &#124; **char tCHAR > >** wchar_t.

   클래스는 표준 MFC 검색 알고리즘을 사용하여 CRT 지원 및 리소스 문자열을 검색할 필요가 없습니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CStringT :: CStringT](#cstringt)|다양한 방법으로 `CStringT` 개체를 구성합니다.|
|[CStringT ::~크스트링T](#_dtorcstringt)|`CStringT` 개체를 제거합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CStringT::AllocSysString](#allocsysstring)|데이터에서 `CStringT` BSTR을 할당합니다.|
|[CStringT::AnsiToOem](#ansitooem)|ANSI 문자 집합에서 OEM 문자 집합으로 내부 변환합니다.|
|[CStringT::부속 형식](#appendformat)|서식이 지정된 데이터를 기존 `CStringT` 개체에 추가합니다.|
|[CStringT::Collate](#collate)|두 문자열을 비교합니다(대/소문자 구분, 로캘 관련 정보 사용).|
|[CStringT::CollateNoCase](#collatenocase)|두 문자열을 비교합니다(대/소문자를 구분하지 않음, 로캘 관련 정보 사용).|
|[CStringT::Compare](#compare)|두 문자열(대/소문자 구분)을 비교합니다.|
|[CStringT::CompareNoCase](#comparenocase)|두 문자열을 비교합니다(대/소문자 구분).|
|[CStringT::D](#delete)|문자열에서 문자 또는 문자를 삭제합니다.|
|[CStringT::Find](#find)|더 큰 문자열 내에서 문자 또는 하위 문자열을 찾습니다.|
|[스트링T ::찾기](#findoneof)|집합에서 첫 번째 일치하는 문자를 찾습니다.|
|[CStringT::형식](#format)|문자열의 서식을 지정합니다. `sprintf`|
|[CStringT::FormatMessage](#formatmessage)|메시지 문자열의 서식을 지정합니다.|
|[CStringT::형식메시지V](#formatmessagev)|변수 인수 목록을 사용하여 메시지 문자열을 서식을 지정합니다.|
|[CStringT::포맷V](#formatv)|변수 인수 목록을 사용하여 문자열의 서식을 지정합니다.|
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|문자열을 지정된 환경 변수의 값으로 설정합니다.|
|[CStringT::Insert](#insert)|문자열 내의 지정된 인덱스에 단일 문자 또는 하위 문자열을 삽입합니다.|
|[CStringT::왼쪽](#left)|문자열의 왼쪽 부분을 추출합니다.|
|[CStringT::LoadString](#loadstring)|Windows 리소스에서 기존 `CStringT` 개체를 로드합니다.|
|[CStringT :: 메이크 로우](#makelower)|이 문자열의 모든 문자를 소문자로 변환합니다.|
|[CStringT::MakeReverse](#makereverse)|문자열을 반전합니다.|
|[CStringT::MakeUpper](#makeupper)|이 문자열의 모든 문자를 대문자 문자로 변환합니다.|
|[CStringT ::중간](#mid)|문자열의 중간 부분을 추출합니다.|
|[CStringT::OemToAnsi](#oemtoansi)|OEM 문자 집합에서 ANSI 문자 집합으로 내부 변환합니다.|
|[CStringT::제거](#remove)|문자열에서 표시된 문자를 제거합니다.|
|[CStringT::Replace](#replace)|표시된 문자를 다른 문자로 바꿉니다.|
|[CStringT::역찾기](#reversefind)|큰 문자열 안에 있는 문자를 찾습니다. 끝에서 시작됩니다.|
|[CStringT::오른쪽](#right)|문자열의 오른쪽 부분을 추출합니다.|
|[CStringT:::세시스트링](#setsysstring)|개체의 데이터로 기존 BSTR `CStringT` 개체를 설정합니다.|
|[CStringT::범위 제외](#spanexcluding)|`pszCharSet`에서 식별된 문자 집합에 없는 첫 번째 문자부터 시작하여 문자열에서 문자를 추출합니다.|
|[CStringT::SpanIncluding](#spanincluding)|집합의 문자만 포함하는 하위 문자열을 추출합니다.|
|[CStringT::토큰화](#tokenize)|대상 문자열에서 지정된 토큰을 추출합니다.|
|[CStringT::Trim](#trim)|문자열에서 모든 선행 및 후행 공백 문자를 트리밍합니다.|
|[CStringT::TrimLeft](#trimleft)|문자열에서 선행 공백 문자를 트리밍합니다.|
|[CStringT::트림라이트](#trimright)|문자열에서 후행 공백 문자를 트리밍합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[CStringT::연산자 =](#operator_eq)|개체에 새 값을 `CStringT` 할당합니다.|
|[CStringT::연산자 +](#operator_add)|두 개의 문자열 또는 문자와 문자열을 연결합니다.|
|[CStringT::연산자 +=](#operator_add_eq)|새 문자열을 기존 문자열의 끝에 연결합니다.|
|[CStringT::연산자 ==](#operator_eq_eq)|두 문자열이 논리적으로 동일한지 확인합니다.|
|[CStringT::연산자 !=](#operator_neq)|두 문자열이 논리적으로 같지 않은지 확인합니다.|
|[CStringT::연산자&lt;](#operator_lt)|연산자의 왼쪽에 있는 문자열이 오른쪽의 문자열보다 적은지 확인합니다.|
|[CStringT::연산자&gt;](#operator_gt)|연산자의 왼쪽에 있는 문자열이 오른쪽의 문자열보다 큰지 확인합니다.|
|[CStringT::연산자&lt;=](#operator_lt_eq)|연산자의 왼쪽에 있는 문자열이 오른쪽의 문자열보다 적거나 같는지 확인합니다.|
|[CStringT::연산자&gt;=](#operator_gt_eq)|연산자의 왼쪽에 있는 문자열이 오른쪽의 문자열보다 크거나 같는지 여부를 결정합니다.|

## <a name="remarks"></a>설명

`CStringT`[CSimpleStringT 클래스에서](../../atl-mfc-shared/reference/csimplestringt-class.md)상속됩니다. 문자 조작, 순서 정렬 및 검색과 같은 고급 `CStringT`기능이 에 의해 구현됩니다.

> [!NOTE]
> `CStringT`개체는 예외를 throw할 수 있습니다. 이 문제는 `CStringT` 어떤 이유로든 개체의 메모리가 부족할 때 발생합니다.

개체는 `CStringT` 가변 길이의 문자 시퀀스로 구성됩니다. `CStringT`에서는 Basic과 유사한 구문을 사용하여 함수와 연산자에게 제공합니다. 연결 및 비교 연산자는 단순화된 메모리 관리와 함께 일반 문자 배열보다 개체를 더 쉽게 사용할 수 있도록 합니다. `CStringT`

> [!NOTE]
> 포함된 null 문자가 `CStringT` 포함된 인스턴스를 만들 수 있지만 이에 대해 권장합니다. 포함된 null 문자가 `CStringT` 포함된 개체에 메서드 및 연산자를 호출하면 의도하지 않은 결과가 생성될 수 있습니다.

`BaseType` 개체는 다른 매개 변수 `StringTraits` 와 `CStringT` 매개 변수의 조합을 사용하여 ATL 라이브러리에 의해 미리 정의된 다음 유형으로 올 수 있습니다.

ATL 응용 프로그램에서 사용하는 경우:

`CString`을 `CStringA`사용하며 `CStringW` MFC DLL(MFC90)에서 내보낼 수 있습니다. DLL), 사용자 DLL에서 결코. 이 방법은 곱하기 정의되지 않도록 `CStringT` 하기 위한 것입니다.

> [!NOTE]
> 코드에 [CStringT를 사용하여 문자열 클래스 내보내기에](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md)설명된 링커 오류에 대한 해결 방법을 포함하는 경우 해당 코드를 제거해야 합니다. 더 이상 필요 없습니다.

다음 문자열 형식은 MFC 기반 응용 프로그램 내에서 사용할 수 있습니다.

|CStringT 유형|선언|
|-------------------|-----------------|
|`CStringA`|CRT가 지원하는 ANSI 문자 유형 문자열입니다.|
|`CStringW`|CRT가 지원하는 유니코드 문자 유형 문자열입니다.|
|`CString`|CRT가 지원하는 ANSI 및 유니코드 문자 유형 모두.|

ATL_CSTRING_NO_CRT 정의된 프로젝트에서 다음 문자열 형식을 사용할 수 있습니다.

|CStringT 유형|선언|
|-------------------|-----------------|
|`CAtlStringA`|CRT 가 지원되지 않는 ANSI 문자 유형 문자열입니다.|
|`CAtlStringW`|CRT가 지원되지 않는 유니코드 문자 유형 문자열입니다.|
|`CAtlString`|CRT가 지원되지 않는 ANSI 및 유니코드 문자 유형 모두.|

ATL_CSTRING_NO_CRT 정의되지 않은 프로젝트에서 다음 문자열 형식을 사용할 수 있습니다.

|CStringT 유형|선언|
|-------------------|-----------------|
|`CAtlStringA`|CRT가 지원하는 ANSI 문자 유형 문자열입니다.|
|`CAtlStringW`|CRT가 지원하는 유니코드 문자 유형 문자열입니다.|
|`CAtlString`|CRT가 지원하는 ANSI 및 유니코드 문자 유형 모두.|

`CString`개체에는 다음과 같은 특성도 있습니다.

- `CStringT`개체는 연결 작업의 결과로 증가할 수 있습니다.

- `CStringT`개체는 "값 의미 체계"를 따릅니다. 개체를 `CStringT` 문자열에 대한 포인터가 아니라 실제 문자열로 간주합니다.

- 함수 인수에 `CStringT` 대한 `PCXSTR` 개체를 자유롭게 대체할 수 있습니다.

- 문자열 버퍼에 대한 사용자 지정 메모리 관리입니다. 자세한 내용은 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)를 참조하십시오.

## <a name="cstringt-predefined-types"></a>CStringT 사전 정의된 형식

템플릿 `CStringT` 인수를 사용하여 지원되는 문자 [유형(wchar_t](../../c-runtime-library/standard-types.md) 또는 [char)을](../../c-runtime-library/standard-types.md)정의하기 때문에 메서드 매개 변수 형식은 때때로 복잡해질 수 있습니다. 이 문제를 단순화하기 위해 미리 정의된 형식 집합이 `CStringT` 정의되어 클래스 전체에서 사용됩니다. 다음 표에는 다양한 유형이 나열되어 있습니다.

|속성|Description|
|----------|-----------------|
|`XCHAR`|개체와 동일한 문자 형식을 가진 단일 문자(wchar_t 또는 **char)입니다.** **wchar_t** `CStringT`|
|`YCHAR`|반대 문자 유형이 `CStringT` 개체로 있는 단일 문자(wchar_t 또는 **char)입니다.** **wchar_t**|
|`PXSTR`|개체와 동일한 문자 형식을 가진 문자 문자열(wchar_t 또는 `CStringT` **char)에**대한 포인터입니다. **wchar_t**|
|`PYSTR`|개체로 반대 문자 형식을 가진 문자 문자열 **(wchar_t** 또는 `CStringT` **char)에**대 한 포인터입니다.|
|`PCXSTR`|개체와 동일한 문자 형식을 가진 **const** 문자 문자열(wchar_t 또는 **char)에**대한 포인터입니다. **wchar_t** `CStringT`|
|`PCYSTR`|반대 문자 형식을 개체로 사용하여 **const** 문자 문자열(wchar_t 또는 `CStringT` **char)에**대한 포인터입니다. **wchar_t**|

> [!NOTE]
> 이전에 문서화되지 않은 `CString` 메서드(예: )를 `AssignCopy`사용한 코드는 다음과 같은 `CStringT` 문서화된 `GetBuffer` `ReleaseBuffer`메서드(예: 또는)를 사용하는 코드로 대체되어야 합니다. 이러한 메서드는 에서 `CSimpleStringT`상속됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>요구 사항

|헤더|용도|
|------------|-------------|
|cstringt.h|MFC 전용 문자열 개체|
|atlstr.h|MFC가 아닌 문자열 개체|

## <a name="cstringtallocsysstring"></a><a name="allocsysstring"></a>CStringT::AllocSysString

BSTR 형식의 자동화 호환 문자열을 할당하고 null 문자 종료를 포함하여 `CStringT` 개체의 내용을 복사합니다.

```
BSTR AllocSysString() const;
```

### <a name="return-value"></a>Return Value

새로 할당된 문자열입니다.

### <a name="remarks"></a>설명

MFC 프로그램에서는 메모리가 부족하면 [CMemoryException 클래스가](../../mfc/reference/cmemoryexception-class.md) throw됩니다. ATL 프로그램에서는 [CAtlException이](../../atl/reference/catlexception-class.md) throw됩니다. 이 함수는 일반적으로 자동화에 대 한 문자열을 반환 하는 데 사용 됩니다.

일반적으로 이 문자열이 COM 함수에 [in] 매개 변수로 전달되면 호출자는 문자열을 해제해야 합니다. 이 작업은 Windows SDK에 설명된 대로 [SysFreeString을](/windows/win32/api/oleauto/nf-oleauto-sysfreestring)사용하여 수행할 수 있습니다. 자세한 내용은 [BSTR에 대한 메모리 할당 및 해제를](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)참조하십시오.

Windows의 OLE 할당 기능에 대한 자세한 내용은 Windows SDK의 [SysAllocString을](/windows/win32/api/oleauto/nf-oleauto-sysallocstring) 참조하십시오.

### <a name="example"></a>예제

다음 예에서는 `CStringT::AllocSysString`의 사용법을 보여줍니다.

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

## <a name="cstringtansitooem"></a><a name="ansitooem"></a>스트링T::안시토오엠

ANSI 문자 집합에서 OEM 문자 집합으로 이 `CStringT` 개체의 모든 문자를 변환합니다.

```cpp
void AnsiToOem();
```

### <a name="remarks"></a>설명

_UNICODE 정의된 경우 이 함수를 사용할 수 없습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

## <a name="cstringtappendformat"></a><a name="appendformat"></a>CStringT::부속 형식

서식이 지정된 데이터를 기존 `CStringT` 개체에 추가합니다.

```cpp
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
형식 제어 문자열입니다.

*nFormatID*<br/>
형식 제어 문자열을 포함하는 문자열 리소스 식별자입니다.

*인수*<br/>
선택적 인수입니다.

### <a name="remarks"></a>설명

이 함수는 에서 일련의 문자와 값을 서식을 지정하고 적용합니다. `CStringT` 각 선택적 인수(있는 경우)는 *pszFormat의* 해당 형식 사양에 따라 변환되고 추가되거나 *nFormatID로*식별된 문자열 리소스에서 추가됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

## <a name="cstringtcollate"></a><a name="collate"></a>CStringT::Collate

제네릭 텍스트 함수를 `_tcscoll`사용하여 두 문자열을 비교합니다.

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
비교에 사용되는 다른 문자열입니다.

### <a name="return-value"></a>Return Value

문자열이 동일한 경우 0, 이 `CStringT` 개체가 psz 보다 크면 0이 <, 이 `CStringT` 개체가 *psz보다*큰 경우 0을 >. *psz*

### <a name="remarks"></a>설명

TCHAR에서 정의된 `_tcscoll`제네릭 텍스트 함수입니다. H, 컴파일 `strcoll`타임에 `_mbscoll`정의된 문자 집합에 따라 에 `wcscoll`매핑됩니다. 각 함수는 현재 사용 중인 코드 페이지에 따라 문자열의 대/소문자를 구분하는 비교를 수행합니다. 자세한 내용은 [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)를 참조하십시오.

## <a name="cstringtcollatenocase"></a><a name="collatenocase"></a>스트링T::콜레이트노케이스

제네릭 텍스트 함수를 `_tcscoll`사용하여 두 문자열을 비교합니다.

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
비교에 사용되는 다른 문자열입니다.

### <a name="return-value"></a>Return Value

문자열이 동일하면(대/소문자 무시), 이 `CStringT` 개체가 psz(대/소문자 무시)보다 `CStringT` < 0이면 0이면, 이 개체가 *psz(대/소문자* 무시)보다 큰 경우 0을 >. *psz*

### <a name="remarks"></a>설명

TCHAR에서 정의된 `_tcscoll`제네릭 텍스트 함수입니다. H, 컴파일 `stricoll`타임에 `_mbsicoll`정의된 문자 집합에 따라 에 `wcsicoll`매핑됩니다. 각 함수는 현재 사용 중인 코드 페이지에 따라 문자열의 대/소문자를 구분하지 않음 비교를 수행합니다. 자세한 내용은 [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

## <a name="cstringtcompare"></a><a name="compare"></a>CStringT::비교

두 문자열(대/소문자 구분)을 비교합니다.

```
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
비교에 사용되는 다른 문자열입니다.

### <a name="return-value"></a>Return Value

문자열이 동일한 경우 0, 이 `CStringT` 개체가 psz 보다 크면 0이 <, 이 `CStringT` 개체가 *psz보다*큰 경우 0을 >. *psz*

### <a name="remarks"></a>설명

TCHAR에서 정의된 `_tcscmp`제네릭 텍스트 함수입니다. H, 컴파일 `strcmp`타임에 `_mbscmp`정의된 문자 집합에 따라 에 `wcscmp`매핑됩니다. 각 함수는 문자열의 대/소문자 구분 비교를 수행하며 로캘의 영향을 받지 않습니다. 자세한 내용은 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)를 참조하십시오.

문자열에 포함된 null이 포함된 경우 비교를 위해 문자열은 첫 번째 포함된 null 문자에서 잘린 것으로 간주됩니다.

### <a name="example"></a>예제

다음 예에서는 `CStringT::Compare`의 사용법을 보여줍니다.

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

## <a name="cstringtcomparenocase"></a><a name="comparenocase"></a>CStringT::비교노케이스

두 문자열을 비교합니다(대/소문자 구분).

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
비교에 사용되는 다른 문자열입니다.

### <a name="return-value"></a>Return Value

문자열이 동일한 경우(대/소문자 무시), `CStringT` 이 개체가 psz(대/소문자 무시)보다 크면 <0, 이 `CStringT` 개체가 *psz(대/소문자* 무시)보다 큰 경우 0을 >. *psz*

### <a name="remarks"></a>설명

TCHAR에서 정의된 `_tcsicmp`제네릭 텍스트 함수입니다. H, 컴파일 `_stricmp`타임에 정의된 문자 집합에 따라 `_wcsicmp` 또는 `_mbsicmp`에 매핑됩니다. 각 함수는 문자열의 대/소문자를 구분하지 않음 비교를 수행합니다. 비교는 로캘의 LC_CTYPE 측면에 따라 달라지지만 LC_COLLATE 않습니다. 자세한 내용은 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

## <a name="cstringtcstringt"></a><a name="cstringt"></a>CStringT :: CStringT

`CStringT` 개체를 생성합니다.

```
CStringT() throw() :
    CThisSimpleString(StringTraits::GetDefaultManager());

explicit CStringT(IAtlStringMgr* pStringMgr) throw() :
    CThisSimpleString( pStringMgr);

CStringT(const VARIANT& varSrc);

CStringT(const VARIANT& varSrc, IAtlStringMgr* pStringMgr);

CStringT(const CStringT& strSrc) :
    CThisSimpleString( strSrc);

operator CSimpleStringT<
                    BaseType,
                    !_CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                    :: c_bIsMFCDLLTraits> &()

template <bool bMFCDLL>
CStringT(const CSimpleStringT<BaseType, bMFCDLL>& strSrc) :
    CThisSimpleString( strSrc);

template <class SystemString>
CStringT(SystemString^ pString) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(const YCHAR* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(LPCSTR pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CStringT(LPCWSTR pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(const unsigned char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

/*CSTRING_EXPLICIT*/ CStringT(char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(unsigned char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const unsigned char* pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(char ch, int nLength = 1) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t ch, int nLength = 1) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength) :
    CThisSimpleString( pch, nLength, StringTraits::GetDefaultManager());

CStringT(const YCHAR* pch, int nLength) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength, AtlStringMgr* pStringMgr) :
    CThisSimpleString( pch, nLength, pStringMgr);

CStringT(const YCHAR* pch, int nLength, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);
```

### <a name="parameters"></a>매개 변수

*Pch*<br/>
null-terminated가 아닌 길이 *nLength의*문자 배열에 대한 포인터입니다.

*nLength*<br/>
*pch의*문자 수입니다.

*채널*<br/>
단일 문자입니다.

*pszSrc*<br/>
이 `CStringT` 개체에 복사할 null 종료된 문자열입니다.

*pStringMgr*<br/>
개체에 대한 메모리 관리자에 대한 포인터입니다. `CStringT` 에 대한 자세한 정보 `CStringT`및 메모리 관리에 대한 자세한 내용은 [CStringT를 사용 하 여 메모리 관리를](../../atl-mfc-shared/memory-management-with-cstringt.md)참조 하십시오. `IAtlStringMgr`

*strSrc*<br/>
이 `CStringT` `CStringT` 개체에 복사할 기존 개체입니다. `CThisString` 자세한 내용은 `CThisSimpleString`비고 섹션을 참조하십시오.

*varSrc*<br/>
이 `CStringT` 개체에 복사할 변형 개체입니다.

*BaseType*<br/>
문자열 클래스의 문자 형식입니다. 다음 중 하나일 수 있습니다.

**char** char(ANSI 문자 문자열의 경우)

**wchar_t(유니코드** 문자 문자열의 경우).

TCHAR(ANSI 및 유니코드 문자 문자열 모두).

*bMFCDLL*<br/>
프로젝트가 MFC DLL(TRUE)인지 여부를 지정하는 부울(FALSE)입니다.

*시스템 스트링*<br/>
`System::String`이어야 하며 프로젝트를 /clr로 컴파일해야 합니다.

*pString*<br/>
개체에 대한 `CStringT` 핸들입니다.

### <a name="remarks"></a>설명

생성자는 입력 데이터를 새 할당된 저장소에 복사하므로 메모리 예외가 발생할 수 있음을 알고 있어야 합니다. 이러한 생성자 중 일부는 변환 함수역할을 합니다. 이를 통해 개체가 예상되는 LPTSTR을 대체할 `CStringT` 수 있습니다.

- `CStringT`( `LPCSTR` `lpsz` ) ANSI `CStringT` 문자열에서 유니코드를 생성합니다. 아래 예제와 같이 이 생성기를 사용하여 문자열 리소스를 로드할 수도 있습니다.

- `CStringT(`): 유니코드 `CStringT` 문자열에서 a를 생성합니다. `LPCWSTR` `lpsz`

- `CStringT`( `const unsigned char*` `psz` ) : 포인터에서 `CStringT` **서명되지 않은 char로**a를 생성 할 수 있습니다.

> [!NOTE]
> ANSI와 유니코드 문자열 간의 암시적 문자열 변환을 해제하도록 _CSTRING_DISABLE_NARROW_WIDE_CONVERSION 매크로를 정의합니다. 매크로는 변환을 지원하는 컴파일 생성자에서 제외됩니다.

*strSrc* 매개 변수는 a `CStringT` 또는 `CThisSimpleString` 개체일 수 있습니다. 에 `CStringT`대 한 기본 인스턴스 중`CString` `CStringA`하나를 `CStringW`사용 하 여 (, 또는); 을 `CThisSimpleString`위해 **이** 포인터를 사용합니다. `CThisSimpleString`[CSimpleStringT 클래스의](../../atl-mfc-shared/reference/csimplestringt-class.md)인스턴스를 선언합니다. `CStringT`

오버로드 연산자는 `CSimpleStringT<>&()` `CStringT` 선언에서 `CSimpleStringT` 개체를 생성합니다.

> [!NOTE]
> 포함된 null 문자가 `CStringT` 포함된 인스턴스를 만들 수 있지만 이에 대해 권장합니다. 포함된 null 문자가 `CStringT` 포함된 개체에 메서드 및 연산자를 호출하면 의도하지 않은 결과가 생성될 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

## <a name="cstringtcstringt"></a><a name="_dtorcstringt"></a>CStringT ::~크스트링T

개체를 `CStringT` 삭제합니다.

```
~CStringT() throw();
```

### <a name="remarks"></a>설명

개체를 `CStringT` 삭제합니다.

## <a name="cstringtdelete"></a><a name="delete"></a>CStringT::D

지정된 인덱스의 문자로 시작하는 문자열에서 문자 또는 문자를 삭제합니다.

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
삭제할 개체의 첫 번째 문자의 0기반 인덱스입니다. `CStringT`

*nCount*<br/>
제거할 문자 수입니다.

### <a name="return-value"></a>Return Value

변경된 문자열의 길이입니다.

### <a name="remarks"></a>설명

*nCount가* 문자열보다 길면 나머지 문자열이 제거됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output
Before: Soccer is best,
    but hockey is quicker!
After: Soccer best,
    but hockey is quicker!
```

## <a name="cstringtfind"></a><a name="find"></a>CStringT :: 찾기

이 문자열에서 문자 또는 하위 문자열의 첫 번째 일치 를 검색합니다.

```
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>매개 변수

*pszSub*<br/>
검색할 하위 문자열입니다.

*iStart*<br/>
검색을 시작할 문자열의 문자 인덱스 또는 0을 처음부터 시작합니다.

*채널*<br/>
검색할 단일 문자입니다.

### <a name="return-value"></a>Return Value

요청된 하위 문자열 또는 문자와 `CStringT` 일치하는 이 개체의 첫 번째 문자의 0-기반 인덱스입니다. -1 하위 문자열 또는 문자를 찾을 수 없는 경우.

### <a name="remarks"></a>설명

함수는 런타임 함수와 `strchr`유사)와 `strstr`문자열(유사)을 모두 허용하도록 오버로드됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

## <a name="cstringtfindoneof"></a><a name="findoneof"></a>스트링T ::찾기

*pszCharSet에*포함된 모든 문자와 일치하는 첫 번째 문자에 대해 이 문자열을 검색합니다.

```
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>매개 변수

*pszCharSet*<br/>
일치를 위한 문자를 포함하는 문자열입니다.

### <a name="return-value"></a>Return Value

*pszCharSet에도*있는 이 문자열의 첫 번째 문자의 0기반 인덱스입니다. -1 일치 하지 않는 경우.

### <a name="remarks"></a>설명

*pszCharSet에서*문자의 첫 번째 발생을 찾습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

## <a name="cstringtformat"></a><a name="format"></a>CStringT::형식

[Sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)가 데이터를 C 스타일 문자 배열로 서식 지정 하는 것과 동일한 방식으로 `CStringT`에 형식이 지정된 데이터를 씁니다.

```cpp
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>매개 변수

*nFormatID*<br/>
형식 제어 문자열을 포함하는 문자열 리소스 식별자입니다.

*pszFormat*<br/>
형식 제어 문자열입니다.

*인수*<br/>
선택적 인수입니다.

### <a name="remarks"></a>설명

이 함수는 `CStringT`일련의 문자와 값을 에 서식을 지정하고 저장합니다. 각 선택적 인수(있는 경우)는 *pszFormat의* 해당 형식 사양에 따라 변환되고 출력되거나 *nFormatID로*식별된 문자열 리소스에서 출력됩니다.

문자열 개체 자체가 에 대한 매개 변수로 `Format`제공되면 호출이 실패합니다. 예를 들어 다음 코드로 인해 예기치 않은 결과가 발생합니다.

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

자세한 내용은 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

## <a name="cstringtformatmessage"></a><a name="formatmessage"></a>CStringT::형식 메시지

메시지 문자열의 서식을 지정합니다.

```cpp
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>매개 변수

*nFormatID*<br/>
형식이 지정되지 않은 메시지 텍스트를 포함하는 문자열 리소스 식별자입니다.

*pszFormat*<br/>
형식 제어 문자열을 가리킵니다. 삽입을 위해 스캔하고 그에 따라 포맷합니다. 형식 문자열은 매개 변수를 임의의 순서로 삽입할 수 있는 경우를 제외하고 런타임 함수 *printf-style*형식 문자열과 유사합니다.

*인수*<br/>
선택적 인수입니다.

### <a name="remarks"></a>설명

함수에는 입력으로 메시지 정의가 필요합니다. 메시지 정의는 *pszFormat* 또는 *nFormatID로*식별된 문자열 리소스에서 결정됩니다. 이 함수는 서식이 지정된 메시지 `CStringT` 텍스트를 개체에 복사하여 요청시 포함된 삽입 시퀀스를 처리합니다.

> [!NOTE]
> `FormatMessage`을 시도하여 새로 서식이 지정된 문자열에 대한 시스템 메모리 할당을 시도합니다. 이 시도가 실패하면 메모리 예외가 자동으로 throw됩니다.

각 삽입에는 *pszFormat* 또는 *nFormatID* 매개 변수 다음에 해당하는 매개 변수가 있어야 합니다. 메시지 텍스트 내에서 메시지를 동적으로 서식 지정하기 위해 여러 이스케이프 시퀀스가 지원됩니다. 자세한 내용은 Windows SDK의 Windows [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) 기능을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

## <a name="cstringtformatmessagev"></a><a name="formatmessagev"></a>CStringT::형식메시지V

변수 인수 목록을 사용하여 메시지 문자열을 서식을 지정합니다.

```cpp
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
형식 제어 문자열을 가리킵니다. 삽입을 위해 스캔하고 그에 따라 포맷합니다. 형식 문자열은 매개 변수를 `printf`임의의 순서로 삽입할 수 있는 경우를 제외하고 런타임 함수 -style 형식 문자열과 유사합니다.

*pArgList*<br/>
인수 목록에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 *pszFormat에*의해 결정된 입력으로 메시지 정의가 필요합니다. 이 함수는 서식이 지정된 메시지 텍스트와 개체에 `CStringT` 대한 인수의 변수 목록을 복사하여 요청시 포함된 삽입 시퀀스를 처리합니다.

> [!NOTE]
> `FormatMessageV`[CStringT::FormatMessage를](#formatmessage)호출합니다. 이 시도가 실패하면 메모리 예외가 자동으로 throw됩니다.

자세한 내용은 Windows SDK의 Windows [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) 기능을 참조하십시오.

## <a name="cstringtformatv"></a><a name="formatv"></a>CStringT::포맷V

변수 인수 목록을 사용하여 메시지 문자열을 서식을 지정합니다.

```cpp
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
형식 제어 문자열을 가리킵니다. 삽입을 위해 스캔하고 그에 따라 포맷합니다. 형식 문자열은 매개 변수를 `printf`임의의 순서로 삽입할 수 있는 경우를 제외하고 런타임 함수 -style 형식 문자열과 유사합니다.

*Args*<br/>
인수 목록에 대한 포인터입니다.

### <a name="remarks"></a>설명

C 스타일 문자 배열에 데이터를 서식을 `CStringT` 지정하는 `vsprintf_s` 것과 같은 방식으로 형식이 지정된 문자열과 변수 인수 목록을 문자열에 씁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

## <a name="cstringtgetenvironmentvariable"></a><a name="getenvironmentvariable"></a>CStringT::Get환경변수

문자열을 지정된 환경 변수의 값으로 설정합니다.

```
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>매개 변수

*pszVar*<br/>
환경 변수를 지정하는 null 종료 된 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출 프로세스의 환경 블록에서 지정된 변수의 값을 검색합니다. 값은 null-종료된 문자 문자열의 형태입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

## <a name="cstringtinsert"></a><a name="insert"></a>CStringT:::삽입

문자열 내의 지정된 인덱스에 단일 문자 또는 하위 문자열을 삽입합니다.

```
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
삽입이 수행되기 전에 문자의 인덱스입니다.

*psz*<br/>
삽입할 하위 문자열에 대한 포인터입니다.

*채널*<br/>
삽입할 문자입니다.

### <a name="return-value"></a>Return Value

변경된 문자열의 길이입니다.

### <a name="remarks"></a>설명

*iIndex* 매개 변수는 문자 또는 하위 문자열에 대 한 공간을 만들기 위해 이동 될 첫 번째 문자를 식별 합니다. *nIndex가* 0이면 전체 문자열 앞에 삽입이 발생합니다. *nIndex가* 문자열의 길이보다 높으면 함수는 현재 문자열과 *ch* 또는 *psz에서*제공하는 새 재질을 연결합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

## <a name="cstringtleft"></a><a name="left"></a>CStringT::왼쪽

이 `CStringT` 개체에서 가장 왼쪽에 *있는 nCount* 문자를 추출 하 고 추출 된 하위 문자열의 복사본을 반환 합니다.

```
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>매개 변수

*nCount*<br/>
이 `CStringT` 개체에서 추출할 문자의 수입니다.

### <a name="return-value"></a>Return Value

지정된 문자 범위의 복사본을 포함하는 `CStringT` 개체입니다. 반환된 `CStringT` 개체가 비어 있을 수 있습니다.

### <a name="remarks"></a>설명

*nCount가* 문자열 길이를 초과하면 전체 문자열이 추출됩니다. `Left`는 기본 `Left` 함수와 유사합니다.

MBCS(다중 바이트 문자 집합)의 경우 *nCount는* 각 8비트 시퀀스를 문자로 처리하므로 *nCount는* 다중 바이트 문자 수를 2배로 곱합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

## <a name="cstringtloadstring"></a><a name="loadstring"></a>CStringT ::로드 스트링

*nID로*식별된 Windows 문자열 리소스를 `CStringT` 기존 개체로 읽습니다.

```
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
모듈의 인스턴스에 대한 핸들입니다.

*nID*<br/>
Windows 문자열 리소스 ID입니다.

*wLanguageID*<br/>
문자열 리소스의 언어입니다.

### <a name="return-value"></a>Return Value

리소스 로드가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

지정된 언어 *(wLanguage)를*사용하여 지정된 모듈 *(hInstance)에서*문자열 리소스 *(nID)를*로드합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

## <a name="cstringtmakelower"></a><a name="makelower"></a>CStringT :: 메이크 로우

개체를 `CStringT` 소문자 문자열로 변환합니다.

```
CStringT& MakeLower();
```

### <a name="return-value"></a>Return Value

결과 소문자 문자열입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

## <a name="cstringtmakereverse"></a><a name="makereverse"></a>CStringT::메이크 리버스

개체의 문자 순서를 반대로 `CStringT` 합니다.

```
CStringT& MakeReverse();
```

### <a name="return-value"></a>Return Value

결과 반전 된 문자열입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

## <a name="cstringtmakeupper"></a><a name="makeupper"></a>CStringT :: 메이크 어퍼

개체를 `CStringT` 대문자 문자열로 변환합니다.

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>Return Value

결과 대문자 문자열입니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

## <a name="cstringtmid"></a><a name="mid"></a>CStringT ::중간

위치 *iFirst(0* 기반)에서 시작하여 `CStringT` 이 개체에서 길이 *nCount* 문자의 하위 문자열을 추출합니다.

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>매개 변수

*iFirst*<br/>
추출된 하위 문자열에 포함할 `CStringT` 이 개체의 첫 번째 문자의 0기반 인덱스입니다.

*nCount*<br/>
이 `CStringT` 개체에서 추출할 문자의 수입니다. 이 매개 변수가 제공되지 않으면 문자열의 나머지 가 추출됩니다.

### <a name="return-value"></a>Return Value

지정된 문자 범위의 복사본을 포함하는 `CStringT` 개체입니다. 반환된 `CStringT` 개체는 비어 있을 수 있습니다.

### <a name="remarks"></a>설명

함수는 추출된 하위 문자열의 복사본을 반환합니다. `Mid`기본 Mid 함수와 유사합니다(Basic의 인덱스가 1기반임을 제외).

멀티바이트 문자 집합(MBCS)의 경우 *nCount는* 각 8비트 문자를 참조합니다. 즉, 한 다바이트 문자의 리드 및 트레일 바이트는 두 문자로 계산됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

## <a name="cstringtoemtoansi"></a><a name="oemtoansi"></a>스트링T::OemToAnsi

OEM 문자 집합에서 `CStringT` ANSI 문자 집합으로 이 개체의 모든 문자를 변환합니다.

```cpp
void OemToAnsi();
```

### <a name="remarks"></a>설명

_UNICODE 정의된 경우 이 함수를 사용할 수 없습니다.

### <a name="example"></a>예제

[CStringT::AnsiToOem에](#ansitooem)대한 예제를 참조하십시오.

## <a name="cstringtoperator-"></a><a name="operator_eq"></a>CStringT::연산자 =

문자열에 새 값을 할당합니다.

```
CStringT& operator=(const CStringT& strSrc);

template<bool bMFCDLL>
CStringT& operator=(const CSimpleStringT<BaseType, bMFCDLL>& str);

CStringT& operator=(PCXSTR pszSrc);
CStringT& operator=(PCYSTR pszSrc);
CStringT& operator=(const unsigned char* pszSrc);
CStringT& operator=(XCHAR ch);
CStringT& operator=(YCHAR ch);
CStringT& operator=(const VARIANT& var);
```

### <a name="parameters"></a>매개 변수

*strSrc*<br/>
이 `CStringT` 문자열에 할당할 A입니다.

*Str*<br/>
`CThisSimpleString` 개체에 대한 참조입니다.

*bMFCDLL*<br/>
프로젝트가 MFC DLL인지 여부를 지정하는 부울입니다.

*BaseType*<br/>
문자열 기본 형식입니다.

*var*<br/>
이 문자열에 할당할 변형 개체입니다.

*채널*<br/>
문자열에 할당할 ANSI 또는 유니코드 문자입니다.

*pszSrc*<br/>
할당되는 원래 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

할당 연산자는 `CStringT` 다른 개체, 문자 포인터 또는 단일 문자를 허용합니다. 새 저장소를 할당할 수 있으므로 이 연산자를 사용할 때마다 메모리 예외가 발생할 수 있습니다.

자세한 `CThisSimpleString`내용은 [CStringT::CStringT의](#cstringt)비고 섹션을 참조하십시오.

> [!NOTE]
> 포함된 null 문자가 `CStringT` 포함된 인스턴스를 만들 수 있지만 이에 대해 권장합니다. 포함된 null 문자가 `CStringT` 포함된 개체에 메서드 및 연산자를 호출하면 의도하지 않은 결과가 생성될 수 있습니다.

## <a name="cstringtoperator-"></a><a name="operator_add"></a>CStringT::연산자 +

두 개의 문자열 또는 문자와 문자열을 연결합니다.

```
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```

### <a name="parameters"></a>매개 변수

*ch1*<br/>
문자열과 연결할 ANSI 또는 유니코드 문자입니다.

*ch2*<br/>
문자열과 연결할 ANSI 또는 유니코드 문자입니다.

*str1*<br/>
문자열 `CStringT` 또는 문자와 연결합니다.

*str2*<br/>
문자열 `CStringT` 또는 문자와 연결합니다.

*psz1*<br/>
문자열 또는 문자와 연결하는 null 종료 된 문자열에 대 한 포인터입니다.

*psz2*<br/>
문자열 또는 문자와 연결하는 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

함수에는 7가지 과부하 `CStringT::operator+` 형식이 있습니다. 첫 번째 버전은 두 개의 `CStringT` 기존 객체를 연결합니다. 다음 두 개체와 `CStringT` null 종료 된 문자열을 연결 합니다. 다음 두 개체와 `CStringT` ANSI 문자를 연결 합니다. 마지막 두 개는 `CStringT` 개체와 유니코드 문자를 연결합니다.

> [!NOTE]
> 포함된 null 문자가 `CStringT` 포함된 인스턴스를 만들 수 있지만 이에 대해 권장합니다. 포함된 null 문자가 `CStringT` 포함된 개체에 메서드 및 연산자를 호출하면 의도하지 않은 결과가 생성될 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_add_eq"></a>CStringT::연산자 +=

문자열끝에 문자를 연결합니다.

```
CStringT& operator+=(const CThisSimpleString& str);

template<bool bMFCDLL>
CStringT& operator+=(const const CSimpleStringT<BaseType, bMFCDLL>& str);

template<int t_nSize>
CStringT& operator+=(const CStaticString<XCHAR, t_nSize>& strSrc);
CStringT& operator+=(PCXSTR pszSrc);
CStringT& operator+=(PCYSTR pszSrc);
CStringT& operator+=(char ch);
CStringT& operator+=(unsigned char ch);
CStringT& operator+=(wchar_t ch);
CStringT& operator+=(const VARIANT& var);
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
`CThisSimpleString` 개체에 대한 참조입니다.

*bMFCDLL*<br/>
프로젝트가 MFC DLL인지 여부를 지정하는 부울입니다.

*BaseType*<br/>
문자열 기본 형식입니다.

*var*<br/>
이 문자열에 연결할 변형 개체입니다.

*채널*<br/>
문자열과 연결할 ANSI 또는 유니코드 문자입니다.

*pszSrc*<br/>
연결되는 원래 문자열에 대한 포인터입니다.

*strSrc*<br/>
이 `CStringT` 문자열에 연결합니다.

### <a name="remarks"></a>설명

연산자는 다른 `CStringT` 개체, 문자 포인터 또는 단일 문자를 허용합니다. 이 `CStringT` 개체에 추가된 문자에 대해 새 저장소를 할당할 수 있으므로 이 연결 연산자를 사용할 때마다 메모리 예외가 발생할 수 있습니다.

자세한 `CThisSimpleString`내용은 [CStringT::CStringT의](#cstringt)비고 섹션을 참조하십시오.

> [!NOTE]
> 포함된 null 문자가 `CStringT` 포함된 인스턴스를 만들 수 있지만 이에 대해 권장합니다. 포함된 null 문자가 `CStringT` 포함된 개체에 메서드 및 연산자를 호출하면 의도하지 않은 결과가 생성될 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_eq_eq"></a>CStringT::연산자 ==

두 문자열이 논리적으로 동일한지 여부를 결정합니다.

```
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>매개 변수

*ch1*<br/>
비교를 위한 ANSI 또는 유니코드 문자입니다.

*ch2*<br/>
비교를 위한 ANSI 또는 유니코드 문자입니다.

*str1*<br/>
비교를 위한 A. `CStringT`

*str2*<br/>
비교를 위한 A. `CStringT`

*psz1*<br/>
비교를 위해 null 종료된 문자열에 대한 포인터입니다.

*psz2*<br/>
비교를 위해 null 종료된 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

왼쪽의 문자열이나 문자가 오른쪽의 문자열이나 문자와 동일한지 테스트하고 그에 따라 TRUE 또는 FALSE를 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

## <a name="cstringtoperator-"></a><a name="operator_neq"></a>CStringT::연산자 !=

두 문자열이 논리적으로 같지 않은지 여부를 결정합니다.

```
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>매개 변수

*ch1*<br/>
문자열과 연결할 ANSI 또는 유니코드 문자입니다.

*ch2*<br/>
문자열과 연결할 ANSI 또는 유니코드 문자입니다.

*str1*<br/>
비교를 위한 A. `CStringT`

*str2*<br/>
비교를 위한 A. `CStringT`

*psz1*<br/>
비교를 위해 null 종료된 문자열에 대한 포인터입니다.

*psz2*<br/>
비교를 위해 null 종료된 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

왼쪽의 문자열이나 문자가 오른쪽의 문자열이나 문자와 같지 않은지 테스트합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

## <a name="cstringtoperator-lt"></a><a name="operator_lt"></a>CStringT::연산자&lt;

연산자의 왼쪽에 있는 문자열이 오른쪽의 문자열보다 적은지 여부를 결정합니다.

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
비교를 위한 A. `CStringT`

*str2*<br/>
비교를 위한 A. `CStringT`

*psz1*<br/>
비교를 위해 null 종료된 문자열에 대한 포인터입니다.

*psz2*<br/>
비교를 위해 null 종료된 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

문자열 간의 사전 비교, 문자별 문자까지:

- 해당하는 두 문자가 같지 않음이 확인될 때까지. 이 경우 해당 비교 결과를 문자열 간의 비교 결과로 가져옵니다.

- 같지 않은 문자는 없으나 한 문자열의 문자 수가 다른 문자열보다 많음이 확인될 때까지. 이 경우 더 짧은 문자열이 더 긴 문자열보다 작은 것으로 간주합니다.

- 같지 않은 문자가 없으며 문자열의 문자 수도 같음이 확인될 때까지. 이 경우 두 문자열은 동일한 것으로 간주합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

## <a name="cstringtoperator-gt"></a><a name="operator_gt"></a>CStringT::연산자&gt;

연산자의 왼쪽에 있는 문자열이 오른쪽의 문자열보다 큰지 여부를 결정합니다.

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
비교를 위한 A. `CStringT`

*str2*<br/>
비교를 위한 A. `CStringT`

*psz1*<br/>
비교를 위해 null 종료된 문자열에 대한 포인터입니다.

*psz2*<br/>
비교를 위해 null 종료된 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

문자열 간의 사전 비교, 문자별 문자까지:

- 해당하는 두 문자가 같지 않음이 확인될 때까지. 이 경우 해당 비교 결과를 문자열 간의 비교 결과로 가져옵니다.

- 같지 않은 문자는 없으나 한 문자열의 문자 수가 다른 문자열보다 많음이 확인될 때까지. 이 경우 더 짧은 문자열이 더 긴 문자열보다 작은 것으로 간주합니다.

- 같지 않은 문자가 없으며 문자열의 문자 수도 같음이 확인될 때까지. 이 경우 두 문자열은 동일한 것으로 간주합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

## <a name="cstringtoperator-lt"></a><a name="operator_lt_eq"></a>CStringT::연산자&lt;=

연산자의 왼쪽에 있는 문자열이 오른쪽의 문자열보다 적거나 같는지 여부를 결정합니다.

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
비교를 위한 A. `CStringT`

*str2*<br/>
비교를 위한 A. `CStringT`

*psz1*<br/>
비교를 위해 null 종료된 문자열에 대한 포인터입니다.

*psz2*<br/>
비교를 위해 null 종료된 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

문자열 간의 사전 비교, 문자별 문자까지:

- 해당하는 두 문자가 같지 않음이 확인될 때까지. 이 경우 해당 비교 결과를 문자열 간의 비교 결과로 가져옵니다.

- 같지 않은 문자는 없으나 한 문자열의 문자 수가 다른 문자열보다 많음이 확인될 때까지. 이 경우 더 짧은 문자열이 더 긴 문자열보다 작은 것으로 간주합니다.

- 같지 않은 문자가 없으며 문자열의 문자 수도 같음이 확인될 때까지. 이 경우 두 문자열은 동일한 것으로 간주합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

## <a name="cstringtoperator-gt"></a><a name="operator_gt_eq"></a>CStringT::연산자&gt;=

연산자의 왼쪽에 있는 문자열이 오른쪽의 문자열보다 크거나 같는지 여부를 결정합니다.

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
비교를 위한 A. `CStringT`

*str2*<br/>
비교를 위한 A. `CStringT`

*psz1*<br/>
비교를 위해 문자열에 대한 포인터입니다.

*psz2*<br/>
비교를 위해 문자열에 대한 포인터입니다.

### <a name="remarks"></a>설명

문자열 간의 사전 비교, 문자별 문자까지:

- 해당하는 두 문자가 같지 않음이 확인될 때까지. 이 경우 해당 비교 결과를 문자열 간의 비교 결과로 가져옵니다.

- 같지 않은 문자는 없으나 한 문자열의 문자 수가 다른 문자열보다 많음이 확인될 때까지. 이 경우 더 짧은 문자열이 더 긴 문자열보다 작은 것으로 간주합니다.

- 같지 않은 문자가 없으며 문자열의 문자 수도 같음이 확인될 때까지. 이 경우 두 문자열은 동일한 것으로 간주합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

## <a name="cstringtremove"></a><a name="remove"></a>CStringT::제거

문자열에서 지정된 문자의 모든 인스턴스를 제거합니다.

```
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>매개 변수

*chRemove*<br/>
문자열에서 제거할 문자입니다.

### <a name="return-value"></a>Return Value

문자열에서 제거된 문자 수입니다. 문자열이 변경되지 않으면 0입니다.

### <a name="remarks"></a>설명

문자에 대한 비교는 대/소문자를 구분합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

## <a name="cstringtreplace"></a><a name="replace"></a>CStringT::바꾸기

의 두 가지 `Replace`버전이 있습니다. 첫 번째 버전은 다른 하위 문자열을 사용하여 하나 이상의 하위 문자열 복사본을 대체합니다. 두 하위 문자열은 null-종료됩니다. 두 번째 버전은 다른 문자를 사용하여 하나 이상의 문자 복사본을 대체합니다. 두 버전 모두 에 저장된 `CStringT`문자 데이터에서 작동합니다.

```
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>매개 변수

*pszOld*<br/>
*pszNew로*대체할 null 종료 된 문자열에 대한 포인터 .

*pszNew*<br/>
*pszOld를*대체하는 null 종료 된 문자열에 대한 포인터입니다.

*chOld*<br/>
*문자를 chNew로*대체합니다.

*chNew*<br/>
문자를 대체하는 *chOld*.

### <a name="return-value"></a>Return Value

문자열이 변경되지 않은 경우 문자 또는 하위 문자열의 대체 된 인스턴스 수를 반환하거나 0을 반환합니다.

### <a name="remarks"></a>설명

`Replace`*pszNew* 및 *pszOld가* 동일한 길이일 필요는 없으며 이전 하위 문자열의 여러 복사본을 새 문자열로 변경할 수 있으므로 문자열 길이를 변경할 수 있습니다. 함수는 대/소문자 구분 일치를 수행합니다.

인스턴스의 `CStringT` 예로는 `CString` `CStringA`" `CStringW`및

의 `CStringA` `Replace` 경우 ANSI 또는 멀티 바이트 (MBCS) 문자와 함께 작동합니다. 의 `CStringW` `Replace` 경우 와이드 문자와 함께 작동합니다.

의 `CString`경우 다음 테이블의 상수가 정의되었는지 여부에 따라 컴파일 시 문자 데이터 형식이 선택됩니다.

|정의된 상수|문자 데이터 유형|
|----------------------|-------------------------|
|_UNICODE|와이드 문자|
|_MBCS|다중 바이트 문자|
|Neither|단일 바이트 문자|
|모두|정의되지 않음|

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

## <a name="cstringtreversefind"></a><a name="reversefind"></a>CStringT::역찾기

이 `CStringT` 개체에서 문자의 마지막 일치 를 검색합니다.

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>매개 변수

*채널*<br/>
검색할 문자입니다.

### <a name="return-value"></a>Return Value

요청된 문자와 일치하는 이 `CStringT` 개체의 마지막 문자의 0기반 인덱스 또는 문자를 찾을 수 없는 경우 -1입니다.

### <a name="remarks"></a>설명

이 함수는 런타임 함수와 `strrchr`유사합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

## <a name="cstringtright"></a><a name="right"></a>CStringT::오른쪽

이 `CStringT` 개체에서 마지막(즉, 가장 오른쪽) *nCount* 문자를 추출하고 추출된 하위 문자열의 복사본을 반환합니다.

```
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>매개 변수

*nCount*<br/>
이 `CStringT` 개체에서 추출할 문자의 수입니다.

### <a name="return-value"></a>Return Value

지정된 문자 범위의 복사본을 포함하는 `CStringT` 개체입니다. 반환된 `CStringT` 개체는 비어 있을 수 있습니다.

### <a name="remarks"></a>설명

*nCount가* 문자열 길이를 초과하면 전체 문자열이 추출됩니다. `Right`기본 `Right` 함수와 유사합니다(Basic의 인덱스가 0기반임을 제외).

멀티바이트 문자 집합(MBCS)의 경우 *nCount는* 각 8비트 문자를 참조합니다. 즉, 한 다바이트 문자의 리드 및 트레일 바이트는 두 문자로 계산됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

## <a name="cstringtsetsysstring"></a><a name="setsysstring"></a>CStringT:::세시스트링

*pbstr로* 가리키는 BSTR을 재할당하고 NULL 문자를 포함하여 `CStringT` 개체의 내용을 복사합니다.

```
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>매개 변수

*pbstr*<br/>
문자 문자열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

새 문자열입니다.

### <a name="remarks"></a>설명

`CStringT` 개체의 내용에 따라 *pbstr에서* 참조하는 BSTR 값이 변경될 수 있습니다. 함수는 메모리가 `CMemoryException` 부족한 경우 를 throw합니다.

이 함수는 일반적으로 자동화에 대 한 참조에 의해 전달 되는 문자열의 값을 변경 하는 데 사용 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

## <a name="cstringtspanexcluding"></a><a name="spanexcluding"></a>CStringT::범위 제외

*pszCharSet으로*식별된 문자 집합에 없는 첫 번째 문자부터 시작하여 문자열에서 문자를 추출합니다.

```
CStringT SpanExcluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>매개 변수

*pszCharSet*<br/>
문자 집합으로 해석되는 문자열입니다.

### <a name="return-value"></a>Return Value

*pszCharSet에*없는 문자열에 있는 문자열에 있는 문자를 포함 하는 하위 문자열, 문자열의 첫 번째 문자로 시작 하 고 *pszCharSet에* 있는 문자열에 있는 첫 번째 문자로 끝나는 문자열 (즉, 문자열의 첫 번째 문자로 시작 하 고 최대 하지만 *pszCharSet*발견 된 문자열의 첫 번째 문자를 제외). *문자열에 pszCharSet의* 문자가 없는 경우 전체 문자열을 반환합니다.

### <a name="remarks"></a>설명

`SpanExcluding`*pszCharSet에서* 문자가 처음 발생하기 전에 모든 문자를 추출하고 반환합니다(즉, *pszCharSet의* 문자와 문자열에 있는 모든 문자는 반환되지 않음). *문자열에 pszCharSet의* 문자가 없는 경우 `SpanExcluding` 전체 문자열을 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

## <a name="cstringtspanincluding"></a><a name="spanincluding"></a>CStringT::스팬 포함

*pszCharSet으로*식별된 문자 집합에 있는 첫 번째 문자부터 시작하여 문자열에서 문자를 추출합니다.

```
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>매개 변수

*pszCharSet*<br/>
문자 집합으로 해석되는 문자열입니다.

### <a name="return-value"></a>Return Value

*pszCharSet에*있는 문자열에 있는 문자를 포함 하는 하위 문자열문자열의 첫 번째 문자로 시작 하 고 *문자가 pszCharSet에*없는 문자열에서 찾을 때 끝납니다. `SpanIncluding`문자열의 첫 번째 문자가 지정된 집합에 없는 경우 빈 하위 문자열을 반환합니다.

### <a name="remarks"></a>설명

문자열의 첫 번째 문자가 문자 집합에 `SpanIncluding` 없는 경우 빈 문자열을 반환합니다. 그렇지 않으면 집합에 있는 연속된 문자 의 시퀀스를 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

## <a name="cstringttokenize"></a><a name="tokenize"></a>CStringT::토큰화

대상 문자열에서 다음 토큰을 찾습니다.

```
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const;
```

### <a name="parameters"></a>매개 변수

*pszTokens*<br/>
토큰 구분 기호를 포함하는 문자열입니다. 이러한 구분 기호의 순서는 중요하지 않습니다.

*iStart*<br/>
검색을 시작할 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

현재 `CStringT` 토큰 값을 포함하는 개체입니다.

### <a name="remarks"></a>설명

함수는 `Tokenize` 대상 문자열에서 다음 토큰을 찾습니다. *pszTokens의* 문자 집합은 찾을 토큰의 가능한 구분 기호를 지정합니다. 함수에 대한 `Tokenize` 각 호출은 *iStart에서*시작되며, 선행 구분 `CStringT` 기호를 건너뛰고 현재 토큰을 포함하는 개체를 반환합니다. *iStart의* 값은 종료 구분 기호 문자 다음의 위치로 업데이트되거나 문자열의 끝에 도달하면 -1로 업데이트됩니다. *iStart를* 사용하여 다음 토큰을 읽을 문자열의 위치를 추적하기 `Tokenize`위해 일련의 호출을 통해 대상 문자열의 나머지 부분에서 더 많은 토큰을 나눌 수 있습니다. 토큰이 더 이상 없는 경우 함수는 빈 문자열을 반환하고 *iStart는* -1로 설정됩니다.

CRT와 달리 [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s,](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md) `Tokenize` _mbstok_s_l 같은 함수는 대상 문자열을 수정하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>설명

이 예제의 출력은 다음과 같습니다.

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

## <a name="cstringttrim"></a><a name="trim"></a>CStringT::트림

문자열에서 선행 및 후행 문자를 트리밍합니다.

```
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>매개 변수

*chTarget*<br/>
트리밍할 대상 문자입니다.

*pszTargets*<br/>
트리밍할 대상 문자를 포함하는 문자열에 대한 포인터입니다. *pszTarget에* 있는 문자의 모든 선행 및 후행 `CStringT` 발생은 오브젝트에서 잘립니다.

### <a name="return-value"></a>Return Value

트리밍된 문자열을 반환합니다.

### <a name="remarks"></a>설명

다음 중 하나의 모든 선행 및 후행 발생을 제거합니다.

- *chTarget에서*지정한 문자입니다.

- *pszTargets에서*지정한 문자열에 있는 모든 문자.

- 공백.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>설명

이 예제의 출력은 다음과 같습니다.

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

## <a name="cstringttrimleft"></a><a name="trimleft"></a>CStringT::트림 레프트

문자열에서 선행 문자를 트리밍합니다.

```
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>매개 변수

*chTarget*<br/>
트리밍할 대상 문자입니다.

*pszTargets*<br/>
트리밍할 대상 문자를 포함하는 문자열에 대한 포인터입니다. *pszTarget에서* 문자의 모든 선행 발생 개체에서 `CStringT` 잘립니다.

### <a name="return-value"></a>Return Value

결과로 트리밍된 문자열입니다.

### <a name="remarks"></a>설명

다음 중 하나의 모든 선행 및 후행 발생을 제거합니다.

- *chTarget에서*지정한 문자입니다.

- *pszTargets에서*지정한 문자열에 있는 모든 문자.

- 공백.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

## <a name="cstringttrimright"></a><a name="trimright"></a>CStringT::트림라이트

문자열에서 후행 문자를 트리밍합니다.

```
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>매개 변수

*chTarget*<br/>
트리밍할 대상 문자입니다.

*pszTargets*<br/>
트리밍할 대상 문자를 포함하는 문자열에 대한 포인터입니다. *pszTarget에* 있는 문자의 모든 후행 발생은 `CStringT` 개체에서 잘립니다.

### <a name="return-value"></a>Return Value

트리밍된 문자열을 `CStringT` 포함하는 개체를 반환합니다.

### <a name="remarks"></a>설명

다음 중 하나의 후행 발생을 제거합니다.

- *chTarget에서*지정한 문자입니다.

- *pszTargets에서*지정한 문자열에 있는 모든 문자.

- 공백.

버전은 `CStringT& TrimRight(XCHAR chTarget)` 하나의 문자 매개 변수를 허용하고 문자열 데이터의 끝에서 `CStringT` 해당 문자의 모든 복사본을 제거합니다. 문자열의 끝에서 시작하여 앞쪽으로 작동합니다. 다른 문자를 찾거나 문자 데이터가 `CSTringT` 부족하면 중지됩니다.

버전은 `CStringT& TrimRight(PCXSTR pszTargets)` 검색할 모든 다른 문자를 포함하는 null-terminated 문자열을 허용합니다. 개체에서 해당 문자의 모든 복사본을 제거합니다. `CStringT` 문자열의 끝에서 시작하여 앞쪽으로 작동합니다. 대상 문자열에 없는 문자를 찾거나 문자 데이터가 부족할 때 `CStringT` 중지됩니다. 의 끝에 있는 하위 문자열에 전체 대상 문자열을 `CStringT`일치시키려고 하지 않습니다.

버전에 `CStringT& TrimRight()` 매개 변수가 필요하지 않습니다. 문자열 의 끝에서 후행 공백 문자를 잘라내며 `CStringT` 합니다. 공백 문자는 줄 바꿈, 공백 또는 탭일 수 있습니다.

-

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
[C심플스트링T 클래스](../../atl-mfc-shared/reference/csimplestringt-class.md)
