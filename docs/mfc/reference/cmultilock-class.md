---
title: CMultiLock 클래스
ms.date: 11/04/2016
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
helpviewer_keywords:
- CMultiLock [MFC], CMultiLock
- CMultiLock [MFC], IsLocked
- CMultiLock [MFC], Lock
- CMultiLock [MFC], Unlock
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
ms.openlocfilehash: a051c6a510c53ac0c7c0a6efd8b4b5720080b264
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319707"
---
# <a name="cmultilock-class"></a>CMultiLock 클래스

다중 스레드 프로그램에 대한 액세스를 제어할 때 사용하는 액세스 제어 메커니즘을 나타냅니다.

## <a name="syntax"></a>구문

```
class CMultiLock
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMultiLock : : CMultiLock](#cmultilock)|`CMultiLock` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMultiLock :: 잠금](#islocked)|배열의 특정 동기화 개체가 잠겨 있는지 확인합니다.|
|[CMultiLock : : 잠금](#lock)|동기화 개체의 배열을 기다립니다.|
|[CMultiLock :: 잠금 해제](#unlock)|소유한 동기화 개체를 해제합니다.|

## <a name="remarks"></a>설명

`CMultiLock`기본 클래스가 없습니다.

동기화 클래스 [CSemaphore,](../../mfc/reference/csemaphore-class.md) [CMutex](../../mfc/reference/cmutex-class.md)및 [CEvent를](../../mfc/reference/cevent-class.md)사용 하려면 동기화 `CMultiLock` 개체를 대기 하 고 해제 하는 [CSingleLock](../../mfc/reference/csinglelock-class.md) 개체를 만들 수 있습니다. 특정 `CMultiLock` 시간에 사용할 수 있는 개체가 여러 개인 경우 사용합니다. 한 `CSingleLock` 번에 하나의 개체만 기다려야 하는 경우에 사용합니다.

개체를 `CMultiLock` 사용하려면 먼저 대기하려는 동기화 개체의 배열을 만듭니다. 다음으로 제어된 `CMultiLock` 리소스 클래스의 멤버 함수 내에서 개체의 생성자라고 합니다. 그런 다음 [Lock](#lock) 멤버 함수를 호출하여 리소스를 사용할 수 있는지 확인합니다(신호). 있는 경우 멤버 함수의 나머지 부분을 계속 합니다. 사용 가능한 리소스가 없는 경우 리소스가 해제될 때까지 지정된 시간 동안 기다리거나 실패를 반환합니다. 리소스 사용이 완료되면 `CMultiLock` 개체를 다시 사용할 경우 `CMultiLock` [Unlock](#unlock) 함수를 호출하거나 개체를 소멸하도록 허용합니다.

`CMultiLock`개체는 스레드에 응답할 수 있는 `CEvent` 개체 수가 많을 때 가장 유용합니다. 모든 포인터가 포함된 `CEvent` 배열을 만들고 `Lock`을 호출합니다. 이렇게 하면 이벤트 중 하나가 신호될 때까지 스레드가 대기하게 됩니다.

개체 를 사용하는 `CMultiLock` 방법에 대한 자세한 내용은 [다중 스레딩: 동기화 클래스 를 사용하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CMultiLock`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

## <a name="cmultilockcmultilock"></a><a name="cmultilock"></a>CMultiLock : : CMultiLock

`CMultiLock` 개체를 생성합니다.

```
CMultiLock(
    CSyncObject* ppObjects [ ],
    DWORD dwCount,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>매개 변수

*pp개체*<br/>
대기할 동기화 개체에 대한 포인터 배열입니다. NULL이 될 수 없습니다.

*dwCount*<br/>
*ppObjects의*개체 수 . 0보다 커야 합니다.

*b초기 잠금*<br/>
제공된 개체에 처음 액세스하려고 할지 여부를 지정합니다.

### <a name="remarks"></a>설명

이 함수는 대기할 동기화 개체의 배열을 만든 후 호출됩니다. 일반적으로 스레드 내에서 호출되며 동기화 개체 중 하나가 사용 가능해질 때까지 기다려야 합니다.

## <a name="cmultilockislocked"></a><a name="islocked"></a>CMultiLock :: 잠금

지정된 개체가 신호가 지정되지 않은지(사용할 수 없음)를 결정합니다.

```
BOOL IsLocked(DWORD dwItem);
```

### <a name="parameters"></a>매개 변수

*dw항목*<br/>
상태가 쿼리되는 개체에 해당하는 개체 배열의 인덱스입니다.

### <a name="return-value"></a>Return Value

지정된 개체가 잠겨 있는 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="cmultilocklock"></a><a name="lock"></a>CMultiLock : : 잠금

생성자에 제공된 동기화 개체에 의해 제어되는 하나 이상의 리소스에 `CMultiLock` 액세스하려면 이 함수를 호출합니다.

```
DWORD Lock(
    DWORD dwTimeOut = INFINITE,
    BOOL bWaitForAll = TRUE,
    DWORD dwWakeMask = 0);
