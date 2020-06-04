---
title: CMutex 클래스
ms.date: 11/04/2016
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
ms.openlocfilehash: 2d6f637ab4828b3e70df205ebf359ae45a940d60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363287"
---
# <a name="cmutex-class"></a>CMutex 클래스

하나의 스레드가 리소스에 대해 상호 독점적으로 액세스할 수 있도록 허용하는 동기화 개체인 "뮤텍스"를 나타냅니다.

## <a name="syntax"></a>구문

```
class CMutex : public CSyncObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMutex:::CMutex](#cmutex)|`CMutex` 개체를 생성합니다.|

## <a name="remarks"></a>설명

뮤텍스는 한 번에 하나의 스레드만 데이터 또는 다른 제어 된 리소스를 수정할 수 있는 경우에 유용합니다. 예를 들어 연결된 목록에 노드를 추가하는 것은 한 번에 하나의 스레드에서만 허용해야 하는 프로세스입니다. 개체를 `CMutex` 사용하여 연결된 목록을 제어하면 한 번에 하나의 스레드만 목록에 액세스할 수 있습니다.

개체를 `CMutex` 사용하려면 필요할 `CMutex` 때 개체를 생성합니다. 대기할 뮤텍스의 이름을 지정하고 응용 프로그램에서 처음에 해당 뮤텍스이름을 소유해야 합니다. 그런 다음 생성자가 반환될 때 뮤텍스에 액세스할 수 있습니다. [CSyncObject:::제어된](../../mfc/reference/csyncobject-class.md#unlock) 리소스에 액세스하는 작업이 완료되면 잠금을 해제합니다.

개체를 사용하는 `CMutex` 다른 방법은 컨트롤하려는 클래스에 형식의 `CMutex` 변수를 데이터 멤버로 추가하는 것입니다. 제어된 개체를 구성하는 동안 뮤텍스가 `CMutex` 처음 소유되어 있는지, 뮤텍스의 이름(프로세스 경계를 넘어 사용되는 경우) 및 원하는 보안 특성을 지정하는 데이터 멤버의 생성자에게 호출합니다.

이러한 방식으로 개체에 의해 제어되는 리소스에 `CMutex` 액세스하려면 먼저 리소스의 액세스 멤버 함수에서 [CSingleLock](../../mfc/reference/csinglelock-class.md) 또는 [CMultiLock](../../mfc/reference/cmultilock-class.md) 형식의 변수를 만듭니다. 그런 다음 lock 개체의 `Lock` 멤버 함수(예: [CSingleLock::Lock)를](../../mfc/reference/csinglelock-class.md#lock)호출합니다. 이 시점에서 스레드는 리소스에 대한 액세스 권한을 얻거나, 리소스가 해제될 때까지 기다렸다가 액세스 권한을 얻거나, 리소스가 해제되고 시간 시간이 지나갈 때까지 기다리며 리소스에 대한 액세스 권한을 얻지 못합니다. 어쨌든 리소스는 스레드에서 안전한 방식으로 액세스되었습니다. 리소스를 해제하려면 잠금 개체의 `Unlock` 멤버 함수(예: [CSingleLock::Unlock)를](../../mfc/reference/csinglelock-class.md#unlock)사용하거나 잠금 개체가 범위를 벗어나도록 허용합니다.

개체 사용에 `CMutex` 대한 자세한 내용은 [다중 스레딩: 동기화 클래스 를 사용하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

## <a name="cmutexcmutex"></a><a name="cmutex"></a>CMutex:::CMutex

명명된 개체 또는 `CMutex` 명명되지 않은 개체를 생성합니다.

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>매개 변수

*b처음 소유*<br/>
`CMutex` 처음에 개체를 만드는 스레드가 뮤텍스에서 제어하는 리소스에 액세스할 수 있는지 지정합니다.

*lpszName*<br/>
`CMutex` 개체의 이름입니다. 이름이 같은 다른 뮤텍스가 있는 경우 개체가 프로세스 경계를 넘어 사용되는 경우 *lpszName을* 제공해야 합니다. **NULL이면**뮤텍스의 이름이 지정되지 않습니다. 이름이 기존 뮤텍스와 일치하면 생성자는 해당 `CMutex` 이름의 뮤텍스를 참조하는 새 개체를 빌드합니다. 이름이 뮤텍스가 아닌 기존 동기화 개체와 일치하면 생성이 실패합니다.

*lpsa속성*<br/>
뮤텍스 개체에 대한 보안 특성입니다. 이 구조에 대한 자세한 설명은 Windows SDK의 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 참조하세요.

### <a name="remarks"></a>설명

`CMutex` 개체에 액세스하거나 해제하려면 [CMultiLock](../../mfc/reference/cmultilock-class.md) 또는 [CSingleLock](../../mfc/reference/csinglelock-class.md) 개체를 만들고 [잠금](../../mfc/reference/csinglelock-class.md#lock) 및 [잠금](../../mfc/reference/csinglelock-class.md#unlock) 해제 멤버 함수를 호출합니다. 개체가 `CMutex` 독립 실행형으로 사용되는 경우 `Unlock` 해당 멤버 함수를 호출하여 해제합니다.

> [!IMPORTANT]
> 개체를 `CMutex` 만든 후 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 사용하여 뮤텍스가 아직 존재하지 않았는지 확인합니다. 뮤텍스가 예기치 않게 존재한 경우 불량 프로세스가 쪼그리고 있음을 나타낼 수 있으며 뮤텍스를 악의적으로 사용하려고 할 수 있습니다. 이 경우 권장되는 보안 에 민감한 절차는 핸들을 닫고 개체를 만드는 데 실패한 것처럼 계속하는 것입니다.

## <a name="see-also"></a>참고 항목

[CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
