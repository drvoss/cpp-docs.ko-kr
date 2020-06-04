---
title: ICommandSource 인터페이스
ms.date: 03/27/2019
f1_keywords:
- ICommandSource
- AFXWINFORMS/ICommandSource
- AFXWINFORMS/ICommandSource::AddCommandHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::AddCommandUIHandler
- AFXWINFORMS/ICommandSource::PostCommand
- AFXWINFORMS/ICommandSource::RemoveCommandHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::RemoveCommandUIHandler
- AFXWINFORMS/ICommandSource::SendCommand
helpviewer_keywords:
- ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
ms.openlocfilehash: 6a03c46c972f7746f39a3c5c65ca9b5509983d59
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356987"
---
# <a name="icommandsource-interface"></a>ICommandSource 인터페이스

명령 소스 개체에서 사용자 컨트롤로 전송된 명령을 관리합니다.

## <a name="syntax"></a>구문

```cpp
interface class ICommandSource
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[I명령 소스::추가 명령 처리기](#addcommandhandler)|명령 소스 개체에 명령 처리기를 추가합니다.|
|[I명령 소스::추가 명령 범위 처리기](#addcommandrangehandler)|명령 소스 개체에 명령 처리기 그룹을 추가합니다.|
|[ICommandSource::추가 명령 범위UI핸들러](#addcommandrangeuihandler)|명령 소스 개체에 사용자 인터페이스 명령 메시지 처리기 그룹을 추가합니다.|
|[ICommandSource::추가 명령UI처리기](#addcommandrangeuihandler)|명령 소스 개체에 사용자 인터페이스 명령 메시지 처리기를 추가합니다.|
|[ICommandSource::P스트노스트커맨드](#postcommand)|메시지가 처리될 때까지 기다리지 않고 메시지를 게시합니다.|
|[I명령 소스::제거 명령 처리기](#removecommandhandler)|명령 소스 개체에서 명령 처리기를 제거합니다.|
|[I명령 소스::제거명령 범위 처리기](#removecommandrangehandler)|명령 소스 개체에서 명령 처리기 그룹을 제거합니다.|
|[I명령 소스::제거명령 범위 UIHandler](#removecommandrangeuihandler)|명령 소스 개체에서 사용자 인터페이스 명령 메시지 처리기 그룹을 제거합니다.|
|[ICommandSource::제거명령UI핸들러](#removecommandrangeuihandler)|명령 소스 개체에서 사용자 인터페이스 명령 메시지 처리기를 제거합니다.|
|[I명령소스::SendCommand](#sendcommand)|메시지를 보내고 메시지를 반환하기 전에 처리될 때까지 기다립니다.|

### <a name="remarks"></a>설명

MFC 보기에서 사용자 컨트롤을 호스트하는 경우 [CWinFormsView 클래스는](../../mfc/reference/cwinformsview-class.md) 명령을 라우팅하고 명령 UI 메시지를 사용자 컨트롤로 업데이트하여 MFC 명령(예: 프레임 메뉴 항목 및 도구 모음 단추)을 처리할 수 있도록 합니다. [ICommandTarget 인터페이스를](../../mfc/reference/icommandtarget-interface.md)구현 하 여 사용자 컨트롤 `ICommandSource` 개체에 대 한 참조를 제공 합니다.

방법: Windows [양식 컨트롤에 명령 라우팅을 추가하여](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) 사용 `ICommandTarget`방법에 대한 예제를 참조하세요.

Windows 양식 사용에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h (어셈블리 atlmfc\lib\mfcmifc80.dll에 정의)

## <a name="icommandsourceaddcommandhandler"></a><a name="addcommandhandler"></a>I명령 소스::추가 명령 처리기

명령 소스 개체에 명령 처리기를 추가합니다.

```cpp
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>매개 변수

