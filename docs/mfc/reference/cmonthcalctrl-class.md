---
title: C월칼Ctrl 클래스
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
ms.openlocfilehash: 8c24c638d7006be112a53ec1e4f622ad528e348c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752825"
---
# <a name="cmonthcalctrl-class"></a>C월칼Ctrl 클래스

달력 컨트롤의 기능을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C월CalCtrl:::C월칼Ctrl](#cmonthcalctrl)|`CMonthCalCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C월CalCtrl::만들기](#create)|월 달력 컨트롤을 만들고 개체에 `CMonthCalCtrl` 연결합니다.|
|[C월CalCtrl::GetCalendarBorder](#getcalendarborder)|현재 월 달력 컨트롤의 테두리 너비를 검색합니다.|
|[C월CalCtrl::GetCalendarCount](#getcalendarcount)|현재 월 달력 컨트롤에 표시되는 달력 수를 검색합니다.|
|[C월CalCtrl::GetCalendar그리드정보](#getcalendargridinfo)|현재 월 달력 컨트롤에 대 한 정보를 검색합니다.|
|[C월칼Ctrl::겟칼리드](#getcalid)|현재 월 달력 컨트롤에 대 한 달력 식별자를 검색 합니다.|
|[C월CalCtrl::GetColor](#getcolor)|월 달력 컨트롤의 지정된 영역의 색상을 가져옵니다.|
|[C월CalCtrl::GetCurrentView](#getcurrentview)|현재 월 달력 컨트롤에 의해 현재 표시 되는 보기를 검색 합니다.|
|[C월CalCtrl::겟커셀](#getcursel)|현재 선택한 날짜에 표시된 대로 시스템 시간을 검색합니다.|
|[C월CalCtrl::GetFirstDayOfweek](#getfirstdayofweek)|달력의 맨 왼쪽 열에 표시할 요일의 첫 날을 가져옵니다.|
|[C월CalCtrl::겟맥스셀카운트](#getmaxselcount)|월 달력 컨트롤에서 선택할 수 있는 현재 최대 일 수를 검색합니다.|
|[C월CalCtrl::겟맥스투데이폭](#getmaxtodaywidth)|현재 월 달력 컨트롤에 대 한 "오늘" 문자열의 최대 너비를 검색합니다.|
|[C월칼렉트: 겟민렉트](#getminreqrect)|월 달력 컨트롤에서 전체 월을 표시하는 데 필요한 최소 크기를 검색합니다.|
|[C월칼Ctrl::겟월델타](#getmonthdelta)|월 캘린더 컨트롤의 스크롤 속도를 검색합니다.|
|[C월CalCtrl::GetMonthRange](#getmonthrange)|월 캘린더 컨트롤의 표시의 높고 낮은 제한을 나타내는 날짜 정보를 검색합니다.|
|[C월CalCtrl::GetRange](#getrange)|월 캘린더 컨트롤에 설정된 현재 최소 날짜와 최대 날짜를 검색합니다.|
|[C월칼Ctrl::겟셀레인지](#getselrange)|사용자가 현재 선택한 날짜 범위의 상한 및 하한을 나타내는 날짜 정보를 검색합니다.|
|[C월칼Ctrl::GetToday](#gettoday)|월 달력 컨트롤에 대해 "오늘"로 지정된 날짜의 날짜 정보를 검색합니다.|
|[C월CalCtrl::히트 테스트](#hittest)|화면의 지정된 지점에 있는 월 캘린더 컨트롤섹션을 결정합니다.|
|[C월칼Ctrl::이센추시뷰](#iscenturyview)|현재 월 달력 컨트롤의 현재 보기가 세기 뷰인지 여부를 나타냅니다.|
|[C월칼Ctrl::이십년뷰](#isdecadeview)|현재 월 달력 컨트롤의 현재 보기가 10년 보기인지 여부를 나타냅니다.|
|[C월CalCtrl::이월보기](#ismonthview)|현재 월 달력 컨트롤의 현재 보기가 월 보기인지 여부를 나타냅니다.|
|[C월칼Ctrl::이스이어뷰](#isyearview)|현재 월 달력 컨트롤의 현재 보기가 연도 보기인지 여부를 나타냅니다.|
|[C월CalCtrl::SetCalendarBorder](#setcalendarborder)|현재 월 달력 컨트롤의 테두리 너비를 설정합니다.|
|[C월CalCtrl::SetCalendarBorder기본](#setcalendarborderdefault)|현재 월 달력 컨트롤의 테두리의 기본 너비를 설정합니다.|
|[C월CalCtrl:::세트칼리드](#setcalid)|현재 월 달력 컨트롤의 달력 식별자를 설정합니다.|
|[C월칼Ctrl::세트센추치뷰](#setcenturyview)|세기 보기를 표시 하도록 현재 월 달력 컨트롤을 설정 합니다.|
|[C월CalCtrl::세트컬러](#setcolor)|월 달력 컨트롤의 지정된 영역의 색상을 설정합니다.|
|[C월CalCtrl::설정현재보기](#setcurrentview)|지정된 뷰를 표시하도록 현재 월 달력 컨트롤을 설정합니다.|
|[C월CalCtrl::세트컬셀](#setcursel)|월 달력 컨트롤에 대해 현재 선택한 날짜를 설정합니다.|
|[C월CalCtrl::SetDaystate](#setdaystate)|월 달력 컨트롤의 일 동안 표시를 설정합니다.|
|[C월CalCtrl::SetDecadeView](#setdecadeview)|현재 월 달력 컨트롤을 10년 보기로 설정합니다.|
|[C월칼Ctrl::셋퍼스트데이오브위크](#setfirstdayofweek)|달력의 가장 왼쪽 열에 표시할 요일을 설정합니다.|
|[C월CalCtrl::세트맥스셀카운트](#setmaxselcount)|월 캘린더 컨트롤에서 선택할 수 있는 최대 일 수를 설정합니다.|
|[C월칼Ctrl::세트월델타](#setmonthdelta)|월 캘린더 컨트롤의 스크롤 속도를 설정합니다.|
|[C월CalCtrl::세트월뷰](#setmonthview)|현재 월 캘린더 컨트롤을 설정하여 월 보기를 표시합니다.|
|[C월CalCtrl::세트레인지](#setrange)|월 캘린더 컨트롤의 최소 및 최대 허용 날짜를 설정합니다.|
|[C월칼Ctrl::세트셀레인지](#setselrange)|월 캘린더 컨트롤의 선택 항목을 지정된 날짜 범위로 설정합니다.|
|[C월칼Ctrl::세트투데이](#settoday)|현재 날짜의 달력 컨트롤을 설정합니다.|
|[C월CalCtrl::세트이어뷰](#setyearview)|현재 월 달력 컨트롤을 연도 보기로 설정합니다.|
|[C월칼Ctrl::크기민렉](#sizeminreq)|월 캘린더 컨트롤을 최소 1개월 크기로 다시 그립니다.|
|[C월칼트르::사이즈렉토민](#sizerecttomin)|현재 월 달력 컨트롤의 경우 지정된 사각형에 맞는 모든 캘린더를 포함할 수 있는 가장 작은 사각형을 계산합니다.|

## <a name="remarks"></a>설명

월 캘린더 컨트롤은 사용자가 날짜를 선택할 수 있는 간단한 일정 인터페이스를 사용자에게 제공합니다. 사용자는 다음과 같은 각을 통해 디스플레이를 변경할 수 있습니다.

- 월에서 앞뒤로 스크롤합니다.

- 오늘 텍스트를 클릭하여 현재 날짜를 표시합니다(MCS_NOTODAY 스타일이 사용되지 않는 경우).

- 팝업 메뉴에서 한 달 또는 1년을 선택합니다.

객체를 만들 때 다양한 스타일을 적용하여 월 캘린더 컨트롤을 사용자 지정할 수 있습니다. 이러한 스타일은 Windows SDK의 [월 캘린더 제어 스타일에](/windows/win32/Controls/month-calendar-control-styles) 설명되어 있습니다.

월 캘린더 컨트롤은 1개월 이상 표시할 수 있으며 날짜를 굵게 표시하여 특별한 날(예: 공휴일)을 나타낼 수 있습니다.

월 달력 컨트롤 사용에 대한 자세한 내용은 [CMonthCalCtrl 사용을](../../mfc/using-cmonthcalctrl.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxdtctl.h

## <a name="cmonthcalctrlcmonthcalctrl"></a><a name="cmonthcalctrl"></a>C월CalCtrl:::C월칼Ctrl

`CMonthCalCtrl` 개체를 생성합니다.

```
CMonthCalCtrl();
```

### <a name="remarks"></a>설명

개체를 `Create` 생성한 후 호출해야 합니다.

## <a name="cmonthcalctrlcreate"></a><a name="create"></a>C월CalCtrl::만들기

월 달력 컨트롤을 만들고 개체에 `CMonthCalCtrl` 연결합니다.

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
월 달력 컨트롤에 적용된 Windows 스타일의 조합을 지정합니다. 스타일에 대한 자세한 내용은 Windows SDK의 [월 캘린더 제어 스타일을](/windows/win32/Controls/month-calendar-control-styles) 참조하십시오.

*rect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다. 월 달력 컨트롤의 위치와 크기를 포함합니다.

*pt*<br/>
월 달력 컨트롤의 위치를 식별하는 [POINT](/windows/win32/api/windef/ns-windef-point) 구조에 대한 참조입니다.

*pParentWnd*<br/>
월 달력 컨트롤의 부모 창인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터입니다. NULL이 아니어야 합니다.

*nID*<br/>
월 캘린더 컨트롤의 제어 ID를 지정합니다.

### <a name="return-value"></a>Return Value

초기화가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

다음 두 단계로 월 캘린더 컨트롤을 만듭니다.

1. [CMonthCalCtrl을](../../mfc/reference/cmonthcalctrl-class.md) 호출하여 `CMonthCalCtrl` 개체를 생성합니다.

1. 월 달력 컨트롤을 만들고 개체에 연결 하는 이 `CMonthCalCtrl` 멤버 함수를 호출 합니다.

호출하면 `Create`공통 컨트롤이 초기화됩니다. 호출 버전에 `Create` 따라 크기가 결정됩니다.

- MFC가 컨트롤의 크기를 한 달로 자동으로 조정하려면 *pt* 매개 변수를 사용하는 재정의를 호출합니다.

- 컨트롤의 크기를 직접 조정하려면 *rect* 매개 변수를 사용하는 이 함수의 재정의를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

## <a name="cmonthcalctrlgetcalendarborder"></a><a name="getcalendarborder"></a>C월CalCtrl::GetCalendarBorder

현재 월 달력 컨트롤의 테두리 너비를 검색합니다.

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>Return Value

컨트롤 테두리의 너비(픽셀)입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [MCM_GETCALENDARBORDER](/windows/win32/Controls/mcm-getcalendarborder) 메시지를 보냅니다.

## <a name="cmonthcalctrlgetcalendarcount"></a><a name="getcalendarcount"></a>C월CalCtrl::GetCalendarCount

현재 월 달력 컨트롤에 표시되는 달력 수를 검색합니다.

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>Return Value

월 캘린더 컨트롤에 현재 표시되는 달력 수입니다. 허용되는 최대 캘린더 수는 12개입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [MCM_GETCALENDARCOUNT](/windows/win32/Controls/mcm-getcalendarcount) 메시지를 보냅니다.

## <a name="cmonthcalctrlgetcalendargridinfo"></a><a name="getcalendargridinfo"></a>C월CalCtrl::GetCalendar그리드정보

현재 월 달력 컨트롤에 대 한 정보를 검색합니다.

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pmcGridInfo*|【아웃】 현재 월 달력 컨트롤에 대한 정보를 수신하는 [MCGRIDINFO](/windows/win32/api/commctrl/ns-commctrl-mcgridinfo) 구조에 대한 포인터입니다. 호출자는 이 구조를 할당하고 초기화할 책임이 있습니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [MCM_GETCALENDARGRIDINFO](/windows/win32/Controls/mcm-getcalendargridinfo) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 월 `m_monthCalCtrl`달력 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 `GetCalendarGridInfo` 메서드를 사용 하 여 현재 월 달력 컨트롤에 표시 되는 달력 날짜를 검색 합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

## <a name="cmonthcalctrlgetcalid"></a><a name="getcalid"></a>C월칼Ctrl::겟칼리드

현재 월 달력 컨트롤에 대 한 달력 식별자를 검색 합니다.

```
CALID GetCalID() const;
```

### <a name="return-value"></a>Return Value

[달력 식별자](/windows/win32/Intl/calendar-identifiers) 상수 중 하나입니다.

### <a name="remarks"></a>설명

달력 식별자는 그레고리오력(지역화), 일본어 또는 회교식 달력과 같은 지역별 달력을 나타냅니다. 응용 프로그램은 다양한 언어 지원 기능이 있는 달력 식별자를 사용할 수 있습니다.

이 메서드는 Windows SDK에 설명 된 [MCM_GETCALID](/windows/win32/Controls/mcm-getcalid) 메시지를 보냅니다.

## <a name="cmonthcalctrlgetcolor"></a><a name="getcolor"></a>C월CalCtrl::GetColor

*nRegion에서*지정한 월 달력 컨트롤 영역의 색상을 검색합니다.

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>매개 변수

*n지역*<br/>
색상을 검색하는 월 달력 컨트롤의 영역입니다. 값 목록은 setColor 의 *nRegion* 매개 [변수를](#setcolor)참조하십시오.

### <a name="return-value"></a>Return Value

성공한 경우 월 달력 컨트롤의 부분과 연관된 색상을 지정하는 [COLORREF](/windows/win32/gdi/colorref) 값입니다. 그렇지 않으면 이 멤버 함수는 -1을 반환합니다.

## <a name="cmonthcalctrlgetcurrentview"></a><a name="getcurrentview"></a>C월CalCtrl::GetCurrentView

현재 월 달력 컨트롤에 의해 현재 표시 되는 보기를 검색 합니다.

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>Return Value

다음 값 중 하나로 표시되는 현재 뷰:

|값|의미|
|-----------|-------------|
|MCMV_MONTH|월간 보기|
|MCMV_YEAR|연간 보기|
|MCMV_DECADE|10년 전망|
|MCMV_CENTURY|센추리 뷰|

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 월 `m_monthCalCtrl`달력 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제는 현재 표시되는 월 캘린더 컨트롤을 보는 보고서입니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

## <a name="cmonthcalctrlgetcursel"></a><a name="getcursel"></a>C월CalCtrl::겟커셀

현재 선택한 날짜에 표시된 대로 시스템 시간을 검색합니다.

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 참조입니다. 현재 시간을 수신합니다.

*pDate시간*<br/>
현재 선택한 날짜 정보를 수신하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다. 이 매개 변수는 유효한 주소여야 하며 NULL일 수 없습니다.

### <a name="return-value"></a>Return Value

성공하면 영하지 않은; 기타 0.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [MCM_GETCURSEL](/windows/win32/Controls/mcm-getcursel)Win32 메시지의 동작을 구현합니다.

> [!NOTE]
> 스타일 MCS_MULTISELECT 설정하면 이 멤버 함수가 실패합니다.

의 MFC 구현에서 `GetCurSel` `COleDateTime` 사용, 사용 또는 `CTime` 구조 용도를 `SYSTEMTIME` 지정할 수 있습니다.

## <a name="cmonthcalctrlgetfirstdayofweek"></a><a name="getfirstdayofweek"></a>C월CalCtrl::GetFirstDayOfweek

달력의 맨 왼쪽 열에 표시할 요일의 첫 날을 가져옵니다.

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>매개 변수

*pbLocal*<br/>
BOOL 값에 대한 포인터입니다. 값이 0이 아닌 경우 컨트롤의 설정이 컨트롤 패널의 설정과 일치하지 않습니다.

### <a name="return-value"></a>Return Value

주의 첫 날을 나타내는 정수 값입니다. 이러한 정수의 표현에 대한 자세한 내용은 **비고를** 참조하십시오.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 MCM_GETFIRSTDAYOFWEEK Win32 [메시지의](/windows/win32/Controls/mcm-getfirstdayofweek)동작을 구현합니다. 요일은 다음과 같이 정수로 표시됩니다.

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

  [CMonthCalCtrl::SetFirstDayOfWeek에](#setfirstdayofweek)대한 예제를 참조하십시오.

## <a name="cmonthcalctrlgetmaxselcount"></a><a name="getmaxselcount"></a>C월CalCtrl::겟맥스셀카운트

월 달력 컨트롤에서 선택할 수 있는 현재 최대 일 수를 검색합니다.

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>Return Value

컨트롤에 대해 선택할 수 있는 총 일 수를 나타내는 정수 값입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 MCM_GETMAXSELCOUNT Win32 [메시지의](/windows/win32/Controls/mcm-getmaxselcount)동작을 구현합니다. MCS_MULTISELECT 스타일 집합이 있는 컨트롤에 이 멤버 함수를 사용합니다.

### <a name="example"></a>예제

  [CMonthCalCtrl::SetMaxSelCount에](#setmaxselcount)대한 예제를 참조하십시오.

## <a name="cmonthcalctrlgetmaxtodaywidth"></a><a name="getmaxtodaywidth"></a>C월CalCtrl::겟맥스투데이폭

현재 월 달력 컨트롤에 대 한 "오늘" 문자열의 최대 너비를 검색합니다.

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>Return Value

픽셀 단위로 "오늘" 문자열의 너비입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 월 `m_monthCalCtrl`달력 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제는 `GetMaxTodayWidth` 메서드.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>설명

사용자는 월력 컨트롤의 맨 아래에 표시되는 "오늘" 문자열을 클릭하여 현재 날짜로 돌아갈 수 있습니다. "오늘" 문자열에는 레이블 텍스트와 날짜 텍스트가 포함됩니다.

이 메서드는 Windows SDK에 설명 된 [MCM_GETMAXTODAYWIDTH](/windows/win32/Controls/mcm-getmaxtodaywidth) 메시지를 보냅니다.

## <a name="cmonthcalctrlgetminreqrect"></a><a name="getminreqrect"></a>C월칼렉트: 겟민렉트

월 달력 컨트롤에서 전체 월을 표시하는 데 필요한 최소 크기를 검색합니다.

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>매개 변수

*pRect*<br/>
경계 사각형 정보를 수신하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터입니다. 이 매개 변수는 유효한 주소여야 하며 NULL일 수 없습니다.

### <a name="return-value"></a>Return Value

성공하면 이 멤버 함수는 `lpRect` 0이 아닌 것을 반환하고 해당 경계 정보를 수신합니다. 실패하면 멤버 함수는 0을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 MCM_GETMINREQRECT Win32 [메시지의](/windows/win32/Controls/mcm-getminreqrect)동작을 구현합니다.

## <a name="cmonthcalctrlgetmonthdelta"></a><a name="getmonthdelta"></a>C월칼Ctrl::겟월델타

월 캘린더 컨트롤의 스크롤 속도를 검색합니다.

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>Return Value

월 캘린더 컨트롤의 스크롤 속도입니다. 스크롤 속도는 사용자가 스크롤 단추를 한 번 클릭할 때 컨트롤이 디스플레이를 이동하는 월 수입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [MCM_GETMONTHDELTA](/windows/win32/Controls/mcm-getmonthdelta)Win32 메시지의 동작을 구현합니다.

## <a name="cmonthcalctrlgetmonthrange"></a><a name="getmonthrange"></a>C월CalCtrl::GetMonthRange

월 캘린더 컨트롤의 표시의 높고 낮은 제한을 나타내는 날짜 정보를 검색합니다.

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

*레프민레인지*<br/>
허용되는 최소 날짜를 포함하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 참조입니다.

*레프맥스 레인지*<br/>
허용되는 최대 `COleDateTime` 날짜를 `CTime` 포함하는 또는 개체에 대한 참조입니다.

*pMinRange*<br/>
범위의 가장 낮은 끝에 있는 날짜를 포함하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

*pMax Range*<br/>
범위의 `SYSTEMTIME` 가장 높은 끝에 있는 날짜를 포함하는 구조체에 대한 포인터입니다.

*dwFlags*<br/>
검색할 범위 제한의 범위를 지정하는 값입니다. 이 값은 다음 중 하나여야 합니다.

|값|의미|
|-----------|-------------|
|GMR_DAYSTATE|부분적으로만 표시되는 가시 범위의 이전 및 후행 개월을 포함합니다.|
|GMR_VISIBLE|완전히 표시되는 달만 포함합니다.|

### <a name="return-value"></a>Return Value

첫 번째 및 두 번째 버전에서 *refMinRange* 및 *refMaxRange* 또는 세 번째 버전에서 *pMinRange* 및 *pMaxRange로* 표시된 두 제한에 따라 범위를 나타내는 정수입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 MCM_GETMONTHRANGE Win32 [메시지의](/windows/win32/Controls/mcm-getmonthrange)동작을 구현합니다. 의 MFC 구현에서 `GetMonthRange`사용, `COleDateTime` 사용 또는 `CTime` 구조 용도를 지정할 `SYSTEMTIME` 수 있습니다.

### <a name="example"></a>예제

  [CMonthCalCtrl::SetDayState에](#setdaystate)대한 예제를 참조하십시오.

## <a name="cmonthcalctrlgetrange"></a><a name="getrange"></a>C월CalCtrl::GetRange

월 캘린더 컨트롤에 설정된 현재 최소 날짜와 최대 날짜를 검색합니다.

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
범위의 가장 `COleDateTime` 낮은 `CTime` 끝에 있는 날짜를 포함하는 개체, 개체 또는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

*pMax Range*<br/>
범위의 가장 `COleDateTime` 높은 `CTime` 끝에 있는 날짜를 포함하는 개체, 개체 또는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

0이 될 수 있는 DWORD(제한설정 없음) 또는 제한 정보를 지정하는 다음 값의 조합입니다.

|값|의미|
|-----------|-------------|
|GDTR_MAX|컨트롤에 대한 최대 제한이 설정됩니다. *pMaxRange는* 유효하며 해당 날짜 정보가 포함되어 있습니다.|
|GDTR_MIN|컨트롤에 대한 최소 제한이 설정됩니다. *pMinRange는* 유효하며 해당 날짜 정보가 포함되어 있습니다.|

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 MCM_GETRANGE Win32 [메시지의](/windows/win32/Controls/mcm-getrange)동작을 구현합니다. 의 MFC 구현에서 `GetRange` `COleDateTime` 사용, 사용 또는 `CTime` 구조 용도를 `SYSTEMTIME` 지정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

## <a name="cmonthcalctrlgetselrange"></a><a name="getselrange"></a>C월칼Ctrl::겟셀레인지

사용자가 현재 선택한 날짜 범위의 상한 및 하한을 나타내는 날짜 정보를 검색합니다.

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

*레프민레인지*<br/>
허용되는 최소 날짜를 포함하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 참조입니다.

*레프맥스 레인지*<br/>
허용되는 최대 `COleDateTime` 날짜를 `CTime` 포함하는 또는 개체에 대한 참조입니다.

*pMinRange*<br/>
범위의 가장 낮은 끝에 있는 날짜를 포함하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

*pMax Range*<br/>
범위의 `SYSTEMTIME` 가장 높은 끝에 있는 날짜를 포함하는 구조체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [MCM_GETSELRANGE](/windows/win32/Controls/mcm-getselrange)Win32 메시지의 동작을 구현합니다. `GetSelRange`MCS_MULTISELECT 스타일을 사용하지 않는 월 달력 컨트롤에 적용하면 실패합니다.

의 MFC 구현에서 `GetSelRange`사용, `COleDateTime` 사용 또는 `CTime` 구조 용도를 지정할 `SYSTEMTIME` 수 있습니다.

## <a name="cmonthcalctrlgettoday"></a><a name="gettoday"></a>C월칼Ctrl::GetToday

월 달력 컨트롤에 대해 "오늘"로 지정된 날짜의 날짜 정보를 검색합니다.

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
현재 날짜를 나타내는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 참조입니다.

*pDate시간*<br/>
날짜 정보를 수신하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다. 이 매개 변수는 유효한 주소여야 하며 NULL일 수 없습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [MCM_GETTODAY](/windows/win32/Controls/mcm-gettoday)Win32 메시지의 동작을 구현합니다. 의 MFC 구현에서 `GetToday` `COleDateTime` 사용, 사용 또는 `CTime` 구조 용도를 `SYSTEMTIME` 지정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

## <a name="cmonthcalctrlhittest"></a><a name="hittest"></a>C월CalCtrl::히트 테스트

지정된 위치에 있는 월 달력 컨트롤(있는 경우)을 결정합니다.

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>매개 변수

*pMCHitTest*<br/>
월 캘린더 컨트롤에 대한 적중 테스트 지점이 포함된 [MCHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-mchittestinfo) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

DWORD 값입니다. 구조의 **uHit** 멤버와 `MCHITTESTINFO` 동일합니다.

### <a name="remarks"></a>설명

`HitTest`는 `MCHITTESTINFO` 적중 테스트에 대한 정보가 포함된 구조를 사용합니다.

## <a name="cmonthcalctrliscenturyview"></a><a name="iscenturyview"></a>C월칼Ctrl::이센추시뷰

현재 월 달력 컨트롤의 현재 보기가 세기 뷰인지 여부를 나타냅니다.

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>Return Value

현재 뷰가 세기 뷰인 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) 메시지를 보냅니다. 해당 메시지가 MCMV_CENTURY 반환하는 경우 이 메서드는 TRUE를 반환합니다.

## <a name="cmonthcalctrlisdecadeview"></a><a name="isdecadeview"></a>C월칼Ctrl::이십년뷰

현재 월 달력 컨트롤의 현재 보기가 10년 보기인지 여부를 나타냅니다.

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>Return Value

현재 뷰가 10년 뷰인 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) 메시지를 보냅니다. 해당 메시지가 MCMV_DECADE 반환하는 경우 이 메서드는 TRUE를 반환합니다.

## <a name="cmonthcalctrlismonthview"></a><a name="ismonthview"></a>C월CalCtrl::이월보기

현재 월 달력 컨트롤의 현재 보기가 월 보기인지 여부를 나타냅니다.

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>Return Value

현재 뷰가 월 보기인 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) 메시지를 보냅니다. 해당 메시지가 MCMV_MONTH 반환하는 경우 이 메서드는 TRUE를 반환합니다.

## <a name="cmonthcalctrlisyearview"></a><a name="isyearview"></a>C월칼Ctrl::이스이어뷰

현재 월 달력 컨트롤의 현재 보기가 연도 보기인지 여부를 나타냅니다.

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>Return Value

현재 뷰가 연도 뷰인 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) 메시지를 보냅니다. 해당 메시지가 MCMV_YEAR 반환하는 경우 이 메서드는 TRUE를 반환합니다.

## <a name="cmonthcalctrlsetcalendarborder"></a><a name="setcalendarborder"></a>C월CalCtrl::SetCalendarBorder

현재 월 달력 컨트롤의 테두리 너비를 설정합니다.

```cpp
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*cxyBorder*|【인】 테두리의 너비(픽셀)입니다.|

### <a name="remarks"></a>설명

이 메서드가 성공하면 테두리 너비가 *cxyBorder* 매개 변수로 설정됩니다. 그렇지 않으면 테두리 너비가 현재 [테마에](/windows/win32/Controls/visual-styles-overview)의해 지정된 기본값으로 재설정되거나 테마를 사용하지 않으면 0으로 재설정됩니다.

이 메서드는 Windows SDK에 설명 된 [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 월 `m_monthCalCtrl`달력 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제는 월 캘린더 컨트롤의 테두리 너비를 8픽셀로 설정합니다. [CMonthCalCtrl::GetCalendarBorder](#getcalendarborder) 메서드를 사용하여 이 메서드가 성공했는지 여부를 확인합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

## <a name="cmonthcalctrlsetcalendarborderdefault"></a><a name="setcalendarborderdefault"></a>C월CalCtrl::SetCalendarBorder기본

현재 월 달력 컨트롤의 테두리의 기본 너비를 설정합니다.

```cpp
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>설명

테두리 너비는 현재 [테마에](/windows/win32/Controls/visual-styles-overview)의해 지정된 기본값또는 테마를 사용하지 않는 경우 0으로 설정됩니다.

이 메서드는 Windows SDK에 설명 된 [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) 메시지를 보냅니다.

## <a name="cmonthcalctrlsetcalid"></a><a name="setcalid"></a>C월CalCtrl:::세트칼리드

현재 월 달력 컨트롤의 달력 식별자를 설정합니다.

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*칼ID*|【인】 [달력 식별자](/windows/win32/Intl/calendar-identifiers) 상수 중 하나입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

달력 식별자는 그레고리오력(지역화), 일본어 또는 회교식 달력과 같은 지역별 달력을 지정합니다. 달력을 `SetCalID` 포함하는 로캘이 컴퓨터에 설치된 경우 *calid* 매개 변수에 의해 지정된 달력을 표시하는 메서드를 사용합니다.

이 메서드는 Windows SDK에 설명 된 [MCM_SETCALID](/windows/win32/Controls/mcm-setcalid) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 월 `m_monthCalCtrl`달력 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제는 일본 황제 시대 달력을 표시하는 월 달력 컨트롤을 설정합니다. 이 `SetCalID` 메서드는 해당 일정이 컴퓨터에 설치된 경우에만 성공합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

## <a name="cmonthcalctrlsetcenturyview"></a><a name="setcenturyview"></a>C월칼Ctrl::세트센추치뷰

세기 보기를 표시 하도록 현재 월 달력 컨트롤을 설정 합니다.

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 메서드를 사용 `MCMV_CENTURY`하 여 00000뷰를 나타내는 뷰를 설정 합니다.

## <a name="cmonthcalctrlsetcolor"></a><a name="setcolor"></a>C월CalCtrl::세트컬러

월 달력 컨트롤의 지정된 영역의 색상을 설정합니다.

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>매개 변수

*n지역*<br/>
설정할 월 달력 색상을 지정하는 정수 값입니다. 이 값은 다음 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|MCSC_BACKGROUND|월 사이에 표시되는 배경색입니다.|
|MCSC_MONTHBK|월 내에 표시되는 배경색입니다.|
|MCSC_TEXT|한 달 이내에 텍스트를 표시하는 데 사용되는 색상입니다.|
|MCSC_TITLEBK|달력 제목에 표시되는 배경색입니다.|
|MCSC_TITLETEXT|캘린더 제목 내에 텍스트를 표시하는 데 사용되는 색상입니다.|
|MCSC_TRAILINGTEXT|헤더 및 후일 텍스트를 표시하는 데 사용되는 색상입니다. 헤더 및 후행 일은 현재 달력에 표시되는 이전 및 다음 달의 날짜입니다.|

*ref*<br/>
월 달력 컨트롤의 지정된 부분에 대 한 새 색상 설정에 대 한 COLORREF 값입니다.

### <a name="return-value"></a>Return Value

성공한 경우 월 달력 컨트롤의 지정된 부분에 대한 이전 색상 설정을 나타내는 COLORREF 값입니다. 그렇지 않으면 이 메시지가 -1을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 MCM_SETCOLOR Win32 [메시지의](/windows/win32/Controls/mcm-setcolor)동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

## <a name="cmonthcalctrlsetcurrentview"></a><a name="setcurrentview"></a>C월CalCtrl::설정현재보기

지정된 뷰를 표시하도록 현재 월 달력 컨트롤을 설정합니다.

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*dwNewView*|【인】 월별, 연간, 10년 또는 세기 보기를 지정하는 다음 값 중 하나입니다.<br /><br /> MCMV_MONTH: 월간 보기<br /><br /> MCMV_YEAR: 연간 보기<br /><br /> MCMV_DECADE: 10년 전망<br /><br /> MCMV_CENTURY: 센추리 뷰|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [MCM_SETCURRENTVIEW](/windows/win32/Controls/mcm-setcurrentview) 메시지를 보냅니다.

## <a name="cmonthcalctrlsetcursel"></a><a name="setcursel"></a>C월CalCtrl::세트컬셀

월 달력 컨트롤에 대해 현재 선택한 날짜를 설정합니다.

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
현재 선택한 월 달력 컨트롤을 나타내는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 참조입니다.

*pDate시간*<br/>
현재 선택 항목으로 설정할 날짜가 포함된 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 MCM_SETCURSEL Win32 [메시지의](/windows/win32/Controls/mcm-setcursel)동작을 구현합니다. 의 MFC 구현에서 `SetCurSel` `COleDateTime` 사용, 사용 또는 `CTime` 구조 용도를 `SYSTEMTIME` 지정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

## <a name="cmonthcalctrlsetdaystate"></a><a name="setdaystate"></a>C월CalCtrl::SetDaystate

월 달력 컨트롤의 일 동안 표시를 설정합니다.

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>매개 변수

*n개월*<br/>
*pStates가* 가리키는 배열에 있는 요소 수를 나타내는 값입니다.

*p스테이트*<br/>
월 달력 컨트롤이 매일 표시에서 그리는 방법을 정의하는 [MONTHDAYSTATE](/windows/win32/Controls/monthdaystate) 값 배열에 대한 포인터입니다. MONTHDAYSTATE 데이터 형식은 비트 필드로 각 비트(1~31)는 한 달의 일 상태를 나타냅니다. 비트가 켜지면 해당 날이 굵게 표시됩니다. 그렇지 않으면 강조없이 표시됩니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 MCM_SETDAYSTATE Win32 [메시지의](/windows/win32/Controls/mcm-setdaystate)동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

## <a name="cmonthcalctrlsetdecadeview"></a><a name="setdecadeview"></a>C월CalCtrl::SetDecadeView

현재 월 달력 컨트롤을 10년 보기로 설정합니다.

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 메서드를 사용 `MCMV_DECADE`하 여 10 0 뷰를 나타내는 뷰를 설정 합니다.

## <a name="cmonthcalctrlsetfirstdayofweek"></a><a name="setfirstdayofweek"></a>C월칼Ctrl::셋퍼스트데이오브위크

달력의 가장 왼쪽 열에 표시할 요일을 설정합니다.

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>매개 변수

*아이데이 (약)*<br/>
요일을 나타내는 정수 값을 해당 주의 첫 번째 날로 설정합니다. 이 값은 일 번호 중 하나여야 합니다. 하루 번호에 대한 설명은 [GetFirstDayOfWeek를](#getfirstdayofweek) 참조하십시오.

*lpnOld*<br/>
이전에 설정한 주의 첫 날을 나타내는 정수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

주 전날의 첫 날이 LOCALE_IFIRSTDAYOFWEEK 값이 아닌 값으로 설정된 경우 비영(nonzero)은 제어판 설정에 표시된 날입니다. 그렇지 않으면 이 함수는 0을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [MCM_SETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-setfirstdayofweek)Win32 메시지의 동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

## <a name="cmonthcalctrlsetmaxselcount"></a><a name="setmaxselcount"></a>C월CalCtrl::세트맥스셀카운트

월 캘린더 컨트롤에서 선택할 수 있는 최대 일 수를 설정합니다.

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>매개 변수

*nMax*<br/>
선택할 수 있는 최대 일 수를 나타내도록 설정되는 값입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 MCM_SETMAXSELCOUNT Win32 [메시지의](/windows/win32/Controls/mcm-setmaxselcount)동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

## <a name="cmonthcalctrlsetmonthdelta"></a><a name="setmonthdelta"></a>C월칼Ctrl::세트월델타

월 캘린더 컨트롤의 스크롤 속도를 설정합니다.

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>매개 변수

*아이델타*<br/>
컨트롤의 스크롤 속도로 설정할 개월 수입니다. 이 값이 0이면 월 델타가 기본값으로 재설정되고 컨트롤에 표시되는 월 수입니다.

### <a name="return-value"></a>Return Value

이전 스크롤 속도입니다. 스크롤 속도가 이전에 설정되지 않은 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [MCM_SETMONTHDELTA](/windows/win32/Controls/mcm-setmonthdelta)Win32 메시지의 동작을 구현합니다.

## <a name="cmonthcalctrlsetmonthview"></a><a name="setmonthview"></a>C월CalCtrl::세트월뷰

현재 월 캘린더 컨트롤을 설정하여 월 보기를 표시합니다.

```
BOOL SetMonthView();
```

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 메서드를 사용 하 여 MCMV_MONTH 뷰를 설정 하 고 월 보기를 나타냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 월 `m_monthCalCtrl`달력 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 월, 연도, 10년 및 세기 보기를 표시할 월 달력 컨트롤을 설정합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

## <a name="cmonthcalctrlsetrange"></a><a name="setrange"></a>C월CalCtrl::세트레인지

월 캘린더 컨트롤의 최소 및 최대 허용 날짜를 설정합니다.

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
범위의 가장 `COleDateTime` 낮은 `CTime` 끝에 있는 날짜를 포함하는 개체, 개체 또는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

*pMax Range*<br/>
범위의 가장 `COleDateTime` 높은 `CTime` 끝에 있는 `SYSTEMTIME` 날짜를 포함하는 개체, 개체 또는 구조체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [MCM_SETRANGE](/windows/win32/Controls/mcm-setrange)Win32 메시지의 동작을 구현합니다. 의 MFC 구현에서 `SetRange`사용, `COleDateTime` 사용 또는 `CTime` 구조 용도를 지정할 `SYSTEMTIME` 수 있습니다.

### <a name="example"></a>예제

  [CMonthCalCtrl::GetRange에](#getrange)대한 예제를 참조하십시오.

## <a name="cmonthcalctrlsetselrange"></a><a name="setselrange"></a>C월칼Ctrl::세트셀레인지

월 캘린더 컨트롤의 선택 항목을 지정된 날짜 범위로 설정합니다.

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
범위의 가장 `COleDateTime` 낮은 `CTime` 끝에 있는 날짜를 포함하는 개체, 개체 또는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

*pMax Range*<br/>
범위의 가장 `COleDateTime` 높은 `CTime` 끝에 있는 `SYSTEMTIME` 날짜를 포함하는 개체, 개체 또는 구조체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 MCM_SETSELRANGE Win32 [메시지의](/windows/win32/Controls/mcm-setselrange)동작을 구현합니다. 의 MFC 구현에서 `SetSelRange`사용, `COleDateTime` 사용 또는 `CTime` 구조 용도를 지정할 `SYSTEMTIME` 수 있습니다.

## <a name="cmonthcalctrlsettoday"></a><a name="settoday"></a>C월칼Ctrl::세트투데이

현재 날짜의 달력 컨트롤을 설정합니다.

```cpp
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
현재 날짜를 포함하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체에 대한 참조입니다.

*pDate시간*<br/>
두 번째 버전에서는 현재 날짜 정보를 포함하는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 포인터입니다. 세 번째 버전에서는 현재 날짜 정보가 포함된 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [MCM_SETTODAY](/windows/win32/Controls/mcm-settoday)Win32 메시지의 동작을 구현합니다.

### <a name="example"></a>예제

  [CMonthCalCtrl::GetToday에](#gettoday)대한 예제를 참조하십시오.

## <a name="cmonthcalctrlsetyearview"></a><a name="setyearview"></a>C월CalCtrl::세트이어뷰

현재 월 달력 컨트롤을 연도 보기로 설정합니다.

```
BOOL SetYearView();
```

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 메서드를 사용 하 여 뷰를 MCMV_YEAR 설정 합니다., 연간 보기를 나타내는.

## <a name="cmonthcalctrlsizeminreq"></a><a name="sizeminreq"></a>C월칼Ctrl::크기민렉

월 캘린더 컨트롤을 한 달을 표시하는 최소 크기로 표시합니다.

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>매개 변수

*bRepaint*<br/>
컨트롤을 다시 칠할지 여부를 지정합니다. 기본적으로 TRUE입니다. FALSE인 경우 다시 그리기가 발생하지 않습니다.

### <a name="return-value"></a>Return Value

월 달력 컨트롤의 크기가 최소인 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

호출에 `SizeMinReq` 한 달 달력에 대한 전체 월 캘린더 컨트롤이 성공적으로 표시됩니다.

## <a name="cmonthcalctrlsizerecttomin"></a><a name="sizerecttomin"></a>C월칼트르::사이즈렉토민

현재 월 달력 컨트롤의 경우 지정된 사각형에 맞는 모든 캘린더를 포함할 수 있는 가장 작은 사각형을 계산합니다.

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*Lprect*|【인】 원하는 수의 달력을 포함하는 사각형을 정의하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

크기가 [lpRect](/windows/win32/api/windef/ns-windef-rect) 매개 변수에 의해 정의된 사각형보다 작거나 같은 사각형을 정의하는 *RECT* 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 *lpRect* 매개 변수에 의해 지정 된 사각형에 맞게 수 있는 달력 수를 계산 하 고 해당 수의 달력을 포함할 수 있는 가장 작은 사각형을 반환 합니다. 실제로 이 메서드는 지정된 사각형을 원하는 수의 달력에 정확히 맞도록 축소합니다.

이 메서드는 Windows SDK에 설명 된 [MCM_SIZERECTTOMIN](/windows/win32/Controls/mcm-sizerecttomin) 메시지를 보냅니다.

## <a name="see-also"></a>참조

[MFC 샘플 CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDateTimeCtrl 클래스](../../mfc/reference/cdatetimectrl-class.md)
