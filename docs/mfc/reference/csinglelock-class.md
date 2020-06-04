---
title: CSingleLock 클래스
ms.date: 11/04/2016
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
ms.openlocfilehash: 231397228d94e58665602453b5d377571e24a967
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318265"
---
# <a name="csinglelock-class"></a>CSingleLock 클래스

다중 스레드 프로그램에서 한 리소스에 대한 액세스를 제어할 때 사용하는 액세스 제어 메커니즘을 나타냅니다.

## <a name="syntax"></a>구문

```
class CSingleLock
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CSingleLock::CSingleLock](#csinglelock)|`CSingleLock` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSingleLock:::잠금](#islocked)|개체가 잠겨 있는지 여부를 확인합니다.|
|[CSingleLock::잠금](#lock)|동기화 개체에서 대기합니다.|
|[CSingleLock::잠금 해제](#unlock)|동기화 개체를 해제합니다.|

## <a name="remarks"></a>설명

`CSingleLock`기본 클래스가 없습니다.

동기화 클래스 [CSemaphore,](../../mfc/reference/csemaphore-class.md) [CMutex,](../../mfc/reference/cmutex-class.md) [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)및 [CEvent를](../../mfc/reference/cevent-class.md)사용 하려면 대기 `CSingleLock` 하 고 동기화 개체를 해제 하는 [CMultiLock](../../mfc/reference/cmultilock-class.md) 개체를 만들어야 합니다. 한 `CSingleLock` 번에 하나의 개체만 기다려야 하는 경우에 사용합니다. 특정 `CMultiLock` 시간에 사용할 수 있는 개체가 여러 개인 경우 사용합니다.

개체를 `CSingleLock` 사용하려면 제어된 리소스 클래스의 멤버 함수 내에서 해당 생성기를 호출합니다. 그런 다음 [IsLocked](#islocked) 멤버 함수를 호출하여 리소스를 사용할 수 있는지 확인합니다. 이 경우 멤버 함수의 나머지 부분을 계속합니다. 리소스를 사용할 수 없는 경우 리소스가 해제될 때까지 지정된 시간 동안 기다리거나 실패를 반환합니다. 리소스 사용이 완료되면 `CSingleLock` 개체를 다시 사용할 경우 `CSingleLock` [Unlock](#unlock) 함수를 호출하거나 개체를 소멸하도록 허용합니다.

`CSingleLock`개체에는 [CSyncObject](../../mfc/reference/csyncobject-class.md)에서 파생된 개체가 필요합니다. 일반적으로 제어된 리소스 클래스의 데이터 멤버입니다. 개체 를 사용하는 `CSingleLock` 방법에 대한 자세한 내용은 [다중 스레딩: 동기화 클래스 를 사용하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CSingleLock`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

## <a name="csinglelockcsinglelock"></a><a name="csinglelock"></a>CSingleLock::CSingleLock

`CSingleLock` 개체를 생성합니다.

```
explicit CSingleLock(
    CSyncObject* pObject,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>매개 변수

*pObject*<br/>
액세스할 동기화 개체를 가리킵니다. NULL이 될 수 없습니다.

*b초기 잠금*<br/>
제공된 개체에 처음 액세스하려고 할지 여부를 지정합니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 제어된 리소스의 액세스 멤버 함수 내에서 호출됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]

## <a name="csinglelockislocked"></a><a name="islocked"></a>CSingleLock:::잠금

`CSingleLock` 개체와 연결된 개체가 신호가 지정되지 않은지 확인합니다(사용할 수 없음).

```
BOOL IsLocked();
```

### <a name="return-value"></a>Return Value

개체가 잠겨 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]

## <a name="csinglelocklock"></a><a name="lock"></a>CSingleLock::잠금

생성자에 제공된 동기화 개체에 의해 제어되는 리소스에 `CSingleLock` 대한 액세스를 얻으려면 이 함수를 호출합니다.

```
BOOL Lock(DWORD dwTimeOut = INFINITE);
```

### <a name="parameters"></a>매개 변수

*dw타임아웃*<br/>
동기화 개체를 사용할 수 있을 때까지 기다리는 시간을 지정합니다(신호). INFINITE인 `Lock` 경우 개체가 신호가 표시될 때까지 기다렸다가 반환합니다.

### <a name="return-value"></a>Return Value

함수가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

동기화 개체가 신호되면 성공적으로 `Lock` 반환되고 스레드가 개체를 소유합니다. 동기화 개체가 신호되지 않은 경우(사용할 `Lock` 수 없음) 동기화 개체가 *dwTimeOut* 매개 변수에 지정된 밀리초 수까지 신호가 표시될 때까지 기다립니다. 동기화 개체가 지정된 시간 내에 신호를 받지 않으면 오류가 `Lock` 반환됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="csinglelockunlock"></a><a name="unlock"></a>CSingleLock::잠금 해제

에서 소유한 동기화 개체를 `CSingleLock`해제합니다.

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>매개 변수

*l카운트*<br/>
릴리스할 액세스 수입니다. 0보다 커야 합니다. 지정된 양으로 인해 개체의 수가 최대값을 초과하는 경우 개수가 변경되지 않고 함수가 FALSE를 반환합니다.

*lPrevCount*<br/>
동기화 개체의 이전 개수를 수신할 변수를 가리킵니다. NULL이면 이전 카운트가 반환되지 않습니다.

### <a name="return-value"></a>Return Value

함수가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 `CSingleLock`'의 소멸자'에 의해 호출됩니다.

세마포의 두 개 이상의 액세스 수를 해제해야 하는 경우 `Unlock` 두 번째 형식을 사용하고 릴리스할 액세스 수를 지정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CMultiLock 클래스](../../mfc/reference/cmultilock-class.md)
