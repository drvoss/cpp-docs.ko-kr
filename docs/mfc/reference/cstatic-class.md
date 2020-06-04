---
title: 정적 클래스
ms.date: 11/04/2016
f1_keywords:
- CStatic
- AFXWIN/CStatic
- AFXWIN/CStatic::CStatic
- AFXWIN/CStatic::Create
- AFXWIN/CStatic::DrawItem
- AFXWIN/CStatic::GetBitmap
- AFXWIN/CStatic::GetCursor
- AFXWIN/CStatic::GetEnhMetaFile
- AFXWIN/CStatic::GetIcon
- AFXWIN/CStatic::SetBitmap
- AFXWIN/CStatic::SetCursor
- AFXWIN/CStatic::SetEnhMetaFile
- AFXWIN/CStatic::SetIcon
helpviewer_keywords:
- CStatic [MFC], CStatic
- CStatic [MFC], Create
- CStatic [MFC], DrawItem
- CStatic [MFC], GetBitmap
- CStatic [MFC], GetCursor
- CStatic [MFC], GetEnhMetaFile
- CStatic [MFC], GetIcon
- CStatic [MFC], SetBitmap
- CStatic [MFC], SetCursor
- CStatic [MFC], SetEnhMetaFile
- CStatic [MFC], SetIcon
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
ms.openlocfilehash: e5c3705c0aa2fd90e73cb54ba5a97c252ed2cf83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371637"
---
# <a name="cstatic-class"></a>정적 클래스

