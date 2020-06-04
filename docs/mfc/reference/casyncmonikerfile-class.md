---
title: CAsync모니커파일 클래스
ms.date: 11/04/2016
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
helpviewer_keywords:
- CAsyncMonikerFile [MFC], CAsyncMonikerFile
- CAsyncMonikerFile [MFC], Close
- CAsyncMonikerFile [MFC], GetBinding
- CAsyncMonikerFile [MFC], GetFormatEtc
- CAsyncMonikerFile [MFC], Open
- CAsyncMonikerFile [MFC], CreateBindStatusCallback
- CAsyncMonikerFile [MFC], GetBindInfo
- CAsyncMonikerFile [MFC], GetPriority
- CAsyncMonikerFile [MFC], OnDataAvailable
- CAsyncMonikerFile [MFC], OnLowResource
- CAsyncMonikerFile [MFC], OnProgress
- CAsyncMonikerFile [MFC], OnStartBinding
- CAsyncMonikerFile [MFC], OnStopBinding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
ms.openlocfilehash: 57ab463445f249b4e9393f19af103b7588962d5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377003"
---
# <a name="casyncmonikerfile-class"></a>CAsync모니커파일 클래스

ActiveX 컨트롤(이전의 OLE 컨트롤)에서 비동기 모니커를 사용할 수 있도록 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CAsyncMonikerFile : public CMonikerFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAsyncMoniker파일::CAsync모니커파일](#casyncmonikerfile)|`CAsyncMonikerFile` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAsyncMoniker파일::닫기](#close)|모든 리소스를 닫고 해제합니다.|
|[CAsync모니커파일::Getbinding](#getbinding)|비동기 전송 바인딩에 대한 포인터를 검색합니다.|
|[CAsyncMoniker파일::GetFormatEtc](#getformatetc)|스트림에서 데이터의 형식을 검색합니다.|
|[CAsync모니커파일::열기](#open)|비동기적으로 파일을 엽니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CAsyncMoniker파일:만들기빈빈상태콜백](#createbindstatuscallback)|을 구현하는 COM 개체를 `IBindStatusCallback`만듭니다.|
|[CAsync모니커파일::GetBindInfo](#getbindinfo)|만들 바인딩 유형에 대한 정보를 요청하기 위해 OLE 시스템 라이브러리에서 호출합니다.|
|[CAsyncMoniker파일::Get우선 순위](#getpriority)|바인딩의 우선 순위를 얻으려면 OLE 시스템 라이브러리에서 호출합니다.|
|[CAsyncMoniker파일::온데이터 사용 가능](#ondataavailable)|비동기 바인딩 작업 중에 클라이언트에서 사용할 수 있게 되면 데이터를 제공하기 위해 호출됩니다.|
|[CAsyncMoniker파일::온로우리소스](#onlowresource)|리소스가 부족할 때 호출됩니다.|
|[CAsync모니커파일::진행 중](#onprogress)|데이터 다운로드 프로세스의 진행 률을 나타내기 위해 호출됩니다.|
|[CAsyncMonikerFile::시작 바인딩](#onstartbinding)|바인딩이 시작될 때 호출됩니다.|
|[CAsync모니커파일::온스톱 바인딩](#onstopbinding)|비동기 전송이 중지될 때 호출됩니다.|

## <a name="remarks"></a>설명

COleStreamFile에서 파생되는 [CMonikerFile에서](../../mfc/reference/cmonikerfile-class.md) [COleStreamFile](../../mfc/reference/colestreamfile-class.md)파생된 [IMoniker 인터페이스는 IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) 인터페이스를 `CAsyncMonikerFile` 사용하여 URL에서 비동기적으로 파일을 로드하는 등 비동기적으로 모든 데이터 스트림에 액세스합니다. 파일은 ActiveX 컨트롤의 데이터 경로 속성일 수 있습니다.

비동기 모니커는 주로 인터넷 지원 응용 프로그램 및 ActiveX 컨트롤에서 파일 전송 중에 응답 가능한 사용자 인터페이스를 제공하는 데 사용됩니다. 대표적인 예로 [CDataPathProperty를](../../mfc/reference/cdatapathproperty-class.md) 사용하여 ActiveX 컨트롤에 대한 비동기 속성을 제공합니다. 개체는 `CDataPathProperty` 긴 속성 교환 프로세스 중에 새 데이터의 가용성을 나타내는 콜백을 반복적으로 가져옵니다.

인터넷 응용 프로그램에서 비동기 모니커 및 ActiveX 컨트롤을 사용하는 방법에 대한 자세한 내용은 다음 문서를 참조하십시오.

- [인터넷 첫 번째 단계: 비동기 모니커](../../mfc/asynchronous-monikers-on-the-internet.md)

- [인터넷 첫 번째 단계: 액티브X 컨트롤](../../mfc/activex-controls-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

`CAsyncMonikerFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="casyncmonikerfilecasyncmonikerfile"></a><a name="casyncmonikerfile"></a>CAsyncMoniker파일::CAsync모니커파일

`CAsyncMonikerFile` 개체를 생성합니다.

```
CAsyncMonikerFile();
```

### <a name="remarks"></a>설명

인터페이스를 `IBindHost` 만들지 않습니다. `IBindHost``Open` 은 멤버 함수에서 제공하는 경우에만 사용됩니다.

인터페이스에 `IBindHost` 대한 설명은 Windows SDK를 참조하십시오.

## <a name="casyncmonikerfileclose"></a><a name="close"></a>CAsyncMoniker파일::닫기

이 함수를 호출하여 모든 리소스를 닫고 해제합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

미개봉 또는 이미 닫힌 파일에서 호출할 수 있습니다.

## <a name="casyncmonikerfilecreatebindstatuscallback"></a><a name="createbindstatuscallback"></a>CAsyncMoniker파일:만들기빈빈상태콜백

을 구현하는 COM 개체를 `IBindStatusCallback`만듭니다.

```
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```

### <a name="parameters"></a>매개 변수

*펀크 제어*<br/>
집계가 사용되지 않는 경우 `IUnknown`제어 알 수 없는(외부) 또는 NULL에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

*pUnk컨트롤이* NULL이 아닌 경우 함수는 을 `IUnknown` 지원하는 새 COM `IBindStatusCallback`개체의 내부포인터를 반환합니다. NULL인 경우 `pUnkControlling` 함수는 을 지원하는 `IUnknown` 새 COM 개체에 `IBindStatusCallback`대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

`CAsyncMonikerFile`을 구현하는 COM 개체가 필요합니다. `IBindStatusCallback` MFC는 이러한 개체를 구현하며 집계할 수 있습니다. 사용자 고유의 `CreateBindStatusCallback` COM 개체를 반환하도록 재정의할 수 있습니다. COM 개체는 COM 개체에 대해 `CreateBindStatusCallback` 알 수 없는 제어 를 호출하여 MFC의 구현을 집계할 수 있습니다. `CCmdTarget` COM 지원을 사용하여 구현된 COM 개체는 `CCmdTarget::GetControllingUnknown`을 사용하여 알 수 없는 제어를 검색할 수 있습니다.

또는 COM 개체를 호출하여 `CreateBindStatusCallback( NULL )`MFC의 구현에 위임할 수 있습니다.

[CAsyncMonikerFile::열기](#open) `CreateBindStatusCallback`호출 .

비동기 모니커 및 비동기 바인딩에 대한 자세한 내용은 [IBindStatusCallback](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775060\(v=vs.85\)) 인터페이스 및 [비동기 바인딩 및 저장소 작업 방법을](/windows/win32/Stg/how-asynchronous-binding-and-storage-work)참조하십시오. 집계에 대한 설명은 [집계](/windows/win32/com/aggregation)를 참조하십시오. 세 가지 항목 모두 Windows SDK에 있습니다.

## <a name="casyncmonikerfilegetbindinfo"></a><a name="getbindinfo"></a>CAsync모니커파일::GetBindInfo

비동기 모니커의 클라이언트에서 호출되어 비동기 모니커에게 바인딩방법을 알려줍니다.

```
virtual DWORD GetBindInfo() const;
```

### <a name="return-value"></a>Return Value

에 대한 `IBindStatusCallBack`설정을 검색합니다. 인터페이스에 `IBindStatusCallback` 대한 설명은 Windows SDK를 참조하십시오.

### <a name="remarks"></a>설명

기본 구현은 바인딩을 비동기로 설정하고, 저장소 매체(스트림)를 사용하고, 데이터 푸시 모델을 사용하도록 설정합니다. 바인딩의 동작을 변경하려는 경우 이 함수를 재정의합니다.

이렇게 하는 한 가지 이유는 데이터 푸시 모델 대신 데이터 풀 모델을 사용하여 바인딩하는 것입니다. 데이터 끌어오기 모델에서 클라이언트는 바인드 작업을 구동하고 모니커는 데이터를 읽을 때만 클라이언트에 데이터를 제공합니다. 데이터 푸시 모델에서 모니커는 비동기 바인딩 작업을 구동하고 새 데이터를 사용할 수 있게 될 때마다 클라이언트에 지속적으로 알린다.

## <a name="casyncmonikerfilegetbinding"></a><a name="getbinding"></a>CAsync모니커파일::Getbinding

이 함수를 호출하여 비동기 전송 바인딩에 대한 포인터를 검색합니다.

```
IBinding* GetBinding() const;
```

### <a name="return-value"></a>Return Value

비동기 전송이 `IBinding` 시작될 때 제공된 인터페이스에 대한 포인터입니다. 어떤 이유로든 전송을 비동기적으로 만들 수 없는 경우 NULL을 반환합니다.

### <a name="remarks"></a>설명

이렇게 하면 `IBinding` 인터페이스를 통해 데이터 전송 프로세스를 제어할 수 있습니다(예: `IBinding::Abort`" 및 `IBinding::Pause`) `IBinding::Resume`

인터페이스에 `IBinding` 대한 설명은 Windows SDK를 참조하십시오.

## <a name="casyncmonikerfilegetformatetc"></a><a name="getformatetc"></a>CAsyncMoniker파일::GetFormatEtc

이 함수를 호출하여 스트림에서 데이터의 형식을 검색합니다.

```
FORMATETC* GetFormatEtc() const;
```

### <a name="return-value"></a>Return Value

현재 열려 있는 스트림에 대한 Windows 구조 [FORMATETC에](/windows/win32/api/objidl/ns-objidl-formatetc) 대한 포인터입니다. 모니커가 바인딩되지 않았거나 비동기 작업이 시작되지 않은 경우 NULL을 반환합니다.

## <a name="casyncmonikerfilegetpriority"></a><a name="getpriority"></a>CAsyncMoniker파일::Get우선 순위

바인딩 프로세스가 바인딩 작업에 대해 스레드에 지정된 우선 순위를 수신하기 시작할 때 비동기 모니커의 클라이언트에서 호출됩니다.

```
virtual LONG GetPriority() const;
```

### <a name="return-value"></a>Return Value

비동기 전송이 수행되는 우선 순위입니다. 표준 스레드 우선 순위 플래그 중 하나: THREAD_PRIORITY_ABOVE_NORMAL, THREAD_PRIORITY_BELOW_NORMAL, THREAD_PRIORITY_HIGHEST, THREAD_PRIORITY_IDLE, THREAD_PRIORITY_LOWEST, THREAD_PRIORITY_NORMAL 및 THREAD_PRIORITY_TIME_CRITICAL. 이러한 값에 대한 설명은 Windows 기능 [SetThreadPriority를](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) 참조하십시오.

### <a name="remarks"></a>설명

`GetPriority` 해야 하지 직접 호출할 수 있습니다. THREAD_PRIORITY_NORMAL 기본 구현에 의해 반환 됩니다.

## <a name="casyncmonikerfileondataavailable"></a><a name="ondataavailable"></a>CAsyncMoniker파일::온데이터 사용 가능

비동기 모니커는 비동기 `OnDataAvailable` 바인딩 작업 중에 사용할 수 있게 되면 클라이언트에 데이터를 제공하기 위해 호출합니다.

```
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```

### <a name="parameters"></a>매개 변수

*dwSize*<br/>
바인딩이 시작된 이후 사용 가능한 데이터의 누적 금액(바이트 단위)입니다. 데이터 양이 작업과 관련이 없거나 특정 양을 사용할 수 없음을 나타내는 0일 수 있습니다.

*bscfFlag*<br/>
BSCF 열거 값입니다. 다음 값 중 하나 이상이 될 수 있습니다.

- BSCF_FIRSTDATANOTIFICATION 지정된 바인드 `OnDataAvailable` 작업에 대한 첫 번째 호출을 식별합니다.

- BSCF_INTERMEDIATEDATANOTIFICATION 바인딩 작업에 `OnDataAvailable` 대한 중간 호출을 식별합니다.

- BSCF_LASTDATANOTIFICATION 바인딩 작업에 `OnDataAvailable` 대한 마지막 호출을 식별합니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 샘플 구현은 다음 예제를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]

## <a name="casyncmonikerfileonlowresource"></a><a name="onlowresource"></a>CAsyncMoniker파일::온로우리소스

리소스가 부족할 때 모니커에서 호출합니다.

```
virtual void OnLowResource();
```

### <a name="remarks"></a>설명

기본 구현은 `GetBinding( )-> Abort( )`을 호출합니다.

## <a name="casyncmonikerfileonprogress"></a><a name="onprogress"></a>CAsync모니커파일::진행 중

일반적으로 긴 작업 중에 적절한 간격으로 이 바인드 작업의 현재 진행 률을 나타내기 위해 모니커에 의해 반복적으로 호출됩니다.

```
virtual void OnProgress(
    ULONG ulProgress,
    ULONG ulProgressMax,
    ULONG ulStatusCode,
    LPCTSTR szStatusText);
```

### <a name="parameters"></a>매개 변수

*ulProgress*<br/>
*ulProgressMax에*표시된 예상 최대값을 기준으로 바인드 작업의 현재 진행률을 나타냅니다.

*ulProgressMax*<br/>
이 작업에 대한 호출 `OnProgress` 기간 동안 *ulProgress의* 예상 최대값을 나타냅니다.

*ulStatusCode*<br/>
바인드 작업의 진행률에 대한 추가 정보를 제공합니다. 유효한 값은 열거형에서 `BINDSTATUS` 가져온 것입니다. 가능한 값은 비고를 참조하십시오.

*szStatusText*<br/>
*ulStatusCode의*값에 따라 현재 진행률에 대한 정보 . 가능한 값은 비고를 참조하십시오.

### <a name="remarks"></a>설명

*ulStatusCode* (및 각 값에 대한 *szStatusText)에* 대한 가능한 값은 다음과 같습니다.

|||
|-|-|
|BINDSTATUS_FINDINGRESOURCE  |바인딩 작업은 바인딩되는 개체 또는 저장소를 보유하는 리소스를 찾는 것입니다. *szStatusText는* 검색 중인 리소스의 표시 이름(예: "www.microsoft.com")을 제공합니다.  |
|BINDSTATUS_CONNECTING  |바인딩 작업이 바인딩되는 개체 또는 저장소를 보유하는 리소스에 연결됩니다. *szStatusText는* 연결된 리소스의 표시 이름(예: IP 주소)을 제공합니다.  |
|BINDSTATUS_SENDINGREQUEST|바인딩 작업이 바인딩되는 개체 또는 저장소를 요청하고 있습니다. *szStatusText는* 개체의 표시 이름(예: 파일 이름)을 제공합니다.|
|BINDSTATUS_REDIRECTING  |바인드 작업이 다른 데이터 위치로 리디렉션되었습니다. *szStatusText는* 새 데이터 위치의 표시 이름을 제공합니다.  |
|BINDSTATUS_USINGCACHEDCOPY  |바인딩 작업이 캐시된 복사본에서 요청된 개체 또는 저장소를 검색하는 것입니다. *szStatusText는* NULL입니다.  |
|BINDSTATUS_BEGINDOWNLOADDATA  |바인딩 작업이 바인딩되는 개체 또는 저장소를 받기 시작했습니다. *szStatusText는* 데이터 위치의 표시 이름을 제공합니다.|
|BINDSTATUS_DOWNLOADINGDATA  |바인딩 작업은 바인딩되는 개체 또는 저장소를 계속 받습니다. *szStatusText는* 데이터 위치의 표시 이름을 제공합니다.  |
|BINDSTATUS_ENDDOWNLOADDATA  |바인딩 작업이 바인딩되는 개체 또는 저장소 수신을 완료했습니다. *szStatusText는* 데이터 위치의 표시 이름을 제공합니다.  |
|BINDSTATUS_CLASSIDAVAILABLE  |바인딩되는 개체의 인스턴스가 만들어지기 직전입니다. *szStatusText는* 새 개체의 CLSID를 문자열 형식으로 제공하므로 원하는 경우 클라이언트가 바인드 작업을 취소할 수 있습니다.  |

## <a name="casyncmonikerfileonstartbinding"></a><a name="onstartbinding"></a>CAsyncMonikerFile::시작 바인딩

바인딩이 시작될 때 작업을 수행하도록 파생 된 클래스에서이 함수를 재정의합니다.

```
virtual void OnStartBinding();
```

### <a name="remarks"></a>설명

이 함수는 모니커에 의해 다시 호출됩니다. 기본 구현은 아무 작업도 수행하지 않습니다.

## <a name="casyncmonikerfileonstopbinding"></a><a name="onstopbinding"></a>CAsync모니커파일::온스톱 바인딩

바인딩 작업의 끝에 모니커에 의해 호출 됩니다.

```
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```

### <a name="parameters"></a>매개 변수

*Hresult*<br/>
오류 또는 경고 값인 HRESULT입니다.

*szErrort*<br/>
오류를 설명하는 문자열입니다.

### <a name="remarks"></a>설명

전송이 중지될 때 작업을 수행하도록 이 함수를 재정의합니다. 기본적으로 함수는 을 `IBinding`해제합니다.

인터페이스에 `IBinding` 대한 설명은 Windows SDK를 참조하십시오.

## <a name="casyncmonikerfileopen"></a><a name="open"></a>CAsync모니커파일::열기

이 멤버 함수를 호출하여 비동기적으로 파일을 엽니다.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszURL*<br/>
비동기적으로 열 수 있는 파일에 대한 포인터입니다. 파일은 유효한 URL 또는 파일 이름일 수 있습니다.

*pError*<br/>
파일 예외에 대한 포인터입니다. 오류가 발생하면 원인으로 설정됩니다.

*프모니커 (것)와 함께*<br/>
비동기 모니커 인터페이스에 `IMoniker`대한 포인터, 검색할 수 `IOleClientSite::GetMoniker(OLEWHICHMK_CONTAINER)`있는 문서 자체 모니커와 경로 이름에서 만든 모니커의 조합인 정확한 모니커입니다. 컨트롤은 이 모니커를 사용하여 바인딩할 수 있지만 컨트롤이 저장해야 하는 모니커가 아닙니다.

*pBind호스트*<br/>
잠재적으로 상대적인 `IBindHost` 경로 이름에서 모니커를 만드는 데 사용할 인터페이스에 대한 포인터입니다. 바인드 호스트가 유효하지 않거나 모니커를 제공하지 않는 경우 `Open(lpszFileName,pError)`호출은 기본값입니다. 인터페이스에 `IBindHost` 대한 설명은 Windows SDK를 참조하십시오.

*p서비스공급자*<br/>
관리되지 않는 개체의 `IServiceProvider` 인터페이스에 따라 특정 오류 HRESULT가 포함된 예외를 발생시킵니다. 서비스 공급자가 유효하지 않거나 에 대한 `IBindHost`서비스를 제공하지 못하는 `Open(lpszFileName,pError)`경우 호출은 기본값입니다.

*p알 수 없음*<br/>
관리되지 않는 개체의 `IUnknown` 인터페이스에 따라 특정 오류 HRESULT가 포함된 예외를 발생시킵니다. 있는 `IServiceProvider` 경우 에 대한 함수 `IBindHost`쿼리가 있습니다. 서비스 공급자가 유효하지 않거나 에 대한 `IBindHost`서비스를 제공하지 못하는 `Open(lpszFileName,pError)`경우 호출은 기본값입니다.

### <a name="return-value"></a>Return Value

파일이 성공적으로 열리면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 호출은 바인딩 프로세스를 시작합니다.

*lpszURL* 매개 변수에 대한 URL 또는 파일 이름을 사용할 수 있습니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]

\- 또는-

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]

## <a name="see-also"></a>참고 항목

[C모니커파일 클래스](../../mfc/reference/cmonikerfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C모니커파일 클래스](../../mfc/reference/cmonikerfile-class.md)<br/>
[CDataPath속성 클래스](../../mfc/reference/cdatapathproperty-class.md)
