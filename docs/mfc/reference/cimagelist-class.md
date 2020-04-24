---
title: CImageList 클래스
ms.date: 11/04/2016
f1_keywords:
- CImageList
- AFXCMN/CImageList
- AFXCMN/CImageList::CImageList
- AFXCMN/CImageList::Add
- AFXCMN/CImageList::Attach
- AFXCMN/CImageList::BeginDrag
- AFXCMN/CImageList::Copy
- AFXCMN/CImageList::Create
- AFXCMN/CImageList::DeleteImageList
- AFXCMN/CImageList::DeleteTempMap
- AFXCMN/CImageList::Detach
- AFXCMN/CImageList::DragEnter
- AFXCMN/CImageList::DragLeave
- AFXCMN/CImageList::DragMove
- AFXCMN/CImageList::DragShowNolock
- AFXCMN/CImageList::Draw
- AFXCMN/CImageList::DrawEx
- AFXCMN/CImageList::DrawIndirect
- AFXCMN/CImageList::EndDrag
- AFXCMN/CImageList::ExtractIcon
- AFXCMN/CImageList::FromHandle
- AFXCMN/CImageList::FromHandlePermanent
- AFXCMN/CImageList::GetBkColor
- AFXCMN/CImageList::GetDragImage
- AFXCMN/CImageList::GetImageCount
- AFXCMN/CImageList::GetImageInfo
- AFXCMN/CImageList::GetSafeHandle
- AFXCMN/CImageList::Read
- AFXCMN/CImageList::Remove
- AFXCMN/CImageList::Replace
- AFXCMN/CImageList::SetBkColor
- AFXCMN/CImageList::SetDragCursorImage
- AFXCMN/CImageList::SetImageCount
- AFXCMN/CImageList::SetOverlayImage
- AFXCMN/CImageList::Write
- AFXCMN/CImageList::m_hImageList
helpviewer_keywords:
- CImageList [MFC], CImageList
- CImageList [MFC], Add
- CImageList [MFC], Attach
- CImageList [MFC], BeginDrag
- CImageList [MFC], Copy
- CImageList [MFC], Create
- CImageList [MFC], DeleteImageList
- CImageList [MFC], DeleteTempMap
- CImageList [MFC], Detach
- CImageList [MFC], DragEnter
- CImageList [MFC], DragLeave
- CImageList [MFC], DragMove
- CImageList [MFC], DragShowNolock
- CImageList [MFC], Draw
- CImageList [MFC], DrawEx
- CImageList [MFC], DrawIndirect
- CImageList [MFC], EndDrag
- CImageList [MFC], ExtractIcon
- CImageList [MFC], FromHandle
- CImageList [MFC], FromHandlePermanent
- CImageList [MFC], GetBkColor
- CImageList [MFC], GetDragImage
- CImageList [MFC], GetImageCount
- CImageList [MFC], GetImageInfo
- CImageList [MFC], GetSafeHandle
- CImageList [MFC], Read
- CImageList [MFC], Remove
- CImageList [MFC], Replace
- CImageList [MFC], SetBkColor
- CImageList [MFC], SetDragCursorImage
- CImageList [MFC], SetImageCount
- CImageList [MFC], SetOverlayImage
- CImageList [MFC], Write
- CImageList [MFC], m_hImageList
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
ms.openlocfilehash: 17cd2a94cb397e59e4622aea8ed7bb6fbe1eee43
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752691"
---
# <a name="cimagelist-class"></a>CImageList 클래스

