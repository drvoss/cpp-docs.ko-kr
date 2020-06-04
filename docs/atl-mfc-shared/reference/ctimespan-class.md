---
title: C타임스팬 클래스
ms.date: 10/18/2018
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
ms.openlocfilehash: 14aa5eb52e2c631a92e40ae7053c566284e00e57
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317496"
---
# <a name="ctimespan-class"></a>C타임스팬 클래스

내부적으로 시간 범위의 초 수로 저장되는 시간입니다.

## <a name="syntax"></a>구문

```
class CTimeSpan
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C시간스팬::C타임스팬](#ctimespan)|다양한 `CTimeSpan` 방법으로 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C시간 범위::형식](#format)|형식이 `CTimeSpan` 지정된 문자열로 변환합니다.|
|[C시간스팬::겟데이](#getdays)|이 의 완료 일 수를 나타내는 `CTimeSpan`값을 반환합니다.|
|[C시간스팬::겟타임](#gethours)|현재 일의 시간(-23~23)을 나타내는 값을 반환합니다.|
|[C시간스팬::겟분](#getminutes)|현재 시간의 분(-59~59)을 나타내는 값을 반환합니다.|
|[C시간 스팬::겟초](#getseconds)|현재 분(-59~59)의 초 수를 나타내는 값을 반환합니다.|
|[C시간스팬::겟타임스팬](#gettimespan)|개체의 값을 `CTimeSpan` 반환합니다.|
|[C시간스팬::겟토탈시간](#gettotalhours)|이 의 총 완료 시간 수를 나타내는 `CTimeSpan`값을 반환합니다.|
|[C시간스팬::겟토탈분](#gettotalminutes)|이 `CTimeSpan`에서 총 완료 분 수를 나타내는 값을 반환합니다.|
|[C시간 범위::겟토탈초](#gettotalseconds)|이 에서 총 완료 초 수를 나타내는 `CTimeSpan`값을 반환합니다.|
|[C시간스팬::직렬화64](#serialize64)|아카이브에서 데이터를 직렬화합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 + -](#operator_add_-)|객체를 `CTimeSpan` 추가하고 뺍니다.|
|[연산자 += -=](#operator_add_eq_-_eq)|이 `CTimeSpan`에서 개체를 `CTimeSpan` 추가하고 뺍니다.|
|[연산자 == < 등](#ctimespan_comparison_operators)|두 개의 상대 시간 값을 비교합니다.|

## <a name="remarks"></a>설명

`CTimeSpan`기본 클래스가 없습니다.

`CTimeSpan`함수는 초를 일, 시간, 분 및 초의 다양한 조합으로 변환합니다.

개체는 `CTimeSpan` 8바이트인 **__time64_t** 구조에 저장됩니다.

동반자 클래스인 [CTime은](../../atl-mfc-shared/reference/ctime-class.md)절대 시간을 나타냅니다.

`CTime` 및 `CTimeSpan` 클래스는 파생을 위해 설계되지 않았습니다. 가상 함수가 없기 때문에 두 `CTime` `CTimeSpan` 개체의 크기는 정확히 8바이트입니다. 대부분의 멤버 함수는 인라인입니다.

사용에 `CTimeSpan`대한 자세한 내용은 *런타임 라이브러리 참조에서* [날짜 및 시간](../../atl-mfc-shared/date-and-time.md)및 시간 [관리](../../c-runtime-library/time-management.md) 문서를 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** 아틀타임.h

## <a name="ctimespan-comparison-operators"></a><a name="ctimespan_comparison_operators"></a>CTimeSpan 비교 연산자

비교 연산자.

```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*<br/>
비교할 개체.

### <a name="return-value"></a>Return Value

이러한 연산자는 두 개의 상대 시간 값을 비교합니다. 조건이 true이면 TRUE를 반환합니다. 그렇지 않으면 거짓.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]

## <a name="ctimespanctimespan"></a><a name="ctimespan"></a>C시간스팬::C타임스팬

