---
title: CFolderPickerDialog 클래스
ms.date: 03/27/2019
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: ed3dc151060519bce216cf4a2f3d6559d6b8937e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373858"
---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog 클래스

CFolderPicker Dialog 클래스는 폴더 선택 모드에서 CFileDialog를 구현합니다.

## <a name="syntax"></a>구문

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CFolder피커디아로그::~CFolder피커디아로그](#_dtorcfolderpickerdialog)|소멸자|
|[CFolder피커디아로그::CFolder피커디아로그](#cfolderpickerdialog)|생성자입니다.|

## <a name="remarks"></a>설명

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[CFileDialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="cfolderpickerdialog"></a>CFolder피커디아로그::CFolder피커디아로그

생성자입니다.

```
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL,
    DWORD dwSize = 0);
```

### <a name="parameters"></a>매개 변수

*lpsz폴더*<br/>
초기 폴더입니다.

*dwFlags*<br/>
대화 상자를 사용자 지정할 수 있는 하나 이상의 플래그의 조합입니다.

*pParentWnd*<br/>
대화 상자 개체의 부모 또는 소유자 창에 대한 포인터입니다.

*dwSize*<br/>
OPENFILENAME 구조의 크기입니다.

### <a name="remarks"></a>설명

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="_dtorcfolderpickerdialog"></a>CFolder피커디아로그::~CFolder피커디아로그

소멸자

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