Windows 정적 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CStatic : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[정전기::정적](#cstatic)|`CStatic` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CStatic::만들기](#create)|Windows 정적 컨트롤을 만들고 개체에 `CStatic` 연결합니다.|
|[정전기::D로상품](#drawitem)|소유자가 그린 정적 컨트롤을 그리려면 재정의합니다.|
|[CStatic::GetBitmap](#getbitmap)|SetBitmap을 사용하여 이전에 설정한 [비트맵](#setbitmap)의 핸들을 검색합니다.|
|[정결::GetCursor](#getcursor)|[SetCursor로](#setcursor)이전에 설정한 커서 이미지의 핸들을 검색합니다.|
|[정결::게센메타파일](#getenhmetafile)|[SetEnhMetaFile로](#setenhmetafile)이전에 설정한 향상된 메타파일의 핸들을 검색합니다.|
|[CStatic::Geticon](#geticon)|[SetIcon으로](#seticon)이전에 설정한 아이콘의 핸들을 검색합니다.|
|[CStatic::세트비트맵](#setbitmap)|정적 컨트롤에 표시할 비트맵을 지정합니다.|
|[정결::설정커서](#setcursor)|정적 컨트롤에 표시할 커서 이미지를 지정합니다.|
|[정적::세텐메타파일](#setenhmetafile)|정적 컨트롤에 표시할 향상된 메타파일을 지정합니다.|
|[정적::세티콘](#seticon)|정적 컨트롤에 표시할 아이콘을 지정합니다.|

## <a name="remarks"></a>설명

정적 컨트롤은 텍스트 문자열, 상자, 사각형, 아이콘, 커서, 비트맵 또는 향상된 메타파일을 표시합니다. 레이블을 지정하거나 상자에 표시하거나 다른 컨트롤을 분리하는 데 사용할 수 있습니다. 정적 컨트롤은 일반적으로 입력을 받지 않으며 출력을 제공하지 않습니다. 그러나 SS_NOTIFY 스타일로 만든 경우 마우스 클릭을 부모에게 알릴 수 있습니다.

두 단계로 정적 컨트롤을 만듭니다. 먼저 생성자 호출하여 개체를 `CStatic` 생성한 다음 [create](#create) member 함수를 호출하여 정적 `CStatic` 컨트롤을 만들고 개체에 연결합니다.

대화 상자 `CStatic` 내에서(대화 상자 리소스를 통해) 개체를 `CStatic` 만들면 사용자가 대화 상자를 닫을 때 개체가 자동으로 소멸됩니다.

창 내에서 `CStatic` 객체를 만드는 경우 객체를 삭제해야 할 수도 있습니다. 창 `CStatic` 내의 스택에 생성된 개체가 자동으로 소멸됩니다. 새 함수를 `CStatic` 사용하여 힙에 개체를 **new** 만드는 경우 개체에서 delete를 호출하여 개체를 완료할 때 **삭제해야** 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cstaticcreate"></a><a name="create"></a>CStatic::만들기

Windows 정적 컨트롤을 만들고 개체에 `CStatic` 연결합니다.

```
virtual BOOL Create(
    LPCTSTR lpszText,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID = 0xffff);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
컨트롤에 배치할 텍스트를 지정합니다. NULL이면 텍스트가 표시되지 않습니다.

*dwStyle*<br/>
정적 컨트롤의 창 스타일을 지정합니다. 정적 제어 [스타일의](../../mfc/reference/styles-used-by-mfc.md#static-styles) 조합을 컨트롤에 적용합니다.

*rect*<br/>
정적 컨트롤의 위치와 크기를 지정합니다. 구조체 `RECT` 또는 개체일 `CRect` 수 있습니다.

*pParentWnd*<br/>
`CStatic` 부모 창(일반적으로 개체)을 `CDialog` 지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
정적 컨트롤의 제어 ID를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 `CStatic` 단계로 개체를 생성합니다. 먼저 생성자 `CStatic`를 호출 한 `Create`다음 호출 `CStatic` 합니다 .

정적 컨트롤에 다음 [창 스타일을](../../mfc/reference/styles-used-by-mfc.md#window-styles) 적용합니다.

- 항상 WS_CHILD

- WS_VISIBLE 보통

- WS_DISABLED 드물게

정적 컨트롤에 비트맵, 커서, 아이콘 또는 메타파일을 표시하려면 다음 [정적 스타일](../../mfc/reference/styles-used-by-mfc.md#static-styles)중 하나를 적용해야 합니다.

- SS_BITMAP 비트맵에 이 스타일을 사용합니다.

- SS_ICON 커서 및 아이콘에 이 스타일을 사용합니다.

- SS_ENHMETAFILE 향상된 메타 파일에 이 스타일을 사용합니다.

커서, 비트맵 또는 아이콘의 경우 다음 스타일을 사용할 수도 있습니다.

- SS_CENTERIMAGE 정적 컨트롤에서 이미지를 가운데에 있는 데 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

## <a name="cstaticcstatic"></a><a name="cstatic"></a>정전기::정적

`CStatic` 개체를 생성합니다.

```
CStatic();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

## <a name="cstaticdrawitem"></a><a name="drawitem"></a>정전기::D로상품

소유자가 그린 정적 컨트롤을 그리는 프레임워크에서 호출합니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
[DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조에 대한 포인터입니다. 구조에는 그릴 항목과 필요한 도면 유형에 대한 정보가 포함되어 있습니다.

### <a name="remarks"></a>설명

이 함수를 재정의하여 소유자가 그린 `CStatic` 객체에 대한 그리기를 구현합니다(컨트롤에 스타일 SS_OWNERDRAW 있음).

## <a name="cstaticgetbitmap"></a><a name="getbitmap"></a>CStatic::GetBitmap

에 연결된 [SetBitmap으로](#setbitmap)이전에 설정된 비트맵의 핸들을 `CStatic`가져옵니다.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Return Value

비트맵이 설정되지 않은 경우 현재 비트맵에 대한 핸들 또는 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

## <a name="cstaticgetcursor"></a><a name="getcursor"></a>정결::GetCursor

에 연결된 [SetCursor로](#setcursor)이전에 설정된 커서의 핸들을 `CStatic`가져옵니다.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Return Value

커서가 설정되지 않은 경우 현재 커서또는 NULL에 대한 핸들입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

## <a name="cstaticgetenhmetafile"></a><a name="getenhmetafile"></a>정결::게센메타파일

`CStatic`에 연결된 [SetEnhMetafile으로](#setenhmetafile)이전에 설정된 향상된 메타파일의 핸들을 가져옵니다.

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>Return Value

향상된 메타파일이 설정되지 않은 경우 현재 향상된 메타파일 또는 NULL에 대한 핸들입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

## <a name="cstaticgeticon"></a><a name="geticon"></a>CStatic::Geticon

에 연결된 [SetIcon으로](#seticon)이전에 설정한 아이콘의 핸들을 `CStatic`가져옵니다.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Return Value

현재 아이콘에 대한 핸들 또는 아이콘이 설정되지 않은 경우 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="cstaticsetbitmap"></a><a name="setbitmap"></a>CStatic::세트비트맵

새 비트맵을 정적 컨트롤과 연결합니다.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>매개 변수

*hBitmap*<br/>
정적 컨트롤에 그려질 비트맵의 핸들입니다.

### <a name="return-value"></a>Return Value

비트맵이 정적 컨트롤과 연관되지 않은 경우 이전에 정적 제어 또는 NULL과 연결되었던 비트맵의 핸들입니다.

### <a name="remarks"></a>설명

비트맵은 정적 컨트롤에 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 그려지고 정적 컨트롤의 크기가 비트맵 크기로 조정됩니다.

다음과 같은 다양한 창 및 정적 제어 스타일을 사용할 수 있습니다.

- SS_BITMAP 항상 비트맵에 이 스타일을 사용합니다.

- SS_CENTERIMAGE 정적 컨트롤에서 이미지를 가운데에 있는 데 사용합니다. 이미지가 정적 컨트롤보다 크면 잘립니다. 정적 컨트롤보다 작으면 이미지 주위의 빈 공간이 비트맵의 왼쪽 위 모서리에 있는 픽셀의 색상으로 채워집니다.

- MFC는 Win32 함수를 `CBitmap` `LoadBitmap`호출하는 것보다 비트맵 이미지로 더 많은 작업을 수행해야 할 때 사용할 수 있는 클래스를 제공합니다. `CBitmap`한 종류의 GDI 개체를 포함하는 것은 그래픽 `CStatic`개체를 정적 `CWnd` 컨트롤로 표시하는 데 사용되는 클래스인 와 협력하여 자주 사용됩니다.

`CImage`는 장치 독립 비트맵(DIB)으로 보다 쉽게 작업할 수 있는 ATL/MFC 클래스입니다. 자세한 내용은 [CImage 클래스](../../atl-mfc-shared/reference/cimage-class.md)를 참조하십시오.

- 일반적인 용도는 `CStatic::SetBitmap` `CBitmap` 또는 `CImage` 개체의 HBITMAP 연산자에서 반환되는 GDI 개체를 제공하는 것입니다. 이 작업을 수행하는 코드는 다음 줄과 유사합니다.

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```

다음 예제는 `CStatic` 힙에 두 개의 개체를 만듭니다. 그런 다음 을 사용하는 `CBitmap::LoadOEMBitmap` 시스템 비트맵과 다른 비트맵을 사용하여 `CImage::Load`파일을 로드합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

## <a name="cstaticsetcursor"></a><a name="setcursor"></a>정결::설정커서

새 커서 이미지를 정적 컨트롤과 연결합니다.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>매개 변수

*hCursor*<br/>
정적 컨트롤에 그려질 커서의 핸들입니다.

### <a name="return-value"></a>Return Value

정적 컨트롤과 연결된 커서의 핸들 또는 정적 컨트롤과 연결된 커서가 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

커서는 정적 컨트롤에 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 그려지고 정적 컨트롤의 크기는 커서 크기로 조정됩니다.

다음과 같은 다양한 창 및 정적 제어 스타일을 사용할 수 있습니다.

- SS_ICON 커서 및 아이콘에 항상 이 스타일을 사용합니다.

- SS_CENTERIMAGE 정적 컨트롤의 가운데에 사용합니다. 이미지가 정적 컨트롤보다 크면 잘립니다. 정적 컨트롤보다 작으면 이미지 주변의 빈 공간이 정적 컨트롤의 배경색으로 채워집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

## <a name="cstaticsetenhmetafile"></a><a name="setenhmetafile"></a>정적::세텐메타파일

새로운 향상된 메타파일 이미지를 정적 컨트롤과 연결합니다.

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>매개 변수

*h메타파일*<br/>
정적 컨트롤에 그려질 향상된 메타파일의 핸들입니다.

### <a name="return-value"></a>Return Value

이전에 정적 제어와 연관된 향상된 메타파일의 핸들 또는 향상된 메타파일이 정적 제어와 연결되지 않은 경우 NULL입니다.

### <a name="remarks"></a>설명

향상된 메타파일은 정적 컨트롤에 자동으로 그려집니다. 향상된 메타파일은 정적 제어의 크기에 맞게 조정됩니다.

다음과 같은 다양한 창 및 정적 제어 스타일을 사용할 수 있습니다.

- SS_ENHMETAFILE 향상된 메타 파일에 항상 이 스타일을 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

## <a name="cstaticseticon"></a><a name="seticon"></a>정적::세티콘

새 아이콘 이미지를 정적 컨트롤과 연결합니다.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*hIcon*<br/>
정적 컨트롤에 그려질 아이콘의 핸들입니다.

### <a name="return-value"></a>Return Value

정적 컨트롤과 연결된 아이콘 또는 정적 컨트롤과 연결된 아이콘이 없는 경우 NULL의 핸들입니다.

### <a name="remarks"></a>설명

아이콘은 정적 컨트롤에 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 그려지고 정적 컨트롤의 크기는 아이콘 크기로 조정됩니다.

다음과 같은 다양한 창 및 정적 제어 스타일을 사용할 수 있습니다.

- SS_ICON 커서 및 아이콘에 항상 이 스타일을 사용합니다.

- SS_CENTERIMAGE 정적 컨트롤의 가운데에 사용합니다. 이미지가 정적 컨트롤보다 크면 잘립니다. 정적 컨트롤보다 작으면 이미지 주변의 빈 공간이 정적 컨트롤의 배경색으로 채워집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="see-also"></a>참고 항목

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit 클래스](../../mfc/reference/cedit-class.md)<br/>
[클리스박스 클래스](../../mfc/reference/clistbox-class.md)<br/>
[C스크롤바 클래스](../../mfc/reference/cscrollbar-class.md)<br/>
[클리언로그 클래스](../../mfc/reference/cdialog-class.md)
