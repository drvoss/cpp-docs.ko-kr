---
title: 드래그리스트박스 클래스
ms.date: 11/04/2016
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
helpviewer_keywords:
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
ms.openlocfilehash: 0d1ae94948e1143a5bac17985423c4bd1bfbaf65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374039"
---
# <a name="cdraglistbox-class"></a>드래그리스트박스 클래스

이 클래스는 `CDragListBox` Windows 목록 상자의 기능을 제공하는 것 외에도 사용자가 목록 상자 내에서 파일 이름과 같은 목록 상자 항목을 이동할 수 있도록 합니다.

## <a name="syntax"></a>구문

```
class CDragListBox : public CListBox
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[드래그리스트 박스::드래그리스트박스](#cdraglistbox)|`CDragListBox` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDragList상자::시작드래그](#begindrag)|끌기 작업이 시작될 때 프레임워크에서 호출됩니다.|
|[CDragList상자::취소드래그](#canceldrag)|끌기 작업이 취소되었을 때 프레임워크에서 호출합니다.|
|[CDragList상자::D 래깅](#dragging)|끌기 작업 중에 프레임워크에서 호출합니다.|
|[CDragList상자::D로인더삽입](#drawinsert)|끌기 목록 상자의 삽입 가이드를 그립니다.|
|[CDragList상자::D](#dropped)|항목을 삭제한 후 프레임워크에서 호출합니다.|
|[CDragList상자::항목에서Pt](#itemfrompt)|드래그되는 항목의 좌표를 반환합니다.|

## <a name="remarks"></a>설명

이 기능을 갖춘 목록 상자를 사용하면 사용자가 가장 유용한 방식으로 목록에서 항목을 정렬할 수 있습니다. 기본적으로 목록 상자는 항목을 목록의 새 위치로 이동합니다. 그러나 `CDragListBox` 개체를 이동하는 대신 항목을 복사하도록 사용자 지정할 수 있습니다.

`CDragListBox` 클래스와 연결된 목록 상자 컨트롤에는 LBS_SORT 또는 LBS_MULTIPLESELECT 스타일이 없어야 합니다. 목록 상자 스타일에 대한 설명은 [목록 상자 스타일을](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)참조하십시오.

응용 프로그램의 기존 대화 상자에서 드래그 목록 상자를 사용하려면 대화 상자 편집기를 사용하여 대화 상자 컨트롤을 대화 상자에 추가한 다음 대화 상자 템플릿의 목록 상자 컨트롤에 해당하는 멤버 변수(범주 `Control` 및 변수 유형)를 `CDragListBox`할당합니다.

멤버 변수에 컨트롤 할당에 대한 자세한 내용은 [대화 상자 컨트롤에 대한 멤버 변수 정의에 대한 바로 가기를](../../windows/defining-member-variables-for-dialog-controls.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CDragListBox`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="cdraglistboxbegindrag"></a><a name="begindrag"></a>CDragList상자::시작드래그

왼쪽 마우스 단추를 누르는 등 끌기 작업을 시작할 수 있는 이벤트가 발생할 때 프레임워크에서 호출합니다.

```
virtual BOOL BeginDrag(CPoint pt);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
드래그되는 항목의 좌표를 포함하는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.

### <a name="return-value"></a>Return Value

드래그가 허용되는 경우 0이 아닌 0입니다.

### <a name="remarks"></a>설명

끌기 작업이 시작될 때 발생하는 작업을 제어하려면 이 함수를 재정의합니다. 기본 구현은 마우스를 캡처하고 사용자가 왼쪽 또는 오른쪽 마우스 단추를 클릭하거나 드래그 작업이 취소될 때 ESC를 누를 때까지 드래그 모드로 유지됩니다.

## <a name="cdraglistboxcanceldrag"></a><a name="canceldrag"></a>CDragList상자::취소드래그

끌기 작업이 취소되었을 때 프레임워크에서 호출합니다.

```
virtual void CancelDrag(CPoint pt);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
드래그되는 항목의 좌표를 포함하는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.

### <a name="remarks"></a>설명

목록 상자 컨트롤에 대한 특수 처리를 처리하려면 이 함수를 재정의합니다.

## <a name="cdraglistboxcdraglistbox"></a><a name="cdraglistbox"></a>드래그리스트 박스::드래그리스트박스

`CDragListBox` 개체를 생성합니다.

```
CDragListBox();
```

## <a name="cdraglistboxdragging"></a><a name="dragging"></a>CDragList상자::D 래깅

개체 내에서 목록 상자 항목을 끌 때 `CDragListBox` 프레임워크에서 호출합니다.

```
virtual UINT Dragging(CPoint pt);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
커서의 x 및 y 화면 좌표를 포함하는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.

### <a name="return-value"></a>Return Value

표시할 커서의 리소스 ID입니다. 다음 값이 가능합니다.

- DL_COPYCURSOR 항목이 복사될 것임을 나타냅니다.

- DL_MOVECURSOR 항목이 이동될 것임을 나타냅니다.

- DL_STOPCURSOR 현재 놓기 대상이 허용되지 않음을 나타냅니다.

### <a name="remarks"></a>설명

기본 동작은 DL_MOVECURSOR 반환합니다. 추가 기능을 제공하려는 경우 이 함수를 재정의합니다.

## <a name="cdraglistboxdrawinsert"></a><a name="drawinsert"></a>CDragList상자::D로인더삽입

표시된 인덱스가 있는 항목 앞에 삽입 가이드를 그리려면 프레임워크에서 호출합니다.

```
virtual void DrawInsert(int nItem);
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
삽입 점의 제로 기반 인덱스입니다.

### <a name="remarks"></a>설명

값 -1은 삽입 가이드를 지웁히 됩니다. 삽입 가이드의 모양이나 동작을 수정하려면 이 함수를 재정의합니다.

## <a name="cdraglistboxdropped"></a><a name="dropped"></a>CDragList상자::D

개체 내에서 항목을 삭제할 때 프레임워크에서 호출합니다. `CDragListBox`

```
virtual void Dropped(
    int nSrcIndex,
    CPoint pt);
```

### <a name="parameters"></a>매개 변수

*nSrc인덱스*<br/>
삭제된 문자열의 0기반 인덱스를 지정합니다.

*pt*<br/>
놓기 사이트의 좌표를 포함하는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.

### <a name="remarks"></a>설명

기본 비헤이비어는 목록 상자 항목과 해당 데이터를 새 위치로 복사한 다음 원래 항목을 삭제합니다. 이 함수를 재정의하여 목록 상자 항목의 복사본을 목록 내의 다른 위치로 드래그할 수 있도록 설정하는 등 기본 동작을 사용자 지정합니다.

## <a name="cdraglistboxitemfrompt"></a><a name="itemfrompt"></a>CDragList상자::항목에서Pt

*pt에*있는 목록 상자 항목의 0 기반 인덱스를 검색 하려면이 함수를 호출 합니다.

```
int ItemFromPt(
    CPoint pt,
    BOOL bAutoScroll = TRUE) const;
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
목록 상자 내의 점 좌표를 포함하는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.

*b 자동 스크롤*<br/>
스크롤이 허용되는 경우 0이 아닌 0입니다.

### <a name="return-value"></a>Return Value

드래그 목록 상자 항목의 0기반 인덱스입니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 TSTCON](../../overview/visual-cpp-samples.md)<br/>
[클리스박스 클래스](../../mfc/reference/clistbox-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클리스박스 클래스](../../mfc/reference/clistbox-class.md)
