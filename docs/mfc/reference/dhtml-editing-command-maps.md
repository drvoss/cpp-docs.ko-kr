---
title: DHTML 편집 명령 맵
ms.date: 11/04/2016
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
ms.openlocfilehash: 62b388eb178be018655ea2b2be00d7321da50335
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365814"
---
# <a name="dhtml-editing-command-maps"></a>DHTML 편집 명령 맵

다음 매크로는 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-derived 클래스에서 DHTML 편집 명령을 매핑하는 데 사용할 수 있습니다. 사용 예는 [HTMLEdit 샘플을](../../overview/visual-cpp-samples.md)참조하십시오.

### <a name="dhtml-editing-command-map-macros"></a>DHTML 편집 명령 맵 매크로

|||
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|클래스에서 DHTML 편집 명령 맵을 선언합니다.|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|클래스 내에서 DHTML 편집 명령 맵의 정의를 시작합니다.|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|DHTML 편집 명령 맵의 끝을 표시합니다.|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|명령 ID를 HTML 편집 명령에 매핑합니다.|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|명령 ID를 HTML 편집 명령 및 메시지 처리기에 매핑합니다.|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|명령 ID를 HTML 편집 명령 및 사용자 인터페이스 요소에 매핑합니다.|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|명령 ID를 HTML 편집 명령, 메시지 처리기 및 사용자 인터페이스 요소로 매핑합니다.|

## <a name="declare_dhtmlediting_cmdmap"></a><a name="declare_dhtmlediting_cmdmap"></a>DECLARE_DHTMLEDITING_CMDMAP

클래스에서 DHTML 편집 명령 맵을 선언합니다.

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>매개 변수

*Classname*<br/>
클래스의 이름입니다.

### <a name="remarks"></a>설명

이 매크로는 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-derived 클래스의 정의에 사용됩니다.

[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) 사용하여 맵을 구현합니다.

### <a name="example"></a>예제

[HTML편집 샘플을](../../overview/visual-cpp-samples.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

## <a name="begin_dhtmlediting_cmdmap"></a><a name="begin_dhtmlediting_cmdmap"></a>BEGIN_DHTMLEDITING_CMDMAP

클래스 내에서 DHTML 편집 명령 맵의 정의를 시작합니다.

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>매개 변수

*Classname*<br/>
DHTML 편집 명령 맵을 포함하는 클래스의 이름입니다. 이 클래스는 [CHtmlEditView에서](../../mfc/reference/chtmleditview-class.md) 직접 또는 간접적으로 파생되어야 하며 클래스 정의 에 [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) 매크로를 포함해야 합니다.

### <a name="remarks"></a>설명

클래스에 DHTML 편집 명령 맵을 추가하여 사용자 인터페이스 명령을 HTML 편집 명령에 매핑합니다.

클래스의 구현(.cpp) 파일에 BEGIN_DHTMLEDITING_CMDMAP 매크로를 배치하고 클래스가 매핑하는 명령에 대한 [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) 매크로를 배치합니다(예: ID_EDIT_CUT IDM_CUT). [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap) 매크로를 사용하여 이벤트 맵의 끝을 표시합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

## <a name="end_dhtmlediting_cmdmap"></a><a name="end_dhtmlediting_cmdmap"></a>END_DHTMLEDITING_CMDMAP

DHTML 편집 명령 맵의 끝을 표시합니다.

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>설명

[BEGIN_DHTMLEDITING_CMDMAP.](#begin_dhtmlediting_cmdmap)

### <a name="example"></a>예제

[HTML편집 샘플을](../../overview/visual-cpp-samples.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

## <a name="dhtmlediting_cmd_entry"></a><a name="dhtmlediting_cmd_entry"></a>DHTMLEDITING_CMD_ENTRY

명령 ID를 HTML 편집 명령에 매핑합니다.

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>매개 변수

*Cmdid*<br/>
명령 ID(예: ID_EDIT_COPY).

*dhtmlcmdID*<br/>
IDM_COPY 같은 *cmdID* 맵을 위한 HTML 편집 명령입니다.

### <a name="example"></a>예제

[HTML편집 샘플을](../../overview/visual-cpp-samples.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

## <a name="dhtmlediting_cmd_entry_func"></a><a name="dhtmlediting_cmd_entry_func"></a>DHTMLEDITING_CMD_ENTRY_FUNC

명령 ID를 HTML 편집 명령 및 메시지 처리기에 매핑합니다.

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>매개 변수

*Cmdid*<br/>
명령 ID(예: ID_EDIT_COPY).

*dhtmlcmdID*<br/>
IDM_COPY 같은 *cmdID* 맵을 위한 HTML 편집 명령입니다.

*member_func_name*<br/>
명령이 매핑되는 메시지-처리기 함수의 이름입니다.

### <a name="example"></a>예제

[HTML편집 샘플을](../../overview/visual-cpp-samples.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

## <a name="dhtmlediting_cmd_entry_type"></a><a name="dhtmlediting_cmd_entry_type"></a>DHTMLEDITING_CMD_ENTRY_TYPE

명령 ID를 HTML 편집 명령 및 사용자 인터페이스 요소에 매핑합니다.

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>매개 변수

*Cmdid*<br/>
명령 ID(예: ID_EDIT_COPY).

*dhtmlcmdID*<br/>
IDM_COPY 같은 *cmdID* 맵을 위한 HTML 편집 명령입니다.

*엘렘 타입*<br/>
AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX 또는 AFX_UI_ELEMTYPE_RADIO 중 하나인 사용자 인터페이스 요소 형식입니다.

### <a name="example"></a>예제

[HTML편집 샘플을](../../overview/visual-cpp-samples.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

## <a name="dhtmlediting_cmd_entry_func_type"></a><a name="dhtmlediting_cmd_entry_func_type"></a>DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

명령 ID를 HTML 편집 명령, 메시지 처리기 및 사용자 인터페이스 요소로 매핑합니다.

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>매개 변수

*Cmdid*<br/>
명령 ID(예: ID_EDIT_COPY).

*dhtmlcmdID*<br/>
IDM_COPY 같은 *cmdID* 맵을 위한 HTML 편집 명령입니다.

*member_func_name*<br/>
명령이 매핑되는 메시지-처리기 함수의 이름입니다.

*엘렘 타입*<br/>
AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX 또는 AFX_UI_ELEMTYPE_RADIO 중 하나인 사용자 인터페이스 요소 형식입니다.

### <a name="example"></a>예제

[HTML편집 샘플을](../../overview/visual-cpp-samples.md)참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxhtml.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
