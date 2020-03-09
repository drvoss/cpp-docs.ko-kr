---
title: CDialog 클래스
ms.date: 09/07/2019
f1_keywords:
- CDialog
- AFXWIN/CDialog
- AFXWIN/CDialog::CDialog
- AFXWIN/CDialog::Create
- AFXWIN/CDialog::CreateIndirect
- AFXWIN/CDialog::DoModal
- AFXWIN/CDialog::EndDialog
- AFXWIN/CDialog::GetDefID
- AFXWIN/CDialog::GotoDlgCtrl
- AFXWIN/CDialog::InitModalIndirect
- AFXWIN/CDialog::MapDialogRect
- AFXWIN/CDialog::NextDlgCtrl
- AFXWIN/CDialog::OnInitDialog
- AFXWIN/CDialog::OnSetFont
- AFXWIN/CDialog::PrevDlgCtrl
- AFXWIN/CDialog::SetDefID
- AFXWIN/CDialog::SetHelpID
- AFXWIN/CDialog::OnCancel
- AFXWIN/CDialog::OnOK
helpviewer_keywords:
- CDialog [MFC], CDialog
- CDialog [MFC], Create
- CDialog [MFC], CreateIndirect
- CDialog [MFC], DoModal
- CDialog [MFC], EndDialog
- CDialog [MFC], GetDefID
- CDialog [MFC], GotoDlgCtrl
- CDialog [MFC], InitModalIndirect
- CDialog [MFC], MapDialogRect
- CDialog [MFC], NextDlgCtrl
- CDialog [MFC], OnInitDialog
- CDialog [MFC], OnSetFont
- CDialog [MFC], PrevDlgCtrl
- CDialog [MFC], SetDefID
- CDialog [MFC], SetHelpID
- CDialog [MFC], OnCancel
- CDialog [MFC], OnOK
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
ms.openlocfilehash: b07190c70fb11950b25aff45fb10e850c0e81b24
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865110"
---
# <a name="cdialog-class"></a>CDialog 클래스

