---
title: 코크매니저 클래스
ms.date: 11/04/2016
f1_keywords:
- COccManager
- AFXOCC/COccManager
- AFXOCC/COccManager::CreateContainer
- AFXOCC/COccManager::CreateDlgControls
- AFXOCC/COccManager::CreateSite
- AFXOCC/COccManager::GetDefBtnCode
- AFXOCC/COccManager::IsDialogMessage
- AFXOCC/COccManager::IsLabelControl
- AFXOCC/COccManager::IsMatchingMnemonic
- AFXOCC/COccManager::OnEvent
- AFXOCC/COccManager::PostCreateDialog
- AFXOCC/COccManager::PreCreateDialog
- AFXOCC/COccManager::SetDefaultButton
- AFXOCC/COccManager::SplitDialogTemplate
helpviewer_keywords:
- COccManager [MFC], CreateContainer
- COccManager [MFC], CreateDlgControls
- COccManager [MFC], CreateSite
- COccManager [MFC], GetDefBtnCode
- COccManager [MFC], IsDialogMessage
- COccManager [MFC], IsLabelControl
- COccManager [MFC], IsMatchingMnemonic
- COccManager [MFC], OnEvent
- COccManager [MFC], PostCreateDialog
- COccManager [MFC], PreCreateDialog
- COccManager [MFC], SetDefaultButton
- COccManager [MFC], SplitDialogTemplate
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
ms.openlocfilehash: 5637a4709e90bb14caff3fe4e396487e62e213e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360356"
---
# <a name="coccmanager-class"></a>코크매니저 클래스

`COleControlContainer` 및 `COleControlSite` 개체로 구현된 다양한 사용자 지정 컨트롤 사이트를 관리합니다.

## <a name="syntax"></a>구문

```
class COccManager : public CNoTrackObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COccManager::만들기 컨테이너](#createcontainer)|`COleContainer` 개체를 만듭니다.|
|[COccManager::만들기Dlg컨트롤](#createdlgcontrols)|연결된 `COleContainer` 개체에서 호스팅하는 ActiveX 컨트롤을 만듭니다.|
|[COccManager::만들기사이트](#createsite)|`COleClientSite` 개체를 만듭니다.|
|[코크 매니저::겟데프브엔코드](#getdefbtncode)|기본 단추의 코드를 검색합니다.|
|[COccManager::IsDialogMessage](#isdialogmessage)|대화 메시지의 대상을 결정합니다.|
|[COccManager::IsLabelControl](#islabelcontrol)|지정된 컨트롤이 레이블 컨트롤인지 확인합니다.|
|[COccManager::이매칭 미네모닉](#ismatchingmnemonic)|현재 니모닉이 지정된 컨트롤의 니모닉과 일치하는지 확인합니다.|
|[코크 매니저::온이벤트](#onevent)|지정된 이벤트를 처리하려고 시도합니다.|
|[COccManager::PostCreateDialog](#postcreatedialog)|대화 상자를 만드는 동안 할당된 리소스를 해제합니다.|
|[COccManager::P리창조디아로그](#precreatedialog)|ActiveX 컨트롤에 대한 대화 상자 템플릿을 처리합니다.|
|[COccManager::설정 기본 버튼](#setdefaultbutton)|지정된 컨트롤의 기본 상태를 전환합니다.|
|[COccManager::분할 대화 상자 템플릿](#splitdialogtemplate)|기존 ActiveX 컨트롤을 지정된 대화 상자 템플릿의 공통 컨트롤과 분리합니다.|

## <a name="remarks"></a>설명

기본 클래스는 `CNoTrackObject`문서화되지 않은 기본 클래스입니다(AFXTLS에 있습니다. H)를 참조하십시오. MFC 프레임워크에서 사용하도록 설계된 `CNoTrackObject` 클래스에서 파생된 클래스는 메모리 누수 감지에서 제외됩니다. 에서 `CNoTrackObject`직접 파생하지 않는 것이 좋습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>요구 사항

**헤더:** afxocc.h

## <a name="coccmanagercreatecontainer"></a><a name="createcontainer"></a>COccManager::만들기 컨테이너

컨트롤 컨테이너를 만들기 위해 프레임워크에서 호출합니다.

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
사용자 지정 사이트 컨테이너와 연결된 창 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

새로 생성된 컨테이너에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

사용자 지정 사이트 만들기에 대한 자세한 내용은 [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite)을 참조하십시오.

## <a name="coccmanagercreatedlgcontrols"></a><a name="createdlgcontrols"></a>COccManager::만들기Dlg컨트롤

*pOccDialogInfo* 매개 변수에 의해 지정된 ActiveX 컨트롤을 만들려면 이 함수를 호출합니다.

```
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    LPCTSTR lpszResourceName,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);

virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    void* lpResource,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
대화 상자 개체의 부모에 대한 포인터입니다.

*lpszResourceName*<br/>
생성중인 리소스의 이름입니다.

*pOccDialogInfo*<br/>
대화 상자 개체를 만드는 데 사용되는 대화 상자 템플릿에 대한 포인터입니다.

*lpResource*<br/>
리소스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

컨트롤이 성공적으로 생성된 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="coccmanagercreatesite"></a><a name="createsite"></a>COccManager::만들기사이트

*pCtrlCont에*의해 가리키는 컨테이너에 의해 호스팅 되는 컨트롤 사이트를 만들 프레임 워크에 의해 호출 됩니다.

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>매개 변수

*pCtrlCont*<br/>
새 제어 사이트를 호스팅하는 제어 컨테이너에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

새로 만든 컨트롤 사이트에 대한 포인터입니다.

### <a name="remarks"></a>설명

[COleControlSite](../../mfc/reference/colecontrolsite-class.md)-derived 클래스를 사용하여 사용자 지정 제어 사이트를 만들려면 이 함수를 재정의합니다.

각 제어 컨테이너는 여러 사이트를 호스트할 수 있습니다. `CreateSite`에 대한 호출이 여러 개인 추가 사이트를 만듭니다.

## <a name="coccmanagergetdefbtncode"></a><a name="getdefbtncode"></a>코크 매니저::겟데프브엔코드

이 함수를 호출하여 컨트롤이 기본 푸시 버튼인지 확인합니다.

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
단추 컨트롤을 포함하는 창 개체입니다.

### <a name="return-value"></a>Return Value

해당 값은

- DLGC_DEFPUSHBUTTON 컨트롤은 대화 상자의 기본 단추입니다.

- DLGC_UNDEFPUSHBUTTON 컨트롤은 대화 상자의 기본 버튼이 아닙니다.

- **0** 컨트롤은 버튼이 아닙니다.

## <a name="coccmanagerisdialogmessage"></a><a name="isdialogmessage"></a>COccManager::IsDialogMessage

프레임워크에서 호출하여 메시지가 지정된 대화 상자용인지 여부를 확인하고 메시지가 있는 경우 메시지를 처리합니다.

```
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,
    LPMSG lpMsg);
```

### <a name="parameters"></a>매개 변수

*pWndDlg*<br/>
메시지의 의도된 대상 대화 상자에 대한 포인터입니다.

*lpMsg*<br/>
검사할 메시지가 `MSG` 포함된 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메시지가 처리되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

기본 `IsDialogMessage` 동작은 키보드 메시지를 확인하고 해당 대화 상자에 대한 선택으로 변환하는 것입니다. 예를 들어 TAB 키를 누르면 다음 컨트롤 또는 컨트롤 그룹을 선택합니다.

지정된 대화 상자에 전송된 메시지에 대한 사용자 지정 동작을 제공하려면 이 함수를 재정의합니다.

## <a name="coccmanagerislabelcontrol"></a><a name="islabelcontrol"></a>COccManager::IsLabelControl

이 함수를 호출하여 지정된 컨트롤이 레이블 컨트롤인지 확인합니다.

```
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
컨트롤을 포함하는 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

컨트롤이 레이블인 경우 0이 아닙니다. 그렇지 않으면 0

### <a name="remarks"></a>설명

레이블 컨트롤은 순서지정에 따라 컨트롤이 무엇이든 레이블처럼 작동하는 컨트롤입니다.

## <a name="coccmanagerismatchingmnemonic"></a><a name="ismatchingmnemonic"></a>COccManager::이매칭 미네모닉

이 함수를 호출하여 컨트롤로 표시되는 현재 니모닉 일치 항목이 있는지 확인합니다.

```
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,
    LPMSG lpMsg);

static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,
    LPMSG lpMsg);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
컨트롤을 포함하는 창에 대한 포인터입니다.

*lpMsg*<br/>
일치하는 니모닉을 포함하는 메시지에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

비영이 대조군과 일치하는 경우; 그렇지 않으면 0

### <a name="remarks"></a>설명

## <a name="coccmanageronevent"></a><a name="onevent"></a>코크 매니저::온이벤트

지정된 이벤트를 처리하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,
    UINT idCtrl,
    AFX_EVENT* pEvent,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>매개 변수

*pCmdTarget*<br/>
이벤트를 처리하려고 `CCmdTarget` 시도하는 개체에 대한 포인터

*idCtrl*<br/>
컨트롤의 리소스 ID입니다.

*p이벤트*<br/>
처리 중인 이벤트입니다.

