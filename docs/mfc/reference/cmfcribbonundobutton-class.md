---
title: CMFC리본언도버튼 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
ms.openlocfilehash: 15cf93d39057f0e235779d47cf24d920d80a807d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753500"
---
# <a name="cmfcribbonundobutton-class"></a>CMFC리본언도버튼 클래스

클래스는 `CMFCRibbonUndoButton` 최신 사용자 명령을 포함하는 드롭다운 목록 단추를 구현합니다. 사용자는 드롭다운 목록에서 가장 최근 명령 중 하나 이상을 선택하여 다시 수행하거나 취소할 수 있습니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC리본언도버튼::CMFC리본언도버튼](#cmfcribbonundobutton)|부모 개체의 `CMFCRibbonUndoButton` 이미지 목록에서 지정한 명령 ID, 텍스트 레이블 및 이미지를 사용하여 새 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC 리본언도 버튼::추가 실행](#addundoaction)|작업 목록에 새 작업을 추가합니다.|
|[CMFC리본언도버튼::클린업언도리스트](#cleanupundolist)|드롭다운 목록인 작업 목록을 지웁습니다.|
|[CMFC리본언도버튼::겟액션넘버](#getactionnumber)|드롭다운 목록에서 선택한 항목 수를 결정합니다.|
|[CMFC리본언도버튼::하스메뉴](#hasmenu)|개체에 메뉴가 포함되어 있는지 여부를 나타냅니다.|

## <a name="remarks"></a>설명

클래스는 `CMFCRibbonUndoButton` 스택을 사용하여 드롭다운 목록을 나타냅니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonUndoButton` 클래스의 개체를 생성 하 고 작업 목록에 새 작업을 추가 하는 방법을 보여 줍니다. 이 코드 조각은 리본 [가젯 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribbonundobutton.h

## <a name="cmfcribbonundobuttonaddundoaction"></a><a name="addundoaction"></a>CMFC 리본언도 버튼::추가 실행

작업 목록에 새 작업을 추가합니다.

```cpp
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 드롭다운 목록에 표시될 작업 레이블입니다.

## <a name="cmfcribbonundobuttoncleanupundolist"></a><a name="cleanupundolist"></a>CMFC리본언도버튼::클린업언도리스트

드롭다운 목록인 작업 목록을 지웁습니다.

```cpp
void CleanUpUndoList();
```

## <a name="cmfcribbonundobuttoncmfcribbonundobutton"></a><a name="cmfcribbonundobutton"></a>CMFC리본언도버튼::CMFC리본언도버튼

부모 개체의 `CMFCRibbonUndoButton` 이미지 목록에서 지정한 명령 ID, 텍스트 레이블 및 이미지를 사용하여 새 개체를 생성합니다.

```
CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex=-1,
    int nLargeImageIndex=-1);

CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 명령 식별자를 지정합니다.

*lpszText*<br/>
【인】 단추의 텍스트 레이블을 지정합니다.

*n스몰 이미지 인덱스*<br/>
【인】 단추의 작은 이미지에 대 한 상위 개체의 이미지 목록에서 0 기반 인덱스입니다.

*nLarge이미지인덱스*<br/>
【인】 단추의 큰 이미지에 대 한 상위 개체의 이미지 목록에서 0 기반 인덱스입니다.

*hIcon*<br/>
【인】 단추의 이미지로 사용할 수 있는 아이콘의 핸들입니다.

## <a name="cmfcribbonundobuttongetactionnumber"></a><a name="getactionnumber"></a>CMFC리본언도버튼::겟액션넘버

드롭다운 목록에서 선택한 항목 수를 결정합니다.

```
int GetActionNumber() const;
```

### <a name="return-value"></a>Return Value

사용자가 선택한 항목 수입니다.

## <a name="cmfcribbonundobuttonhasmenu"></a><a name="hasmenu"></a>CMFC리본언도버튼::하스메뉴

개체에 메뉴가 포함되어 있는지 여부를 나타냅니다.

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>Return Value

항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본갤러리 클래스](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[CMFC리본버튼 클래스](../../mfc/reference/cmfcribbonbutton-class.md)
