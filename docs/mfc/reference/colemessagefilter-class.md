---
title: COleMessage필터 클래스
ms.date: 11/04/2016
f1_keywords:
- COleMessageFilter
- AFXOLE/COleMessageFilter
- AFXOLE/COleMessageFilter::COleMessageFilter
- AFXOLE/COleMessageFilter::BeginBusyState
- AFXOLE/COleMessageFilter::EnableBusyDialog
- AFXOLE/COleMessageFilter::EnableNotRespondingDialog
- AFXOLE/COleMessageFilter::EndBusyState
- AFXOLE/COleMessageFilter::OnMessagePending
- AFXOLE/COleMessageFilter::Register
- AFXOLE/COleMessageFilter::Revoke
- AFXOLE/COleMessageFilter::SetBusyReply
- AFXOLE/COleMessageFilter::SetMessagePendingDelay
- AFXOLE/COleMessageFilter::SetRetryReply
helpviewer_keywords:
- COleMessageFilter [MFC], COleMessageFilter
- COleMessageFilter [MFC], BeginBusyState
- COleMessageFilter [MFC], EnableBusyDialog
- COleMessageFilter [MFC], EnableNotRespondingDialog
- COleMessageFilter [MFC], EndBusyState
- COleMessageFilter [MFC], OnMessagePending
- COleMessageFilter [MFC], Register
- COleMessageFilter [MFC], Revoke
- COleMessageFilter [MFC], SetBusyReply
- COleMessageFilter [MFC], SetMessagePendingDelay
- COleMessageFilter [MFC], SetRetryReply
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
ms.openlocfilehash: 8a6c160a76ae27059238c3e8e26b5bea87a87f7f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753838"
---
# <a name="colemessagefilter-class"></a>COleMessage필터 클래스

OLE 애플리케이션의 상호 작용으로 요구되는 동시성을 관리합니다.

## <a name="syntax"></a>구문

