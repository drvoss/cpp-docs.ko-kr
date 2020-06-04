---
title: CFileTime 클래스
ms.date: 10/18/2018
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
ms.openlocfilehash: fd19d941365c7772363417ce3e9225bd9b0300b2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748846"
---
# <a name="cfiletime-class"></a>CFileTime 클래스

이 클래스는 파일과 연결된 날짜 및 시간 값을 관리하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
class CFileTime :  public FILETIME
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C파일타임::CFileTime](#cfiletime)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CFile시간::현재 시간 가져옵니다](#getcurrenttime)|이 정적 함수를 `CFileTime` 호출하여 현재 시스템 날짜 및 시간을 나타내는 개체를 검색합니다.|
|[CFileTime::GetTime](#gettime)|이 메서드를 호출하여 개체에서 시간을 검색합니다. `CFileTime`|
|[C파일시간::로컬토UTC](#localtoutc)|이 메서드를 호출하여 UTC(조정된 유니버설 타임)를 기반으로 로컬 파일 시간을 파일 시간으로 변환합니다.|
|[CFileTime::설정 시간](#settime)|이 메서드를 호출하여 개체에 저장된 `CFileTime` 날짜와 시간을 설정합니다.|
|[C파일타임::UTCToLocal](#utctolocal)|이 메서드를 호출하여 UTC(조정된 유니버설 타임)를 기준으로 시간을 현지 파일 시간으로 변환합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CFileTime::연산자 -](#operator_-)|이 연산자는 `CFileTime` 또는 `CFileTimeSpan` 개체에 대한 빼기를 수행하는 데 사용됩니다.|
|[CFileTime::연산자 !=](#operator_neq)|이 연산자는 `CFileTime` 두 개체를 비교하여 부등가등입니다.|
|[CFileTime::연산자 +](#operator_add)|이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하는 데 사용됩니다.|
|[CFileTime::연산자 +=](#operator_add_eq)|이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하고 결과를 현재 개체에 할당하는 데 사용됩니다.|
|[CFileTime::연산자&lt;](#operator_lt)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 작은 값을 확인합니다.|
|[CFileTime::연산자&lt;=](#operator_lt_eq)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 작거나 같은 값을 확인합니다.|
|[CFileTime::연산자 =](#operator_eq)|할당 연산자입니다.|
|[CFileTime::연산자 -=](#operator_-_eq)|이 연산자는 `CFileTimeSpan` 개체에 대한 빼기를 수행하고 결과를 현재 개체에 할당하는 데 사용됩니다.|
|[CFileTime::연산자 ==](#operator_eq_eq)|이 연산자는 두 `CFileTime` 개체가 같은지 비교합니다.|
|[CFileTime::연산자&gt;](#operator_gt)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 큰 값을 확인합니다.|
|[CFileTime::연산자&gt;=](#operator_gt_eq)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 크거나 같은 값을 확인합니다.|

### <a name="public-constants"></a>공용 상수

|속성|Description|
|----------|-----------------|
|[CFileTime::D](#day)|하루를 구성하는 100나노초 간격의 수를 저장하는 정적 데이터 멤버입니다.|
|[CFile시간::시간](#hour)|1시간을 구성하는 100나노초 간격의 수를 저장하는 정적 데이터 멤버입니다.|
|[C파일시간::밀리초](#millisecond)|1밀리초를 구성하는 100나노초 간격의 수를 저장하는 정적 데이터 멤버입니다.|
|[CFile시간::분](#minute)|1분을 구성하는 100나노초 간격의 수를 저장하는 정적 데이터 멤버입니다.|
|[CFile시간::두 번째](#second)|1초를 구성하는 100나노초 간격의 수를 저장하는 정적 데이터 멤버입니다.|
|[CFile시간::주](#week)|100나노초 간격을 저장하는 정적 데이터 멤버입니다.|

## <a name="remarks"></a>설명

이 클래스는 파일 생성, 액세스 및 수정과 관련된 날짜 및 시간 값을 관리하는 메서드를 제공합니다. 이 클래스의 메서드 와 데이터는 상대 `CFileTimeSpan` 시간 값을 처리하는 개체와 함께 자주 사용됩니다.

날짜 및 시간 값은 1601년 1월 1일 이후100나노초 간격의 수를 나타내는 64비트 값으로 저장됩니다. 조정된 유니버설 타임(UTC) 형식입니다.

계산을 단순화하기 위해 다음과 같은 정적 const 멤버 변수가 제공됩니다.

|멤버 변수|100나노초 간격수|
|---------------------|-----------------------------------------|
|Millisecond|10000|
|초|밀리초 \* 1,000|
|Minute|두 \* 번째 60|
|Hour|분 \* 60|
|일|시간 \* 24|
|Week|제 \* 7일|

**참고 사항** 모든 파일 시스템이 생성 및 마지막 액세스 시간을 기록할 수 있는 것은 아니며 모든 파일 시스템이 동일한 방식으로 기록하는 것은 아닙니다. 예를 들어 Windows NT FAT 파일 시스템에서 생성 시간은 10밀리초의 해상도를 가지며 쓰기 시간은 2초의 해상도를 가지며 액세스 시간은 1일(액세스 날짜)의 해상도를 가짐을 가짐입니다. NTFS의 액세스 시간은 1시간의 해상도입니다. 또한 FAT는 현지 시간으로 디스크의 시간을 기록하지만 NTFS는 UTC의 디스크에 시간을 기록합니다. 자세한 내용은 [파일 시간](/windows/win32/SysInfo/file-times)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`FILETIME`

`CFileTime`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀타임.h

## <a name="cfiletimecfiletime"></a><a name="cfiletime"></a>C파일타임::CFileTime

생성자입니다.

```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>매개 변수

*피트*<br/>
[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 구조입니다.

*n시간*<br/>
64비트 값으로 표현된 날짜 및 시간입니다.

### <a name="remarks"></a>설명

`FILETIME` 개체는 `CFileTime` 구조체에서 기존 날짜 및 시간을 사용하여 만들거나 64비트 값(로컬 또는 조정된 유니버설 타임(UTC) 시간 형식)으로 표현할 수 있습니다. 기본 생성자는 시간을 0으로 설정합니다.

## <a name="cfiletimeday"></a><a name="day"></a>CFileTime::D

하루를 구성하는 100나노초 간격의 수를 저장하는 정적 데이터 멤버입니다.

```
static const ULONGLONG Day = Hour* 24;
```

### <a name="example"></a>예제

[CFileTime::밀리초의](#millisecond)예제를 참조하십시오.

## <a name="cfiletimegetcurrenttime"></a><a name="getcurrenttime"></a>CFile시간::현재 시간 가져옵니다

이 정적 함수를 `CFileTime` 호출하여 현재 시스템 날짜 및 시간을 나타내는 개체를 검색합니다.

```
static CFileTime GetCurrentTime() throw();
```

### <a name="return-value"></a>Return Value

조정된 유니버설 타임(UTC) 형식으로 현재 시스템 날짜와 시간을 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]

## <a name="cfiletimegettime"></a><a name="gettime"></a>CFileTime::GetTime

이 메서드를 호출하여 개체에서 시간을 검색합니다. `CFileTime`

```
ULONGLONG GetTime() const throw();
```

### <a name="return-value"></a>Return Value

날짜와 시간을 로컬 또는 조정된 유니버설 타임(UTC) 형식으로 사용할 수 있는 64비트 번호로 반환합니다.

## <a name="cfiletimehour"></a><a name="hour"></a>CFile시간::시간

1시간을 구성하는 100나노초 간격의 수를 저장하는 정적 데이터 멤버입니다.

```
static const ULONGLONG Hour = Minute* 60;
```

### <a name="example"></a>예제

[CFileTime::밀리초의](#millisecond)예제를 참조하십시오.

## <a name="cfiletimelocaltoutc"></a><a name="localtoutc"></a>C파일시간::로컬토UTC

이 메서드를 호출하여 UTC(조정된 유니버설 타임)를 기반으로 로컬 파일 시간을 파일 시간으로 변환합니다.

```
CFileTime LocalToUTC() const throw();
```

### <a name="return-value"></a>Return Value

시간을 `CFileTime` 포함하는 개체를 UTC 형식으로 반환합니다.

### <a name="example"></a>예제

[CFileTime::UTCToLocal에](#utctolocal)대한 예제를 참조하십시오.

## <a name="cfiletimemillisecond"></a><a name="millisecond"></a>C파일시간::밀리초

1밀리초를 구성하는 100나노초 간격의 수를 저장하는 정적 데이터 멤버입니다.

```
static const ULONGLONG Millisecond = 10000;
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]

## <a name="cfiletimeminute"></a><a name="minute"></a>CFile시간::분

1분을 구성하는 100나노초 간격의 수를 저장하는 정적 데이터 멤버입니다.

```
static const ULONGLONG Minute = Second* 60;
```

### <a name="example"></a>예제

[CFileTime::밀리초의](#millisecond)예제를 참조하십시오.

## <a name="cfiletimeoperator--"></a><a name="operator_-"></a>CFileTime::연산자 -

이 연산자는 `CFileTime` 또는 `CFileTimeSpan` 개체에 대한 빼기를 수행하는 데 사용됩니다.

```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*<br/>
`CFileTimeSpan` 개체입니다.

*피트*<br/>
`CFileTime` 개체입니다.

### <a name="return-value"></a>Return Value

두 `CFileTime` 개체 간의 `CFileTimeSpan` 시간 차이의 결과를 나타내는 개체 또는 개체를 반환합니다.

## <a name="cfiletimeoperator-"></a><a name="operator_neq"></a>CFileTime::연산자 !=

이 연산자는 `CFileTime` 두 개체를 비교하여 부등가등입니다.

```
bool operator!=(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*피트*<br/>
비교할 `CFileTime` 개체입니다.

### <a name="return-value"></a>Return Value

비교중인 항목이 개체와 같지 않은 `CFileTime` 경우 TRUE를 반환합니다( 그렇지 않으면 FALSE).

## <a name="cfiletimeoperator-"></a><a name="operator_add"></a>CFileTime::연산자 +

이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하는 데 사용됩니다.

```
CFileTime operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>Return Value

원래 `CFileTime` 시간의 결과와 상대 시간을 나타내는 객체를 반환합니다.

## <a name="cfiletimeoperator-"></a><a name="operator_add_eq"></a>CFileTime::연산자 +=

이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하고 결과를 현재 개체에 할당하는 데 사용됩니다.

```
CFileTime& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*범위*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>Return Value

원래 시간의 `CFileTime` 결과와 상대 시간을 나타내는 업데이트된 개체를 반환합니다.

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt"></a>CFileTime::연산자&lt;

이 연산자는 두 `CFileTime` 개체를 비교하여 더 작은 값을 확인합니다.

```
bool operator<(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*피트*<br/>
비교할 `CFileTime` 개체입니다.

### <a name="return-value"></a>Return Value

첫 번째 개체가 두 번째 개체보다 적거나 FALSE인 경우 TRUE를 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt_eq"></a>CFileTime::연산자&lt;=

이 연산자는 두 `CFileTime` 개체를 비교하여 더 작거나 같은 값을 확인합니다.

```
bool operator<=(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*피트*<br/>
비교할 `CFileTime` 개체입니다.

### <a name="return-value"></a>Return Value

첫 번째 개체가 (이전 시간) 미만이거나 두 번째 개체와 같거나 FALSE인 경우 TRUE를 반환합니다.

## <a name="cfiletimeoperator-"></a><a name="operator_eq"></a>CFileTime::연산자 =

할당 연산자입니다.

```
CFileTime& operator=(const FILETIME& ft) throw();
```

### <a name="parameters"></a>매개 변수

*피트*<br/>
새 `CFileTime` 시간과 날짜를 포함하는 개체입니다.

### <a name="return-value"></a>Return Value

업데이트된 `CFileTime` 개체를 반환합니다.

## <a name="cfiletimeoperator--"></a><a name="operator_-_eq"></a>CFileTime::연산자 -=

이 연산자는 `CFileTimeSpan` 개체에 대한 빼기를 수행하고 결과를 현재 개체에 할당하는 데 사용됩니다.

```
CFileTime& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*범위*<br/>
빼는 상대적 시간을 포함하는 `CFileTimeSpan` 객체입니다.

### <a name="return-value"></a>Return Value

업데이트된 `CFileTime` 개체를 반환합니다.

## <a name="cfiletimeoperator-"></a><a name="operator_eq_eq"></a>CFileTime::연산자 ==

이 연산자는 두 `CFileTime` 개체가 같은지 비교합니다.

```
bool operator==(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*피트*<br/>
비교할 `CFileTime` 개체입니다.

### <a name="return-value"></a>Return Value

개체가 같으면 TRUE를 반환합니다( 그렇지 않으면 FALSE).

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt"></a>CFileTime::연산자&gt;

이 연산자는 두 `CFileTime` 개체를 비교하여 더 큰 값을 확인합니다.

```
bool operator>(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*피트*<br/>
비교할 `CFileTime` 개체입니다.

### <a name="return-value"></a>Return Value

첫 번째 개체가 두 번째 개체보다 큰 경우 TRUE를 반환합니다( 나중에 시간), 그렇지 않으면 FALSE입니다.

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt_eq"></a>CFileTime::연산자&gt;=

이 연산자는 두 `CFileTime` 개체를 비교하여 더 크거나 같은 값을 확인합니다.

```
bool operator>=(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*피트*<br/>
비교할 `CFileTime` 개체입니다.

### <a name="return-value"></a>Return Value

첫 번째 개체가 나중에 시간보다 크거나 두 번째 개체와 같거나 FALSE인 경우 TRUE를 반환합니다.

## <a name="cfiletimesecond"></a><a name="second"></a>CFile시간::두 번째

하루를 구성하는 100나노초 간격의 수를 저장하는 정적 데이터 멤버입니다.

```
static const ULONGLONG Second = Millisecond* 1000;
```

### <a name="example"></a>예제

[CFileTime::밀리초의](#millisecond)예제를 참조하십시오.

## <a name="cfiletimesettime"></a><a name="settime"></a>CFileTime::설정 시간

이 메서드를 호출하여 개체에 저장된 `CFileTime` 날짜와 시간을 설정합니다.

```cpp
void SetTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>매개 변수

*n시간*<br/>
날짜와 시간을 나타내는 64비트 값(로컬 또는 조정된 유니버설 타임(UTC) 형식입니다.

## <a name="cfiletimeutctolocal"></a><a name="utctolocal"></a>C파일타임::UTCToLocal

이 메서드를 호출하여 UTC(조정된 유니버설 타임)를 기준으로 시간을 현지 파일 시간으로 변환합니다.

```
CFileTime UTCToLocal() const throw();
```

### <a name="return-value"></a>Return Value

로컬 `CFileTime` 파일 시간 형식으로 시간을 포함하는 개체를 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]

## <a name="cfiletimeweek"></a><a name="week"></a>CFile시간::주

100나노초 간격을 저장하는 정적 데이터 멤버입니다.

```
static const ULONGLONG Week = Day* 7;
```

### <a name="example"></a>예제

[CFileTime::밀리초의](#millisecond)예제를 참조하십시오.

## <a name="see-also"></a>참조

[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFile타임스팬 클래스](../../atl-mfc-shared/reference/cfiletimespan-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
