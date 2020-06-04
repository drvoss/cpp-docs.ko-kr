---
title: CMFC스핀버튼Ctrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
ms.openlocfilehash: 445b857400d8c82109ca7220b84bac692a2abf89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376184"
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFC스핀버튼Ctrl 클래스

클래스는 `CMFCSpinButtonCtrl` 스핀 버튼 컨트롤을 그리는 시각적 관리자를 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCSpinButtonCtrl : public CSpinButtonCtrl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|기본 생성자입니다.|
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC스핀버튼Ctrl::온드로우](#ondraw)|현재 스핀 버튼 컨트롤을 다시 그립니다.|

## <a name="remarks"></a>설명

시각적 관리자를 사용하여 응용 프로그램에서 스핀 단추 컨트롤을 그리려면 `CSpinButtonCtrl` 클래스의 `CMFCSpinButtonCtrl` 모든 인스턴스를 클래스로 바꿉습니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCSpinButtonCtrl` 클래스의 개체를 만들고 해당 `Create` 메서드를 사용 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)

[CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxspinbuttonctrl.h

## <a name="cmfcspinbuttonctrlondraw"></a><a name="ondraw"></a>CMFC스핀버튼Ctrl::온드로우

현재 스핀 버튼 컨트롤을 다시 그립니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

### <a name="remarks"></a>설명

프레임워크는 [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) 메시지를 처리하는 `CMFCSpinButtonCtrl::OnDraw` `CMFCSpinButtonCtrl::OnPaint` 메서드를 호출하고 해당 메서드는 차례로 이 메서드를 호출합니다. 이 메서드를 재정의하여 프레임워크가 스핀 단추 컨트롤을 그리는 방법을 사용자 지정합니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC비주얼매니저 클래스](../../mfc/reference/cmfcvisualmanager-class.md)
