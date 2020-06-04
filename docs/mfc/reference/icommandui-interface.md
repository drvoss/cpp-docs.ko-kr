---
title: ICommandUI 인터페이스
ms.date: 09/07/2019
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
helpviewer_keywords:
- ICommandUI interface [MFC]
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
ms.openlocfilehash: b75509beb7287fad5e51dc9d15fc3e47cacf6854
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751313"
---
# <a name="icommandui-interface"></a>ICommandUI 인터페이스

사용자 인터페이스 명령을 관리합니다.

## <a name="syntax"></a>구문

```
interface class ICommandUI
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[icommandui__Check](#check)|이 명령에 대한 사용자 인터페이스 항목을 적절한 검사 상태로 설정합니다.|
|[ICommandUI::계속 라우팅](#continuerouting)|명령 라우팅 메커니즘에 현재 메시지를 처리기 체인 아래로 계속 라우팅하도록 지시합니다.|
|[ICommandUI::사용](#enabled)|이 명령에 대한 사용자 인터페이스 항목을 활성화하거나 사용하지 않도록 설정합니다.|
|[ICommandUI:::ID](#id)|개체로 표시되는 사용자 인터페이스 개체의 `ICommandUI` ID를 가져옵니다.|
|[ICommandUI::인덱스](#index)|개체로 표시되는 사용자 인터페이스 개체의 `ICommandUI` 인덱스를 가져옵니다.|
|[ICommandUI::라디오](#radio)|이 명령에 대한 사용자 인터페이스 항목을 적절한 검사 상태로 설정합니다.|
|[ICommandUI:::텍스트](#text)|이 명령에 대한 사용자 인터페이스 항목의 텍스트를 설정합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 사용자 인터페이스 명령을 관리하는 메서드 및 속성을 제공합니다. `ICommandUI`.NET 구성 요소와 상호 운용하는 MFC 응용 프로그램에 사용되는 것을 `ICommandUI` 제외하면 [CCmdUI 클래스와](../../mfc/reference/ccmdui-class.md)유사합니다.

`ICommandUI`[iCommandTarget-파생](../../mfc/reference/icommandtarget-interface.md)클래스의 ON_UPDATE_COMMAND_UI 처리기 내에서 사용됩니다. 응용 프로그램 사용자가 메뉴를 활성화(선택 또는 클릭)하면 각 메뉴 항목이 사용 설정 또는 비활성화된 것으로 표시됩니다. 각 메뉴 명령의 대상은 ON_UPDATE_COMMAND_UI 처리기를 구현하여 이 정보를 제공합니다. 응용 프로그램의 각 명령 사용자 인터페이스 개체에 대해 [클래스 마법사를](mfc-class-wizard.md) 사용하여 각 처리기에 대한 메시지 맵 항목 및 함수 프로토타입을 만듭니다.

명령 라우팅에서 인터페이스가 `ICommandUI` 사용되는 방법에 대한 자세한 내용은 Windows 양식 [컨트롤에 명령 라우팅 추가 방법을](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)참조하십시오.

Windows 양식 사용에 대한 자세한 내용은 [MFC의 Windows 양식 사용자 컨트롤 사용을](../../dotnet/using-a-windows-form-user-control-in-mfc.md)참조하십시오.

MFC에서 사용자 인터페이스 명령을 관리하는 방법에 대한 자세한 내용은 [CCmdUI 클래스를](../../mfc/reference/ccmdui-class.md)참조하십시오.

## <a name="icommanduicheck"></a><a name="check"></a>ICommandUI::확인

이 명령에 대한 사용자 인터페이스 항목을 적절한 검사 상태로 설정합니다.

```
property UICheckState Check;
```

## <a name="remarks"></a>설명

이 속성은 이 명령에 대한 사용자 인터페이스 항목을 적절한 검사 상태로 설정합니다. 검사를 다음 값으로 설정합니다.

- 0 선택 취소
- 1 확인
- 2 세트 확정되지 않음

## <a name="icommanduicontinuerouting"></a><a name="continuerouting"></a>ICommandUI::계속 라우팅

명령 라우팅 메커니즘을 지시하여 현재 메시지를 처리기 체인 아래로 계속 라우팅합니다.

```cpp
void ContinueRouting();
```

## <a name="remarks"></a>설명

FALSE를 반환 하는 ON_COMMAND_EX 처리기와 함께 사용 해야 하는 고급 멤버 함수입니다. 자세한 내용은 기술 참고 TN006: 메시지 맵을 참조하십시오.

## <a name="icommanduienabled"></a><a name="enabled"></a>ICommandUI::사용

이 명령에 대한 사용자 인터페이스 항목을 활성화하거나 사용하지 않도록 설정합니다.

```
property bool Enabled;
```

## <a name="remarks"></a>설명

이 속성은 이 명령에 대한 사용자 인터페이스 항목을 사용 하거나 사용하지 않도록 설정합니다. 항목을 활성화하려면 TRUE로 설정, FALSE를 비활성화합니다.

## <a name="icommanduiid"></a><a name="id"></a>ICommandUI:::ID

ICommandUI 개체로 표시되는 사용자 인터페이스 개체의 ID를 가져옵니다.

```
property unsigned int ID;
```

## <a name="remarks"></a>설명

이 속성은 메뉴 항목, 도구 모음 단추 또는 ICommandUI 개체로 표시되는 다른 사용자 인터페이스 개체의 ID(핸들)를 가져옵니다.

## <a name="icommanduiindex"></a><a name="index"></a>ICommandUI::인덱스

ICommandUI 개체로 표시되는 사용자 인터페이스 개체의 인덱스를 가져옵니다.

```
property unsigned int Index;
```

## <a name="remarks"></a>설명

이 속성은 메뉴 항목, 도구 모음 단추 또는 ICommandUI 개체로 표시되는 다른 사용자 인터페이스 개체의 인덱스(핸들)를 가져옵니다.

## <a name="icommanduiradio"></a><a name="radio"></a>ICommandUI::라디오

이 명령에 대한 사용자 인터페이스 항목을 적절한 검사 상태로 설정합니다.

```
property bool Radio;
```

## <a name="remarks"></a>설명

이 속성은 이 명령에 대한 사용자 인터페이스 항목을 적절한 검사 상태로 설정합니다. 항목을 활성화하려면 라디오를 TRUE로 설정합니다. 그렇지 않으면 거짓.

## <a name="icommanduitext"></a><a name="text"></a>ICommandUI:::텍스트

이 명령에 대한 사용자 인터페이스 항목의 텍스트를 설정합니다.

```
property String^ Text;
```

## <a name="remarks"></a>설명

이 속성은 이 명령에 대한 사용자 인터페이스 항목의 텍스트를 설정합니다. 텍스트를 텍스트 문자열 핸들로 설정합니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h (어셈블리 atlmfc\lib\mfcmifc80.dll에 정의)

## <a name="see-also"></a>참조

[CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)