Windows의 공용 이미지 목록 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CImageList : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C이미지리스트::C이미지리스트](#cimagelist)|`CImageList` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C이미지리스트::추가](#add)|이미지 또는 이미지를 이미지 목록에 추가합니다.|
|[C이미지리스트::첨부](#attach)|이미지 목록을 개체에 `CImageList` 연결합니다.|
|[C이미지리스트::시작드래그](#begindrag)|이미지 끌기를 시작합니다.|
|[C이미지리스트::복사](#copy)|개체 내에서 이미지를 `CImageList` 복사합니다.|
|[C이미지리스트::만들기](#create)|이미지 목록을 초기화하고 `CImageList` 개체에 연결합니다.|
|[C이미지리스트::DeleteImageList](#deleteimagelist)|이미지 목록을 삭제합니다.|
|[C이미지리스트::DeleteTempMap](#deletetempmap)|[CWinApp](../../mfc/reference/cwinapp-class.md) 유휴 시간 처리기에서 호출하여 에서 만든 임시 `CImageList` 개체를 `FromHandle`삭제합니다.|
|[C이미지리스트::D에타치](#detach)|개체에서 이미지 목록 개체를 `CImageList` 분리 하고 이미지 목록에 핸들을 반환 합니다.|
|[C이미지리스트::D래그엔터](#dragenter)|끌기 작업 중에 업데이트를 잠그고 드래그 이미지를 지정된 위치에 표시합니다.|
|[C이미지리스트::D래그리브](#dragleave)|창을 잠금 해제하고 드래그 이미지를 숨겨 창을 업데이트할 수 있습니다.|
|[C이미지리스트::D래그무브](#dragmove)|끌어서 놓기 작업 중에 드래그되는 이미지를 이동합니다.|
|[C이미지리스트::D래그쇼놀록](#dragshownolock)|창을 잠그지 않고 드래그 작업 중에 드래그 이미지를 표시하거나 숨깁니다.|
|[C이미지리스트::D로](#draw)|끌어서 놓기 작업 중에 드래그되는 이미지를 그립니다.|
|[C이미지리스트::D로엑스](#drawex)|지정된 장치 컨텍스트에서 이미지 목록 항목을 그립니다. 이 함수는 지정된 그리기 스타일을 사용하고 이미지를 지정된 색상과 혼합합니다.|
|[C이미지리스트::D로직](#drawindirect)|이미지 목록에서 이미지를 그립니다.|
|[C이미지리스트::엔드드래그](#enddrag)|끌기 작업을 종료합니다.|
|[C이미지리스트::추출아이콘](#extracticon)|이미지 목록에서 이미지와 마스크를 기반으로 아이콘을 만듭니다.|
|[C이미지리스트::에서 핸들](#fromhandle)|이미지 목록에 핸들이 `CImageList` 지정되면 개체에 대한 포인터를 반환합니다. `CImageList` 개체가 핸들에 연결되지 않은 경우 임시 `CImageList` 개체를 만들어 연결합니다.|
|[C이미지리스트::에서핸들 영구](#fromhandlepermanent)|이미지 목록에 핸들이 `CImageList` 지정되면 개체에 대한 포인터를 반환합니다. 개체가 `CImageList` 핸들에 연결되지 않은 경우 NULL이 반환됩니다.|
|[C이미지리스트::겟비크컬러](#getbkcolor)|이미지 목록의 현재 배경색을 검색합니다.|
|[C이미지리스트::겟드래그이미지](#getdragimage)|드래그에 사용되는 임시 이미지 목록을 가져옵니다.|
|[C이미지리스트::겟이미지카운트](#getimagecount)|이미지 목록에서 이미지 수를 검색합니다.|
|[C이미지리스트::겟이미지정보](#getimageinfo)|이미지에 대 한 정보를 검색합니다.|
|[C이미지리스트::겟세이프핸들](#getsafehandle)|을 `m_hImageList`검색합니다.|
|[C이미지리스트::읽기](#read)|아카이브에서 이미지 목록을 읽습니다.|
|[C이미지리스트::제거](#remove)|이미지 목록에서 이미지를 제거합니다.|
|[C이미지리스트::바꾸기](#replace)|이미지 목록의 이미지를 새 이미지로 바꿉습니다.|
|[C이미지리스트::세트BkColor](#setbkcolor)|이미지 목록의 배경색을 설정합니다.|
|[C이미지리스트::세트드래그커서이미지](#setdragcursorimage)|새 드래그 이미지를 만듭니다.|
|[C이미지리스트::세트이미지카운트](#setimagecount)|이미지 목록에서 이미지 수를 재설정합니다.|
|[C이미지리스트::세트오버레이이미지](#setoverlayimage)|오버레이 마스크로 사용할 이미지 목록에 이미지의 0기반 인덱스를 추가합니다.|
|[C이미지리스트::쓰기](#write)|이미지 목록을 아카이브에 씁니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C이미지리스트::연산자 히마게리스트](#operator_himagelist)|에 첨부된 히마게리스트를 반환합니다. `CImageList`|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C이미지리스트:m_hImageList](#m_himagelist)|이 개체에 연결된 이미지 목록을 포함하는 핸들입니다.|

## <a name="remarks"></a>설명

"이미지 목록"은 동일한 크기의 이미지 모음으로, 각각 0기반 인덱스로 참조할 수 있습니다. 이미지 목록은 큰 아이콘 또는 비트맵 집합을 효율적으로 관리하는 데 사용됩니다. 이미지 목록의 모든 이미지는 화면 장치 형식의 단일 와이드 비트맵에 포함됩니다. 이미지 목록에는 이미지를 투명하게 그리는 데 사용되는 마스크가 포함된 흑백 비트맵도 포함될 수 있습니다(아이콘 스타일). Microsoft Win32 응용 프로그램 프로그래밍 인터페이스(API)는 이미지를 그리고, 이미지 목록을 만들고 삭제하고, 이미지를 추가 및 제거하고, 이미지를 바꾸고, 이미지를 병합하고, 이미지를 드래그할 수 있는 이미지 목록 기능을 제공합니다.

이 컨트롤(및 `CImageList` 따라서 클래스)은 Windows 95/98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

사용 `CImageList`방법에 대한 자세한 내용은 [컨트롤](../../mfc/controls-mfc.md) 및 [CImageList 사용](../../mfc/using-cimagelist.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CImageList`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="cimagelistadd"></a><a name="add"></a>C이미지리스트::추가

이 함수를 호출하여 하나 이상의 이미지 또는 아이콘을 이미지 목록에 추가합니다.

```
int Add(
    CBitmap* pbmImage,
    CBitmap* pbmMask);

int Add(
    CBitmap* pbmImage,
    COLORREF crMask);

int Add(HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*pbm이미지*<br/>
이미지 또는 이미지가 포함된 비트맵에 대한 포인터입니다. 이미지 수는 비트맵의 너비에서 유추됩니다.

*pbmMask*<br/>
마스크가 포함된 비트맵에 대한 포인터입니다. 이미지 목록에 마스크를 사용하지 않으면 이 매개 변수는 무시됩니다.

*crMask*<br/>
마스크를 생성하는 데 사용되는 색상입니다. 지정된 비트맵에서 이 색상의 각 픽셀이 검은색으로 변경되고 마스크의 해당 비트가 1로 설정됩니다.

*hIcon*<br/>
새 이미지에 대한 비트맵 및 마스크를 포함하는 아이콘의 핸들입니다.

### <a name="return-value"></a>Return Value

성공한 경우 첫 번째 새 이미지의 제로 기반 인덱스; 그렇지 않은 경우 - 1.

### <a name="remarks"></a>설명

아이콘 핸들을 완료하면 아이콘 핸들을 해제할 책임이 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]

## <a name="cimagelistattach"></a><a name="attach"></a>C이미지리스트::첨부

이 함수를 호출하여 이미지 `CImageList` 목록을 개체에 연결합니다.

```
BOOL Attach(HIMAGELIST hImageList);
```

### <a name="parameters"></a>매개 변수

*hImageList*<br/>
이미지 목록 개체에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

첨부 파일이 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]

## <a name="cimagelistbegindrag"></a><a name="begindrag"></a>C이미지리스트::시작드래그

이 함수를 호출하여 이미지 끌기를 시작합니다.

```
BOOL BeginDrag(
    int nImage,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
드래그할 이미지의 0기반 인덱스입니다.

*ptHotSpot*<br/>
시작 드래그 위치의 좌표(일반적으로 커서 위치). 좌표는 이미지의 왼쪽 위 모서리를 기준으로 합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 드래그에 사용되는 임시 이미지 목록을 만듭니다. 이미지는 지정된 이미지와 해당 마스크를 현재 커서와 결합합니다. 후속 WM_MOUSEMOVE 메시지에 대한 응답으로 `DragMove` 멤버 함수를 사용하여 드래그 이미지를 이동할 수 있습니다. 끌기 작업을 종료하려면 멤버 함수를 `EndDrag` 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]

## <a name="cimagelistcimagelist"></a><a name="cimagelist"></a>C이미지리스트::C이미지리스트

`CImageList` 개체를 생성합니다.

```
CImageList();
```

## <a name="cimagelistcopy"></a><a name="copy"></a>C이미지리스트::복사

이 멤버 함수는 Windows SDK에 설명된 대로 [ImageList_Copy](/windows/win32/api/commctrl/nf-commctrl-imagelist_copy)Win32 함수의 동작을 구현합니다.

```
BOOL Copy(
    int iDst,
    int iSrc,
    UINT uFlags = ILCF_MOVE);

BOOL Copy(
    int iDst,
    CImageList* pSrc,
    int iSrc,
    UINT uFlags = ILCF_MOVE);
```

### <a name="parameters"></a>매개 변수

*아이디스트*<br/>
복사 작업의 대상으로 사용할 이미지의 0기반 인덱스입니다.

*아이스터크 (동음이의)*<br/>
복사 작업의 소스로 사용할 이미지의 0기반 인덱스입니다.

*uFlags*<br/>
만들 복사 작업의 형식을 지정하는 비트 플래그 값입니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|ILCF_MOVE|원본 이미지가 대상 이미지의 인덱스에 복사됩니다. 이 작업을 수행하면 지정된 이미지의 여러 인스턴스가 생성됩니다. ILCF_MOVE 기본값입니다.|
|ILCF_SWAP|소스 이미지와 대상 이미지는 이미지 목록 내에서 위치를 교환합니다.|

*pSrc*<br/>
복사 작업의 `CImageList` 대상인 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]

## <a name="cimagelistcreate"></a><a name="create"></a>C이미지리스트::만들기

이미지 목록을 초기화하고 [CImageList](../../mfc/reference/cimagelist-class.md) 개체에 연결합니다.

```
BOOL Create(
    int cx,
    int cy,
    UINT nFlags,
    int nInitial,
    int nGrow);

BOOL Create(
    UINT nBitmapID,
    int cx,
    int nGrow,
    COLORREF crMask);

BOOL Create(
    LPCTSTR lpszBitmapID,
    int cx,
    int nGrow,
    COLORREF crMask);

BOOL Create(
    CImageList& imagelist1,
    int nImage1,
    CImageList& imagelist2,
    int nImage2,
    int dx,
    int dy);

BOOL Create(CImageList* pImageList);
```

### <a name="parameters"></a>매개 변수

*Cx*<br/>
픽셀 단위로 각 이미지의 치수입니다.

*Cy*<br/>
픽셀 단위로 각 이미지의 치수입니다.

*nFlags*<br/>
만들 이미지 목록의 유형을 지정합니다. 이 매개 변수는 다음 값의 조합일 수 있지만 `ILC_COLOR` 값 중 하나만 포함할 수 있습니다.

|값|의미|
|-----------|-------------|
|ILC_COLOR|다른 ILC_COLOR* 플래그가 지정되지 않은 경우 기본 동작을 사용합니다. 일반적으로 기본값은 ILC_COLOR4. 그러나 이전 디스플레이 드라이버의 경우 기본값은 ILC_COLORDDB.|
|ILC_COLOR4|4비트(16색) 장치 독립 비트맵(DIB) 섹션을 이미지 목록의 비트맵으로 사용합니다.|
|ILC_COLOR8|8비트 DIB 섹션을 사용합니다. 색상 표에 사용되는 색상은 하프톤 팔레트와 동일한 색상입니다.|
|ILC_COLOR16|16비트(32/64k 색상) DIB 섹션을 사용합니다.|
|ILC_COLOR24|24비트 DIB 섹션을 사용합니다.|
|ILC_COLOR32|32비트 DIB 섹션을 사용합니다.|
|ILC_COLORDDB|장치 종속 비트맵을 사용합니다.|
|ILC_MASK|마스크를 사용합니다. 이미지 목록에는 마스크로 사용되는 흑백 비트맵인 두 개의 비트맵이 포함되어 있습니다. 이 값이 포함되지 않은 경우 이미지 목록에 는 하나의 비트맵만 포함됩니다. 마스크된 이미지에 대한 자세한 내용은 [이미지 목록에서 이미지 그리기를](../../mfc/drawing-images-from-an-image-list.md) 참조하십시오.|

*n초기*<br/>
이미지 목록에 처음 포함된 이미지 수입니다.

*nGrow*<br/>
새 이미지를 위한 공간을 만들기 위해 목록의 크기를 조정해야 할 때 이미지 목록이 증가할 수 있는 이미지 수입니다. 이 매개 변수는 크기 조정된 이미지 목록에 포함할 수 있는 새 이미지 수를 나타냅니다.

*nBitmapID*<br/>
이미지 목록과 연결될 비트맵의 리소스 아이디입니다.

*crMask*<br/>
마스크를 생성하는 데 사용되는 색상입니다. 지정된 비트맵에서 이 색상의 각 픽셀이 검은색으로 변경되고 마스크의 해당 비트가 1로 설정됩니다.

*lpsz비트맵ID*<br/>
이미지의 리소스 아이디를 포함하는 문자열입니다.

*이미지 리스트1*<br/>
`CImageList` 개체에 대한 참조입니다.

*n이미지1*<br/>
첫 번째 기존 이미지의 인덱스입니다.

*이미지 리스트2*<br/>
`CImageList` 개체에 대한 참조입니다.

*n이미지2*<br/>
두 번째 기존 이미지의 인덱스입니다.

*Dx*<br/>
첫 번째 이미지와 관련하여 두 번째 이미지의 x축을 픽셀 단위로 오프셋합니다.

*Dy*<br/>
첫 번째 이미지와 관련하여 두 번째 이미지의 y축을 픽셀 단위로 오프셋합니다.

*pImageList*<br/>
`CImageList` 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 단계로 `CImageList` 구성합니다. 먼저 생성자 호출 한 `Create`다음 호출 `CImageList` 합니다 .

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]

## <a name="cimagelistdeleteimagelist"></a><a name="deleteimagelist"></a>C이미지리스트::DeleteImageList

이 함수를 호출하여 이미지 목록을 삭제합니다.

```
BOOL DeleteImageList();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]

## <a name="cimagelistdeletetempmap"></a><a name="deletetempmap"></a>C이미지리스트::DeleteTempMap

`CWinApp` 유휴 시간 처리기에 의해 `DeleteTempMap` 자동으로 호출되어 `CImageList` [FromHandle에서](#fromhandle)만든 임시 개체를 삭제하지만 `hImageList`개체와 `ImageList` 일시적으로 연결된 핸들() 은 삭제되지 않습니다.

```
static void PASCAL DeleteTempMap();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]

## <a name="cimagelistdetach"></a><a name="detach"></a>C이미지리스트::D에타치

이 함수를 호출하여 개체에서 이미지 `CImageList` 목록 개체를 분리합니다.

```
HIMAGELIST Detach();
```

### <a name="return-value"></a>Return Value

이미지 목록 개체에 대한 핸들입니다.

### <a name="remarks"></a>설명

이 함수는 이미지 목록 개체에 대한 핸들을 반환합니다.

### <a name="example"></a>예제

  [CImageList::연결](#attach)에 대한 예제를 참조하십시오.

## <a name="cimagelistdragenter"></a><a name="dragenter"></a>C이미지리스트::D래그엔터

끌기 작업 중에 *pWndLock에서* 지정한 창에 대한 업데이트를 잠그고 *점에*의해 지정된 위치에 드래그 이미지를 표시합니다.

```
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWndLock*<br/>
드래그 이미지를 소유하는 창에 대한 포인터입니다.

*지점*<br/>
드래그 이미지를 표시할 위치입니다. 좌표는 클라이언트 영역이 아닌 창의 왼쪽 위 모서리를 기준으로 합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

좌표는 창의 왼쪽 위 모서리를 기준으로 하므로 좌표를 지정할 때 테두리, 제목 표시줄 및 메뉴 막대와 같은 창 요소의 너비를 보정해야 합니다.

*pWndLock이* NULL인 경우 이 함수는 데스크톱 창과 연결된 디스플레이 컨텍스트에서 이미지를 그리고 좌표는 화면의 왼쪽 위 모서리를 기준으로 합니다.

이 함수는 끌기 작업 중에 지정된 창에 대한 다른 모든 업데이트를 잠그습니다. 드래그 앤 드롭 작업의 대상을 강조 표시하는 등 끌기 작업 중에 드로잉을 수행해야 하는 경우 [CImageList::DragLeave](#dragleave) 기능을 사용하여 드래그한 이미지를 일시적으로 숨길 수 있습니다.

### <a name="example"></a>예제

  [CImageList::BeginDrag](#begindrag)에 대한 예제를 참조하십시오.

## <a name="cimagelistdragleave"></a><a name="dragleave"></a>C이미지리스트::D래그리브

*pWndLock에서* 지정한 창을 잠금 해제하고 드래그 이미지를 숨겨 창을 업데이트할 수 있습니다.

```
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```

### <a name="parameters"></a>매개 변수

*pWndLock*<br/>
드래그 이미지를 소유하는 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  [CImageList::EndDrag](#enddrag)에 대한 예제를 참조하십시오.

## <a name="cimagelistdragmove"></a><a name="dragmove"></a>C이미지리스트::D래그무브

이 함수를 호출하여 끌어서 놓기 작업 중에 드래그되는 이미지를 이동합니다.

```
static BOOL PASCAL DragMove(CPoint pt);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
새 드래그 위치.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 WM_MOUSEMOVE 메시지에 대한 응답으로 호출됩니다. 끌기 작업을 시작하려면 멤버 `BeginDrag` 함수를 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]

## <a name="cimagelistdragshownolock"></a><a name="dragshownolock"></a>C이미지리스트::D래그쇼놀록

창을 잠그지 않고 드래그 작업 중에 드래그 이미지를 표시하거나 숨깁니다.

```
static BOOL PASCAL DragShowNolock(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
끌기 이미지를 표시할지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

[CImageList::DragEnter](#dragenter) 함수는 끌기 작업 중에 창에 대한 모든 업데이트를 잠그습니다. 그러나 이 함수는 창을 잠그지 않습니다.

## <a name="cimagelistdraw"></a><a name="draw"></a>C이미지리스트::D로

이 함수를 호출하여 끌어서 놓기 작업 중에 드래그되는 이미지를 그립니다.

```
BOOL Draw(
    CDC* pDC,
    int nImage,
    POINT pt,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
대상 장치 컨텍스트에 대한 포인터입니다.

*nImage*<br/>
그릴 이미지의 0 기반 인덱스입니다.

*pt*<br/>
지정된 장치 컨텍스트 내에서 그릴 위치입니다.

*nStyle*<br/>
도면 스타일을 지정하는 플래그입니다. 다음 값 중 하나 이상이 될 수 있습니다.

|값|의미|
|-----------|-------------|
|ILD_BLEND25, ILD_FOCUS|이미지를 그리며 25%를 시스템 강조 표시 색상과 혼합합니다. 이미지 목록에 마스크가 포함되어 있지 않으면 이 값은 영향을 주지 않습니다.|
|ILD_BLEND50, ILD_SELECTED, ILD_BLEND|이미지를 그리며 50%를 시스템 강조 표시 색상과 혼합합니다. 이미지 목록에 마스크가 포함되어 있지 않으면 이 값은 영향을 주지 않습니다.|
|ILD_MASK|마스크를 그립니다.|
|ILD_NORMAL|이미지 목록의 배경색을 사용하여 이미지를 그립니다. 배경색이 CLR_NONE 값인 경우 마스크를 사용하여 이미지가 투명하게 그려집니다.|
|ILD_TRANSPARENT|배경색에 관계없이 마스크를 사용하여 이미지를 투명하게 그립니다.|

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  [CImageList::SetOverlayImage](#setoverlayimage)에 대한 예제를 참조하십시오.

## <a name="cimagelistdrawex"></a><a name="drawex"></a>C이미지리스트::D로엑스

지정된 장치 컨텍스트에서 이미지 목록 항목을 그립니다.

```
BOOL DrawEx(
    CDC* pDC,
    int nImage,
    POINT pt,
    SIZE sz,
    COLORREF clrBk,
    COLORREF clrFg,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
대상 장치 컨텍스트에 대한 포인터입니다.

*nImage*<br/>
그릴 이미지의 0 기반 인덱스입니다.

*pt*<br/>
지정된 장치 컨텍스트 내에서 그릴 위치입니다.

*Sz*<br/>
이미지의 왼쪽 위 모서리를 기준으로 그리는 이미지 부분의 크기입니다. 윈도우 SDK에서 [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *DX와* *다이* 참조.

*clrBk*<br/>
이미지의 배경 색입니다. 윈도우 SDK에서 [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *rgbBk를* 참조하십시오.

*clrFg*<br/>
이미지의 전경 색상입니다. Windows SDK에서 [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *rgbFg를* 참조하십시오.

*nStyle*<br/>
도면 스타일을 지정하는 플래그입니다. windows SDK에서 [ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex) *fStyle을* 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 지정된 그리기 스타일을 사용하고 이미지를 지정된 색상과 혼합합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]

## <a name="cimagelistdrawindirect"></a><a name="drawindirect"></a>C이미지리스트::D로직

이 멤버 함수를 호출하여 이미지 목록에서 이미지를 그립니다.

```
BOOL DrawIndirect(IMAGELISTDRAWPARAMS* pimldp);

BOOL DrawIndirect(
    CDC* pDC,
    int nImage,
    POINT pt,
    SIZE sz,
    POINT ptOrigin,
    UINT fStyle = ILD_NORMAL,
    DWORD dwRop = SRCCOPY,
    COLORREF rgbBack = CLR_DEFAULT,
    COLORREF rgbFore = CLR_DEFAULT,
    DWORD fState = ILS_NORMAL,
    DWORD Frame = 0,
    COLORREF crEffect = CLR_DEFAULT);
```

### <a name="parameters"></a>매개 변수

*핌드 (핌)*<br/>
그리기 작업에 대한 정보가 포함된 [IMAGELISTDRAWPARAMS](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) 구조에 대한 포인터입니다.

*pDC*<br/>
대상 장치 컨텍스트에 대한 포인터입니다. 이 [CDC](../../mfc/reference/cdc-class.md) 개체를 완료하면 삭제해야 합니다.

*nImage*<br/>
그려질 이미지의 0기반 인덱스입니다.

*pt*<br/>
이미지가 그려질 x- 및 y-좌표를 포함하는 [POINT](/windows/win32/api/windef/ns-windef-point) 구조입니다.

*Sz*<br/>
그릴 이미지의 크기를 나타내는 [SIZE](/windows/win32/api/windef/ns-windef-size) 구조입니다.

*ptOrigin*<br/>
이미지 자체에 대해 드로잉 작업의 왼쪽 위 모서리를 지정하는 x-및 y 좌표를 포함하는 [POINT](/windows/win32/api/windef/ns-windef-point) 구조입니다. x 좌표의 왼쪽과 y 좌표 위에 있는 이미지의 픽셀은 그려지지 않습니다.

*f스타일*<br/>
드로잉 스타일과 선택적으로 오버레이 이미지를 지정하는 플래그를 지정합니다. 오버레이 이미지에 대한 자세한 내용은 비고 섹션을 참조하십시오. ILD_NORMAL MFC 기본 구현은 이미지 목록의 배경색을 사용하여 이미지를 그립니다. 배경색이 CLR_NONE 값인 경우 마스크를 사용하여 이미지가 투명하게 그려집니다.

다른 가능한 스타일은 [이미지리스트DRAWPARAMS](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) 구조의 *fStyle* 멤버 아래에 설명되어 있습니다.

*dwRop*<br/>
래스터 작업 코드를 지정하는 값입니다. 이러한 코드는 원본 사각형의 색상 데이터를 대상 사각형의 색상 데이터와 결합하여 최종 색상을 달성하는 방법을 정의합니다. MFC의 기본 구현인 SRCCOPY는 소스 사각형을 대상 사각형에 직접 복사합니다. *fStyle* 매개변수에 ILD_ROP 플래그가 포함되지 않은 경우 이 매개 변수는 무시됩니다.

다른 가능한 값은 [IMAGELISTDRAWPARAMS](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) 구조의 *dwRop* 멤버 아래에 설명되어 있습니다.

*rgbBack*<br/>
기본적으로 이미지 배경 색은 CLR_DEFAULT. 이 매개 변수는 응용 프로그램 정의 RGB 값 또는 다음 값 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|CLR_DEFAULT|기본 배경 색입니다. 이미지는 이미지 목록 배경 색을 사용하여 그려집니다.|
|CLR_NONE|배경색이 없습니다. 이미지가 투명하게 그려집니다.|

*rgbFore*<br/>
이미지 전경 색상은 기본적으로 CLR_DEFAULT. 이 매개 변수는 응용 프로그램 정의 RGB 값 또는 다음 값 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|CLR_DEFAULT|기본 전경 색상입니다. 이미지는 시스템 강조 표시 색상을 전경 색상으로 사용하여 그려집니다.|
|CLR_NONE|블렌드 색상이 없습니다. 이미지가 대상 장치 컨텍스트의 색상과 혼합됩니다.|

이 매개 변수는 *fStyle에* ILD_BLEND25 또는 ILD_BLEND50 플래그가 포함된 경우에만 사용됩니다.

*f상태*<br/>
도면 상태를 지정하는 플래그입니다. 이 멤버에는 하나 이상의 이미지 목록 상태 플래그가 포함될 수 있습니다.

*프레임*<br/>
포화 및 알파 블렌딩 효과의 동작에 영향을 줍니다.

ILS_SATURATE 함께 사용하면 이 멤버는 아이콘의 각 픽셀에 대해 RGB 삼중항의 각 색상 구성 요소에 추가되는 값을 보유합니다.

ILS_APLHA 함께 사용하면 이 멤버는 알파 채널의 값을 보유합니다. 이 값은 0에서 255까지, 0은 완전히 투명하고 255는 완전히 불투명할 수 있습니다.

*crEffect*<br/>
광선 및 그림자 효과에 사용되는 [COLORREF](/windows/win32/gdi/colorref) 값입니다.

### <a name="return-value"></a>Return Value

TRUE 이미지가 성공적으로 그려진 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

Win32 구조를 직접 채우려면 첫 번째 버전을 사용합니다. 하나 이상의 MFC의 기본 인수를 활용하거나 구조관리를 피하려면 두 번째 버전을 사용합니다.

오버레이 이미지는 *nImage* 매개 변수에 의해 이 멤버 함수에 지정된 기본 이미지 위에 그려진 이미지입니다. [INDEXTOOVERLAYMASK](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) 매크로를 사용하여 지정된 오버레이 마스크의 한 기반 인덱스와 함께 [그리기](#draw) 멤버 함수를 사용하여 오버레이 마스크를 그립니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]

## <a name="cimagelistenddrag"></a><a name="enddrag"></a>C이미지리스트::엔드드래그

끌기 작업을 종료하려면 이 함수를 호출합니다.

```
static void PASCAL EndDrag();
```

### <a name="remarks"></a>설명

끌기 작업을 시작하려면 멤버 `BeginDrag` 함수를 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]

## <a name="cimagelistextracticon"></a><a name="extracticon"></a>C이미지리스트::추출아이콘

이 함수를 호출하여 이미지 목록에서 이미지 및 관련 마스크를 기반으로 아이콘을 만듭니다.

```
HICON ExtractIcon(int nImage);
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
이미지의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

성공하면 아이콘을 처리합니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 메서드는 [ImageList_ExtractIcon](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon) 매크로의 동작에 의존 하여 아이콘을 만듭니다. 아이콘 만들기 및 정리에 대한 자세한 내용은 [ImageList_ExtractIcon](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon) 매크로를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]

## <a name="cimagelistfromhandle"></a><a name="fromhandle"></a>C이미지리스트::에서 핸들

이미지 목록에 핸들이 `CImageList` 지정되면 개체에 대한 포인터를 반환합니다.

```
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```

### <a name="parameters"></a>매개 변수

*hImageList*<br/>
이미지 목록을 지정합니다.

### <a name="return-value"></a>Return Value

성공한 경우 `CImageList` 개체에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

a가 `CImageList` 핸들에 아직 연결되어 있지 `CImageList` 않으면 임시 개체가 만들어지고 첨부됩니다. 이 `CImageList` 임시 개체는 다음에 응용 프로그램이 이벤트 루프에서 유휴 시간을 가지며 모든 임시 개체가 삭제될 때까지만 유효합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]

## <a name="cimagelistfromhandlepermanent"></a><a name="fromhandlepermanent"></a>C이미지리스트::에서핸들 영구

이미지 목록에 핸들이 `CImageList` 지정되면 개체에 대한 포인터를 반환합니다.

```
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```

### <a name="parameters"></a>매개 변수

*hImageList*<br/>
이미지 목록을 지정합니다.

### <a name="return-value"></a>Return Value

성공한 경우 `CImageList` 개체에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

개체가 `CImageList` 핸들에 연결되지 않은 경우 NULL이 반환됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]

## <a name="cimagelistgetbkcolor"></a><a name="getbkcolor"></a>C이미지리스트::겟비크컬러

이 함수를 호출하여 이미지 목록의 현재 배경색을 검색합니다.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Return Value

개체 배경 색의 `CImageList` RGB 색상 값입니다.

### <a name="example"></a>예제

  [CImageList::SetBkColor](#setbkcolor)에 대한 예제를 참조하십시오.

## <a name="cimagelistgetdragimage"></a><a name="getdragimage"></a>C이미지리스트::겟드래그이미지

드래그에 사용되는 임시 이미지 목록을 가져옵니다.

```
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,
    LPPOINT lpPointHotSpot);
```

### <a name="parameters"></a>매개 변수

*lpPoint*<br/>
현재 드래그 위치를 받는 [POINT](/windows/win32/api/windef/ns-windef-point) 구조의 주소입니다.

*lp포인트핫스팟*<br/>
드래그 위치를 `POINT` 기준으로 드래그 이미지의 오프셋을 받는 구조의 주소입니다.

### <a name="return-value"></a>Return Value

성공하면 드래그에 사용되는 임시 이미지 목록에 대한 포인터입니다. 그렇지 않으면 NULL이 됩니다.

## <a name="cimagelistgetimagecount"></a><a name="getimagecount"></a>C이미지리스트::겟이미지카운트

이 함수를 호출하여 이미지 목록에서 이미지 수를 검색합니다.

```
int GetImageCount() const;
```

### <a name="return-value"></a>Return Value

이미지 수입니다.

### <a name="example"></a>예제

  [CImageList::ExtractIcon에](#extracticon)대 한 예제를 참조 하십시오.

## <a name="cimagelistgetimageinfo"></a><a name="getimageinfo"></a>C이미지리스트::겟이미지정보

이 함수를 호출하여 이미지에 대한 정보를 검색합니다.

```
BOOL GetImageInfo(
    int nImage,
    IMAGEINFO* pImageInfo) const;
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
이미지의 0기반 인덱스입니다.

*p이미지정보*<br/>
이미지에 대한 정보를 받는 [IMAGEINFO](/windows/win32/api/commctrl/ns-commctrl-imageinfo) 구조에 대한 포인터입니다. 이 구조의 정보를 사용하여 이미지의 비트맵을 직접 조작할 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

구조에는 `IMAGEINFO` 이미지 목록의 이미지에 대한 정보가 포함되어 있습니다.

## <a name="cimagelistgetsafehandle"></a><a name="getsafehandle"></a>C이미지리스트::겟세이프핸들

이 함수를 호출하여 데이터 멤버를 검색합니다. `m_hImageList`

```
HIMAGELIST GetSafeHandle() const;
```

### <a name="return-value"></a>Return Value

첨부된 이미지 리스트에 대한 핸들; 그렇지 않으면 개체가 연결되지 않은 경우 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]

## <a name="cimagelistm_himagelist"></a><a name="m_himagelist"></a>C이미지리스트:m_hImageList

이 개체에 연결된 이미지 목록의 핸들입니다.

`HIMAGELIST m_hImageList;`

### <a name="remarks"></a>설명

`m_hImageList` 데이터 멤버는 HIMAGELIST 형식의 공용 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]

## <a name="cimagelistoperator-himagelist"></a><a name="operator_himagelist"></a>C이미지리스트::연산자 히마게리스트

이 연산자를 사용하여 개체의 연결된 핸들을 `CImageList` 가져옵니다.

```
operator HIMAGELIST() const;
```

### <a name="return-value"></a>Return Value

성공하면 개체로 표시되는 이미지 목록에 `CImageList` 대한 핸들입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 연산자는 HIMAGELIST 개체의 직접 사용을 지원하는 캐스팅 연산자입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]

## <a name="cimagelistread"></a><a name="read"></a>C이미지리스트::읽기

이 함수를 호출하여 아카이브에서 이미지 목록을 읽습니다.

```
BOOL Read(CArchive* pArchive);
```

### <a name="parameters"></a>매개 변수

*p아카이브*<br/>
이미지 목록을 `CArchive` 읽을 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]

## <a name="cimagelistremove"></a><a name="remove"></a>C이미지리스트::제거

이 함수를 호출하여 이미지 목록 개체에서 이미지를 제거합니다.

```
BOOL Remove(int nImage);
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
제거할 이미지의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

*이제 nImage* 다음에 있는 모든 항목이 한 위치로 이동합니다. 예를 들어 이미지 목록에 두 개의 항목이 포함된 경우 첫 번째 항목을 삭제하면 나머지 항목이 첫 번째 위치에 있게 됩니다. *n첫*번째 위치에 있는 항목에 대해 이미지 =0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]

## <a name="cimagelistreplace"></a><a name="replace"></a>C이미지리스트::바꾸기

이 함수를 호출하여 이미지 목록의 이미지를 새 이미지로 바꿉꿉입니다.

```
BOOL Replace(
    int nImage,
    CBitmap* pbmImage,
    CBitmap* pbmMask);

int Replace(
    int nImage,
    HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
대체할 이미지의 0기반 인덱스입니다.

*pbm이미지*<br/>
이미지를 포함하는 비트맵에 대한 포인터입니다.

*pbmMask*<br/>
마스크가 포함된 비트맵에 대한 포인터입니다. 이미지 목록에 마스크를 사용하지 않으면 이 매개 변수는 무시됩니다.

*hIcon*<br/>
새 이미지에 대한 비트맵 및 마스크를 포함하는 아이콘에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

BOOL을 반환하는 버전은 성공하면 0이 아닌 버전을 반환합니다. 그렇지 않으면 0.

**int를** 반환하는 버전은 성공하면 이미지의 0기반 인덱스를 반환합니다. 그렇지 않은 경우 - 1.

### <a name="remarks"></a>설명

[SetImageCount를](#setimagecount) 호출한 후 이 멤버 함수를 호출하여 자리 표시자 이미지 인덱스 번호에 유효한 새 이미지를 할당합니다.

### <a name="example"></a>예제

  [CImageList::SetImageCount](#setimagecount)에 대한 예제를 참조하십시오.

## <a name="cimagelistsetbkcolor"></a><a name="setbkcolor"></a>C이미지리스트::세트BkColor

이 함수를 호출하여 이미지 목록의 배경색을 설정합니다.

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>매개 변수

*Cr*<br/>
설정할 배경 색입니다. 그것은 CLR_NONE 수 있습니다. 이 경우 마스크를 사용하여 이미지가 투명하게 그려집니다.

### <a name="return-value"></a>Return Value

성공한 경우 이전 배경 색; 그렇지 않으면 CLR_NONE.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]

## <a name="cimagelistsetdragcursorimage"></a><a name="setdragcursorimage"></a>C이미지리스트::세트드래그커서이미지

지정된 이미지(일반적으로 마우스 커서 이미지)와 현재 드래그 이미지를 결합하여 새 드래그 이미지를 만듭니다.

```
BOOL SetDragCursorImage(
    int nDrag,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>매개 변수

*n드래그*<br/>
드래그 이미지와 결합할 새 이미지의 인덱스입니다.

*ptHotSpot*<br/>
새 이미지 내의 핫 스폿의 위치입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

끌기 함수는 끌기 작업 중에 새 이미지를 사용하기 때문에 Windows [ShowCursor](/windows/win32/api/winuser/nf-winuser-showcursor) 함수를 사용하여 호출 `CImageList::SetDragCursorImage`한 후 실제 마우스 커서를 숨겨야 합니다. 그렇지 않으면 드래그 작업 기간 동안 시스템에 두 개의 마우스 커서가 있는 것처럼 보일 수 있습니다.

## <a name="cimagelistsetimagecount"></a><a name="setimagecount"></a>C이미지리스트::세트이미지카운트

이 멤버 함수를 호출하여 개체의 `CImageList` 이미지 수를 재설정합니다.

```
BOOL SetImageCount(UINT uNewCount);
```

### <a name="parameters"></a>매개 변수

*uNewCount*<br/>
이미지 목록의 새 총 이미지 수를 지정하는 값입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 호출하여 이미지 목록의 이미지 수를 늘리려면 각 추가 이미지에 대해 새 인덱스를 유효한 이미지에 할당하려면 새 이미지에 대해 [바꾸기를](#replace) 호출합니다. 유효한 이미지에 인덱스를 할당하지 못하면 새 이미지를 만드는 그리기 작업을 예측할 수 없습니다.

이 함수를 사용하여 이미지 목록의 크기를 줄이면 잘린 이미지가 해제됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]

## <a name="cimagelistsetoverlayimage"></a><a name="setoverlayimage"></a>C이미지리스트::세트오버레이이미지

이 함수를 호출하여 오버레이 마스크로 사용할 이미지 목록에 이미지의 0기반 인덱스를 추가합니다.

```
BOOL SetOverlayImage(
    int nImage,
    int nOverlay);
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
오버레이 마스크로 사용할 이미지의 0기반 인덱스입니다.

*n오버레이*<br/>
오버레이 마스크의 한 기반 인덱스입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

최대 4개의 인덱스를 목록에 추가할 수 있습니다.

오버레이 마스크는 다른 이미지 위에 투명하게 그려진 이미지입니다. INDEXTOOVERLAYMASK 매크로를 사용하여 지정된 오버레이 마스크의 한 기반 인덱스가 있는 [CImageList::Draw](#draw) 멤버 함수를 사용하여 이미지 위에 오버레이 마스크를 그립니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]

## <a name="cimagelistwrite"></a><a name="write"></a>C이미지리스트::쓰기

이 함수를 호출하여 이미지 목록 개체를 아카이브에 작성합니다.

```
BOOL Write(CArchive* pArchive);
```

### <a name="parameters"></a>매개 변수

*p아카이브*<br/>
이미지 목록을 `CArchive` 저장할 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CListCtrl 클래스](../../mfc/reference/clistctrl-class.md)<br/>
[크탭터클래스](../../mfc/reference/ctabctrl-class.md)
