---
title: 디버깅 및 오류 보고 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlcomcli/ATL::AtlHresultFromLastError
- atlcom/ATL::AtlReportError
- atldef/ATL::AtlThrow
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
ms.openlocfilehash: f7636b1f4e13340b223edd8c63c39bbeb21c8bd0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330200"
---
# <a name="debugging-and-error-reporting-global-functions"></a>디버깅 및 오류 보고 전역 함수

이러한 함수는 유용한 디버깅 및 추적 기능을 제공합니다.

|||
|-|-|
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|HRESULT `GetLastError` 의 형태로 오류 코드를 반환합니다.|
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Win32 오류 코드 HRESULT로 변환합니다.|
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|클라이언트에 `IErrorInfo` 오류 세부 정보를 제공하도록 설정합니다.|
|[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)|`CAtlException`을 throw합니다.|
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Windows 함수 `GetLastError`의 결과에 따라 오류를 표시하려면 이 함수를 호출합니다.|

## <a name="atlhresultfromlasterror"></a><a name="atlhresultfromlasterror"></a>아틀H결과서오류

호출 스레드의 마지막 오류 코드 값을 HRESULT 형식으로 반환합니다.

```
HRESULT AtlHresultFromLastError();
```

### <a name="remarks"></a>설명

`AtlHresultFromLastError`호출하여 `GetLastError` 마지막 오류를 가져오고 HRESULT_FROM_WIN32 매크로를 사용하여 HRESULT로 변환한 후 오류를 반환합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlcomcli.h

## <a name="atlhresultfromwin32"></a><a name="atlhresultfromwin32"></a>아틀H결과윈32

Win32 오류 코드 HRESULT로 변환합니다.

```
AtlHresultFromWin32(DWORD error);
```

### <a name="parameters"></a>매개 변수

*error*<br/>
변환할 오류 값입니다.

### <a name="remarks"></a>설명

매크로 HRESULT_FROM_WIN32 사용하여 Win32 오류 코드를 HRESULT로 변환합니다.

> [!NOTE]
> 사용 하는 `HRESULT_FROM_WIN32(GetLastError())`대신 , [함수 AtlHresultFromLastError를](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)사용 하 여 .

### <a name="requirements"></a>요구 사항

**헤더:** atlcomcli.h

## <a name="atlreporterror"></a><a name="atlreporterror"></a>아틀리포트오류

개체의 `IErrorInfo` 클라이언트에 오류 정보를 제공 하도록 인터페이스를 설정 합니다.