다양한 `CTimeSpan` 방법으로 개체를 생성합니다.

```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(
    LONG lDays,
    int nHours,
    int nMins,
    int nSecs) throw();
```

### <a name="parameters"></a>매개 변수

*시간 스팬Src*<br/>
이미 `CTimeSpan` 존재하는 개체입니다.

*time*<br/>
**시간** 범위의 __time64_t 시간 값입니다.

*lDays,* *nHours,* *nMins,* *nSecs*<br/>
일, 시간, 분 및 초각각.

### <a name="remarks"></a>설명

이러한 모든 생성자는 지정된 `CTimeSpan` 상대 시간으로 초기화된 새 개체를 만듭니다. 각 생성자는 아래에 설명되어 있습니다.

- `CTimeSpan( );`초기화되지 않은 `CTimeSpan` 개체를 생성합니다.

- `CTimeSpan( const CTimeSpan& );`다른 `CTimeSpan` `CTimeSpan` 값에서 개체를 생성합니다.

- `CTimeSpan( __time64_t );``CTimeSpan` **__time64_t** 형식에서 개체를 생성합니다.

- `CTimeSpan( LONG, int, int, int );`각 구성요소가 다음 범위로 구속된 구성요소에서 `CTimeSpan` 객체를 생성합니다.

   |구성 요소|범위|
   |---------------|-----------|
   |*lDays*|0-25,000 (약)|
   |*시간 (것)시간*|0-23|
   |*nMins*|0-59|
   |*nSecs*|0-59|

Microsoft Foundation 클래스 라이브러리의 디버그 버전은 하나 이상의 시간 구성 요소가 범위를 벗어난 경우 어설션합니다. 호출하기 전에 인수의 유효성을 검사하는 것은 사용자의 책임입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]

## <a name="ctimespanformat"></a><a name="format"></a>C시간 범위::형식

이에 `CTimeSpan`해당하는 서식이 지정된 문자열을 생성합니다.

```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>매개 변수

*pFormat*, *pszFormat*<br/>
`printf` 서식 문자열과 유사한 서식 문자열입니다. 백분율()`%`기호 앞에 오는 서식 지정 코드는 `CTimeSpan` 해당 구성 요소로 대체됩니다. 서식 문자열의 다른 문자는 반환된 문자열에 변경되지 않고 복사됩니다. 서식 코드의 값과 `Format` 의미는 다음과 같습니다.

- **%D** 이 것의 총 일수`CTimeSpan`

- **%H** 현재 일의 시간

- **%M** 현재 시간의 분

- **%S** 현재 분단위의 초

- **%%** 백분율 기호

*nID*<br/>
이 형식을 식별하는 문자열의 ID입니다.

### <a name="return-value"></a>Return Value

서식이 지정된 시간을 포함하는 `CString` 개체입니다.

### <a name="remarks"></a>설명

라이브러리의 디버그 버전은 서식 코드를 확인하고 코드가 위의 목록에 없는 경우 어설션합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]

## <a name="ctimespangetdays"></a><a name="getdays"></a>C시간스팬::겟데이

이 의 완료 일 수를 나타내는 `CTimeSpan`값을 반환합니다.

```
LONGLONG GetDays() const throw();
```

### <a name="return-value"></a>Return Value

시간 범위의 전체 24시간 일 수를 반환합니다. 시간 범위가 음수인 경우 이 값은 음수일 수 있습니다.

### <a name="remarks"></a>설명

일광 절약 시간제는 `GetDays` 잠재적으로 놀라운 결과를 반환할 수 있습니다. 예를 들어 DST가 적용되는 `GetDays` 경우 4월 의 하루가 한 시간 단축되어 전체 일로 계산되지 않으므로 4월 1일부터 5월 1일까지의 일수를 30이 아닌 29일로 보고합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]

## <a name="ctimespangethours"></a><a name="gethours"></a>C시간스팬::겟타임

현재 일의 시간(-23~23)을 나타내는 값을 반환합니다.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Return Value

현재 일의 시간 수를 반환합니다. 범위는 -23에서 23사이입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]

## <a name="ctimespangetminutes"></a><a name="getminutes"></a>C시간스팬::겟분

현재 시간의 분(-59~59)을 나타내는 값을 반환합니다.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Return Value

현재 시간의 분 수를 반환합니다. 범위는 -59에서 59사이입니다.

### <a name="example"></a>예제

[GetHours에](#gethours)대한 예제를 참조하십시오.

## <a name="ctimespangetseconds"></a><a name="getseconds"></a>C시간 스팬::겟초

현재 분(-59~59)의 초 수를 나타내는 값을 반환합니다.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Return Value

현재 분에서 초 수를 반환합니다. 범위는 -59에서 59사이입니다.

### <a name="example"></a>예제

[GetHours에](#gethours)대한 예제를 참조하십시오.

## <a name="ctimespangettimespan"></a><a name="gettimespan"></a>C시간스팬::겟타임스팬

개체의 값을 `CTimeSpan` 반환합니다.

```
__ time64_t GetTimeSpan() const throw();
```

### <a name="return-value"></a>Return Value

개체의 현재 값을 `CTimeSpan` 반환합니다.

## <a name="ctimespangettotalhours"></a><a name="gettotalhours"></a>C시간스팬::겟토탈시간

이 의 총 완료 시간 수를 나타내는 `CTimeSpan`값을 반환합니다.

```
LONGLONG GetTotalHours() const throw();
```

### <a name="return-value"></a>Return Value

이 에서 총 완료 시간을 `CTimeSpan`반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]

## <a name="ctimespangettotalminutes"></a><a name="gettotalminutes"></a>C시간스팬::겟토탈분

이 `CTimeSpan`에서 총 완료 분 수를 나타내는 값을 반환합니다.

```
LONGLONG GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Return Value

