---
title: 레지스트리 및 TypeLib 전역 함수
ms.date: 03/27/2019
f1_keywords:
- atlbase/ATL::AtlGetPerUserRegistration
- afxpriv/ATL::AfxRegCreateKey
- afxpriv/ATL::AfxRegDeleteKey
- atlbase/ATL::AtlRegisterTypeLib
- afxpriv/ATL::AfxRegOpenKey
- afxpriv/ATL::AfxRegOpenKeyEx
- afxdisp/ATL::AfxUnregisterPreviewHandler
- atlbase/ATL::AtlSetPerUserRegistration
- atlbase/ATL::AtlUnRegisterTypeLib
- atlbase/ATL::AtlLoadTypeLib
- atlbase/ATL::AtlUpdateRegistryFromResourceD
- atlbase/ATL::RegistryDataExchange
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
ms.openlocfilehash: 69df927ddd04c19d10703854aa8c8948894309d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326082"
---
# <a name="registry-and-typelib-global-functions"></a>레지스트리 및 TypeLib 전역 함수

이러한 함수는 형식 라이브러리를 로드하고 등록하는 데 대한 지원을 제공합니다.

> [!IMPORTANT]
> 다음 테이블에 나열된 함수는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AfxRegCreateKey](#afxregcreatekey)|지정된 레지스트리 키를 만듭니다.|
|[AfxRegDeleteKey](#afxregdeletekey)|지정된 레지스트리 키를 삭제합니다.|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|미리 보기 처리기를 등록하는 도우미입니다.|
|[AfxUn레지스터 프리뷰핸들러](#afxunregisterpreviewhandler)| 미리 보기 처리기를 등록 취소하는 도우미입니다. |
|[AtlRegisterTypeLib](#atlregistertypelib)|이 함수는 형식 라이브러리를 등록하기 위해 호출됩니다.|
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|이 함수는 형식 라이브러리를 등록 취소하기 위해 호출됩니다.|
|[AfxRegOpenKey](#afxregopenkey)|지정된 레지스트리 키를 엽니다.|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|지정된 레지스트리 키를 엽니다.|
|[AtlLoadTypeLib](#atlloadtypelib)|이 함수는 형식 라이브러리를 로드하기 위해 호출됩니다.|
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|이 함수는 제공된 리소스에서 레지스트리를 업데이트하기 위해 호출됩니다.|
|[RegistryDataExchange](#registrydataexchange)|이 함수는 시스템 레지스트리에서 읽거나 쓰기 위해 호출됩니다. [레지스트리 데이터 교환 매크로에](../../atl/reference/registry-data-exchange-macros.md)의해 호출 됩니다.|

이러한 함수는 프로그램이 정보를 저장하는 데 사용하는 레지스트리의 노드를 제어합니다.

|||
|-|-|
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|응용 프로그램이 레지스트리 액세스를 **HKEY_CURRENT_USER(HKCU)** 노드로 리디렉션하는지 여부를 검색합니다. **HKEY_CURRENT_USER**|
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|응용 프로그램이 레지스트리 액세스를 **HKEY_CURRENT_USER(HKCU)** 노드로 리디렉션할지 여부를 설정합니다. **HKEY_CURRENT_USER**|

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a>아틀겟퍼유저 등록

이 함수를 사용하여 응용 프로그램이 레지스트리 액세스를**HKEY_CURRENT_USER(HKCU)** 노드로 리디렉션하는지 여부를 확인합니다. **HKEY_CURRENT_USER**

### <a name="syntax"></a>구문

```
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);
```

### <a name="parameters"></a>매개 변수

*pEnabled*<br/>
【아웃】 TRUE는 레지스트리 정보가 **HKCU** 노드로 전달됨을 나타냅니다. FALSE는 응용 프로그램이 레지스트리 정보를 기본 노드에 기록했음을 나타냅니다. 기본 노드는 **HKEY_CLASSES_ROOT** **HKEY_CLASSES_ROOT(HKCR)입니다.**

### <a name="return-value"></a>Return Value

S_OK 메서드가 성공하면 오류가 발생하면 HRESULT 오류 코드가 나타납니다.

### <a name="remarks"></a>설명

레지스트리 리디렉션은 기본적으로 활성화되어 있지 않습니다. 이 옵션을 사용하도록 설정하면 레지스트리 액세스가 **HKEY_CURRENT_USER\Software\Class**로 리디렉션됩니다.

리디렉션은 전역이 아닙니다. MFC 및 ATL 프레임워크만 이 레지스트리 리디렉션의 영향을 받습니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="afxregcreatekey"></a><a name="afxregcreatekey"></a>아fx레그만들기키

지정된 레지스트리 키를 만듭니다.

### <a name="syntax"></a>구문

```
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열린 레지스트리 키에 대한 핸들입니다.

*lpSubKey*<br/>
이 함수가 열리거나 만드는 키의 이름입니다.

*phk결과*<br/>
열린 키또는 생성된 키에 대한 핸들을 받는 변수에 대한 포인터입니다.

*Ptm*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값이 ERROR_SUCCESS. 함수가 실패하면 반환 값은 Winerror.h에 정의된 제로가 아닌 오류 코드입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxregdeletekey"></a><a name="afxregdeletekey"></a>아fxRegDelete키

지정된 레지스트리 키를 삭제합니다.

### <a name="syntax"></a>구문

```
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열린 레지스트리 키에 대한 핸들입니다.

*lpSubKey*<br/>
삭제할 키의 이름입니다.

*Ptm*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값이 ERROR_SUCCESS. 함수가 실패하면 반환 값은 Winerror.h에 정의된 제로가 아닌 오류 코드입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxregisterpreviewhandler"></a>

미리 보기 처리기를 등록하는 도우미입니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);
```

### <a name="parameters"></a>매개 변수

*lpszCLSID*<br/>
처리기의 CLSID를 지정합니다.

*lpsz쇼트타입네임*<br/>
처리기의 프로그ID를 지정합니다.

*lpsz필터익스펙트*<br/>
이 처리기에 등록된 파일 확장명(확장)을 지정합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="atlregistertypelib"></a><a name="atlregistertypelib"></a>아틀레지스터타이프리브

이 함수는 형식 라이브러리를 등록하기 위해 호출됩니다.

```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>매개 변수

*힌스트타이프리브*<br/>
모듈 인스턴스에 대한 핸들입니다.

*lpszIndex*<br/>
N이 형식\\라이브러리 리소스의 정수 인덱스인 형식 "\N"의 문자열입니다. 인덱스가 필요하지 않은 경우 NULL이 될 수 있습니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 도우미 기능은 [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) 및 [CAtlComModule::RegisterTypeLib에](../../atl/reference/catlcommodule-class.md#registertypelib)의해 사용됩니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="afxregopenkey"></a><a name="afxregopenkey"></a>아fx레그오픈키

지정된 레지스트리 키를 엽니다.

### <a name="syntax"></a>구문

```
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열린 레지스트리 키에 대한 핸들입니다.

*lpSubKey*<br/>
이 함수가 열리거나 만드는 키의 이름입니다.

*phk결과*<br/>
생성된 키에 대한 핸들을 받는 변수에 대한 포인터입니다.

*Ptm*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값이 ERROR_SUCCESS. 함수가 실패하면 반환 값은 Winerror.h에 정의된 제로가 아닌 오류 코드입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxregopenkeyex"></a><a name="afxregopenkeyex"></a>아fxRegOpenKeyEx

지정된 레지스트리 키를 엽니다.

### <a name="syntax"></a>구문

```
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
열린 레지스트리 키에 대한 핸들입니다.

*lpSubKey*<br/>
이 함수가 열리거나 만드는 키의 이름입니다.

*ul옵션*<br/>
이 매개 변수는 예약되어 있으며 0이어야 합니다.

*삼원하는*<br/>
키에 대한 원하는 액세스 권한을 지정하는 마스크입니다.

*phk결과*<br/>
열린 키에 대한 핸들을 받는 변수에 대한 포인터입니다.

*Ptm*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값이 ERROR_SUCCESS. 함수가 실패하면 반환 값은 Winerror.h에 정의된 제로가 아닌 오류 코드입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxunregisterpreviewhandler"></a><a name="afxunregisterpreviewhandler"></a>AfxUn레지스터 프리뷰핸들러

미리 보기 처리기를 등록 취소하는 도우미입니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);
```

### <a name="parameters"></a>매개 변수

*lpszCLSID*<br/>
처리기의 CLSID를 등록 취소하도록 지정합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a>아틀셋퍼유저 등록

응용 프로그램이 레지스트리 액세스를**HKEY_CURRENT_USER(HKCU)** 노드로 리디렉션할지 여부를 설정합니다. **HKEY_CURRENT_USER**

### <a name="syntax"></a>구문

```
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE는 레지스트리 정보가 **HKCU** 노드로 전달됨을 나타냅니다. FALSE는 응용 프로그램이 레지스트리 정보를 기본 노드에 기록했음을 나타냅니다. 기본 노드는 **HKEY_CLASSES_ROOT** **HKEY_CLASSES_ROOT(HKCR)입니다.**

### <a name="return-value"></a>Return Value

S_OK 메서드가 성공하면 오류가 발생하면 HRESULT 오류 코드가 나타납니다.

### <a name="remarks"></a>설명

레지스트리 리디렉션은 기본적으로 활성화되어 있지 않습니다. 이 옵션을 사용하도록 설정하면 레지스트리 액세스가 **HKEY_CURRENT_USER\Software\Class**로 리디렉션됩니다.

리디렉션은 전역이 아닙니다. MFC 및 ATL 프레임워크만 이 레지스트리 리디렉션의 영향을 받습니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="atlunregistertypelib"></a><a name="atlunregistertypelib"></a>아틀룬레지스터타이프리브

이 함수는 형식 라이브러리를 등록 취소하기 위해 호출됩니다.

### <a name="syntax"></a>구문

```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex);
```

### <a name="parameters"></a>매개 변수

*힌스트타이프리브*<br/>
모듈 인스턴스에 대한 핸들입니다.

*lpszIndex*<br/>
N이 형식\\라이브러리 리소스의 정수 인덱스인 형식 "\N"의 문자열입니다. 인덱스가 필요하지 않은 경우 NULL이 될 수 있습니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 도우미 기능은 [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) 및 [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver).

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="atlloadtypelib"></a><a name="atlloadtypelib"></a>아틀로드 타입리브

이 함수는 형식 라이브러리를 로드하기 위해 호출됩니다.

### <a name="syntax"></a>구문

```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```

### <a name="parameters"></a>매개 변수

*힌스트타이프리브*<br/>
형식 라이브러리와 연결된 모듈을 처리합니다.

*lpszIndex*<br/>
N이 형식\\라이브러리 리소스의 정수 인덱스인 형식 "\N"의 문자열입니다. 인덱스가 필요하지 않은 경우 NULL이 될 수 있습니다.

*pbstrPath*<br/>
성공적으로 반환하면 형식 라이브러리와 연결된 모듈의 전체 경로가 포함됩니다.

*ppTypeLib*<br/>
성공적으로 반환하면 로드된 형식 라이브러리에 대한 포인터에 대한 포인터가 포함됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 도우미 함수는 [AtlRegisterTypeLib](#atlregistertypelib) 및 [AtlUnRegisterTypeLib에서](#atlunregistertypelib)사용됩니다.

## <a name="atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a>아틀업데이트레지스트리로부터자원D

이 함수는 Visual Studio 2013에서 사용이 중단되었으며, Visual Studio 2015에서 제거되었습니다.

```
<removed>
```

## <a name="registrydataexchange"></a><a name="registrydataexchange"></a>레지스트리데이터익스체인지

이 함수는 시스템 레지스트리에서 읽거나 쓰기 위해 호출됩니다.

### <a name="syntax"></a>구문

```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```

### <a name="parameters"></a>매개 변수

*Pt*<br/>
현재 개체에 대한 포인터입니다.

*rdxOp*<br/>
함수가 수행해야 하는 작업을 나타내는 열거형 값입니다. 허용된 값에 대한 설명 섹션의 표를 참조하십시오.

*pItem*<br/>
레지스트리에서 읽거나 기록할 데이터에 대한 포인터입니다. 데이터는 레지스트리에서 삭제할 키를 나타낼 수도 있습니다. 기본값은 NULL입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

BEGIN_RDX_MAP [및](registry-data-exchange-macros.md#begin_rdx_map) [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) 매크로를 호출하는 `RegistryDataExchange`함수로 확장합니다.

함수가 수행해야 하는 작업을 나타내는 가능한 열거형 값은 다음 표에 나와 있습니다.

|열거형 값|작업(Operation)|
|----------------|---------------|
|eReadFromReg|레지스트리에서 데이터를 읽습니다.|
|eWriteToReg|레지스트리에 데이터를 씁니다.|
|eDeleteFromReg|레지스트리에서 키를 삭제합니다.|

### <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="see-also"></a>참고 항목

[Functions](atl-functions.md)<br/>
[레지스트리 데이터 교환 매크로](registry-data-exchange-macros.md)
