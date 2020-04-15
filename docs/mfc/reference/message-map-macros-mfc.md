---
title: 메시지 맵 매크로(MFC)
ms.date: 03/27/2019
f1_keywords:
- AFXWIN/DECLARE_MESSAGE_MAP
- AFXWIN/BEGIN_MESSAGE_MAP
- AFXWIN/BEGIN_TEMPLATE_MESSAGE_MAP
- AFXWIN/END_MESSAGE_MAP
- AFXWIN/ON_COMMAND
- AFXWIN/ON_COMMAND_EX
- AFXWIN/ON_CONTROL
- AFXWIN/ON_MESSAGE
- AFXWIN/ON_OLECMD
- AFXWIN/ON_REGISTERED_MESSAGE
- AFXWIN/ON_REGISTERED_THREAD_MESSAGE
- AFXWIN/ON_THREAD_MESSAGE
- AFXWIN/ON_UPDATE_COMMAND_UI
- AFXWIN/ON_COMMAND_RANGE
- AFXWIN/ON_UPDATE_COMMAND_UI_RANGE
- AFXWIN/ON_CONTROL_RANGE
helpviewer_keywords:
- message map macros
- Windows messages [MFC], declaration
- demarcating Windows messages
- message maps [MFC], macros
- message maps [MFC], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
ms.openlocfilehash: 6e9291f0f39057403bc27c7fe4ff5ca5a82dfe3a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356591"
---
# <a name="message-map-macros-mfc"></a>메시지 맵 매크로(MFC)

메시지 맵을 지원하기 위해 MFC는 다음 매크로를 제공합니다.

### <a name="message-map-declaration-and-demarcation-macros"></a>메시지 맵 선언 및 구분 매크로