```
HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
【인】 오류를 보고하는 개체의 CLSID입니다.

*lpszDesc*<br/>
【인】 오류를 설명하는 문자열입니다. 유니코드 버전은 *lpszDesc이* LPCOLESTR 형식임을 지정합니다. ANSI 버전은 LPCSTR 의 유형을 지정합니다.

*Iid*<br/>
【인】 운영 체제에서 오류가 정의된 경우 오류 또는 GUID_NULL 정의하는 인터페이스의 IID입니다.

*hRes*<br/>
【인】 호출자에게 반환하려는 HRESULT입니다.

*nID*<br/>
【인】 오류 설명 문자열이 저장되는 리소스 식별자입니다. 이 값은 포함적으로 0x0200과 0xFFFF 사이에 있어야 합니다. 디버그 빌드에서 *nID가* 유효한 문자열을 인덱싱하지 않으면 **ASSERT가** 발생합니다. 릴리스 빌드에서 오류 설명 문자열이 "알 수 없는 오류"로 설정됩니다.

*dwHelpID*<br/>
【인】 오류에 대한 도움말 컨텍스트 식별자입니다.

*lpszHelpFile*<br/>
【인】 오류를 설명하는 도움말 파일의 경로 및 이름입니다.

*힌스트 (약)*<br/>
【인】 리소스에 대한 핸들입니다. 기본적으로 이 매개 `__AtlBaseModuleModule::GetResourceInstance` `__AtlBaseModuleModule` 변수는 [CAtlBaseModule의](../../atl/reference/catlbasemodule-class.md) 전역 인스턴스 또는 이 매개 변수에서 파생된 클래스입니다.

### <a name="return-value"></a>Return Value

*hRes* 매개 변수가 0이 아닌 경우 *reRes 값을 반환합니다.* *reRes가* 0이면 처음 네 가지 `AtlReportError` 버전의 반환이 DISP_E_EXCEPTION. 마지막 두 버전은 매크로 **MAKE_HRESULT(1,** `nID` **FACILITY_ITF)** 의 결과를 반환합니다.

### <a name="remarks"></a>설명

문자열 *lpszDesc오류의* 텍스트 설명으로 사용됩니다. 클라이언트에서 반환하는 `AtlReportError` `IErrorInfo` *reRes를* 받으면 클라이언트는 오류에 대한 자세한 내용을 위해 구조에 액세스할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]

> [!CAUTION]
> C++ `AtlReportError` 캐치 핸들러에서는 사용하지 마십시오. 이러한 함수의 일부 재정의는 내부적으로 ATL 문자열 변환 매크로를 `_alloca` 사용하며, 이 매크로는 내부적으로 함수를 사용합니다. C++ catch 처리기에서 사용하면 `AtlReportError` C++ catch 처리기에서 예외가 발생할 수 있습니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="atlthrow"></a><a name="atlthrow"></a>아틀로로우

HRESULT 상태 코드를 기반으로 오류를 신호하려면 이 함수를 호출합니다.

```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```

### <a name="parameters"></a>매개 변수

*Hr*<br/>
표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 함수는 오류 조건이 발생할 경우 ATL 및 MFC 코드에서 사용됩니다. 사용자 고유의 코드에서 호출할 수도 있습니다. 이 함수의 기본 구현은 _ATL_NO_EXCEPTIONS 심볼의 정의와 프로젝트, MFC 또는 ATL의 유형에 따라 달라집니다.

모든 경우에 이 함수는 HRESULT를 디버거에 추적합니다.

Visual Studio 2015 업데이트 3 이상에서 이 함수는 가짜 SAL 경고를 피하기 위해 __declspec(noreturn)로 인해 발생한것입니다.

_ATL_NO_EXCEPTIONS MFC 프로젝트에 정의되지 않은 경우 이 함수는 HRESULT 값을 기반으로 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md) throw합니다.

_ATL_NO_EXCEPTIONS ATL 프로젝트에 정의되지 않은 경우 함수는 [CAtlException](../../atl/reference/catlexception-class.md)을 throw합니다.

_ATL_NO_EXCEPTIONS 정의된 경우 이 함수는 예외를 throw하는 대신 어설션 오류가 발생합니다.

ATL 프로젝트의 경우 오류가 발생할 경우 ATL에서 사용할 이 함수를 직접 구현할 수 있습니다. 이렇게 하려면 동일한 시그니처로 `AtlThrow` 사용자 고유의 함수를 정의하고 함수의 이름으로 #define. `AtlThrow` 이것은 atlexcept.h를 포함하기 전에 수행해야합니다 (이는 atlbase.h가 atlexcept.h를 포함하기 때문에 ATL 헤더를 포함하기 전에 수행해야함을 의미합니다). 스퓨리어스 SAL 경고를 피하기 위해 함수를 `__declspec(noreturn)` 특성으로 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]

## <a name="requirements"></a>요구 사항

**헤더:** atldef.h

## <a name="atlthrowlastwin32"></a><a name="atlthrowlastwin32"></a>아틀로라스트윈32

Windows 함수 `GetLastError`의 결과에 따라 오류를 표시하려면 이 함수를 호출합니다.

```
inline void AtlThrowLastWin32();
```

### <a name="remarks"></a>설명

이 함수는 디버거에 대한 `GetLastError` 결과를 추적합니다.

_ATL_NO_EXCEPTIONS MFC 프로젝트에 정의되지 않은 경우 이 함수는 `GetLastError`에서 반환되는 값을 기반으로 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException을](../../mfc/reference/coleexception-class.md) throw합니다.

_ATL_NO_EXCEPTIONS ATL 프로젝트에 정의되지 않은 경우 함수는 [CAtlException](../../atl/reference/catlexception-class.md)을 throw합니다.

_ATL_NO_EXCEPTIONS 정의된 경우 이 함수는 예외를 throw하는 대신 어설션 오류가 발생합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldef.h

## <a name="see-also"></a>참고 항목

[Functions](../../atl/reference/atl-functions.md)<br/>
[디버깅 및 오류 보고 매크로](../../atl/reference/debugging-and-error-reporting-macros.md)
