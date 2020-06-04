---
title: CSyncObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
ms.openlocfilehash: ebfbc185cdca2effc96ce2e6d96d05f997c52bf7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365978"
---
# <a name="csyncobject-class"></a>CSyncObject 클래스

Win32의 동기화 개체에 일반적인 기능을 제공하는 순수 가상 클래스입니다.

## <a name="syntax"></a>구문

```
class CSyncObject : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CSync 개체::CSync 개체](#csyncobject)|`CSyncObject` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C싱크 오브젝트::잠금](#lock)|동기화 개체에 대한 액세스 권한을 얻습니다.|
|[CSyncObject::잠금 해제](#unlock)|동기화 개체에 대한 액세스 권한을 얻습니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CSyncObject::연산자 핸들](#operator_handle)|동기화 개체에 대한 액세스를 제공합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C싱크 오브젝트:m_hObject](#m_hobject)|기본 동기화 개체에 대한 핸들입니다.|

## <a name="remarks"></a>설명

Microsoft 재단 클래스 라이브러리는 에서 `CSyncObject`파생된 여러 클래스를 제공합니다. 다음은 [CEvent,](../../mfc/reference/cevent-class.md) [CMutex,](../../mfc/reference/cmutex-class.md) [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)및 [Cemaphore입니다.](../../mfc/reference/csemaphore-class.md)

동기화 개체를 사용하는 방법에 대한 자세한 내용은 [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

## <a name="csyncobjectcsyncobject"></a><a name="csyncobject"></a>CSync 개체::CSync 개체

제공된 이름으로 동기화 개체를 생성합니다.

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>매개 변수

*pstrName*<br/>
개체 이름입니다. NULL이면 *pstrName은* null이 됩니다.

## <a name="csyncobjectlock"></a><a name="lock"></a>C싱크 오브젝트::잠금

이 함수를 호출하여 동기화 개체에서 제어하는 리소스에 액세스합니다.

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>매개 변수

*dw타임아웃*<br/>
동기화 개체를 사용할 수 있을 때까지 기다리는 시간(신호)을 지정합니다. INFINITE인 `Lock` 경우 개체가 신호가 표시될 때까지 기다렸다가 반환합니다.

### <a name="return-value"></a>Return Value

함수가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

동기화 개체가 신호되면 성공적으로 `Lock` 반환되고 스레드가 개체를 소유합니다. 동기화 개체가 신호되지 않은 경우(사용할 `Lock` 수 없음) 동기화 개체가 *dwTimeOut* 매개 변수에 지정된 밀리초 수까지 신호가 표시될 때까지 기다립니다. 동기화 개체가 지정된 시간 내에 신호를 받지 않으면 오류가 `Lock` 반환됩니다.

## <a name="csyncobjectm_hobject"></a><a name="m_hobject"></a>C싱크 오브젝트:m_hObject

기본 동기화 개체에 대한 핸들입니다.

```
HANDLE m_hObject;
```

## <a name="csyncobjectoperator-handle"></a><a name="operator_handle"></a>CSyncObject::연산자 핸들

이 연산자에서 개체의 `CSyncObject` 핸들을 가져옵니다.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Return Value

성공하면 동기화 개체의 핸들; 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

핸들을 사용하여 Windows API를 직접 호출할 수 있습니다.

## <a name="csyncobjectunlock"></a><a name="unlock"></a>CSyncObject::잠금 해제

매개 변수가 `Unlock` 없는 선언은 순수 가상 함수이며 `CSyncObject`에서 파생된 모든 클래스에서 재정의해야 합니다.

```
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,
    LPLONG lpPrevCount = NULL);
```

### <a name="parameters"></a>매개 변수

*l카운트*<br/>
기본 구현에서 사용되지 않습니다.

*lpPrevCount*<br/>
기본 구현에서 사용되지 않습니다.

### <a name="return-value"></a>Return Value

기본 구현은 항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

두 매개 변수가 있는 선언의 기본 구현은 항상 TRUE를 반환합니다. 이 함수는 호출 스레드가 소유한 동기화 개체에 대한 액세스를 해제하기 위해 호출됩니다. 두 번째 선언은 제어된 리소스에 대해 두 개 이상의 액세스를 허용하는 세마포와 같은 동기화 개체에 대해 제공됩니다.

## <a name="see-also"></a>참고 항목

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