이 에서 총 완료 분 `CTimeSpan`수를 반환합니다.

### <a name="example"></a>예제

[GetTotalHours에](#gettotalhours)대한 예제를 참조하십시오.

## <a name="ctimespangettotalseconds"></a><a name="gettotalseconds"></a>C시간 범위::겟토탈초

이 에서 총 완료 초 수를 나타내는 `CTimeSpan`값을 반환합니다.

```
LONGLONG GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Return Value

이 에서 총 완료 초 `CTimeSpan`수를 반환합니다.

### <a name="example"></a>예제

[GetTotalHours에](#gettotalhours)대한 예제를 참조하십시오.

## <a name="ctimespanoperator---"></a><a name="operator_add_-"></a>C시간 범위::연산자 +, -

객체를 `CTimeSpan` 추가하고 뺍니다.

```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*<br/>
개체에 추가할 값입니다. `CTimeSpan`

### <a name="return-value"></a>Return Value

작업 `CTimeSpan` 결과를 나타내는 개체입니다.

### <a name="remarks"></a>설명

이 두 연산자는 서로 객체를 추가하고 빼기 `CTimeSpan` 할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]

## <a name="ctimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>C시간 범위::연산자 +=, -=

이 `CTimeSpan`에서 개체를 `CTimeSpan` 추가하고 뺍니다.

```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*범위*<br/>
개체에 추가할 값입니다. `CTimeSpan`

### <a name="return-value"></a>Return Value

업데이트된 `CTimeSpan` 개체입니다.

### <a name="remarks"></a>설명

이러한 연산자는 이 에서 개체를 `CTimeSpan` 추가하고 뺄 `CTimeSpan`수 있도록 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]

## <a name="ctimespanserialize64"></a><a name="serialize64"></a>C시간스팬::직렬화64

> [!NOTE]
> 이 메서드는 MFC 프로젝트에서만 사용할 수 있습니다.

아카이브에서 멤버 변수와 연결된 데이터를 직렬화합니다.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
업데이트할 `CArchive` 개체입니다.

### <a name="return-value"></a>Return Value

업데이트된 `CArchive` 개체입니다.

## <a name="see-also"></a>참고 항목

[asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
