---
title: 콜레데이트타임스팬 클래스
ms.date: 03/27/2019
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
ms.openlocfilehash: 8f6a26c2724146f8723dee3ddce60ddce6995ec8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747155"
---
# <a name="coledatetimespan-class"></a>콜레데이트타임스팬 클래스

상대 시간, 시간 범위를 나타냅니다.

## <a name="syntax"></a>구문

```
class COleDateTimeSpan
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레데이트 타임스팬::콜레데이트타임스팬](#coledatetimespan)|`COleDateTimeSpan` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[콜레데이트 타임스팬::형식](#format)|개체의 서식이 지정된 문자열 `COleDateTimeSpan` 표현을 생성합니다.|
|[콜레데이트 타임스팬::겟데이즈](#getdays)|이 `COleDateTimeSpan` 개체가 나타내는 범위의 일 부분을 반환합니다.|
|[콜레데이트 타임스팬::겟타임](#gethours)|이 `COleDateTimeSpan` 개체가 나타내는 범위의 시간 부분을 반환합니다.|
|[콜레데이트 타임스팬::겟분](#getminutes)|이 `COleDateTimeSpan` 개체가 나타내는 범위의 분 부분을 반환합니다.|
|[콜레데이트 타임스팬::겟초](#getseconds)|이 `COleDateTimeSpan` 개체가 나타내는 범위의 두 번째 부분을 반환합니다.|
|[COleDate시간 스팬::GetStatus](#getstatus)|이 `COleDateTimeSpan` 개체의 상태(유효성)를 가져옵니다.|
|[콜레데이트 타임스팬::겟토탈데일](#gettotaldays)|이 `COleDateTimeSpan` 개체가 나타내는 일 수를 반환합니다.|
|[콜레데이트 타임스팬::겟토탈시간](#gettotalhours)|이 `COleDateTimeSpan` 개체가 나타내는 시간 수를 반환합니다.|
|[콜레데이트 타임스팬::겟토탈분](#gettotalminutes)|이 `COleDateTimeSpan` 개체가 나타내는 분 수를 반환합니다.|
|[콜레데이트 타임스팬::겟토탈초](#gettotalseconds)|이 `COleDateTimeSpan` 개체가 나타내는 시간(초)을 반환합니다.|
|[콜레데이트 타임스팬::세트데이트타임스팬](#setdatetimespan)|이 `COleDateTimeSpan` 개체의 값을 설정합니다.|
|[콜레데이트 타임스팬::설정 상태](#setstatus)|이 `COleDateTimeSpan` 개체의 상태(유효성)를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|||
|-|-|
|[연산자 +, -](#operator_add_-)|값에 대한 `COleDateTimeSpan` 기호를 추가, 빼기 및 변경합니다.|
|[연산자 +=, -=](#operator_add_eq_-_eq)|이 `COleDateTimeSpan` 값에서 `COleDateTimeSpan` 값을 추가하고 뺍니다.|
|[연산자 =](#operator_eq)|값을 복사합니다. `COleDateTimeSpan`|
|[연산자 ==, <, <=](#coledatetimespan_relational_operators)|두 `COleDateTimeSpan` 값을 비교합니다.|
|[operator double](#operator_double)|이 `COleDateTimeSpan` 값을 **double로**변환합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[콜레데이트 타임스팬::m_span](#m_span)|이 `COleDateTimeSpan` 개체에 대한 기본 **double을** 포함합니다.|
|[콜레데이트 타임스팬:m_status](#m_status)|이 `COleDateTimeSpan` 개체의 상태를 포함합니다.|

## <a name="remarks"></a>설명

`COleDateTimeSpan`기본 클래스가 없습니다.

A는 `COleDateTimeSpan` 며칠 동안 시간을 유지합니다.

`COleDateTimeSpan`동반자 클래스 [COleDateTime와](../../atl-mfc-shared/reference/coledatetime-class.md)함께 사용됩니다. `COleDateTime`올레 자동화의 `DATE` 데이터 형식을 캡슐화합니다. `COleDateTime`은 절대 시간 값을 나타냅니다. 모든 `COleDateTime` 계산에는 `COleDateTimeSpan` 값이 포함됩니다. 이러한 클래스 간의 관계는 [CTime과](../../atl-mfc-shared/reference/ctime-class.md) [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)사이의 관계와 유사합니다.

및 클래스에 대한 자세한 내용은 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오. `COleDateTimeSpan` `COleDateTime`

## <a name="requirements"></a>요구 사항

**헤더:** ATLComTime.h

## <a name="coledatetimespan-relational-operators"></a><a name="coledatetimespan_relational_operators"></a>COleDateTimeSpan 관계형 연산자

비교 연산자.

```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```

### <a name="parameters"></a>매개 변수

*날짜 스팬*<br/>
비교할 `COleDateTimeSpan`입니다.

### <a name="return-value"></a>Return Value

이러한 연산자는 두 날짜/시간 범위 값을 비교하고 조건이 true인 경우 TRUE를 반환합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

> [!NOTE]
> 피연산자 중 하나도 유효하지 않은 경우 ATLASSERT가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]

## <a name="coledatetimespancoledatetimespan"></a><a name="coledatetimespan"></a>콜레데이트 타임스팬::콜레데이트타임스팬

`COleDateTimeSpan` 개체를 생성합니다.

```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>매개 변수

