---
title: CDateTimeCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
helpviewer_keywords:
- CDateTimeCtrl [MFC], CDateTimeCtrl
- CDateTimeCtrl [MFC], CloseMonthCal
- CDateTimeCtrl [MFC], Create
- CDateTimeCtrl [MFC], GetDateTimePickerInfo
- CDateTimeCtrl [MFC], GetIdealSize
- CDateTimeCtrl [MFC], GetMonthCalColor
- CDateTimeCtrl [MFC], GetMonthCalCtrl
- CDateTimeCtrl [MFC], GetMonthCalFont
- CDateTimeCtrl [MFC], GetMonthCalStyle
- CDateTimeCtrl [MFC], GetRange
- CDateTimeCtrl [MFC], GetTime
- CDateTimeCtrl [MFC], SetFormat
- CDateTimeCtrl [MFC], SetMonthCalColor
- CDateTimeCtrl [MFC], SetMonthCalFont
- CDateTimeCtrl [MFC], SetMonthCalStyle
- CDateTimeCtrl [MFC], SetRange
- CDateTimeCtrl [MFC], SetTime
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
ms.openlocfilehash: 577dde7f4f4209f15590825fdb87fe23f788a1ce
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754617"
---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl 클래스

날짜 및 시간 선택 컨트롤의 기능을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CDateTimeCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDate타임Ctrl::CDate타임Ctrl](#cdatetimectrl)|`CDateTimeCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDate타임Ctrl::닫기월칼](#closemonthcal)|현재 날짜 및 시간 선택기 컨트롤을 닫습니다.|
|[CDateTimeCtrl::만들기](#create)|날짜 및 시간 선택기 컨트롤을 만들고 `CDateTimeCtrl` 개체에 연결합니다.|
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|현재 날짜 및 시간 선택기 컨트롤에 대한 정보를 검색합니다.|
|[CDate타임Ctrl::겟이상적 크기](#getidealsize)|현재 날짜 또는 시간을 표시하는 데 필요한 날짜 및 시간 선택기 컨트롤의 이상적인 크기를 반환합니다.|
|[CDate타임Ctrl::겟월칼라컬러](#getmonthcalcolor)|날짜 및 시간 선택기 컨트롤 내에서 해당 월 달력의 지정된 부분에 대한 색상을 검색합니다.|
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|날짜 및 `CMonthCalCtrl` 시간 선택기 컨트롤과 연결된 개체를 검색합니다.|
|[CDate타임Ctrl::겟월CalFont](#getmonthcalfont)|날짜 및 시간 선택기 컨트롤의 자식 월 달력 컨트롤에서 현재 사용 중인 글꼴을 검색합니다.|
|[CDate타임Ctrl::겟월칼스타일](#getmonthcalstyle)|현재 날짜 및 시간 선택기 컨트롤의 스타일을 가져옵니다.|
|[CDate타임Ctrl::GetRange](#getrange)|날짜 및 시간 선택기 컨트롤에 대해 현재 최소 및 최대 허용 시스템 시간을 검색합니다.|
|[CDateTimeCtrl::GetTime](#gettime)|날짜 및 시간 선택기 컨트롤에서 현재 선택한 시간을 검색하고 `SYSTEMTIME` 지정된 구조에 넣습니다.|
|[CDateTimeCtrl::설정 형식](#setformat)|지정된 형식 문자열에 따라 날짜 및 시간 선택기 컨트롤의 표시를 설정합니다.|
|[CDate타임Ctrl::세트월칼컬러](#setmonthcalcolor)|날짜 및 시간 선택기 컨트롤 내에서 월 달력의 지정된 부분에 대한 색상을 설정합니다.|
|[CDate타임Ctrl::세트월CalFont](#setmonthcalfont)|날짜 및 시간 선택기 컨트롤의 자식 월 달력 컨트롤에서 사용할 글꼴을 설정합니다.|
|[CDate타임Ctrl::세트월칼스타일](#setmonthcalstyle)|현재 날짜 및 시간 선택기 컨트롤의 스타일을 설정합니다.|
|[CDate타임Ctrl::세트레인지](#setrange)|날짜 및 시간 선택기 컨트롤에 대해 허용되는 최소 및 최대 시스템 시간을 설정합니다.|
|[CDateTimeCtrl::설정 시간](#settime)|날짜 및 시간 선택기 컨트롤에서 시간을 설정합니다.|

## <a name="remarks"></a>설명

날짜 및 시간 선택기 컨트롤(DTP 컨트롤)은 날짜 및 시간 정보를 사용자와 교환하는 간단한 인터페이스를 제공합니다. 이 인터페이스에는 각각 컨트롤에 저장된 날짜 및 시간 정보의 일부를 표시하는 필드가 포함되어 있습니다. 사용자는 지정된 필드의 문자열 내용을 변경하여 컨트롤에 저장된 정보를 변경할 수 있습니다. 사용자는 마우스 나 키보드를 사용하여 필드에서 필드로 이동할 수 있습니다.

생성할 때 개체에 다양한 스타일을 적용하여 날짜 및 시간 선택기 컨트롤을 사용자 지정할 수 있습니다. [날짜 및 시간 선택기 컨트롤과](/windows/win32/Controls/date-and-time-picker-control-styles) 관련된 스타일에 대한 자세한 내용은 Windows SDK의 날짜 및 시간 선택기 제어 스타일을 참조하십시오. 형식 스타일을 사용하여 DTP 컨트롤의 표시 형식을 설정할 수 있습니다. 이러한 형식 스타일은 Windows SDK 항목 [날짜 및 시간 선택기 제어 스타일에서](/windows/win32/Controls/date-and-time-picker-control-styles)"형식 스타일"에 설명되어 있습니다.

날짜 및 시간 선택기 컨트롤은 [CDateTimeCtrl 사용에](../../mfc/using-cdatetimectrl.md)설명된 알림 및 콜백도 사용합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDateTimeCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxdtctl.h

## <a name="cdatetimectrlcdatetimectrl"></a><a name="cdatetimectrl"></a>CDate타임Ctrl::CDate타임Ctrl

`CDateTimeCtrl` 개체를 생성합니다.

```
CDateTimeCtrl();
```

## <a name="cdatetimectrlclosemonthcal"></a><a name="closemonthcal"></a>CDate타임Ctrl::닫기월칼

현재 날짜 및 시간 선택기 컨트롤을 닫습니다.

```cpp
void CloseMonthCal() const;
```

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [DTM_CLOSEMONTHCAL](/windows/win32/Controls/dtm-closemonthcal) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 날짜 및 시간 선택기 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 *m_dateTimeCtrl*을 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제는 현재 날짜 및 시간 선택기 컨트롤에 대한 드롭다운 일정을 닫습니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]

## <a name="cdatetimectrlcreate"></a><a name="create"></a>CDateTimeCtrl::만들기

날짜 및 시간 선택기 컨트롤을 만들고 `CDateTimeCtrl` 개체에 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
날짜 시간 제어 스타일의 조합을 지정합니다. 날짜 및 시간 선택기 스타일에 대한 자세한 내용은 Windows SDK의 [날짜 및 시간 선택기 제어 스타일을](/windows/win32/Controls/date-and-time-picker-control-styles) 참조하십시오.

*rect*<br/>
날짜 및 시간 선택기 컨트롤의 위치와 크기인 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*pParentWnd*<br/>
날짜 및 시간 선택기 컨트롤의 상위 창인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터입니다. NULL이 아니어야 합니다.

*nID*<br/>
날짜 및 시간 선택기 컨트롤의 컨트롤 ID를 지정합니다.

### <a name="return-value"></a>Return Value

생성이 성공한 경우 영하지 않습니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

##### <a name="to-create-a-date-and-time-picker-control"></a>날짜 및 시간 선택기 컨트롤을 만들려면

1. [CDateTimeCtrl을](#cdatetimectrl) 호출하여 `CDateTimeCtrl` 개체를 생성합니다.

1. Windows 날짜 및 시간 선택기 컨트롤을 만들고 개체에 연결 `CDateTimeCtrl` 하는 이 멤버 함수를 호출 합니다.

호출하면 `Create`공통 컨트롤이 초기화됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]

## <a name="cdatetimectrlgetdatetimepickerinfo"></a><a name="getdatetimepickerinfo"></a>CDateTimeCtrl::GetDateTimePickerInfo

현재 날짜 및 시간 선택기 컨트롤에 대한 정보를 검색합니다.

```
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pDate시간 선택기정보*|【아웃】 현재 날짜 및 시간 선택기 컨트롤에 대한 설명을 수신하는 [DATETIMEPICKERINFO](/windows/win32/api/commctrl/ns-commctrl-datetimepickerinfo) 구조에 대한 포인터입니다.<br /><br /> 호출자는 이 구조를 할당할 책임이 있습니다. 그러나 이 메서드는 구조체의 *cbSize* 멤버를 초기화합니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [DTM_GETDATETIMEPICKERINFO](/windows/win32/Controls/dtm-getdatetimepickerinfo) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 날짜 및 시간 선택기 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 *m_dateTimeCtrl*을 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제는 현재 날짜 및 시간 선택기 컨트롤에 대한 정보를 성공적으로 검색하는지 여부를 나타냅니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]

## <a name="cdatetimectrlgetmonthcalcolor"></a><a name="getmonthcalcolor"></a>CDate타임Ctrl::겟월칼라컬러

날짜 및 시간 선택기 컨트롤 내에서 해당 월 달력의 지정된 부분에 대한 색상을 검색합니다.

```
COLORREF GetMonthCalColor(int iColor) const;
```

### <a name="parameters"></a>매개 변수

*아이 컬러*<br/>
검색할 월 달력의 색상 영역을 지정하는 **int** 값입니다. 값 목록은 [SetMonthCalColor](#setmonthcalcolor)에 대한 *iColor* 매개 변수를 참조하십시오.

### <a name="return-value"></a>Return Value

성공한 경우 월 달력 컨트롤의 지정된 부분에 대한 색상 설정을 나타내는 COLORREF 값입니다. 함수가 실패하면 -1을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [DTM_GETMCCOLOR](/windows/win32/Controls/dtm-getmccolor)Win32 메시지의 동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]

## <a name="cdatetimectrlgetmonthcalctrl"></a><a name="getmonthcalctrl"></a>CDateTimeCtrl::GetMonthCalCtrl

날짜 및 `CMonthCalCtrl` 시간 선택기 컨트롤과 연결된 개체를 검색합니다.

```
CMonthCalCtrl* GetMonthCalCtrl() const;
```

### <a name="return-value"></a>Return Value

[CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) 개체에 대한 포인터 또는 실패하거나 창이 표시되지 않는 경우 NULL입니다.

### <a name="remarks"></a>설명

날짜 및 시간 선택기 컨트롤은 사용자가 드롭다운 화살표를 클릭할 때 자식 월 캘린더 컨트롤을 만듭니다. 개체가 `CMonthCalCtrl` 더 이상 필요하지 않은 경우 개체가 소멸되므로 응용 프로그램은 날짜 시간 선택기 컨트롤의 자식 월 달력을 나타내는 개체를 저장하는 데 의존해서는 안 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]

## <a name="cdatetimectrlgetmonthcalfont"></a><a name="getmonthcalfont"></a>CDate타임Ctrl::겟월CalFont

날짜 및 시간 선택기 컨트롤의 월 달력 컨트롤에서 현재 사용 되는 글꼴을 가져옵니다.

```
CFont* GetMonthCalFont() const;
```

### <a name="return-value"></a>Return Value

[CFont](../../mfc/reference/cfont-class.md) 개체에 대한 포인터 또는 실패할 경우 NULL입니다.

### <a name="remarks"></a>설명

반환 `CFont` 값으로 가리키는 개체는 임시 개체이며 다음 유휴 처리 시간 동안 소멸됩니다.

## <a name="cdatetimectrlgetmonthcalstyle"></a><a name="getmonthcalstyle"></a>CDate타임Ctrl::겟월칼스타일

현재 날짜 및 시간 선택기 컨트롤과 연결된 드롭다운 월 달력 컨트롤의 스타일을 가져옵니다.

```
DWORD GetMonthCalStyle() const;
```

### <a name="return-value"></a>Return Value

날짜 및 시간 선택기 컨트롤 스타일의 비트 조합(OR)인 드롭다운 월 달력 컨트롤의 스타일입니다. 자세한 내용은 [월 캘린더 제어 스타일을](/windows/win32/Controls/month-calendar-control-styles)참조하십시오.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [DTM_GETMCSTYLE](/windows/win32/Controls/dtm-getmcstyle) 메시지를 보냅니다.

## <a name="cdatetimectrlgetrange"></a><a name="getrange"></a>CDate타임Ctrl::GetRange

날짜 및 시간 선택기 컨트롤에 대해 현재 최소 및 최대 허용 시스템 시간을 검색합니다.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;
```

### <a name="parameters"></a>매개 변수

*pMinRange*<br/>
[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체또는 개체에서 허용되는 가장 빠른 시간을 포함하는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 `CDateTimeCtrl` 포인터입니다.

*pMax Range*<br/>
개체에 허용되는 `COleDateTime` 최신 `CTime` 시간을 포함하는 개체 또는 개체에 대한 포인터입니다. `CDateTimeCtrl`

### <a name="return-value"></a>Return Value

설정된 범위를 나타내는 플래그가 포함된 DWORD 값입니다. 다음과 같은 경우

`return value & GDTR_MAX` == 0

두 번째 매개 변수가 유효합니다. 마찬가지로,

`return value & GDTR_MIN` == 0

첫 번째 매개 변수가 유효합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [DTM_GETRANGE](/windows/win32/Controls/dtm-getrange)Win32 메시지의 동작을 구현합니다. MFC의 구현에서 사용법 중 `COleDateTime` `CTime` 하나 또는 사용을 지정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]

## <a name="cdatetimectrlgettime"></a><a name="gettime"></a>CDateTimeCtrl::GetTime

날짜 및 시간 선택기 컨트롤에서 현재 선택한 시간을 검색하고 `SYSTEMTIME` 지정된 구조에 넣습니다.

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>매개 변수

*timeDest*<br/>
첫 번째 버전에서는 시스템 시간 정보를 수신하는 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체에 대한 참조입니다. 두 번째 버전에서는 시스템 시간 정보를 수신하는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 참조입니다.

*p시간*<br/>
시스템 시간 정보를 수신하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다. NULL이 아니어야 합니다.

### <a name="return-value"></a>Return Value

첫 번째 버전에서는 시간이 `COleDateTime` 개체에 성공적으로 기록된 경우 0이 아닌 경우 그렇지 않으면 0. 두 번째 및 세 번째 버전에서 DWORD 값은 [NMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) 구조에 설정된 *dwFlag* 멤버와 같습니다. 자세한 내용은 아래 **비고** 섹션을 참조하십시오.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 DTM_GETSYSTEMTIME Win32 [메시지의](/windows/win32/Controls/dtm-getsystemtime)동작을 구현합니다. 의 `GetTime`MFC 구현에서 시간 `COleDateTime` 정보를 `CTime` 저장하기 위해 구조를 `SYSTEMTIME` 사용하거나 클래스를 사용할 수 있습니다.

위의 두 번째 및 세 번째 버전에서 반환 값 DWORD는 날짜 및 시간 선택기 컨트롤이 [NMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) 구조 멤버 *dwFlags에*표시된 대로 "날짜 없음" 상태로 설정되어 있는지 여부를 나타냅니다. 반환된 값이 GDT_NONE 같으면 컨트롤이 "날짜 없음" 상태로 설정되고 DTS_SHOWNONE 스타일을 사용합니다. 반환된 값이 GDT_VALID 같으면 시스템 시간이 대상 위치에 성공적으로 저장됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]

## <a name="cdatetimectrlgetidealsize"></a><a name="getidealsize"></a>CDate타임Ctrl::겟이상적 크기

현재 날짜 또는 시간을 표시하는 데 필요한 날짜 및 시간 선택기 컨트롤의 이상적인 크기를 반환합니다.

```
BOOL GetIdealSize(LPSIZE psize) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*크기 조정*|【아웃】 컨트롤에 이상적인 크기를 포함하는 [SIZE](/windows/win32/api/windef/ns-windef-size) 구조에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

반환 값은 항상 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [DTM_GETIDEALSIZE](/windows/win32/Controls/dtm-getidealsize) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 날짜 및 시간 선택기 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 *m_dateTimeCtrl*을 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제는 날짜 및 시간 선택기 컨트롤을 표시하는 이상적인 크기를 검색합니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]

## <a name="cdatetimectrlsetformat"></a><a name="setformat"></a>CDateTimeCtrl::설정 형식

지정된 형식 문자열에 따라 날짜 및 시간 선택기 컨트롤의 표시를 설정합니다.

```
BOOL SetFormat(LPCTSTR pstrFormat);
```

### <a name="parameters"></a>매개 변수

*pstrFormat*<br/>
원하는 표시를 정의하는 0-종단 형식 문자열에 대한 포인터입니다. 이 매개 변수를 NULL로 설정하면 컨트롤이 현재 스타일에 대한 기본 형식 문자열로 재설정됩니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

> [!NOTE]
> 사용자 입력은 이 호출의 성공 또는 실패를 결정하지 않습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 DTM_SETFORMAT Win32 [메시지의](/windows/win32/Controls/dtm-setformat)동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]

## <a name="cdatetimectrlsetmonthcalcolor"></a><a name="setmonthcalcolor"></a>CDate타임Ctrl::세트월칼컬러

날짜 및 시간 선택기 컨트롤 내에서 월 달력의 지정된 부분에 대한 색상을 설정합니다.

```
COLORREF SetMonthCalColor(
    int iColor,
    COLORREF ref);
```

### <a name="parameters"></a>매개 변수

*아이 컬러*<br/>
**int** 값은 설정할 월 달력 제어영역을 지정합니다. 이 값은 다음 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|MCSC_BACKGROUND|월 사이에 표시되는 배경색을 설정합니다.|
|MCSC_MONTHBK|한 달 내에 표시되는 배경색을 설정합니다.|
|MCSC_TEXT|한 달 이내에 텍스트를 표시하는 데 사용되는 색상을 설정합니다.|
|MCSC_TITLEBK|캘린더 제목에 표시되는 배경색을 설정합니다.|
|MCSC_TITLETEXT|캘린더 제목 내에 텍스트를 표시하는 데 사용되는 색상을 설정합니다.|
|MCSC_TRAILINGTEXT|헤더 및 후일 텍스트를 표시하는 데 사용되는 색상을 설정합니다. 헤더 및 후행 일은 현재 달력에 표시되는 이전 및 다음 달의 날짜입니다.|

*ref*<br/>
월력의 지정된 영역에 대해 설정될 색상을 나타내는 COLORREF 값입니다.

### <a name="return-value"></a>Return Value

성공한 경우 월 달력 컨트롤의 지정된 부분에 대한 이전 색상 설정을 나타내는 COLORREF 값입니다. 그렇지 않으면 메시지가 -1을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 DTM_SETMCCOLOR Win32 [메시지의](/windows/win32/Controls/dtm-setmccolor)동작을 구현합니다.

### <a name="example"></a>예제

  [CDateTimeCtrl::GetMonthCalColor에](#getmonthcalcolor)대한 예제를 참조하십시오.

## <a name="cdatetimectrlsetmonthcalfont"></a><a name="setmonthcalfont"></a>CDate타임Ctrl::세트월CalFont

날짜 및 시간 선택기 컨트롤의 자식 월 달력 컨트롤에서 사용할 글꼴을 설정합니다.

```cpp
void SetMonthCalFont(
    HFONT hFont,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*hFont*<br/>
설정될 글꼴을 처리합니다.

*bRedraw*<br/>
글꼴을 설정하면 컨트롤을 즉시 다시 그려야 하는지 여부를 지정합니다. 이 매개변수를 TRUE로 설정하면 컨트롤이 다시 그려지습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 DTM_SETMCFONT Win32 [메시지의](/windows/win32/Controls/dtm-setmcfont)동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]

> [!NOTE]
> 이 코드를 사용하는 경우 형식의 `CDialog` `CFont` *m_MonthFont라는* -derived 클래스의 멤버를 만들어야 합니다.

## <a name="cdatetimectrlsetmonthcalstyle"></a><a name="setmonthcalstyle"></a>CDate타임Ctrl::세트월칼스타일

현재 날짜 및 시간 선택기 컨트롤과 연결된 드롭다운 월 달력 컨트롤의 스타일을 설정합니다.

```
DWORD SetMonthCalStyle(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*dwStyle*|【인】 월 캘린더 제어 스타일의 비트 조합(OR)인 새 월 달력 제어 스타일입니다. 자세한 내용은 [월 캘린더 제어 스타일을](/windows/win32/Controls/month-calendar-control-styles)참조하십시오.|

### <a name="return-value"></a>Return Value

드롭다운 월 캘린더 컨트롤의 이전 스타일입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [DTM_SETMCSTYLE](/windows/win32/Controls/dtm-setmcstyle) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 날짜 및 시간 선택기 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 *m_dateTimeCtrl*을 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 주 번호, 축약된 요일 이름 및 오늘 표시기를 표시할 날짜 및 시간 선택기 컨트롤을 설정합니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]

## <a name="cdatetimectrlsetrange"></a><a name="setrange"></a>CDate타임Ctrl::세트레인지

날짜 및 시간 선택기 컨트롤에 대해 허용되는 최소 및 최대 시스템 시간을 설정합니다.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);
```

### <a name="parameters"></a>매개 변수

*pMinRange*<br/>
[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체또는 개체에서 허용되는 가장 빠른 시간을 포함하는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 `CDateTimeCtrl` 포인터입니다.

*pMax Range*<br/>
개체에 허용되는 `COleDateTime` 최신 `CTime` 시간을 포함하는 개체 또는 개체에 대한 포인터입니다. `CDateTimeCtrl`

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 DTM_SETRANGE Win32 [메시지의](/windows/win32/Controls/dtm-setrange)동작을 구현합니다. MFC의 구현에서 사용법 중 `COleDateTime` `CTime` 하나 또는 사용을 지정할 수 있습니다. 개체에 `COleDateTime` NULL 상태가 있으면 범위가 제거됩니다. 포인터 `CTime` 또는 포인터가 `COleDateTime` NULL이면 범위가 제거됩니다.

### <a name="example"></a>예제

  [CDateTimeCtrl::GetRange에](#getrange)대한 예제를 참조하십시오.

## <a name="cdatetimectrlsettime"></a><a name="settime"></a>CDateTimeCtrl::설정 시간

날짜 및 시간 선택기 컨트롤에서 시간을 설정합니다.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* pTimeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```

### <a name="parameters"></a>매개 변수

*시간새*<br/>
컨트롤이 설정될 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체에 대한 참조입니다.

*pTimeNew*<br/>
위의 두 번째 버전에서는 컨트롤이 설정되는 시간을 포함하는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 대한 포인터입니다. 위의 세 번째 버전에서는 컨트롤이 설정되는 시간을 포함하는 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 DTM_SETSYSTEMTIME Win32 [메시지의](/windows/win32/Controls/dtm-setsystemtime)동작을 구현합니다. 의 MFC `SetTime`구현에서 `COleDateTime` 또는 `CTime` 클래스를 `SYSTEMTIME` 사용하거나 구조를 사용하여 시간 정보를 설정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C월칼Ctrl 클래스](../../mfc/reference/cmonthcalctrl-class.md)
