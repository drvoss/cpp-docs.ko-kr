---
title: 올레디스패치드라이버 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDispatchDriver
- AFXDISP/COleDispatchDriver
- AFXDISP/COleDispatchDriver::COleDispatchDriver
- AFXDISP/COleDispatchDriver::AttachDispatch
- AFXDISP/COleDispatchDriver::CreateDispatch
- AFXDISP/COleDispatchDriver::DetachDispatch
- AFXDISP/COleDispatchDriver::GetProperty
- AFXDISP/COleDispatchDriver::InvokeHelper
- AFXDISP/COleDispatchDriver::ReleaseDispatch
- AFXDISP/COleDispatchDriver::SetProperty
- AFXDISP/COleDispatchDriver::m_bAutoRelease
- AFXDISP/COleDispatchDriver::m_lpDispatch
helpviewer_keywords:
- COleDispatchDriver [MFC], COleDispatchDriver
- COleDispatchDriver [MFC], AttachDispatch
- COleDispatchDriver [MFC], CreateDispatch
- COleDispatchDriver [MFC], DetachDispatch
- COleDispatchDriver [MFC], GetProperty
- COleDispatchDriver [MFC], InvokeHelper
- COleDispatchDriver [MFC], ReleaseDispatch
- COleDispatchDriver [MFC], SetProperty
- COleDispatchDriver [MFC], m_bAutoRelease
- COleDispatchDriver [MFC], m_lpDispatch
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
ms.openlocfilehash: 2b52ed3137a9a515278e018d69751aedaddb0cf1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753885"
---
# <a name="coledispatchdriver-class"></a>올레디스패치드라이버 클래스

OLE 자동화의 클라이언트 쪽을 구현합니다.

## <a name="syntax"></a>구문