*드블스판스rc*<br/>
새 `COleDateTimeSpan` 개체에 복사할 일 수입니다.

*lDays,* *nHours,* *nMins,* *nSecs*<br/>
새 `COleDateTimeSpan` 개체에 복사할 일 및 시간 값을 지정합니다.

### <a name="remarks"></a>설명

이러한 모든 생성자는 지정된 `COleDateTimeSpan` 값으로 초기화된 새 개체를 만듭니다. 이러한 각 생성자에 대한 간략한 설명은 다음과 같습니다.

- **콜레데이트타임스팬()** 초기화된 `COleDateTimeSpan` 개체를 0으로 생성합니다.

- **콜레데이트타임스팬()** `dblSpanSrc` **)** 부동 `COleDateTimeSpan` 점 값에서 개체를 생성합니다.

- **COleDate시간 스팬 (,** `lDays` **,** `nHours` **,** `nMins` **)** `nSecs` **)** 지정된 숫자 `COleDateTimeSpan` 값으로 초기화된 개체를 생성합니다.

새 `COleDateTimeSpan` 개체의 상태가 유효한 것으로 설정됩니다.

값의 경계에 대한 `COleDateTimeSpan` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]

## <a name="coledatetimespanformat"></a><a name="format"></a>콜레데이트 타임스팬::형식

개체의 서식이 지정된 문자열 `COleDateTimeSpan` 표현을 생성합니다.

