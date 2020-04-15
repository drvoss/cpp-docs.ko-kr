---
title: C임계 섹션 클래스
ms.date: 11/04/2016
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
ms.openlocfilehash: d79199a332f6930619e6b4995b04bc590b6ea580
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369373"
---
# <a name="ccriticalsection-class"></a>C임계 섹션 클래스

한 번에 하나의 스레드가 리소스 또는 코드 섹션에 액세스할 수 있도록 하는 동기화 개체인 "중요 섹션"을 나타냅니다.

## <a name="syntax"></a>구문

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C임계 섹션::C임계 섹션](#ccriticalsection)|`CCriticalSection` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C임계 섹션::잠금](#lock)|`CCriticalSection` 개체에 대한 액세스 권한을 얻는 데 사용합니다.|
|[C임계 섹션::잠금 해제](#unlock)|`CCriticalSection` 개체를 해제합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C임계 섹션::연산자 CRITICAL_SECTION*](#operator_critical_section_star)|내부 CRITICAL_SECTION 개체에 대한 포인터를 검색합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C임계 섹션::m_sect](#m_sect)|CRITICAL_SECTION 개체입니다.|

## <a name="remarks"></a>설명

중요한 섹션은 한 번에 하나의 스레드만 데이터 또는 다른 제어된 리소스를 수정할 수 있는 경우에 유용합니다. 예를 들어 연결된 목록에 노드를 추가하는 것은 한 번에 하나의 스레드에서만 허용해야 하는 프로세스입니다. 개체를 `CCriticalSection` 사용하여 연결된 목록을 제어하면 한 번에 하나의 스레드만 목록에 액세스할 수 있습니다.

> [!NOTE]
> `CCriticalSection` 클래스의 기능은 실제 Win32 CRITICAL_SECTION 개체에 의해 제공됩니다.

중요 섹션은 속도가 중요하고 프로세스가 경계를 넘어 리소스가 사용되지 않을 때 뮤텍스 대신 [사용됩니다(CMutex](../../mfc/reference/cmutex-class.md)참조).

개체를 `CCriticalSection` 사용하는 방법에는 독립 실행형 및 클래스에 포함된 두 가지 방법이 있습니다.

- 독립 실행형 메서드 독립 실행형 `CCriticalSection` 개체를 `CCriticalSection` 사용 하려면 필요할 때 개체를 생성 합니다. 생성자에서 성공적으로 반환된 후 [Lock](#lock)을 호출하여 개체를 명시적으로 잠급전지 임계 섹션에 액세스가 완료되면 [잠금 해제를](#unlock) 호출합니다. 이 방법은 소스 코드를 읽는 사람에게 는 명확하지만 액세스 전후에 중요한 섹션을 잠그고 잠금을 해제해야 하므로 오류가 발생하기 쉽습니다.

   보다 바람직한 방법은 [CSingleLock](../../mfc/reference/csinglelock-class.md) 클래스를 사용하는 것입니다. 또한 `Lock` 메서드와 `Unlock` 메서드가 있지만 예외가 발생하면 리소스 잠금 해제에 대해 걱정할 필요가 없습니다.

- 포함된 메서드 클래스에 -type 데이터 멤버를 `CCriticalSection`추가하고 필요할 때 데이터 멤버를 잠그면 여러 스레드와 클래스를 공유할 수도 있습니다.

개체 사용에 `CCriticalSection` 대한 자세한 내용은 [다중 스레딩: 동기화 클래스 를 사용하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

## <a name="ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a>C임계 섹션::C임계 섹션

`CCriticalSection` 개체를 생성합니다.

```
CCriticalSection();
```

### <a name="remarks"></a>설명

개체에 `CCriticalSection` 액세스하거나 해제하려면 [CSingleLock](../../mfc/reference/csinglelock-class.md) 개체를 만들고 [잠금](../../mfc/reference/csinglelock-class.md#lock) 및 [잠금](../../mfc/reference/csinglelock-class.md#unlock) 해제 멤버 함수를 호출합니다. 개체가 `CCriticalSection` 독립 실행형으로 사용되는 경우 [Unlock](#unlock) 멤버 함수를 호출하여 해제합니다.

생성자가 필요한 시스템 메모리를 할당하지 못하면 메모리 [예외(CMemoryException](../../mfc/reference/cmemoryexception-class.md)형식)가 자동으로 throw됩니다.

### <a name="example"></a>예제

  [CCriticalSection::Lock](#lock)에 대한 예제를 참조하십시오.

## <a name="ccriticalsectionlock"></a><a name="lock"></a>C임계 섹션::잠금

이 멤버 함수를 호출하여 임계 섹션 개체에 액세스합니다.

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>매개 변수

*dw타임아웃*<br/>
`Lock`이 매개 변수 값을 무시합니다.

### <a name="return-value"></a>Return Value

함수가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

`Lock`는 임계 섹션 개체가 신호(사용 가능)가 될 때까지 반환되지 않는 차단 호출입니다.

시간 대기가 필요한 경우 개체 대신 [CMutex](../../mfc/reference/cmutex-class.md) 개체를 `CCriticalSection` 사용할 수 있습니다.

필요한 `Lock` 시스템 메모리를 할당하지 못하면 메모리 예외(CMemoryException 형식)가 자동으로 throw됩니다. [CMemoryException](../../mfc/reference/cmemoryexception-class.md)

### <a name="example"></a>예제

이 예제에서는 공유 `_strShared` `CCriticalSection` 개체를 사용하여 공유 리소스(정적 개체)에 대한 액세스를 제어하여 중첩된 임계 섹션 접근 방식을 보여 줍니다. 이 `SomeMethod` 함수는 안전한 방식으로 공유 리소스를 업데이트하는 것을 보여 줍니다.

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

## <a name="ccriticalsectionm_sect"></a><a name="m_sect"></a>C임계 섹션::m_sect

모든 `CCriticalSection` 메서드에서 사용되는 임계 섹션 개체를 포함합니다.

```
CRITICAL_SECTION m_sect;
```

## <a name="ccriticalsectionoperator-critical_section"></a><a name="operator_critical_section_star"></a>C임계 섹션::연산자 CRITICAL_SECTION*

CRITICAL_SECTION 개체를 검색합니다.

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>설명

이 함수를 호출하여 내부 CRITICAL_SECTION 개체에 대한 포인터를 검색합니다.

## <a name="ccriticalsectionunlock"></a><a name="unlock"></a>C임계 섹션::잠금 해제

다른 `CCriticalSection` 스레드에서 사용할 개체를 해제합니다.

```
BOOL Unlock();
```

### <a name="return-value"></a>Return Value

개체가 스레드에 `CCriticalSection` 의해 소유되고 릴리스가 성공한 경우 Nonzero입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

`CCriticalSection` 독립 실행형으로 사용되는 경우 `Unlock` 임계 섹션에 의해 제어되는 리소스 사용을 완료한 직후에 호출해야 합니다. [CSingleLock](../../mfc/reference/csinglelock-class.md) 개체를 사용 하는 `CCriticalSection::Unlock` 경우 잠금 개체의 `Unlock` 멤버 함수에 의해 호출 됩니다.

### <a name="example"></a>예제

  [CCriticalSection::Lock](#lock)에 대한 예제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CMutex 클래스](../../mfc/reference/cmutex-class.md)
