---
title: C세마포어 클래스
ms.date: 11/04/2016
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
ms.openlocfilehash: 26e1fd55d321b221f4732874d57d02a79c4c6398
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318508"
---
# <a name="csemaphore-class"></a>C세마포어 클래스

클래스의 `CSemaphore` 개체는 "semaphore"를 나타내며, 하나 이상의 프로세스에서 제한된 수의 스레드가 현재 지정된 리소스에 액세스하는 스레드 수의 수에 대해 유지를 허용하는 동기화 개체입니다.

## <a name="syntax"></a>구문

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C세마포어::C세마포어](#csemaphore)|`CSemaphore` 개체를 생성합니다.|

## <a name="remarks"></a>설명

세마포는 제한된 수의 사용자만 지원할 수 있는 공유 리소스에 대한 액세스를 제어하는 데 유용합니다. 개체의 `CSemaphore` 현재 수는 허용되는 추가 사용자 수입니다. 개수가 0에 도달하면 `CSemaphore` 개체에 의해 제어되는 리소스를 사용하려는 모든 시도가 시스템 큐에 삽입되고 시간 초과되거나 개수가 0 이상으로 증가할 때까지 기다립니다. `CSemaphore` 제어된 리소스에 한 번에 액세스할 수 있는 최대 사용자 수는 개체를 구성하는 동안 지정됩니다.

개체를 `CSemaphore` 사용하려면 필요할 `CSemaphore` 때 개체를 생성합니다. 대기하려는 세마포의 이름을 지정하고 응용 프로그램에서 처음에 세마포를 소유해야 합니다. 그런 다음 생성자가 반환될 때 세마포에 액세스할 수 있습니다. [CSyncObject:::제어된](../../mfc/reference/csyncobject-class.md#unlock) 리소스에 액세스하는 작업이 완료되면 잠금을 해제합니다.

개체를 사용하는 `CSemaphore` 다른 방법은 컨트롤하려는 클래스에 형식의 `CSemaphore` 변수를 데이터 멤버로 추가하는 것입니다. 제어된 개체를 구성하는 동안 초기 액세스 `CSemaphore` 수, 최대 액세스 수, 세마포이름(프로세스 경계를 넘어 사용되는 경우) 및 원하는 보안 특성을 지정하는 데이터 멤버의 생성자에게 호출합니다.

이러한 방식으로 개체에 의해 제어되는 리소스에 `CSemaphore` 액세스하려면 먼저 리소스의 액세스 멤버 함수에서 [CSingleLock](../../mfc/reference/csinglelock-class.md) 또는 [CMultiLock](../../mfc/reference/cmultilock-class.md) 형식의 변수를 만듭니다. 그런 다음 lock 개체의 `Lock` 멤버 함수(예: [CSingleLock::Lock)를](../../mfc/reference/csinglelock-class.md#lock)호출합니다. 이 시점에서 스레드는 리소스에 대한 액세스 권한을 얻거나, 리소스가 해제될 때까지 기다렸다가 액세스 권한을 얻거나, 리소스가 해제되고 시간 시간이 지나갈 때까지 기다리며 리소스에 대한 액세스 권한을 얻지 못합니다. 어쨌든 리소스는 스레드에서 안전한 방식으로 액세스되었습니다. 리소스를 해제하려면 잠금 개체의 `Unlock` 멤버 함수(예: [CSingleLock::Unlock)를](../../mfc/reference/csinglelock-class.md#unlock)사용하거나 잠금 개체가 범위를 벗어나도록 허용합니다.

또는 제어된 리소스에 `CSemaphore` 액세스하기 전에 개체를 독립 실행형으로 만들고 명시적으로 액세스할 수 있습니다. 이 방법은 소스 코드를 읽는 사람에게 는 명확하지만 오류가 발생하기 쉽습니다.

개체 를 사용하는 `CSemaphore` 방법에 대한 자세한 내용은 [다중 스레딩: 동기화 클래스 를 사용하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

## <a name="csemaphorecsemaphore"></a><a name="csemaphore"></a>C세마포어::C세마포어

명명된 개체 또는 `CSemaphore` 명명되지 않은 개체를 생성합니다.

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>매개 변수

*l 초기 카운트*<br/>
세마포에 대한 초기 사용 횟수입니다. 0보다 크거나 같아야 하며 *lMaxCount*보다 작거나 같아야 합니다.

*lMaxCount*<br/>
세마포의 최대 사용 횟수입니다. 0보다 커야 합니다.

*pstrName*<br/>
세마포의 이름입니다. 세마포가 프로세스 경계를 넘어 액세스될 경우 제공해야 합니다. 이 `NULL`경우 개체의 이름이 지정되지 않습니다. 이름이 기존 세마포와 일치하면 생성자는 해당 이름의 `CSemaphore` 세마포를 참조하는 새 개체를 빌드합니다. 이름이 세마포가 아닌 기존 동기화 개체와 일치하면 구성이 실패합니다.

*lpsa속성*<br/>
세마포 개체에 대한 보안 특성입니다. 이 구조에 대한 자세한 설명은 Windows SDK의 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 참조하세요.

### <a name="remarks"></a>설명

`CSemaphore` 개체에 액세스하거나 해제하려면 [CMultiLock](../../mfc/reference/cmultilock-class.md) 또는 [CSingleLock](../../mfc/reference/csinglelock-class.md) 개체를 만들고 [잠금](../../mfc/reference/csinglelock-class.md#lock) 및 [잠금](../../mfc/reference/csinglelock-class.md#unlock) 해제 멤버 함수를 호출합니다.

> [!IMPORTANT]
> 개체를 `CSemaphore` 만든 후 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 사용하여 뮤텍스가 아직 존재하지 않았는지 확인합니다. 뮤텍스가 예기치 않게 존재한 경우 불량 프로세스가 쪼그리고 있음을 나타낼 수 있으며 뮤텍스를 악의적으로 사용하려고 할 수 있습니다. 이 경우 권장되는 보안 에 민감한 절차는 핸들을 닫고 개체를 만드는 데 실패한 것처럼 계속하는 것입니다.

## <a name="see-also"></a>참고 항목

[CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
