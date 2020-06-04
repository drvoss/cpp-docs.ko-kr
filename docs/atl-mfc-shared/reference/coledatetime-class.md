---
title: 콜레데이트타임 클래스
ms.date: 03/27/2019
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
ms.openlocfilehash: 8ba09430427b6ece8ae5956912cbcc40fb33fcf2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747163"
---
# <a name="coledatetime-class"></a>콜레데이트타임 클래스

OLE 자동화에 `DATE` 사용되는 데이터 형식을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class COleDateTime
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레데이트 타임::콜데이트타임](#coledatetime)|`COleDateTime` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[콜레데이트 타임::형식](#format)|개체의 서식이 지정된 문자열 `COleDateTime` 표현을 생성합니다.|
|[콜레데이트 타임::겟아스DB타임스탬프](#getasdbtimestamp)|이 메서드를 호출하여 `COleDateTime` 개체에서 시간을 `DBTIMESTAMP` 데이터 구조로 가져옵니다.|
|[콜레데이트 타임::겟아스시스템타임](#getassystemtime)|`COleDateTime` [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 데이터 구조로 개체에서 시간을 가져오려면 이 메서드를 호출합니다.|
|[콜레데이트 타임::겟아수데이트](#getasudate)|이 메서드를 호출하여 데이터 `COleDateTime` 구조로서의 시간을 가져옵니다. `UDATE`|
|[콜레데이트 타임::GetCurrentTime](#getcurrenttime)|현재 `COleDateTime` 시간(정적 멤버 함수)을 나타내는 개체를 만듭니다.|
|[콜레데이트 타임::겟데이](#getday)|이 `COleDateTime` 개체가 나타내는 날을 반환합니다(1 - 31).|
|[콜레데이트 타임::겟데이오브위크](#getdayofweek)|이 `COleDateTime` 개체가 나타내는 요일을 반환합니다(일요일 = 1).|
|[콜레데이트 타임::겟데이오브이어](#getdayofyear)|이 `COleDateTime` 개체가 나타내는 연도의 요일을 반환합니다(1월 1일 = 1).|
|[콜레데이트 타임::겟아워](#gethour)|이 `COleDateTime` 개체가 나타내는 시간을 반환합니다(0 - 23).|
|[콜레데이트 타임::겟미닛](#getminute)|이 `COleDateTime` 개체가 나타내는 분(0 - 59)을 반환합니다.|
|[콜레데이트 타임::겟월](#getmonth)|이 `COleDateTime` 개체가 나타내는 달을 반환합니다(1 - 12).|
|[콜레데이트 타임::GetSecond](#getsecond)|이 `COleDateTime` 개체가 나타내는 두 번째 개체를 반환합니다(0 - 59).|
|[COleDate시간::GetStatus](#getstatus)|이 `COleDateTime` 개체의 상태(유효성)를 가져옵니다.|
|[콜레데이트 타임::겟이어](#getyear)|이 `COleDateTime` 개체가 나타내는 연도를 반환합니다.|
|[콜레데이트타임::P어스데이트타임](#parsedatetime)|문자열에서 날짜/시간 값을 읽고 `COleDateTime`의 값을 설정합니다.|
|[콜레데이트 타임::세트데이트](#setdate)|이 `COleDateTime` 개체의 값을 지정된 날짜 전용 값으로 설정합니다.|
|[콜레데이트 타임::세트데이트 타임](#setdatetime)|이 `COleDateTime` 개체의 값을 지정된 날짜/시간 값으로 설정합니다.|
|[COleDate시간::설정 상태](#setstatus)|이 `COleDateTime` 개체의 상태(유효성)를 설정합니다.|
|[콜레데이트 타임::세트타임](#settime)|이 `COleDateTime` 개체의 값을 지정된 시간 전용 값으로 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[COleDateTime::연산자 ==, COleDateTime::연산자 < 등](#coledatetime_relational_operators)|두 `COleDateTime` 값을 비교합니다.|
|[COleDateTime::연산자 +, COleDateTime::연산자 -](#operator_add_-)|값을 추가하고 `COleDateTime` 뺍니다.|
|[COleDateTime::연산자 +=, COleDateTime::연산자 -=](#operator_add_eq_-_eq)|이 `COleDateTime` 개체에서 `COleDateTime` 값을 추가하고 뺍니다.|
|[COleDateTime::연산자 =](#operator_eq)|값을 복사합니다. `COleDateTime`|
|[COleDateTime::연산자 날짜, COleDateTime::연산자 날짜*](#operator_date)|`COleDateTime` 값을 또는 a로 `DATE` `DATE*`변환합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[콜레데이트 타임::m_dt](#m_dt)|이 `DATE` `COleDateTime` 개체에 대한 기본 을 포함합니다.|
|[콜레데이트 타임::m_status](#m_status)|이 `COleDateTime` 개체의 상태를 포함합니다.|

## <a name="remarks"></a>설명

`COleDateTime`기본 클래스가 없습니다.

OLE 자동화의 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 데이터 형식에 대 한 가능한 형식 중 하나입니다. 값은 `COleDateTime` 절대 날짜 및 시간 값을 나타냅니다.

형식은 `DATE` 부동 점 값으로 구현됩니다. 일수 측정은 1899년 12월 30일 자정부터 측정됩니다. 다음 표에는 몇 가지 날짜와 관련 값이 표시됩니다.

|Date|값|
|----------|-----------|
|1899년 12월 29일 자정|-1.0|
|1899년 12월 29일 오전 6시|-1.25|
|1899년 12월 30일 자정|0.0|
|1899년 12월 31일 자정|1.0|
|1900년 1월 1일 오전 6시|2.25|

> [!CAUTION]
> 위의 표에서 일 값은 1899년 12월 30일 자정 이전에 음수가 되지만 시간 별 값은 그렇지 않습니다. 예를 들어, 6:00 AM은 항상 하루를 나타내는 정수가 양수(1899년 12월 30일 이후) 또는 음수(1899년 12월 30일 이전)인지 여부에 관계없이 분수 값 0.25로 표시됩니다. 즉, 간단한 부동 점 비교는 1899년 12월 29일 오전 6:00을 같은 날 7:00 AM을 나타내는 것보다 `COleDateTime` **늦게** 정렬합니다.

수업은 `COleDateTime` 100년 1월 1일부터 9999년 12월 31일까지 진행됩니다. 클래스는 `COleDateTime` 그레고리오 력; 줄리안 날짜를 지원하지 않습니다. `COleDateTime`은 일광 절약 시간을 무시합니다. (날짜 [및 시간 참조: 자동화 지원.)](../../atl-mfc-shared/date-and-time-automation-support.md)

> [!NOTE]
> `%y` 이 형식을 사용하여 1900년부터 시작되는 날짜에 대해서만 두 자리 연도를 검색할 수 있습니다. 1900년 이전의 날짜에 `%y` 형식을 사용하는 경우 코드는 ASSERT 오류를 생성합니다.

이 형식은 날짜 전용 또는 시간 전용 값을 나타내는 데도 사용됩니다. 규칙에 따라 날짜 0(1899년 12월 30일)은 시간 전용 값에 사용되며 시간 00:00(자정)은 날짜 전용 값에 사용됩니다.

100 `COleDateTime` 미만의 날짜를 사용하여 개체를 만드는 경우 날짜가 허용되지만 이후 `GetYear` `GetMonth`호출은 `GetHour` `GetMinute`" `GetSecond` 에 대한 `GetDay`실패 및 실패 및 반환 -1입니다. 이전에는 두 자리 날짜를 사용할 수 있었지만 MFC 4.2 이상에서 날짜가 100 이상이어야 합니다.

문제를 방지하려면 4자리 날짜를 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]

값에 `COleDateTime` 대한 기본 산술 연산은 컴패니언 클래스 [COleDateTimeSpan을](../../atl-mfc-shared/reference/coledatetimespan-class.md)사용합니다. `COleDateTimeSpan`값은 시간 간격을 정의합니다. 이러한 클래스 간의 관계는 [CTime과](../../atl-mfc-shared/reference/ctime-class.md) [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)사이의 관계와 유사합니다.

및 클래스에 대한 자세한 내용은 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오. `COleDateTimeSpan` `COleDateTime`

## <a name="requirements"></a>요구 사항

**헤더:** ATLComTime.h

## <a name="coledatetime-relational-operators"></a><a name="coledatetime_relational_operators"></a>COleDateTime 관계형 연산자

비교 연산자.

```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```

### <a name="parameters"></a>매개 변수

*date*<br/>
비교할 `COleDateTime` 개체입니다.

### <a name="remarks"></a>설명

> [!NOTE]
> 두 피연산자 중 하나가 유효하지 않은 경우 ATLASSERT가 발생합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]

### <a name="example"></a>예제

연산자 **>=** ** \< **및 **>** **<** 및 의 경우 `COleDateTime` 개체가 null로 설정된 경우 어설션합니다.

[!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]

## <a name="coledatetimecoledatetime"></a><a name="coledatetime"></a>콜레데이트 타임::콜데이트타임

`COleDateTime` 개체를 생성합니다.

```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& timeStamp) throw();
```

### <a name="parameters"></a>매개 변수

*날짜Src*<br/>
새 `COleDateTime` `COleDateTime` 개체에 복사할 기존 개체입니다.

*varSrc*<br/>
날짜/시간 값(VT_DATE)으로 `VARIANT` `COleVariant` 변환하여 새 `COleDateTime` 개체에 복사할 기존 데이터 구조(개체일 수 있음)입니다.

*dtSrc*<br/>
새 `COleDateTime` 개체에`DATE`복사할 날짜/시간() 값입니다.

*timeSrc*<br/>
날짜/시간 값으로 변환하여 새 `time_t` `__time64_t` `COleDateTime` 개체에 복사할 A 또는 값입니다.

*systimeSrc*<br/>
날짜/시간 값으로 변환하여 새 `SYSTEMTIME` `COleDateTime` 개체로 복사하는 구조입니다.

*파일 시간SRC*<br/>
날짜/시간 값으로 변환하여 새 `FILETIME` `COleDateTime` 개체로 복사하는 구조입니다. A는 `FILETIME` 유니버설 조정 시간(UTC)을 사용하므로 구조체에서 현지 시간을 통과하면 결과가 올바르지 않습니다. 자세한 내용은 Windows SDK의 [파일 시간을](/windows/win32/SysInfo/file-times) 참조하십시오.

*nYear*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
새 `COleDateTime` 개체에 복사할 날짜 및 시간 값을 지정합니다.

*wDosDate*, *wDosTime*<br/>
날짜/시간 값으로 변환하고 새 `COleDateTime` 개체로 복사할 MS-DOS 날짜 및 시간 값입니다.

*타임 스탬프*<br/>
현재 현지 시간을 포함하는 [DBTimeStamp](/dotnet/api/system.data.oledb.oledbtype) 구조에 대한 참조입니다.

### <a name="remarks"></a>설명

이러한 모든 생성자는 `COleDateTime` 지정된 값으로 초기화된 새 개체를 만듭니다. 다음 표에서는 각 날짜 및 시간 구성 요소에 대해 유효한 범위를 보여 주며 다음과 같은 범위가 표시됩니다.

|날짜/시간 구성 요소|유효 범위|
|--------------------------|-----------------|
|year|100 - 9999|
|month|0 - 12|
|일|0 - 31|
|hour|0 - 23|
|minute|0 - 59|
|second|0 - 59|

일 구성 요소의 실제 상한은 월 및 연도 구성 요소에 따라 다릅니다. 자세한 내용은 `SetDate` 또는 `SetDateTime` 멤버 함수를 참조하십시오.

다음은 각 생성자의 간략한 설명입니다.

- `COleDateTime(`**)을** `COleDateTime` 0으로 초기화한 객체를 생성합니다(자정, 1899년 12월 30일 자정).

- `COleDateTime(``dateSrc` **)** 기존 `COleDateTime` `COleDateTime` 개체에서 개체를 생성합니다.

- `COleDateTime(`*varSrc)* **)** 개체를 `COleDateTime` 생성합니다. 구조체 또는 `VARIANT` [COleVariant](../../mfc/reference/colevariant-class.md) 개체를 날짜/시간() `VT_DATE`값으로 변환하려고 시도합니다. 이 변환에 성공하면 변환된 값이 새 `COleDateTime` 개체에 복사됩니다. 그렇지 않으면 `COleDateTime` 개체 값이 0(자정, 1899년 12월 30일)으로 설정되고 상태가 유효하지 않은 것으로 설정됩니다.

- `COleDateTime(``dtSrc` **)** 값에서 `COleDateTime` 개체를 `DATE` 생성합니다.

- `COleDateTime(``timeSrc` **)** 값에서 `COleDateTime` 개체를 `time_t` 생성합니다.

- `COleDateTime(`*systimeSrc)* **)** `SYSTEMTIME` 값에서 `COleDateTime` 개체를 생성합니다.

- `COleDateTime(``filetimeSrc` **)** 값에서 `COleDateTime` 개체를 `FILETIME` 생성합니다. . A는 `FILETIME` 유니버설 조정 시간(UTC)을 사용하므로 구조체에서 현지 시간을 통과하면 결과가 올바르지 않습니다. 자세한 내용은 Windows SDK의 [파일 시간을](/windows/win32/SysInfo/file-times) 참조하십시오.

- `COleDateTime(``nYear` **)** . `nMonth` `nDay` `nHour` `nMin` `nSec` `COleDateTime`

- `COleDateTime(``wDosDate` `wDosTime` **)** 지정된 MS-DOS 날짜 및 시간 값에서 `COleDateTime` 개체를 생성합니다.

데이터 형식에 `time_t` 대한 자세한 내용은 *런타임 라이브러리 참조의* [시간](../../c-runtime-library/reference/time-time32-time64.md) 함수를 참조하십시오.

자세한 내용은 Windows SDK의 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 및 [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 구조를 참조하십시오.

값의 경계에 대한 `COleDateTime` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

> [!NOTE]
> 매개 변수를 `DBTIMESTAMP` 사용하는 생성자는 OLEDB.h가 포함된 경우에만 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]

## <a name="coledatetimeformat"></a><a name="format"></a>콜레데이트 타임::형식

날짜/시간 값의 서식이 지정된 표현을 만듭니다.

```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
다음 로캘 플래그 중 하나를 나타냅니다.

- LOCALE_NOUSEROVERRIDE 사용자 지정 사용자 설정 대신 시스템 기본 로캘 설정을 사용합니다.

- VAR_TIMEVALUEONLY 구문 분석 하는 동안 날짜 부분을 무시 합니다.

- VAR_DATEVALUEONLY 구문 분석 하는 동안 시간 부분을 무시 합니다.

*Lcid*<br/>
변환에 사용할 로캘 ID를 나타냅니다. 언어 식별자에 대한 자세한 내용은 [언어 식별자를](/windows/win32/Intl/language-identifiers)참조하십시오.

*lpszFormat*<br/>
`printf` 서식 문자열과 유사한 서식 문자열입니다. 백분율() `%`기호 앞에 오는 각 서식 지정 코드는 `COleDateTime` 해당 구성 요소로 대체됩니다. 서식 문자열의 다른 문자는 반환된 문자열에 변경되지 않고 복사됩니다. 자세한 내용은 런타임 함수 [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)을 참조하십시오. 서식 코드의 값과 `Format` 의미는 다음과 같습니다.

- `%H`현재 일의 시간

- `%M`현재 시간의 분

- `%S`현재 분단위의 초

- `%%`백분율 기호

*nFormatID*<br/>
형식 제어 문자열의 리소스 ID입니다.

### <a name="return-value"></a>Return Value

형식이 지정된 날짜/시간 값을 포함하는 A입니다. `CString`

### <a name="remarks"></a>설명

이 `COleDateTime` 개체의 상태가 null이면 반환 값은 빈 문자열입니다. 상태가 잘못되면 반환 문자열은 ATL_IDS_DATETIME_INVALID 문자열 리소스에 의해 지정됩니다.

이 함수에 대한 세 가지 양식에 대한 간략한 설명은 다음과 같습니다.

`Format`*(dwFlags,* *lcid)*<br/>
이 양식은 날짜 및 시간에 대한 언어 사양(로캘 아이디)을 사용하여 값을 포맷합니다. 기본 매개 변수를 사용하여 이 양식은 시간 부분이 0(자정)이 아니면 날짜와 시간을 인쇄하며, 이 경우 날짜 부분만 인쇄하거나 날짜 부분은 0(1899년 12월 30일)이면 시간만 인쇄합니다. 날짜/시간 값이 0(1899년 12월 30일 자정)이면 기본 매개변수가 있는 이 양식이 자정에 인쇄됩니다.

`Format`*(lpszFormat)*<br/>
이 양식은 에서와 `printf`같이 % 기호(%) 앞에 오는 특수 서식 지정 코드가 포함된 형식 문자열을 사용하여 값의 서식을 지정합니다. 서식 문자열은 함수에 대한 매개 변수로 전달됩니다. 서식 지정 코드에 대한 자세한 내용은 런타임 라이브러리 참조의 [strftime, wcsftime을](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 참조하십시오.

`Format`*(nFormatID)*<br/>
이 양식은 에서와 `printf`같이 % 기호(%) 앞에 오는 특수 서식 지정 코드가 포함된 형식 문자열을 사용하여 값의 서식을 지정합니다. 서식 문자열은 리소스입니다. 이 문자열 리소스의 ID는 매개 변수로 전달됩니다. 서식 지정 코드에 대한 자세한 내용은 *런타임 라이브러리 참조의* [strftime, wcsftime을](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]

## <a name="coledatetimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>콜레데이트 타임::겟아스DB타임스탬프

이 메서드를 호출하여 `COleDateTime` 개체에서 시간을 `DBTIMESTAMP` 데이터 구조로 가져옵니다.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& timeStamp) const throw();
```

### <a name="parameters"></a>매개 변수

*타임 스탬프*<br/>
[DBTimeStamp](/dotnet/api/system.data.oledb.oledbtype) 구조에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

참조된 *타임스탬프* 구조에 결과 시간을 저장합니다. 이 `DBTIMESTAMP` 함수에 의해 초기화된 `fraction` 데이터 구조에는 해당 멤버가 0으로 설정됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]

## <a name="coledatetimegetassystemtime"></a><a name="getassystemtime"></a>콜레데이트 타임::겟아스시스템타임

이 메서드를 호출하여 `COleDateTime` 개체에서 시간을 `SYSTEMTIME` 데이터 구조로 가져옵니다.

```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```

### <a name="parameters"></a>매개 변수

*sysTime*<br/>
개체에서 변환된 날짜/시간 값을 수신하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) `COleDateTime` 구조에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE를 반환합니다. 변환이 실패하거나 개체가 `COleDateTime` NULL 또는 유효하지 않은 경우 FALSE입니다.

### <a name="remarks"></a>설명

`GetAsSystemTime`은 참조된 *sysTime* 개체에 결과 시간을 저장합니다. 이 `SYSTEMTIME` 함수에 의해 초기화된 `wMilliseconds` 데이터 구조에는 해당 멤버가 0으로 설정됩니다.

`COleDateTime` 개체에 보관된 상태 정보에 대한 자세한 내용은 [GetStatus](#getstatus)를 참조하십시오.

## <a name="coledatetimegetasudate"></a><a name="getasudate"></a>콜레데이트 타임::겟아수데이트

이 메서드를 호출하여 `COleDateTime` 개체에서 시간을 `UDATE` 데이터 구조로 가져옵니다.

```
bool GetAsUDATE(UDATE& uDate) const throw();
```

### <a name="parameters"></a>매개 변수

*uDate*<br/>
개체에서 변환된 날짜/시간 값을 수신하는 `UDATE` 구조에 대한 참조입니다. `COleDateTime`

### <a name="return-value"></a>Return Value

성공하면 TRUE를 반환합니다. 변환이 실패하거나 개체가 `COleDateTime` NULL 또는 유효하지 않은 경우 FALSE입니다.

### <a name="remarks"></a>설명

구조는 `UDATE` "압축 해제" 날짜를 나타냅니다.

## <a name="coledatetimegetcurrenttime"></a><a name="getcurrenttime"></a>콜레데이트 타임::GetCurrentTime

이 정적 멤버 함수를 호출하여 현재 날짜/시간 값을 반환합니다.

```
static COleDateTime WINAPI GetCurrentTime() throw();
```

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]

## <a name="coledatetimegetday"></a><a name="getday"></a>콜레데이트 타임::겟데이

이 날짜/시간 값으로 표시되는 월의 날짜를 가져옵니다.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Return Value

이 `COleDateTime` 개체의 값으로 표시되는 월의 `COleDateTime::error` 일 또는 해당 일을 얻을 수 없는 경우입니다.

### <a name="remarks"></a>설명

유효한 반환 값은 1에서 31 사이입니다.

이 `COleDateTime` 개체의 값을 쿼리하는 다른 멤버 함수에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [겟월](#getmonth)

- [Getyear](#getyear)

- [겟아워](#gethour)

- [겟미닛](#getminute)

- [GetSecond](#getsecond)

- [겟데이오브위크](#getdayofweek)

- [겟데이오브이어](#getdayofyear)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]

## <a name="coledatetimegetdayofweek"></a><a name="getdayofweek"></a>콜레데이트 타임::겟데이오브위크

이 날짜/시간 값으로 표시되는 월의 날짜를 가져옵니다.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Return Value

이 `COleDateTime` 개체의 값으로 표시되는 요일 `COleDateTime::error` 또는 요일을 얻을 수 없는 경우입니다.

### <a name="remarks"></a>설명

유효한 반환 값은 1에서 7 사이이며, 여기서 1=일요일, 2=월요일 등입니다.

이 `COleDateTime` 개체의 값을 쿼리하는 다른 멤버 함수에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [겟데이](#getday)

- [겟월](#getmonth)

- [Getyear](#getyear)

- [겟아워](#gethour)

- [겟미닛](#getminute)

- [GetSecond](#getsecond)

- [겟데이오브이어](#getdayofyear)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]

## <a name="coledatetimegetdayofyear"></a><a name="getdayofyear"></a>콜레데이트 타임::겟데이오브이어

이 날짜/시간 값으로 표시되는 연도의 날짜를 가져옵니다.

```
int GetDayOfYear() const throw();
```

### <a name="return-value"></a>Return Value

이 `COleDateTime` 개체의 값으로 표시되는 연도의 `COleDateTime::error` 일 또는 연도의 일을 얻을 수 없는 경우입니다.

### <a name="remarks"></a>설명

유효한 반환 값은 1에서 366 사이이며 여기서 1월 1 = 1입니다.

이 `COleDateTime` 개체의 값을 쿼리하는 다른 멤버 함수에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [겟데이](#getday)

- [겟월](#getmonth)

- [Getyear](#getyear)

- [겟아워](#gethour)

- [겟미닛](#getminute)

- [GetSecond](#getsecond)

- [겟데이오브위크](#getdayofweek)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]

## <a name="coledatetimegethour"></a><a name="gethour"></a>콜레데이트 타임::겟아워

이 날짜/시간 값으로 표시되는 시간을 가져옵니다.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Return Value

이 `COleDateTime` 개체의 값으로 표시되는 `COleDateTime::error` 시간 또는 시간을 얻을 수 없는 경우입니다.

### <a name="remarks"></a>설명

유효한 반환 값은 0에서 23 사이의 범위입니다.

이 `COleDateTime` 개체의 값을 쿼리하는 다른 멤버 함수에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [겟데이](#getday)

- [겟월](#getmonth)

- [Getyear](#getyear)

- [겟미닛](#getminute)

- [GetSecond](#getsecond)

- [겟데이오브위크](#getdayofweek)

- [겟데이오브이어](#getdayofyear)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]

## <a name="coledatetimegetminute"></a><a name="getminute"></a>콜레데이트 타임::겟미닛

이 날짜/시간 값으로 표시되는 분을 가져옵니다.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Return Value

이 `COleDateTime` 개체의 값으로 표시되는 `COleDateTime::error` 분 또는 분을 가져올 수 없는 경우입니다.

### <a name="remarks"></a>설명

유효한 반환 값은 0에서 59 사이입니다.

이 `COleDateTime` 개체의 값을 쿼리하는 다른 멤버 함수에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [겟데이](#getday)

- [겟월](#getmonth)

- [Getyear](#getyear)

- [겟아워](#gethour)

- [GetSecond](#getsecond)

- [겟데이오브위크](#getdayofweek)

- [겟데이오브이어](#getdayofyear)

### <a name="example"></a>예제

[GetHour에](#gethour)대한 예제를 참조하십시오.

## <a name="coledatetimegetmonth"></a><a name="getmonth"></a>콜레데이트 타임::겟월

이 날짜/시간 값으로 표시되는 월을 가져옵니다.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Return Value

이 `COleDateTime` 개체의 값으로 표시되는 `COleDateTime::error` 달 또는 월을 얻을 수 없는 경우입니다.

### <a name="remarks"></a>설명

유효한 반환 값은 1에서 12 사이의 범위입니다.

이 `COleDateTime` 개체의 값을 쿼리하는 다른 멤버 함수에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [겟데이](#getday)

- [Getyear](#getyear)

- [겟아워](#gethour)

- [겟미닛](#getminute)

- [GetSecond](#getsecond)

- [겟데이오브위크](#getdayofweek)

- [겟데이오브이어](#getdayofyear)

### <a name="example"></a>예제

[GetDay에](#getday)대한 예제를 참조하십시오.

## <a name="coledatetimegetsecond"></a><a name="getsecond"></a>콜레데이트 타임::GetSecond

이 날짜/시간 값으로 표시되는 두 번째 값을 가져옵니다.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Return Value

이 `COleDateTime` 개체의 값으로 표시되는 `COleDateTime::error` 두 번째 또는 두 번째 개체를 가져올 수 없는 경우입니다.

### <a name="remarks"></a>설명

유효한 반환 값은 0에서 59 사이입니다.

> [!NOTE]
> 클래스는 `COleDateTime` 윤초를 지원하지 않습니다.

구현에 대한 `COleDateTime`자세한 내용은 날짜 [및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

이 `COleDateTime` 개체의 값을 쿼리하는 다른 멤버 함수에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [겟데이](#getday)

- [겟월](#getmonth)

- [Getyear](#getyear)

- [겟아워](#gethour)

- [겟미닛](#getminute)

- [겟데이오브위크](#getdayofweek)

- [겟데이오브이어](#getdayofyear)

### <a name="example"></a>예제

[GetHour에](#gethour)대한 예제를 참조하십시오.

## <a name="coledatetimegetstatus"></a><a name="getstatus"></a>COleDate시간::GetStatus

지정된 `COleDateTime` 개체의 상태(유효성)를 가져옵니다.

```
DateTimeStatus GetStatus() const throw();
```

### <a name="return-value"></a>Return Value

이 `COleDateTime` 값의 상태를 반환합니다. 기본값으로 `GetStatus` `COleDateTime` 구성된 개체를 호출하면 유효한 개체가 반환됩니다. 생성자가 `GetStatus` null로 `COleDateTime` 설정된 초기화 된 개체를 `GetStatus` 호출하면 null이 반환됩니다.

### <a name="remarks"></a>설명

반환 값은 클래스 `DateTimeStatus` 내에서 정의된 줄임마드 형식에 `COleDateTime` 의해 정의됩니다.

```
enum DateTimeStatus
{
   error = -1,
   valid = 0,
   invalid = 1,    // Invalid date (out of range, etc.)
   null = 2,       // Literally has no value
};
```

이러한 상태 값에 대한 간략한 설명은 다음 목록을 참조하십시오.

- `COleDateTime::error`날짜/시간 값의 일부를 가져오려고 하는 동안 오류가 발생했음을 나타냅니다.

- `COleDateTime::valid`이 `COleDateTime` 개체가 유효하다는 것을 나타냅니다.

- `COleDateTime::invalid`이 `COleDateTime` 개체가 잘못되었음을 나타냅니다. 즉, 해당 값이 올바르지 않을 수 있습니다.

- `COleDateTime::null`이 `COleDateTime` 개체가 null, 즉 이 개체에 대해 제공된 값이 없음을 나타냅니다. (C++ NULL과 반대로 "값이 없음"의 데이터베이스 의미에서 "null"입니다.)

다음과 같은 `COleDateTime` 경우 개체의 상태가 잘못되었습니다.

- 해당 값이 날짜/시간 `VARIANT` `COleVariant` 값으로 변환할 수 없는 또는 값에서 설정 된 경우입니다.

- 해당 값이 `time_t`에서 설정 `SYSTEMTIME`된 `FILETIME` 경우 에서 를 볼 수 없습니다 또는 값 유효한 날짜/시간 값으로 변환할 수 없습니다.

- 해당 값이 잘못된 `SetDateTime` 매개 변수 값으로 설정된 경우.

- 이 개체가 산술 할당 작업 중에 오버플로 또는 언더플로우를 `+=` `-=`경험한 경우 또는 .

- 이 개체에 잘못된 값이 할당된 경우

- 이 개체의 상태가 명시적으로 잘못된 것으로 `SetStatus`설정된 경우 을 사용하여

상태를 유효하지 않게 설정할 수 있는 작업에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [COleDateTime](#coledatetime)

- [설정날짜 시간](#setdatetime)

- [연산자 +, -](#operator_add_-)

- [연산자 +=, -=](#operator_add_eq_-_eq)

값의 경계에 대한 `COleDateTime` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]

## <a name="coledatetimegetyear"></a><a name="getyear"></a>콜레데이트 타임::겟이어

이 날짜/시간 값으로 표시되는 연도를 가져옵니다.

```
int GetYear() const throw();
```

### <a name="return-value"></a>Return Value

이 `COleDateTime` 개체의 값으로 표시되는 `COleDateTime::error` 연도 또는 연도를 얻을 수 없는 경우입니다.

### <a name="remarks"></a>설명

유효한 반환 값은 세기를 포함하는 100에서 9999 사이의 범위입니다.

이 `COleDateTime` 개체의 값을 쿼리하는 다른 멤버 함수에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [겟데이](#getday)

- [겟월](#getmonth)

- [겟아워](#gethour)

- [겟미닛](#getminute)

- [GetSecond](#getsecond)

- [겟데이오브위크](#getdayofweek)

- [겟데이오브이어](#getdayofyear)

값의 경계에 대한 `COleDateTime` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

### <a name="example"></a>예제

[GetDay에](#getday)대한 예제를 참조하십시오.

## <a name="coledatetimem_dt"></a><a name="m_dt"></a>콜레데이트 타임::m_dt

이 `COleDateTime` `DATE` 개체의 기본 구조입니다.

```
DATE m_dt;
```

### <a name="remarks"></a>설명

> [!CAUTION]
> 이 함수에서 `DATE` 반환되는 포인터에서 액세스하는 개체의 값을 변경하면 `COleDateTime` 이 개체의 값이 변경됩니다. 이 `COleDateTime` 개체의 상태는 변경되지 않습니다.

개체 구현에 대한 자세한 내용은 날짜 [및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오. `DATE`

## <a name="coledatetimem_status"></a><a name="m_status"></a>콜레데이트 타임::m_status

이 `COleDateTime` 개체의 상태를 포함합니다.

```
DateTimeStatus m_status;
```

### <a name="remarks"></a>설명

이 데이터 멤버의 형식은 `DateTimeStatus` `COleDateTime` 클래스 내에서 정의된 수련 된 형식입니다. 자세한 내용은 [COleDateTime::GetStatus](#getstatus)를 참조하십시오.

> [!CAUTION]
> 이 데이터 멤버는 고급 프로그래밍 상황에 적합합니다. 인라인 멤버 함수 [GetStatus](#getstatus) 및 [SetStatus를](#setstatus)사용 해야 합니다. 이 `SetStatus` 데이터 멤버를 명시적으로 설정하는 것에 대한 자세한 내용은 참조하세요.

## <a name="coledatetimeoperator-"></a><a name="operator_eq"></a>COleDateTime::연산자 =

값을 복사합니다. `COleDateTime`

```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& uDate) throw();
```

### <a name="remarks"></a>설명

이러한 오버로드된 할당 연산자는 원본 날짜/시간 값을 이 `COleDateTime` 개체에 복사합니다. 이러한 오버로드된 각 할당 연산자에 대한 간략한 설명은 다음과 같습니다.

- **연산자 =()** `dateSrc` **)** 피연산자의 값과 상태가 이 `COleDateTime` 개체에 복사됩니다.

- **연산자** *=(varSrc)* **)** [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 값(또는 [COleVariant](../../mfc/reference/colevariant-class.md) 개체)을 날짜/시간(VT_DATE)으로 변환하는 데 성공하면 변환된 값이 `COleDateTime` 이 개체에 복사되고 해당 상태가 유효한 것으로 설정됩니다. 변환에 성공하지 못하면 이 개체의 값이 0(1899년 12월 30일 자정)으로 설정되고 상태가 유효하지 않은 것으로 설정됩니다.

- **연산자 =()** `dtSrc` **)** `DATE` 값이 이 `COleDateTime` 개체에 복사되고 해당 상태가 유효한 것으로 설정됩니다.

- **연산자 =()** `timeSrc` **)** 또는 값이 변환되어 이 `COleDateTime` 개체로 복사됩니다. `__time64_t` `time_t` 변환에 성공하면 이 개체의 상태가 유효한 것으로 설정됩니다. 실패하면 유효하지 않은 것으로 설정됩니다.

- **연산자** *=(systimeSrc)* **)** [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 값이 변환되어 이 `COleDateTime` 개체로 복사됩니다. 변환에 성공하면 이 개체의 상태가 유효한 것으로 설정됩니다. 실패하면 유효하지 않은 것으로 설정됩니다.

- **연산자 =()** `uDate` **)** `UDATE` 값이 변환되어 이 `COleDateTime` 개체로 복사됩니다. 변환에 성공하면 이 개체의 상태가 유효한 것으로 설정됩니다. 실패하면 유효하지 않은 것으로 설정됩니다. 구조는 `UDATE` "압축 해제" 날짜를 나타냅니다. 자세한 내용은 [VarDateFromUdate](/windows/win32/api/oleauto/nf-oleauto-vardatefromudate)기능을 참조하십시오.

- **연산자 =()** `filetimeSrc` **)** [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 값이 변환되어 이 `COleDateTime` 개체로 복사됩니다. 변환에 성공하면 이 개체의 상태가 유효한 것으로 설정됩니다. 그렇지 않으면 유효하지 않은 것으로 설정됩니다. `FILETIME`UTC(유니버설 조정 시간)를 사용하므로 구조에서 UTC 시간을 통과하면 결과가 UTC 시간에서 현지 시간으로 변환되고 변형 시간으로 저장됩니다. 이 동작은 Visual C++ 6.0 및 Visual C++.NET 2003 SP2와 동일합니다. 자세한 내용은 Windows SDK의 [파일 시간을](/windows/win32/SysInfo/file-times) 참조하십시오.

자세한 내용은 Windows SDK의 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 항목을 참조하십시오.

데이터 형식에 `time_t` 대한 자세한 내용은 *런타임 라이브러리 참조의* [시간](../../c-runtime-library/reference/time-time32-time64.md) 함수를 참조하십시오.

자세한 내용은 Windows SDK의 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 및 [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 구조를 참조하십시오.

값의 경계에 대한 `COleDateTime` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

## <a name="coledatetimeoperator---"></a><a name="operator_add_-"></a>COleDate시간::연산자 +, -

값을 추가하고 `ColeDateTime` 뺍니다.

```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```

### <a name="remarks"></a>설명

`COleDateTime`개체는 절대 시간을 나타냅니다. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) 개체는 상대 시간을 나타냅니다. 처음 두 연산자는 값에서 `COleDateTimeSpan` 값을 추가하고 뺄 `COleDateTime` 수 있습니다. 세 번째 연산자는 값을 `COleDateTime` 산출하기 위해 `COleDateTimeSpan` 다른 값에서 한 값을 뺄 수 있습니다.

피연산자 중 하나가 null이면 결과 `COleDateTime` 값의 상태는 null입니다.

결과 `COleDateTime` 값이 허용 가능한 값의 범위를 벗어나면 해당 `COleDateTime` 값의 상태가 잘못됩니다.

피연산자 중 하나가 유효하지 않고 다른 피연산자 중 `COleDateTime` 하나가 null이 아닌 경우 결과 값의 상태가 유효하지 않습니다.

**+** 및 **-** 연산자는 개체가 `COleDateTime` null로 설정된 경우 어설션합니다. 예는 [COleDateTime 관계형 연산자를](#coledatetime_relational_operators) 참조하십시오.

유효, 유효하지 않은 및 null 상태 값에 대한 자세한 내용은 [m_status](#m_status) 멤버 변수를 참조하십시오.

값의 경계에 대한 `COleDateTime` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]

## <a name="coledatetimeoperator---"></a><a name="operator_add_eq_-_eq"></a>COleDateTime::연산자 +=, -=

이 `COleDateTime` 개체에서 `ColeDateTime` 값을 추가하고 뺍니다.

```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>설명

이러한 연산자는 이 에서 `COleDateTimeSpan` 및 에서 값을 `COleDateTime`추가하고 뺄 수 있도록 합니다. 피연산자 중 하나가 null이면 결과 `COleDateTime` 값의 상태는 null입니다.

결과 `COleDateTime` 값이 허용 가능한 값의 범위를 벗어나면 이 `COleDateTime` 값의 상태가 유효하지 않은 상태로 설정됩니다.

피연산자 중 하나가 유효하지 않고 다른 피연산자 중 `COleDateTime` 하나가 null이 아닌 경우 결과 값의 상태가 유효하지 않습니다.

유효, 유효하지 않은 및 null 상태 값에 대한 자세한 내용은 [m_status](#m_status) 멤버 변수를 참조하십시오.

**+=** 및 **-=** 연산자는 개체가 `COleDateTime` null로 설정된 경우 어설션합니다. 예는 [COleDateTime 관계형 연산자를](#coledatetime_relational_operators) 참조하십시오.

값의 경계에 대한 `COleDateTime` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

## <a name="coledatetimeoperator-date"></a><a name="operator_date"></a>COleDateTime::연산자 날짜

`ColeDateTime` 값을 로 `DATE`변환합니다.

```
operator DATE() const throw();
```

### <a name="remarks"></a>설명

이 연산자는 이 `DATE` `COleDateTime` 개체에서 값이 복사된 개체를 반환합니다. 개체 구현에 대한 자세한 내용은 날짜 [및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오. `DATE`

개체가 `DATE` null로 `COleDateTime` 설정된 경우 연산자는 어설션합니다. 예는 [COleDateTime 관계형 연산자를](#coledatetime_relational_operators) 참조하십시오.

## <a name="coledatetimeparsedatetime"></a><a name="parsedatetime"></a>콜레데이트타임::P어스데이트타임

문자열을 구문 분석하여 날짜/시간 값을 읽습니다.

```
bool ParseDateTime(
    LPCTSTR lpszDate,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT) throw();
```

### <a name="parameters"></a>매개 변수

*lpszDate*<br/>
구문 분석할 null 종료된 문자열에 대한 포인터입니다. 자세한 내용은 설명을 참조하세요.

*dwFlags*<br/>
로캘 설정 및 구문 분석에 대한 플래그를 나타냅니다. 다음 플래그 중 하나 이상:

- LOCALE_NOUSEROVERRIDE 사용자 지정 사용자 설정이 아닌 시스템 기본 로캘 설정을 사용합니다.

- VAR_TIMEVALUEONLY 구문 분석 하는 동안 날짜 부분을 무시 합니다.

- VAR_DATEVALUEONLY 구문 분석 하는 동안 시간 부분을 무시 합니다.

*Lcid*<br/>
변환에 사용할 로캘 ID를 나타냅니다.

### <a name="return-value"></a>Return Value

문자열이 날짜/시간 값(그렇지 않으면 FALSE)으로 성공적으로 변환된 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

문자열이 날짜/시간 값으로 성공적으로 변환된 경우 이 `COleDateTime` 개체의 값은 해당 값으로 설정되고 해당 상태는 유효한 것으로 설정됩니다.

> [!NOTE]
> 연도 값은 100에서 9999 사이여야 합니다.

*lpszDate* 매개 변수는 다양한 형식을 취할 수 있습니다. 예를 들어 다음 문자열에는 허용 가능한 날짜/시간 형식이 포함됩니다.

`"25 January 1996"`

`"8:30:00"`

`"20:30:00"`

`"January 25, 1996 8:30:00"`

`"8:30:00 Jan. 25, 1996"`

`"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`

로캘 ID는 문자열 형식이 날짜/시간 값으로 변환할 수 있는지 여부에도 영향을 미칩니다.

VAR_DATEVALUEONLY 경우 시간 값은 시간 0 또는 자정으로 설정됩니다. VAR_TIMEVALUEONLY 경우 날짜 값은 1899년 12월 30일을 의미하는 0날짜로 설정됩니다.

문자열을 날짜/시간 값으로 변환할 수 없거나 숫자 오버플로가 있는 경우 이 `COleDateTime` 개체의 상태가 잘못되었습니다.

값의 경계 및 구현에 `COleDateTime` 대한 자세한 내용은 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

## <a name="coledatetimesetdate"></a><a name="setdate"></a>콜레데이트 타임::세트데이트

이 `COleDateTime` 개체의 날짜를 설정합니다.

```
int SetDate(
    int nYear,
    int nMonth,
    int nDay) throw();
```

### <a name="parameters"></a>매개 변수

*nYear,* *nMonth*, *nDay*<br/>
이 `COleDateTime` 개체에 복사할 날짜를 지정합니다.

### <a name="return-value"></a>Return Value

이 `COleDateTime` 개체의 값이 성공적으로 설정된 경우 0입니다. 그렇지 않으면 1. 이 반환 값은 `DateTimeStatus` 수온이 있는 형식을 기반으로 합니다. 자세한 내용은 [SetStatus](#setstatus) 멤버 함수를 참조하십시오.

### <a name="remarks"></a>설명

날짜가 지정된 값으로 설정됩니다. 시간은 시간 0, 자정으로 설정됩니다.

매개 변수 값에 대한 경계는 다음 표를 참조하십시오.

|매개 변수|Bounds|
|---------------|------------|
|*nYear*|100 - 9999|
|*nMonth*|1 - 12|
|*nDay*|0 - 31|

해당 월의 일이 초과되면 다음 달의 올바른 요일로 변환되고 해당 월에 따라 연도가 증가합니다. 일 값 0은 이전 달의 마지막 날을 나타냅니다. 동작은 `SystemTimeToVariantTime`와 동일합니다.

매개 변수에 의해 지정된 날짜 값이 유효하지 않으면 이 개체의 상태가 로 `COleDateTime::invalid`설정됩니다. [GetStatus를](#getstatus) 사용하여 `DATE` 값의 유효성을 확인해야 하며 [m_dt](#m_dt) 값이 수정되지 않은 상태로 유지된다고 가정해서는 안 됩니다.

다음은 날짜 값의 몇 가지 예입니다.

|*nYear*|*nMonth*|*nDay*|값|
|-------------|--------------|------------|-----------|
|2000|2|29|2000년 2월 29일|
|1776|7|4|1776년 7월 4일|
|1925|4|35|1925년 4월 35일(유효하지 않음)|
|10000|1|1|1월 1일 10000(유효하지 않음)|

날짜와 시간을 모두 설정하려면 [COleDateTime::SetDateTime](#setdatetime)을 참조하십시오.

이 `COleDateTime` 개체의 값을 쿼리하는 멤버 함수에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [겟데이](#getday)

- [겟월](#getmonth)

- [Getyear](#getyear)

- [겟아워](#gethour)

- [겟미닛](#getminute)

- [GetSecond](#getsecond)

- [겟데이오브위크](#getdayofweek)

- [겟데이오브이어](#getdayofyear)

값의 경계에 대한 `COleDateTime` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]

## <a name="coledatetimesetdatetime"></a><a name="setdatetime"></a>콜레데이트 타임::세트데이트 타임

이 `COleDateTime` 개체의 날짜와 시간을 설정합니다.

```
int SetDateTime(
    int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>매개 변수

*nYear*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
이 `COleDateTime` 개체에 복사할 날짜 및 시간 구성요소를 지정합니다.

### <a name="return-value"></a>Return Value

이 `COleDateTime` 개체의 값이 성공적으로 설정된 경우 0입니다. 그렇지 않으면 1. 이 반환 값은 `DateTimeStatus` 수온이 있는 형식을 기반으로 합니다. 자세한 내용은 [SetStatus](#setstatus) 멤버 함수를 참조하십시오.

### <a name="remarks"></a>설명

매개 변수 값에 대한 경계는 다음 표를 참조하십시오.

|매개 변수|Bounds|
|---------------|------------|
|*nYear*|100 - 9999|
|*nMonth*|1 - 12|
|*nDay*|0 - 31|
|*nHour*|0 - 23|
|*nMin*|0 - 59|
|*nSec*|0 - 59|

해당 월의 일이 초과되면 다음 달의 올바른 요일로 변환되고 해당 월에 따라 연도가 증가합니다. 일 값 0은 이전 달의 마지막 날을 나타냅니다. 동작은 [SystemTimeToVariantTime](/windows/win32/api/oleauto/nf-oleauto-systemtimetovarianttime)과 동일합니다.

매개 변수에 의해 지정된 날짜 또는 시간 값이 유효하지 않으면 이 개체의 상태가 유효하지 않은 것으로 설정되고 이 개체의 값이 변경되지 않습니다.

다음은 시간 값의 몇 가지 예입니다.

|*nHour*|*nMin*|*nSec*|값|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|올바르지 않음|
|9|60|0|올바르지 않음|

다음은 날짜 값의 몇 가지 예입니다.

|*nYear*|*nMonth*|*nDay*|값|
|-------------|--------------|------------|-----------|
|1995|4|15|1995년 4월 15일|
|1789|7|14|1789년 7월 17일|
|1925|2|30|올바르지 않음|
|10000|1|1|올바르지 않음|

날짜만 설정하려면 [COleDateTime::SetDate](#setdate)를 참조하십시오. 시간만 설정하려면 [COleDateTime::SetTime](#settime)을 참조하십시오.

이 `COleDateTime` 개체의 값을 쿼리하는 멤버 함수에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [겟데이](#getday)

- [겟월](#getmonth)

- [Getyear](#getyear)

- [겟아워](#gethour)

- [겟미닛](#getminute)

- [GetSecond](#getsecond)

- [겟데이오브위크](#getdayofweek)

- [겟데이오브이어](#getdayofyear)

값의 경계에 대한 `COleDateTime` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

### <a name="example"></a>예제

[GetStatus](#getstatus)에 대한 예제를 참조하십시오.

## <a name="coledatetimesetstatus"></a><a name="setstatus"></a>COleDate시간::설정 상태

이 `COleDateTime` 개체의 상태를 설정합니다.

```cpp
void SetStatus(DateTimeStatus status) throw();
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
이 `COleDateTime` 개체의 새 상태 값입니다.

### <a name="remarks"></a>설명

*상태* 매개 변수 값은 `DateTimeStatus` 클래스 내에서 정의된 수거된 `COleDateTime` 형식에 의해 정의됩니다. 자세한 내용은 [COleDateTime::GetStatus를](#getstatus) 참조하십시오.

> [!CAUTION]
> 이 함수는 고급 프로그래밍 상황에 적합합니다. 이 함수는 이 개체의 데이터를 변경하지 않습니다. 상태를 **null** 또는 **유효하지 않은**상태로 설정하는 데 가장 자주 사용됩니다. 할당 연산자[(연산자 =](#operator_eq)) 및 [SetDateTime](#setdatetime) 소스 값에 따라 개체의 상태를 설정 합니다.

### <a name="example"></a>예제

[GetStatus](#getstatus)에 대한 예제를 참조하십시오.

## <a name="coledatetimesettime"></a><a name="settime"></a>콜레데이트 타임::세트타임

이 `COleDateTime` 개체의 시간을 설정합니다.

```
int SetTime(
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>매개 변수

*nHour,* *nMin,* *nSec*<br/>
이 `COleDateTime` 개체에 복사할 시간 구성 요소를 나타냅니다.

### <a name="return-value"></a>Return Value

이 `COleDateTime` 개체의 값이 성공적으로 설정된 경우 0입니다. 그렇지 않으면 1. 이 반환 값은 `DateTimeStatus` 수온이 있는 형식을 기반으로 합니다. 자세한 내용은 [SetStatus](#setstatus) 멤버 함수를 참조하십시오.

### <a name="remarks"></a>설명

시간은 지정된 값으로 설정됩니다. 날짜는 1899년 12월 30일을 의미하는 0날짜로 설정됩니다.

매개 변수 값에 대한 경계는 다음 표를 참조하십시오.

|매개 변수|Bounds|
|---------------|------------|
|*nHour*|0 - 23|
|*nMin*|0 - 59|
|*nSec*|0 - 59|

매개 변수에 의해 지정된 시간 값이 유효하지 않으면 이 개체의 상태가 유효하지 않은 상태로 설정되고 이 개체의 값이 변경되지 않습니다.

다음은 시간 값의 몇 가지 예입니다.

|*nHour*|*nMin*|*nSec*|값|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|올바르지 않음|
|9|60|0|올바르지 않음|

날짜와 시간을 모두 설정하려면 [COleDateTime::SetDateTime](#setdatetime)을 참조하십시오.

이 `COleDateTime` 개체의 값을 쿼리하는 멤버 함수에 대한 자세한 내용은 다음 멤버 함수를 참조하십시오.

- [겟데이](#getday)

- [겟월](#getmonth)

- [Getyear](#getyear)

- [겟아워](#gethour)

- [겟미닛](#getminute)

- [GetSecond](#getsecond)

- [겟데이오브위크](#getdayofweek)

- [겟데이오브이어](#getdayofyear)

값의 경계에 대한 `COleDateTime` 자세한 내용은 날짜 및 [시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)문서를 참조하십시오.

### <a name="example"></a>예제

[SetDate](#setdate)에 대한 예제를 참조하십시오.

## <a name="see-also"></a>참조

[COle변형 클래스](../../mfc/reference/colevariant-class.md)<br/>
[CTime 클래스](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[C타임스팬 클래스](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
