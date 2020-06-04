---
title: CDialogImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
ms.openlocfilehash: d5ab7293f73429a93c3fcab243c2e34d3c78f28a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747712"
---
# <a name="cdialogimpl-class"></a>CDialogImpl 클래스

이 클래스는 모달 또는 모데리스 대화 상자를 만드는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `CDialogImpl`

*TBase*<br/>
새 클래스의 기본 클래스입니다. 기본 기본 클래스는 [CWindow](../../atl/reference/cwindow-class.md)입니다.

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[만들기](#create)|모덜리스 대화 상자를 만듭니다.|
|[파괴창](#destroywindow)|모덜리스 대화 상자를 삭제합니다.|
|[Domodal](#domodal)|모달 대화 상자를 만듭니다.|
|[엔드디아로그](#enddialog)|모달 대화 상자를 삭제합니다.|

### <a name="cdialogimplbaset-methods"></a>클리클로그임프베이스T 방법

|||
|-|-|
|[겟디아로그프락](#getdialogproc)|현재 대화 상자 프로시저를 반환합니다.|
|[맵디아로그렉트](#mapdialogrect)|지정된 사각형의 대화 상자 단위를 화면 단위(픽셀)에 매핑합니다.|
|[OnFinalMessage](#onfinalmessage)|마지막 메시지를 받은 후 호출되는 일반적으로 WM_NCDESTROY.|

### <a name="static-functions"></a>정적 함수

|||
|-|-|
|[대화프랭크](#dialogproc)|대화 상자로 전송된 메시지를 처리합니다.|
|[스타트디아로그프락](#startdialogproc)|대화 상자로 전송된 메시지를 처리하기 위해 첫 번째 메시지가 수신될 때 호출됩니다.|

## <a name="remarks"></a>설명

함께 `CDialogImpl` 모달 또는 모덜리스 대화 상자를 만들 수 있습니다. `CDialogImpl`는 기본 메시지 맵을 사용하여 적절한 처리기로 메시지를 전달하는 대화 상자 프로시저를 제공합니다.

기본 클래스 소멸자는 `~CWindowImplRoot` 개체를 파괴하기 전에 창이 사라졌음을 확인합니다.

`CDialogImpl``CDialogImplBaseT`에서 파생됩니다. `CWindowImplRoot`

> [!NOTE]
> 클래스는 대화 `IDD` 상자 템플릿 리소스 ID를 지정하는 멤버를 정의해야 합니다. 예를 들어 ATL 프로젝트 마법사는 클래스에 다음 줄을 자동으로 추가합니다.

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

마법사의 **이름** 페이지에 입력된 짧은 **이름은** 어디에 `MyDlg` 있습니다.

|항목|참조|
|--------------------------------|---------|
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|
|ATL에서 대화 상자 사용|[ATL 윈도우 클래스](../../atl/atl-window-classes.md)|
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|
|대화 상자|[Windows](/windows/win32/dlgbox/dialog-boxes) SDK의 대화 상자 및 후속 항목|

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="cdialogimplcreate"></a><a name="create"></a>CDialogImpl::만들기

모덜리스 대화 상자를 만듭니다.

```
HWND Create(
    HWND hWndParent,
    LPARAM dwInitParam = NULL );

HWND Create(
    HWND hWndParent,
    RECT&,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>매개 변수

*hWnd부모*<br/>
【인】 소유자 창에 대한 핸들입니다.

**RECT&** *rect* [in] 대화 상자의 크기와 위치를 지정하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조입니다.

*dwInitParam*<br/>
【인】 WM_INITDIALOG 메시지의 *lParam* 매개 변수에서 대화 상자에 전달할 값을 지정합니다.

### <a name="return-value"></a>Return Value

새로 만든 대화 상자의 핸들입니다.

### <a name="remarks"></a>설명

이 대화 상자는 개체에 `CDialogImpl` 자동으로 연결됩니다. 모달 대화 상자를 만들려면 [DoModal](#domodal)을 호출합니다. 위의 두 번째 재정의는 [CComControl](../../atl/reference/ccomcontrol-class.md)에서만 사용됩니다.

## <a name="cdialogimpldestroywindow"></a><a name="destroywindow"></a>시딜로그임플::D에스트로이윈도우

모덜리스 대화 상자를 삭제합니다.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Return Value

대화 상자가 성공적으로 소멸된 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

대화 상자가 성공적으로 소멸된 경우 TRUE를 반환합니다. 그렇지 않으면 거짓.

## <a name="cdialogimpldialogproc"></a><a name="dialogproc"></a>시디아로임프::D

이 정적 함수는 대화 상자 프로시저를 구현합니다.

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
【인】 대화 상자의 핸들입니다.

*uMsg*<br/>
【인】 대화 상자로 전송된 메시지입니다.

*wParam*<br/>
【인】 추가 메시지 관련 정보입니다.

*lParam*<br/>
【인】 추가 메시지 관련 정보입니다.

### <a name="return-value"></a>Return Value

TRUE 메시지가 처리되는 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

`DialogProc`는 기본 메시지 맵을 사용하여 적절한 처리기로 메시지를 배달합니다.

메시지를 처리하기 `DialogProc` 위한 다른 메커니즘을 제공하기 위해 재정의할 수 있습니다.

## <a name="cdialogimpldomodal"></a><a name="domodal"></a>시클로그임플::D오모달

모달 대화 상자를 만듭니다.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>매개 변수

*hWnd부모*<br/>
【인】 소유자 창에 대한 핸들입니다. 기본값은 [GetActiveWindow](/windows/win32/api/winuser/nf-winuser-getactivewindow) Win32 함수의 반환 값입니다.

*dwInitParam*<br/>
【인】 WM_INITDIALOG 메시지의 *lParam* 매개 변수에서 대화 상자에 전달할 값을 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 [EndDialog](#enddialog)에 대한 호출에 지정된 *nRetCode* 매개 변수의 값입니다. 그렇지 않으면 -1입니다.

### <a name="remarks"></a>설명

이 대화 상자는 개체에 `CDialogImpl` 자동으로 연결됩니다.

모덜리스 대화 상자를 만들려면 [만들기를](#create)호출합니다.

## <a name="cdialogimplenddialog"></a><a name="enddialog"></a>시딜로그임플::엔드디아로그

모달 대화 상자를 삭제합니다.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>매개 변수

*nRetCode*<br/>
【인】 [CDialogImpl::DoModal에서](#domodal)반환할 값입니다.

### <a name="return-value"></a>Return Value

대화 상자가 소멸된 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

`EndDialog`대화 상자 절차를 통해 호출해야 합니다. 대화 상자가 소멸된 후 Windows는 *nRetCode* 값을 대화 상자를 `DoModal`만든 에 대한 반환 값으로 사용합니다.

> [!NOTE]
> 모덜리스 `EndDialog` 대화 상자를 파괴하기 위해 호출하지 마십시오. 대신 [CWindow::DestroyWindow에](../../atl/reference/cwindow-class.md#destroywindow) 전화하십시오.

## <a name="cdialogimplgetdialogproc"></a><a name="getdialogproc"></a>시딜로그임플::겟디아로그프로크

반환 `DialogProc`, 현재 대화 상자 프로시저입니다.

```
virtual WNDPROC GetDialogProc();
```

### <a name="return-value"></a>Return Value

현재 대화 상자 절차입니다.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 대화 상자 프로시저를 사용자 고유의 것으로 바꿉꿉습니다.

## <a name="cdialogimplmapdialogrect"></a><a name="mapdialogrect"></a>시딜로그임플:::맵디아로그렉트

지정된 사각형의 대화 상자 단위를 화면 단위(픽셀)로 변환합니다.

```
BOOL MapDialogRect(LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
업데이트 영역을 둘러싸는 `CRect` 업데이트의 클라이언트 좌표를 수신하는 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

업데이트가 성공하면 0이 아닙니다. 업데이트가 실패하면 0입니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.

### <a name="remarks"></a>설명

이 함수는 지정된 `RECT` 구조의 좌표를 변환된 좌표로 대체하므로 구조가 대화 상자를 만들거나 대화 상자 내에 컨트롤을 배치하는 데 사용할 수 있습니다.

## <a name="cdialogimplonfinalmessage"></a><a name="onfinalmessage"></a>시클로그임플::온 파이널 메시지

마지막 메시지(일반적으로)를 `WM_NCDESTROY`받은 후 호출됩니다.

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
【인】 파괴되는 창에 대한 핸들입니다.

### <a name="remarks"></a>설명

창 소멸 시 개체를 자동으로 삭제하려면 **이** 삭제를 호출할 수 있습니다.

## <a name="cdialogimplstartdialogproc"></a><a name="startdialogproc"></a>시딜로그임플::시작디아로그프로크

첫 번째 메시지가 수신될 때 한 번만 호출되어 대화 상자로 전송된 메시지를 처리합니다.

```
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
【인】 대화 상자의 핸들입니다.

*uMsg*<br/>
【인】 대화 상자로 전송된 메시지입니다.

*wParam*<br/>
【인】 추가 메시지 관련 정보입니다.

*lParam*<br/>
【인】 추가 메시지 관련 정보입니다.

### <a name="return-value"></a>Return Value

창 프로시저입니다.

### <a name="remarks"></a>설명

에 대한 초기 `StartDialogProc` `DialogProc` 호출 이후에는 대화 상자 프로시저로 설정되고 추가 호출이 진행됩니다.

## <a name="see-also"></a>참조

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