```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>매개 변수

*p 포맷*<br/>
`printf` 서식 문자열과 유사한 서식 문자열입니다. 백분율()`%`기호 앞에 오는 서식 지정 코드는 `COleDateTimeSpan` 해당 구성 요소로 대체됩니다. 서식 문자열의 다른 문자는 반환된 문자열에 변경되지 않고 복사됩니다. 서식 코드의 값과 `Format` 의미는 다음과 같습니다.

- **%H** 현재 일의 시간

- **%M** 현재 시간의 분

- **%S** 현재 분단위의 초

- **%%** 백분율 기호

위에 나열된 네 개의 형식 코드는 Format에서 허용하는 유일한 코드입니다.

-

*nID*<br/>
형식 제어 문자열의 리소스 ID입니다.

### <a name="return-value"></a>Return Value

형식이 지정된 날짜/시간 범위 값을 포함하는 A입니다. `CString`

### <a name="remarks"></a>설명

이러한 함수를 호출하여 시간 범위 값의 형식이 지정된 표현을 만듭니다. 이 `COleDateTimeSpan` 개체의 상태가 null이면 반환 값은 빈 문자열입니다. 상태가 잘못되면 반환 문자열은 문자열 리소스 IDS_INVALID_DATETIMESPAN 지정됩니다.

이 함수의 양식에 대한 간략한 설명은 다음과 같습니다.

*형식(pFormat)* **)** **Format(**<br/>
이 양식은 `printf`에서와 같이 % 기호(%) 앞에 오는 특수 서식 지정 코드가 포함된 형식 문자열을 사용하여 값을 서식화합니다. 서식 문자열은 함수에 대한 매개 변수로 전달됩니다.

*형식(nID)* **)** **Format(**<br/>
이 양식은 `printf`에서와 같이 % 기호(%) 앞에 오는 특수 서식 지정 코드가 포함된 형식 문자열을 사용하여 값을 서식화합니다. 서식 문자열은 리소스입니다. 이 문자열 리소스의 ID는 매개 변수로 전달됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]

## <a name="coledatetimespangetdays"></a><a name="getdays"></a>콜레데이트 타임스팬::겟데이즈

이 날짜/시간 범위 값의 일 부분을 검색합니다.

```
LONG GetDays() const throw();
```

### <a name="return-value"></a>Return Value

이 날짜/시간 범위 값의 일 부분입니다.

### <a name="remarks"></a>설명

이 함수의 반환 값은 약 3,615,000에서 3,615,000 사이입니다.

`COleDateTimeSpan` 개체의 값을 쿼리하는 다른 함수의 경우 다음 멤버 함수를 참조하십시오.

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [겟초](#getseconds)

- [겟토탈일](#gettotaldays)

- [겟토탈아워](#gettotalhours)

- [겟토탈분](#gettotalminutes)

- [겟토탈초](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]

## <a name="coledatetimespangethours"></a><a name="gethours"></a>콜레데이트 타임스팬::겟타임

이 날짜/시간 범위 값의 시간 부분을 검색합니다.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Return Value

이 날짜/시간 범위 값의 시간 부분입니다.

### <a name="remarks"></a>설명

이 함수의 반환 값은 23에서 23 사이입니다.

`COleDateTimeSpan` 개체의 값을 쿼리하는 다른 함수의 경우 다음 멤버 함수를 참조하십시오.

- [겟데이즈](#getdays)

- [GetMinutes](#getminutes)

- [겟초](#getseconds)

- [겟토탈일](#gettotaldays)

- [겟토탈아워](#gettotalhours)

- [겟토탈분](#gettotalminutes)

- [겟토탈초](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]

## <a name="coledatetimespangetminutes"></a><a name="getminutes"></a>콜레데이트 타임스팬::겟분

이 날짜/시간 범위 값의 분 부분을 검색합니다.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Return Value

이 날짜/시간 범위 값의 분 부분입니다.

### <a name="remarks"></a>설명

이 함수의 반환 값은 59에서 59 사이입니다.

`COleDateTimeSpan` 개체의 값을 쿼리하는 다른 함수의 경우 다음 멤버 함수를 참조하십시오.

- [겟데이즈](#getdays)

- [GetHours](#gethours)

- [겟초](#getseconds)

- [겟토탈일](#gettotaldays)

- [겟토탈아워](#gettotalhours)

- [겟토탈분](#gettotalminutes)

- [겟토탈초](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]

## <a name="coledatetimespangetseconds"></a><a name="getseconds"></a>콜레데이트 타임스팬::겟초

이 날짜/시간 범위 값의 두 번째 부분을 검색합니다.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Return Value

이 날짜/시간 범위 값의 초 부분입니다.

### <a name="remarks"></a>설명

이 함수의 반환 값은 59에서 59 사이입니다.

`COleDateTimeSpan` 개체의 값을 쿼리하는 다른 함수의 경우 다음 멤버 함수를 참조하십시오.

- [겟데이즈](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [겟토탈일](#gettotaldays)

- [겟토탈아워](#gettotalhours)

- [겟토탈분](#gettotalminutes)

- [겟토탈초](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]

## <a name="coledatetimespangetstatus"></a><a name="getstatus"></a>COleDate시간 스팬::GetStatus

이 `COleDateTimeSpan` 개체의 상태(유효성)를 가져옵니다.

```
DateTimeSpanStatus GetStatus() const throw();
```

### <a name="return-value"></a>Return Value

이 `COleDateTimeSpan` 값의 상태입니다.

### <a name="remarks"></a>설명

반환 값은 클래스 `DateTimeSpanStatus` 내에서 정의된 줄임마드 형식에 `COleDateTimeSpan` 의해 정의됩니다.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
};
```

이러한 상태 값에 대한 간략한 설명은 다음 목록을 참조하십시오.

- `COleDateTimeSpan::valid`이 `COleDateTimeSpan` 개체가 유효하다는 것을 나타냅니다.

- `COleDateTimeSpan::invalid`이 `COleDateTimeSpan` 개체가 잘못되었음을 나타냅니다. 즉, 해당 값이 올바르지 않을 수 있습니다.