*pHandlerInfo*<br/>
NULL이 아닌 `OnEvent` 경우 명령을 `pTarget` `pmf` 디스패치하는 `AFX_CMDHANDLERINFO` 대신 구조의 멤버와 멤버를 채웁니다. 일반적으로 이 매개 변수는 NULL이어야 합니다.

### <a name="return-value"></a>Return Value

이벤트가 처리된 경우 Nonzero( 그렇지 않으면 0).

### <a name="remarks"></a>설명

이 함수를 재정의하여 기본 이벤트 처리 프로세스를 사용자 지정합니다.

## <a name="coccmanagerprecreatedialog"></a><a name="precreatedialog"></a>COccManager::P리창조디아로그

실제 대화 상자를 만들기 전에 ActiveX 컨트롤에 대한 대화 상자 템플릿을 처리하기 위해 프레임워크에서 호출합니다.

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>매개 변수

*pOccDialogInfo*<br/>
대화 `_AFX_OCC_DIALOG_INFO` 상자 템플릿 및 대화 상자에서 호스팅하는 ActiveX 컨트롤에 대한 정보가 포함된 구조입니다.

*포리그템플릿*<br/>
대화 상자를 만드는 데 사용할 대화 상자 템플릿에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

대화 상자를 만드는 데 사용되는 대화 상자 템플릿 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본 동작은 `SplitDialogTemplate`에서 호출하여 ActiveX 컨트롤이 있는지 확인한 다음 결과 대화 상자 템플릿을 반환합니다.

이 함수를 재정의하여 ActiveX 컨트롤을 호스팅하는 대화 상자를 만드는 프로세스를 사용자 지정합니다.

## <a name="coccmanagerpostcreatedialog"></a><a name="postcreatedialog"></a>COccManager::PostCreateDialog

대화 상자 템플릿에 할당된 메모리를 확보하려면 프레임워크에서 호출합니다.

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>매개 변수

*pOccDialogInfo*<br/>
대화 `_AFX_OCC_DIALOG_INFO` 상자 템플릿 및 대화 상자에서 호스팅하는 ActiveX 컨트롤에 대한 정보가 포함된 구조입니다.

### <a name="remarks"></a>설명

이 메모리는 에 대한 `SplitDialogTemplate`호출에 의해 할당되었으며 대화 상자의 모든 호스팅된 ActiveX 컨트롤에 사용되었습니다.

이 함수를 재정의하여 대화 상자 개체에서 사용하는 리소스를 정리하는 프로세스를 사용자 지정합니다.

## <a name="coccmanagersetdefaultbutton"></a><a name="setdefaultbutton"></a>COccManager::설정 기본 버튼

이 함수를 호출하여 컨트롤을 기본 단추로 설정합니다.

```
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,
    BOOL bDefault);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
컨트롤을 포함하는 창에 대한 포인터입니다.

*bDefault*<br/>
컨트롤이 기본 단추가 되어야 하는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤에는 OLEMISC_ACTSLIKEBUTTON 상태 비트가 설정되어 있어야 합니다. OLEMISC 플래그에 대한 자세한 내용은 Windows SDK의 [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) 항목을 참조하십시오.

## <a name="coccmanagersplitdialogtemplate"></a><a name="splitdialogtemplate"></a>COccManager::분할 대화 상자 템플릿

일반적인 대화 상자 컨트롤에서 ActiveX 컨트롤을 분할 하는 프레임 워크에 의해 호출 됩니다.

```
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,
    DLGITEMTEMPLATE** ppOleDlgItems);
```

### <a name="parameters"></a>매개 변수

*템플릿*<br/>
검사할 대화 상자 템플릿에 대한 포인터입니다.

*ppOleDlg항목*<br/>
ActiveX 컨트롤인 대화 상자 항목에 대한 포인터 목록입니다.

### <a name="return-value"></a>Return Value

비ActiveX 컨트롤만 포함하는 대화 상자 템플릿 구조에 대한 포인터입니다. ActiveX 컨트롤이 없는 경우 NULL이 반환됩니다.

### <a name="remarks"></a>설명

ActiveX 컨트롤이 발견되면 템플릿이 분석되고 비ActiveX 컨트롤만 포함하는 새 템플릿이 만들어집니다. 이 과정에서 발견된 모든 ActiveX 컨트롤은 *ppOleDlgItems*에 추가됩니다.

템플릿에 ActiveX 컨트롤이 없는 경우 NULL이 *반환됩니다.*

> [!NOTE]
> 새 템플릿에 할당된 메모리가 `PostCreateDialog` 함수에서 해제됩니다.

이 함수를 재정의하여 이 프로세스를 사용자 지정합니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[콜레컨트롤사이트 클래스](../../mfc/reference/colecontrolsite-class.md)<br/>
[콜레컨트롤컨테이너 클래스](../../mfc/reference/colecontrolcontainer-class.md)
