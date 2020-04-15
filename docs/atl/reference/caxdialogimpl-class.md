---
title: CAxDialogImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl::AdviseSinkMap
- ATLWIN/ATL::CAxDialogImpl::Create
- ATLWIN/ATL::CAxDialogImpl::DestroyWindow
- ATLWIN/ATL::CAxDialogImpl::DoModal
- ATLWIN/ATL::CAxDialogImpl::EndDialog
- ATLWIN/ATL::CAxDialogImpl::GetDialogProc
- ATLWIN/ATL::CAxDialogImpl::GetIDD
- ATLWIN/ATL::CAxDialogImpl::IsDialogMessage
- ATLWIN/ATL::CAxDialogImpl::m_bModal
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
ms.openlocfilehash: d8e60a817d197f67c14318a7d50ddf796e570142
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318736"
---
# <a name="caxdialogimpl-class"></a>CAxDialogImpl 클래스

이 클래스는 ActiveX 컨트롤을 호스트하는 대화 상자(모달 또는 모데리스)를 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, class TBase = CWindow>
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `CAxDialogImpl`

*TBase*<br/>
에 대한 `CDialogImplBaseT`기본 창 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAxDialogImpl::조언싱크맵](#advisesinkmap)|이 메서드를 호출하여 개체의 싱크 맵 이벤트 맵에 있는 모든 항목에 대한 조언또는 조언을 해제합니다.|
|[CAxDialogImpl::만들기](#create)|이 메서드를 호출하여 모덜리스 대화 상자를 만듭니다.|
|[CAxDialogImpl::D에스트로이윈도우](#destroywindow)|모덜리스 대화 상자를 삭제하려면 이 메서드를 호출합니다.|
|[CAxDialogImpl::DoModal](#domodal)|이 메서드를 호출하여 모달 대화 상자를 만듭니다.|
|[CAxDialogImpl::EndDialog](#enddialog)|이 메서드를 호출하여 모달 대화 상자를 삭제합니다.|
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|콜백 함수에 대한 포인터를 얻으려면 이 메서드를 `DialogProc` 호출합니다.|
|[CAxDialogImpl::GetIDD](#getidd)|대화 상자 템플릿 리소스 ID를 얻으려면이 메서드를 호출 합니다.|
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|이 메서드를 호출하여 메시지가 이 대화 상자에 대한 것인지 확인하고 메시지가 있는 경우 메시지를 처리합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CAxDialogImpl::m_bModal](#m_bmodal)|디버그 빌드에만 존재 하며 대화 상자가 모달인 경우 true로 설정된 변수입니다.|

## <a name="remarks"></a>설명

`CAxDialogImpl`모달 또는 모덜리스 대화 상자를 만들 수 있습니다. `CAxDialogImpl`는 기본 메시지 맵을 사용하여 적절한 처리기로 메시지를 전달하는 대화 상자 프로시저를 제공합니다.

`CAxDialogImpl``CDialogImplBaseT`에서 파생되는 이 파생 은 차례로 *TBase* `CWindow`TBase(기본적으로) `CMessageMap`및 에서 파생됩니다.

클래스는 대화 상자 템플릿 리소스 ID를 지정하는 IDD 멤버를 정의해야 합니다. 예를 들어 **클래스 추가** 대화 상자를 사용하여 ATL 대화 상자 개체를 추가하면 클래스에 다음 줄이 자동으로 추가됩니다.

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]

ATL 대화 상자 마법사에 입력된 짧은 `MyDialog` **이름은** 어디에 있습니다.

자세한 내용은 [대화 상자 구현을](../../atl/implementing-a-dialog-box.md) 참조하십시오.

함께 `CAxDialogImpl` 만든 모달 대화 상자의 ActiveX 컨트롤은 가속기 키를 지원하지 않습니다. `CAxDialogImpl`으로 만든 대화 상자에서 가속기 키를 지원하려면 modeless 대화 상자를 만들고 자체 메시지 루프를 사용하여 [CAxDialogImpl::IsDialogMessage를](#isdialogmessage) 사용하여 가속기 키를 처리하기 위해 큐에서 메시지를 받은 후 메시지를 사용합니다.

자세한 `CAxDialogImpl`내용은 [ATL 제어 제약 FAQ를](../../atl/atl-control-containment-faq.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CDialogImplBaseT`

`CAxDialogImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="caxdialogimpladvisesinkmap"></a><a name="advisesinkmap"></a>CAxDialogImpl::조언싱크맵

이 메서드를 호출하여 개체의 싱크 맵 이벤트 맵에 있는 모든 항목에 대한 조언또는 조언을 해제합니다.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>매개 변수

*bAdvise*<br/>
모든 싱크 항목을 권장하는 경우 true로 설정합니다. 모든 싱크 항목을 조언하지 않을 경우 false입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="caxdialogimplcreate"></a><a name="create"></a>CAxDialogImpl::만들기

이 메서드를 호출하여 모덜리스 대화 상자를 만듭니다.

```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>매개 변수

*hWnd부모*<br/>
【인】 소유자 창에 대한 핸들입니다.

*dwInitParam*<br/>
【인】 WM_INITDIALOG 메시지의 *lParam* 매개 변수에서 대화 상자에 전달할 값을 지정합니다.

*RECT&*<br/>
이 매개 변수는 사용되지 않습니다. 이 매개 변수는 `CComControl`에 의해 전달됩니다.

### <a name="return-value"></a>Return Value

새로 만든 대화 상자의 핸들입니다.

### <a name="remarks"></a>설명

이 대화 상자는 개체에 `CAxDialogImpl` 자동으로 연결됩니다. 모달 대화 상자를 만들려면 [DoModal](#domodal)을 호출합니다.

두 번째 재정의는 [CComControl](../../atl/reference/ccomcontrol-class.md)에서 대화 상자를 사용할 수 있도록 만 제공됩니다.

## <a name="caxdialogimpldestroywindow"></a><a name="destroywindow"></a>CAxDialogImpl::D에스트로이윈도우

모덜리스 대화 상자를 삭제하려면 이 메서드를 호출합니다.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Return Value

TRUE 창이 성공적으로 소멸된 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

모달 `DestroyWindow` 대화 상자를 삭제하기 위해 호출하지 마십시오. 대신 [EndDialog를 호출합니다.](#enddialog)

## <a name="caxdialogimpldomodal"></a><a name="domodal"></a>CAxDialogImpl::DoModal

이 메서드를 호출하여 모달 대화 상자를 만듭니다.

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

성공하면 [EndDialog](#enddialog)에 대한 호출에 지정된 *nRetCode* 매개 변수의 값입니다. 그렇지 않으면 -1.

### <a name="remarks"></a>설명

이 대화 상자는 개체에 `CAxDialogImpl` 자동으로 연결됩니다.

모덜리스 대화 상자를 만들려면 [만들기를](#create)호출합니다.

## <a name="caxdialogimplenddialog"></a><a name="enddialog"></a>CAxDialogImpl::EndDialog

이 메서드를 호출하여 모달 대화 상자를 삭제합니다.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>매개 변수

*nRetCode*<br/>
【인】 [DoModal에서](#domodal)반환할 값입니다.

### <a name="return-value"></a>Return Value

대화 상자가 소멸된 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

`EndDialog`대화 상자 절차를 통해 호출해야 합니다. 대화 상자가 소멸된 후 Windows는 *nRetCode* 값을 대화 상자를 `DoModal`만든 에 대한 반환 값으로 사용합니다.

> [!NOTE]
> 모덜리스 `EndDialog` 대화 상자를 파괴하기 위해 호출하지 마십시오. 대신 [DestroyWindow를](#destroywindow) 호출합니다.

## <a name="caxdialogimplgetdialogproc"></a><a name="getdialogproc"></a>CAxDialogImpl::GetDialogProc

콜백 함수에 대한 포인터를 얻으려면 이 메서드를 `DialogProc` 호출합니다.

```
virtual DLGPROC GetDialogProc();
```

### <a name="return-value"></a>Return Value

콜백 함수에 `DialogProc` 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

이 `DialogProc` 함수는 응용 프로그램 정의 콜백 함수입니다.

## <a name="caxdialogimplgetidd"></a><a name="getidd"></a>CAxDialogImpl::GetIDD

대화 상자 템플릿 리소스 ID를 얻으려면이 메서드를 호출 합니다.

```
int GetIDD();
```

### <a name="return-value"></a>Return Value

대화 상자 템플릿 리소스 ID를 반환합니다.

## <a name="caxdialogimplisdialogmessage"></a><a name="isdialogmessage"></a>CAxDialogImpl::IsDialogMessage

이 메서드를 호출하여 메시지가 이 대화 상자에 대한 것인지 확인하고 메시지가 있는 경우 메시지를 처리합니다.

```
BOOL IsDialogMessage(LPMSG pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
검사할 메시지가 포함된 [MSG](/windows/win32/api/winuser/ns-winuser-msg) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 메시지가 처리된 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 메시지 루프 내에서 호출됩니다.

## <a name="caxdialogimplm_bmodal"></a><a name="m_bmodal"></a>CAxDialogImpl::m_bModal

디버그 빌드에만 존재 하며 대화 상자가 모달인 경우 true로 설정된 변수입니다.

```
bool m_bModal;
```

## <a name="see-also"></a>참고 항목

[CDialogImpl 클래스](../../atl/reference/cdialogimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
