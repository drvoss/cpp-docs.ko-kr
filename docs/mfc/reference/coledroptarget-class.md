---
title: 콜레드롭타겟 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDropTarget
- AFXOLE/COleDropTarget
- AFXOLE/COleDropTarget::COleDropTarget
- AFXOLE/COleDropTarget::OnDragEnter
- AFXOLE/COleDropTarget::OnDragLeave
- AFXOLE/COleDropTarget::OnDragOver
- AFXOLE/COleDropTarget::OnDragScroll
- AFXOLE/COleDropTarget::OnDrop
- AFXOLE/COleDropTarget::OnDropEx
- AFXOLE/COleDropTarget::Register
- AFXOLE/COleDropTarget::Revoke
helpviewer_keywords:
- COleDropTarget [MFC], COleDropTarget
- COleDropTarget [MFC], OnDragEnter
- COleDropTarget [MFC], OnDragLeave
- COleDropTarget [MFC], OnDragOver
- COleDropTarget [MFC], OnDragScroll
- COleDropTarget [MFC], OnDrop
- COleDropTarget [MFC], OnDropEx
- COleDropTarget [MFC], Register
- COleDropTarget [MFC], Revoke
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
ms.openlocfilehash: 01eb277da029d06ee44d8e048cf3244f4371a9ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375002"
---
# <a name="coledroptarget-class"></a>콜레드롭타겟 클래스

창과 OLE 라이브러리 사이의 통신 메커니즘을 제공합니다.

## <a name="syntax"></a>구문

```
class COleDropTarget : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레드롭타겟::콜레드롭타겟](#coledroptarget)|`COleDropTarget` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[콜레드롭 타겟::온드래그엔터](#ondragenter)|커서가 창에 처음 들어올 때 호출됩니다.|
|[콜레드롭 타겟::온드래그리브](#ondragleave)|커서를 창 밖으로 끌 때 호출됩니다.|
|[콜레드롭 타겟::온드래그오버](#ondragover)|창 위로 커서를 끌 때 반복적으로 호출됩니다.|
|[콜레드롭타겟::온드래그스크롤](#ondragscroll)|커서가 창의 스크롤 영역으로 드래그되는지 여부를 결정하기 위해 호출됩니다.|
|[콜레드롭 타겟::드롭 드롭](#ondrop)|데이터가 창에 삭제될 때 호출되는 기본 처리기입니다.|
|[콜레드롭 타겟::온드롭엑스](#ondropex)|데이터가 창에 삭제될 때 호출되는 초기 처리기입니다.|
|[COleDropTarget::레지스터](#register)|창을 유효한 놓기 대상으로 등록합니다.|
|[콜레드롭타겟::해지](#revoke)|창이 유효한 놓기 대상이 되지 않게 합니다.|

## <a name="remarks"></a>설명

이 클래스의 개체를 만들면 창에서 OLE 끌어서 놓기 메커니즘을 통해 데이터를 받아들일 수 있습니다.

drop 명령을 허용하는 창을 얻으려면 먼저 `COleDropTarget` 클래스의 개체를 만든 다음 원하는 `CWnd` 개체에 대한 포인터를 사용하여 [Register](#register) 함수를 유일한 매개 변수로 호출해야 합니다.

OLE를 사용한 끌어서 놓기 작업에 대한 자세한 내용은 [OLE 끌어서 놓기](../../mfc/drag-and-drop-ole.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropTarget`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="coledroptargetcoledroptarget"></a><a name="coledroptarget"></a>콜레드롭타겟::콜레드롭타겟

클래스의 `COleDropTarget`개체를 생성합니다.

```
COleDropTarget();
```

### <a name="remarks"></a>설명