```

### <a name="parameters"></a>매개 변수

*dw타임아웃*<br/>
동기화 개체를 사용할 수 있을 때까지 기다리는 시간을 지정합니다(신호). INFINITE인 `Lock` 경우 개체가 신호가 표시될 때까지 기다렸다가 반환합니다.

*b웨이트포올*<br/>
기다렸다가 대기한 모든 개체가 반환하기 전에 동시에 신호를 받아야 하는지 여부를 지정합니다. FALSE인 `Lock` 경우 대기한 개체 중 하나가 신호를 받으면 반환됩니다.

*dw웨이크 마스크*<br/>
대기를 중단할 수 있는 다른 조건을 지정합니다. 이 매개 변수에 사용할 수 있는 옵션의 전체 목록은 Windows SDK의 [MsgWaitForMultipleObjects를](/windows/win32/api/winuser/nf-winuser-msgwaitformultipleobjects) 참조하십시오.

### <a name="return-value"></a>Return Value

실패하면 `Lock` 반환 - 1. 성공하면 다음 값 중 하나를 반환합니다.

- WAIT_OBJECT_0 WAIT_OBJECT_0 + 사이 (개체 수 - 1)

   *bWaitForAll이* TRUE이면 모든 개체가 신호(사용 가능)됩니다. *bWaitForAll이* FALSE인 경우 반환 값 - WAIT_OBJECT_0 신호가 있는 개체의 개체 배열에 있는 인덱스입니다(사용 가능).

- WAIT_OBJECT_0 + (개체 수)

   *dwWakeMask에* 지정된 이벤트는 스레드의 입력 큐에서 사용할 수 있습니다.

- WAIT_ABANDONED_0 WAIT_ABANDONED_0 + 사이 (개체 수 - 1)

   *bWaitForAll이* TRUE이면 모든 개체가 신호를 받고 오브젝트 중 하나 이상이 버려진 뮤텍스 개체입니다. *bWaitForAll이* FALSE인 경우 반환 값 - WAIT_ABANDONED_0 대기를 만족시킨 버려진 뮤텍스 개체의 개체 배열에 있는 인덱스입니다.

- WAIT_TIMEOUT

   *dwTimeOut에* 지정된 시간 시간 간격은 대기가 성공하지 않고 만료되었습니다.

### <a name="remarks"></a>설명

*bWaitForAllTRUE이면* `Lock` 모든 동기화 개체가 동시에 신호가 표시되는 즉시 성공적으로 반환됩니다. *bWaitForAll이* FALSE이면 하나 이상의 동기화 개체가 신호가 표시되는 즉시 `Lock` 반환됩니다.

즉시 `Lock` 반환할 수 없는 경우 반환하기 전에 *dwTimeOut* 매개 변수에 지정된 밀리초 수를 초과하지 않습니다. *dwTimeOut이* 무한인 `Lock` 경우 개체에 대한 액세스가 얻거나 *dwWakeMask에* 지정된 조건이 충족될 때까지 반환되지 않습니다. 그렇지 않으면 `Lock` 동기화 개체를 획득할 수 있으면 성공적으로 반환됩니다. 그렇지 않으면 오류가 반환됩니다.

## <a name="cmultilockunlock"></a><a name="unlock"></a>CMultiLock :: 잠금 해제

에서 소유한 동기화 개체를 `CMultiLock`해제합니다.

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>매개 변수

*l카운트*<br/>
릴리스할 참조 개수입니다. 0보다 커야 합니다. 지정된 양으로 인해 개체의 수가 최대값을 초과하는 경우 개수가 변경되지 않고 함수가 FALSE를 반환합니다.

*lPrevCount*<br/>
동기화 개체에 대한 이전 개수를 수신할 변수를 가리킵니다. NULL이면 이전 카운트가 반환되지 않습니다.

### <a name="return-value"></a>Return Value

함수가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 `CMultiLock`'의 소멸자'에 의해 호출됩니다.

첫 번째 `Unlock` 형식은 에서 관리하는 동기화 개체의 잠금을 해제하려고 시도합니다. `CMultiLock` 두 번째 `Unlock` 형식은 에서 `CSemaphore` 소유한 `CMultiLock`개체의 잠금을 해제하려고 시도합니다. 잠긴 `CMultiLock` `CSemaphore` 개체를 소유하지 않으면 함수가 FALSE를 반환합니다. 그렇지 않으면 TRUE를 반환합니다. *lCount* 및 *lpPrevCount는* [CSingleLock::Unlock의](../../mfc/reference/csinglelock-class.md#unlock)매개 변수와 정확히 동일합니다. 두 번째 `Unlock` 형식은 다중 잠금 상황에 거의 적용되지 않습니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)