화면에 대화 상자를 표시 하는 데 사용 되는 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CDialog : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDialog::CDialog](#cdialog)|`CDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>공용 방법

|이름|설명|
|----------|-----------------|
|[CDialog::Create](#create)|`CDialog` 개체를 초기화합니다. 모덜리스 대화 상자를 만들어 `CDialog` 개체에 연결 합니다.|
|[CDialog::CreateIndirect](#createindirect)|리소스 기반이 아닌 메모리의 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다.|
|[CDialog::DoModal](#domodal)|모달 대화 상자를 호출 하 고 완료 되 면를 반환 합니다.|
|[CDialog::EndDialog](#enddialog)|모달 대화 상자를 닫습니다.|
|[CDialog::GetDefID](#getdefid)|대화 상자에 대 한 기본 누름 단추 컨트롤의 ID를 가져옵니다.|
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|대화 상자에서 지정 된 대화 상자 컨트롤로 포커스를 이동 합니다.|
|[CDialog::InitModalIndirect](#initmodalindirect)|리소스 기반이 아닌 메모리의 대화 상자 템플릿을 사용 하 여 모달 대화 상자를 만듭니다. 매개 변수는 함수 `DoModal`가 호출 될 때까지 저장 됩니다.|
|[CDialog::MapDialogRect](#mapdialogrect)|사각형의 대화 상자 단위를 화면 단위로 변환 합니다.|
|[CDialog::NextDlgCtrl](#nextdlgctrl)|대화 상자에서 다음 대화 상자 컨트롤로 포커스를 이동 합니다.|
|[CDialog::OnInitDialog](#oninitdialog)|대화 상자 초기화를 확대 하도록 재정의 합니다.|
|[CDialog::OnSetFont](#onsetfont)|텍스트를 그릴 때 대화 상자 컨트롤에서 사용할 글꼴을 지정 하려면를 재정의 합니다.|
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|대화 상자에서 이전 대화 상자 컨트롤로 포커스를 이동 합니다.|
|[CDialog::SetDefID](#setdefid)|대화 상자의 기본 누름 단추를 지정 된 누름 단추를 변경 합니다.|
|[CDialog::SetHelpID](#sethelpid)|대화 상자에 대 한 상황에 맞는 도움말 ID를 설정 합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CDialog::OnCancel](#oncancel)|취소 단추 또는 ESC 키 동작을 수행 하려면를 재정의 합니다. 기본값은 대화 상자를 닫고 `DoModal` IDCANCEL를 반환 합니다.|
|[CDialog::OnOK](#onok)|모달 대화 상자에서 확인 단추 작업을 수행 하려면를 재정의 합니다. 기본값은 대화 상자를 닫고 `DoModal` IDOK를 반환 합니다.|

## <a name="remarks"></a>주의

대화 상자는 모달 및 모덜리스의 두 가지 유형이 있습니다. 응용 프로그램을 계속 하기 전에 사용자가 모달 대화 상자를 닫아야 합니다. 모덜리스 대화 상자를 사용 하면 사용자가 대화 상자를 표시 하 고 대화 상자를 취소 하거나 제거 하지 않고 다른 작업으로 돌아갈 수 있습니다.

`CDialog` 개체는 대화 상자 템플릿과 `CDialog`파생 클래스의 조합입니다. 대화 상자 편집기를 사용 하 여 대화 상자 템플릿을 만들고 리소스에 저장 한 다음 클래스 추가 마법사를 사용 하 여 `CDialog`에서 파생 된 클래스를 만듭니다.

다른 창과 같은 대화 상자는 Windows에서 메시지를 받습니다. 대화 상자에서 사용자가 대화 상자와 상호 작용 하는 방식이 기 때문에 대화 상자의 컨트롤에서 알림 메시지를 처리 하는 데 특히 관심이 있습니다. [클래스 마법사](mfc-class-wizard.md) 를 사용 하 여 처리 하려는 메시지를 선택 하 고 클래스에 적절 한 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가 합니다. 처리기 멤버 함수에 응용 프로그램 전용 코드를 작성 하기만 하면 됩니다.

원한다 면 항상 메시지 맵 항목과 멤버 함수를 수동으로 작성할 수 있습니다.

가장 간단한 모든 대화 상자에서 파생 된 대화 상자 클래스에 멤버 변수를 추가 하 여 사용자가 대화 상자의 컨트롤에 입력 한 데이터를 저장 하거나 사용자에 대 한 데이터를 표시 합니다. 변수 추가 마법사를 사용 하 여 멤버 변수를 만들고 컨트롤에 연결할 수 있습니다. 동시에 각 변수에 대해 변수 형식 및 허용 되는 값 범위를 선택 합니다. 코드 마법사는 파생 된 대화 상자 클래스에 멤버 변수를 추가 합니다.

멤버 변수와 대화 상자의 컨트롤 간에 데이터 교환을 자동으로 처리 하기 위해 데이터 맵이 생성 됩니다. 데이터 맵은 대화 상자의 컨트롤을 적절 한 값으로 초기화 하 고, 데이터를 검색 하 고, 데이터의 유효성을 검사 하는 함수를 제공 합니다.

모달 대화 상자를 만들려면 파생 된 대화 상자 클래스에 대 한 생성자를 사용 하 여 스택에서 개체를 생성 한 다음 `DoModal`를 호출 하 여 대화 상자 창과 컨트롤을 만듭니다. 모덜리스 대화 상자를 만들려면 대화 상자 클래스의 생성자에서 `Create`를 호출 합니다.

Windows SDK에 설명 된 대로 [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) 데이터 구조를 사용 하 여 메모리에서 템플릿을 만들 수도 있습니다. `CDialog` 개체를 구성한 후에는 [Createindirect](#createindirect) 를 호출 하 여 모덜리스 대화 상자를 만들거나 [Initmodalindirect](#initmodalindirect) 및 [DoModal](#domodal) 를 호출 하 여 모달 대화 상자를 만듭니다.

Exchange 및 유효성 검사 데이터 맵은 새 대화 상자 클래스에 추가 되는 `CWnd::DoDataExchange`의 재정의로 작성 됩니다. Exchange 및 유효성 검사 기능에 대 한 자세한 내용은 `CWnd`의 [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) 멤버 함수를 참조 하세요.

프로그래머와 프레임 워크 호출은 [CWnd:: UpdateData](../../mfc/reference/cwnd-class.md#updatedata)를 호출 하 여 간접적으로 `DoDataExchange` 합니다.

사용자가 확인 단추를 클릭 하 여 모달 대화 상자를 닫을 때 프레임 워크는 `UpdateData`를 호출 합니다. [취소] 단추를 클릭 하면 데이터가 검색 되지 않습니다. [OnInitDialog](#oninitdialog) 의 기본 구현도를 `UpdateData` 호출 하 여 컨트롤의 초기 값을 설정 합니다. 일반적으로 `OnInitDialog`를 재정의 하 여 컨트롤을 추가로 초기화 합니다. `OnInitDialog`은 모든 대화 상자 컨트롤이 생성 된 후 대화 상자가 표시 되기 직전에 호출 됩니다.

모달 또는 모덜리스 대화 상자를 실행 하는 동안 언제 든 지 `CWnd::UpdateData`을 호출할 수 있습니다.

직접 대화 상자를 개발 하는 경우에는 필요한 멤버 변수를 파생 된 대화 상자 클래스에 직접 추가 하 고 멤버 함수를 추가 하 여 이러한 값을 설정 하거나 가져올 수 있습니다.

사용자가 확인 또는 취소 단추를 누르거나 코드가 `EndDialog` 멤버 함수를 호출 하는 경우 모달 대화 상자가 자동으로 닫힙니다.

모덜리스 대화 상자를 구현 하는 경우 항상 `OnCancel` 멤버 함수를 재정의 하 고 그 안에서 `DestroyWindow`를 호출 합니다. `CDialog::OnCancel`기본 클래스를 호출 하지 마세요 .이는 `EndDialog`를 호출 하기 때문에 대화 상자가 표시 되지 않지만이를 소멸 시 키 지 않도록 합니다. 모덜리스 대화 상자는 일반적으로 **new**와 함께 할당 되므로 **이**를 삭제 하려면 모덜리스 대화 상자에 대 한 `PostNcDestroy`를 재정의 해야 합니다. 모달 대화 상자는 일반적으로 프레임에 생성 되며 `PostNcDestroy` 정리가 필요 하지 않습니다.

`CDialog`에 대 한 자세한 내용은 [대화 상자](../../mfc/dialog-boxes.md)를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[에서 파생되지 않은](../../mfc/reference/cwnd-class.md)

`CDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cdialog"></a>  CDialog::CDialog

리소스 기반 모달 대화 상자를 생성 하려면 공용 형식의 생성자를 호출 합니다.

```
explicit CDialog(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd = NULL);

explicit CDialog(
    UINT nIDTemplate,
    CWnd* pParentWnd = NULL);

CDialog();
```

### <a name="parameters"></a>매개 변수

*lpszTemplateName*<br/>
대화 상자 템플릿 리소스의 이름인 null로 끝나는 문자열을 포함 합니다.

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID 번호를 포함 합니다.

*pParentWnd*<br/>
Dialog 개체가 속한 부모 또는 소유자 창 개체 ( [CWnd](../../mfc/reference/cwnd-class.md)형식)를 가리킵니다. NULL 인 경우에는 대화 상자 개체의 부모 창이 주 응용 프로그램 창으로 설정 됩니다.

### <a name="remarks"></a>주의

생성자의 한 형태는 템플릿 이름으로 대화 상자 리소스에 대 한 액세스를 제공 합니다. 다른 생성자는 일반적으로 **IDD_** 접두사 (예: IDD_DIALOG1)를 사용 하 여 템플릿 ID 번호로 액세스를 제공 합니다.

메모리의 템플릿에서 모달 대화 상자를 생성 하려면 먼저 매개 변수가 없는 protected 생성자를 호출한 다음 `InitModalIndirect`를 호출 합니다.

위의 방법 중 하나를 사용 하 여 모달 대화 상자를 생성 한 후 `DoModal`를 호출 합니다.

모덜리스 대화 상자를 생성 하려면 보호 된 형식의 `CDialog` 생성자를 사용 합니다. 사용자 고유의 대화 상자 클래스를 파생 시켜 모덜리스 대화 상자를 구현 해야 하므로 생성자는 보호 됩니다. 모덜리스 대화 상자 생성은 2 단계 프로세스입니다. 먼저 생성자를 호출 합니다. 그런 다음 `Create` 멤버 함수를 호출 하 여 리소스 기반 대화 상자를 만들거나 `CreateIndirect`를 호출 하 여 메모리의 템플릿에서 대화 상자를 만듭니다.

##  <a name="create"></a>  CDialog::Create

`Create`를 호출 하 여 리소스의 대화 상자 템플릿을 사용 하 여 모덜리스 대화 상자를 만듭니다.

```
virtual BOOL Create(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd = NULL);

virtual BOOL Create(
    UINT nIDTemplate,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszTemplateName*<br/>
대화 상자 템플릿 리소스의 이름인 null로 끝나는 문자열을 포함 합니다.

*pParentWnd*<br/>
Dialog 개체가 속한 부모 창 개체 ( [CWnd](../../mfc/reference/cwnd-class.md)형식)를 가리킵니다. NULL 인 경우에는 대화 상자 개체의 부모 창이 주 응용 프로그램 창으로 설정 됩니다.

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID 번호를 포함 합니다.

### <a name="return-value"></a>반환 값

대화 상자 만들기 및 초기화에 성공 하면 두 폼 모두 0이 아닌 값을 반환 합니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>주의

생성자 내부에 `Create` 호출을 추가 하거나 생성자가 호출 된 후 호출을 호출할 수 있습니다.

템플릿 이름이 나 템플릿 ID 번호 (예: IDD_DIALOG1)를 사용 하 여 대화 상자 템플릿 리소스에 액세스 하기 위해 두 가지 형식의 `Create` 멤버 함수가 제공 됩니다.

두 형태 모두에서 부모 창 개체에 대 한 포인터를 전달 합니다. *PParentWnd* 가 NULL 인 경우 대화 상자는 부모 또는 소유자 창이 주 응용 프로그램 창으로 설정 된 상태로 생성 됩니다.

`Create` 멤버 함수는 대화 상자를 만든 후 즉시 반환 됩니다.

부모 창을 만들 때 대화 상자를 표시 하려면 대화 상자 템플릿의 WS_VISIBLE 스타일을 사용 합니다. 그렇지 않으면 `ShowWindow`를 호출 해야 합니다. 추가 대화 상자 스타일 및 해당 응용 프로그램의 경우 *MFC 참조*의 Windows SDK 및 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 에서 [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) 구조를 참조 하세요.

`Create` 함수를 사용 하 여 만든 대화 상자를 삭제 하려면 `CWnd::DestroyWindow` 함수를 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]

##  <a name="createindirect"></a>  CDialog::CreateIndirect

이 멤버 함수를 호출 하 여 메모리에 있는 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다.

```
virtual BOOL CreateIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,
    CWnd* pParentWnd = NULL,
    void* lpDialogInit = NULL);

virtual BOOL CreateIndirect(
    HGLOBAL hDialogTemplate,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*lpDialogTemplate*<br/>
대화 상자를 만드는 데 사용 되는 대화 상자 템플릿을 포함 하는 메모리를 가리킵니다. 이 템플릿은 Windows SDK에 설명 된 대로 [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) 구조체 및 컨트롤 정보 형식으로 되어 있습니다.

*pParentWnd*<br/>
Dialog 개체의 부모 창 개체 ( [CWnd](../../mfc/reference/cwnd-class.md)형식)를 가리킵니다. NULL 인 경우에는 대화 상자 개체의 부모 창이 주 응용 프로그램 창으로 설정 됩니다.

*lpDialogInit*<br/>
DLGINIT 리소스를 가리킵니다.

*hDialogTemplate*<br/>
대화 상자 템플릿을 포함 하는 전역 메모리에 대 한 핸들을 포함 합니다. 이 템플릿은 대화 상자의 각 컨트롤에 대 한 데이터와 `DLGTEMPLATE` 구조 형식으로 되어 있습니다.

### <a name="return-value"></a>반환 값

대화 상자가 성공적으로 생성 되 고 초기화 된 경우 0이 아닌 것입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>주의

`CreateIndirect` 멤버 함수는 대화 상자를 만든 후 즉시 반환 됩니다.

부모 창을 만들 때 대화 상자를 표시 하려면 대화 상자 템플릿의 WS_VISIBLE 스타일을 사용 합니다. 그렇지 않으면 `ShowWindow`를 호출 하 여이를 표시 해야 합니다. 템플릿에서 다른 대화 상자 스타일을 지정 하는 방법에 대 한 자세한 내용은 Windows SDK의 [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) 구조를 참조 하세요.

`CreateIndirect` 함수를 사용 하 여 만든 대화 상자를 삭제 하려면 `CWnd::DestroyWindow` 함수를 사용 합니다.

ActiveX 컨트롤을 포함 하는 대화 상자에는 DLGINIT 리소스에서 제공 되는 추가 정보가 필요 합니다.

##  <a name="domodal"></a>  CDialog::DoModal

이 멤버 함수를 호출 하 여 모달 대화 상자를 호출 하 고 완료 되 면 대화 상자 결과를 반환 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>반환 값

대화 상자를 닫는 데 사용 되는 [CDialog:: EndDialog](#enddialog) 멤버 함수에 전달 된 *nresult* 매개 변수의 값을 지정 하는 **int** 값입니다. 함수가 대화 상자를 만들 수 없는 경우 반환 값은-1이 고, 다른 오류가 발생 한 경우 IDABORT입니다 .이 경우 출력 창에는 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)의 오류 정보가 포함 됩니다.

### <a name="remarks"></a>주의

이 멤버 함수는 대화 상자가 활성화 되어 있는 동안 사용자와의 모든 상호 작용을 처리 합니다. 이를 통해 대화 상자를 모달로 만듭니다. 즉, 사용자가 대화 상자를 닫을 때까지 다른 창과 상호 작용할 수 없습니다.

사용자가 대화 상자에서 누름 단추 중 하나를 클릭 하는 경우 (예: 확인 또는 취소) 대화 상자를 닫기 위해 [OnOK](#onok) 또는 [OnCancel](#oncancel)와 같은 메시지 처리기 멤버 함수를 호출 합니다. 기본 `OnOK` 멤버 함수는 대화 상자 데이터의 유효성을 검사 하 고 업데이트 한 다음 result IDOK를 사용 하 여 대화 상자를 닫습니다. 그러면 기본 `OnCancel` 멤버 함수는 대화 상자를 닫습니다. 이러한 메시지 처리기 함수를 재정의 하 여 해당 동작을 변경할 수 있습니다.

> [!NOTE]
> 이제 모달 대화 상자 메시지 처리를 위해 `PreTranslateMessage`가 호출 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]

##  <a name="enddialog"></a>  CDialog::EndDialog

이 멤버 함수를 호출 하 여 모달 대화 상자를 종료 합니다.

```
void EndDialog(int nResult);
```

### <a name="parameters"></a>매개 변수

*nResult*<br/>
대화 상자에서 `DoModal`호출자에 게 반환 되는 값을 포함 합니다.

### <a name="remarks"></a>주의

이 멤버 함수는 *Nresult* 를 `DoModal`반환 값으로 반환 합니다. 모달 대화 상자를 만들 때마다 처리를 완료 하려면 `EndDialog` 함수를 사용 해야 합니다.

[OnInitDialog](#oninitdialog)에서도 언제 든 지 `EndDialog`을 호출할 수 있으며,이 경우에는 대화 상자가 표시 되기 전에 또는 입력 포커스가 설정 되기 전에 닫아야 합니다.

`EndDialog`는 대화 상자를 즉시 닫지 않습니다. 대신 현재 메시지 처리기가 반환 되는 즉시 대화 상자를 닫도록 지시 하는 플래그를 설정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]

[!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]

##  <a name="getdefid"></a>  CDialog::GetDefID

`GetDefID` 멤버 함수를 호출 하 여 대화 상자에 대 한 기본 누름 단추 컨트롤의 ID를 가져옵니다.

```
DWORD GetDefID() const;
```

### <a name="return-value"></a>반환 값

32 비트 값 (`DWORD`)입니다. 기본 누름 단추에 ID 값이 있으면 상위 단어에는 DC_HASDEFID 포함 되 고 하위 단어에는 ID 값이 포함 됩니다. 기본 누름 단추에 ID 값이 없는 경우 반환 값은 0입니다.

### <a name="remarks"></a>주의

이는 일반적으로 확인 단추입니다.

##  <a name="gotodlgctrl"></a>  CDialog::GotoDlgCtrl

대화 상자에서 지정 된 컨트롤로 포커스를 이동 합니다.

```
void GotoDlgCtrl(CWnd* pWndCtrl);
```

### <a name="parameters"></a>매개 변수

*pWndCtrl*<br/>
포커스를 받을 창 (컨트롤)을 식별 합니다.

### <a name="remarks"></a>주의

*PWndCtrl*으로 전달할 컨트롤 (자식 창)에 대 한 포인터를 가져오려면 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대 한 포인터를 반환 하는 `CWnd::GetDlgItem` 멤버 함수를 호출 합니다.

### <a name="example"></a>예제

  [CWnd:: GetDlgItem](../../mfc/reference/cwnd-class.md#getdlgitem)의 예제를 참조 하세요.

##  <a name="initmodalindirect"></a>  CDialog::InitModalIndirect

메모리에서 생성 하는 대화 상자 템플릿을 사용 하 여 모달 대화 상자 개체를 초기화 하려면이 멤버 함수를 호출 합니다.

```
BOOL InitModalIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,
    CWnd* pParentWnd = NULL,
    void* lpDialogInit = NULL);

    BOOL InitModalIndirect(
    HGLOBAL hDialogTemplate,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*lpDialogTemplate*<br/>
대화 상자를 만드는 데 사용 되는 대화 상자 템플릿을 포함 하는 메모리를 가리킵니다. 이 템플릿은 Windows SDK에 설명 된 대로 [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) 구조체 및 컨트롤 정보 형식으로 되어 있습니다.

*hDialogTemplate*<br/>
대화 상자 템플릿을 포함 하는 전역 메모리에 대 한 핸들을 포함 합니다. 이 템플릿은 대화 상자의 각 컨트롤에 대 한 데이터와 `DLGTEMPLATE` 구조 형식으로 되어 있습니다.

*pParentWnd*<br/>
Dialog 개체가 속한 부모 또는 소유자 창 개체 ( [CWnd](../../mfc/reference/cwnd-class.md)형식)를 가리킵니다. NULL 인 경우에는 대화 상자 개체의 부모 창이 주 응용 프로그램 창으로 설정 됩니다.

*lpDialogInit*<br/>
DLGINIT 리소스를 가리킵니다.

### <a name="return-value"></a>반환 값

Dialog 개체가 성공적으로 생성 되 고 초기화 된 경우 0이 아닌 것입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>주의

모달 대화 상자를 간접적으로 만들려면 먼저 메모리의 전역 블록을 할당 하 고 대화 상자 템플릿을 사용 하 여 채웁니다. 그런 다음 빈 `CDialog` 생성자를 호출 하 여 대화 상자 개체를 생성 합니다. 그런 다음 `InitModalIndirect`를 호출 하 여 핸들을 메모리 내 대화 상자 템플릿에 저장 합니다. Windows 대화 상자는 나중에 [DoModal](#domodal) 멤버 함수가 호출 될 때 생성 되 고 표시 됩니다.

ActiveX 컨트롤을 포함 하는 대화 상자에는 DLGINIT 리소스에서 제공 되는 추가 정보가 필요 합니다.

##  <a name="mapdialogrect"></a>  CDialog::MapDialogRect

을 호출 하 여 사각형의 대화 상자 단위를 화면 단위로 변환 합니다.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*lpRect*<br/>
변환할 대화 상자 좌표를 포함 하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 [crect](../../atl-mfc-shared/reference/crect-class.md) 개체를 가리킵니다.

### <a name="remarks"></a>주의

대화 상자 단위는 대화 상자 텍스트에 사용 되는 글꼴의 평균 너비와 문자 높이에서 파생 된 현재 대화 상자 기본 단위를 기준으로 하 여 설명 됩니다. 하나의 가로 단위는 대화 상자 기본 너비 단위의 1/4이 고, 세로 단위 하나는 대화 상자 기본 높이 단위의 8-8입니다.

`GetDialogBaseUnits` Windows 함수는 시스템 글꼴에 대 한 크기 정보를 반환 하지만, 리소스 정의 파일에서 DS_SETFONT 스타일을 사용 하는 경우 각 대화 상자에 다른 글꼴을 지정할 수 있습니다. `MapDialogRect` Windows 함수는이 대화 상자에 해당 하는 글꼴을 사용 합니다.

`MapDialogRect` 멤버 함수는 사각형을 사용 하 여 대화 상자를 만들거나 상자 내에 컨트롤을 배치할 수 있도록 *lpRect* 의 대화 상자 단위를 화면 단위 (픽셀)로 바꿉니다.

##  <a name="nextdlgctrl"></a>  CDialog::NextDlgCtrl

대화 상자에서 다음 컨트롤로 포커스를 이동 합니다.

```
void NextDlgCtrl() const;
```

### <a name="remarks"></a>주의

대화 상자의 마지막 컨트롤에 포커스가 있는 경우 첫 번째 컨트롤로 이동 합니다.

##  <a name="oncancel"></a>  CDialog::OnCancel

사용자가 **취소** 를 클릭 하거나 모달 또는 모덜리스 대화 상자에서 ESC 키를 누르면 프레임 워크에서이 메서드를 호출 합니다.

```
virtual void OnCancel();
```

### <a name="remarks"></a>주의

사용자가 **취소** 를 클릭 하거나 ESC 키를 눌러 대화 상자를 닫을 때 이전 데이터 복원과 같은 작업을 수행 하려면이 메서드를 재정의 합니다. 기본값은 [EndDialog](#enddialog) 를 호출 하 여 [DoModal](#domodal) 이 IDCANCEL를 반환 하도록 하는 모달 대화 상자를 닫습니다.

모덜리스 대화 상자에서 **취소** 단추를 구현 하는 경우 `OnCancel` 메서드를 재정의 하 고 내부에서 [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) 를 호출 해야 합니다. 기본 클래스 메서드를 호출 하지 마세요 .이 메서드는 대화 상자를 표시 하지 않고 제거할 수 없게 하는 `EndDialog`를 호출 합니다.

> [!NOTE]
>  Windows XP에서 컴파일된 프로그램에서 `CFileDialog` 개체를 사용 하는 경우에는이 메서드를 재정의할 수 없습니다. `CFileDialog`에 대 한 자세한 내용은 [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md)를 참조 하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]

##  <a name="oninitdialog"></a>  CDialog::OnInitDialog

이 메서드는 `WM_INITDIALOG` 메시지에 대 한 응답으로 호출 됩니다.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>반환 값

응용 프로그램에서 대화 상자의 컨트롤 중 하나에 입력 포커스를 설정 했는지 여부를 지정 합니다. `OnInitDialog`에서 0이 아닌 값을 반환 하는 경우 Windows에서는 입력 포커스를 대화 상자의 첫 번째 컨트롤인 기본 위치로 설정 합니다. 응용 프로그램은 대화 상자의 컨트롤 중 하나에 명시적으로 입력 포커스를 설정한 경우에만 0을 반환할 수 있습니다.

### <a name="remarks"></a>주의

Windows에서는 대화 상자가 표시 되기 직전에 발생 하는 [Create](#create), [Createindirect](#createindirect)또는 [DoModal](#domodal) 호출 중에 대화 상자에 `WM_INITDIALOG` 메시지를 보냅니다.

대화 상자가 초기화 될 때 특수 한 처리를 수행 하려면이 메서드를 재정의 합니다. 재정의 된 버전에서 먼저 기본 클래스 `OnInitDialog`를 호출 하지만 해당 반환 값을 무시 합니다. 일반적으로 재정의 된 메서드에서 `TRUE`을 반환 합니다.

Windows는 모든 MFC 라이브러리 대화 상자에 공통 된 표준 전역 대화 상자 프로시저를 사용 하 여 `OnInitDialog` 함수를 호출 합니다. 이 함수는 메시지 맵을 통해이 함수를 호출 하지 않으므로이 메서드에 대 한 메시지 맵 항목이 필요 하지 않습니다.

> [!NOTE]
> Windows Vista 이상 운영 체제에서 컴파일되는 프로그램에서 `CFileDialog` 개체를 사용 하는 경우에는이 메서드를 재정의할 수 없습니다. Windows Vista 이상에서 `CFileDialog` 변경 내용에 대 한 자세한 내용은 [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md)를 참조 하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]

##  <a name="onok"></a>  CDialog::OnOK

사용자가 **확인** 단추 (ID가 IDOK 인 단추)를 클릭할 때 호출 됩니다.

```
virtual void OnOK();
```

### <a name="remarks"></a>주의

**확인** 단추가 활성화 될 때 작업을 수행 하려면이 메서드를 재정의 합니다. 대화 상자에 자동 데이터 유효성 검사 및 교환이 포함 된 경우이 메서드의 기본 구현에서는 대화 상자 데이터의 유효성을 검사 하 고 응용 프로그램에서 적절 한 변수를 업데이트 합니다.

모덜리스 대화 상자에서 **확인** 단추를 구현 하는 경우 `OnOK` 메서드를 재정의 하 고 내부에서 [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) 를 호출 해야 합니다. 대화 상자가 표시 되지 않지만 소멸 하지 않는 [EndDialog](#enddialog) 를 호출 하기 때문에 기본 클래스 메서드를 호출 하지 마세요.

> [!NOTE]
>  Windows XP에서 컴파일된 프로그램에서 `CFileDialog` 개체를 사용 하는 경우에는이 메서드를 재정의할 수 없습니다. `CFileDialog`에 대 한 자세한 내용은 [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md)를 참조 하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]

##  <a name="onsetfont"></a>  CDialog::OnSetFont

대화 상자 컨트롤에서 텍스트를 그릴 때 사용할 글꼴을 지정 합니다.

```
Virtual void OnSetFont(CFont* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
진행 이 대화 상자의 모든 컨트롤에 대 한 기본 글꼴로 사용 되는 글꼴에 대 한 포인터를 지정 합니다.

### <a name="remarks"></a>주의

이 대화 상자에는 지정 된 글꼴이 모든 컨트롤에 대 한 기본값으로 사용 됩니다.

대화 상자 편집기는 일반적으로 대화 상자 템플릿 리소스의 일부로 대화 상자 글꼴을 설정 합니다.

> [!NOTE]
> Windows Vista 이상 운영 체제에서 컴파일되는 프로그램에서 `CFileDialog` 개체를 사용 하는 경우에는이 메서드를 재정의할 수 없습니다. Windows Vista 이상에서 `CFileDialog` 변경 내용에 대 한 자세한 내용은 [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md)를 참조 하세요.

##  <a name="prevdlgctrl"></a>  CDialog::PrevDlgCtrl

대화 상자에서 이전 컨트롤로 포커스를 설정 합니다.

```
void PrevDlgCtrl() const;
```

### <a name="remarks"></a>주의

포커스가 대화 상자의 첫 번째 컨트롤에 있으면 상자의 마지막 컨트롤로 이동 합니다.

##  <a name="setdefid"></a>  CDialog::SetDefID

대화 상자의 기본 누름 단추 컨트롤을 변경 합니다.

```
void SetDefID(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
기본값이 될 누름 컨트롤의 ID를 지정 합니다.

##  <a name="sethelpid"></a>  CDialog::SetHelpID

대화 상자에 대 한 상황에 맞는 도움말 ID를 설정 합니다.

```
void SetHelpID(UINT nIDR);
```

### <a name="parameters"></a>매개 변수

*nIDR*<br/>
상황에 맞는 도움말 ID를 지정 합니다.

## <a name="see-also"></a>참고 항목

[MFC Sample DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 DLGTEMPL](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