```
class COleMessageFilter : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COleMessage 필터::COleMessage필터](#colemessagefilter)|`COleMessageFilter` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleMessage필터::시작바쁜 상태](#beginbusystate)|응용 프로그램을 사용 중 이면 상태로 둡자입니다.|
|[COleMessage필터::사용 바쁜 디아로그](#enablebusydialog)|호출된 응용 프로그램이 사용 중일 때 나타나는 대화 상자를 활성화하고 사용하지 않도록 설정합니다.|
|[COleMessage필터::인에이블노응답디아로그](#enablenotrespondingdialog)|호출된 응용 프로그램이 응답하지 않을 때 나타나는 대화 상자를 활성화하고 사용하지 않도록 설정합니다.|
|[COleMessage필터::엔드비상태](#endbusystate)|응용 프로그램의 사용 중 상태가 종료됩니다.|
|[COleMessage필터::온메시지 보류](#onmessagepending)|OLE 호출이 진행 중인 동안 메시지를 처리하기 위해 프레임워크에서 호출합니다.|
|[COleMessage필터::레지스터](#register)|OLE 시스템 DLL에 메시지 필터를 등록합니다.|
|[COleMessage필터::해지](#revoke)|OLE 시스템 DLL을 사용한 메시지 필터 등록을 취소합니다.|
|[COleMessage 필터::설정바쁜회신](#setbusyreply)|OLE 호출에 대한 사용 중인 응용 프로그램의 회신을 결정합니다.|
|[COleMessage필터::설정메시지보류지연](#setmessagependingdelay)|응용 프로그램이 OLE 호출에 대한 응답을 기다리는 데 걸리는 시간이 결정됩니다.|
|[COleMessage 필터::세트 다시회신](#setretryreply)|사용 중인 응용 프로그램에 대한 호출 응용 프로그램의 회신을 결정합니다.|

## <a name="remarks"></a>설명

이 `COleMessageFilter` 클래스는 OLE 자동화 응용 프로그램뿐만 아니라 시각적 편집 서버 및 컨테이너 응용 프로그램에 유용합니다. 호출되는 서버 응용 프로그램의 경우 이 클래스를 사용하여 응용 프로그램을 "사용 중"으로 만들어 다른 컨테이너 응용 프로그램의 수신 호출이 취소되거나 나중에 다시 시도되도록 할 수 있습니다. 이 클래스는 호출된 응용 프로그램이 사용 중일 때 호출 응용 프로그램에서 수행할 작업을 결정하는 데도 사용할 수 있습니다.

일반적인 용도는 서버 응용 프로그램이 문서 또는 기타 OLE 액세스 가능한 개체가 소멸되는 위험할 때 [BeginBusyState](#beginbusystate) 및 [EndBusyState를](#endbusystate) 호출하는 것입니다. 이러한 호출은 [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle) 사용자 인터페이스 업데이트 중에 수행됩니다.

기본적으로 `COleMessageFilter` 응용 프로그램이 초기화될 때 개체가 할당됩니다. [AfxOleGetMessageFilter로](application-control.md#afxolegetmessagefilter)검색할 수 있습니다.

고급 클래스입니다. 직접 작업할 필요가 거의 없습니다.

자세한 내용은 [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="colemessagefilterbeginbusystate"></a><a name="beginbusystate"></a>COleMessage필터::시작바쁜 상태

이 함수를 호출하여 사용 중 상태를 시작합니다.

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>설명

응용 프로그램의 사용 중인 상태를 제어 하기 위해 [EndBusyState와](#endbusystate) 함께 작동 합니다. [SetBusyReply](#setbusyreply) 함수는 사용 중일 때 호출 하는 응용 프로그램에 대 한 응용 프로그램의 회신을 결정 합니다.

응용 `BeginBusyState` `EndBusyState` 프로그램이 사용 중인지 여부를 결정하는 카운터인 및 는 각각 증분 및 감소를 호출합니다. 예를 들어 두 `BeginBusyState` 번의 호출과 한 번의 호출로 `EndBusyState` 인해 여전히 사용 중 상태가 됩니다. 사용 중인 상태를 취소하려면 호출된 횟수와 `BeginBusyState` 동일한 횟수를 호출해야 `EndBusyState` 합니다.

기본적으로 프레임워크는 [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)에 의해 수행되는 유휴 처리 중에 사용 중인 상태로 들어갑니다. 응용 프로그램이 ON_COMMANDUPDATEUI 알림을 처리하는 동안 유휴 처리가 완료된 후 수신 호출이 나중에 처리됩니다.

## <a name="colemessagefiltercolemessagefilter"></a><a name="colemessagefilter"></a>COleMessage 필터::COleMessage필터

`COleMessageFilter` 개체를 만듭니다.

```
COleMessageFilter();
```

## <a name="colemessagefilterenablebusydialog"></a><a name="enablebusydialog"></a>COleMessage필터::사용 바쁜 디아로그

OLE 호출 중에 메시지 보류 중인 지연이 만료될 때 표시되는 사용 중인 대화 상자를 활성화하고 사용하지 않도록 [설정합니다(SetRetryReply](#setretryreply)참조).

```cpp
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>매개 변수

*b인가능하게*<br/>
"사용 중" 대화 상자를 사용 중지할지 여부를 지정합니다.

## <a name="colemessagefilterenablenotrespondingdialog"></a><a name="enablenotrespondingdialog"></a>COleMessage필터::인에이블노응답디아로그

OLE 호출 중에 키보드 또는 마우스 메시지가 보류 중이고 통화 시간이 시간 지정된 경우 표시되는 "응답하지 않음" 대화 상자를 활성화하고 사용하지 않도록 설정합니다.

