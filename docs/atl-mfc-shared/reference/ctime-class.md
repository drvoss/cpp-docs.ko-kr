---
title: CTime 클래스
ms.date: 10/18/2018
f1_keywords:
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
ms.openlocfilehash: e6e471fe648c5fa370cce750e8569e158eb1ffe4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317563"
---
# <a name="ctime-class"></a>CTime 클래스

절대 시간과 날짜를 나타냅니다.

## <a name="syntax"></a>구문

```
class CTime
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C시간::CTime](#ctime)|다양한 `CTime` 방법으로 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CTime::Format](#format)|개체를 `CTime` 현지 표준 시간대에 따라 형식이 지정된 문자열로 변환합니다.|
|[CTime::FormatGmt](#formatgmt)|UTC를 `CTime` 기반으로 오브젝트를 형식이 지정된 문자열로 변환합니다.|
|[C시간::겟아스DB타임스탬프](#getasdbtimestamp)|`CTime` 개체에 저장된 시간 정보를 Win32 호환 DBTIMESTAMP 구조로 변환합니다.|
|[CTime::GetAsSystemTime](#getassystemtime)|`CTime` 개체에 저장된 시간 정보를 Win32 호환 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조로 변환합니다.|
|[C시간::GetCurrentTime](#getcurrenttime)|현재 `CTime` 시간(정적 멤버 함수)을 나타내는 개체를 만듭니다.|
|[CTime::GetDay](#getday)|객체에 의해 나타내는 `CTime` 일을 반환합니다.|
|[C시간::겟데이오브위크](#getdayofweek)|개체로 표시된 요일을 반환합니다. `CTime`|
|[C시간::겟GmtTm](#getgmttm)|UTC를 `CTime` 기반으로 오브젝트를 구성 요소로 나눕습니다.|
|[C시간::겟아워](#gethour)|개체로 표시되는 시간을 `CTime` 반환합니다.|
|[CTime::GetLocalTm](#getlocaltm)|대상을 `CTime` 현지 표준 시간대에 따라 구성 요소로 나눕습니다.|
|[CTime::GetMinute](#getminute)|개체로 표시되는 분을 `CTime` 반환합니다.|
|[C시간::GetMonth](#getmonth)|개체로 표시되는 월을 반환합니다. `CTime`|
|[C시간::GetSecond](#getsecond)|개체로 표시되는 두 `CTime` 번째 를 반환합니다.|
|[C시간::GetTime](#gettime)|지정된 `CTime` 개체에 대한 **__time64_t** 값을 반환합니다.|
|[C시간::GetYear](#getyear)|개체로 표시되는 연도를 반환합니다. `CTime`|
|[CTime::Serialize64](#serialize64)|아카이브에서 데이터를 직렬화합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 + -](#operator_add_-)|이러한 연산자는 `CTimeSpan` 객체와 `CTime` 객체를 추가하고 뺍니다.|
|[연산자 +=, -=](#operator_add_eq_-_eq)|이러한 연산자는 이 `CTimeSpan` 개체에 개체를 `CTime` 추가하고 빼고 빼고 이 개체에서 개체를 뺍니다.|
|[연산자 =](#operator_eq)|할당 연산자입니다.|
|[operator ==, < , etc.](#ctime_comparison_operators)|비교 연산자.|

## <a name="remarks"></a>설명

`CTime`기본 클래스가 없습니다.

`CTime`값은 조정된 유니버설 시간(그리니치 표준시, GMT)과 동일한 조정된 유니버설 시간(UTC)을 기반으로 합니다. 표준 시간대가 결정되는 방법에 대한 정보는 [시간 관리를](../../c-runtime-library/time-management.md) 참조하십시오.

개체를 `CTime` 만들 때 `nDST` 매개 변수를 0으로 설정하여 표준 시간이 적용중임을 나타내거나 0보다 큰 값으로 설정하여 일광 절약 시간이 적용되고 있음을 나타내거나 C 런타임 라이브러리 코드가 표준 시간 또는 일광 절약 시간이 적용되는지 여부를 계산하도록 0보다 작은 값으로 설정합니다. `tm_isdst`는 필수 필드입니다. 설정하지 않으면 해당 값이 정의되지 않으며 [mktime의](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) 반환 값을 예측할 수 없습니다. `timeptr`가 [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md) 또는 [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)에 대한 이전 호출에서 반환된 tm 구조를 가리키면 `tm_isdst`필드에 올바른 값이 포함됩니다.

동반자 클래스인 [CTimeSpan은](../../atl-mfc-shared/reference/ctimespan-class.md)시간 간격을 나타냅니다.

`CTime` 및 `CTimeSpan` 클래스는 파생을 위해 설계되지 않았습니다. 가상 함수가 없기 때문에 `CTime` `CTimeSpan` 개체의 크기와 개체의 크기는 정확히 8바이트입니다. 대부분의 멤버 함수는 인라인입니다.

> [!NOTE]
> 상한은 12/31/3000입니다. 하한은 1970년 1월 1일 오전 12:00:00 GMT입니다.

사용에 `CTime`대한 자세한 내용은 런타임 라이브러리 참조에서 [날짜 및 시간](../../atl-mfc-shared/date-and-time.md)및 시간 [관리](../../c-runtime-library/time-management.md) 문서를 참조하십시오.

> [!NOTE]
> 구조는 `CTime` MFC 7.1에서 MFC 8.0으로 변경되었습니다. MFC 8.0 또는 이후 버전에서 `CTime` **연산자 <<** 사용하여 구조를 직렬화하는 경우 이전 버전의 MFC에서는 결과 파일을 읽을 수 없습니다.

## <a name="requirements"></a>요구 사항

**헤더:** 아틀타임.h

## <a name="ctime-comparison-operators"></a><a name="ctime_comparison_operators"></a>CTime 비교 연산자

비교 연산자.

```
bool operator==(CTime time) const throw();
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw();
```

### <a name="parameters"></a>매개 변수

*time*<br/>
비교할 `CTime` 개체입니다.

### <a name="return-value"></a>Return Value

이러한 연산자는 두 번의 절대 시간을 비교하고 조건이 true인 경우 TRUE를 반환합니다. 그렇지 않으면 거짓.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

## <a name="ctimectime"></a><a name="ctime"></a>C시간::CTime

지정된 시간으로 `CTime` 초기화된 새 개체를 만듭니다.

```
CTime() throw();
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts, int nDST = -1) throw();
```

### <a name="parameters"></a>매개 변수

*timeSrc*<br/>
이미 `CTime` 있는 개체를 나타냅니다.

*time*<br/>
`__time64_t` 시간 값(1970년 1월 1일 이후의 초)입니다. 현지 시간으로 조정됩니다. 예를 들어 뉴욕에 있고 0의 매개 `CTime` 변수를 전달하여 개체를 만드는 경우 [CTime:GetMonth은](#getmonth) 12를 반환합니다.

*nYear*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
새 `CTime` 개체에 복사할 날짜 및 시간 값을 나타냅니다.

*nDST*<br/>
일광 절약 시간이 적용되는지 여부를 나타냅니다. 세 가지 값 중 하나를 가질 수 있습니다.

- *nDST가* 0표준 시간으로 설정되어 있습니다.

- *nDST가* 0Daylight 절약 시간보다 큰 값으로 설정됩니다.

- *nDST는* 0보다 작은 값으로 설정기본값입니다. 표준 시간또는 일광 절약 시간이 적용되는지 여부를 자동으로 계산합니다.

*wDosDate*, *wDosTime*<br/>
날짜/시간 값으로 변환하고 새 `CTime` 개체로 복사할 MS-DOS 날짜 및 시간 값입니다.

*세인트*<br/>
날짜/시간 값으로 변환되고 새 `CTime`개체로 복사되는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조체입니다.

*피트*<br/>
날짜/시간 값으로 변환되고 새 `CTime` 개체로 복사 되는 [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 구조체입니다.

*Dbts*<br/>
현재 현지 시간을 포함하는 DBTIMESTAMP 구조에 대한 참조입니다.

### <a name="remarks"></a>설명

각 생성자는 아래에 설명되어 있습니다.

- `CTime();`초기화되지 않은 `CTime` 개체를 생성합니다. 이 생성기를 사용하면 `CTime` 개체 배열을 정의할 수 있습니다. 이러한 배열을 사용하기 전에 유효한 시간을 사용하여 초기화해야 합니다.

- `CTime( const CTime& );`다른 `CTime` `CTime` 값에서 개체를 생성합니다.

- `CTime( __time64_t );``CTime` **__time64_t** 형식에서 개체를 생성합니다. 이 생성자는 UTC 시간을 예상하고 결과를 저장하기 전에 결과를 현지 시간으로 변환합니다.

- `CTime( int, int, ...);`각 구성요소가 다음 범위로 구속된 현지 시간 구성요소에서 `CTime` 객체를 생성합니다.

   |구성 요소|범위|
   |---------------|-----------|
   |*nYear*|1970-3000|
   |*nMonth*|1-12|
   |*nDay*|1-31|
   |*nHour*|0-23|
   |*nMin*|0-59|
   |*nSec*|0-59|

   이 생성자는 UTC로 적절한 변환을 합니다. Microsoft 파운데이션 클래스 라이브러리의 디버그 버전은 하나 이상의 시간 구성 요소가 범위를 벗어난 경우 어설션합니다. 호출하기 전에 인수의 유효성을 검사해야 합니다. 이 생성자는 현지 시간을 예상합니다.

- `CTime( WORD, WORD );`지정된 MS-DOS 날짜 및 시간 값에서 `CTime` 개체를 생성합니다. 이 생성자는 현지 시간을 예상합니다.

- `CTime( const SYSTEMTIME& );`구조체에서 `CTime` 개체를 `SYSTEMTIME` 생성합니다. 이 생성자는 현지 시간을 예상합니다.

- `CTime( const FILETIME& );`구조체에서 `CTime` 개체를 `FILETIME` 생성합니다. 초기화를 직접 사용하지 `CTime FILETIME` 않을 가능성이 높습니다. 개체를 `CFile` 사용하여 파일을 조작하는 경우 `CFile::GetStatus` 구조체로 초기화된 `CTime` 개체를 통해 파일 `FILETIME` 타임스탬프를 검색합니다. 이 생성자는 UTC를 기반으로 하는 시간을 가정하고 결과를 저장하기 전에 값을 현지 시간으로 자동으로 변환합니다.

   > [!NOTE]
   > 매개 변수를 `DBTIMESTAMP` 사용하는 생성자는 OLEDB.h가 포함된 경우에만 사용할 수 있습니다.

자세한 내용은 Windows SDK의 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 및 [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 구조를 참조하십시오. 또한 Windows SDK에서 [MS-DOS 날짜 및 시간](/windows/win32/SysInfo/ms-dos-date-and-time) 항목을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

## <a name="ctimeformat"></a><a name="format"></a>C시간::형식

이 멤버 함수를 호출하여 날짜 시간 값의 형식이 지정된 표현을 만듭니다.

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
`printf` 서식 문자열과 유사한 서식 문자열입니다. 백분율()`%`기호 앞에 오는 서식 지정 코드는 `CTime` 해당 구성 요소로 대체됩니다. 서식 문자열의 다른 문자는 반환된 문자열에 변경되지 않고 복사됩니다. 서식 코드 목록은 런타임 함수 [strftime을](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 참조하십시오.

*nFormatID*<br/>
이 형식을 식별하는 문자열의 ID입니다.

### <a name="return-value"></a>Return Value

형식이 지정된 시간을 포함하는 [CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>설명

이 `CTime` 개체의 상태가 null이면 반환 값은 빈 문자열입니다.

이 메서드는 형식에 날짜 시간 값이 1970년 1월 1일 자정부터 12월 31일 까지 3000 유니버설 조정 시간(UTC)의 범위가 지정되지 않는 경우 예외를 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

## <a name="ctimeformatgmt"></a><a name="formatgmt"></a>C시간::포맷Gmt

이 `CTime` 개체에 해당하는 서식이 지정된 문자열을 생성합니다.

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
서식 문자열과 유사한 서식 `printf` 문자열을 지정합니다. 자세한 내용은 런타임 함수 [strftime을](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 참조하십시오.

*nFormatID*<br/>
이 형식을 식별하는 문자열의 ID입니다.

### <a name="return-value"></a>Return Value

형식이 지정된 시간을 포함하는 [CString입니다.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>설명

시간 값은 변환되지 않으므로 UTC를 반영합니다.

이 메서드는 형식에 날짜 시간 값이 1970년 1월 1일 자정부터 12월 31일 까지 3000 유니버설 조정 시간(UTC)의 범위가 지정되지 않는 경우 예외를 throw합니다.

### <a name="example"></a>예제

[CTime::Format에](#format)대한 예제를 참조하십시오.

## <a name="ctimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>C시간::겟아스DB타임스탬프

이 멤버 함수를 호출하여 개체에 `CTime` 저장된 시간 정보를 Win32 호환 DBTIMESTAMP 구조로 변환합니다.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>매개 변수

*Dbts*<br/>
현재 현지 시간을 포함하는 DBTIMESTAMP 구조에 대한 참조입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

참조된 dbts 구조에 결과 시간을 *저장합니다.* 이 `DBTIMESTAMP` 함수에 의해 초기화된 `fraction` 데이터 구조에는 해당 멤버가 0으로 설정됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

## <a name="ctimegetassystemtime"></a><a name="getassystemtime"></a>C시간::겟아스시스템타임

이 멤버 함수를 호출하여 개체에 `CTime` 저장된 시간 정보를 Win32 호환 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조로 변환합니다.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>매개 변수

*timeDest*<br/>
개체의 변환된 날짜/시간 값을 보유하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 참조입니다. `CTime`

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

`GetAsSystemTime`은 참조된 *시간Dest* 구조에 결과 시간을 저장합니다. 이 `SYSTEMTIME` 함수에 의해 초기화된 `wMilliseconds` 데이터 구조에는 해당 멤버가 0으로 설정됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

## <a name="ctimegetcurrenttime"></a><a name="getcurrenttime"></a>C시간::GetCurrentTime

현재 `CTime` 시간을 나타내는 개체를 반환합니다.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>설명

조정된 유니버설 타임(UTC)에서 현재 시스템 날짜와 시간을 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

## <a name="ctimegetday"></a><a name="getday"></a>C시간::겟데이

객체에 의해 나타내는 `CTime` 일을 반환합니다.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Return Value

현지 시간을 기준으로 1부터 31까지의 범위에서 월의 요일을 반환합니다.

### <a name="remarks"></a>설명

이 함수는 정적으로 할당된 내부 버퍼를 사용하는 을 호출합니다. `GetLocalTm` 이 버퍼의 데이터는 다른 `CTime` 멤버 함수에 대한 호출로 인해 덮어씁니까.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

## <a name="ctimegetdayofweek"></a><a name="getdayofweek"></a>C시간::겟데이오브위크

개체로 표시된 요일을 반환합니다. `CTime`

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Return Value

현지 시간을 기준으로 요일을 반환합니다. 1 = 일요일, 2 = 월요일, 7 = 토요일.

### <a name="remarks"></a>설명

이 함수는 내부 정적으로 할당된 버퍼를 사용하는 `GetLocalTm`호출합니다. 이 버퍼의 데이터는 다른 `CTime` 멤버 함수에 대한 호출로 인해 덮어씁니까.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

## <a name="ctimegetgmttm"></a><a name="getgmttm"></a>C시간::겟GmtTm

이 `CTime` 개체에 포함된 시간의 분해가 포함된 **구조체 tm을** 가져옵니다.

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>매개 변수

*ptm*<br/>
시간 데이터를 수신하는 버퍼를 가리킵니다. 이 포인터가 NULL이면 예외가 throw됩니다.

### <a name="return-value"></a>Return Value

포함 파일 TIME에 정의된 대로 채워진 **구조체 tm에** 대한 포인터입니다. H. 구조 레이아웃에 대한 [gmtime, _gmtime32 _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) 참조하십시오.

### <a name="remarks"></a>설명

`GetGmtTm`UTC를 반환합니다.

*ptm은* NULL이 될 수 없습니다. *ptm이* NULL일 수 있는 이전 동작으로 되돌리려면 정적으로 할당된 내부 버퍼를 사용해야 함을 나타내고 _SECURE_ATL 정의 해제합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

## <a name="ctimegethour"></a><a name="gethour"></a>C시간::겟아워

개체로 표시되는 시간을 `CTime` 반환합니다.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Return Value

0에서 23 범위의 현지 시간을 기준으로 시간을 반환합니다.

### <a name="remarks"></a>설명

이 함수는 내부 정적으로 할당된 버퍼를 사용하는 `GetLocalTm`호출합니다. 이 버퍼의 데이터는 다른 `CTime` 멤버 함수에 대한 호출로 인해 덮어씁니까.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

## <a name="ctimegetlocaltm"></a><a name="getlocaltm"></a>C시간::GetLocalTm

이 `CTime` 개체에 포함된 시간의 분해를 포함하는 **구조체 tm을** 가져옵니다.

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>매개 변수

*ptm*<br/>
시간 데이터를 수신하는 버퍼를 가리킵니다. 이 포인터가 NULL이면 예외가 throw됩니다.

### <a name="return-value"></a>Return Value

포함 파일 TIME에 정의된 대로 채워진 **구조체 tm에** 대한 포인터입니다. H. 구조 레이아웃에 대한 [gmtime, _gmtime32 _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) 참조하십시오.

### <a name="remarks"></a>설명

`GetLocalTm`현지 시간을 반환합니다.

*ptm은* NULL이 될 수 없습니다. *ptm이* NULL일 수 있는 이전 동작으로 되돌리려면 정적으로 할당된 내부 버퍼를 사용해야 함을 나타내고 _SECURE_ATL 정의 해제합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

## <a name="ctimegetminute"></a><a name="getminute"></a>C시간::GetMinute

개체로 표시되는 분을 `CTime` 반환합니다.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Return Value

현지 시간을 기준으로 0에서 59 범위로 분을 반환합니다.

### <a name="remarks"></a>설명

이 함수는 내부 정적으로 할당된 버퍼를 사용하는 `GetLocalTm`호출합니다. 이 버퍼의 데이터는 다른 `CTime` 멤버 함수에 대한 호출로 인해 덮어씁니까.

### <a name="example"></a>예제

[GetHour에](#gethour)대한 예제를 참조하십시오.

## <a name="ctimegetmonth"></a><a name="getmonth"></a>C시간::GetMonth

개체로 표시되는 월을 반환합니다. `CTime`

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Return Value

현지 시간을 기준으로 1부터 12까지(1 = 1월)의 월을 반환합니다.

### <a name="remarks"></a>설명

이 함수는 내부 정적으로 할당된 버퍼를 사용하는 `GetLocalTm`호출합니다. 이 버퍼의 데이터는 다른 `CTime` 멤버 함수에 대한 호출로 인해 덮어씁니까.

### <a name="example"></a>예제

[GetDay에](#getday)대한 예제를 참조하십시오.

## <a name="ctimegetsecond"></a><a name="getsecond"></a>C시간::GetSecond

개체로 표시되는 두 `CTime` 번째 를 반환합니다.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Return Value

0에서 59 범위의 현지 시간을 기준으로 두 번째 를 반환합니다.

### <a name="remarks"></a>설명

이 함수는 내부 정적으로 할당된 버퍼를 사용하는 `GetLocalTm`호출합니다. 이 버퍼의 데이터는 다른 `CTime` 멤버 함수에 대한 호출로 인해 덮어씁니까.

### <a name="example"></a>예제

[GetHour에](#gethour)대한 예제를 참조하십시오.

## <a name="ctimegettime"></a><a name="gettime"></a>C시간::GetTime

지정된 `CTime` 개체에 대한 **__time64_t** 값을 반환합니다.

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>Return Value

`GetTime`은 현재 `CTime` 개체와 1970년 1월 1일 사이의 초 수를 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

## <a name="ctimegetyear"></a><a name="getyear"></a>C시간::GetYear

개체로 표시되는 연도를 반환합니다. `CTime`

```
int GetYear();
```

### <a name="return-value"></a>Return Value

1970년 1월 1일부터 2038년 1월 18일(포함)까지의 현지 시간을 기준으로 연도를 반환합니다.

### <a name="remarks"></a>설명

이 함수는 내부 정적으로 할당된 버퍼를 사용하는 `GetLocalTm`호출합니다. 이 버퍼의 데이터는 다른 `CTime` 멤버 함수에 대한 호출로 인해 덮어씁니까.

### <a name="example"></a>예제

[GetDay에](#getday)대한 예제를 참조하십시오.

## <a name="ctimeoperator-"></a><a name="operator_eq"></a>C시간::연산자 =

할당 연산자입니다.

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>매개 변수

*time*<br/>
새 날짜/시간 값입니다.

### <a name="return-value"></a>Return Value

업데이트된 `CTime` 개체입니다.

### <a name="remarks"></a>설명

이 오버로드된 할당 연산자는 `CTime` 소스 시간을 이 개체에 복사합니다. `CTime` 개체의 내부 시간 저장소는 표준 시간대와 독립적입니다. 할당 하는 동안 표준 시간대 변환이 필요 하지 않습니다.

## <a name="ctimeoperator---"></a><a name="operator_add_-"></a>C시간::연산자 +, -

이러한 연산자는 `CTimeSpan` 객체와 `CTime` 객체를 추가하고 뺍니다.

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>매개 변수

*Timespan*<br/>
추가하거나 뺄 `CTimeSpan` 대상입니다.

*time*<br/>
빼는 `CTime` 개체입니다.

### <a name="return-value"></a>Return Value

작업의 `CTime` `CTimeSpan` 결과를 나타내는 A 또는 개체입니다.

### <a name="remarks"></a>설명

`CTime`개체는 절대 `CTimeSpan` 시간을 나타내고, 객체는 상대 시간을 나타냅니다. 처음 두 연산자는 `CTimeSpan` `CTime` 객체에 객체를 추가하고 빼기 할 수 있습니다. 세 번째 연산자는 한 `CTime` 객체를 다른 `CTimeSpan` 오브젝트에서 빼서 객체를 생성할 수 있도록 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

## <a name="ctimeoperator---"></a><a name="operator_add_eq_-_eq"></a>C시간::연산자 +=, -=

이러한 연산자는 이 `CTimeSpan` 개체에 개체를 `CTime` 추가하고 빼고 빼고 이 개체에서 개체를 뺍니다.

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*범위*<br/>
추가하거나 뺄 `CTimeSpan` 대상입니다.

### <a name="return-value"></a>Return Value

업데이트된 `CTime` 개체입니다.

### <a name="remarks"></a>설명

이러한 연산자는 이 `CTimeSpan` `CTime` 개체에 객체를 추가하고 빼기 할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

## <a name="ctimeserialize64"></a><a name="serialize64"></a>C시간::직렬화64

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

[asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[C타임스팬 클래스](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
