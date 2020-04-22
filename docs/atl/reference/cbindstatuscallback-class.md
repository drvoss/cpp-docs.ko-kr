---
title: CBindStatusCallback 클래스
ms.date: 11/04/2016
f1_keywords:
- CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::Download
- ATLCTL/ATL::CBindStatusCallback::GetBindInfo
- ATLCTL/ATL::CBindStatusCallback::GetPriority
- ATLCTL/ATL::CBindStatusCallback::OnDataAvailable
- ATLCTL/ATL::CBindStatusCallback::OnLowResource
- ATLCTL/ATL::CBindStatusCallback::OnObjectAvailable
- ATLCTL/ATL::CBindStatusCallback::OnProgress
- ATLCTL/ATL::CBindStatusCallback::OnStartBinding
- ATLCTL/ATL::CBindStatusCallback::OnStopBinding
- ATLCTL/ATL::CBindStatusCallback::StartAsyncDownload
- ATLCTL/ATL::CBindStatusCallback::m_dwAvailableToRead
- ATLCTL/ATL::CBindStatusCallback::m_dwTotalRead
- ATLCTL/ATL::CBindStatusCallback::m_pFunc
- ATLCTL/ATL::CBindStatusCallback::m_pT
- ATLCTL/ATL::CBindStatusCallback::m_spBindCtx
- ATLCTL/ATL::CBindStatusCallback::m_spBinding
- ATLCTL/ATL::CBindStatusCallback::m_spMoniker
- ATLCTL/ATL::CBindStatusCallback::m_spStream
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
ms.openlocfilehash: 0ae7f4fcdba18be84d99140e395b6f2ac3db792a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748205"
---
# <a name="cbindstatuscallback-class"></a>CBindStatusCallback 클래스

이 클래스는 `IBindStatusCallback` 인터페이스를 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS | BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
데이터가 수신될 때 호출될 함수를 포함하는 클래스입니다.