- `COleDateTimeSpan::null`이 `COleDateTimeSpan` 개체가 null, 즉 이 개체에 대해 제공된 값이 없음을 나타냅니다. (C++ NULL과 반대로 "값이 없음"의 데이터베이스 의미에서 "null"입니다.)

다음과 같은 `COleDateTimeSpan` 경우 개체의 상태가 잘못되었습니다.

- 이 개체가 산술 할당 작업 중에 오버플로 또는 언더플로우를 `+=` `-=`경험한 경우 또는 .

- 이 개체에 잘못된 값이 할당된 경우

- 이 개체의 상태가 명시적으로 잘못된 것으로 `SetStatus`설정된 경우 을 사용하여

상태를 유효하지 않게 설정할 수 있는 작업에 대한 자세한 내용은 [COleDateTimeSpan:::연산자 +,](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) 및 [COleDateTimeSpan:::연산자 +===](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)

값의 경계에 대한 `COleDateTimeSpan` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

## <a name="coledatetimespangettotaldays"></a><a name="gettotaldays"></a>콜레데이트 타임스팬::겟토탈데일

일로 표현된 이 날짜/시간 범위 값을 검색합니다.

```
double GetTotalDays() const throw();
```

### <a name="return-value"></a>Return Value

일로 표현된 날짜/시간 범위 값입니다. 이 함수는 double을 반환하기 위해 프로토타입으로 제작되지만 항상 정수 값을 반환합니다.

### <a name="remarks"></a>설명

이 함수의 반환 값은 약 - 3.65e6에서 3.65e6 사이입니다.

`COleDateTimeSpan` 개체의 값을 쿼리하는 다른 함수의 경우 다음 멤버 함수를 참조하십시오.

