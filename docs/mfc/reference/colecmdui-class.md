---
title: 콜레CmdUI 클래스
ms.date: 09/12/2018
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
helpviewer_keywords:
- COleCmdUI [MFC], COleCmdUI
- COleCmdUI [MFC], Enable
- COleCmdUI [MFC], SetCheck
- COleCmdUI [MFC], SetText
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
ms.openlocfilehash: 1b7a6b21a3ad778b4a5ca345b1aaf42875810e4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376276"
---
# <a name="colecmdui-class"></a>콜레CmdUI 클래스

애플리케이션의 `IOleCommandTarget`기반 기능과 관련된 사용자 인터페이스 개체의 상태를 업데이트하기 위한 MFC용 메서드를 구현합니다.

## <a name="syntax"></a>구문

```
class COleCmdUI : public CCmdUI
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레cmdui::: 콜레CmdUI](#colecmdui)|`COleCmdUI` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleCmdUI::사용](#enable)|사용 명령 플래그를 설정하거나 지웁습니다.|
|[콜레CmdUI :: 세트 체크](#setcheck)|온/오프 토글 명령의 상태를 설정합니다.|
|[COleCmdUI::SetText](#settext)|명령에 대한 텍스트 이름 또는 상태 문자열을 반환합니다.|

## <a name="remarks"></a>설명

DocObjects에 대해 활성화되지 않은 응용 프로그램에서 사용자가 응용 프로그램의 메뉴를 볼 때 MFC는 UPDATE_COMMAND_UI 통보를 처리합니다. 각 알림에는 특정 명령의 상태를 반영하도록 조작할 수 있는 [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체가 제공됩니다. 그러나 DocObjects에 대 한 응용 프로그램을 사용 하는 경우 `COleCmdUI` MFC 는 UPDATE_OLE_COMMAND_UI 알림을 처리 하 고 개체를 할당 합니다.

`COleCmdUI`DocObject는 컨테이너의 사용자 인터페이스(예: FileNew, 열기, 인쇄 등)에서 시작되는 명령을 수신하고 컨테이너가 DocObject의 사용자 인터페이스에서 시작되는 명령을 수신할 수 있도록 합니다. 동일한 `IDispatch` 명령을 디스패치하는 데 사용할 `IOleCommandTarget` 수 있지만 일반적으로 인수없이 표준 명령 집합에 의존하며 형식 정보가 관련되지 않으므로 쿼리하고 실행하는 더 간단한 방법을 제공합니다. `COleCmdUI`DocObject 사용자 인터페이스 명령의 다른 속성을 활성화, 업데이트 및 설정하는 데 사용할 수 있습니다. 명령을 호출하려면 [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd)를 호출하십시오.

DocObject에 대한 자세한 내용은 CDocObjectServer 및 [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)을 참조하십시오. [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[Ccmdui](../../mfc/reference/ccmdui-class.md)

`COleCmdUI`

## <a name="requirements"></a>요구 사항

**헤더:** afxdocobj.h

## <a name="colecmduicolecmdui"></a><a name="colecmdui"></a>콜레cmdui::: 콜레CmdUI

특정 사용자 `COleCmdUI` 인터페이스 명령과 연결된 개체를 생성합니다.

```
COleCmdUI(
    OLECMD* rgCmds,
    ULONG cCmds,
    const GUID* m_pGroup);
```

### <a name="parameters"></a>매개 변수

*rgCmds*<br/>
지정된 GUID와 연결된 지원되는 명령 목록입니다. 구조는 `OLECMD` 명령을 명령 플래그와 연결합니다.

*cCmds*<br/>
*rgCmds의*명령 수입니다.

*pGroup*<br/>
명령 집합을 식별하는 GUID에 대한 포인터입니다.

### <a name="remarks"></a>설명

개체는 `COleCmdUI` 메뉴 항목 또는 컨트롤 바 단추와 같은 DocObject 사용자 인터페이스 개체를 업데이트하기 위한 프로그래밍 인터페이스를 제공합니다. 사용자 인터페이스 개체를 활성화, 비활성화, 검사 및/또는 `COleCmdUI` 개체를 통해 지울 수 있습니다.

## <a name="colecmduienable"></a><a name="enable"></a>COleCmdUI::사용

이 함수를 호출하여 개체의 `COleCmdUI` 명령 플래그를 OLECOMDF_ENABLED 설정하여 명령을 사용할 수 있고 사용할 수 있는 인터페이스에 알려주거나 명령 플래그를 지웁습니다.

```
virtual void Enable(BOOL bOn);
```

### <a name="parameters"></a>매개 변수

*본*<br/>
`COleCmdUI` 개체와 연결된 명령을 활성화할지 비활성화할지 여부를 나타냅니다. Nonzero는 명령을 활성화합니다. 0은 명령을 비활성화합니다.

## <a name="colecmduisetcheck"></a><a name="setcheck"></a>콜레CmdUI :: 세트 체크

이 함수를 호출하여 켜기/끄기 토글 명령의 상태를 설정합니다.

```
virtual void SetCheck(int nCheck);
```

### <a name="parameters"></a>매개 변수

*nCheck*<br/>
온/오프 토글 명령을 설정할 상태를 결정하는 값입니다. 값은 다음과 같습니다.

|값|설명|
|-----------|-----------------|
|**1**|명령을 켜도록 설정합니다.|
|**2**|명령을 확정되지 않음으로 설정합니다. 이 명령의 특성이 관련 선택 영역의 켜기 및 끄기 상태 모두에 있으므로 상태를 확인할 수 없습니다.|
|다른 값|명령을 끄도록 설정합니다.|

## <a name="colecmduisettext"></a><a name="settext"></a>COleCmdUI::SetText

이 함수를 호출하여 명령에 대한 텍스트 이름 또는 상태 문자열을 반환합니다.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
명령과 함께 사용할 텍스트에 대한 포인터입니다.

## <a name="see-also"></a>참고 항목

[CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
