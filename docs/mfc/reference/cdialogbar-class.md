---
title: 클리클로그바 클래스
ms.date: 11/04/2016
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
ms.openlocfilehash: cf9a2658807959108b3bb0af672d4c1835b58bc5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375670"
---
# <a name="cdialogbar-class"></a>클리클로그바 클래스

컨트롤 막대에 Windows 모덜리스 대화 상자의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CDialogBar : public CControlBar
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[클리언로그바::클리언로그바](#cdialogbar)|`CDialogBar` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDialogBar::만들기](#create)|Windows 대화 상자 막대를 만들고 개체에 `CDialogBar` 연결합니다.|

## <a name="remarks"></a>설명

대화 상자 막대는 사용자가 탭할 수 있는 표준 Windows 컨트롤이 포함되어 있다는 대화 상자와 유사합니다. 또 다른 유사점은 대화 상자 막대를 나타내는 대화 상자 템플릿을 만드는 것입니다.

대화 상자 막대를 만들고 사용하는 것은 개체를 만들고 사용하는 것과 유사합니다. `CFormView` 먼저 대화 [상자 편집기를](../../windows/dialog-editor.md) 사용하여 스타일 WS_CHILD 다른 스타일이 없는 대화 상자 템플릿을 정의합니다. 템플릿에 스타일 WS_VISIBLE 없어야 합니다. 응용 프로그램 코드에서 생성자 호출하여 `CDialogBar` 개체를 `Create` 생성한 다음 호출하여 대화 상자 막대 `CDialogBar` 창을 만들고 개체에 연결합니다.

자세한 `CDialogBar`내용은 문서 대화 [표시 줄](../../mfc/dialog-bars.md) 및 기술 참고 [31](../../mfc/tn031-control-bars.md), 제어 막대를 참조하십시오.

> [!NOTE]
> 현재 릴리스에서 개체는 Windows Forms 컨트롤을 `CDialogBar` 호스트할 수 없습니다. Visual C++의 Windows Forms 컨트롤에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="cdialogbarcdialogbar"></a><a name="cdialogbar"></a>클리언로그바::클리언로그바

`CDialogBar` 개체를 생성합니다.

```
CDialogBar();
```

## <a name="cdialogbarcreate"></a><a name="create"></a>CDialogBar::만들기

또는 에 의해 `lpszTemplateName` 지정된 대화 상자 `nIDTemplate`리소스 템플릿을 로드, 대화 모음 창을 만들고, `CDialogBar` 스타일을 설정하고, 객체와 연결합니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

virtual BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
상위 `CWnd` 개체에 대한 포인터입니다.

*lpszTemplateName*<br/>
`CDialogBar` 개체의 대화 상자 리소스 템플릿 이름에 대한 포인터입니다.

*nStyle*<br/>
도구 모음 스타일입니다. 지원되는 추가 도구 모음 스타일은 다음과 같습니다.

- CBRS_TOP 컨트롤 막대는 프레임 창 의 맨 위에 있습니다.

- CBRS_BOTTOM 컨트롤 막대는 프레임 창 의 하단에 있습니다.

- CBRS_NOALIGN 컨트롤 막대는 부모의 크기를 조정할 때 위치가 바지지 않습니다.

- CBRS_TOOLTIPS 컨트롤 막대는 도구 팁을 표시합니다.

- CBRS_SIZE_DYNAMIC 컨트롤 바는 동적입니다.

- CBRS_SIZE_FIXED 컨트롤 바가 고정되어 있습니다.

- CBRS_FLOATING 컨트롤 바가 부동입니다.

- CBRS_FLYBY 상태 표시줄은 단추에 대한 정보를 표시합니다.

- CBRS_HIDE_INPLACE 컨트롤 막대가 사용자에게 표시되지 않습니다.

*nID*<br/>
대화 상자 막대의 제어 ID입니다.

*nIDTemplate*<br/>
`CDialogBar` 개체의 대화 상자 템플릿의 리소스 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

CBRS_TOP 또는 CBRS_BOTTOM 맞춤 스타일을 지정하는 경우 대화 상자 막대의 너비는 프레임 창의 너비이며 높이는 *nIDTemplate에서*지정한 리소스의 너비입니다. CBRS_LEFT 또는 CBRS_RIGHT 정렬 스타일을 지정하는 경우 대화 상자 막대의 높이는 프레임 창의 높이이고 너비는 *nIDTemplate에서*지정한 리소스의 높이입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>참고 항목

[MFC 샘플 CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFormView 클래스](../../mfc/reference/cformview-class.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)
