---
title: CMFC리본체크박스 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetCompactSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetIntermediateSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetRegularSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::IsDrawTooltipImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDraw
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawMenuImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawOnList
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::SetACCData
helpviewer_keywords:
- CMFCRibbonCheckBox [MFC], CMFCRibbonCheckBox
- CMFCRibbonCheckBox [MFC], GetCompactSize
- CMFCRibbonCheckBox [MFC], GetIntermediateSize
- CMFCRibbonCheckBox [MFC], GetRegularSize
- CMFCRibbonCheckBox [MFC], IsDrawTooltipImage
- CMFCRibbonCheckBox [MFC], OnDraw
- CMFCRibbonCheckBox [MFC], OnDrawMenuImage
- CMFCRibbonCheckBox [MFC], OnDrawOnList
- CMFCRibbonCheckBox [MFC], SetACCData
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
ms.openlocfilehash: 089c8056afebef31ff98a435bf145566ae64fe1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375261"
---
# <a name="cmfcribboncheckbox-class"></a>CMFC리본체크박스 클래스

`CMFCRibbonCheckBox` 클래스는 리본 패널, 빠른 실행 도구 모음 또는 팝업 메뉴에 추가할 수 있는 확인란을 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonCheckBox : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|[(CMFC 리본 단추 재정의::GetCompactSize.)](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize)|
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|[(CMFC 리본 단추 재정의::GetintermediateSize.)](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize)|
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|[(CMFC 리본 단추 재정의::GetRegularSize.)](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize)|
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|( `CMFCRibbonButton::IsDrawTooltipImage`을 재정의합니다.)|
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|[(CMFC 리본 단추 재정의::온드로우.)](../../mfc/reference/cmfcribbonbutton-class.md#ondraw)|
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|[(CMFC 리본베이스 요소 재정의::온드로우 메뉴이미지.)](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage)|
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|( `CMFCRibbonButton::OnDrawOnList`을 재정의합니다.)|
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|[(CMFC 리본 단추 재정의::SetACCData.)](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata)|

## <a name="remarks"></a>설명

애플리케이션에서 `CMFCRibbonCheckBox`를 사용하려면 코드에 다음 생성자를 추가합니다.

```
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)
```

*여기서 nID는* 확인란 명령 ID이고 *lpszText는* 확인란의 텍스트 레이블입니다.

[CMFC리본 패널::Add를](../../mfc/reference/cmfcribbonpanel-class.md#add)사용하여 리본 패널에 확인란을 추가할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribbon체크박스.h

## <a name="cmfcribboncheckboxcmfcribboncheckbox"></a><a name="cmfcribboncheckbox"></a>CMFC리본 체크박스::CMFC리본체크박스

리본 확인란 개체의 생성자

```
CMFCRibbonCheckBox(
    UINT nID,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 명령 ID를 지정합니다.

*lpszText*<br/>
【인】 텍스트 레이블을 지정합니다.

### <a name="return-value"></a>Return Value

리본 확인란 개체를 생성합니다.

### <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonCheckBox` 클래스의 개체를 생성 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]

## <a name="cmfcribboncheckboxgetcompactsize"></a><a name="getcompactsize"></a>CMFC리본 체크박스::겟컴팩트사이즈

재정의하면 확인란의 컴팩트한 크기를 가져옵니다.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 확인란과 연결된 CDC에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

확인란의 컴팩트한 `CSize` 크기를 포함하는 개체를 반환합니다.

### <a name="remarks"></a>설명

재정의하지 않으면 확인란의 중간 크기를 반환합니다.

## <a name="cmfcribboncheckboxgetintermediatesize"></a><a name="getintermediatesize"></a>CMFC 리본 체크 박스 :: Getintermediatesize크기

확인란의 중간 크기를 가져옵니다.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 이 확인란과 연결된 CDC에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

확인란의 중간 크기를 포함하는 `CSize` 개체입니다.

### <a name="remarks"></a>설명

재정의하지 않으면 중간 크기를 기본 확인란 크기() `AFX_CHECK_BOX_DEFAULT_SIZE`및 텍스트 크기 및 여백으로 계산합니다.

## <a name="cmfcribboncheckboxgetregularsize"></a><a name="getregularsize"></a>CMFC 리본 체크 박스 ::GetRegularsize

확인란의 일반 크기를 가져옵니다.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 이 확인란과 연결된 CDC 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

확인란의 `CSize` 일반 크기를 포함하는 개체를 반환합니다.

### <a name="remarks"></a>설명

재정의하지 않으면 확인란의 중간 크기를 반환합니다.

## <a name="cmfcribboncheckboxisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a>CMFC 리본 확인란::이스드툴팁이미지

확인란과 연결된 툴팁 이미지가 있는지 여부를 나타냅니다.

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Return Value

확인란과 연결된 도구 설명 이미지가 있는 경우 TRUE를 반환하거나 그렇지 않은 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboncheckboxondraw"></a><a name="ondraw"></a>CMFC 리본 체크 박스 ::에 그리기

지정된 장치 컨텍스트를 사용하여 확인란을 그리는 프레임워크에서 호출합니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 확인란을 그릴 CDC에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboncheckboxondrawmenuimage"></a><a name="ondrawmenuimage"></a>CMFC 리본 체크 박스::온드로우 메뉴이미지

확인란에 대한 메뉴 이미지를 그리는 프레임워크에서 호출됩니다.

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>매개 변수

【인】 *CDC&#42;*<br/>
확인란과 연결된 CDC에 대한 포인터입니다.

*CRect*<br/>
【인】 메뉴 `CRect` 이미지를 그릴 사각형을 지정하는 개체입니다.

### <a name="return-value"></a>Return Value

이미지가 그려진 경우 TRUE를 반환하거나 그렇지 않은 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

재정의하지 않으면 FALSE를 반환합니다.

## <a name="cmfcribboncheckboxondrawonlist"></a><a name="ondrawonlist"></a>CMFC리본 체크박스::온드로우온리스트

명령 목록 상자에 확인란을 그리는 프레임 워크에 의해 호출 됩니다.

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 확인란을 그릴 장치 컨텍스트에 대한 포인터입니다.

*strText*<br/>
【인】 표시 텍스트입니다.

*nTextOffset*<br/>
【인】 목록 상자의 왼쪽에서 표시 텍스트까지의 거리(픽셀 단위)입니다.

*rect*<br/>
【인】 확인란의 표시 사각형입니다.

*bIsSelected*<br/>
【인】 확인란이 선택된 경우 TRUE, 그렇지 않은 경우 FALSE입니다.

*b 강조 표시*<br/>
【인】 확인란이 강조 표시된 경우 TRUE, 그렇지 않은 경우 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboncheckboxsetaccdata"></a><a name="setaccdata"></a>CMFC 리본 확인란::설정ACC데이터

확인란에 대한 접근성 데이터를 설정합니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
확인란의 상위 창입니다.

*데이터*<br/>
확인란의 접근성 데이터입니다.

### <a name="return-value"></a>Return Value

항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 확인란에 대한 내게 필요한 옵션 데이터를 설정하고 항상 TRUE를 반환합니다. 내게 필요한 옵션 데이터를 설정하고 성공 또는 실패를 나타내는 값을 반환하려면 이 메서드를 재정의합니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본패널 클래스](../../mfc/reference/cmfcribbonpanel-class.md)
