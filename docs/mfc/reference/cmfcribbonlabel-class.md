---
title: CMFC리본라벨 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
ms.openlocfilehash: cd30e374441661368d3ea7abf5177424f8dffb3c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375130"
---
# <a name="cmfcribbonlabel-class"></a>CMFC리본라벨 클래스

리본에 대해 클릭할 수 없는 텍스트 레이블을 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC리본 라벨::CMFC리본 라벨](#cmfcribbonlabel)|지정된 텍스트 문자열을 `CMFCRibbonLabel` 가진 개체를 생성하고 초기화합니다.|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCRibbonLabel::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC 리본 라벨::세액데이터](#setaccdata)|현재 리본 레이블 요소에 대한 접근성 데이터를 결정합니다. [(CMFC 리본 단추 재정의::SetACCData.)](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata)|

### <a name="remarks"></a>설명

리본 레이블을 만든 후 [CMFCRibbonPanel::Add를](../../mfc/reference/cmfcribbonpanel-class.md#add)호출하여 패널에 추가합니다.

빠른 액세스 도구 모음에는 리본 레이블을 추가할 수 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonLabel.h

## <a name="cmfcribbonlabelcmfcribbonlabel"></a><a name="cmfcribbonlabel"></a>CMFC리본 라벨::CMFC리본 라벨

지정된 텍스트 문자열을 표시하는 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) 개체를 생성하고 초기화합니다.

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
【인】 레이블에 표시할 텍스트입니다.

*비스멀티라인*<br/>
【인】 TRUE 레이블이 다중 줄 레이블임을 지정합니다. 그렇지 않으면 false입니다.

## <a name="cmfcribbonlabelsetaccdata"></a><a name="setaccdata"></a>CMFC 리본 라벨::세액데이터

현재 리본 레이블 요소에 대한 접근성 데이터를 결정합니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
【인】 현재 리본 레이블의 상위 창을 나타냅니다.

*데이터*<br/>
【아웃】 현재 리본 `CAccessibilityData` 레이블의 접근성 데이터로 채워진 형식의 개체입니다.

### <a name="return-value"></a>Return Value

*TRUE 데이터* 매개 변수가 현재 리본 레이블의 내게 필요한 옵션 데이터로 성공적으로 채워진 경우; 그렇지 않으면 false입니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본버튼 클래스](../../mfc/reference/cmfcribbonbutton-class.md)
