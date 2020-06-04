---
title: CMFC리본갤러리메뉴버튼 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CopyFrom
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CreatePopupMenu
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::GetPalette
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::HasButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed
helpviewer_keywords:
- CMFCRibbonGalleryMenuButton [MFC], CMFCRibbonGalleryMenuButton
- CMFCRibbonGalleryMenuButton [MFC], CopyFrom
- CMFCRibbonGalleryMenuButton [MFC], CreatePopupMenu
- CMFCRibbonGalleryMenuButton [MFC], GetPalette
- CMFCRibbonGalleryMenuButton [MFC], HasButton
- CMFCRibbonGalleryMenuButton [MFC], IsEmptyMenuAllowed
ms.assetid: 4d459d9b-8b1a-4371-92f6-dc4ce6cc42c8
ms.openlocfilehash: 305393def3b176b052b1db89c66c1e755f528ee6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375136"
---
# <a name="cmfcribbongallerymenubutton-class"></a>CMFC리본갤러리메뉴버튼 클래스

리본 갤러리가 포함된 리본 메뉴 단추를 구현합니다.
자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCRibbonGalleryMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton](#cmfcribbongallerymenubutton)|`CMFCRibbonGalleryMenuButton` 개체를 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCRibbonGalleryMenuButton::CopyFrom](#copyfrom)|[(CMFCToolBar메뉴 단추 재정의::복사에서](../../mfc/reference/cmfctoolbarmenubutton-class.md#copyfrom)시작))|
|[CMFCRibbonGalleryMenuButton::CreatePopupMenu](#createpopupmenu)|[(CMFCToolBar메뉴 단추 재정의::만들기팝업 메뉴.)](../../mfc/reference/cmfctoolbarmenubutton-class.md#createpopupmenu)|
|[CMFCRibbonGalleryMenuButton::GetPalette](#getpalette)||
|[CMFCRibbonGalleryMenuButton::HasButton](#hasbutton)|( `CMFCToolBarMenuButton::HasButton`을 재정의합니다.)|
|[CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|[(재정의 CMFCToolBar메뉴 버튼::는빈메뉴허용.)](../../mfc/reference/cmfctoolbarmenubutton-class.md#isemptymenuallowed)|

### <a name="remarks"></a>설명

갤러리 메뉴 단추가 팝업 메뉴로 화살표와 함께 표시됩니다. 사용자가 이 단추를 클릭하면 이미지 갤러리가 표시됩니다. 갤러리 메뉴 단추를 생성하는 경우 이러한 이미지를 포함하는 이미지 목록을 지정해야 합니다.

## <a name="example"></a>예제

다음 예제에서는 메뉴 단추에 글머리 기호 갤러리를 표시하는 방법을 보여 줍니다.

```cpp
BOOL CMainFrame::OnShowPopupMenu (CMFCPopupMenu* pMenuPopup)
{
    int nBulletIndex = pMenuBar->CommandToIndex (ID_PARA_BULLETS);

    if (nBulletIndex>= 0)
    {
        CMFCToolBarButton* pExButton =
        pMenuBar->GetButton(nBulletIndex);
        ASSERT_VALID (pExButton);

        CMFCRibbonGalleryMenuButton paletteBullet (
        pExButton->m_nID,
        pExButton->GetImage (),
        pExButton->m_strText);

        InitBulletPalette (&paletteBullet.GetPalette ());

        pMenuBar->ReplaceButton (ID_PARA_BULLETS,
        paletteBullet);
    }
}
```

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[Cobject](../../mfc/reference/cobject-class.md)\
❏&nbsp;[CMFCToolBar 버튼](../../mfc/reference/cmfctoolbarbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CMFCToolBar메뉴버튼](../../mfc/reference/cmfctoolbarmenubutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;❏&nbsp;[CMFC리본갤러리메뉴버튼](../../mfc/reference/cmfcribbongallerymenubutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afx리본팔레트갤러리.h

## <a name="cmfcribbongallerymenubuttoncopyfrom"></a><a name="copyfrom"></a>CMFC리본 갤러리메뉴버튼::복사

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>매개 변수

【인】 *src*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcribbongallerymenubuttoncmfcribbongallerymenubutton"></a><a name="cmfcribbongallerymenubutton"></a>CMFC리본 갤러리메뉴버튼::CMFC리본갤러리메뉴버튼

[CMFC리본갤러리메뉴버튼을생성하고 초기화합니다.](../../mfc/reference/cmfcribbongallerymenubutton-class.md)

```
CMFCRibbonGalleryMenuButton(
    UINT uiID,
    int iImage,
    LPCTSTR lpszText,
    CMFCToolBarImages& imagesPalette);

CMFCRibbonGalleryMenuButton(
    UINT uiID,
    int iImage,
    LPCTSTR lpszText,
    UINT uiImagesPaletteResID = 0,
    int cxPaletteImage = 0);
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
단추의 명령 ID입니다. 사용자가 이 단추를 클릭할 때 WM_COMMAND 메시지에 전송되는 값입니다.

*아이 이미지*<br/>
갤러리 메뉴 버튼으로 표시할 이미지의 인덱스입니다. 이미지는 *이미지에 저장됩니다팔레트* 매개 변수.

*lpszText*<br/>
메뉴 단추에 표시할 텍스트입니다.

*이미지팔레트*<br/>
갤러리에 표시할 이미지 목록이 포함되어 있습니다.

*uiimages팔레트ResID*<br/>
갤러리에 표시할 이미지 목록의 리소스 ID입니다.

*cx팔레트이미지*<br/>
갤러리에 표시할 이미지의 픽셀 너비를 지정합니다.

### <a name="remarks"></a>설명

갤러리 메뉴 버튼은 화살표가 있는 팝업 메뉴로 표시됩니다. 사용자가 이 단추를 클릭하면 이미지 갤러리가 표시됩니다.

### <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonGalleryMenuButton` 클래스의 생성자 사용 방법을 보여 줍니다. 이 코드 조각은 MS [Office 2007 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#8](../../mfc/reference/codesnippet/cpp/cmfcribbongallerymenubutton-class_1.cpp)]

## <a name="cmfcribbongallerymenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a>CMFC리본 갤러리메뉴 버튼::만들기팝업 메뉴

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbongallerymenubuttongetpalette"></a><a name="getpalette"></a>CMFC리본 갤러리메뉴버튼::겟팔레트

```
CMFCRibbonGallery& GetPalette();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbongallerymenubuttonhasbutton"></a><a name="hasbutton"></a>CMFC리본 갤러리메뉴버튼::하스버튼

```
virtual BOOL HasButton() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbongallerymenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a>CMFC리본 갤러리메뉴버튼:빈메뉴 허용됨

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC툴바메뉴버튼 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[CMFC리본갤러리 클래스](../../mfc/reference/cmfcribbongallery-class.md)