```
class COleDispatchDriver
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[올레디스패치 드라이버::콜레디스패치드라이버](#coledispatchdriver)|`COleDispatchDriver` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[올레디스패치 드라이버::첨부 디스패치](#attachdispatch)|개체에 `IDispatch` 연결을 연결합니다. `COleDispatchDriver`|
|[올레디스패치 드라이버::만들기 디스패치](#createdispatch)|`IDispatch` 연결을 만들고 개체에 `COleDispatchDriver` 연결합니다.|
|[COle디스패치드라이버::D에타치디스패치](#detachdispatch)|`IDispatch` 연결을 해제하지 않고 연결을 분리합니다.|
|[COleDispatchDriver::GetProperty](#getproperty)|자동화 속성을 가져옵니다.|
|[COleDispatchDriver::InvokeHelper](#invokehelper)|자동화 메서드를 호출하는 도우미입니다.|
|[올레디스패치드라이버:릴리스디스패치](#releasedispatch)|연결을 `IDispatch` 해제합니다.|
|[올레디스패치 드라이버::설정 속성](#setproperty)|자동화 속성을 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[COle디스패치 드라이버::연산자 =](#operator_eq)|소스 값을 개체에 `COleDispatchDriver` 복사합니다.|
|[COle디스패치드라이버::연산자 LP디스패치](#operator_lpdispatch)|기본 `IDispatch` 포인터에 액세스합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[올레디스패치 드라이버::m_bAutoRelease](#m_bautorelease)|동안 `IDispatch` `ReleaseDispatch` 또는 개체 소멸을 해제할지 여부를 지정합니다.|
|[올레디스패치 드라이버::m_lpDispatch](#m_lpdispatch)|이 `COleDispatchDriver`에 연결된 `IDispatch` 인터페이스에 대한 포인터를 나타냅니다.|

## <a name="remarks"></a>설명

`COleDispatchDriver`기본 클래스가 없습니다.

OLE 디스패치 인터페이스는 개체의 메서드 및 속성에 대한 액세스를 제공합니다. 형식의 `COleDispatchDriver` `IDispatch`디스패치 연결을 연결, 분리, 생성 및 해제하는 멤버 함수입니다. 다른 멤버 함수는 가변 인수 `IDispatch::Invoke`목록을 사용하여 호출을 단순화합니다.

이 클래스는 직접 사용할 수 있지만 일반적으로 클래스 추가 마법사에서 만든 클래스에서만 사용됩니다. 형식 라이브러리를 가져와 새 C++ 클래스를 만들 면 새 `COleDispatchDriver`클래스에서 파생 됩니다.

사용에 `COleDispatchDriver`대한 자세한 내용은 다음 문서를 참조하십시오.

- [자동화 클라이언트](../../mfc/automation-clients.md)

- [자동화 서버](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`COleDispatchDriver`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="coledispatchdriverattachdispatch"></a><a name="attachdispatch"></a>올레디스패치 드라이버::첨부 디스패치

`AttachDispatch` 멤버 함수를 호출하여 `IDispatch` 개체에 대한 `COleDispatchDriver` 포인터를 연결합니다. 자세한 내용은 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)을 참조하십시오.

```cpp
void AttachDispatch(
    LPDISPATCH lpDispatch,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpDispatch*<br/>
`IDispatch` 개체에 연결될 OLE `COleDispatchDriver` 개체에 대한 포인터입니다.

*bAutoRelease*<br/>
이 개체가 범위를 벗어날 때 디스패치를 해제할지 여부를 지정합니다.

### <a name="remarks"></a>설명

이 함수는 `IDispatch` 개체에 이미 연결된 모든 `COleDispatchDriver` 포인터를 해제합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

## <a name="coledispatchdrivercoledispatchdriver"></a><a name="coledispatchdriver"></a>올레디스패치 드라이버::콜레디스패치드라이버

`COleDispatchDriver` 개체를 생성합니다.

```
COleDispatchDriver();
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);
COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>매개 변수

*lpDispatch*<br/>
`IDispatch` 개체에 연결될 OLE `COleDispatchDriver` 개체에 대한 포인터입니다.

*bAutoRelease*<br/>
이 개체가 범위를 벗어날 때 디스패치를 해제할지 여부를 지정합니다.

*dispatchSrc*<br/>
기존 `COleDispatchDriver` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

`COleDispatchDriver`양식 `LPDISPATCH lpDispatch`(, **BOOL**`bAutoRelease` = **TRUE)은** [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) 인터페이스를 연결합니다.

`COleDispatchDriver`& `dispatchSrc` **양식(const)은** `COleDispatchDriver`기존 `COleDispatchDriver` 개체를 복사하고 참조 수를 증가시입니다.

양식 `COleDispatchDriver`() 개체를 `COleDispatchDriver` 만들지만 인터페이스를 `IDispatch` 연결하지 않습니다. () `COleDispatchDriver`인수 없이 사용 하기 전에 `IDispatch` [COleDispatchDriver::CreateDispatch](#createdispatch) [드라이버:::AttachDispatch](#attachdispatch)를 사용 하 여 연결 해야 합니다. 자세한 내용은 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)을 참조하십시오.

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](#createdispatch)에 대한 예제를 참조하세요.

## <a name="coledispatchdrivercreatedispatch"></a><a name="createdispatch"></a>올레디스패치 드라이버::만들기 디스패치

[IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) 인터페이스 개체를 만들고 `COleDispatchDriver` 개체에 연결합니다.

```
BOOL CreateDispatch(
    REFCLSID clsid,
    COleException* pError = NULL);

BOOL CreateDispatch(
    LPCTSTR lpszProgID,
    COleException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
만들려는 `IDispatch` 연결 개체의 클래스 ID입니다.

*pError*<br/>
만들기에서 발생하는 상태 코드를 포함할, OLE 예외 개체에 대한 포인터입니다.

*lpszProgID*<br/>
디스패치 개체를 만들려는 자동화 개체의 프로그래밍 ID(예: "Excel.Document.5")에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

## <a name="coledispatchdriverdetachdispatch"></a><a name="detachdispatch"></a>COle디스패치드라이버::D에타치디스패치

이 개체에서 `IDispatch` 현재 연결을 분리합니다.

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>Return Value

이전에 연결된 OLE `IDispatch` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

릴리스되지 `IDispatch` 않습니다.

LPDispatch 유형에 대한 자세한 내용은 Windows SDK에서 [IDispatch 인터페이스 구현을](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]

## <a name="coledispatchdrivergetproperty"></a><a name="getproperty"></a>올레디스패치 드라이버::GetProperty

*dwDispID에*의해 지정된 개체 속성을 가져옵니다.

```cpp
void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
검색할 속성을 식별합니다.

*vtProp*<br/>
검색할 속성을 지정합니다. 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](#invokehelper)의 설명 섹션을 참조하세요.

*pvProp*<br/>
속성 값을 받을 변수의 주소입니다. *vtProp*에서 지정한 형식과 일치해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]

## <a name="coledispatchdriverinvokehelper"></a><a name="invokehelper"></a>콜레디스패치 드라이버::호출 도우미

wFlags 에 의해 지정된 컨텍스트에서 *dwDispID에*의해 지정된 개체 메서드 또는 속성을 *호출합니다.*

```cpp
void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
호출할 메서드 또는 속성을 식별합니다.

*wFlags*<br/>
에 대한 호출의 컨텍스트를 `IDispatch::Invoke`설명하는 플래그입니다. . 가능한 값 목록은 [IDispatch::In](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) Windows SDK에서 *wFlags* 매개 변수를 참조하십시오.

*vtRet*<br/>
반환 값 형식을 지정합니다. 가능한 값은 설명 섹션을 참조하세요.

*pvRet*<br/>
속성 값이나 반환 값을 받을 변수의 주소입니다. *vtRet*.

*pbParamInfo*<br/>
*pbParamInfo*다음 매개 변수의 형식을 지정 하는 바이트의 null-종료 된 문자열에 대 한 포인터 .

*...*<br/>
매개 변수의 변수 목록, *pbParamInfo에*지정된 형식 .

### <a name="remarks"></a>설명

*pbParamInfo* 매개 변수는 메서드 또는 속성에 전달 된 매개 변수의 형식을 지정 합니다. 인수의 변수 목록은 구문 선언에서 **...** 로 표시됩니다.

*vtRet* 인수에 대한 가능한 값은 VARENUM 열거형에서 가져온 것입니다. 가능한 값은 다음과 같습니다.

|기호|반환 형식|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|**CY**|
|VT_DATE|**날짜**|
|VT_BSTR|BSTR|
|VT_DISPATCH|LP디스패치|
|VT_ERROR|SCODE|
|VT_BOOL|**Bool**|
|VT_VARIANT|**변형**|
|VT_UNKNOWN|LP알 수 없음|

*pbParamInfo* 인수는 **VTS_** 상수의 공간 분리 된 목록입니다. 공백(쉼표가 아님)으로 구분된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정합니다. 가능한 값은 [EVENT_CUSTOM](event-maps.md#event_custom) 매크로를 통해 나열됩니다.

이 함수는 매개 변수를 VARIANTARG 값으로 변환하고 나서 [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) 메서드를 호출합니다. `Invoke` 호출에 실패하면 이 함수가 예외를 throw합니다. 반환되는 `IDispatch::Invoke` SCODE(상태 코드)가 DISP_E_EXCEPTION 경우 이 함수는 [COleException](../../mfc/reference/coleexception-class.md) 개체를 throw합니다. 그렇지 않으면 [COleDispatchException을](../../mfc/reference/coledispatchexception-class.md)throw합니다.

자세한 내용은 [VARIANTARG](/windows/win32/api/oaidl/ns-oaidl-variant), [IDispatch 인터페이스 구현](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface), [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)및 Windows SDK의 [COM 오류 코드 구조를](/windows/win32/com/structure-of-com-error-codes) 참조하십시오.

### <a name="example"></a>예제

  [COleDispatchDriver::CreateDispatch](#createdispatch)에 대한 예제를 참조하세요.

## <a name="coledispatchdriverm_bautorelease"></a><a name="m_bautorelease"></a>올레디스패치 드라이버::m_bAutoRelease

TRUE인 경우 [m_lpDispatch](#m_lpdispatch) 액세스하는 COM 개체는 [ReleaseDispatch가](#releasedispatch) 호출되거나 `COleDispatchDriver` 이 개체가 소멸될 때 자동으로 해제됩니다.

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>설명

기본적으로 생성자에서 TRUE로 `m_bAutoRelease` 설정됩니다.

COM 개체 릴리스에 대한 자세한 내용은 Windows SDK에서 참조 계산 및 [IUnknown:릴리스](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) [구현을](/windows/win32/com/implementing-reference-counting) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

## <a name="coledispatchdriverm_lpdispatch"></a><a name="m_lpdispatch"></a>올레디스패치 드라이버::m_lpDispatch

이 `COleDispatchDriver`에 `IDispatch` 연결된 인터페이스에 대한 포인터입니다.

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>설명

`m_lpDispatch` 데이터 멤버는 LPDispatch 형식의 공용 변수입니다.

자세한 내용은 Windows SDK의 [IDispatch를](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) 참조하십시오.

### <a name="example"></a>예제

  [COleDispatchDriver::AttachDispatch](#attachdispatch)에 대한 예제를 참조하십시오.

## <a name="coledispatchdriveroperator-"></a><a name="operator_eq"></a>COle디스패치 드라이버::연산자 =

소스 값을 개체에 `COleDispatchDriver` 복사합니다.

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>매개 변수

*dispatchSrc*<br/>
기존 `COleDispatchDriver` 개체에 대한 포인터입니다.

## <a name="coledispatchdriveroperator-lpdispatch"></a><a name="operator_lpdispatch"></a>COle디스패치드라이버::연산자 LP디스패치

개체의 기본 `IDispatch` 포인터에 `COleDispatchDriver` 액세스합니다.

```
operator LPDISPATCH();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

## <a name="coledispatchdriverreleasedispatch"></a><a name="releasedispatch"></a>올레디스패치드라이버:릴리스디스패치

연결을 `IDispatch` 해제합니다. 자세한 내용은 [IDispatch 인터페이스 구현을](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) 참조하십시오.

```cpp
void ReleaseDispatch();
```

### <a name="remarks"></a>설명

이 연결에 대해 자동 릴리스가 설정된 `IDispatch::Release` 경우 이 함수는 인터페이스를 해제하기 전에 호출합니다.

### <a name="example"></a>예제

  [COleDispatchDriver::AttachDispatch](#attachdispatch)에 대한 예제를 참조하십시오.

## <a name="coledispatchdriversetproperty"></a><a name="setproperty"></a>올레디스패치 드라이버::설정 속성

*dwDispID로*지정된 OLE 개체 속성을 설정합니다.

```cpp
void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
설정할 속성을 확인합니다.

*vtProp*<br/>
설정할 속성의 유형을 지정합니다. 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](#invokehelper)의 설명 섹션을 참조하세요.

*...*<br/>
*vtProp에*의해 지정된 형식의 단일 매개 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)
