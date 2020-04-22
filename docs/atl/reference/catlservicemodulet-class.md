---
title: CAtlServiceModuleT 클래스
ms.date: 05/06/2019
f1_keywords:
- CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::Handler
- ATLBASE/ATL::CAtlServiceModuleT::InitializeSecurity
- ATLBASE/ATL::CAtlServiceModuleT::Install
- ATLBASE/ATL::CAtlServiceModuleT::IsInstalled
- ATLBASE/ATL::CAtlServiceModuleT::LogEvent
- ATLBASE/ATL::CAtlServiceModuleT::OnContinue
- ATLBASE/ATL::CAtlServiceModuleT::OnInterrogate
- ATLBASE/ATL::CAtlServiceModuleT::OnPause
- ATLBASE/ATL::CAtlServiceModuleT::OnShutdown
- ATLBASE/ATL::CAtlServiceModuleT::OnStop
- ATLBASE/ATL::CAtlServiceModuleT::OnUnknownRequest
- ATLBASE/ATL::CAtlServiceModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlServiceModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlServiceModuleT::RegisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::Run
- ATLBASE/ATL::CAtlServiceModuleT::ServiceMain
- ATLBASE/ATL::CAtlServiceModuleT::SetServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::Start
- ATLBASE/ATL::CAtlServiceModuleT::Uninstall
- ATLBASE/ATL::CAtlServiceModuleT::Unlock
- ATLBASE/ATL::CAtlServiceModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::WinMain
- ATLBASE/ATL::CAtlServiceModuleT::m_bService
- ATLBASE/ATL::CAtlServiceModuleT::m_dwThreadID
- ATLBASE/ATL::CAtlServiceModuleT::m_hServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::m_status
- ATLBASE/ATL::CAtlServiceModuleT::m_szServiceName
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
ms.openlocfilehash: 6d1985384c2d9a324abac548f27be6be5f0cacf5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748598"
---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT 클래스

이 클래스는 서비스를 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, UINT nServiceNameID>
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 `CAtlServiceModuleT`클래스입니다.

