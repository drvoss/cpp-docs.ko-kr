---
title: CMFC리본진행률
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
ms.openlocfilehash: b7cbddbd4fca8379562b762fadbb3d2bda44f166
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753538"
---
# <a name="cmfcribbonprogressbar-class"></a>CMFC리본진행률

긴 작업의 진행률을 시각적으로 나타내는 컨트롤을 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC리본 진행률 표시줄::CMFC리본 진행률바](#cmfcribbonprogressbar)|`CMFCRibbonProgressBar` 개체를 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC리본 진행률 표시줄::GetPos](#getpos)|현재 진행률을 반환합니다.|
|[CMFC리본 진행률 바::겟레인지맥스](#getrangemax)|현재 범위의 최대값을 반환합니다.|
|[CMFC리본 진행률 표시줄::겟레인지민](#getrangemin)|현재 범위의 최소값을 반환합니다.|
|[CMFC리본 진행률 표시줄::GetRegularsize](#getregularsize)|리본 요소의 보통 크기를 반환합니다. [(CMFC 리본베이스 요소 재정의::GetRegularSize.)](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)|
|[CMFC리본 진행률 표시줄::이무한모드](#isinfinitemode)|진행률 표시줄이 무한 모드에서 작동하는지 여부를 지정합니다.|
|[CMFC리본 진행률 표시줄::온드로우](#ondraw)|리본 요소를 그리기 위해 프레임워크에서 호출됩니다. [(CMFC 리본베이스 요소 재정의::온드로우.)](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw)|
|[CMFC리본 진행률 표시줄::설정 무한모드](#setinfinitemode)|진행률 표시줄을 무한 모드에서 작동하도록 설정합니다.|
|[CMFC리본 진행률 표시줄::세트포지](#setpos)|현재 진행률을 설정합니다.|
|[CMFC리본 진행률 표시줄::설정 범위](#setrange)|최소값과 최대값을 설정합니다.|

## <a name="remarks"></a>설명

A는 `CMFCRibbonProgressBar` 일반 모드와 무한의 두 가지 모드로 작동 할 수 있습니다. 일반 모드에서진행률 표시줄은 왼쪽에서 오른쪽으로 채워지고 최대값에 도달하면 중지됩니다. 무한 모드에서 진행률 표시줄은 최소값에서 최대값까지 반복적으로 채워져 있습니다. 무한 모드를 사용하여 작업이 진행 중이지만 완료 시간을 알 수 없음을 나타낼 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonProgressBar` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 진행률 표시줄을 무한 모드(작업 완료 시간을 알 수 없음)에서 작동하도록 설정하고 진행률 표시줄의 최소 값과 최대값을 설정하고 진행률 표시줄의 현재 위치를 설정하는 방법을 보여 주며 있습니다. 이 코드 조각은 MS [Office 2007 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afx리본진행바.h

## <a name="cmfcribbonprogressbarcmfcribbonprogressbar"></a><a name="cmfcribbonprogressbar"></a>CMFC리본 진행률 표시줄::CMFC리본 진행률바

[CMFC리본진행바](../../mfc/reference/cmfcribbonprogressbar-class.md) 오브젝트를 생성하고 초기화합니다.

```
CMFCRibbonProgressBar();

CMFCRibbonProgressBar(
    UINT nID,
    int nWidth = 90,
    int nHeight = 22);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 리본 진행률 표시줄에 대한 명령 ID를 지정합니다.

*nWidth*<br/>
【인】 리본 진행률 표시줄의 너비(픽셀)를 지정합니다.

*nHeight*<br/>
【인】 리본 진행률 표시줄의 높이(픽셀)를 지정합니다.

## <a name="cmfcribbonprogressbargetpos"></a><a name="getpos"></a>CMFC리본 진행률 표시줄::GetPos

진행률 표시줄의 현재 위치를 반환합니다.

```
int GetPos () const;
```

### <a name="return-value"></a>Return Value

진행률 표시줄의 현재 위치를 나타내는 값입니다.

### <a name="remarks"></a>설명

설정되는 범위는 [CMFCRibbonProgressBar::SetRange](#setrange) 메서드에서 지정한 범위 내에 있어야 합니다.

## <a name="cmfcribbonprogressbargetrangemax"></a><a name="getrangemax"></a>CMFC리본 진행률 바::겟레인지맥스

진행률 표시줄의 현재 최대값을 반환합니다.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Return Value

현재 범위의 최대값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribbonprogressbargetrangemin"></a><a name="getrangemin"></a>CMFC리본 진행률 표시줄::겟레인지민

진행률 표시줄의 현재 최소 범위 값을 반환합니다.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Return Value

현재 범위의 최소값입니다.

## <a name="cmfcribbonprogressbargetregularsize"></a><a name="getregularsize"></a>CMFC리본 진행률 표시줄::GetRegularsize

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonprogressbarisinfinitemode"></a><a name="isinfinitemode"></a>CMFC리본 진행률 표시줄::이무한모드

진행률 표시줄이 무한 모드에서 작동하는지 여부를 지정합니다.

```
BOOL IsInfiniteMode() const;
```

### <a name="return-value"></a>Return Value

진행률 표시줄이 무한 모드인 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

무한 모드에서 진행률 표시줄은 최소값에서 최대값까지 반복적으로 채워지습니다. 무한 모드를 사용하여 작업이 진행 중이지만 완료 시간을 알 수 없음을 나타낼 수 있습니다.

## <a name="cmfcribbonprogressbarondraw"></a><a name="ondraw"></a>CMFC리본 진행률 표시줄::온드로우

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcribbonprogressbarsetinfinitemode"></a><a name="setinfinitemode"></a>CMFC리본 진행률 표시줄::설정 무한모드

진행률 표시줄을 무한 모드에서 작동하도록 설정합니다.

```cpp
void SetInfiniteMode(BOOL bSet = TRUE);
```

### <a name="parameters"></a>매개 변수

*bSet*<br/>
【인】 진행률 표시줄이 무한 모드에 있음을 지정하는 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

일반적으로 진행률 표시줄이 무한 모드인 경우 사용자에게 작업이 진행 중이지만 완료 시간을 알 수 없음을 알려줍니다. 따라서 진행률 표시줄은 최소값에서 최대값까지 반복적으로 채워지다.

## <a name="cmfcribbonprogressbarsetpos"></a><a name="setpos"></a>CMFC리본 진행률 표시줄::세트포지

진행률 표시줄의 현재 위치를 설정합니다.

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
【인】 진행률 표시줄이 설정된 위치를 지정합니다.

*bRedraw*<br/>
【인】 진행률 표시줄을 다시 그려야 하는지 여부를 지정합니다.

### <a name="remarks"></a>설명

설정되는 범위는 [CMFCRibbonProgressBar::SetRange](#setrange) 메서드에서 지정한 범위 내에 있어야 합니다.

## <a name="cmfcribbonprogressbarsetrange"></a><a name="setrange"></a>CMFC리본 진행률 표시줄::설정 범위

진행률 표시줄의 최소값과 최대값을 설정합니다.

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
【인】 범위의 최소값을 지정합니다.

*nMax*<br/>
【인】 범위의 최대값을 지정합니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 최소 및 최대 값을 설정 하 여 진행률 막대의 범위를 정의 합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본베이스요소 클래스](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFC리본바 클래스](../../mfc/reference/cmfcribbonbar-class.md)
