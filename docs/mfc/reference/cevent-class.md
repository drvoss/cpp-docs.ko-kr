---
title: CEvent 클래스
ms.date: 11/04/2016
f1_keywords:
- CEvent
- AFXMT/CEvent
- AFXMT/CEvent::CEvent
- AFXMT/CEvent::PulseEvent
- AFXMT/CEvent::ResetEvent
- AFXMT/CEvent::SetEvent
- AFXMT/CEvent::Unlock
helpviewer_keywords:
- CEvent [MFC], CEvent
- CEvent [MFC], PulseEvent
- CEvent [MFC], ResetEvent
- CEvent [MFC], SetEvent
- CEvent [MFC], Unlock
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
ms.openlocfilehash: 009a17342cb92025d67bf2fe0df1b9d5c7c0c6f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373953"
---
# <a name="cevent-class"></a>CEvent 클래스

한 스레드가 이벤트가 발생했음을 다른 스레드에 알릴 수 있는 동기화 개체인 이벤트를 나타냅니다.

## <a name="syntax"></a>구문

```
class CEvent : public CSyncObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C이벤트::C이벤트](#cevent)|`CEvent` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CEvent::P울스이벤트](#pulseevent)|이벤트를 사용 가능한(신호)으로 설정하고 대기 스레드를 해제하고 이벤트를 사용할 수 없음(신호가 없음)으로 설정합니다.|
|[C이벤트::재설정이벤트](#resetevent)|이벤트를 사용할 수 없음(신호가 없음)으로 설정합니다.|
|[C이벤트::세트이벤트](#setevent)|이벤트를 사용 가능한(신호)로 설정하고 대기 스레드를 해제합니다.|
|[C이벤트::잠금 해제](#unlock)|이벤트 개체를 해제합니다.|

## <a name="remarks"></a>설명

이벤트는 스레드가 해당 작업을 수행할 시기를 알아야 하는 경우에 유용합니다. 예를 들어 데이터를 데이터 아카이브에 복사하는 스레드는 새 데이터를 사용할 수 있을 때 알림을 받아야 합니다. `CEvent` 새 데이터를 사용할 수 있을 때 복사 스레드에 알리는 개체를 사용 하 여 스레드는 가능한 한 빨리 해당 작업을 수행할 수 있습니다.

`CEvent`개체에는 수동 및 자동의 두 가지 유형이 있습니다.

하나 `CEvent` 이상의 스레드가 해제된 후 자동 개체가 신호가 없는(사용할 수 없음) 상태로 자동으로 반환됩니다. 기본적으로 `CEvent` 생성 하는 동안 `TRUE` *bManualReset* 매개 변수에 대 한 전달 하지 않는 한 개체는 자동으로 됩니다.

수동 `CEvent` 개체는 [SetEvent](#setevent) 또는 [ResetEvent에](#resetevent) 의해 다른 함수가 호출될 때까지 설정된 상태로 유지됩니다. 수동 `CEvent` 객체를 작성하려면 `TRUE` 시공 중에 매개변수를 `bManualReset` 전달합니다.

개체를 `CEvent` 사용하려면 필요할 `CEvent` 때 개체를 생성합니다. 대기할 이벤트의 이름을 지정하고 응용 프로그램에서 처음에 이벤트를 소유하도록 지정합니다. 그런 다음 생성자가 반환될 때 이벤트에 액세스할 수 있습니다. [SetEvent를](#setevent) 호출하여 이벤트 개체에 신호를(사용할 수 있도록)한 다음 제어된 리소스에 액세스하는 작업이 완료되면 [Unlock을](#unlock) 호출합니다.

개체를 사용하는 `CEvent` 다른 방법은 컨트롤하려는 클래스에 형식의 `CEvent` 변수를 데이터 멤버로 추가하는 것입니다. 제어 대상 개체를 구성하는 동안 `CEvent` 데이터 멤버의 생성자에게 호출하고 이벤트가 처음 신호인지 여부를 지정하고 원하는 이벤트 개체의 유형, 이벤트 이름(프로세스 경계를 넘어 사용되는 경우) 및 원하는 보안 특성을 지정합니다.

이러한 방식으로 개체에 `CEvent` 의해 제어되는 리소스에 액세스하려면 먼저 리소스의 액세스 메서드에서 [CSingleLock](../../mfc/reference/csinglelock-class.md) 또는 [CMultiLock](../../mfc/reference/cmultilock-class.md) 형식의 변수를 만듭니다. 그런 다음 `Lock` 잠금 개체의 메서드를 호출합니다(예: [CMultiLock::Lock).](../../mfc/reference/cmultilock-class.md#lock) 이 시점에서 스레드는 리소스에 대한 액세스 권한을 얻거나, 리소스가 해제될 때까지 기다렸다가 액세스 권한을 얻거나, 리소스가 해제될 때까지 기다렸다가 시간 시간이 부족하고 리소스에 대한 액세스 권한을 얻지 못합니다. 어쨌든 리소스는 스레드에서 안전한 방식으로 액세스되었습니다. 리소스를 해제하려면 `SetEvent` 이벤트 개체에 신호를 요청한 다음 `Unlock` 잠금 개체(예: [CMultiLock::Unlock)의](../../mfc/reference/cmultilock-class.md#unlock)메서드를 사용하거나 잠금 개체가 범위를 벗어나도록 합니다.

개체 를 사용하는 `CEvent` 방법에 대한 자세한 내용은 [다중 스레딩: 동기화 클래스 사용 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)참조하십시오.

## <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]

[!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CEvent`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

