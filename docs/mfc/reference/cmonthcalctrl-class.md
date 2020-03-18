---
title: CMonthCalCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::Create
- AFXDTCTL/CMonthCalCtrl::GetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::GetCalendarCount
- AFXDTCTL/CMonthCalCtrl::GetCalendarGridInfo
- AFXDTCTL/CMonthCalCtrl::GetCalID
- AFXDTCTL/CMonthCalCtrl::GetColor
- AFXDTCTL/CMonthCalCtrl::GetCurrentView
- AFXDTCTL/CMonthCalCtrl::GetCurSel
- AFXDTCTL/CMonthCalCtrl::GetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::GetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::GetMaxTodayWidth
- AFXDTCTL/CMonthCalCtrl::GetMinReqRect
- AFXDTCTL/CMonthCalCtrl::GetMonthDelta
- AFXDTCTL/CMonthCalCtrl::GetMonthRange
- AFXDTCTL/CMonthCalCtrl::GetRange
- AFXDTCTL/CMonthCalCtrl::GetSelRange
- AFXDTCTL/CMonthCalCtrl::GetToday
- AFXDTCTL/CMonthCalCtrl::HitTest
- AFXDTCTL/CMonthCalCtrl::IsCenturyView
- AFXDTCTL/CMonthCalCtrl::IsDecadeView
- AFXDTCTL/CMonthCalCtrl::IsMonthView
- AFXDTCTL/CMonthCalCtrl::IsYearView
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorderDefault
- AFXDTCTL/CMonthCalCtrl::SetCalID
- AFXDTCTL/CMonthCalCtrl::SetCenturyView
- AFXDTCTL/CMonthCalCtrl::SetColor
- AFXDTCTL/CMonthCalCtrl::SetCurrentView
- AFXDTCTL/CMonthCalCtrl::SetCurSel
- AFXDTCTL/CMonthCalCtrl::SetDayState
- AFXDTCTL/CMonthCalCtrl::SetDecadeView
- AFXDTCTL/CMonthCalCtrl::SetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::SetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::SetMonthDelta
- AFXDTCTL/CMonthCalCtrl::SetMonthView
- AFXDTCTL/CMonthCalCtrl::SetRange
- AFXDTCTL/CMonthCalCtrl::SetSelRange
- AFXDTCTL/CMonthCalCtrl::SetToday
- AFXDTCTL/CMonthCalCtrl::SetYearView
- AFXDTCTL/CMonthCalCtrl::SizeMinReq
- AFXDTCTL/CMonthCalCtrl::SizeRectToMin
helpviewer_keywords:
- CMonthCalCtrl [MFC], CMonthCalCtrl
- CMonthCalCtrl [MFC], Create
- CMonthCalCtrl [MFC], GetCalendarBorder
- CMonthCalCtrl [MFC], GetCalendarCount
- CMonthCalCtrl [MFC], GetCalendarGridInfo
- CMonthCalCtrl [MFC], GetCalID
- CMonthCalCtrl [MFC], GetColor
- CMonthCalCtrl [MFC], GetCurrentView
- CMonthCalCtrl [MFC], GetCurSel
- CMonthCalCtrl [MFC], GetFirstDayOfWeek
- CMonthCalCtrl [MFC], GetMaxSelCount
- CMonthCalCtrl [MFC], GetMaxTodayWidth
- CMonthCalCtrl [MFC], GetMinReqRect
- CMonthCalCtrl [MFC], GetMonthDelta
- CMonthCalCtrl [MFC], GetMonthRange
- CMonthCalCtrl [MFC], GetRange
- CMonthCalCtrl [MFC], GetSelRange
- CMonthCalCtrl [MFC], GetToday
- CMonthCalCtrl [MFC], HitTest
- CMonthCalCtrl [MFC], IsCenturyView
- CMonthCalCtrl [MFC], IsDecadeView
- CMonthCalCtrl [MFC], IsMonthView
- CMonthCalCtrl [MFC], IsYearView
- CMonthCalCtrl [MFC], SetCalendarBorder
- CMonthCalCtrl [MFC], SetCalendarBorderDefault
- CMonthCalCtrl [MFC], SetCalID
- CMonthCalCtrl [MFC], SetCenturyView
- CMonthCalCtrl [MFC], SetColor
- CMonthCalCtrl [MFC], SetCurrentView
- CMonthCalCtrl [MFC], SetCurSel
- CMonthCalCtrl [MFC], SetDayState
- CMonthCalCtrl [MFC], SetDecadeView
- CMonthCalCtrl [MFC], SetFirstDayOfWeek
- CMonthCalCtrl [MFC], SetMaxSelCount
- CMonthCalCtrl [MFC], SetMonthDelta
- CMonthCalCtrl [MFC], SetMonthView
- CMonthCalCtrl [MFC], SetRange
- CMonthCalCtrl [MFC], SetSelRange
- CMonthCalCtrl [MFC], SetToday
- CMonthCalCtrl [MFC], SetYearView
- CMonthCalCtrl [MFC], SizeMinReq
- CMonthCalCtrl [MFC], SizeRectToMin
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
ms.openlocfilehash: 963aecfed4f6eb67a0ab227df06fce98c0778f7f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425726"
---
# <a name="cmonthcalctrl-class"></a>CMonthCalCtrl 클래스