*Cmdid*<br/>
명령 ID입니다.
*cmdHandler*<br/>
명령 처리기 메서드에 대한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 명령 처리기 cmdHandler를 명령 소스 개체에 추가 하 고 처리기를 cmdID에 매핑합니다.
방법: AddCommandHandler를 사용하는 방법에 대한 예제를 보려면 [Windows 양식 컨트롤에 명령 라우팅을 추가합니다.](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

## <a name="icommandsourceaddcommandrangehandler"></a><a name="addcommandrangehandler"></a>I명령 소스::추가 명령 범위 처리기

명령 소스 개체에 명령 처리기 그룹을 추가합니다.

```cpp
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>매개 변수

*cmdIDMin*<br/>
명령 ID 범위의 시작 인덱스입니다.
*cmdIDMax*<br/>
명령 ID 범위의 끝 인덱스입니다.
*cmdHandler*<br/>
명령이 매핑되는 메시지 처리기 메서드에 대한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 연속된 범위의 명령 ID를 단일 메시지 처리기에 매핑하고 명령 소스 개체에 추가합니다. 이는 한 가지 방법으로 관련 단추 그룹을 처리하는 데 사용됩니다.

## <a name="icommandsourceaddcommandrangeuihandler"></a><a name="addcommandrangeuihandler"></a>ICommandSource::추가 명령 범위UI핸들러

명령 소스 개체에 사용자 인터페이스 명령 메시지 처리기 그룹을 추가합니다.

```cpp
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>매개 변수

*cmdIDMin*<br/>
명령 ID 범위의 시작 인덱스입니다.
*cmdIDMax*<br/>
명령 ID 범위의 끝 인덱스입니다.
*cmdHandler*<br/>
명령이 매핑되는 메시지 처리기 메서드에 대한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 연속된 범위의 명령 ID를 단일 사용자 인터페이스 명령 메시지 처리기에 매핑 하고 명령 소스 개체에 추가 합니다. 이는 한 가지 방법으로 관련 단추 그룹을 처리하는 데 사용됩니다.

## <a name="icommandsourceaddcommanduihandler"></a><a name="addcommanduihandler"></a>ICommandSource::추가 명령UI처리기

명령 소스 개체에 사용자 인터페이스 명령 메시지 처리기를 추가합니다.

```cpp
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>매개 변수

*Cmdid*<br/>
명령 ID입니다.
*cmduiHandler*<br/>
사용자 인터페이스 명령 메시지 처리기 메서드에 대한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 사용자 인터페이스 명령 메시지 처리기 cmdHandler를 명령 소스 개체에 추가 하 고 처리기를 cmdID에 매핑 합니다.

## <a name="icommandsourcepostcommand"></a><a name="postcommand"></a>ICommandSource::P스트노스트커맨드

메시지가 처리될 때까지 기다리지 않고 메시지를 게시합니다.

```cpp
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>매개 변수

*명령*<br/>
게시할 메시지의 명령 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 명령에 의해 지정된 ID에 매핑된 메시지를 비동기적으로 게시합니다. CWnd::PostMessage를 호출하여 메시지를 창의 메시지 큐에 배치한 다음 해당 창이 메시지를 처리할 때까지 기다리지 않고 반환합니다.

## <a name="icommandsourceremovecommandhandler"></a><a name="removecommandhandler"></a>I명령 소스::제거 명령 처리기

명령 소스 개체에서 명령 처리기를 제거합니다.

```cpp
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>매개 변수

*Cmdid*<br/>
명령 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 명령 원본 개체에서 cmdID에 매핑된 명령 처리기를 제거합니다.

## <a name="icommandsourceremovecommandrangehandler"></a><a name="removecommandrangehandler"></a>I명령 소스::제거명령 범위 처리기

명령 소스 개체에서 명령 처리기 그룹을 제거합니다.

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>매개 변수

*cmdIDMin*<br/>
명령 ID 범위의 시작 인덱스입니다.
*cmdIDMax*<br/>
명령 ID 범위의 끝 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 명령 원본 개체에서 cmdIDMin 및 cmdIDMax로 지정한 명령 ID에 매핑된 메시지 처리기 그룹을 제거합니다.

## <a name="icommandsourceremovecommandrangeuihandler"></a><a name="removecommandrangeuihandler"></a>I명령 소스::제거명령 범위 UIHandler

명령 소스 개체에서 사용자 인터페이스 명령 메시지 처리기 그룹을 제거합니다.

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>매개 변수

*cmdIDMin*<br/>
명령 ID 범위의 시작 인덱스입니다.
*cmdIDMax*<br/>
명령 ID 범위의 끝 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 명령 원본 개체에서 cmdIDMin 및 cmdIDMax로 지정한 명령 ID에 매핑된 사용자 인터페이스 명령 메시지 처리기 그룹을 제거합니다.

## <a name="icommandsourceremovecommanduihandler"></a><a name="removecommanduihandler"></a>ICommandSource::제거명령UI핸들러

명령 소스 개체에서 사용자 인터페이스 명령 메시지 처리기를 제거합니다.

```cpp
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>매개 변수

*Cmdid*<br/>
명령 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 명령 소스 개체에서 cmdID에 매핑된 사용자 인터페이스 명령 메시지 처리기를 제거합니다.

## <a name="icommandsourcesendcommand"></a><a name="sendcommand"></a>I명령소스::SendCommand

메시지를 보내고 메시지를 반환하기 전에 처리될 때까지 기다립니다.

```cpp
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>매개 변수

*명령*<br/>
보낼 메시지의 명령 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 명령에 의해 지정된 ID에 매핑된 메시지를 동기적으로 보냅니다. CWnd::SendMessage를 호출하여 창의 메시지 큐에 메시지를 배치하고 해당 창 프로시저가 메시지를 처리한 후 반환합니다.

## <a name="see-also"></a>참고 항목

[방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandTarget 인터페이스](../../mfc/reference/icommandtarget-interface.md)