## <a name="ceventcevent"></a><a name="cevent"></a>C이벤트::C이벤트

명명된 개체 또는 `CEvent` 명명되지 않은 개체를 생성합니다.

```
CEvent(
    BOOL bInitiallyOwn = FALSE,
    BOOL bManualReset = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>매개 변수

*b처음 소유*<br/>
TRUE이면 `CMultilock` 또는 `CSingleLock` 개체에 대한 스레드가 활성화됩니다. 그렇지 않으면 리소스에 액세스하려는 모든 스레드를 기다려야 합니다.

*b수동 리셋*<br/>
TRUE인 경우 이벤트 개체가 수동 이벤트라고 지정하고 그렇지 않으면 이벤트 개체가 자동 이벤트입니다.

*lpszName*<br/>
`CEvent` 개체의 이름입니다. 객체가 프로세스 경계를 넘어 사용될 경우 제공되어야 합니다. 이름이 기존 이벤트와 일치하면 생성자는 해당 `CEvent` 이름의 이벤트를 참조하는 새 개체를 빌드합니다. 이름이 이벤트가 아닌 기존 동기화 개체와 일치하면 생성이 실패합니다. NULL이면 이름은 null이 됩니다.

*lpsa속성*<br/>
이벤트 개체에 대한 보안 특성입니다. 이 구조에 대한 자세한 설명은 Windows SDK의 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 참조하세요.

### <a name="remarks"></a>설명

`CEvent` 개체에 액세스하거나 해제하려면 [CMultiLock](../../mfc/reference/cmultilock-class.md) 또는 [CSingleLock](../../mfc/reference/csinglelock-class.md) 개체를 만들고 [잠금](../../mfc/reference/csinglelock-class.md#lock) 및 [잠금](../../mfc/reference/csinglelock-class.md#unlock) 해제 멤버 함수를 호출합니다.

신호로 `CEvent` 개체의 상태를 변경하려면(스레드는 기다릴 필요가 없습니다) [SetEvent](#setevent) 또는 [PulseEvent](#pulseevent)를 호출합니다. `CEvent` 개체의 상태를 신호가 아닌 상태로 설정하려면(스레드는 기다려야 함) [ResetEvent](#resetevent)를 호출합니다.

> [!IMPORTANT]
> 개체를 `CEvent` 만든 후 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 사용하여 뮤텍스가 아직 존재하지 않았는지 확인합니다. 뮤텍스가 예기치 않게 존재한 경우 불량 프로세스가 쪼그리고 있음을 나타낼 수 있으며 뮤텍스를 악의적으로 사용하려고 할 수 있습니다. 이 경우 권장되는 보안 에 민감한 절차는 핸들을 닫고 개체를 만드는 데 실패한 것처럼 계속하는 것입니다.

## <a name="ceventpulseevent"></a><a name="pulseevent"></a>CEvent::P울스이벤트

이벤트 상태를 신호(사용 가능)로 설정하고 대기 스레드를 해제하고 자동으로 비신호(사용할 수 없음)로 재설정합니다.

```
BOOL PulseEvent();
```

### <a name="return-value"></a>Return Value

함수가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이벤트가 수동인 경우 모든 대기 스레드가 해제되고 이벤트가 신호되지 않은 `PulseEvent` 것으로 설정되고 반환됩니다. 이벤트가 자동으로 수행되면 단일 스레드가 해제되고 이벤트가 신호되지 않은 `PulseEvent` 것으로 설정되고 반환됩니다.

대기 중인 스레드가 없거나 즉시 해제할 수 `PulseEvent` 없는 경우 이벤트의 상태를 신호가 지정되지 않은 상태로 설정하고 반환합니다.

`PulseEvent`기본 Win32 `PulseEvent` 함수를 사용 하 여, 일시적으로 커널 모드 비동기 프로시저 호출에 의해 대기 상태에서 제거 될 수 있습니다. `PulseEvent` 따라서 신뢰할 수 없으므로 새 응용 프로그램에서 사용해서는 안 됩니다. 자세한 내용은 [PulseEvent 기능을](/windows/win32/api/winbase/nf-winbase-pulseevent)참조하십시오.

## <a name="ceventresetevent"></a><a name="resetevent"></a>C이벤트::재설정이벤트

[SetEvent](#setevent) 멤버 함수에서 신호로 명시적으로 설정할 때까지 이벤트의 상태를 비신호로 설정합니다.

```
BOOL ResetEvent();
```

### <a name="return-value"></a>Return Value

함수가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이렇게 하면 이 이벤트에 액세스하려는 모든 스레드가 대기하게 됩니다.

이 멤버 함수는 자동 이벤트에서 사용되지 않습니다.

## <a name="ceventsetevent"></a><a name="setevent"></a>C이벤트::세트이벤트

이벤트 상태를 신호로 설정하여 대기 스레드를 해제합니다.

```
BOOL SetEvent();
```

### <a name="return-value"></a>Return Value

함수가 성공한 경우 0이 아닌 0입니다.

### <a name="remarks"></a>설명

이벤트가 수동인 경우 [ResetEvent가](#resetevent) 호출될 때까지 이벤트가 신호로 유지됩니다. 이 경우 두 개 이상의 스레드를 해제할 수 있습니다. 이벤트가 자동으로 수행되면 단일 스레드가 해제될 때까지 이벤트가 신호로 유지됩니다. 그러면 시스템은 이벤트의 상태를 신호가 없는 상태로 설정합니다. 대기 중인 스레드가 없는 경우 한 스레드가 해제될 때까지 상태가 신호로 유지됩니다.

## <a name="ceventunlock"></a><a name="unlock"></a>C이벤트::잠금 해제

이벤트 개체를 해제합니다.

```
BOOL Unlock();
```

### <a name="return-value"></a>Return Value

스레드가 이벤트 개체를 소유하고 이벤트가 자동 이벤트인 경우 Nonzero입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 잠금 개체를 다시 사용할 경우 완료된 후 해제하는 자동 이벤트를 현재 소유하고 있는 스레드에서 호출합니다. 잠금 개체를 다시 사용하지 않는 경우 잠금 개체의 소멸자가 이 함수를 호출합니다.

## <a name="see-also"></a>참고 항목

[CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