달력 컨트롤의 기능을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMonthCalCtrl:: CMonthCalCtrl](#cmonthcalctrl)|`CMonthCalCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMonthCalCtrl:: Create](#create)|Month calendar 컨트롤을 만들어 `CMonthCalCtrl` 개체에 연결 합니다.|
|[CMonthCalCtrl:: GetCalendarBorder](#getcalendarborder)|현재 month calendar 컨트롤의 테두리 너비를 검색 합니다.|
|[CMonthCalCtrl:: GetCalendarCount](#getcalendarcount)|현재 월 달력 컨트롤에 표시 되는 달력 수를 검색 합니다.|
|[CMonthCalCtrl:: GetCalendarGridInfo](#getcalendargridinfo)|현재 monthcalendar 컨트롤에 대 한 정보를 검색 합니다.|
|[CMonthCalCtrl:: GetCalID](#getcalid)|현재 monthcalendar 컨트롤의 달력 식별자를 검색 합니다.|
|[CMonthCalCtrl:: GetColor](#getcolor)|Month calendar 컨트롤의 지정 된 영역 색을 가져옵니다.|
|[CMonthCalCtrl:: GetCurrentView](#getcurrentview)|현재 monthcalendar 컨트롤에서 현재 표시 하는 뷰를 검색 합니다.|
|[CMonthCalCtrl:: GetCurSel](#getcursel)|현재 선택 된 날짜로 표시 되는 시스템 시간을 검색 합니다.|
|[CMonthCalCtrl:: GetFirstDayOfWeek](#getfirstdayofweek)|달력의 가장 왼쪽 열에 표시 되는 첫째 요일을 가져옵니다.|
|[CMonthCalCtrl:: GetMaxSelCount](#getmaxselcount)|Month calendar 컨트롤에서 선택할 수 있는 현재 최대 일 수를 검색 합니다.|
|[CMonthCalCtrl:: GetMaxTodayWidth](#getmaxtodaywidth)|현재 month calendar 컨트롤에 대 한 "Today" 문자열의 최대 너비를 검색 합니다.|
|[CMonthCalCtrl:: GetMinReqRect](#getminreqrect)|Month calendar 컨트롤에서 전체 월을 표시 하는 데 필요한 최소 크기를 검색 합니다.|
|[CMonthCalCtrl:: GetMonthDelta](#getmonthdelta)|Monthcalendar 컨트롤의 스크롤 주기를 검색 합니다.|
|[CMonthCalCtrl:: GetMonthRange](#getmonthrange)|Monthcalendar 컨트롤 표시의 상한 및 하 한을 나타내는 날짜 정보를 검색 합니다.|
|[CMonthCalCtrl:: GetRange](#getrange)|Month calendar 컨트롤에서 설정 된 현재 최소 및 최대 날짜를 검색 합니다.|
|[CMonthCalCtrl:: GetSelRange](#getselrange)|사용자가 현재 선택한 날짜 범위의 상한 및 하 한을 나타내는 날짜 정보를 검색 합니다.|
|[CMonthCalCtrl:: GetToday](#gettoday)|Monthcalendar 컨트롤에 대해 "오늘"로 지정 된 날짜에 대 한 날짜 정보를 검색 합니다.|
|[CMonthCalCtrl:: System.windows.media.visualtreehelper.hittest](#hittest)|화면의 지정 된 지점에 있는 monthcalendar 컨트롤의 섹션을 결정 합니다.|
|[CMonthCalCtrl:: IsCenturyView](#iscenturyview)|현재 monthcalendar 컨트롤의 현재 보기가 세기 뷰 인지 여부를 나타냅니다.|
|[CMonthCalCtrl:: IsDecadeView](#isdecadeview)|현재 월 달력 컨트롤의 현재 뷰가 10 월 뷰입니다 여부를 나타냅니다.|
|[CMonthCalCtrl:: IsMonthView](#ismonthview)|현재 월 달력 컨트롤의 현재 뷰가 월 보기 인지 여부를 나타냅니다.|
|[CMonthCalCtrl:: IsYearView](#isyearview)|현재 monthcalendar 컨트롤의 현재 뷰가 연도 뷰 인지 여부를 나타냅니다.|
|[CMonthCalCtrl:: SetCalendarBorder](#setcalendarborder)|현재 월 달력 컨트롤의 테두리 두께를 설정 합니다.|
|[CMonthCalCtrl:: SetCalendarBorderDefault](#setcalendarborderdefault)|현재 월 달력 컨트롤 테두리의 기본 너비를 설정 합니다.|
|[CMonthCalCtrl:: SetCalID](#setcalid)|현재 month calendar 컨트롤의 달력 식별자를 설정 합니다.|
|[CMonthCalCtrl:: SetCenturyView](#setcenturyview)|세기 보기를 표시 하도록 현재 월 달력 컨트롤을 설정 합니다.|
|[CMonthCalCtrl:: SetColor](#setcolor)|Month calendar 컨트롤의 지정 된 영역 색을 설정 합니다.|
|[CMonthCalCtrl:: SetCurrentView](#setcurrentview)|지정 된 뷰를 표시 하도록 현재 월 달력 컨트롤을 설정 합니다.|
|[CMonthCalCtrl:: SetCurSel](#setcursel)|Monthcalendar 컨트롤에 현재 선택한 날짜를 설정 합니다.|
|[CMonthCalCtrl:: SetDayState](#setdaystate)|Monthcalendar 컨트롤의 일에 대 한 표시를 설정 합니다.|
|[CMonthCalCtrl:: SetDecadeView](#setdecadeview)|현재 월 달력 컨트롤을 10 년 뷰로 설정 합니다.|
|[CMonthCalCtrl:: SetFirstDayOfWeek](#setfirstdayofweek)|달력의 가장 왼쪽 열에 표시할 요일을 설정 합니다.|
|[CMonthCalCtrl:: SetMaxSelCount](#setmaxselcount)|Monthcalendar 컨트롤에서 선택할 수 있는 최대 일 수를 설정 합니다.|
|[CMonthCalCtrl:: SetMonthDelta](#setmonthdelta)|Monthcalendar 컨트롤에 대 한 스크롤 빈도를 설정 합니다.|
|[CMonthCalCtrl:: SetMonthView](#setmonthview)|월 보기를 표시 하도록 현재 월 달력 컨트롤을 설정 합니다.|
|[CMonthCalCtrl:: SetRange](#setrange)|Monthcalendar 컨트롤에 대해 허용 되는 최소 및 최대 날짜를 설정 합니다.|
|[CMonthCalCtrl:: SetSelRange](#setselrange)|Month calendar 컨트롤의 선택 항목을 지정 된 날짜 범위로 설정 합니다.|
|[CMonthCalCtrl:: SetToday](#settoday)|현재 날짜에 대 한 달력 컨트롤을 설정 합니다.|
|[CMonthCalCtrl:: SetYearView](#setyearview)|현재 월 달력 컨트롤을 연도 뷰로 설정 합니다.|
|[CMonthCalCtrl:: SizeMinReq](#sizeminreq)|Month calendar 컨트롤을 최소 1 개월 크기로 다시 그립니다.|
|[CMonthCalCtrl:: SizeRectToMin](#sizerecttomin)|현재 month calendar 컨트롤의 경우 지정 된 사각형에 맞는 모든 달력을 포함할 수 있는 가장 작은 사각형을 계산 합니다.|

## <a name="remarks"></a>설명

Month calendar 컨트롤은 사용자가 날짜를 선택할 수 있는 간단한 달력 인터페이스를 사용자에 게 제공 합니다. 사용자는 다음을 수행 하 여 표시를 변경할 수 있습니다.

- 월부터 매월 앞뒤로 스크롤합니다.

- 오늘 텍스트를 클릭 하 여 현재 날짜를 표시 합니다 (MCS_NOTODAY 스타일이 사용 되지 않는 경우).

- 팝업 메뉴에서 월 또는 연도를 선택 합니다.

개체를 만들 때 다양 한 스타일을 개체에 적용 하 여 month calendar 컨트롤을 사용자 지정할 수 있습니다. 이러한 스타일은 Windows SDK의 [Month Calendar 컨트롤 스타일](/windows/win32/Controls/month-calendar-control-styles) 에 설명 되어 있습니다.

Month calendar 컨트롤은 한 달 이상 표시 될 수 있으며 날짜를 굵게 표시 하 여 특별 한 일 (예: 휴일)을 나타낼 수 있습니다.

Month calendar 컨트롤 사용에 대 한 자세한 내용은 [CMonthCalCtrl 사용](../../mfc/using-cmonthcalctrl.md)을 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[에서 파생되지 않은](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxdtctl

##  <a name="cmonthcalctrl"></a>CMonthCalCtrl:: CMonthCalCtrl

`CMonthCalCtrl` 개체를 생성합니다.

```
CMonthCalCtrl();
```

### <a name="remarks"></a>설명

개체를 생성 한 후 `Create`를 호출 해야 합니다.

##  <a name="create"></a>CMonthCalCtrl:: Create

Month calendar 컨트롤을 만들어 `CMonthCalCtrl` 개체에 연결 합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(
    DWORD dwStyle,
    const POINT& pt,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
Month calendar 컨트롤에 적용 되는 Windows 스타일의 조합을 지정 합니다. 스타일에 대 한 자세한 내용은 Windows SDK의 [Month Calendar 컨트롤 스타일](/windows/win32/Controls/month-calendar-control-styles) 을 참조 하세요.

*rect*<br/>
[RECT](/previous-versions/dd162897\(v=vs.85\)) 구조체에 대 한 참조입니다. Month calendar 컨트롤의 위치와 크기를 포함 합니다.

*pt*<br/>
Month calendar 컨트롤의 위치를 식별 하는 [요소](/previous-versions/dd162805\(v=vs.85\)) 구조체에 대 한 참조입니다.

*pParentWnd*<br/>
Month calendar 컨트롤의 부모 창인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대 한 포인터입니다. NULL이 아니어야 합니다.

*nID*<br/>
Monthcalendar 컨트롤의 컨트롤 ID를 지정 합니다.

### <a name="return-value"></a>Return Value

초기화에 성공 하면 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 단계로 month calendar 컨트롤을 만듭니다.

1. [Cmonthcalctrl](../../mfc/reference/cmonthcalctrl-class.md) 을 호출 하 여 `CMonthCalCtrl` 개체를 생성 합니다.

1. 이 멤버 함수를 호출 합니다 .이 함수는 month calendar 컨트롤을 만들고이를 `CMonthCalCtrl` 개체에 연결 합니다.

`Create`를 호출 하면 공용 컨트롤이 초기화 됩니다. 호출 하는 `Create` 버전에 따라 크기가 결정 됩니다.

- MFC에서 컨트롤의 크기를 한 달로 자동으로 조정 하도록 하려면 *pt* 매개 변수를 사용 하는 재정의를 호출 합니다.

- 컨트롤의 크기를 조정 하려면 *rect* 매개 변수를 사용 하는이 함수의 재정의를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

##  <a name="getcalendarborder"></a>CMonthCalCtrl:: GetCalendarBorder

현재 month calendar 컨트롤의 테두리 너비를 검색 합니다.

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>Return Value

컨트롤 테두리의 너비 (픽셀)입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에서 설명 하는 [MCM_GETCALENDARBORDER](/windows/win32/Controls/mcm-getcalendarborder) 메시지를 보냅니다.

##  <a name="getcalendarcount"></a>CMonthCalCtrl:: GetCalendarCount

현재 월 달력 컨트롤에 표시 되는 달력 수를 검색 합니다.

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>Return Value

Month calendar 컨트롤에 현재 표시 된 달력의 수입니다. 허용 되는 최대 달력 수는 12입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에서 설명 하는 [MCM_GETCALENDARCOUNT](/windows/win32/Controls/mcm-getcalendarcount) 메시지를 보냅니다.

##  <a name="getcalendargridinfo"></a>CMonthCalCtrl:: GetCalendarGridInfo

현재 monthcalendar 컨트롤에 대 한 정보를 검색 합니다.

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pmcGridInfo*|제한이 현재 month calendar 컨트롤에 대 한 정보를 수신 하는 [Mcgridinfo](/windows/win32/api/commctrl/ns-commctrl-mcgridinfo) 구조체에 대 한 포인터입니다. 호출자는이 구조체를 할당 하 고 초기화 해야 합니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공 하면 TRUE이 고, 그렇지 않으면입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에서 설명 하는 [MCM_GETCALENDARGRIDINFO](/windows/win32/Controls/mcm-getcalendargridinfo) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 month calendar 컨트롤에 프로그래밍 방식으로 액세스 하는 데 사용 되는 변수 `m_monthCalCtrl`를 정의 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 `GetCalendarGridInfo` 메서드를 사용 하 여 현재 month calendar 컨트롤이 표시 하는 달력 날짜를 검색 합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

##  <a name="getcalid"></a>CMonthCalCtrl:: GetCalID

현재 monthcalendar 컨트롤의 달력 식별자를 검색 합니다.

```
CALID GetCalID() const;
```

### <a name="return-value"></a>Return Value

[달력 식별자](/windows/win32/Intl/calendar-identifiers) 상수 중 하나입니다.

### <a name="remarks"></a>설명

달력 식별자는 양력 (지역화 된), 일본어 또는 회교식 달력과 같은 지역별 달력을 나타냅니다. 응용 프로그램은 다양 한 언어 지원 기능이 있는 달력 식별자를 사용할 수 있습니다.

이 메서드는 Windows SDK에서 설명 하는 [MCM_GETCALID](/windows/win32/Controls/mcm-getcalid) 메시지를 보냅니다.

##  <a name="getcolor"></a>CMonthCalCtrl:: GetColor

*Nregion*으로 지정 된 month calendar 컨트롤 영역의 색을 검색 합니다.

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>매개 변수

*nRegion*<br/>
색을 검색할 month calendar 컨트롤의 지역입니다. 값 목록은 [Setcolor](#setcolor)의 *nregion* 매개 변수를 참조 하세요.

### <a name="return-value"></a>Return Value

성공 하면 month calendar 컨트롤의 부분과 관련 된 색을 지정 하는 [Colorref](/windows/win32/gdi/colorref) 값입니다. 그렇지 않으면이 멤버 함수는-1을 반환 합니다.

##  <a name="getcurrentview"></a>CMonthCalCtrl:: GetCurrentView

현재 monthcalendar 컨트롤에서 현재 표시 하는 뷰를 검색 합니다.

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>Return Value

현재 뷰로, 다음 값 중 하나로 표시 됩니다.

|값|의미|
|-----------|-------------|
|MCMV_MONTH|월별 보기|
|MCMV_YEAR|연간 보기|
|MCMV_DECADE|10 년 보기|
|MCMV_CENTURY|세기 보기|

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에서 설명 하는 [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 month calendar 컨트롤에 프로그래밍 방식으로 액세스 하는 데 사용 되는 변수 `m_monthCalCtrl`를 정의 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 현재 표시 된 month calendar 컨트롤의 보기를 보고 합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

##  <a name="getcursel"></a>CMonthCalCtrl:: GetCurSel

현재 선택 된 날짜로 표시 되는 시스템 시간을 검색 합니다.

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대 한 참조입니다. 현재 시간을 받습니다.

*pDateTime*<br/>
현재 선택 된 날짜 정보를 수신 하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조체에 대 한 포인터입니다. 이 매개 변수는 유효한 주소 여야 하며 NULL 일 수 없습니다.

### <a name="return-value"></a>Return Value

성공 하면 0이 아닌 값 otherwize 0.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_GETCURSEL](/windows/win32/Controls/mcm-getcursel)의 동작을 구현 합니다.

> [!NOTE]
>  이 멤버 함수는 스타일 MCS_MULTISELECT 설정 된 경우 실패 합니다.

MFC의 `GetCurSel`구현에서는 `COleDateTime` 사용, `CTime` 사용 또는 `SYSTEMTIME` 구조 사용을 지정할 수 있습니다.

##  <a name="getfirstdayofweek"></a>CMonthCalCtrl:: GetFirstDayOfWeek

달력의 가장 왼쪽 열에 표시 되는 첫째 요일을 가져옵니다.

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>매개 변수

*Plocal*<br/>
부울 값에 대 한 포인터입니다. 값이 0이 아닌 경우 컨트롤의 설정이 제어판의 설정과 일치 하지 않습니다.

### <a name="return-value"></a>Return Value

주의 첫째 요일을 나타내는 정수 값입니다. 이러한 정수가 나타내는 내용에 대 한 자세한 내용은 **설명 부분** 을 참조 하십시오.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_GETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-getfirstdayofweek)의 동작을 구현 합니다. 요일은 다음과 같이 정수로 표시 됩니다.

|값|요일|
|-----------|---------------------|
|0|월요일|
|1|화요일|
|2|수요일|
|3|목요일|
|4|금요일|
|5|토요일|
|6|일요일|

### <a name="example"></a>예제

  [Cmonthcalctrl:: SetFirstDayOfWeek](#setfirstdayofweek)의 예제를 참조 하세요.

##  <a name="getmaxselcount"></a>CMonthCalCtrl:: GetMaxSelCount

Month calendar 컨트롤에서 선택할 수 있는 현재 최대 일 수를 검색 합니다.

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>Return Value

컨트롤에 대해 선택할 수 있는 총 일 수를 나타내는 정수 값입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_GETMAXSELCOUNT](/windows/win32/Controls/mcm-getmaxselcount)의 동작을 구현 합니다. MCS_MULTISELECT 스타일이 설정 된 컨트롤에 대해이 멤버 함수를 사용 합니다.

### <a name="example"></a>예제

  [Cmonthcalctrl:: SetMaxSelCount](#setmaxselcount)의 예제를 참조 하세요.

##  <a name="getmaxtodaywidth"></a>CMonthCalCtrl:: GetMaxTodayWidth

현재 month calendar 컨트롤에 대 한 "Today" 문자열의 최대 너비를 검색 합니다.

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>Return Value

"오늘" 문자열의 너비 (픽셀)입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 month calendar 컨트롤에 프로그래밍 방식으로 액세스 하는 데 사용 되는 변수 `m_monthCalCtrl`를 정의 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제는 `GetMaxTodayWidth` 메서드.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>설명

사용자는 month calendar 컨트롤의 맨 아래에 표시 되는 "오늘" 문자열을 클릭 하 여 현재 날짜로 돌아갈 수 있습니다. "Today" 문자열은 레이블 텍스트 및 날짜 텍스트를 포함 합니다.

이 메서드는 Windows SDK에서 설명 하는 [MCM_GETMAXTODAYWIDTH](/windows/win32/Controls/mcm-getmaxtodaywidth) 메시지를 보냅니다.

##  <a name="getminreqrect"></a>CMonthCalCtrl:: GetMinReqRect

Month calendar 컨트롤에서 전체 월을 표시 하는 데 필요한 최소 크기를 검색 합니다.

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>매개 변수

*pRect*<br/>
경계 사각형 정보를 수신 하는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조체에 대 한 포인터입니다. 이 매개 변수는 유효한 주소 여야 하며 NULL 일 수 없습니다.

### <a name="return-value"></a>Return Value

성공 하면이 멤버 함수는 0이 아닌 값을 반환 하 고 `lpRect`는 적용 가능한 경계 정보를 받습니다. 실패 하면 멤버 함수는 0을 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_GETMINREQRECT](/windows/win32/Controls/mcm-getminreqrect)의 동작을 구현 합니다.

##  <a name="getmonthdelta"></a>CMonthCalCtrl:: GetMonthDelta

Monthcalendar 컨트롤의 스크롤 주기를 검색 합니다.

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>Return Value

Month calendar 컨트롤의 스크롤 빈도입니다. 스크롤 비율은 사용자가 스크롤 단추를 한 번 클릭 하면 컨트롤이 표시를 이동 하는 월 수입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_GETMONTHDELTA](/windows/win32/Controls/mcm-getmonthdelta)의 동작을 구현 합니다.

##  <a name="getmonthrange"></a>CMonthCalCtrl:: GetMonthRange

Monthcalendar 컨트롤 표시의 상한 및 하 한을 나타내는 날짜 정보를 검색 합니다.

```
int GetMonthRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    CTime& refMinRange,
    CTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange,
    DWORD dwFlags) const;
```

### <a name="parameters"></a>매개 변수

*refMinRange*<br/>
허용 되는 최소 날짜를 포함 하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대 한 참조입니다.

*refMaxRange*<br/>
허용 되는 최대 날짜를 포함 하는 `COleDateTime` 또는 `CTime` 개체에 대 한 참조입니다.

*pMinRange*<br/>
범위의 최하위 끝에 있는 날짜를 포함 하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조체에 대 한 포인터입니다.

*pMaxRange*<br/>
범위의 최고 끝에 있는 날짜를 포함 하는 `SYSTEMTIME` 구조체에 대 한 포인터입니다.

*dwFlags*<br/>
검색할 범위 제한의 범위를 지정 하는 값입니다. 이 값은 다음 중 하나 여야 합니다.

|값|의미|
|-----------|-------------|
|GMR_DAYSTATE|부분적 으로만 표시 되는 표시 된 범위의 선행 및 후행 월을 포함 합니다.|
|GMR_VISIBLE|완전히 표시 되는 월만 포함 합니다.|

### <a name="return-value"></a>Return Value

첫 번째 및 두 번째 버전에서 *refMinRange* 및 *refMaxRange* 로 표시 되는 두 제한에 따라 범위를 지정 하는 정수 이며 세 번째 버전의 *pMinRange* 및 *pMaxRange* 입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_GETMONTHRANGE](/windows/win32/Controls/mcm-getmonthrange)의 동작을 구현 합니다. MFC의 `GetMonthRange`구현에서는 `COleDateTime` 사용, `CTime` 사용 또는 `SYSTEMTIME` 구조 사용을 지정할 수 있습니다.

### <a name="example"></a>예제

  [Cmonthcalctrl:: SetDayState](#setdaystate)의 예제를 참조 하세요.

##  <a name="getrange"></a>CMonthCalCtrl:: GetRange

Month calendar 컨트롤에서 설정 된 현재 최소 및 최대 날짜를 검색 합니다.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;

DWORD GetRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>매개 변수

*pMinRange*<br/>
범위에서 가장 낮은 끝의 날짜를 포함 하는 `COleDateTime` 개체, `CTime` 개체 또는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조체에 대 한 포인터입니다.

*pMaxRange*<br/>
범위의 최고 끝에 있는 날짜를 포함 하는 `COleDateTime` 개체, `CTime` 개체 또는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조체에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

0 (제한이 설정 되지 않음) 이거나 제한 정보를 지정 하는 다음 값의 조합일 수 있는 DWORD입니다.

|값|의미|
|-----------|-------------|
|GDTR_MAX|컨트롤에 대해 최대 한도가 설정 됩니다. *pMaxRange* 는 유효 하며 해당 날짜 정보를 포함 합니다.|
|GDTR_MIN|컨트롤에 대해 최소 제한이 설정 됩니다. *pMinRange* 는 유효 하며 해당 날짜 정보를 포함 합니다.|

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_GETRANGE](/windows/win32/Controls/mcm-getrange)의 동작을 구현 합니다. MFC의 `GetRange`구현에서는 `COleDateTime` 사용, `CTime` 사용 또는 `SYSTEMTIME` 구조 사용을 지정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

##  <a name="getselrange"></a>CMonthCalCtrl:: GetSelRange

사용자가 현재 선택한 날짜 범위의 상한 및 하 한을 나타내는 날짜 정보를 검색 합니다.

```
BOOL GetSelRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange) const;

BOOL GetSelRange(
    CTime& refMinRange,
    CTime& refMaxRange) const;

BOOL GetSelRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>매개 변수

*refMinRange*<br/>
허용 되는 최소 날짜를 포함 하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대 한 참조입니다.

*refMaxRange*<br/>
허용 되는 최대 날짜를 포함 하는 `COleDateTime` 또는 `CTime` 개체에 대 한 참조입니다.

*pMinRange*<br/>
범위의 최하위 끝에 있는 날짜를 포함 하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조체에 대 한 포인터입니다.

*pMaxRange*<br/>
범위의 최고 끝에 있는 날짜를 포함 하는 `SYSTEMTIME` 구조체에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_GETSELRANGE](/windows/win32/Controls/mcm-getselrange)의 동작을 구현 합니다. MCS_MULTISELECT 스타일을 사용 하지 않는 month calendar 컨트롤에 적용 되는 `GetSelRange`는 실패 합니다.

MFC의 `GetSelRange`구현에서는 `COleDateTime` 사용, `CTime` 사용 또는 `SYSTEMTIME` 구조 사용을 지정할 수 있습니다.

##  <a name="gettoday"></a>CMonthCalCtrl:: GetToday

Monthcalendar 컨트롤에 대해 "오늘"로 지정 된 날짜에 대 한 날짜 정보를 검색 합니다.

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
현재 날짜를 나타내는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대 한 참조입니다.

*pDateTime*<br/>
날짜 정보를 수신 하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조체에 대 한 포인터입니다. 이 매개 변수는 유효한 주소 여야 하며 NULL 일 수 없습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_GETTODAY](/windows/win32/Controls/mcm-gettoday)의 동작을 구현 합니다. MFC의 `GetToday`구현에서는 `COleDateTime` 사용, `CTime` 사용 또는 `SYSTEMTIME` 구조 사용을 지정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

##  <a name="hittest"></a>CMonthCalCtrl:: System.windows.media.visualtreehelper.hittest

지정 된 위치에 있는 월 달력 컨트롤 (있는 경우)을 결정 합니다.

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>매개 변수

*pMCHitTest*<br/>
Month calendar 컨트롤의 적중 테스트 지점이 포함 된 [Mchittestinfo](/windows/win32/api/commctrl/ns-commctrl-mchittestinfo) 구조에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

DWORD 값입니다. `MCHITTESTINFO` 구조체의 **Uhit** 멤버와 동일 합니다.

### <a name="remarks"></a>설명

`HitTest`는 적중 테스트에 대 한 정보를 포함 하는 `MCHITTESTINFO` 구조체를 사용 합니다.

##  <a name="iscenturyview"></a>CMonthCalCtrl:: IsCenturyView

현재 monthcalendar 컨트롤의 현재 보기가 세기 뷰 인지 여부를 나타냅니다.

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>Return Value

현재 보기가 세기 뷰 이면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에서 설명 하는 [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) 메시지를 보냅니다. 해당 메시지가 MCMV_CENTURY을 반환 하는 경우이 메서드는 TRUE를 반환 합니다.

##  <a name="isdecadeview"></a>CMonthCalCtrl:: IsDecadeView

현재 월 달력 컨트롤의 현재 뷰가 10 월 뷰입니다 여부를 나타냅니다.

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>Return Value

현재 뷰가 10 년 뷰입니다 경우 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에서 설명 하는 [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) 메시지를 보냅니다. 해당 메시지가 MCMV_DECADE을 반환 하는 경우이 메서드는 TRUE를 반환 합니다.

##  <a name="ismonthview"></a>CMonthCalCtrl:: IsMonthView

현재 월 달력 컨트롤의 현재 뷰가 월 보기 인지 여부를 나타냅니다.

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>Return Value

현재 보기가 월 보기 이면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에서 설명 하는 [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) 메시지를 보냅니다. 해당 메시지가 MCMV_MONTH을 반환 하는 경우이 메서드는 TRUE를 반환 합니다.

##  <a name="isyearview"></a>CMonthCalCtrl:: IsYearView

현재 monthcalendar 컨트롤의 현재 뷰가 연도 뷰 인지 여부를 나타냅니다.

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>Return Value

현재 뷰가 연도 보기 이면 TRUE이 고, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에서 설명 하는 [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) 메시지를 보냅니다. 해당 메시지가 MCMV_YEAR을 반환 하는 경우이 메서드는 TRUE를 반환 합니다.

##  <a name="setcalendarborder"></a>CMonthCalCtrl:: SetCalendarBorder

현재 월 달력 컨트롤의 테두리 두께를 설정 합니다.

```
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*cxyBorder*|진행 테두리의 너비 (픽셀)입니다.|

### <a name="remarks"></a>설명

이 메서드가 성공 하면 테두리 너비가 *cxyBorder* 매개 변수로 설정 됩니다. 그렇지 않으면 테두리 너비가 현재 [테마](/windows/win32/Controls/visual-styles-overview)에 지정 된 기본값으로 다시 설정 되 고 테마가 사용 되지 않는 경우에는 0으로 다시 설정 됩니다.

이 메서드는 Windows SDK에서 설명 하는 [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 month calendar 컨트롤에 프로그래밍 방식으로 액세스 하는 데 사용 되는 변수 `m_monthCalCtrl`를 정의 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 month calendar 컨트롤의 테두리 너비를 8 픽셀로 설정 합니다. [Cmonthcalctrl:: GetCalendarBorder](#getcalendarborder) 메서드를 사용 하 여이 메서드가 성공 했는지 여부를 확인 합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

##  <a name="setcalendarborderdefault"></a>CMonthCalCtrl:: SetCalendarBorderDefault

현재 월 달력 컨트롤 테두리의 기본 너비를 설정 합니다.

```
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>설명

테두리 너비는 현재 [테마](/windows/win32/Controls/visual-styles-overview)에서 지정 된 기본값으로 설정 됩니다. 또는 테마가 사용 되지 않는 경우 0입니다.

이 메서드는 Windows SDK에서 설명 하는 [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) 메시지를 보냅니다.

##  <a name="setcalid"></a>CMonthCalCtrl:: SetCalID

현재 month calendar 컨트롤의 달력 식별자를 설정 합니다.

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*calid*|진행 [달력 식별자](/windows/win32/Intl/calendar-identifiers) 상수 중 하나입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공 하면 TRUE이 고, 그렇지 않으면입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

달력 식별자는 양력 (지역화 된), 일본어 또는 회교식 달력과 같은 지역별 달력을 지정 합니다. 달력을 포함 하는 로캘이 컴퓨터에 설치 된 경우에는 `SetCalID` 메서드를 사용 하 여 *calid* 매개 변수로 지정 된 달력을 표시할 수 있습니다.

이 메서드는 Windows SDK에서 설명 하는 [MCM_SETCALID](/windows/win32/Controls/mcm-setcalid) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 month calendar 컨트롤에 프로그래밍 방식으로 액세스 하는 데 사용 되는 변수 `m_monthCalCtrl`를 정의 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 월 달력 컨트롤을 설정 하 여 일본 황제 달력을 표시 합니다. `SetCalID` 메서드는 해당 달력이 컴퓨터에 설치 되어 있는 경우에만 성공 합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

##  <a name="setcenturyview"></a>CMonthCalCtrl:: SetCenturyView

세기 보기를 표시 하도록 현재 월 달력 컨트롤을 설정 합니다.

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>Return Value

이 메서드가 성공 하면 TRUE이 고, 그렇지 않으면입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 [Cmonthcalctrl:: SetCurrentView](#setcurrentview) 메서드를 사용 하 여 뷰를 세기 뷰를 나타내는 `MCMV_CENTURY`로 설정 합니다.

##  <a name="setcolor"></a>CMonthCalCtrl:: SetColor

Month calendar 컨트롤의 지정 된 영역 색을 설정 합니다.

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>매개 변수

*nRegion*<br/>
설정할 월 달력 색을 지정 하는 정수 값입니다. 이 값은 다음 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|MCSC_BACKGROUND|월 사이에 표시 되는 배경색입니다.|
|MCSC_MONTHBK|월 내에 표시 되는 배경색입니다.|
|MCSC_TEXT|한 달 내에 텍스트를 표시 하는 데 사용 되는 색입니다.|
|MCSC_TITLEBK|달력의 제목에 표시 되는 배경색입니다.|
|MCSC_TITLETEXT|달력의 제목 내에 텍스트를 표시 하는 데 사용 되는 색입니다.|
|MCSC_TRAILINGTEXT|머리글 및 후행 일 텍스트를 표시 하는 데 사용 되는 색입니다. 머리글과 후행 일은 현재 달력에 표시 되는 이전 및 다음 달의 날짜입니다.|

*ref*<br/>
Month calendar 컨트롤의 지정 된 부분에 대 한 새 색 설정의 COLORREF 값입니다.

### <a name="return-value"></a>Return Value

성공 하면 month calendar 컨트롤의 지정 된 부분에 대 한 이전 색 설정을 나타내는 COLORREF 값입니다. 그렇지 않으면이 메시지는-1을 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_SETCOLOR](/windows/win32/Controls/mcm-setcolor)의 동작을 구현 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

##  <a name="setcurrentview"></a>CMonthCalCtrl:: SetCurrentView

지정 된 뷰를 표시 하도록 현재 월 달력 컨트롤을 설정 합니다.

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*dwNewView*|진행 월별, 연간, 10 또는 세기 뷰를 지정 하는 다음 값 중 하나입니다.<br /><br /> MCMV_MONTH: 월별 보기<br /><br /> MCMV_YEAR: 연간 보기<br /><br /> MCMV_DECADE: 10 년 뷰<br /><br /> MCMV_CENTURY: 세기 뷰|

### <a name="return-value"></a>Return Value

이 메서드가 성공 하면 TRUE이 고, 그렇지 않으면입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에서 설명 하는 [MCM_SETCURRENTVIEW](/windows/win32/Controls/mcm-setcurrentview) 메시지를 보냅니다.

##  <a name="setcursel"></a>CMonthCalCtrl:: SetCurSel

Monthcalendar 컨트롤에 현재 선택한 날짜를 설정 합니다.

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
현재 선택 된 month calendar 컨트롤을 나타내는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대 한 참조입니다.

*pDateTime*<br/>
현재 선택 항목으로 설정할 날짜를 포함 하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조체에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_SETCURSEL](/windows/win32/Controls/mcm-setcursel)의 동작을 구현 합니다. MFC의 `SetCurSel`구현에서는 `COleDateTime` 사용, `CTime` 사용 또는 `SYSTEMTIME` 구조 사용을 지정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

##  <a name="setdaystate"></a>CMonthCalCtrl:: SetDayState

Monthcalendar 컨트롤의 일에 대 한 표시를 설정 합니다.

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>매개 변수

*nMonths*<br/>
*Pstates* 가 가리키는 배열에 있는 요소 수를 나타내는 값입니다.

*pStates*<br/>
Monthcalendar 컨트롤에서 각 날짜를 표시 하는 방법을 정의 하는 값의 [Monthdaystate](/windows/win32/Controls/monthdaystate) 배열에 대 한 포인터입니다. MONTHDAYSTATE 데이터 형식은 비트 필드입니다. 여기서 각 비트 (1-31)는 한 달의 일 상태를 나타냅니다. 비트가 켜져 있으면 해당 날짜가 굵게 표시 됩니다. 그렇지 않으면 강조 표시 되지 않고 표시 됩니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_SETDAYSTATE](/windows/win32/Controls/mcm-setdaystate)의 동작을 구현 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

##  <a name="setdecadeview"></a>CMonthCalCtrl:: SetDecadeView

현재 월 달력 컨트롤을 10 년 뷰로 설정 합니다.

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>Return Value

이 메서드가 성공 하면 TRUE이 고, 그렇지 않으면입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 [Cmonthcalctrl:: SetCurrentView](#setcurrentview) 메서드를 사용 하 여 뷰를 10 년 뷰를 나타내는 `MCMV_DECADE`로 설정 합니다.

##  <a name="setfirstdayofweek"></a>CMonthCalCtrl:: SetFirstDayOfWeek

달력의 가장 왼쪽 열에 표시할 요일을 설정 합니다.

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>매개 변수

*iDay*<br/>
요일을 1 일로 설정 해야 하는 날짜를 나타내는 정수 값입니다. 이 값은 일 번호 중 하나 여야 합니다. [GetFirstDayOfWeek](#getfirstdayofweek) 를 참조 하십시오.

*lpnOld*<br/>
이전에 설정한 주의 첫째 요일을 나타내는 정수에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

이 값이 0이 아닌 값으로 설정 된 경우에는 0이 아닌 값으로 설정 되 고,이 값은 제어판 설정에 표시 되는 일 LOCALE_IFIRSTDAYOFWEEK입니다. 그렇지 않으면이 함수는 0을 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_SETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-setfirstdayofweek)의 동작을 구현 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

##  <a name="setmaxselcount"></a>CMonthCalCtrl:: SetMaxSelCount

Monthcalendar 컨트롤에서 선택할 수 있는 최대 일 수를 설정 합니다.

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>매개 변수

*nMax*<br/>
선택할 수 있는 최대 날짜 수를 나타내도록 설정 되는 값입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_SETMAXSELCOUNT](/windows/win32/Controls/mcm-setmaxselcount)의 동작을 구현 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

##  <a name="setmonthdelta"></a>CMonthCalCtrl:: SetMonthDelta

Monthcalendar 컨트롤에 대 한 스크롤 빈도를 설정 합니다.

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>매개 변수

*iDelta*<br/>
컨트롤의 스크롤 비율로 설정할 월 수입니다. 이 값이 0 이면 월 델타는 컨트롤에 표시 되는 월 수 인 기본값으로 다시 설정 됩니다.

### <a name="return-value"></a>Return Value

이전 스크롤 율입니다. 스크롤 비율이 이전에 설정 되지 않은 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_SETMONTHDELTA](/windows/win32/Controls/mcm-setmonthdelta)의 동작을 구현 합니다.

##  <a name="setmonthview"></a>CMonthCalCtrl:: SetMonthView

월 보기를 표시 하도록 현재 월 달력 컨트롤을 설정 합니다.

```
BOOL SetMonthView();
```

### <a name="return-value"></a>Return Value

이 메서드가 성공 하면 TRUE이 고, 그렇지 않으면입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 [Cmonthcalctrl:: SetCurrentView](#setcurrentview) 메서드를 사용 하 여 뷰를 월 보기를 나타내는 MCMV_MONTH로 설정 합니다.

### <a name="example"></a>예제

다음 코드 예제에서는 month calendar 컨트롤에 프로그래밍 방식으로 액세스 하는 데 사용 되는 변수 `m_monthCalCtrl`를 정의 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예에서는 month 달력 컨트롤을 설정 하 여 월, 연도, 10 년 및 세기 뷰를 표시 합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

##  <a name="setrange"></a>CMonthCalCtrl:: SetRange

Monthcalendar 컨트롤에 허용 되는 최소 및 최대 날짜를 설정 합니다.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);

BOOL SetRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>매개 변수

*pMinRange*<br/>
범위에서 가장 낮은 끝의 날짜를 포함 하는 `COleDateTime` 개체, `CTime` 개체 또는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조체에 대 한 포인터입니다.

*pMaxRange*<br/>
범위의 최고 끝에 있는 날짜를 포함 하는 `COleDateTime` 개체, `CTime` 개체 또는 `SYSTEMTIME` 구조체에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_SETRANGE](/windows/win32/Controls/mcm-setrange)의 동작을 구현 합니다. MFC의 `SetRange`구현에서는 `COleDateTime` 사용, `CTime` 사용 또는 `SYSTEMTIME` 구조 사용을 지정할 수 있습니다.

### <a name="example"></a>예제

  [Cmonthcalctrl:: GetRange](#getrange)의 예제를 참조 하세요.

##  <a name="setselrange"></a>CMonthCalCtrl:: SetSelRange

Month calendar 컨트롤의 선택 항목을 지정 된 날짜 범위로 설정 합니다.

```
BOOL SetSelRange(
    const COleDateTime& pMinRange,
    const COleDateTime& pMaxRange);

BOOL SetSelRange(
    const CTime& pMinRange,
    const CTime& pMaxRange);

BOOL SetSelRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>매개 변수

*pMinRange*<br/>
범위에서 가장 낮은 끝의 날짜를 포함 하는 `COleDateTime` 개체, `CTime` 개체 또는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조체에 대 한 포인터입니다.

*pMaxRange*<br/>
범위의 최고 끝에 있는 날짜를 포함 하는 `COleDateTime` 개체, `CTime` 개체 또는 `SYSTEMTIME` 구조체에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_SETSELRANGE](/windows/win32/Controls/mcm-setselrange)의 동작을 구현 합니다. MFC의 `SetSelRange`구현에서는 `COleDateTime` 사용, `CTime` 사용 또는 `SYSTEMTIME` 구조 사용을 지정할 수 있습니다.

##  <a name="settoday"></a>CMonthCalCtrl:: SetToday

현재 날짜에 대 한 달력 컨트롤을 설정 합니다.

```
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
현재 날짜를 포함 하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체에 대 한 참조입니다.

*pDateTime*<br/>
두 번째 버전에서 현재 날짜 정보를 포함 하는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대 한 포인터입니다. 세 번째 버전에서 현재 날짜 정보를 포함 하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 Win32 메시지 [MCM_SETTODAY](/windows/win32/Controls/mcm-settoday)의 동작을 구현 합니다.

### <a name="example"></a>예제

  [Cmonthcalctrl:: GetToday](#gettoday)의 예제를 참조 하세요.

##  <a name="setyearview"></a>CMonthCalCtrl:: SetYearView

현재 월 달력 컨트롤을 연도 뷰로 설정 합니다.

```
BOOL SetYearView();
```

### <a name="return-value"></a>Return Value

이 메서드가 성공 하면 TRUE이 고, 그렇지 않으면입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 [Cmonthcalctrl:: SetCurrentView](#setcurrentview) 메서드를 사용 하 여 뷰를 연간 뷰를 나타내는 MCMV_YEAR로 설정 합니다.

##  <a name="sizeminreq"></a>CMonthCalCtrl:: SizeMinReq

월 달력 컨트롤을 한 달에 표시 되는 최소 크기로 표시 합니다.

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>매개 변수

*bRepaint*<br/>
컨트롤을 다시 그릴지 여부를 지정 합니다. 기본적으로 TRUE입니다. FALSE 이면 다시 그려야 합니다.

### <a name="return-value"></a>Return Value

Month calendar 컨트롤의 크기가 최소로 조정 되 면 0이 아닌 값으로 조정 됩니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`SizeMinReq`를 호출 하면 한 달의 달력에 대 한 전체 월 달력 컨트롤이 표시 됩니다.

##  <a name="sizerecttomin"></a>CMonthCalCtrl:: SizeRectToMin

현재 month calendar 컨트롤의 경우 지정 된 사각형에 맞는 모든 달력을 포함할 수 있는 가장 작은 사각형을 계산 합니다.

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*lpRect*|진행 원하는 달력 수를 포함 하는 사각형을 정의 하는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조체에 대 한 포인터입니다.|

### <a name="return-value"></a>Return Value

*LpRect* 매개 변수에 의해 정의 된 사각형 보다 작거나 같은 크기의 사각형을 정의 하는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 *lpRect* 매개 변수로 지정 된 사각형에 맞출 수 있는 달력 수를 계산한 다음 해당 수의 달력을 포함할 수 있는 가장 작은 사각형을 반환 합니다. 실제로이 메서드는 지정 된 사각형을 원하는 수의 달력에 정확히 맞게 축소 합니다.

이 메서드는 Windows SDK에서 설명 하는 [MCM_SIZERECTTOMIN](/windows/win32/Controls/mcm-sizerecttomin) 메시지를 보냅니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDateTimeCtrl 클래스](../../mfc/reference/cdatetimectrl-class.md)
