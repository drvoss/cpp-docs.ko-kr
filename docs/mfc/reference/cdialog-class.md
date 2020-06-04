---
title: 클리언로그 클래스
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
ms.openlocfilehash: 36913cfdd8beda31136176c966890a90077c1b30
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753369"
---
# <a name="cdialog-class"></a>클리언로그 클래스

화면에 대화 상자를 표시하는 데 사용되는 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CDialog : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDialog::CDialog](#cdialog)|`CDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDialog::Create](#create)|`CDialog` 개체를 초기화합니다. 모덜리스 대화 상자를 만들고 개체에 `CDialog` 연결합니다.|
|[CDialog::CreateIndirect](#createindirect)|리소스 기반이 아닌 메모리의 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다.|
|[CDialog::DoModal](#domodal)|모달 대화 상자를 호출하고 완료되면 반환합니다.|
|[CDialog::끝디아로그](#enddialog)|모달 대화 상자를 닫습니다.|
|[CDialog::GetDefID](#getdefid)|대화 상자에 대한 기본 푸시 버튼 컨트롤의 ID를 가져옵니다.|
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|대화 상자에서 포커스를 지정된 대화 상자 컨트롤로 이동합니다.|
|[CDialog::InitModalIndirect](#initmodalindirect)|리소스 기반이 아닌 메모리의 대화 상자 템플릿에서 모달 대화 상자를 만듭니다. 매개 변수는 함수가 `DoModal` 호출될 때까지 저장됩니다.|
|[CDialog::MapDialogRect](#mapdialogrect)|사각형의 대화 상자 단위를 화면 단위로 변환합니다.|
|[CDialog::NextDlgCtrl](#nextdlgctrl)|대화 상자의 다음 대화 상자 컨트롤로 포커스를 이동합니다.|
|[CDialog::OnInitDialog](#oninitdialog)|대화 상자 초기화를 보강하기 위해 재정의합니다.|
|[시디로그::온셋글꼴](#onsetfont)|대화 상자 컨트롤이 텍스트를 그릴 때 사용할 글꼴을 지정하려면 재정의합니다.|
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|대화 상자의 이전 대화 상자 컨트롤로 포커스를 이동합니다.|
|[시디언그::세트데피드](#setdefid)|대화 상자에 대한 기본 푸시 버튼 컨트롤을 지정된 푸시 버튼으로 변경합니다.|
|[CDialog::SetHelpID](#sethelpid)|대화 상자에 대한 컨텍스트 구분 도움말 ID를 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CDialog::OnCancel](#oncancel)|취소 단추 또는 ESC 키 작업을 수행하려면 재정의합니다. 기본값은 대화 상자를 닫고 `DoModal` IDCANCEL을 반환합니다.|
|[CDialog::OnOK](#onok)|재정의하여 모달 대화 상자에서 확인 단추 작업을 수행합니다. 기본값은 대화 상자를 닫고 `DoModal` IDOK를 반환합니다.|

## <a name="remarks"></a>설명

대화 상자는 모달과 모덜리스의 두 가지 유형입니다. 응용 프로그램을 계속하기 전에 사용자가 모달 대화 상자를 닫아야 합니다. 모덜리스 대화 상자를 사용하면 대화 상자를 취소하거나 제거하지 않고도 대화 상자를 표시하고 다른 작업으로 돌아갈 수 있습니다.

`CDialog` 개체는 대화 상자 템플릿과 -derived 클래스의 조합입니다. `CDialog` 대화 상자 편집기를 사용하여 대화 상자 템플릿을 만들고 리소스에 저장한 다음 클래스 추가 마법사를 사용하여 에서 `CDialog`파생된 클래스를 만듭니다.

다른 창과 마찬가지로 대화 상자는 Windows에서 메시지를 수신합니다. 대화 상자에서는 사용자가 대화 상자와 상호 작용하는 방식이기 때문에 대화 상자의 컨트롤에서 알림 메시지를 처리하는 데 특히 관심이 있습니다. 클래스 [마법사를](mfc-class-wizard.md) 사용하여 처리할 메시지를 선택하고 적절한 메시지 맵 항목 및 메시지 처리기 멤버 함수를 클래스에 추가합니다. 처리기 멤버 함수에 응용 프로그램 별 코드를 작성하기만 하면 됩니다.

원하는 경우 언제든지 메시지 맵 항목 및 멤버 함수를 수동으로 작성할 수 있습니다.

가장 사소한 대화 상자를 제외한 모든 대화 상자에서 파생 대화 상자 클래스에 멤버 변수를 추가하여 사용자가 대화 상자의 컨트롤에 입력한 데이터를 저장하거나 사용자에 대한 데이터를 표시합니다. 변수 추가 마법사를 사용하여 멤버 변수를 만들고 컨트롤과 연결할 수 있습니다. 동시에 각 변수에 대해 변수 형식과 허용 가능한 값 범위를 선택합니다. 코드 마법사는 파생 대화 상자 클래스에 멤버 변수를 추가합니다.

멤버 변수와 대화 상자의 컨트롤 간의 데이터 교환을 자동으로 처리하기 위한 데이터 맵이 생성됩니다. 데이터 맵은 적절한 값으로 대화 상자의 컨트롤을 초기화하고 데이터를 검색하고 데이터의 유효성을 검사하는 함수를 제공합니다.

모달 대화 상자를 만들려면 파생 대화 상자 클래스의 생성자를 사용하여 스택에서 개체를 `DoModal` 생성한 다음 호출하여 대화 상자 창과 해당 컨트롤을 만듭니다. 모덜리스 대화 상자를 만들려면 대화 `Create` 상자 클래스의 생성자에서 호출합니다.

Windows SDK에 설명된 대로 [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) 데이터 구조를 사용하여 메모리에 템플릿을 만들 수도 있습니다. `CDialog` 개체를 생성한 후 [CreateDirect를](#createindirect) 호출하여 모덜리스 대화 상자를 만들거나 [InitModalDirect](#initmodalindirect) 및 [DoModal을](#domodal) 호출하여 모달 대화 상자를 만듭니다.

교환 및 유효성 검사 데이터 맵은 `CWnd::DoDataExchange` 새 대화 상자 클래스에 추가되는 재정의로 작성됩니다. 교환 및 유효성 검사 `CWnd` 기능에 대한 자세한 내용은 [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) 멤버 함수를 참조하십시오.

프로그래머와 프레임워크모두 `DoDataExchange` [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)에 대한 호출을 통해 간접적으로 호출됩니다.

사용자가 OK `UpdateData` 단추를 클릭하여 모달 대화 상자를 닫을 때 프레임워크가 호출됩니다. (취소 단추를 클릭하면 데이터가 검색되지 않습니다.) [OnInitDialog의](#oninitdialog) 기본 구현은 `UpdateData` 컨트롤의 초기 값을 설정하기 위해 호출됩니다. 일반적으로 컨트롤을 `OnInitDialog` 추가로 초기화하기 위해 재정의합니다. `OnInitDialog`모든 대화 상자 컨트롤이 만들어지고 대화 상자가 표시되기 직전에 호출됩니다.

모달 `CWnd::UpdateData` 또는 모덜리스 대화 상자를 실행하는 동안 언제든지 호출할 수 있습니다.

직접 대화 상자를 개발하는 경우 파생 대화 상자 클래스에 필요한 멤버 변수를 직접 추가하고 멤버 함수를 추가하여 이러한 값을 설정하거나 가져옵니다.

사용자가 확인 또는 취소 단추를 누르거나 코드에서 `EndDialog` 멤버 함수를 호출할 때 모달 대화 상자가 자동으로 닫힙니다.

모덜리스 대화 상자를 구현할 때항상 `OnCancel` 멤버 함수를 `DestroyWindow` 재정의하고 그 안에서 호출합니다. 기본 클래스를 `CDialog::OnCancel`호출하지 마십시오. `EndDialog` 또한 모덜리스 `PostNcDestroy` 대화 상자를 새 로 할당하기 때문에 **이를**삭제하려면 모덜리스 대화 상자를 재정의해야 **합니다.** 모달 대화 상자는 일반적으로 프레임에 생성되며 `PostNcDestroy` 정리가 필요하지 않습니다.

자세한 `CDialog`내용은 대화 [상자 를](../../mfc/dialog-boxes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cdialogcdialog"></a><a name="cdialog"></a>CDialog::CDialog

리소스 기반 모달 대화 상자를 구성하려면 생성자의 공용 형식을 호출합니다.

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
대화 상자 템플릿 리소스의 이름인 null-종단 문자열을 포함합니다.

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID 번호를 포함합니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 상위 또는 소유자 창 [개체(CWnd](../../mfc/reference/cwnd-class.md)형식)를 가리킵니다. NULL인 경우 대화 상자 개체의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

### <a name="remarks"></a>설명

생성자의 한 형식은 템플릿 이름으로 대화 상자 리소스에 대한 액세스를 제공합니다. 다른 생성자는 템플릿 ID 번호로 액세스를 제공하며, 일반적으로 **IDD_** 접두사(예: IDD_DIALOG1)가 있습니다.

메모리의 템플릿에서 모달 대화 상자를 구성하려면 먼저 매개 변수가 없는 보호된 `InitModalIndirect`생성자를 호출한 다음 을 호출합니다.

위의 방법 중 하나를 사용 하 여 모달 `DoModal`대화 상자를 구성 한 후 호출 합니다.

모덜리스 대화 상자를 구성하려면 `CDialog` 생성자의 보호된 형식을 사용합니다. 모덜리스 대화 상자를 구현하려면 사용자 고유의 대화 상자 클래스를 파생해야 하기 때문에 생성자가 보호됩니다. 모덜리스 대화 상자의 구성은 2단계 프로세스입니다. 먼저 생성자 호출합니다. 그런 다음 `Create` 멤버 함수를 호출하여 리소스 기반 대화 `CreateIndirect` 상자를 만들거나 호출하여 메모리의 템플릿에서 대화 상자를 만듭니다.

## <a name="cdialogcreate"></a><a name="create"></a>CDialog::만들기

리소스의 대화 상자 템플릿을 사용하여 모덜리스 대화 상자를 만들려면 호출합니다. `Create`

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
대화 상자 템플릿 리소스의 이름인 null-종단 문자열을 포함합니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 상위 창 [개체(CWnd](../../mfc/reference/cwnd-class.md)형식)를 가리킵니다. NULL인 경우 대화 상자 개체의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID 번호를 포함합니다.

### <a name="return-value"></a>Return Value

대화 상자 만들기 및 초기화가 성공한 경우 두 양식 모두 0이 아닌 것으로 돌아갑니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

생성자 내부에 호출을 `Create` 넣거나 생성자가 호출된 후 호출할 수 있습니다.

`Create` 멤버 함수의 두 가지 형태는 템플릿 이름 또는 템플릿 ID 번호(예: IDD_DIALOG1)에 의해 대화 상자 템플릿 리소스에 액세스하기 위해 제공됩니다.

두 양식의 경우 포인터를 부모 창 개체에 전달합니다. *pParentWnd가* NULL이면 상위 또는 소유자 창이 기본 응용 프로그램 창으로 설정된 대화 상자가 만들어집니다.

멤버 `Create` 함수는 대화 상자를 만들면 바로 반환됩니다.

부모 창을 만들 때 대화 상자가 나타나야 하는 경우 대화 상자 템플릿에서 WS_VISIBLE 스타일을 사용합니다. 그렇지 않으면 을 `ShowWindow`호출해야 합니다. 추가 대화 상자 스타일 및 해당 응용 프로그램에 대 한 Windows SDK 및 [창 스타일에서](../../mfc/reference/styles-used-by-mfc.md#window-styles) [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) 구조를 *참조 합니다.*

함수를 `CWnd::DestroyWindow` 사용하여 `Create` 함수에 의해 생성된 대화 상자를 삭제합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]

## <a name="cdialogcreateindirect"></a><a name="createindirect"></a>CDialog::직접 만들기

이 멤버 함수를 호출하여 메모리의 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다.

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
대화 상자를 만드는 데 사용되는 대화 상자 템플릿이 포함된 메모리를 가리킵니다. 이 템플릿은 Windows SDK에 설명된 대로 [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) 구조 및 제어 정보의 형태로 되어 있습니다.

*pParentWnd*<br/>
대화 상자 개체의 상위 창 [개체(CWnd](../../mfc/reference/cwnd-class.md)형식)를 가리킵니다. NULL인 경우 대화 상자 개체의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

*lpDialogInit*<br/>
DLGINIT 리소스를 가리킵니다.

*hDialogTemplate*<br/>
대화 상자 템플릿을 포함하는 전역 메모리에 대한 핸들을 포함합니다. 이 템플릿은 대화 상자의 각 컨트롤에 대한 `DLGTEMPLATE` 구조 및 데이터의 형태로 되어 있습니다.

### <a name="return-value"></a>Return Value

대화 상자가 만들어지고 성공적으로 초기화된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

멤버 `CreateIndirect` 함수는 대화 상자를 만들면 바로 반환됩니다.

부모 창을 만들 때 대화 상자가 나타나야 하는 경우 대화 상자 템플릿에서 WS_VISIBLE 스타일을 사용합니다. 그렇지 않으면 호출하여 `ShowWindow` 표시되도록 해야 합니다. 템플릿에서 다른 대화 상자 스타일을 지정하는 방법에 대한 자세한 내용은 Windows SDK의 [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) 구조를 참조하십시오.

함수를 `CWnd::DestroyWindow` 사용하여 `CreateIndirect` 함수에 의해 생성된 대화 상자를 삭제합니다.

ActiveX 컨트롤이 포함된 대화 상자에는 DLGINIT 리소스에 제공된 추가 정보가 필요합니다.

## <a name="cdialogdomodal"></a><a name="domodal"></a>CDialog::DoModal

이 멤버 함수를 호출하여 모달 대화 상자를 호출하고 완료되면 대화 상자 결과를 반환합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

대화 상자를 닫는 데 사용되는 [CDialog::EndDialog](#enddialog) 멤버 함수에 전달된 *nResult* 매개 변수의 값을 지정하는 **int** 값입니다. 반환 값은 함수가 대화 상자를 만들 수 없는 경우 -1, 또는 IDABORT 다른 오류가 발생 하는 경우, 이 경우 출력 창 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)에서 오류 정보를 포함 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 대화 상자가 활성화되어 있는 동안 사용자와의 모든 상호 작용을 처리합니다. 이것이 대화 상자 모달을 만드는 것입니다. 즉, 대화 상자가 닫혀야 사용자가 다른 창과 상호 작용할 수 없습니다.

사용자가 확인 또는 취소와 같은 대화 상자에서 푸시 버튼 중 하나를 클릭하면 [OnOK](#onok) 또는 [OnCancel과](#oncancel)같은 메시지 처리기 멤버 함수가 호출되어 대화 상자를 닫으려고 시도합니다. 기본 `OnOK` 멤버 함수는 대화 상자 데이터의 유효성을 검사하고 업데이트하고 결과 IDOK를 `OnCancel` 사용하여 대화 상자를 닫고, 기본 멤버 함수는 대화 상자 데이터의 유효성을 검사하거나 업데이트하지 않고 결과 IDCANCEL을 사용하여 대화 상자를 닫습니다. 이러한 메시지 처리기 함수를 재정의하여 동작을 변경할 수 있습니다.

> [!NOTE]
> `PreTranslateMessage`이제 모달 대화 상자 메시지 처리에 대 한 호출 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]

## <a name="cdialogenddialog"></a><a name="enddialog"></a>CDialog::끝디아로그

이 멤버 함수를 호출하여 모달 대화 상자를 종료합니다.

```cpp
void EndDialog(int nResult);
```

### <a name="parameters"></a>매개 변수

*nResult*<br/>
대화 상자에서 의 호출자에게 반환할 값을 `DoModal`포함합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 *nResult를* `DoModal`의 반환 값으로 반환합니다. 모달 대화 `EndDialog` 상자를 만들 때마다 처리를 완료하려면 이 함수를 사용해야 합니다.

`EndDialog` [OnInitDialog에서도](#oninitdialog)언제든지 호출할 수 있으며, 이 경우 대화 상자가 표시되기 전이나 입력 포커스가 설정되기 전에 대화 상자를 닫아야 합니다.

`EndDialog`대화 상자를 즉시 닫지 않습니다. 대신 현재 메시지 처리기가 반환되는 즉시 대화 상자를 닫도록 지시하는 플래그를 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]

[!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]

## <a name="cdialoggetdefid"></a><a name="getdefid"></a>시언로그::GetDefID

`GetDefID` 대화 상자에 대한 기본 푸시 버튼 컨트롤의 ID를 얻으려면 멤버 함수를 호출합니다.

```
DWORD GetDefID() const;
```

### <a name="return-value"></a>Return Value

32비트 값()입니다. `DWORD` 기본 푸시버튼에 ID 값이 있는 경우 고차 단어에는 DC_HASDEFID 포함되고 하위 순서 단어는 ID 값을 포함합니다. 기본 푸시버튼에 ID 값이 없는 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

이것은 일반적으로 확인 버튼입니다.

## <a name="cdialoggotodlgctrl"></a><a name="gotodlgctrl"></a>CDialog::고토들크툴

대화 상자에서 지정된 컨트롤로 포커스를 이동합니다.

```cpp
void GotoDlgCtrl(CWnd* pWndCtrl);
```

### <a name="parameters"></a>매개 변수

*pWndCtrl*<br/>
포커스를 수신할 창(컨트롤)을 식별합니다.

### <a name="remarks"></a>설명

*pWndCtrl로*전달할 컨트롤(자식 창)에 대한 포인터를 `CWnd::GetDlgItem` 얻으려면 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터를 반환하는 멤버 함수를 호출합니다.

### <a name="example"></a>예제

  [CWnd::GetDlg항목에](../../mfc/reference/cwnd-class.md#getdlgitem)대한 예제를 참조하십시오.

## <a name="cdialoginitmodalindirect"></a><a name="initmodalindirect"></a>CDialog::이니몰달 간접

이 멤버 함수를 호출하여 메모리에서 생성한 대화 상자 템플릿을 사용하여 모달 대화 상자 개체를 초기화합니다.

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
대화 상자를 만드는 데 사용되는 대화 상자 템플릿이 포함된 메모리를 가리킵니다. 이 템플릿은 Windows SDK에 설명된 대로 [DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate) 구조 및 제어 정보의 형태로 되어 있습니다.

*hDialogTemplate*<br/>
대화 상자 템플릿을 포함하는 전역 메모리에 대한 핸들을 포함합니다. 이 템플릿은 대화 상자의 각 컨트롤에 대한 `DLGTEMPLATE` 구조 및 데이터의 형태로 되어 있습니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 상위 또는 소유자 창 [개체(CWnd](../../mfc/reference/cwnd-class.md)형식)를 가리킵니다. NULL인 경우 대화 상자 개체의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

*lpDialogInit*<br/>
DLGINIT 리소스를 가리킵니다.

### <a name="return-value"></a>Return Value

대화 상자 개체를 만들고 성공적으로 초기화한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

모달 대화 상자를 간접적으로 만들려면 먼저 전역 메모리 블록을 할당하고 대화 상자 템플릿으로 채웁니다. 그런 다음 `CDialog` 빈 생성기를 호출하여 대화 상자 개체를 생성합니다. 다음으로, `InitModalIndirect` 메모리 내 대화 상자 템플릿에 핸들을 저장하려면 호출합니다. [DoModal](#domodal) 멤버 함수가 호출될 때 Windows 대화 상자가 만들어지고 나중에 표시됩니다.

ActiveX 컨트롤이 포함된 대화 상자에는 DLGINIT 리소스에 제공된 추가 정보가 필요합니다.

## <a name="cdialogmapdialogrect"></a><a name="mapdialogrect"></a>시언로그::맵디아로그렉트

호출을 사용하여 사각형의 대화 상자 단위를 화면 단위로 변환합니다.

```cpp
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
변환할 대화 상자 좌표를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체를 가리킵니다.

### <a name="remarks"></a>설명

대화 상자 단위는 대화 상자 텍스트에 사용되는 글꼴의 문자의 평균 너비와 높이에서 파생된 현재 대화 상자 기본 단위의 관점에서 표시됩니다. 하나의 수평 단위는 대화 상자 기본 너비 단위의 1/4이며, 하나의 수직 단위는 대화 상자 기본 높이 단위의 1/8입니다.

Windows `GetDialogBaseUnits` 함수는 시스템 글꼴에 대한 크기 정보를 반환하지만 리소스 정의 파일에서 DS_SETFONT 스타일을 사용하는 경우 각 대화 상자에 대해 다른 글꼴을 지정할 수 있습니다. Windows `MapDialogRect` 함수는 이 대화 상자에 적합한 글꼴을 사용합니다.

멤버 `MapDialogRect` 함수는 *lpRect의* 대화 상자 단위를 화면 단위(픽셀)로 대체하므로 사각형을 사용하여 대화 상자를 만들거나 상자 내에 컨트롤을 배치할 수 있습니다.

## <a name="cdialognextdlgctrl"></a><a name="nextdlgctrl"></a>CDialog::NextDlgCtrl

대화 상자의 다음 컨트롤로 포커스를 이동합니다.

```cpp
void NextDlgCtrl() const;
```

### <a name="remarks"></a>설명

포커스가 대화 상자의 마지막 컨트롤에 있으면 첫 번째 컨트롤로 이동합니다.

## <a name="cdialogoncancel"></a><a name="oncancel"></a>CDialog::OnCancel

프레임워크는 사용자가 **모달** 또는 모데리스 대화 상자에서 ESC 키 취소를 클릭하거나 누르면 이 메서드를 호출합니다.

```
virtual void OnCancel();
```

### <a name="remarks"></a>설명

사용자가 **취소를** 클릭하거나 ESC 키를 누르고 대화 상자를 닫을 때 이 메서드를 재정의하여 이전 데이터 복원과 같은 작업을 수행합니다. 기본값은 [EndDialog를](#enddialog) 호출하고 [DoModal이](#domodal) IDCANCEL을 반환하도록 하여 모달 대화 상자를 닫습니다.

모덜리스 대화 상자에서 **취소** 단추를 구현하는 경우 메서드를 `OnCancel` 재정의하고 그 안에 [DestroyWindow를](../../mfc/reference/cwnd-class.md#destroywindow) 호출해야 합니다. 기본 클래스 메서드를 호출 `EndDialog`하지 마십시오 호출 하기 때문에 대화 상자를 보이지 않게 하지만 삭제 하지 않습니다.

> [!NOTE]
> Windows XP에서 컴파일된 프로그램에서 `CFileDialog` 개체를 사용할 때는 이 메서드를 재정의할 수 없습니다. 자세한 `CFileDialog`내용은 [CFileDialog 클래스를](../../mfc/reference/cfiledialog-class.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]

## <a name="cdialogoninitdialog"></a><a name="oninitdialog"></a>CDialog::IninitDialog

이 메서드는 메시지에 대 `WM_INITDIALOG` 한 응답으로 호출 됩니다.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Return Value

응용 프로그램이 대화 상자의 컨트롤 중 하나에 입력 포커스를 설정했는지 여부를 지정합니다. 0이 아닌 값을 반환하는 경우 `OnInitDialog` Windows는 입력 포커스를 대화 상자의 첫 번째 컨트롤인 기본 위치로 설정합니다. 응용 프로그램은 대화 상자의 컨트롤 중 하나에 입력 포커스를 명시적으로 설정한 경우에만 0을 반환할 수 있습니다.

### <a name="remarks"></a>설명

Windows는 `WM_INITDIALOG` 대화 상자가 표시되기 직전에 발생하는 [만들기](#create) [직접](#createindirect)또는 [DoModal](#domodal) 호출 중에 대화 상자에 메시지를 보냅니다.

대화 상자가 초기화될 때 특수 처리를 수행하려는 경우 이 메서드를 재정의합니다. 재정의된 버전에서는 먼저 기본 클래스를 `OnInitDialog` 호출하지만 반환 값을 무시합니다. 일반적으로 재정의된 메서드에서 반환됩니다. `TRUE`

Windows는 `OnInitDialog` 모든 Microsoft Foundation 클래스 라이브러리 대화 상자에 공통적인 표준 전역 대화 상자 절차를 사용하여 함수를 호출합니다. 메시지 맵을 통해이 함수를 호출 하지 않습니다., 따라서이 메서드에 대 한 메시지 맵 항목이 필요 하지 않습니다.

> [!NOTE]
> Windows Vista 또는 이후 운영 `CFileDialog` 체제에서 컴파일된 프로그램에서 개체를 사용할 때는 이 메서드를 재정의할 수 없습니다. Windows Vista 및 `CFileDialog` 이후 변경 사항에 대한 자세한 내용은 [CFileDialog 클래스를](../../mfc/reference/cfiledialog-class.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]

## <a name="cdialogonok"></a><a name="onok"></a>CDialog::ONOK

사용자가 **확인** 단추(IDOK ID가 있는 단추)를 클릭할 때 호출됩니다.

```
virtual void OnOK();
```

### <a name="remarks"></a>설명

**확인** 버튼이 활성화될 때 작업을 수행하려면 이 메서드를 재정의합니다. 대화 상자에 자동 데이터 유효성 검사 및 교환이 포함된 경우 이 메서드의 기본 구현은 대화 상자 데이터의 유효성을 검사하고 응용 프로그램의 적절한 변수를 업데이트합니다.

모덜리스 대화 상자에서 **확인** 단추를 구현하는 경우 메서드를 `OnOK` 재정의하고 그 안에 [DestroyWindow를](../../mfc/reference/cwnd-class.md#destroywindow) 호출해야 합니다. 대화 상자를 보이지 않게 하지만 삭제하지 않는 [EndDialog를](#enddialog) 호출하기 때문에 기본 클래스 메서드를 호출하지 마십시오.

> [!NOTE]
> Windows XP에서 컴파일된 프로그램에서 `CFileDialog` 개체를 사용할 때는 이 메서드를 재정의할 수 없습니다. 자세한 `CFileDialog`내용은 [CFileDialog 클래스를](../../mfc/reference/cfiledialog-class.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]

## <a name="cdialogonsetfont"></a><a name="onsetfont"></a>시디로그::온셋글꼴

텍스트를 그릴 때 사용할 대화 상자 컨트롤글꼴을 지정합니다.

```
Virtual void OnSetFont(CFont* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
【인】 이 대화 상자의 모든 컨트롤에 대한 기본 글꼴로 사용되는 글꼴에 대한 포인터를 지정합니다.

### <a name="remarks"></a>설명

대화 상자는 지정된 글꼴을 모든 컨트롤의 기본값으로 사용합니다.

대화 상자 편집기는 일반적으로 대화 상자 템플릿 리소스의 일부로 대화 상자 글꼴을 설정합니다.

> [!NOTE]
> Windows Vista 또는 이후 운영 `CFileDialog` 체제에서 컴파일된 프로그램에서 개체를 사용할 때는 이 메서드를 재정의할 수 없습니다. Windows Vista 및 `CFileDialog` 이후 변경 사항에 대한 자세한 내용은 [CFileDialog 클래스를](../../mfc/reference/cfiledialog-class.md)참조하십시오.

## <a name="cdialogprevdlgctrl"></a><a name="prevdlgctrl"></a>CDialog::PrevDlgCtrl

대화 상자에서 이전 컨트롤에 포커스를 설정합니다.

```cpp
void PrevDlgCtrl() const;
```

### <a name="remarks"></a>설명

포커스가 대화 상자의 첫 번째 컨트롤에 있으면 상자의 마지막 컨트롤로 이동합니다.

## <a name="cdialogsetdefid"></a><a name="setdefid"></a>시디언그::세트데피드

대화 상자에 대한 기본 푸시 버튼 컨트롤을 변경합니다.

```cpp
void SetDefID(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
기본값이 될 푸시 버튼 컨트롤의 ID를 지정합니다.

## <a name="cdialogsethelpid"></a><a name="sethelpid"></a>CDialog::SetHelpID

대화 상자에 대한 컨텍스트 구분 도움말 ID를 설정합니다.

```cpp
void SetHelpID(UINT nIDR);
```

### <a name="parameters"></a>매개 변수

*nIDR*<br/>
상황에 맞는 도움말 ID를 지정합니다.

## <a name="see-also"></a>참조

[MFC Sample DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 DLGTEMPL](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