- [겟데이즈](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [겟초](#getseconds)

- [겟토탈아워](#gettotalhours)

- [겟토탈분](#gettotalminutes)

- [겟토탈초](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]

## <a name="coledatetimespangettotalhours"></a><a name="gettotalhours"></a>콜레데이트 타임스팬::겟토탈시간

시간으로 표현된 이 날짜/시간 범위 값을 검색합니다.

```
double GetTotalHours() const throw();
```

### <a name="return-value"></a>Return Value

시간으로 표현된 날짜/시간 범위 값입니다. 이 함수는 double을 반환하기 위해 프로토타입으로 제작되지만 항상 정수 값을 반환합니다.

### <a name="remarks"></a>설명

이 함수의 반환 값은 약 - 8.77e7에서 8.77e7 사이입니다.

`COleDateTimeSpan` 개체의 값을 쿼리하는 다른 함수의 경우 다음 멤버 함수를 참조하십시오.

- [겟데이즈](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [겟초](#getseconds)

- [겟토탈일](#gettotaldays)

- [겟토탈분](#gettotalminutes)

- [겟토탈초](#gettotalseconds)

### <a name="example"></a>예제

[GetTotalDays에](#gettotaldays)대한 예제를 참조하십시오.

## <a name="coledatetimespangettotalminutes"></a><a name="gettotalminutes"></a>콜레데이트 타임스팬::겟토탈분

분으로 표현된 이 날짜/시간 범위 값을 검색합니다.

```
double GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Return Value

분으로 표현된 이 날짜/시간 범위 값입니다. 이 함수는 double을 반환하기 위해 프로토타입으로 제작되지만 항상 정수 값을 반환합니다.

### <a name="remarks"></a>설명

이 함수의 반환 값은 약 - 5.26e9에서 5.26e9 사이입니다.

`COleDateTimeSpan` 개체의 값을 쿼리하는 다른 함수의 경우 다음 멤버 함수를 참조하십시오.

- [겟데이즈](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [겟초](#getseconds)

- [겟토탈일](#gettotaldays)

- [겟토탈아워](#gettotalhours)

- [겟토탈초](#gettotalseconds)

### <a name="example"></a>예제

[GetTotalDays에](#gettotaldays)대한 예제를 참조하십시오.

## <a name="coledatetimespangettotalseconds"></a><a name="gettotalseconds"></a>콜레데이트 타임스팬::겟토탈초

초 단위로 표현된 이 날짜/시간 범위 값을 검색합니다.

```
double GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Return Value

초 단위로 표현된 이 날짜/시간 범위 값입니다. 이 함수는 double을 반환하기 위해 프로토타입으로 제작되지만 항상 정수 값을 반환합니다.

### <a name="remarks"></a>설명

이 함수의 반환 값은 약 - 3.16e11에서 3.16e11 사이입니다.

`COleDateTimeSpan` 개체의 값을 쿼리하는 다른 함수의 경우 다음 멤버 함수를 참조하십시오.

- [겟데이즈](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [겟초](#getseconds)

- [겟토탈일](#gettotaldays)

- [겟토탈아워](#gettotalhours)

- [겟토탈분](#gettotalminutes)

### <a name="example"></a>예제

[GetTotalDays에](#gettotaldays)대한 예제를 참조하십시오.

## <a name="coledatetimespanm_span"></a><a name="m_span"></a>콜레데이트 타임스팬::m_span

이 `COleDateTime` 개체의 기본 **이중 값입니다.**

```
double m_span;
```

### <a name="remarks"></a>설명

이 값은 날짜/시간 범위를 일(날짜)으로 표현합니다.

> [!CAUTION]
> **이중** 데이터 멤버의 값을 변경하면 이 `COleDateTimeSpan` 개체의 값이 변경됩니다. 이 `COleDateTimeSpan` 개체의 상태는 변경되지 않습니다.

## <a name="coledatetimespanm_status"></a><a name="m_status"></a>콜레데이트 타임스팬:m_status

이 데이터 멤버의 형식은 `DateTimeSpanStatus` `COleDateTimeSpan` 클래스 내에서 정의된 수련 된 형식입니다.

```
DateTimeSpanStatus m_status;
```

### <a name="remarks"></a>설명

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

이러한 상태 값에 대한 간략한 설명은 다음 목록을 참조하십시오.

- `COleDateTimeSpan::valid`이 `COleDateTimeSpan` 개체가 유효하다는 것을 나타냅니다.

- `COleDateTimeSpan::invalid`이 `COleDateTimeSpan` 개체가 잘못되었음을 나타냅니다. 즉, 해당 값이 올바르지 않을 수 있습니다.

- `COleDateTimeSpan::null`이 `COleDateTimeSpan` 개체가 null, 즉 이 개체에 대해 제공된 값이 없음을 나타냅니다. (C++ NULL과 반대로 "값이 없음"의 데이터베이스 의미에서 "null"입니다.)

다음과 같은 `COleDateTimeSpan` 경우 개체의 상태가 잘못되었습니다.

- 이 개체가 산술 할당 작업 중에 오버플로 또는 언더플로우를 `+=` `-=`경험한 경우 또는 .

- 이 개체에 잘못된 값이 할당된 경우

- 이 개체의 상태가 [SetStatus](#setstatus)를 사용하여 유효하지 않게 명시적으로 설정된 경우 .

상태를 유효하지 않게 설정할 수 있는 작업에 대한 자세한 내용은 [COleDateTimeSpan:::연산자 +,](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) 및 [COleDateTimeSpan:::연산자 +===](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)

> [!CAUTION]
> 이 데이터 멤버는 고급 프로그래밍 상황에 적합합니다. 인라인 멤버 함수 [GetStatus](#getstatus) 및 [SetStatus를](#setstatus)사용 해야 합니다. 이 `SetStatus` 데이터 멤버를 명시적으로 설정하는 것에 대한 자세한 내용은 참조하세요.

값의 경계에 대한 `COleDateTimeSpan` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

## <a name="coledatetimespanoperator-"></a><a name="operator_eq"></a>COleDate시간 범위::연산자 =

값을 복사합니다. `COleDateTimeSpan`

```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```

### <a name="remarks"></a>설명

이 오버로드된 할당 연산자는 원본 날짜/시간 `COleDateTimeSpan` 범위 값을 이 개체에 복사합니다.

## <a name="coledatetimespanoperator---"></a><a name="operator_add_-"></a>COleDate시간 범위::연산자 +, -

값에 대한 `COleDateTimeSpan` 기호를 추가, 빼기 및 변경합니다.

```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```

### <a name="remarks"></a>설명

처음 두 연산자를 사용하면 날짜/시간 범위 값을 추가하고 뺄 수 있습니다. 세 번째 를 사용하면 날짜/시간 범위 값의 부호를 변경할 수 있습니다.

피연산자 중 하나가 null이면 결과 `COleDateTimeSpan` 값의 상태는 null입니다.

피연산자 중 하나가 유효하지 않고 다른 피연산자 중 `COleDateTimeSpan` 하나가 null이 아닌 경우 결과 값의 상태가 유효하지 않습니다.

유효, 유효하지 않은 및 null 상태 값에 대한 자세한 내용은 [m_status](#m_status) 멤버 변수를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]

## <a name="coledatetimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>COleDateTimeSpan::연산자 +=, -=

이 `COleDateTimeSpan` 값에서 `COleDateTimeSpan` 값을 추가하고 뺍니다.

```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>설명

이러한 연산자를 사용하면 이 `COleDateTimeSpan` 개체에서 날짜/시간 범위 값을 추가하고 뺄 수 있습니다. 피연산자 중 하나가 null이면 결과 `COleDateTimeSpan` 값의 상태는 null입니다.

피연산자 중 하나가 유효하지 않고 다른 피연산자 중 `COleDateTimeSpan` 하나가 null이 아닌 경우 결과 값의 상태가 유효하지 않습니다.

유효, 유효하지 않은 및 null 상태 값에 대한 자세한 내용은 [m_status](#m_status) 멤버 변수를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]

## <a name="coledatetimespanoperator-double"></a><a name="operator_double"></a>COleDate시간 범위::연산자 더블

이 `COleDateTimeSpan` 값을 **double로**변환합니다.

```
operator double() const throw();
```

### <a name="remarks"></a>설명

이 연산자는 이 `COleDateTimeSpan` 값의 값을 부동 소수점 수로 반환합니다.

## <a name="coledatetimespansetdatetimespan"></a><a name="setdatetimespan"></a>콜레데이트 타임스팬::세트데이트타임스팬

이 날짜/시간 범위 값의 값을 설정합니다.

```cpp
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>매개 변수

*lDays,* *nHours,* *nMins,* *nSecs*<br/>
이 `COleDateTimeSpan` 개체에 복사할 날짜 범위 및 시간 범위 값을 나타냅니다.

### <a name="remarks"></a>설명

`COleDateTimeSpan` 개체의 값을 쿼리하는 함수의 경우 다음 멤버 함수를 참조하십시오.

- [겟데이즈](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [겟초](#getseconds)

- [겟토탈일](#gettotaldays)

- [겟토탈아워](#gettotalhours)

- [겟토탈분](#gettotalminutes)

- [겟토탈초](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]

## <a name="coledatetimespansetstatus"></a><a name="setstatus"></a>콜레데이트 타임스팬::설정 상태

이 `COleDateTimeSpan` 개체의 상태(유효성)를 설정합니다.

```cpp
void SetStatus(DateTimeSpanStatus status) throw();
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
이 `COleDateTimeSpan` 개체의 새 상태 값입니다.

### <a name="remarks"></a>설명

*Status* 매개 변수 값은 `DateTimeSpanStatus` 클래스 내에서 정의된 수거된 `COleDateTimeSpan` 형식에 의해 정의됩니다.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

이러한 상태 값에 대한 간략한 설명은 다음 목록을 참조하십시오.

- `COleDateTimeSpan::valid`이 `COleDateTimeSpan` 개체가 유효하다는 것을 나타냅니다.

- `COleDateTimeSpan::invalid`이 `COleDateTimeSpan` 개체가 잘못되었음을 나타냅니다. 즉, 해당 값이 올바르지 않을 수 있습니다.

- `COleDateTimeSpan::null`이 `COleDateTimeSpan` 개체가 null, 즉 이 개체에 대해 제공된 값이 없음을 나타냅니다. (C++ NULL과 반대로 "값이 없음"의 데이터베이스 의미에서 "null"입니다.)

   > [!CAUTION]
   > 이 함수는 고급 프로그래밍 상황에 적합합니다. 이 함수는 이 개체의 데이터를 변경하지 않습니다. 상태를 **null** 또는 **유효하지 않은**상태로 설정하는 데 가장 자주 사용됩니다. 할당 연산자[(연산자 =](#operator_eq)) 및 [SetDateTimeSpan은](#setdatetimespan) 소스 값에 따라 개체의 상태를 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]

## <a name="see-also"></a>참조

[콜레데이트타임 클래스](../../atl-mfc-shared/reference/coledatetime-class.md)<br/>
[CTime 클래스](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[C타임스팬 클래스](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
