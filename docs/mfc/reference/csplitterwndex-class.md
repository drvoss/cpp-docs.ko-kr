---
title: C스플리터WndEx 클래스
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: d7952e3082bf68cff7ad9ba218073081ee522320
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363914"
---
# <a name="csplitterwndex-class"></a>C스플리터WndEx 클래스

사용자 지정된 분할자 창을 나타냅니다.

## <a name="syntax"></a>구문

```
class CSplitterWndEx : public CSplitterWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CSplitterWndEx::CSplitterWndEx`|기본 생성자입니다.|
|`CSplitterWndEx::~CSplitterWndEx`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C스플리터 Wndex::온드로우 스플리터](#ondrawsplitter)|스플리터 창을 그리는 프레임 워크에 의해 호출 됩니다. (재정의 [CSplitterWnd::온드로우 스플리터](csplitterwnd-class.md#ondrawsplitter).)|

## <a name="remarks"></a>설명

스플리터 `OnDrawSplitter` 창의 그래픽 구성 요소의 모양을 사용자 지정하는 방법을 재정의합니다.

이 `CSplitterWndEx` 클래스는 시각적 관리자에 의해 구현되는 [OnDrawSplitterBorder,](cmfcvisualmanager-class.md#ondrawsplitterborder) [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox)및 [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) 메서드와 함께 사용됩니다. 시각적 관리자가 응용 프로그램에서 스플리터 창을 그리도록 하려면 `CSplitterWnd` 클래스의 `CSplitterWndEx` 선언을 클래스로 바꿉습니다. 프레임 창 응용 프로그램의 경우 스플리터 창 클래스는 mainfrm.h에 있는 CMainFrame 클래스에 선언됩니다. 예를 들어 샘플 `OutlookDemo` 디렉터리에서 샘플을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

[CSplitterWnd](csplitterwnd-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxsplitterwndex.h

## <a name="csplitterwndexondrawsplitter"></a><a name="ondrawsplitter"></a>C스플리터 Wndex::온드로우 스플리터

스플리터 창을 그리는 프레임 워크에 의해 호출 됩니다.

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다. 이 매개 변수가 NULL이면 프레임워크는 활성 창을 다시 그립니다.

*nType*<br/>
【인】 `CSplitterWnd::ESplitType` 그릴 스플리터 창 요소를 지정하는 열거 값 중 하나입니다. 유효한 값은 `splitBox`, `splitBar`, `splitIntersection` 및 `splitBorder`입니다.

*rect*<br/>
【인】 지정된 스플리터 창 요소를 그릴 차원 및 위치를 지정하는 경계 사각형입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../hierarchy-chart.md)<br/>
[클래스](mfc-classes.md)<br/>
[C스플리터Wnd 클래스](csplitterwnd-class.md)<br/>
[CMFC비주얼매니저 클래스](cmfcvisualmanager-class.md)
