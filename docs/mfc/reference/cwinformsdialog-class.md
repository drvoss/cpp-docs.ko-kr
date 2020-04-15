---
title: CWinForms디아로그 클래스
ms.date: 03/27/2019
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
helpviewer_keywords:
- CWinFormsDialog [MFC], CWinFormsDialog
- CWinFormsDialog [MFC], GetControl
- CWinFormsDialog [MFC], GetControlHandle
- CWinFormsDialog [MFC], OnInitDialog
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
ms.openlocfilehash: 3772033df59e065cedca61012cd479c812cf5b66
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367434"
---
# <a name="cwinformsdialog-class"></a>CWinForms디아로그 클래스

Windows Forms 사용자 정의 컨트롤을 호스팅하는 MFC 대화 상자 클래스의 래퍼입니다.

## <a name="syntax"></a>구문

```
template <typename TManagedControl>
class CWinFormsDialog :
    public CDialog
```

#### <a name="parameters"></a>매개 변수

*TManagedControl*<br/>
MFC 응용 프로그램에 표시할 .NET 프레임워크 사용자 컨트롤입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CWinForms디아로그::CWinForms디아로그](#cwinformsdialog)|`CWinFormsDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CWinForms대화문::Getcontrol](#getcontrol)|Windows Forms 사용자 컨트롤에 대한 참조를 검색합니다.|
|[CWinForms대화단::GetControl핸들](#getcontrolhandle)|Windows Forms 사용자 컨트롤에 대한 창 핸들을 검색합니다.|
|[CWinForms디아로그::InInitDialog](#oninitdialog)|MFC 대화 상자를 만들고 Windows Forms 사용자 컨트롤을 호스팅하여 초기화합니다.|

### <a name="public-operators"></a>Public 연산자

|속성||
|----------|-|
|[CWinForms디아로그::연산자 -&gt;](#operator_-_gt)|[CWinFormsDialog를 대체합니다::GetControl](#getcontrol) 식에서.|
|[CWinForms디아로그::연산자 TManagedControl^](#operator-tmanagedcontrol-hat)|Windows Forms 사용자 컨트롤에 대 한 참조로 형식을 캐스팅 합니다.|

## <a name="remarks"></a>설명

`CWinFormsDialog`는 Windows Forms 사용자 컨트롤을 호스트하는 MFC 대화 상자 [클래스(CDialog)의](../../mfc/reference/cdialog-class.md)래퍼입니다. 이렇게 하면 모달 또는 모덜리스 MFC 대화 상자에 .NET Framework 컨트롤을 표시할 수 있습니다.

Windows 양식 사용에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md) 및 Windows 양식 사용자 [컨트롤을 MFC 대화 상자로 호스팅하는](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)것을 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h

## <a name="cwinformsdialogcwinformsdialog"></a><a name="cwinformsdialog"></a>CWinForms디아로그::CWinForms디아로그

`CWinFormsDialog` 개체를 생성합니다.

```
CWinFormsDialog(UINT nIDTemplate = IDD);
```

### <a name="parameters"></a>매개 변수

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID를 포함합니다. 대화 상자 편집기를 사용하여 대화 상자 템플릿을 만들고 응용 프로그램의 리소스 스크립트 파일에 저장합니다. 대화 상자 템플릿에 대한 자세한 내용은 [CDialog 클래스](../../mfc/reference/cdialog-class.md)를 참조하십시오.

## <a name="cwinformsdialoggetcontrol"></a><a name="getcontrol"></a>CWinForms대화문::Getcontrol

Windows Forms 사용자 컨트롤에 대한 참조를 검색합니다.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Return Value

MFC 대화 상자에서 Windows 양식 컨트롤에 대한 참조를 반환합니다.

## <a name="cwinformsdialoggetcontrolhandle"></a><a name="getcontrolhandle"></a>CWinForms대화단::GetControl핸들

Windows Forms 사용자 컨트롤에 대한 창 핸들을 검색합니다.

```
inline HWND GetControlHandle() const throw();
```

### <a name="return-value"></a>Return Value

Windows Forms 사용자 컨트롤에 창 핸들을 반환 합니다.

## <a name="cwinformsdialogoninitdialog"></a><a name="oninitdialog"></a>CWinForms디아로그::InInitDialog

MFC 대화 상자를 만들고 Windows Forms 사용자 컨트롤을 호스팅하여 초기화합니다.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Return Value

응용 프로그램이 대화 상자의 컨트롤 중 하나에 입력 포커스를 설정했는지 여부를 지정하는 부울 값입니다. 0이 아닌 것을 반환하는 경우 `OnInitDialog` Windows는 입력 포커스를 대화 상자의 첫 번째 컨트롤로 설정합니다. 이 메서드는 응용 프로그램이 대화 상자의 컨트롤 중 하나에 입력 포커스를 명시적으로 설정한 경우에만 0을 반환할 수 있습니다.

### <a name="remarks"></a>설명

MFC 대화 상자를 만들 때 [(만들기를](../../mfc/reference/cdialog-class.md#create)사용 하 여 , [만들기 간접,](../../mfc/reference/cdialog-class.md#createindirect)또는 [DoModal](../../mfc/reference/cdialog-class.md#domodal) 메서드 에서 상속 [CDialog)](../../mfc/reference/cdialog-class.md)WM_INITDIALOG 메시지가 전송 되 고이 메서드가 호출 됩니다. 대화 상자에 Windows Forms 컨트롤의 인스턴스를 만들고 사용자 컨트롤의 크기에 맞게 대화 상자의 크기를 조정 합니다. 그런 다음 MFC 대화 상자에서 새 컨트롤을 호스트합니다.

대화 상자가 초기화될 때 특별한 처리를 수행해야 하는 경우 이 멤버 함수를 재정의합니다. 이 메서드를 사용 하 여에 대 한 자세한 내용은 [참조 CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog).

## <a name="cwinformsdialogoperator--gt"></a><a name="operator_-_gt"></a>CWinForms디아로그::연산자 -&gt;

[CWinFormsDialog를 대체합니다::GetControl](#getcontrol) 식에서.

```
inline TManagedControl^  operator->() const throw();
```

### <a name="remarks"></a>설명

이 연산자는 식에서 대체하는 `GetControl` 편리한 구문을 제공합니다.

Windows 양식 사용에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

## <a name="cwinformsdialogoperator-tmanagedcontrol"></a><a name="operator-tmanagedcontrol-hat"></a>CWinForms디아로그::연산자 TManagedControl^

Windows Forms 사용자 컨트롤에 대 한 참조로 형식을 캐스팅 합니다.

```
inline operator TManagedControl^() const throw();
```

### <a name="remarks"></a>설명

이 연산자는 Windows Forms 컨트롤에 대한 참조로 형식을 캐스팅합니다. Windows Forms 사용자 `CWinFormsDialog<TManagedControl>` 컨트롤 개체에 대한 포인터를 허용하는 함수에 대화 상자를 전달하는 데 사용됩니다.

## <a name="see-also"></a>참고 항목

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CWinForms뷰 클래스](../../mfc/reference/cwinformsview-class.md)<br/>
[클리언로그 클래스](../../mfc/reference/cdialog-class.md)