*nBindFlags*<br/>
[GetBindInfo](#getbindinfo)에서 반환되는 바인딩 플래그를 지정합니다. 기본 구현은 바인딩을 비동기로 설정하고, 최신 버전의 데이터/개체를 검색하며, 검색된 데이터를 디스크 캐시에 저장하지 않습니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CBindStatus콜백::CBindStatus콜백](#cbindstatuscallback)|생성자입니다.|
|[CBindStatusCallback::~CBindStatusCallback](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CBindStatus콜백::D](#download)|다운로드 프로세스를 시작하고 개체를 `CBindStatusCallback` 만들고 호출하는 `StartAsyncDownload`정적 메서드입니다.|
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|만들 바인딩 유형에 대한 정보를 요청하기 위해 비동기 모니커에서 호출합니다.|
|[CBindStatus콜백::Get우선 순위](#getpriority)|바인드 작업의 우선 순위를 얻으려면 비동기 모니커에서 호출합니다. ATL 구현은 `E_NOTIMPL`을 반환합니다.|
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|사용할 수 있게 되면 응용 프로그램에 데이터를 제공하기 위해 호출됩니다. 데이터를 읽은 다음 전달된 함수를 호출하여 데이터를 사용합니다.|
|[CBindStatusCallback::OnLowResource](#onlowresource)|리소스가 부족할 때 호출됩니다. ATL 구현은 S_OK 반환합니다.|
|[CBindStatus콜백::온오브젝트 사용 가능](#onobjectavailable)|비동기 모니커에 의해 호출되어 개체 인터페이스 포인터를 응용 프로그램에 전달합니다. ATL 구현은 S_OK 반환합니다.|
|[CBindStatusCallback::OnProgress](#onprogress)|데이터 다운로드 프로세스의 진행 률을 나타내기 위해 호출됩니다. ATL 구현은 S_OK 반환합니다.|
|[CBindStatus호출::시작 바인딩](#onstartbinding)|바인딩이 시작될 때 호출됩니다.|
|[CBindStatus콜백::온스톱 바인딩](#onstopbinding)|비동기 데이터 전송이 중지될 때 호출됩니다.|
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|사용 가능한 바이트를 초기화하고 바이트를 0으로 읽고 URL에서 푸시 형식 스트림 `OnDataAvailable` 개체를 만들고 데이터를 사용할 수 있는 때마다 호출합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CBindStatus콜백::m_dwAvailableToRead](#m_dwavailabletoread)|읽을 수 있는 바이트 수입니다.|
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|읽은 총 바이트 수입니다.|
|[CBindStatus콜백::m_pFunc](#m_pfunc)|데이터를 사용할 수 있을 때 호출되는 함수에 대한 포인터입니다.|
|[CBindStatusCallback::m_pT](#m_pt)|비동기 데이터 전송을 요청하는 개체에 대한 포인터입니다.|
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|현재 바인드 작업에 대한 [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) 인터페이스에 대한 포인터입니다.|
|[CBindStatus콜백::m_spBinding](#m_spbinding)|현재 바인드 작업에 대한 `IBinding` 인터페이스에 대한 포인터입니다.|
|[CBindStatus콜백::m_spMoniker](#m_spmoniker)|사용할 URL에 대한 [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) 인터페이스에 대한 포인터입니다.|
|[CBindStatusCallback::m_spStream](#m_spstream)|데이터 전송을 위한 [IStream](/windows/win32/api/objidl/nn-objidl-istream) 인터페이스에 대한 포인터입니다.|

## <a name="remarks"></a>설명

`CBindStatusCallback` 클래스가 `IBindStatusCallback` 인터페이스를 구현합니다. `IBindStatusCallback`비동기 데이터 전송에서 알림을 받을 수 있도록 응용 프로그램에서 구현해야 합니다. 시스템에서 제공하는 비동기 모니커는 메서드를 `IBindStatusCallback` 사용하여 개체와 및 개체에서 전송되는 비동기 데이터 전송에 대한 정보를 보내고 받습니다.

일반적으로 `CBindStatusCallback` 개체는 특정 바인딩 작업과 연결됩니다. 예를 들어 [ASYNC](../../overview/visual-cpp-samples.md) 샘플에서 URL 속성을 설정할 때 `CBindStatusCallback` `Download`다음을 호출할 때 개체가 만들어집니다.

[!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]

비동기 모니커는 콜백 함수를 `OnData` 사용하여 데이터가 있을 때 응용 프로그램을 호출합니다. 비동기 모니커는 시스템에서 제공됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

`IBindStatusCallback`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`CBindStatusCallback`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="cbindstatuscallbackcbindstatuscallback"></a><a name="cbindstatuscallback"></a>CBindStatus콜백::CBindStatus콜백

생성자입니다.

```
CBindStatusCallback();
```

### <a name="remarks"></a>설명

비동기 데이터 전송에 관한 알림을 받을 개체를 만듭니다. 일반적으로 각 바인드 작업에 대해 하나의 개체가 만들어집니다.

생성자는 [또한 m_pT](#m_pt) 초기화하고 null로 [m_pFunc.](#m_pfunc)

## <a name="cbindstatuscallbackcbindstatuscallback"></a><a name="dtor"></a>CBindStatus콜백::~CBindStatus콜백

소멸자입니다.

```
~CBindStatusCallback();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제합니다.

## <a name="cbindstatuscallbackdownload"></a><a name="download"></a>CBindStatus콜백::D

지정된 `CBindStatusCallback` URL에서 `StartAsyncDownload` 비동기적으로 데이터 다운로드를 시작하도록 개체 및 호출을 만듭니다.

```
static HRESULT Download(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>매개 변수

*Pt*<br/>
【인】 비동기 데이터 전송을 요청하는 개체에 대한 포인터입니다. 개체는 `CBindStatusCallback` 이 개체의 클래스에서 템플릿화됩니다.

*pFunc*<br/>
【인】 읽은 데이터를 수신하는 함수에 대한 포인터입니다. 함수는 개체의 형식 `T`클래스의 멤버입니다. 구문 및 예제는 [StartAsync다운로드를](#startasyncdownload) 참조하십시오.

*bstrURL*<br/>
【인】 데이터를 가져오는 URL입니다. 유효한 URL 또는 파일 이름일 수 있습니다. NULL이 될 수 없습니다. 다음은 그 예입니다.

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
【인】 컨테이너의 입니다. `IUnknown` 기본적으로 NULL입니다.

*bRelative*<br/>
【인】 URL이 상대적인지 절대인지를 나타내는 플래그입니다. 기본적으로 FALSE는 URL이 절대적임을 의미합니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

데이터를 사용할 수 있는 때마다 을 `OnDataAvailable`통해 개체로 전송됩니다. `OnDataAvailable`데이터를 읽고 *pFunc가* 가리키는 함수를 호출합니다(예: 데이터를 저장하거나 화면에 인쇄).

## <a name="cbindstatuscallbackgetbindinfo"></a><a name="getbindinfo"></a>CBindStatus콜백::겟빈인정보

어떻게 바인딩하는 방법을 모니커를 알려줍니다.

```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```

### <a name="parameters"></a>매개 변수

*pgrfBSCF*<br/>
【아웃】 BINDF 열거 형 값에 대한 포인터는 바인드 작업이 발생하는 방법을 나타냅니다. 기본적으로 다음과 같은 열거 값을 사용 하 여 설정 합니다.

BINDF_ASYNCHRONOUS 비동기 다운로드.

BINDF_ASYNCSTORAGE `OnDataAvailable` 데이터를 사용할 수 있을 때까지 차단하는 대신 아직 데이터를 사용할 수 없는 E_PENDING 반환합니다.

BINDF_GETNEWESTVERSION 바인딩 작업은 데이터의 최신 버전을 검색해야 합니다.

BINDF_NOWRITECACHE 바인딩 작업은 검색된 데이터를 디스크 캐시에 저장하지 않아야 합니다.

*pbindinfo*<br/>
【인, 아웃】 개체가 바인딩을 `BINDINFO` 수행하려는 방법에 대한 자세한 정보를 제공하는 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

기본 구현은 바인딩을 비동기로 설정하고 데이터 푸시 모델을 사용합니다. 데이터 푸시 모델에서 모니커는 비동기 바인딩 작업을 구동하고 새 데이터를 사용할 수 있게 될 때마다 클라이언트에 지속적으로 알린다.

## <a name="cbindstatuscallbackgetpriority"></a><a name="getpriority"></a>CBindStatus콜백::Get우선 순위

바인드 작업의 우선 순위를 얻으려면 비동기 모니커에서 호출합니다.

```
STDMETHOD(GetPriority)(LONG* pnPriority);
```

### <a name="parameters"></a>매개 변수

*pnPriority*<br/>
【아웃】 성공 시 우선 순위를 받는 **LONG** 변수의 주소입니다.

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

## <a name="cbindstatuscallbackm_dwavailabletoread"></a><a name="m_dwavailabletoread"></a>CBindStatus콜백::m_dwAvailableToRead

읽을 수 있는 바이트 수를 저장하는 데 사용할 수 있습니다.

```
DWORD m_dwAvailableToRead;
```

### <a name="remarks"></a>설명

에서 `StartAsyncDownload`0으로 초기화됩니다.

## <a name="cbindstatuscallbackm_dwtotalread"></a><a name="m_dwtotalread"></a>CBindStatus콜백::m_dwTotalRead

비동기 데이터 전송에서 읽은 누적 바이트 합계입니다.

```
DWORD m_dwTotalRead;
```

### <a name="remarks"></a>설명

매번 `OnDataAvailable` 증분되는 것은 실제로 읽은 바이트 수에 의해 호출됩니다. 에서 `StartAsyncDownload`0으로 초기화됩니다.

## <a name="cbindstatuscallbackm_pfunc"></a><a name="m_pfunc"></a>CBindStatus콜백::m_pFunc

가리키는 `m_pFunc` 함수는 사용 가능한 `OnDataAvailable` 데이터를 읽은 후 호출됩니다(예: 데이터를 저장하거나 화면에 인쇄).

```
ATL_PDATAAVAILABLE m_pFunc;
```

### <a name="remarks"></a>설명

가리키는 `m_pFunc` 함수는 개체 클래스의 멤버이며 다음과 같은 구문이 있습니다.

```cpp
void Function_Name(
   CBindStatusCallback<T>* pbsc,
   BYTE* pBytes,
   DWORD dwSize
   );
```

## <a name="cbindstatuscallbackm_pt"></a><a name="m_pt"></a>CBindStatus콜백::m_pT

비동기 데이터 전송을 요청하는 개체에 대한 포인터입니다.

```
T* m_pT;
```

### <a name="remarks"></a>설명

개체는 `CBindStatusCallback` 이 개체의 클래스에서 템플릿화됩니다.

## <a name="cbindstatuscallbackm_spbindctx"></a><a name="m_spbindctx"></a>CBindStatus콜백::m_spBindCtx

바인딩 컨텍스트(특정 모니커 바인딩 작업에 대한 정보를 저장하는 개체)에 대한 액세스를 제공하는 [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) 인터페이스에 대한 포인터입니다.

```
CComPtr<IBindCtx> m_spBindCtx;
```

### <a name="remarks"></a>설명

에서 `StartAsyncDownload`초기화됩니다.

## <a name="cbindstatuscallbackm_spbinding"></a><a name="m_spbinding"></a>CBindStatus콜백::m_spBinding

현재 바인딩 `IBinding` 작업의 인터페이스에 대한 포인터입니다.

```
CComPtr<IBinding> m_spBinding;
```

### <a name="remarks"></a>설명

에서 `OnStartBinding` 초기화되고 `OnStopBinding`출시됩니다.

## <a name="cbindstatuscallbackm_spmoniker"></a><a name="m_spmoniker"></a>CBindStatus콜백::m_spMoniker

사용할 URL에 대한 [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) 인터페이스에 대한 포인터입니다.

```
CComPtr<IMoniker> m_spMoniker;
```

### <a name="remarks"></a>설명

에서 `StartAsyncDownload`초기화됩니다.

## <a name="cbindstatuscallbackm_spstream"></a><a name="m_spstream"></a>CBindStatus콜백::m_spStream

현재 바인드 작업의 [IStream](/windows/win32/api/objidl/nn-objidl-istream) 인터페이스에 대한 포인터입니다.

```
CComPtr<IStream> m_spStream;
```

### <a name="remarks"></a>설명

BCSF `OnDataAvailable` 플래그가 BCSF_FIRSTDATANOTIFICATION 때 구조에서 초기화되고 BCSF 플래그가 `STGMEDIUM` BCSF_LASTDATANOTIFICATION 때 해제됩니다.

## <a name="cbindstatuscallbackondataavailable"></a><a name="ondataavailable"></a>CBindStatus콜백::온데이터 사용 가능

시스템에서 제공된 비동기 모니커 호출을 `OnDataAvailable` 사용하여 개체가 사용 가능해지면 개체에 데이터를 제공합니다.

```
STDMETHOD(
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```

### <a name="parameters"></a>매개 변수

*grfBSCF*<br/>
【인】 BSCF 열거 값입니다. 다음 중 하나 이상: BSCF_FIRSTDATANOTIFICATION, BSCF_INTERMEDIARYDATANOTIFICATION 또는 BSCF_LASTDATANOTIFICATION.

*dwSize*<br/>
【인】 바인딩이 시작된 이후 사용 가능한 데이터의 누적 금액(바이트 단위)입니다. 데이터 양이 관련이 없거나 특정 양이 사용 가능하지 않음을 나타내는 0일 수 있습니다.

*pformatetc*<br/>
【인】 사용 가능한 데이터의 형식을 포함하는 [FORMATETC](/windows/win32/com/the-formatetc-structure) 구조에 대한 포인터입니다. 형식이 없는 경우 CF_NULL 수 있습니다.

*pstgmed*<br/>
【인】 현재 사용 가능한 실제 데이터를 보유하는 [STGMEDIUM](/windows/win32/com/the-stgmedium-structure) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

`OnDataAvailable`데이터를 읽은 다음 개체 클래스의 메서드를 호출합니다(예: 데이터를 저장하거나 화면에 인쇄). [참조 CBindStatusCallback::StartAsync자세한](#startasyncdownload) 내용은 다운로드.

## <a name="cbindstatuscallbackonlowresource"></a><a name="onlowresource"></a>CBindStatus콜백::온로우리소스

리소스가 부족할 때 호출됩니다.

```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```

### <a name="parameters"></a>매개 변수

*dwReserved*<br/>
예약되어 있습니다.

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

## <a name="cbindstatuscallbackonobjectavailable"></a><a name="onobjectavailable"></a>CBindStatus콜백::온오브젝트 사용 가능

비동기 모니커에 의해 호출되어 개체 인터페이스 포인터를 응용 프로그램에 전달합니다.

```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
요청된 인터페이스의 인터페이스 식별자입니다. 사용되지 않습니다.

*펑크*<br/>
I알 수 없는 인터페이스의 주소입니다. 사용되지 않습니다.

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

## <a name="cbindstatuscallbackonprogress"></a><a name="onprogress"></a>CBindStatus콜백::진행 중

데이터 다운로드 프로세스의 진행 률을 나타내기 위해 호출됩니다.

```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```

### <a name="parameters"></a>매개 변수

*ulProgress*<br/>
서명되지 않은 긴 정수입니다. 사용되지 않습니다.

*ulProgressMax*<br/>
서명되지 않은 긴 정수 미사용.

*ulStatusCode*<br/>
서명되지 않은 긴 정수입니다. 사용되지 않습니다.

*szStatusText*<br/>
문자열 값의 주소입니다. 사용되지 않습니다.

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

## <a name="cbindstatuscallbackonstartbinding"></a><a name="onstartbinding"></a>CBindStatus호출::시작 바인딩

[M_spBinding](#m_spbinding) 데이터 멤버를 *pbinding*의 `IBinding`포인터로 설정합니다.

```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```

### <a name="parameters"></a>매개 변수

*dwReserved*<br/>
다음에 사용하도록 예약됩니다.

*pBinding*<br/>
【인】 현재 바인드 작업의 IBinding 인터페이스의 주소입니다. NULL이 될 수 없습니다. 클라이언트는 바인딩 개체에 대한 참조를 유지하기 위해 이 포인터에서 AddRef를 호출해야 합니다.

## <a name="cbindstatuscallbackonstopbinding"></a><a name="onstopbinding"></a>CBindStatus콜백::온스톱 바인딩

m_spBinding `IBinding` 데이터 [멤버에서](#m_spbinding)포인터를 해제합니다.

```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```

### <a name="parameters"></a>매개 변수

*Hresult*<br/>
바인딩 작업에서 반환된 상태 코드입니다.

*szError*<br/>
문자열 값의 주소입니다. 사용되지 않습니다.

### <a name="remarks"></a>설명

바인딩 작업의 끝을 나타내기 위해 시스템에서 제공하는 비동기 모니커에서 호출합니다.

## <a name="cbindstatuscallbackstartasyncdownload"></a><a name="startasyncdownload"></a>CBindStatus콜백::시작동기다운로드

지정된 URL에서 비동기적으로 데이터 다운로드를 시작합니다.

```
HRESULT StartAsyncDownload(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>매개 변수

*Pt*<br/>
【인】 비동기 데이터 전송을 요청하는 개체에 대한 포인터입니다. 개체는 `CBindStatusCallback` 이 개체의 클래스에서 템플릿화됩니다.

*pFunc*<br/>
【인】 읽히는 데이터를 수신하는 함수에 대한 포인터입니다. 함수는 개체의 형식 `T`클래스의 멤버입니다. 구문 및 예제는 **비고를** 참조하십시오.

*bstrURL*<br/>
【인】 데이터를 가져오는 URL입니다. 유효한 URL 또는 파일 이름일 수 있습니다. NULL이 될 수 없습니다. 다음은 그 예입니다.

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
【인】 컨테이너의 입니다. `IUnknown` 기본적으로 NULL입니다.

*bRelative*<br/>
【인】 URL이 상대적인지 절대인지를 나타내는 플래그입니다. 기본적으로 FALSE는 URL이 절대적임을 의미합니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

데이터를 사용할 수 있는 때마다 을 `OnDataAvailable`통해 개체로 전송됩니다. `OnDataAvailable`데이터를 읽고 *pFunc가* 가리키는 함수를 호출합니다(예: 데이터를 저장하거나 화면에 인쇄).

*pFunc가* 가리키는 함수는 개체 클래스의 구성원이며 다음과 같은 구문이 있습니다.

```cpp
void Function_Name(
    CBindStatusCallback<T>* pbsc,
    BYTE* pBytes,
    DWORD dwSize);
```

다음 [예제(ASYNC](../../overview/visual-cpp-samples.md) 샘플에서 가져온)에서 `OnData` 함수는 수신된 데이터를 텍스트 상자에 씁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)
