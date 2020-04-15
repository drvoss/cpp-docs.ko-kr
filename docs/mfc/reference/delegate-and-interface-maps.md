---
title: 위임 및 인터페이스 맵 매크로(MFC)
ms.date: 03/30/2017
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
ms.openlocfilehash: e08597d024f5e3a74dcf47363ad3de0aa60cf6c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365831"
---
# <a name="delegate-and-interface-map-macros"></a>대리자 및 인터페이스 맵 매크로

MFC는 대리자 및 인터페이스 맵에 대해 다음 매크로를 지원합니다.

|||
|-|-|
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|대리자 맵을 시작합니다.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|인터페이스된 맵의 정의를 시작합니다.|
|[CommandHandler 대리자](#commandhandler)|명령 소스에 콜백 메서드를 등록합니다.  |
|[END_DELEGATE_MAP](#end_delegate_map)|대리자 맵을 종료합니다.|
|[END_INTERFACE_MAP](#end_interface_map)|구현 파일에서 인터페이스 맵을 종료합니다. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|대리자 맵에 항목을 만듭니다.|
|[INTERFACE_PART](#interface_part)|개체가 지원하는 각 인터페이스에 대해 BEGIN_INTERFACE_MAP 매크로와 END_INTERFACE_MAP 매크로 사이에 사용됩니다.|
|[MAKE_DELEGATE](#make_delegate)|이벤트 처리기를 관리되는 컨트롤에 연결합니다.|

## <a name="begin_delegate_map"></a><a name="begin_delegate_map"></a>BEGIN_DELEGATE_MAP

대리자 맵을 시작합니다.

### <a name="syntax"></a>구문

```
BEGIN_DELEGATE_MAP(  CLASS );
```

### <a name="parameters"></a>매개 변수

*클래스*<br/>
관리되는 컨트롤이 호스트되는 클래스입니다.

### <a name="remarks"></a>설명

이 매크로는 대리자 맵을 구성하는 대리자 항목 목록의 시작을 표시합니다. 이 매크로가 사용되는 방법의 예는 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** msclr\event.h

## <a name="begin_interface_map"></a><a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP

구현 파일에 사용될 때 인터페이스된 맵의 정의를 시작합니다.

### <a name="syntax"></a>구문

```
BEGIN_INTERFACE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
인터페이스 맵을 정의할 클래스

*베이스 클래스*<br/>
*클래스에서* 파생 되는 클래스입니다.

### <a name="remarks"></a>설명

구현되는 각 인터페이스에 대해 하나 이상의 INTERFACE_PART 매크로 호출이 있습니다. 클래스가 사용하는 각 집계에 대해 매크로 호출이 하나 INTERFACE_AGGREGATE.

인터페이스 맵에 대한 자세한 내용은 [기술 참고 38을](../tn038-mfc-ole-iunknown-implementation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="commandhandler-delegate"></a><a name="commandhandler"></a>명령 처리기 대리자

명령 소스에 콜백 메서드를 등록합니다.

### <a name="syntax"></a>구문

```
delegate void CommandHandler(  UINT^ cmdID  );
```

### <a name="parameters"></a>매개 변수

*Cmdid*<br/>
명령 ID입니다.

### <a name="remarks"></a>설명

이 대리자는 명령 원본에 콜백 메서드를 등록합니다. 명령 소스 개체에 대리자를 추가하면 콜백 메서드는 지정된 원본에서 오는 명령에 대한 처리기가 됩니다.

자세한 내용은 [Windows 양식 컨트롤에 명령 라우팅 추가 방법: 를 참조하세요.](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

Windows 양식 사용에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h (어셈블리 atlmfc\lib\mfcmifc80.dll에 정의)

## <a name="commanduihandler"></a><a name="commanduihandler"></a>커맨드UI핸들러

사용자 인터페이스 업데이트 명령 메시지와 콜백 메서드를 등록합니다.

### <a name="syntax"></a>구문

```
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);
```

### <a name="parameters"></a>매개 변수

*Cmdid*<br/>
명령 ID입니다.

*cmdui*<br/>
명령 메시지 ID입니다.

### <a name="remarks"></a>설명

이 대리자는 사용자 인터페이스 업데이트 명령 메시지와 함께 콜백 메서드를 등록합니다. `CommandUIHandler`이 대리자가 사용자 인터페이스 개체 업데이트 명령과 함께 사용된다는 점을 제외하면 [CommandHandler와](#commandhandler) 유사합니다. 사용자 인터페이스 업데이트 명령은 메시지 처리기 메서드와 일대일로 매핑되어야 합니다.

Windows 양식 사용에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h (어셈블리 atlmfc\lib\mfcmifc80.dll에 정의)

## <a name="end_delegate_map"></a><a name="end_delegate_map"></a>END_DELEGATE_MAP

대리자 맵을 종료합니다.

### <a name="syntax"></a>구문

```
END_DELEGATE_MAP();
```

### <a name="remarks"></a>설명

이 매크로는 대리자 맵을 구성하는 대리자 항목 목록의 끝을 표시합니다. 이 매크로가 사용되는 방법의 예는 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** msclr\event.h

## <a name="end_interface_map"></a><a name="end_interface_map"></a>END_INTERFACE_MAP

구현 파일에서 인터페이스 맵을 종료합니다.

### <a name="syntax"></a>구문

```
END_INTERFACE_MAP( )
```

### <a name="remarks"></a>설명

인터페이스 맵에 대한 자세한 내용은 [기술 참고 38을](../tn038-mfc-ole-iunknown-implementation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="event_delegate_entry"></a><a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY

대리자 맵에 항목을 만듭니다.

### <a name="syntax"></a>구문

```
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);
```

### <a name="parameters"></a>매개 변수

*멤버*<br/>
컨트롤에 연결할 이벤트 처리기 메서드입니다.

*ARG0*<br/>
와 같은 `Object^`관리되는 이벤트 처리기 메서드의 첫 번째 인수입니다.

*ARG1*<br/>
와 같은 `EventArgs^`관리되는 이벤트 처리기 메서드의 두 번째 인수입니다.

### <a name="remarks"></a>설명

대리자 맵의 각 항목은 [MAKE_DELEGATE](#make_delegate)에서 만든 관리되는 이벤트 처리기 대리자에 해당합니다.

### <a name="example"></a>예제

다음 코드 예제에서는 EVENT_DELEGATE_ENTRY 사용하여 `OnClick` 이벤트 처리기에 대한 대리자 맵에 항목을 만드는 방법을 보여 주며 있습니다. 또한 MAKE_DELEGATE 코드 예제를 참조하십시오. 자세한 내용은 [네이티브 C++ 클래스에서 Windows 양식 이벤트를 싱크하는 방법을](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)참조하십시오.

```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()
```

### <a name="requirements"></a>요구 사항

**헤더:** msclr\event.h

## <a name="interface_part"></a><a name="interface_part"></a>INTERFACE_PART

개체가 지원하는 각 인터페이스에 대해 BEGIN_INTERFACE_MAP 매크로와 END_INTERFACE_MAP 매크로 사이에 사용됩니다.

### <a name="syntax"></a>구문

```
INTERFACE_PART( theClass, iid, localClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
인터페이스 맵을 포함하는 클래스의 이름
*Iid*<br/>
포함된 클래스에 매핑할 IID입니다.
*localClass*<br/>
로컬 클래스의 이름입니다.

### <a name="remarks"></a>설명

클래스 *및* *localClass에*표시된 클래스의 구성원에 IID를 매핑할 수 있습니다.

인터페이스 맵에 대한 자세한 내용은 [기술 참고 38을](../tn038-mfc-ole-iunknown-implementation.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="make_delegate"></a><a name="make_delegate"></a>MAKE_DELEGATE

이벤트 처리기를 관리되는 컨트롤에 연결합니다.

### <a name="syntax"></a>구문

```
MAKE_DELEGATE( DELEGATE,  MEMBER) ;
```

### <a name="parameters"></a>매개 변수

*대리자*<br/>
[EventHandler](/dotnet/api/system.eventhandler)와 같은 관리되는 이벤트 처리기 대리자의 형식입니다.

*멤버*<br/>
컨트롤에 연결할 이벤트 처리기 메서드의 이름입니다.

### <a name="remarks"></a>설명

이 매크로는 *대리자* 형식및 NAME *MEMBER의*관리되는 이벤트 처리기 대리자를 만듭니다. 관리되는 이벤트 처리기 대리자를 사용하면 네이티브 클래스에서 관리되는 이벤트를 처리할 수 있습니다.

### <a name="example"></a>예제

다음 코드 예제에서는 `MAKE_DELEGATE` `OnClick` MFC 컨트롤에 `MyControl`이벤트 처리기를 연결 하기 위해 호출 하는 방법을 보여 주어 있습니다. MFC 응용 프로그램에서 이 매크로가 작동하는 방식에 대한 자세한 설명은 [네이티브 C++ 클래스의 Windows 양식 이벤트를 싱크하는 방법을](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)참조하세요.

```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```

### <a name="requirements"></a>요구 사항

**헤더:** msclr\event.h

## <a name="see-also"></a>참고 항목

[방법: 네이티브 C++ 클래스에서 Windows Forms 이벤트 싱크](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)<br/>
[방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[매크로 및 전역](mfc-macros-and-globals.md)<br/>
