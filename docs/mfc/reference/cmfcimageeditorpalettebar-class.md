---
title: CMFCImageEditorPaletteBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::GetRowHeight
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable
helpviewer_keywords:
- CMFCImageEditorPaletteBar [MFC], GetRowHeight
- CMFCImageEditorPaletteBar [MFC], IsButtonExtraSizeAvailable
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
ms.openlocfilehash: 33d4bc0c72718d028031ac11bc67da6aec5e4907
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374420"
---
# <a name="cmfcimageeditorpalettebar-class"></a>CMFCImageEditorPaletteBar 클래스

이미지 편집기 대화 상자에 팔레트 표시줄 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CMFCImageEditorPaletteBar : public CMFCToolBar
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[CMFC이미지에디터팔레트바::겟로우높이트](#getrowheight)|도구 모음 단추의 높이를 반환합니다. [(CMFCToolBar 재정의::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFC이미지에디터팔레트바::이버튼엑스트라사이즈사용 가능](#isbuttonextrasizeavailable)|도구 모음에 테두리가 확장된 단추를 표시할 수 있는지 여부를 결정합니다. [(재정의 CMFCToolBar::IsButton추가 크기 초과 사용 가능.)](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable)|

### <a name="remarks"></a>설명

이 클래스는 사용자 코드에서 직접 사용할 수 없습니다.

프레임워크는 이 클래스를 사용하여 이미지 편집기 대화 상자에 팔레트 막대를 표시합니다. 이미지 편집기 대화 상자에 대한 자세한 내용은 [CMFCImageEditorDialog 클래스를](../../mfc/reference/cmfcimageeditordialog-class.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFC베이스툴바](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFC이미지에디터팔레트바](../../mfc/reference/cmfcimageeditorpalettebar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afximageeditordialog.h

## <a name="cmfcimageeditorpalettebargetrowheight"></a><a name="getrowheight"></a>CMFC이미지에디터팔레트바::겟로우높이트

도구 모음 단추의 높이를 반환합니다.

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Return Value

도구 모음의 각 단추의 높이입니다.

## <a name="cmfcimageeditorpalettebarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a>CMFC이미지에디터팔레트바::이버튼엑스트라사이즈사용 가능

도구 모음에 테두리가 확장된 단추를 표시할 수 있는지 여부를 결정합니다.

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Return Value

이 메서드는 FALSE를 반환합니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC이미지에디터디아로그 클래스](../../mfc/reference/cmfcimageeditordialog-class.md)
