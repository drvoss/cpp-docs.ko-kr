---
title: CMFC데스크탑경고디아로그 클래스
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::CreateFromParams
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::GetDlgSize
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::HasFocus
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::PreTranslateMessage
helpviewer_keywords:
- CMFCDesktopAlertDialog [MFC], CreateFromParams
- CMFCDesktopAlertDialog [MFC], GetDlgSize
- CMFCDesktopAlertDialog [MFC], HasFocus
- CMFCDesktopAlertDialog [MFC], PreTranslateMessage
ms.assetid: a53c60aa-9607-485b-b826-ec64962075f6
ms.openlocfilehash: 479959e9b021255e309caf6fee02588a8cd8f1d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367650"
---
# <a name="cmfcdesktopalertdialog-class"></a>CMFC데스크탑경고디아로그 클래스

이 `CMFCDesktopAlertDialog` 클래스는 [CMFCDesktopAlertWnd 클래스와](../../mfc/reference/cmfcdesktopalertwnd-class.md) 함께 사용되어 팝업 창에 사용자 지정 대화 상자를 표시합니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCDesktopAlertDialog : public CDialogEx
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCDesktopAlertDialog::CreateFromParams](#createfromparams)||
|[CMFCDesktopAlertDialog::GetDlgSize](#getdlgsize)||
|[CMFCDesktopAlertDialog::HasFocus](#hasfocus)||
|[CMFCDesktopAlertDialog::PreTranslateMessage](#pretranslatemessage)|( `CDialogEx::PreTranslateMessage`을 재정의합니다.)|

### <a name="remarks"></a>설명

다음 단계를 수행하여 팝업 창에 사용자 지정 대화 상자를 표시합니다.

1. `CMFCDesktopAlertDialog`에서 클래스를 파생합니다.

1. 프로젝트 리소스에서 자식 대화 상자 템플릿을 만듭니다.

1. [CMFCDesktopAlertWnd:::대화](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) 상자 템플릿의 리소스 ID와 파생된 클래스의 런타임 클래스 정보를 매개 변수로 포인터로 만듭니다.

1. 호스트된 컨트롤에서 생성되는 모든 알림을 처리하는 사용자 지정 대화 상자를 프로그래밍하거나 이러한 알림을 직접 처리하는 호스트된 컨트롤을 프로그래밍합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDesktopAlertDialog.h

## <a name="cmfcdesktopalertdialogcreatefromparams"></a><a name="createfromparams"></a>CMFC데스크톱경고디아로그::창조로부터파라임

```
BOOL CreateFromParams(
    CMFCDesktopAlertWndInfo& params,
    CMFCDesktopAlertWnd* pParent);
```

### <a name="parameters"></a>매개 변수

【인】 *매개 변수*<br/>

【인】 *pParent*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcdesktopalertdialoggetdlgsize"></a><a name="getdlgsize"></a>CMFC데스크톱 경고디아로그::GetDlgSize

```
CSize GetDlgSize();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcdesktopalertdialoghasfocus"></a><a name="hasfocus"></a>CMFC데스크톱 경고디아로그::하스포커스

```
BOOL HasFocus() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcdesktopalertdialogpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFC데스크톱경고디아로그::P다시번역메시지

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

[in] *pMsg*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd 클래스](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFC데스크탑경고폰드정보 클래스](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[클리클로덱스 클래스](../../mfc/reference/cdialogex-class.md)
