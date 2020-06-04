---
title: CMFC윈도우매니저디아로그 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
ms.openlocfilehash: e3928c0d3ae4f607dceb99c0762277e8ea9ddbde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319835"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFC윈도우매니저디아로그 클래스

개체를 `CMFCWindowsManagerDialog` 사용하면 사용자가 MDI 응용 프로그램에서 MDI 자식 창을 관리할 수 있습니다.

## <a name="syntax"></a>구문

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC윈도우매니저디아로그::CMFC윈도우매니저디아클로그](#cmfcwindowsmanagerdialog)|`CMFCWindowsManagerDialog` 개체를 생성합니다.|

## <a name="remarks"></a>설명

에는 `CMFCWindowsManagerDialog` 응용 프로그램에서 현재 열려 있는 MDI 자식 창 목록이 포함되어 있습니다. 사용자는 이 대화 상자를 사용하여 MDI 자식 창의 상태를 수동으로 제어할 수 있습니다.

`CMFCWindowsManagerDialog`[CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)내에 내장되어 있습니다. 은 `CMFCWindowsManagerDialog` 수동으로 만들어야 하는 클래스가 아닙니다. 대신 [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog)함수를 호출하면 개체를 `CMFCWindowsManagerDialog` 만들고 표시합니다.

## <a name="example"></a>예제

다음 예제에서는 를 호출하여 `CMFCWindowsManagerDialog` `CMDIFrameWndEx::ShowWindowsDialog`개체를 생성하는 방법을 보여 줍니다. 이 코드 조각은 Visual [Studio 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxWindowsManagerDialog.h

## <a name="cmfcwindowsmanagerdialogcmfcwindowsmanagerdialog"></a><a name="cmfcwindowsmanagerdialog"></a>CMFC윈도우매니저디아로그::CMFC윈도우매니저디아클로그

[CMFC윈도우매니저디아로그](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 개체를 생성합니다.

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>매개 변수

*pMDIFrame*<br/>
【인】 상위 또는 소유자 창에 대한 포인터입니다.

*b도움말 버튼*<br/>
【인】 프레임워크에 **도움말** 단추를 표시할지 여부를 지정하는 부울 매개 변수입니다.

### <a name="remarks"></a>설명

시각적 관리자에 대한 자세한 내용은 [시각화 관리자를](../../mfc/visualization-manager.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)