|||
|-|-|
|[DECLARE_MESSAGE_MAP](#declare_message_map)|메시지 맵이 클래스에서 메시지를 함수에 매핑하는 데 사용됩니다(클래스 선언에 사용해야 합니다).|
|[BEGIN_MESSAGE_MAP](#begin_message_map)|메시지 맵의 정의를 시작합니다(클래스 구현에서 사용해야 합니다).|
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_message_map)|단일 템플릿 인수를 포함하는 클래스 형식에서 메시지 맵의 정의를 시작합니다. |
|[END_MESSAGE_MAP](#end_message_map)|메시지 맵의 정의를 종료합니다(클래스 구현에서 사용해야 합니다).|

### <a name="message-mapping-macros"></a>메시지 매핑 매크로

|||
|-|-|
|[ON_COMMAND](#on_command)|지정된 명령 메시지를 처리할 함수를 나타냅니다.|
|[ON_COMMAND_EX](#on_command_ex)|지정된 명령 메시지를 처리할 함수를 나타냅니다.|
|[ON_CONTROL](#on_control)|지정된 제어 알림 메시지를 처리할 함수를 나타냅니다.|
|[ON_MESSAGE](#on_message)|사용자 정의 메시지를 처리할 함수를 나타냅니다.|
|[ON_OLECMD](#on_olecmd)|DocObject 또는 해당 컨테이너에서 메뉴 명령을 처리할 함수를 나타냅니다.|
|[ON_REGISTERED_MESSAGE](#on_registered_message)|등록된 사용자 정의 메시지를 처리할 함수를 나타냅니다.|
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|클래스가 있을 때 등록된 사용자 정의 메시지를 `CWinThread` 처리할 함수를 나타냅니다.|
|[ON_THREAD_MESSAGE](#on_thread_message)|클래스가 있을 때 사용자 정의 메시지를 처리할 `CWinThread` 함수를 나타냅니다.|
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|지정된 사용자 인터페이스 업데이트 명령 메시지를 처리할 함수를 나타냅니다.|

### <a name="message-map-range-macros"></a>메시지 맵 범위 매크로

|||
|-|-|
|[ON_COMMAND_RANGE](#on_command_range)|매크로에 처음 두 매개 변수에 지정된 명령 아이디의 범위를 처리할 함수를 나타냅니다.|
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|매크로에 처음 두 매개 변수에 지정된 명령 아이디의 범위를 처리할 업데이트 처리기를 나타냅니다.|
|[ON_CONTROL_RANGE](#on_control_range)|두 번째 및 세 번째 매개 변수에 지정된 컨트롤 아이디 범위에서 매크로에 이르는 알림을 처리할 함수를 나타냅니다. 첫 번째 매개 변수는 BN_CLICKED 같은 제어 알림 메시지입니다.|

메시지 맵, 메시지 맵 선언 및 구분 매크로 및 메시지 매핑 매크로에 대한 자세한 내용은 [메시지 맵](../../mfc/reference/message-maps-mfc.md) 및 메시지 처리 및 [매핑 항목을](../../mfc/message-handling-and-mapping.md)참조하십시오. 메시지 맵 범위에 대한 자세한 내용은 [메시지 맵 범위에 대한 처리기를](../../mfc/handlers-for-message-map-ranges.md)참조하십시오.

## <a name="begin_message_map"></a><a name="begin_message_map"></a>BEGIN_MESSAGE_MAP

메시지 맵의 정의를 시작합니다.

### <a name="syntax"></a>구문

```cpp
BEGIN_MESSAGE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
메시지 맵이 있는 클래스의 이름을 지정합니다.

*베이스 클래스*<br/>
의 기본 클래스의 이름을 *지정합니다Class*.

### <a name="remarks"></a>설명

클래스의 멤버 함수를 정의하는 구현(.cpp) 파일에서 BEGIN_MESSAGE_MAP 매크로로 메시지 맵을 시작한 다음 각 메시지 처리기 함수에 대한 매크로 항목을 추가하고 END_MESSAGE_MAP 매크로로 메시지 맵을 완료합니다.

메시지 맵에 대한 자세한 내용은 [메시지 맵을](message-maps-mfc.md) 참조하십시오.

### <a name="example"></a>예제

```cpp
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="begin_template_message_map"></a><a name="begin_template_message_map"></a>BEGIN_TEMPLATE_MESSAGE_MAP

단일 템플릿 인수를 포함하는 클래스 형식에서 메시지 맵의 정의를 시작합니다.

### <a name="syntax"></a>구문

```cpp
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
메시지 맵이 있는 클래스의 이름을 지정합니다.

*type_name*<br/>
클래스에 대해 지정된 템플릿 매개 변수의 이름입니다.

*베이스 클래스*<br/>
의 기본 클래스의 이름을 *지정합니다Class*.

### <a name="remarks"></a>설명

이 매크로는 [BEGIN_MESSAGE_MAP](message-map-macros-mfc.md#begin_message_map) 매크로와 유사합니다. 그러나 이 매크로는 단일 템플릿 인수를 포함하는 클래스를 위한 것입니다.

클래스의 메서드 구현 섹션에서 BEGIN_TEMPLATE_MESSAGE_MAP 매크로로 메시지 맵을 시작합니다. 그런 다음 표준 메시지 맵과 마찬가지로 각 메시지 처리기 메서드에 대해 매크로 항목을 추가합니다. BEGIN_MESSAGE_MAP 매크로와 마찬가지로 [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map) 매크로로 템플릿 메시지 맵을 완료합니다.

템플릿 클래스에 대한 메시지 맵 구현에 대한 자세한 내용은 [템플릿 클래스에 대한 메시지 맵 만들기](../how-to-create-a-message-map-for-a-template-class.md)방법을 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="declare_message_map"></a><a name="declare_message_map"></a>DECLARE_MESSAGE_MAP

클래스가 메시지 맵을 정의한다고 선언합니다. 프로그램의 `CCmdTarget`각 파생 클래스는 메시지를 처리하는 메시지 맵을 제공해야 합니다.

### <a name="syntax"></a>구문

```cpp
DECLARE_MESSAGE_MAP( )
```

### <a name="remarks"></a>설명

클래스 선언의 끝에 DECLARE_MESSAGE_MAP 매크로를 사용합니다. 그런 다음 클래스의 멤버 함수를 정의하는 .cpp 파일에서 BEGIN_MESSAGE_MAP 매크로, 각 메시지 처리기 함수에 대한 매크로 항목 및 END_MESSAGE_MAP 매크로를 사용합니다.

> [!NOTE]
> DECLARE_MESSAGE_MAP 후에 멤버를 선언하는 경우 새 액세스**유형(공개,** **비공개**또는 **보호)을**지정해야 합니다.

메시지 맵 및 DECLARE_MESSAGE_MAP 매크로에 대한 자세한 내용은 [메시지 처리 및 매핑 항목을](../../mfc/message-handling-and-mapping.md)참조하십시오.

### <a name="example"></a>예제

```cpp
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
```

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="end_message_map"></a><a name="end_message_map"></a>END_MESSAGE_MAP

메시지 맵의 정의를 종료합니다.

### <a name="syntax"></a>구문

```cpp
END_MESSAGE_MAP( )
```

### <a name="remarks"></a>설명

메시지 맵 및 END_MESSAGE_MAP 매크로에 대한 자세한 내용은 [메시지 처리 및 매핑 항목을](../../mfc/message-handling-and-mapping.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="on_command"></a><a name="on_command"></a>ON_COMMAND

이 매크로는 명령 메시지를 멤버 함수에 매핑합니다.

### <a name="syntax"></a>구문

```cpp
ON_COMMAND( commandId, memberFxn )
```

### <a name="parameters"></a>매개 변수

*Commandid*<br/>
명령 ID입니다.

*멤버Fxn*<br/>
명령이 매핑되는 메시지-처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

메뉴 항목 또는 도구 모음 단추와 같은 명령 사용자 인터페이스 개체에서 명령 메시지를 처리할 함수를 나타냅니다.

명령 대상 개체가 지정된 ID로 Windows WM_COMMAND 메시지를 수신하면 ON_COMMAND `memberFxn` 멤버 함수를 호출하여 메시지를 처리합니다.

ON_COMMAND 사용하여 단일 명령을 멤버 함수에 매핑합니다. [ON_COMMAND_RANGE](#on_command_range) 사용하여 명령 아이디 범위를 하나의 멤버 함수에 매핑합니다. 하나의 메시지 맵 항목만 지정된 명령 ID와 일치시킬 수 있습니다. 즉, 명령을 두 개 이상의 처리기에 매핑할 수 없습니다. 자세한 내용 및 예제는 [메시지 처리 및 매핑 항목을](../../mfc/message-handling-and-mapping.md)참조하십시오.

### <a name="example"></a>예제

```cpp
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>요구 사항

**헤더:** afxmsg_.h

## <a name="on_command_ex"></a><a name="on_command_ex"></a>ON_COMMAND_EX

확장된 명령 처리기 멤버 함수입니다.

### <a name="syntax"></a>구문

```cpp
ON_COMMAND_EX(commandId, memberFxn);
```

### <a name="parameters"></a>매개 변수

*Commandid*<br/>
명령 ID입니다.

*멤버Fxn*<br/>
명령이 매핑되는 메시지-처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

확장된 형태의 명령 메시지 처리기를 고급 용도로 사용할 수 있습니다. ON_COMMAND_EX 매크로는 이러한 메시지 처리기에 사용되며 [ON_COMMAND](message-map-macros-mfc.md#on_command) 기능의 수퍼세트를 제공합니다. 확장 된 명령 처리기 멤버 함수는 단일 매개 변수, 명령 ID를 포함 하는 UINT를 사용 하 고 BOOL을 반환 합니다. 반환 값은 TRUE로 명령이 처리되었음을 나타내야 합니다. 그렇지 않으면 라우팅은 다른 명령 대상 개체에 계속됩니다.

자세한 내용은 기술 노트 [TN006: 메시지 맵]tm006-메시지-maps.md)을 참조하십시오.

### <a name="requirements"></a>요구 사항

헤더 파일: afxmsg_.h

## <a name="on_control"></a><a name="on_control"></a>ON_CONTROL

사용자 지정 제어 알림 메시지를 처리할 함수를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
ON_CONTROL( wNotifyCode, commandId, memberFxn )
```

### <a name="parameters"></a>매개 변수

*wNotifyCode*<br/>
컨트롤의 알림 코드입니다.

*Commandid*<br/>
명령 ID입니다.

*멤버Fxn*<br/>
명령이 매핑되는 메시지-처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

컨트롤 알림 메시지는 컨트롤에서 부모 창으로 전송된 메시지입니다.

메시지 처리기 함수에 매핑되어야 하는 모든 제어 알림 메시지에 대해 메시지 맵에 정확히 하나의 ON_CONTROL 매크로 문이 있어야 합니다.

자세한 내용 및 예제는 [메시지 처리 및 매핑 항목을](../../mfc/message-handling-and-mapping.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxmsg_.h

## <a name="on_message"></a><a name="on_message"></a>ON_MESSAGE

사용자 정의 메시지를 처리할 함수를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
ON_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>매개 변수

*메시지*<br/>
메시지 ID입니다.

*멤버Fxn*<br/>
메시지가 매핑되는 메시지 처리기 함수의 이름입니다.

함수의 형식은 이어야 `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`합니다.

### <a name="remarks"></a>설명

사용자 정의 메시지는 표준 Windows WM_MESSAGE 메시지가 아닌 모든 메시지입니다. 메시지 ID를 선택할 때는 WM_USER(0x0400) ~ 0x7FFF 또는 WM_APP(0x8000) ~ 0xBFFF 범위 내에서 값을 사용해야 합니다. 메시지 아이디에 대한 자세한 내용은 [WM_APP](/windows/win32/winmsg/wm-app)를 참조하십시오.

메시지 처리기 함수에 매핑해야 하는 모든 사용자 정의 메시지에 대해 메시지 맵에 정확히 하나의 ON_MESSAGE 매크로 문이 있어야 합니다.

> [!NOTE]
> ON_MESSAGE 사용자 정의 메시지 외에도 덜 일반적인 Windows 메시지를 처리합니다. 자세한 내용은 [메시지 맵을](../../mfc/tn006-message-maps.md)참조하십시오.

자세한 내용 및 예제는 [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md) 및 사용자 정의 [처리기를](user-defined-handlers.md) 참조하십시오.

### <a name="example"></a>예제

```cpp
#define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd2, CWnd)
   ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()

// inside the class declaration
afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

LRESULT CMyWnd2::OnMyMessage(WPARAM wParam, LPARAM lParam)
{
   UNREFERENCED_PARAMETER(wParam);
   UNREFERENCED_PARAMETER(lParam);

   // Handle message here.

   return 0;
}
```

### <a name="requirements"></a>요구 사항

**헤더:** afxmsg_.h

## <a name="on_olecmd"></a><a name="on_olecmd"></a>ON_OLECMD

명령 디스패치 인터페이스를 `IOleCommandTarget`통해 명령을 라우팅합니다.

### <a name="syntax"></a>구문

```cpp
ON_OLECMD( pguid, olecmdid, commandId )
```

### <a name="parameters"></a>매개 변수

*pguid*<br/>
명령이 속한 명령 그룹의 식별자입니다. 표준 그룹에 NULL을 사용합니다.

*올렘디드*<br/>
OLE 명령의 식별자입니다.

*Commandid*<br/>
메뉴를 실행하기 위해 ID, 도구 모음 ID, 단추 ID 또는 명령을 실행하는 리소스 또는 개체의 기타 ID입니다.

### <a name="remarks"></a>설명

`IOleCommandTarget`컨테이너는 DocObject의 사용자 인터페이스에서 시작되는 명령을 수신할 수 있으며, 컨테이너가 동일한 명령(예: 파일 메뉴의 새 명령, 열기, SaveAs 및 인쇄, 복사, 붙여넣기, 수행 취소 등)을 DocObject로 보낼 수 있습니다.

`IOleCommandTarget`OLE 자동화보다 `IDispatch`간단합니다. `IOleCommandTarget`인수가 거의 없고 형식 정보가 관련되지 않은 표준 명령 집합에 전적으로 의존합니다(명령 인수에 대한 형식 안전도 감소). 인수로 명령을 디스패치해야 하는 경우 [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)를 사용합니다.

`IOleCommandTarget` 표준 메뉴 명령은 다음 매크로에서 MFC에 의해 구현되었습니다.

**ON_OLECMD_CLEARSELECTION ()**

지우기 편집 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`

**ON_OLECMD_COPY ()**

복사 편집 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`

**ON_OLECMD_CUT ()**

잘라내기 편집 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`

**ON_OLECMD_NEW ()**

새 파일 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`

**ON_OLECMD_OPEN () )**

파일 열기 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`

**ON_OLECMD_PAGESETUP ()**

파일 페이지 설치 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`

**ON_OLECMD_PASTE () )**

붙여넣기 편집 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`

**ON_OLECMD_PASTESPECIAL () )**

특수 편집 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`

**ON_OLECMD_PRINT ()**

파일 인쇄 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`

**ON_OLECMD_PRINTPREVIEW ()**

파일 인쇄 미리 보기 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`

**ON_OLECMD_REDO ()**

다시 편집 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`

**ON_OLECMD_SAVE ()**

파일 저장 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`

**ON_OLECMD_SAVE_AS ()**

파일 저장 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`

**ON_OLECMD_SAVE_COPY_AS ()**

파일 저장 복사를 명령으로 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`

**ON_OLECMD_SELECTALL ()**

모두 선택 선택 편집 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`

**ON_OLECMD_UNDO ()**

수행 취소 편집 명령을 디스패치합니다. 다음과 같이 구현됩니다.

`ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`

### <a name="requirements"></a>요구 사항

**헤더:** afxdocob.h

## <a name="on_registered_message"></a><a name="on_registered_message"></a>ON_REGISTERED_MESSAGE

Windows `RegisterWindowMessage` 함수는 시스템 전체에서 고유하게 보장되는 새 창 메시지를 정의하는 데 사용됩니다.

### <a name="syntax"></a>구문

```cpp
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )
```

### <a name="parameters"></a>매개 변수

*n메시지변수*<br/>
등록된 창 메시지 ID 변수입니다.

*멤버Fxn*<br/>
메시지가 매핑되는 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

이 매크로는 등록된 메시지를 처리할 함수를 나타냅니다.

자세한 내용 및 예제는 [메시지 처리 및 매핑 항목을](../../mfc/message-handling-and-mapping.md)참조하십시오.

### <a name="example"></a>예제

```cpp
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));

BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>요구 사항

**헤더:** afxmsg_.h

## <a name="on_registered_thread_message"></a><a name="on_registered_thread_message"></a>ON_REGISTERED_THREAD_MESSAGE

Windows RegisterWindowMessage 함수에 의해 등록된 메시지를 처리할 함수를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )
```

### <a name="parameters"></a>매개 변수

*n메시지변수*<br/>
등록된 창 메시지 ID 변수입니다.

*멤버Fxn*<br/>
메시지가 매핑되는 CWinThread 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

RegisterWindowMessage는 시스템 전체에서 고유하게 보장되는 새 창 메시지를 정의하는 데 사용됩니다. ON_REGISTERED_THREAD_MESSAGE CWinThread 클래스가 있을 때 ON_REGISTERED_MESSAGE 대신 사용해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxmsg_.h

## <a name="on_thread_message"></a><a name="on_thread_message"></a>ON_THREAD_MESSAGE

사용자 정의 메시지를 처리할 함수를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
ON_THREAD_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>매개 변수

*메시지*<br/>
메시지 ID입니다.

*멤버Fxn*<br/>
메시지가 매핑되는 `CWinThread`-message-handler 함수의 이름입니다.

### <a name="remarks"></a>설명

ON_THREAD_MESSAGE `CWinThread` 클래스가 있을 때 ON_MESSAGE 대신 사용해야 합니다. 사용자 정의 메시지는 표준 Windows WM_MESSAGE 메시지가 아닌 모든 메시지입니다. 메시지 처리기 함수에 매핑되어야 하는 모든 사용자 정의 메시지에 대해 메시지 맵에 정확히 하나의 ON_THREAD_MESSAGE 매크로 문이 있어야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="on_update_command_ui"></a><a name="on_update_command_ui"></a>On_update_command_ui

이 매크로는 사용자 인터페이스 업데이트 명령 메시지를 처리할 함수를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
ON_UPDATE_COMMAND_UI( messageId, memberFxn )
```

### <a name="parameters"></a>매개 변수

*메시지 ID*<br/>
메시지 ID입니다.

*멤버Fxn*<br/>
메시지가 매핑되는 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

메시지 처리기 함수에 매핑되어야 하는 모든 사용자 인터페이스 업데이트 명령에 대해 메시지 맵에 정확히 하나의 ON_UPDATE_COMMAND_UI 매크로 문이 있어야 합니다.

자세한 내용 및 예제는 [메시지 처리 및 매핑 항목을](../../mfc/message-handling-and-mapping.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="on_command_range"></a><a name="on_command_range"></a>ON_COMMAND_RANGE

이 매크로를 사용하여 연속된 명령 아이디 범위를 단일 메시지 처리기 함수에 매핑합니다.

### <a name="syntax"></a>구문

```cpp
ON_COMMAND_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>매개 변수

*id1*<br/>
명령 ID의 연속 범위의 시작 부분에 명령 ID입니다.

*id2*<br/>
명령 ID의 연속 범위 끝에 명령 ID입니다.

*멤버Fxn*<br/>
명령이 매핑되는 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

ID 범위는 *id1에서* 시작하여 *id2로*끝납니다.

ON_COMMAND_RANGE 사용하여 명령 아이디 범위를 하나의 멤버 함수에 매핑합니다. [ON_COMMAND](#on_command) 사용하여 단일 명령을 멤버 함수에 매핑합니다. 하나의 메시지 맵 항목만 지정된 명령 ID와 일치시킬 수 있습니다. 즉, 명령을 두 개 이상의 처리기에 매핑할 수 없습니다. 메시지 범위 매핑에 대한 자세한 내용은 [메시지 맵 범위에 대한 처리기를](../../mfc/handlers-for-message-map-ranges.md)참조하십시오.

메시지 맵 범위에 대한 자동 지원이 없으므로 매크로를 직접 배치해야 합니다.

### <a name="example"></a>예제

```cpp
// The code fragment below shows how to use ON_COMMAND_RANGE macro
// to map a contiguous range of command IDs to a single message
// handler function (i.e. OnRangeCmds() in the sample below). In
// addition, it also shows how to use CheckMenuRadioItem() to check a
// selected menu item and makes it a radio item.

BEGIN_MESSAGE_MAP(CChildFrame, CMDIChildWnd)
   ON_COMMAND_RANGE(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, &CChildFrame::OnRangeCmds)
END_MESSAGE_MAP()

void CChildFrame::OnRangeCmds(UINT nID)
{
   CMenu* mmenu = AfxGetMainWnd()->GetMenu();
   CMenu* submenu = mmenu->GetSubMenu(5);
   submenu->CheckMenuRadioItem(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3,
      nID, MF_BYCOMMAND);
}
```

### <a name="requirements"></a>요구 사항

**헤더:** afxmsg_.h

## <a name="on_update_command_ui_range"></a><a name="on_update_command_ui_range"></a>ON_UPDATE_COMMAND_UI_RANGE

연속된 범위의 명령 아이디를 단일 업데이트 메시지 처리기 함수에 매핑합니다.

### <a name="syntax"></a>구문

```cpp
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>매개 변수

*id1*<br/>
명령 ID의 연속 범위의 시작 부분에 명령 ID입니다.

*id2*<br/>
명령 ID의 연속 범위 끝에 명령 ID입니다.

*멤버Fxn*<br/>
명령이 매핑되는 업데이트 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

업데이트 메시지 처리기는 명령과 연관된 메뉴 항목 및 도구 모음 단추의 상태를 업데이트합니다. ID 범위는 *id1에서* 시작하여 *id2로*끝납니다.

메시지 맵 범위에 대한 자동 지원이 없으므로 매크로를 직접 배치해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxmsg_.h

## <a name="on_control_range"></a><a name="on_control_range"></a>ON_CONTROL_RANGE

이 매크로를 사용하여 BN_CLICKED 같은 지정된 Windows 알림 메시지에 대한 단일 메시지 처리기 함수에 연속적인 제어 아이디 범위를 매핑합니다.

### <a name="syntax"></a>구문

```cpp
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )
```

### <a name="parameters"></a>매개 변수

*wNotifyCode*<br/>
처리기가 응답하는 알림 코드입니다.

*id1*<br/>
연속된 범위의 컨트롤 ID를 시작할 때 명령 ID입니다.

*id2*<br/>
연속된 제어 ID 범위의 끝에 있는 명령 ID입니다.

*멤버Fxn*<br/>
컨트롤이 매핑되는 메시지 처리기 함수의 이름입니다.

### <a name="remarks"></a>설명

ID 범위는 *id1에서* 시작하여 *id2로*끝납니다. 매핑된 컨트롤에서 오는 지정된 알림에 대해 처리기가 호출됩니다.

메시지 맵 범위에 대한 자동 지원이 없으므로 매크로를 직접 배치해야 합니다.

제어 아이디 범위에 대한 처리기 함수 구현에 대한 자세한 내용은 [메시지 맵 범위에 대한 처리기를](../../mfc/handlers-for-message-map-ranges.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxmsg_.h

## <a name="see-also"></a>참고 항목

[ON_COMMAND](message-map-macros-mfc.md#on_command)<br/>
[TN006: 메시지 맵](../tn006-message-maps.md)<br/>
[콜레CmdUI 클래스](colecmdui-class.md)<br/>
[콜레서버독::오넥세올레Cmd](coleserverdoc-class.md#onexecolecmd)<br/>
[레지스터 윈도우 메시지](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew)<br/>
[사용자 정의 처리기](user-defined-handlers.md)<br/>
[CCmdUI 클래스](ccmdui-class.md)