```cpp
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnableNot응답하지 않음*<br/>
"응답하지 않음" 대화 상자가 활성화되어 있는지 또는 사용하지 않도록 설정되었는지 여부를 지정합니다.

## <a name="colemessagefilterendbusystate"></a><a name="endbusystate"></a>COleMessage필터::엔드비상태

이 함수를 호출하여 사용 중인 상태를 종료합니다.

```
virtual void EndBusyState();
```

### <a name="remarks"></a>설명

응용 프로그램의 사용 중인 상태를 제어 하기 위해 [BeginBusyState와](#beginbusystate) 함께 작동 합니다. [SetBusyReply](#setbusyreply) 함수는 사용 중일 때 호출 하는 응용 프로그램에 대 한 응용 프로그램의 회신을 결정 합니다.

응용 `BeginBusyState` `EndBusyState` 프로그램이 사용 중인지 여부를 결정하는 카운터인 및 는 각각 증분 및 감소를 호출합니다. 예를 들어 두 `BeginBusyState` 번의 호출과 한 번의 호출로 `EndBusyState` 인해 여전히 사용 중 상태가 됩니다. 사용 중인 상태를 취소하려면 호출된 횟수와 `BeginBusyState` 동일한 횟수를 호출해야 `EndBusyState` 합니다.

기본적으로 프레임워크는 [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)에 의해 수행되는 유휴 처리 중에 사용 중인 상태로 들어갑니다. 응용 프로그램이 ON_UPDATE_COMMAND_UI 알림을 처리하는 동안 유휴 처리가 완료된 후 수신 호출이 처리됩니다.

## <a name="colemessagefilteronmessagepending"></a><a name="onmessagepending"></a>COleMessage필터::온메시지 보류

OLE 호출이 진행 중인 동안 메시지를 처리하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
보류 중인 메시지에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

호출 응용 프로그램이 호출이 완료되기를 기다리는 경우 `OnMessagePending` 프레임워크는 보류 중인 메시지에 대한 포인터를 사용하여 호출합니다. 기본적으로 프레임워크는 메시지를 WM_PAINT 전달하므로 시간이 오래 걸리는 호출 중에 창 업데이트가 발생할 수 있습니다.

활성화되기 전에 [등록](#register) 호출을 통해 메시지 필터를 등록해야 합니다.

## <a name="colemessagefilterregister"></a><a name="register"></a>COleMessage필터::레지스터

OLE 시스템 DLL에 메시지 필터를 등록합니다.

```
BOOL Register();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

