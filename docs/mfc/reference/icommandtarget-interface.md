---
title: ICommandTarget 인터페이스
ms.date: 11/04/2016
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
ms.openlocfilehash: be64f4e0367b9ecc1b24fa96f067f4acd45a9978
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751459"
---
# <a name="icommandtarget-interface"></a>ICommandTarget 인터페이스

명령 소스 개체에서 명령을 수신하는 인터페이스를 사용자 컨트롤에 제공합니다.

## <a name="syntax"></a>구문

```
interface class ICommandTarget
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[ICommandTarget::초기화](#initialize)|명령 대상 개체를 초기화합니다.|

## <a name="remarks"></a>설명

MFC 보기에서 사용자 컨트롤을 호스트하는 경우 [CWinFormsView는](../../mfc/reference/cwinformsview-class.md) 명령을 라우팅하고 명령 UI 메시지를 사용자 컨트롤로 업데이트하여 MFC 명령(예: 프레임 메뉴 항목 및 도구 모음 단추)을 처리할 수 있도록 합니다. 을 `ICommandTarget`구현하면 사용자 컨트롤에 [ICommandSource](../../mfc/reference/icommandsource-interface.md) 개체에 대한 참조를 제공합니다.

방법: Windows [양식 컨트롤에 명령 라우팅을 추가하여](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) 사용 `ICommandTarget`방법에 대한 예제를 참조하세요.

Windows 양식 사용에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h (어셈블리 atlmfc\lib\mfcmifc80.dll에 정의)

## <a name="icommandtargetinitialize"></a><a name="initialize"></a>ICommandTarget::초기화

명령 대상 개체를 초기화합니다.

```cpp
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>매개 변수

*cmd소스*<br/>
명령 소스 개체에 대한 핸들입니다.

### <a name="remarks"></a>설명

MFC 보기에서 사용자 컨트롤을 호스트하는 경우 CWinFormsView는 명령을 라우팅하고 명령 UI 메시지를 사용자 컨트롤로 업데이트하여 MFC 명령을 처리할 수 있도록 합니다.

이 메서드는 명령 대상 개체를 초기화 하 고 지정 된 명령 소스 개체 cmdSource와 연결 합니다. 사용자 컨트롤 클래스 구현에서 호출해야 합니다. 초기화 구현에서 ICommandSource:AddCommandHandler를 호출하여 명령 소스 개체에 명령 처리기를 등록해야 합니다. 방법: Windows 양식 컨트롤에 명령 라우팅을 추가하여 초기화를 사용하여 이 작업을 수행하는 방법에 대한 예제를 참조하세요.

## <a name="see-also"></a>참조

[방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandSource 인터페이스](../../mfc/reference/icommandsource-interface.md)
