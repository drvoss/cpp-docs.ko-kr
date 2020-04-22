---
title: CAtlExeModuleT 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::InitializeCom
- ATLBASE/ATL::CAtlExeModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlExeModuleT::PostMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::RegisterClassObjects
- ATLBASE/ATL::CAtlExeModuleT::RevokeClassObjects
- ATLBASE/ATL::CAtlExeModuleT::Run
- ATLBASE/ATL::CAtlExeModuleT::RunMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::UninitializeCom
- ATLBASE/ATL::CAtlExeModuleT::Unlock
- ATLBASE/ATL::CAtlExeModuleT::WinMain
- ATLBASE/ATL::CAtlExeModuleT::m_bDelayShutdown
- ATLBASE/ATL::CAtlExeModuleT::m_dwPause
- ATLBASE/ATL::CAtlExeModuleT::m_dwTimeOut
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
ms.openlocfilehash: 33edd8f2483bc21ea6cf8b68f80a2501c37d1a40
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748753"
---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT 클래스

이 클래스는 응용 프로그램의 모듈을 나타냅니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 `CAtlExeModuleT`클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[카틀렉스 모듈: :CAtlExe 모듈](#catlexemodulet)|생성자입니다.|
|[카틀렉스 모듈: :~카틀렉스 모듈](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[카틀렉스 모듈::초기화콤](#initializecom)|COM을 초기화합니다.|
|[카틀렉스 모듈: :P어스커맨드라인](#parsecommandline)|명령줄을 구문 분석하고 필요한 경우 등록을 수행합니다.|
|[카틀렉스 모듈: :P스트메시지루프](#postmessageloop)|이 메서드는 메시지 루프가 종료된 직후에 호출됩니다.|
|[카틀렉스 모듈: :P레메지루프](#premessageloop)|이 메서드는 메시지 루프를 입력하기 직전에 호출됩니다.|
|[CAtlExeModuleT::레지스터클래스개체](#registerclassobjects)|클래스 개체를 등록합니다.|
|[카틀렉스 모듈::취소클래스 개체](#revokeclassobjects)|클래스 개체를 해지합니다.|
|[카틀렉스 모듈: :실행](#run)|이 메서드는 EXE 모듈에서 코드를 실행하여 초기화하고, 메시지 루프를 실행하고, 정리합니다.|
|[카틀렉스 모듈: ::실행 메시지 루프](#runmessageloop)|이 메서드는 메시지 루프를 실행 합니다.|
|[카틀렉스 모듈: :초기화 해제](#uninitializecom)|COM을 초기화하지 않습니다.|
|[카틀렉스 모듈: :잠금 해제](#unlock)|모듈의 잠금 수를 감소시입니다.|
|[카틀렉스 모듈: ::윈메인](#winmain)|이 메서드는 EXE를 실행 하는 데 필요한 코드를 구현 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[카틀렉스 모듈: :m_bDelayShutdown](#m_bdelayshutdown)|모듈 종료가 지연되어야 한다는 플래그입니다.|
|[카틀렉스 모듈: :m_dwPause](#m_dwpause)|종료 하기 전에 모든 개체가 해제 되도록 하는 데 사용 되는 일시 중지 값입니다.|
|[카틀렉스 모듈: :m_dwTimeOut](#m_dwtimeout)|모듈 언로드를 지연하는 데 사용되는 시간 시간 시간 값입니다.|

## <a name="remarks"></a>설명

`CAtlExeModuleT`는 응용 프로그램(EXE)에 대한 모듈을 나타내며 EXE 생성, 명령줄 처리, 클래스 개체 등록, 메시지 루프 실행 및 종료 시 정리를 지원하는 코드가 포함되어 있습니다.

이 클래스는 EXE 서버의 COM 개체가 지속적으로 생성되고 소멸될 때 성능을 향상시키도록 설계되었습니다. 마지막 COM 개체가 해제된 후 EXE는 [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) 데이터 멤버가 지정한 기간을 기다립니다. 이 기간 동안 활동이 없으면(즉, COM 개체가 만들어지지 않음) 종료 프로세스가 시작됩니다.

[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) 데이터 멤버는 EXE가 위에 정의된 메커니즘을 사용해야 하는지 여부를 결정하는 데 사용되는 플래그입니다. false로 설정된 경우 모듈이 즉시 종료됩니다.

ATL 모듈에 대한 자세한 내용은 [ATL 모듈 클래스를](../../atl/atl-module-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlExeModuleT`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="catlexemoduletcatlexemodulet"></a><a name="catlexemodulet"></a>카틀렉스 모듈: :CAtlExe 모듈

생성자입니다.

```
CAtlExeModuleT() throw();
```

### <a name="remarks"></a>설명

EXE 모듈을 초기화할 수 없는 경우 WinMain은 추가 처리 없이 즉시 반환됩니다.

## <a name="catlexemoduletcatlexemodulet"></a><a name="dtor"></a>카틀렉스 모듈: :~카틀렉스 모듈

소멸자입니다.

```
~CAtlExeModuleT() throw();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제합니다.

## <a name="catlexemoduletinitializecom"></a><a name="initializecom"></a>카틀렉스 모듈::초기화콤

COM을 초기화합니다.

```
static HRESULT InitializeCom() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 생성자에서 호출 되며 기본 구현에서 다른 방식으로 COM을 초기화 하도록 재정의할 수 있습니다. 기본 구현은 `CoInitializeEx(NULL, COINIT_MULTITHREADED)` 호출하거나 `CoInitialize(NULL)` 프로젝트 구성에 따라 다릅니다.

이 메서드를 재정의하려면 일반적으로 [CAtlExeModuleT::UninitializeCom](#uninitializecom).

## <a name="catlexemoduletm_bdelayshutdown"></a><a name="m_bdelayshutdown"></a>카틀렉스 모듈: :m_bDelayShutdown

모듈 종료가 지연되어야 한다는 플래그입니다.

```
bool m_bDelayShutdown;
```

### <a name="remarks"></a>설명

자세한 내용은 [CAtlExeModuleT 개요를](../../atl/reference/catlexemodulet-class.md) 참조하십시오.

## <a name="catlexemoduletm_dwpause"></a><a name="m_dwpause"></a>카틀렉스 모듈: :m_dwPause

종료 하기 전에 모든 개체가 사라졌는지 확인 하는 데 사용 되는 일시 중지 값입니다.

```
DWORD m_dwPause;
```

### <a name="remarks"></a>설명

[CAtlExeModuleT::InitializeCom을](#initializecom) 호출한 후 이 값을 변경하여 서버를 종료하기 위한 일시 중지 값으로 사용되는 밀리초 수를 설정합니다. 기본값은 1000밀리초입니다.

## <a name="catlexemoduletm_dwtimeout"></a><a name="m_dwtimeout"></a>카틀렉스 모듈: :m_dwTimeOut

모듈 언로드를 지연하는 데 사용되는 시간 시간 시간 값입니다.

```
DWORD m_dwTimeOut;
```

### <a name="remarks"></a>설명

[CAtlExeModuleT::InitializeCom을](#initializecom) 호출한 후 이 값을 변경하여 서버를 종료하기 위한 시간 시간 시간 값으로 사용되는 밀리초 수를 정의합니다. 기본값은 5000밀리초입니다. 자세한 내용은 [CAtlExeModuleT 개요를](../../atl/reference/catlexemodulet-class.md) 참조하십시오.

## <a name="catlexemoduletparsecommandline"></a><a name="parsecommandline"></a>카틀렉스 모듈: :P어스커맨드라인

명령줄을 구문 분석하고 필요한 경우 등록을 수행합니다.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>매개 변수

*lpCmdLine*<br/>
명령줄이 응용 프로그램에 전달되었습니다.

*pnRetCode*<br/>
등록에 해당하는 HRESULT(발생한 경우).

### <a name="return-value"></a>Return Value

응용 프로그램이 계속 실행되어야 하는 경우 true를 반환합니다(그렇지 않으면 false).

### <a name="remarks"></a>설명

이 메서드는 [CAtlExeModuleT::WinMain에서](#winmain) 호출되며 명령줄 스위치를 처리하기 위해 재정의할 수 있습니다. 기본 구현은 **/RegServer** 및 **/UnRegServer** 명령줄 인수를 확인하고 등록 또는 등록 취소를 수행합니다.

## <a name="catlexemoduletpostmessageloop"></a><a name="postmessageloop"></a>카틀렉스 모듈: :P스트메시지루프

이 메서드는 메시지 루프가 종료된 직후에 호출됩니다.

```
HRESULT PostMessageLoop() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 응용 프로그램 정리를 수행 하려면이 메서드를 재정의 합니다. 기본 구현은 [CAtlExeModuleT::해지클래스 개체를 호출합니다.](#revokeclassobjects)

## <a name="catlexemoduletpremessageloop"></a><a name="premessageloop"></a>카틀렉스 모듈: :P레메지루프

이 메서드는 메시지 루프를 입력하기 직전에 호출됩니다.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>매개 변수

*n표시Cmd*<br/>
WinMain에서 *nShowCmd* 매개 변수로 전달 된 값입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 응용 프로그램에 대한 사용자 지정 초기화 코드를 추가합니다. 기본 구현은 클래스 개체를 등록합니다.

## <a name="catlexemoduletregisterclassobjects"></a><a name="registerclassobjects"></a>CAtlExeModuleT::레지스터클래스개체

다른 응용 프로그램이 연결할 수 있도록 클래스 개체를 OLE로 등록합니다.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>매개 변수

*dwClsContext*<br/>
클래스 개체를 실행할 컨텍스트를 지정합니다. 가능한 값은 CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER 또는 CLSCTX_LOCAL_SERVER.

*dwFlags*<br/>
클래스 개체에 대한 연결 유형을 결정합니다. 가능한 값은 REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE 또는 REGCLS_MULTI_SEPARATE.

### <a name="return-value"></a>Return Value

등록할 클래스가 없는 경우, S_FALSE 성공 또는 오류에 대한 오류 HRESULT가 없는 경우 성공 S_OK 반환합니다.

## <a name="catlexemoduletrevokeclassobjects"></a><a name="revokeclassobjects"></a>카틀렉스 모듈::취소클래스 개체

클래스 개체를 제거합니다.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Return Value

등록할 클래스가 없는 경우, S_FALSE 성공 또는 오류에 대한 오류 HRESULT가 없는 경우 성공 S_OK 반환합니다.

## <a name="catlexemoduletrun"></a><a name="run"></a>카틀렉스 모듈: :실행

이 메서드는 EXE 모듈에서 코드를 실행하여 초기화하고, 메시지 루프를 실행하고, 정리합니다.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>매개 변수

*n표시Cmd*<br/>
창을 표시하는 방법을 지정합니다. 이 매개 변수는 [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) 섹션에서 설명하는 값 중 하나일 수 있습니다. 기본값은 SW_HIDE.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드를 재정의할 수 있습니다. 그러나 실제로는 [CAtlExeModuleT::PreMessageLoop,](#premessageloop) [CAtlExeModuleT::RunMessageLoop,](#runmessageloop)또는 [CAtlExeModuleT::PostMessageLoop](#postmessageloop) 대신 재정의하는 것이 좋습니다.

## <a name="catlexemoduletrunmessageloop"></a><a name="runmessageloop"></a>카틀렉스 모듈: ::실행 메시지 루프

이 메서드는 메시지 루프를 실행 합니다.

```cpp
void RunMessageLoop() throw();
```

### <a name="remarks"></a>설명

이 메서드를 재정의하여 메시지 루프의 동작을 변경할 수 있습니다.

## <a name="catlexemoduletuninitializecom"></a><a name="uninitializecom"></a>카틀렉스 모듈: :초기화 해제

COM을 초기화하지 않습니다.

```
static void UninitializeCom() throw();
```

### <a name="remarks"></a>설명

기본적으로 이 메서드는 단순히 [CoUninitialize를](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize) 호출하고 소멸자에서 호출됩니다. [CAtlExeModuleT::InitializeCom을](#initializecom)재정의하는 경우 이 메서드를 재정의합니다.

## <a name="catlexemoduletunlock"></a><a name="unlock"></a>카틀렉스 모듈: :잠금 해제

모듈의 잠금 수를 감소시입니다.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Return Value

진단 또는 테스트에 유용할 수 있는 값을 반환합니다.

## <a name="catlexemoduletwinmain"></a><a name="winmain"></a>카틀렉스 모듈: ::윈메인

이 메서드는 EXE를 실행 하는 데 필요한 코드를 구현 합니다.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>매개 변수

*n표시Cmd*<br/>
창을 표시하는 방법을 지정합니다. 이 매개 변수는 [WinMain](/windows/win32/api/winbase/nf-winbase-winmain) 섹션에서 설명하는 값 중 하나일 수 있습니다.

### <a name="return-value"></a>Return Value

실행 의 반환 값을 반환 합니다.

### <a name="remarks"></a>설명

이 메서드를 재정의할 수 있습니다. [CAtlExeModuleT::PreMessageLoop,](#premessageloop) [CAtlExeModuleT::PostMessageLoop,](#postmessageloop)또는 [CAtlExeModuleT:::RunMessageLoop가](#runmessageloop) 충분한 유연성을 제공하지 않는 경우 이 `WinMain` 메서드를 사용하여 함수를 재정의할 수 있습니다.

## <a name="see-also"></a>참조

[ATL덕 샘플](../../overview/visual-cpp-samples.md)<br/>
[CAtlModuleT 클래스](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlDllModuleT 클래스](../../atl/reference/catldllmodulet-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