메시지 필터는 시스템 DLL에 등록되어 있지 않으면 영향을 주지 않습니다. 일반적으로 응용 프로그램의 초기화 코드는 응용 프로그램의 메시지 필터를 등록합니다. 응용 프로그램에 의해 등록된 다른 모든 메시지 필터는 [프로그램이 해지](#revoke)호출로 종료되기 전에 해지되어야 합니다.

프레임워크의 기본 메시지 필터는 초기화 중에 자동으로 등록되고 종료 시 해지됩니다.

## <a name="colemessagefilterrevoke"></a><a name="revoke"></a>COleMessage필터::해지

[등록](#register)에 대한 호출에 의해 수행된 이전 등록을 해지합니다.

```cpp
void Revoke();
```

### <a name="remarks"></a>설명

프로그램이 종료되기 전에 메시지 필터를 해지해야 합니다.

프레임워크에 의해 자동으로 생성되고 등록된 기본 메시지 필터도 자동으로 해지됩니다.

## <a name="colemessagefiltersetbusyreply"></a><a name="setbusyreply"></a>COleMessage 필터::설정바쁜회신

이 함수는 응용 프로그램의 "사용 중인 응답"을 설정합니다.

```cpp
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>매개 변수

*n바쁜회신*<br/>
COMPOBJ에 `SERVERCALL` 정의된 열거형의 값입니다. H. 다음 값 중 하나를 가질 수 있습니다.

- SERVERCALL_ISHANDLED 응용 프로그램은 호출을 수락할 수 있지만 특정 호출을 처리하는 데 실패할 수 있습니다.

- SERVERCALL_REJECTED 응용 프로그램은 아마도 호출을 처리 할 수 없습니다.

- SERVERCALL_RETRYLATER 응용 프로그램이 호출을 처리할 수 없는 상태로 일시적으로 있습니다.

### <a name="remarks"></a>설명

[BeginBusyState](#beginbusystate) 및 [EndBusyState](#endbusystate) 함수는 응용 프로그램의 사용 중 상태를 제어합니다.

응용 프로그램이 호출로 `BeginBusyState`사용 중이 되면 OLE 시스템 DLL의 호출에 응답하고 마지막 설정에 `SetBusyReply`의해 결정된 값입니다. 호출 응용 프로그램은 이 바쁜 회신을 사용하여 취할 작업을 결정합니다.

기본적으로 사용 중인 회신은 SERVERCALL_RETRYLATER. 이 회신을 사용하면 호출 응용 프로그램이 가능한 한 빨리 호출을 다시 시도합니다.

## <a name="colemessagefiltersetmessagependingdelay"></a><a name="setmessagependingdelay"></a>COleMessage필터::설정메시지보류지연

추가 작업을 수행 하기 전에 호출 응용 프로그램 호출 응용 프로그램에서 호출 된 응용 프로그램의 응답을 대기 하는 기간 확인 합니다.

```cpp
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>매개 변수

*n시간 시간*<br/>
메시지 보류 지연의 밀리초입니다.

### <a name="remarks"></a>설명

이 기능은 [SetRetry회신과](#setretryreply)함께 작동합니다.

## <a name="colemessagefiltersetretryreply"></a><a name="setretryreply"></a>COleMessage 필터::세트 다시회신

호출 된 응용 프로그램에서 사용 하지 않는 응답을 받을 때 호출 응용 프로그램의 작업을 결정 합니다.

```cpp
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>매개 변수

*nRetry회신*<br/>
다시 시도 사이의 밀리초 수입니다.

### <a name="remarks"></a>설명

호출된 응용 프로그램이 사용 중임을 나타내는 경우 호출 응용 프로그램은 서버가 더 이상 사용 중일 때까지 기다리거나, 즉시 다시 시도하거나, 지정된 간격 이후에 다시 시도하도록 결정할 수 있습니다. 또한 통화를 모두 취소하기로 결정할 수도 있습니다.

호출자의 응답은 함수 `SetRetryReply` 및 [SetMessagePendingDelay에](#setmessagependingdelay)의해 제어됩니다. `SetRetryReply`는 호출 응용 프로그램이 지정된 호출에 대해 다시 시도사이에 기다려야 하는 길이를 결정합니다. `SetMessagePendingDelay`은 추가 작업을 수행하기 전에 호출 응용 프로그램이 서버의 응답을 기다리는 데 걸리는 시간이 결정됩니다.

일반적으로 기본값은 허용되며 변경할 필요가 없습니다. 프레임워크는 호출이 진행되거나 메시지 보류 지연이 만료될 때까지 *모든 nRetryReply* 밀리초마다 호출을 다시 시도합니다. *nRetryReply에* 대한 값이 0이면 즉시 다시 시도가 지정되고 - 1은 호출 취소를 지정합니다.

메시지 보류 지연이 만료되면 OLE "사용 중인 대화 [상자"(COleBusyDialog](../../mfc/reference/colebusydialog-class.md)참조)가 표시되므로 사용자가 통화를 취소하거나 다시 시도할 수 있습니다. 이 대화 상자를 활성화하거나 사용하지 않도록 설정하려면 [사용즉시 대화 상자를](#enablebusydialog) 호출합니다.

통화 중에 키보드 또는 마우스 메시지가 보류 중이고 통화 시간이 초과되면(메시지 보류 지연 초과) "응답하지 않음" 대화 상자가 표시됩니다. 이 대화 상자를 활성화하거나 사용하지 않도록 설정하려면 [EnableNotRespondingDialog를](#enablenotrespondingdialog) 호출합니다. 일반적으로 이 상태는 문제가 잘못되어 사용자가 참을성이 없다는 것을 나타냅니다.

대화 상자를 사용하지 않도록 설정하면 현재 "재시도 회신"이 항상 사용 중인 응용 프로그램에 대한 호출에 사용됩니다.

## <a name="see-also"></a>참조

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)