이 개체를 창과 연결하려면 [등록을](#register) 호출합니다.

## <a name="coledroptargetondragenter"></a><a name="ondragenter"></a>콜레드롭 타겟::온드래그엔터

커서를 창으로 처음 드래그할 때 프레임워크에서 호출됩니다.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서가 입력하는 창을 가리킵니다.

*pDataObject*<br/>
삭제할 수 있는 데이터가 포함된 데이터 개체를 가리킵니다.

*dwKeyState*<br/>
수정자 키의 상태를 포함합니다. 이는 MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON 및 MK_RBUTTON 여러 가지 조합입니다.

*지점*<br/>
클라이언트 좌표에서 커서의 현재 위치를 포함합니다.

### <a name="return-value"></a>Return Value

*포인트에*의해 지정된 위치에서 드롭을 시도한 경우 발생하는 효과입니다. 다음 중 하나 이상이 될 수 있습니다.

- DROPEFFECT_NONE 한 방울은 허용되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행됩니다.

- DROPEFFECT_LINK 삭제된 데이터에서 원본 데이터에 대한 링크가 설정됩니다.

- DROPEFFECT_SCROLL 드래그 스크롤 작업이 발생하려고 하거나 대상에서 발생 합니다.

### <a name="remarks"></a>설명

이 함수를 재정의하여 창에서 놓기 작업이 수행되도록 합니다. 기본 구현호출 [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), 단순히 기본적으로 DROPEFFECT_NONE 반환합니다.

자세한 내용은 [IDropTarget::Dwindows](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) SDK에서 ragEnter를 참조하십시오.

## <a name="coledroptargetondragleave"></a><a name="ondragleave"></a>콜레드롭 타겟::온드래그리브

끌기 작업이 적용되는 동안 커서가 창을 떠날 때 프레임워크에서 호출됩니다.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서가 나가는 창을 가리킵니다.

### <a name="remarks"></a>설명

끌기 작업이 지정된 창을 떠날 때 특수 동작을 원하는 경우 이 함수를 재정의합니다. 이 함수의 기본 구현은 [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave)를 호출합니다.

자세한 내용은 [IDropTarget::DWindows](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragleave) SDK에서 ragLeave를 참조하십시오.

## <a name="coledroptargetondragover"></a><a name="ondragover"></a>콜레드롭 타겟::온드래그오버

커서를 창 위로 드래그할 때 프레임워크에서 호출됩니다.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서가 끝난 창을 가리킵니다.

*pDataObject*<br/>
삭제할 데이터가 포함된 데이터 개체를 가리킵니다.

*dwKeyState*<br/>
수정자 키의 상태를 포함합니다. 이는 MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON 및 MK_RBUTTON 여러 가지 조합입니다.

*지점*<br/>
클라이언트 좌표에서 커서의 현재 위치를 포함합니다.

### <a name="return-value"></a>Return Value

*포인트에*의해 지정된 위치에서 드롭을 시도한 경우 발생하는 효과입니다. 다음 중 하나 이상이 될 수 있습니다.

- DROPEFFECT_NONE 한 방울은 허용되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행됩니다.

- DROPEFFECT_LINK 삭제된 데이터에서 원본 데이터에 대한 링크가 설정됩니다.

- DROPEFFECT_SCROLL 드래그 스크롤 작업이 발생하려고 하거나 대상에서 발생 중임을 나타냅니다.

### <a name="remarks"></a>설명

이 함수는 창에서 놓기 작업이 발생할 수 있도록 재정의해야 합니다. 이 함수의 기본 구현은 [CView::OnDragOver를](../../mfc/reference/cview-class.md#ondragover)호출하며 기본적으로 DROPEFFECT_NONE 반환합니다. 이 함수는 끌어서 놓기 작업 중에 자주 호출되므로 가능한 한 많이 최적화해야 합니다.

자세한 내용은 Windows SDK에서 [IDropTarget::DragOver를](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]

## <a name="coledroptargetondragscroll"></a><a name="ondragscroll"></a>콜레드롭타겟::온드래그스크롤

[OnDragEnter](#ondragenter) 또는 [OnDragOver를](#ondragover) 호출하기 전에 프레임 워크에서 호출하여 *점이* 스크롤 영역에 있는지 여부를 확인합니다.

```
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서가 현재 끝난 창을 가리킵니다.

*dwKeyState*<br/>
수정자 키의 상태를 포함합니다. 이는 MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON 및 MK_RBUTTON 여러 가지 조합입니다.

*지점*<br/>
화면을 기준으로 커서의 위치를 픽셀 단위로 포함합니다.

### <a name="return-value"></a>Return Value

*포인트에*의해 지정된 위치에서 드롭을 시도한 경우 발생하는 효과입니다. 다음 중 하나 이상이 될 수 있습니다.

- DROPEFFECT_NONE 한 방울은 허용되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행됩니다.

- DROPEFFECT_LINK 삭제된 데이터에서 원본 데이터에 대한 링크가 설정됩니다.

- DROPEFFECT_SCROLL 드래그 스크롤 작업이 발생하려고 하거나 대상에서 발생 중임을 나타냅니다.

### <a name="remarks"></a>설명

이 이벤트에 대한 특수 동작을 제공하려는 경우 이 함수를 재정의합니다. 이 함수의 기본 구현은 [CView:OnDragScroll를](../../mfc/reference/cview-class.md#ondragscroll)호출하여 DROPEFFECT_NONE 반환하고 커서를 창 테두리 내부의 기본 스크롤 영역으로 드래그할 때 창을 스크롤합니다.

## <a name="coledroptargetondrop"></a><a name="ondrop"></a>콜레드롭 타겟::드롭 드롭

드롭 작업이 발생할 때 프레임워크에서 호출합니다.

```
virtual BOOL OnDrop(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서가 현재 끝난 창을 가리킵니다.

*pDataObject*<br/>
삭제할 데이터가 포함된 데이터 개체를 가리킵니다.

*드롭 이펙트*<br/>
드롭 작업에 대해 사용자가 선택한 효과입니다. 다음 중 하나 이상이 될 수 있습니다.

- DROPEFFECT_COPY 복사 작업이 수행됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행됩니다.

- DROPEFFECT_LINK 삭제된 데이터에서 원본 데이터에 대한 링크가 설정됩니다.

*지점*<br/>
화면을 기준으로 커서의 위치를 픽셀 단위로 포함합니다.

### <a name="return-value"></a>Return Value

투하가 성공하면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

프레임워크는 먼저 [OnDropEx를 호출합니다.](#ondropex) 함수가 `OnDropEx` 드롭을 처리하지 않으면 프레임워크는 이 멤버 `OnDrop`함수를 호출합니다. 일반적으로 응용 프로그램은 오른쪽 마우스 단추 드래그 앤 드롭을 처리하기 위해 뷰 클래스에서 [OnDropEx를](../../mfc/reference/cview-class.md#ondropex) 재정의합니다. 일반적으로 View 클래스 [OnDrop은](../../mfc/reference/cview-class.md#ondrop) 간단한 끌어서 놓기를 처리하는 데 사용됩니다.

호출 `COleDropTarget::OnDrop` [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop)의 기본 구현은 기본적으로 FALSE를 반환합니다.

자세한 내용은 Windows SDK에서 [IDropTarget::Drop를](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) 참조하십시오.

## <a name="coledroptargetondropex"></a><a name="ondropex"></a>콜레드롭 타겟::온드롭엑스

드롭 작업이 발생할 때 프레임워크에서 호출합니다.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서가 현재 끝난 창을 가리킵니다.

*pDataObject*<br/>
삭제할 데이터가 포함된 데이터 개체를 가리킵니다.

*dropDefault*<br/>
사용자가 현재 키 상태에 따라 기본 놓기 작업에 대해 선택한 효과입니다. 그것은 DROPEFFECT_NONE 수 있습니다. 삭제 효과는 비고 섹션에서 설명합니다.

*드롭리스트*<br/>
드롭 소스가 지원하는 삭제 효과의 목록입니다. 낙하 효과 값은 비트별** OR(&#124;) **연산을 사용하여 결합될 수 있다. 삭제 효과는 비고 섹션에서 설명합니다.

*지점*<br/>
화면을 기준으로 커서의 위치를 픽셀 단위로 포함합니다.

### <a name="return-value"></a>Return Value

*점에*의해 지정된 위치에서 놓기 시도에서 발생한 놓기 효과입니다. 삭제 효과는 비고 섹션에서 설명합니다.

### <a name="remarks"></a>설명

프레임워크는 먼저 이 함수를 호출합니다. 드롭을 처리하지 않으면 프레임워크에서 [OnDrop](#ondrop)을 호출합니다. 일반적으로 오른쪽 마우스 단추 드래그 앤 드롭을 지원 하기 위해 뷰 클래스에서 [OnDropEx를](../../mfc/reference/cview-class.md#ondropex) 재정의 합니다. 일반적으로 View 클래스 [OnDrop은](../../mfc/reference/cview-class.md#ondrop) 간단한 끌어서 놓기 지원 사례를 처리하는 데 사용됩니다.

호출 `COleDropTarget::OnDropEx` [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex)의 기본 구현 기본적으로 [CView::OnDropEx는](../../mfc/reference/cview-class.md#ondropex) 단순히 더미 값을 반환하여 [OnDrop](#ondrop) 멤버 함수를 호출해야 함을 나타냅니다.

놓기 효과는 놓기 작업과 관련된 작업을 설명합니다. 드롭 효과의 다음 목록을 참조하십시오.

- DROPEFFECT_NONE 한 방울은 허용되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행됩니다.

- DROPEFFECT_LINK 삭제된 데이터에서 원본 데이터에 대한 링크가 설정됩니다.

- DROPEFFECT_SCROLL 드래그 스크롤 작업이 발생하려고 하거나 대상에서 발생 중임을 나타냅니다.

자세한 내용은 Windows SDK에서 [IDropTarget::Drop를](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) 참조하십시오.

## <a name="coledroptargetregister"></a><a name="register"></a>COleDropTarget::레지스터

이 함수를 호출하여 OLE DLL에 창을 유효한 놓기 대상으로 등록합니다.

```
BOOL Register(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
드롭 대상으로 등록할 창을 가리킵니다.

### <a name="return-value"></a>Return Value

등록에 성공하면 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

드롭 작업을 허용하려면 이 함수를 호출해야 합니다.

자세한 내용은 Windows SDK의 [RegisterDragDrop을](/windows/win32/api/ole2/nf-ole2-registerdragdrop) 참조하십시오.

## <a name="coledroptargetrevoke"></a><a name="revoke"></a>콜레드롭타겟::해지

드롭 대상 목록에서 제거하려면 [등록](#register) 호출을 통해 드롭 대상으로 등록된 창을 삭제하기 전에 이 함수를 호출합니다.

```
virtual void Revoke();
```

### <a name="remarks"></a>설명

이 함수는 등록된 창에 대해 [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) 처리기에서 자동으로 호출되므로 일반적으로 이 함수를 명시적으로 호출할 필요가 없습니다.

자세한 내용은 Windows SDK에서 [해지드래그드롭을](/windows/win32/api/ole2/nf-ole2-revokedragdrop) 참조하십시오.

## <a name="see-also"></a>참고 항목

[MFC 샘플 HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 클라이언트](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[콜레드롭소스 클래스](../../mfc/reference/coledropsource-class.md)