*n서비스이름 ID*<br/>
서비스의 리소스 식별자입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAtlService 모듈: :CAtlService 모듈T](#catlservicemodulet)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAtlService모듈T::처리기](#handler)|서비스에 대한 처리기 루틴입니다.|
|[CAtlService모듈::초기화보안](#initializesecurity)|서비스에 대한 기본 보안 설정을 제공합니다.|
|[CAtlService모듈::설치](#install)|서비스를 설치하고 만듭니다.|
|[CAtlService모듈: :설치](#isinstalled)|서비스가 설치되었는지 확인합니다.|
|[CAtlService 모듈: :로그 이벤트](#logevent)|이벤트 로그에 씁니다.|
|[CAtlService모듈: :계속](#oncontinue)|서비스를 계속하려면 이 메서드를 재정의합니다.|
|[카틀서비스모듈::온인터로게이트](#oninterrogate)|이 메서드를 재정의하여 서비스를 인터로게이지합니다.|
|[CAtlService 모듈: :에 일시 중지](#onpause)|이 메서드를 재정의하여 서비스를 일시 중지합니다.|
|[CAtlService모듈: :OnShutdown](#onshutdown)|이 메서드를 재정의하여 서비스를 종료합니다.|
|[CAtlService모듈: :온스톱](#onstop)|이 메서드를 재정의하여 서비스를 중지합니다.|
|[CAtlService모듈::알 수 없음 요청](#onunknownrequest)|이 메서드를 재정의하여 서비스에 대한 알 수 없는 요청을 처리합니다.|
|[CAtlService모듈: :P어슬코맨라인](#parsecommandline)|명령줄을 구문 분석하고 필요한 경우 등록을 수행합니다.|
|[카틀서비스모듈::P레메시지루프](#premessageloop)|이 메서드는 메시지 루프를 입력하기 직전에 호출됩니다.|
|[CAtlService모듈: :레지스터앱Id](#registerappid)|레지스트리에 서비스를 등록합니다.|
|[CAtlService모듈: :실행](#run)|서비스를 실행합니다.|
|[CAtlServiceModuleT::ServiceMain](#servicemain)|서비스 제어 관리자에서 호출하는 메서드입니다.|
|[CAtlService모듈: ::설정 서비스 상태](#setservicestatus)|서비스 상태를 업데이트합니다.|
|[CAtlService모듈: :시작](#start)|서비스가 `CAtlServiceModuleT::WinMain` 시작될 때 호출됩니다.|
|[CAtlService모듈::제거](#uninstall)|서비스를 중지하고 제거합니다.|
|[CAtlService모듈: :잠금 해제](#unlock)|서비스의 잠금 수를 감소시입니다.|
|[CAtlService모듈::등록 해제](#unregisterappid)|레지스트리에서 서비스를 제거합니다.|
|[카틀서비스모듈::윈메인](#winmain)|이 메서드는 서비스를 실행 하는 데 필요한 코드를 구현 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CAtlService모듈: m_bService](#m_bservice)|프로그램이 서비스로 실행 중임을 나타내는 플래그입니다.|
|[CAtlService모듈: m_dwThreadID](#m_dwthreadid)|스레드 식별자를 저장하는 멤버 변수입니다.|
|[CAtlService모듈: m_hServiceStatus](#m_hservicestatus)|현재 서비스의 상태 정보 구조에 핸들을 저장하는 멤버 변수입니다.|
|[CAtlService모듈: m_status](#m_status)|현재 서비스에 대한 상태 정보 구조를 저장하는 멤버 변수입니다.|
|[CAtlService모듈: m_szServiceName](#m_szservicename)|등록중인 서비스의 이름입니다.|

## <a name="remarks"></a>설명

`CAtlServiceModuleT`, [AtlExeModuleT에서](../../atl/reference/catlexemodulet-class.md)파생된 ATL 서비스 모듈을 구현합니다. `CAtlServiceModuleT`에서는 명령줄 처리, 설치, 등록 및 제거 방법을 제공합니다. 추가 기능이 필요한 경우 이러한 방법과 다른 메서드를 재정의할 수 있습니다.

이 클래스는 이전 버전의 ATL에서 사용된 사용되지 않는 [CComModule 클래스를](../../atl/reference/ccommodule-class.md) 대체합니다. 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)

`CAtlServiceModuleT`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="catlservicemoduletcatlservicemodulet"></a><a name="catlservicemodulet"></a>CAtlService 모듈: :CAtlService 모듈T

생성자입니다.

```
CAtlServiceModuleT() throw();
```

### <a name="remarks"></a>설명

데이터 멤버를 초기화하고 초기 서비스 상태를 설정합니다.

## <a name="catlservicemodulethandler"></a><a name="handler"></a>CAtlService모듈T::처리기

서비스에 대한 처리기 루틴입니다.

```cpp
void Handler(DWORD dwOpcode) throw();
```

### <a name="parameters"></a>매개 변수

*dwOpcode*<br/>
처리기 작업을 정의하는 스위치입니다. 자세한 내용은 비고를 참조하십시오.

### <a name="remarks"></a>설명

이 코드는 SCM(서비스 제어 관리자)이 서비스 상태를 검색하고 중지 또는 일시 중지와 같은 명령을 내리기 위해 호출하는 코드입니다. SCM은 서비스가 수행해야 하는 작업을 `Handler` 나타내기 위해 아래와 같은 작업 코드를 전달합니다.

|작업 코드|의미|
|--------------------|-------------|
|SERVICE_CONTROL_STOP|서비스를 중지합니다. 메서드 [CAtlServiceModuleT::onStop](#onstop) atlbase.h에서 동작을 변경 합니다 재정의 합니다.|
|SERVICE_CONTROL_PAUSE|사용자가 구현했습니다. 빈 메서드 [CAtlServiceModuleT::onPause](#onpause) atlbase.h에서 서비스를 일시 중지합니다.|
|SERVICE_CONTROL_CONTINUE|사용자가 구현했습니다. 빈 메서드 [CAtlServiceModuleT::Onservice.h에서 서비스를](#oncontinue) 계속하려면 atlbase.h에서 계속합니다.|
|SERVICE_CONTROL_INTERROGATE|사용자가 구현했습니다. 빈 메서드 [CAtlServiceModuleT::oninterrogate](#oninterrogate) atlbase.h에서 서비스를 심문합니다.|
|SERVICE_CONTROL_SHUTDOWN|사용자가 구현했습니다. 빈 메서드 [CAtlServiceModuleT::OnShutdown](#onshutdown) atlbase.h에서 서비스를 종료합니다.|

작업 코드가 인식되지 않으면 [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) 메서드가 호출됩니다.

기본 ATL 생성 서비스는 중지 명령만 처리합니다. SCM이 중지 명령을 통과하면 서비스는 프로그램이 중지될 것이라는 것을 SCM에 알려줍니다. 그런 다음 `PostThreadMessage` 서비스는 종료 메시지를 자체에 게시하도록 호출합니다. 이렇게 하면 메시지 루프가 종료되고 서비스가 궁극적으로 닫힙됩니다.

## <a name="catlservicemoduletinitializesecurity"></a><a name="initializesecurity"></a>CAtlService모듈::초기화보안

서비스에 대한 기본 보안 설정을 제공합니다.

```
HRESULT InitializeSecurity() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

파생된 `CAtlServiceModuleT` 모든 클래스는 파생 된 클래스에서이 메서드를 구현 해야 합니다.

에 대한 호출에서 PKT 수준 인증, 가장 RPC_C_IMP_LEVEL_IDENTIFY 및 적절한 null이 아닌 `CoInitializeSecurity`보안 설명자 사용

마법사에서 생성된 어트리뷰션되지 않은 서비스 프로젝트의 경우

[!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]

어트리뷰트된 서비스 프로젝트의 경우,

[!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]

## <a name="catlservicemoduletinstall"></a><a name="install"></a>CAtlService모듈::설치

서비스를 설치하고 만듭니다.

```
BOOL Install() throw();
```

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

SCM(서비스 제어 관리자) 데이터베이스에 서비스를 설치한 다음 서비스 개체를 만듭니다. 서비스를 만들 수 없는 경우 메시지 상자가 표시 되고 메서드는 FALSE를 반환합니다.

## <a name="catlservicemoduletisinstalled"></a><a name="isinstalled"></a>CAtlService모듈: :설치

서비스가 설치되었는지 확인합니다.

```
BOOL IsInstalled() throw();
```

### <a name="return-value"></a>Return Value

서비스가 설치된 경우 TRUE를 반환합니다.

## <a name="catlservicemoduletlogevent"></a><a name="logevent"></a>CAtlService 모듈: :로그 이벤트

이벤트 로그에 씁니다.

```cpp
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
이벤트 로그에 쓸 문자열입니다.

*...*<br/>
이벤트 로그에 쓸 추가 문자열(옵션)입니다.

### <a name="remarks"></a>설명

이 메서드는 [ReportEvent](/windows/win32/api/winbase/nf-winbase-reporteventw)함수를 사용하여 이벤트 로그에 세부 정보를 기록합니다. 실행 중인 서비스가 없는 경우 문자열이 콘솔로 전송됩니다.

## <a name="catlservicemoduletm_bservice"></a><a name="m_bservice"></a>CAtlService모듈: m_bService

프로그램이 서비스로 실행 중임을 나타내는 플래그입니다.

```
BOOL m_bService;
```

### <a name="remarks"></a>설명

서비스 EXE를 응용 프로그램 EXE와 구별하는 데 사용됩니다.

## <a name="catlservicemoduletm_dwthreadid"></a><a name="m_dwthreadid"></a>CAtlService모듈: m_dwThreadID

서비스의 스레드 식별자를 저장하는 멤버 변수입니다.

```
DWORD m_dwThreadID;
```

### <a name="remarks"></a>설명

이 변수는 현재 스레드의 스레드 식별자를 저장합니다.

## <a name="catlservicemoduletm_hservicestatus"></a><a name="m_hservicestatus"></a>CAtlService모듈: m_hServiceStatus

현재 서비스의 상태 정보 구조에 핸들을 저장하는 멤버 변수입니다.

```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```

### <a name="remarks"></a>설명

[SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status) 구조에는 서비스에 대한 정보가 포함되어 있습니다.

## <a name="catlservicemoduletm_status"></a><a name="m_status"></a>CAtlService모듈: m_status

현재 서비스에 대한 상태 정보 구조를 저장하는 멤버 변수입니다.

```
SERVICE_STATUS m_status;
```

### <a name="remarks"></a>설명

[SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status) 구조에는 서비스에 대한 정보가 포함되어 있습니다.

## <a name="catlservicemoduletm_szservicename"></a><a name="m_szservicename"></a>CAtlService모듈: m_szServiceName

등록중인 서비스의 이름입니다.

```
TCHAR [256] m_szServiceName;
```

### <a name="remarks"></a>설명

서비스 이름을 저장하는 null 종료 문자열입니다.

## <a name="catlservicemoduletoncontinue"></a><a name="oncontinue"></a>CAtlService모듈: :계속

서비스를 계속하려면 이 메서드를 재정의합니다.

```cpp
void OnContinue() throw();
```

## <a name="catlservicemoduletoninterrogate"></a><a name="oninterrogate"></a>카틀서비스모듈::온인터로게이트

이 메서드를 재정의하여 서비스를 인터로게이지합니다.

```cpp
void OnInterrogate() throw();
```

## <a name="catlservicemoduletonpause"></a><a name="onpause"></a>CAtlService 모듈: :에 일시 중지

이 메서드를 재정의하여 서비스를 일시 중지합니다.

```cpp
void OnPause() throw();
```

## <a name="catlservicemoduletonshutdown"></a><a name="onshutdown"></a>CAtlService모듈: :OnShutdown

이 메서드를 재정의하여 서비스를 종료합니다.

```cpp
void OnShutdown() throw();
```

## <a name="catlservicemoduletonstop"></a><a name="onstop"></a>CAtlService모듈: :온스톱

이 메서드를 재정의하여 서비스를 중지합니다.

```cpp
void OnStop() throw();
```

## <a name="catlservicemoduletonunknownrequest"></a><a name="onunknownrequest"></a>CAtlService모듈::알 수 없음 요청

서비스에 대한 알 수 없는 요청을 처리하려면 이 메서드를 재정의합니다.

```cpp
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```

### <a name="parameters"></a>매개 변수

*dwOpcode*<br/>
예약되어 있습니다.

## <a name="catlservicemoduletparsecommandline"></a><a name="parsecommandline"></a>CAtlService모듈: :P어슬코맨라인

명령줄을 구문 분석하고 필요한 경우 등록을 수행합니다.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>매개 변수

*lpCmdLine*<br/>
명령줄입니다.

*pnRetCode*<br/>
등록에 해당하는 HRESULT(발생한 경우).

### <a name="return-value"></a>Return Value

명령줄에 제공된 RGS 파일을 등록할 수 없는 경우 성공 또는 false를 반환합니다.

### <a name="remarks"></a>설명

명령줄을 구문 분석하고 필요한 경우 제공된 RGS 파일을 등록하거나 등록 취소합니다. 이 메서드는 [CAtlExeModuleT::ParseCommandLine을](../../atl/reference/catlexemodulet-class.md#parsecommandline) 호출하여 **/RegServer** 및 **/UnregServer**. 인수 **-/Service를** 추가하면 서비스가 등록됩니다.

## <a name="catlservicemoduletpremessageloop"></a><a name="premessageloop"></a>카틀서비스모듈::P레메시지루프

이 메서드는 메시지 루프를 입력하기 직전에 호출됩니다.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>매개 변수

*n표시Cmd*<br/>
이 매개 변수는 [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop).

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 서비스에 대한 사용자 지정 초기화 코드를 추가합니다.

## <a name="catlservicemoduletregisterappid"></a><a name="registerappid"></a>CAtlService모듈: :레지스터앱Id

레지스트리에 서비스를 등록합니다.

```
inline HRESULT RegisterAppId(bool bService = false) throw();
```

### <a name="parameters"></a>매개 변수

*b 서비스*<br/>
서비스로 등록하려면 true여야 합니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catlservicemoduletrun"></a><a name="run"></a>CAtlService모듈: :실행

서비스를 실행합니다.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>매개 변수

*n표시Cmd*<br/>
창을 표시하는 방법을 지정합니다. 이 매개 변수는 [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) 섹션에서 설명하는 값 중 하나일 수 있습니다. 기본값은 SW_HIDE.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

호출 후, `Run` [호출 CAtlServiceModuleT::PreMessageLoop,](#premessageloop) [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop)및 [CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).

## <a name="catlservicemoduletservicemain"></a><a name="servicemain"></a>CAtlService모듈: ::서비스메인

이 메서드는 서비스 제어 관리자에서 호출합니다.

```cpp
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```

### <a name="parameters"></a>매개 변수

*dwArgc*<br/>
argc 인수입니다.

*lpszArgv*<br/>
argv 인수입니다.

### <a name="remarks"></a>설명

제어판에서 서비스 응용 프로그램을 `ServiceMain` 열고 서비스를 선택하고 시작을 클릭하면 SCM(서비스 제어 관리자)이 호출됩니다.

SCM 호출 `ServiceMain`후 서비스는 SCM에 처리기 함수를 제공해야 합니다. 이 기능을 사용하면 SCM이 서비스의 상태를 가져오고 특정 지침(예: 일시 중지 또는 중지)을 전달할 수 있습니다. 그런 다음 [CAtlServiceModuleT::Run을](#run) 호출하여 서비스의 주요 작업을 수행합니다. `Run`서비스가 중지될 때까지 계속 실행됩니다.

## <a name="catlservicemoduletsetservicestatus"></a><a name="setservicestatus"></a>CAtlService모듈: ::설정 서비스 상태

이 메서드는 서비스 상태를 업데이트합니다.

```cpp
void SetServiceStatus(DWORD dwState) throw();
```

### <a name="parameters"></a>매개 변수

*dwState*<br/>
새 상태입니다. 가능한 값은 [SetServiceStatus를](/windows/win32/api/winsvc/nf-winsvc-setservicestatus) 참조하십시오.

### <a name="remarks"></a>설명

서비스에 대한 서비스 제어 관리자의 상태 정보를 업데이트합니다. [그것은 CAtlServiceModuleT에 의해 호출::실행,](#run) [CAtlServiceModuleT::ServiceMain](#servicemain) 및 기타 처리기 메서드. 상태는 멤버 변수 [CAtlServiceModuleT:m_status에도](#m_status)저장됩니다.

## <a name="catlservicemoduletstart"></a><a name="start"></a>CAtlService모듈: :시작

서비스가 `CAtlServiceModuleT::WinMain` 시작될 때 호출됩니다.

```
HRESULT Start(int nShowCmd) throw();
```

### <a name="parameters"></a>매개 변수

*n표시Cmd*<br/>
창을 표시하는 방법을 지정합니다. 이 매개 변수는 [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) 섹션에서 설명하는 값 중 하나일 수 있습니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[CAtlServiceModuleT::WinMain](#winmain) 메서드는 등록 및 설치뿐만 아니라 레지스트리 항목을 제거하고 모듈을 제거하는 데 관련된 작업을 모두 처리합니다. 서비스가 실행되면 `WinMain` 를 `Start`호출합니다.

## <a name="catlservicemoduletuninstall"></a><a name="uninstall"></a>CAtlService모듈::제거

서비스를 중지하고 제거합니다.

```
BOOL Uninstall() throw();
```

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

서비스 실행을 중지 하고 서비스 제어 관리자 데이터베이스에서 제거 합니다.

## <a name="catlservicemoduletunlock"></a><a name="unlock"></a>CAtlService모듈: :잠금 해제

서비스의 잠금 수를 감소시입니다.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Return Value

진단 및 디버깅에 유용할 수 있는 잠금 수를 반환합니다.

## <a name="catlservicemoduletunregisterappid"></a><a name="unregisterappid"></a>CAtlService모듈::등록 해제

레지스트리에서 서비스를 제거합니다.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="catlservicemoduletwinmain"></a><a name="winmain"></a>카틀서비스모듈::윈메인

이 메서드는 서비스를 시작 하는 데 필요한 코드를 구현 합니다.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>매개 변수

*n표시Cmd*<br/>
창을 표시하는 방법을 지정합니다. 이 매개 변수는 [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) 섹션에서 설명하는 값 중 하나일 수 있습니다.

### <a name="return-value"></a>Return Value

서비스의 반환 값을 반환 합니다.

### <a name="remarks"></a>설명

이 메서드는 [명령줄(CAtlServiceModuleT::ParseCommandLine](#parsecommandline)사용)을 처리한 다음 서비스를 [시작합니다(CAtlServiceModuleT::Start](#start)사용).

## <a name="see-also"></a>참조

[CAtlExeModuleT 클래스](../../atl/reference/catlexemodulet-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
