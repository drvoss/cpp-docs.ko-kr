---
title: CUserToolsManager 클래스
ms.date: 11/04/2016
f1_keywords:
- CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CreateNewTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::FindTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetArgumentsMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetFilter
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetInitialDirMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetMaxTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetToolsEntryCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetUserTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::InvokeTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::IsUserToolCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::LoadState
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolDown
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolUp
- AFXUSERTOOLSMANAGER/CUserToolsManager::RemoveTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::SaveState
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetFilter
helpviewer_keywords:
- CUserToolsManager [MFC], CUserToolsManager
- CUserToolsManager [MFC], CreateNewTool
- CUserToolsManager [MFC], FindTool
- CUserToolsManager [MFC], GetArgumentsMenuID
- CUserToolsManager [MFC], GetDefExt
- CUserToolsManager [MFC], GetFilter
- CUserToolsManager [MFC], GetInitialDirMenuID
- CUserToolsManager [MFC], GetMaxTools
- CUserToolsManager [MFC], GetToolsEntryCmd
- CUserToolsManager [MFC], GetUserTools
- CUserToolsManager [MFC], InvokeTool
- CUserToolsManager [MFC], IsUserToolCmd
- CUserToolsManager [MFC], LoadState
- CUserToolsManager [MFC], MoveToolDown
- CUserToolsManager [MFC], MoveToolUp
- CUserToolsManager [MFC], RemoveTool
- CUserToolsManager [MFC], SaveState
- CUserToolsManager [MFC], SetDefExt
- CUserToolsManager [MFC], SetFilter
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
ms.openlocfilehash: 1e9be5d7cb81f2769b98d9baeae786873f5fa73d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751987"
---
# <a name="cusertoolsmanager-class"></a>CUserToolsManager 클래스

응용 프로그램에서 [CUserTool 클래스](../../mfc/reference/cusertool-class.md) 개체의 컬렉션을 유지 관리합니다. 사용자 도구는 외부 애플리케이션을 실행하는 메뉴 항목입니다. `CUserToolsManager` 개체를 사용하면 사용자 또는 개발자가 응용 프로그램에 새 사용자 도구를 추가할 수 있습니다. 사용자 도구와 연결된 명령 실행을 지원하고 사용자 도구에 관한 정보를 Windows 레지스트리를 저장합니다.

## <a name="syntax"></a>구문

```
class CUserToolsManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CUserTools관리자::CUserToolsManager](#cusertoolsmanager)|`CUserToolsManager`를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CUserToolsManager::만들기새 도구](#createnewtool)|새 사용자 도구를 만듭니다.|
|[CUserTools관리자::찾기 도구](#findtool)|지정된 명령 ID와 연결된 `CMFCUserTool` 개체에 대한 포인터를 반환합니다.|
|[CUserToolsManager::Get인수메뉴ID](#getargumentsmenuid)|**사용자 지정** 대화 상자의 **도구** 탭에서 **인수** 메뉴와 연결된 리소스 ID를 반환합니다.|
|[CUserTools관리자::겟데프펙스트](#getdefext)|**파일 열기** 대화 [상자(CFileDialog)가](../../mfc/reference/cfiledialog-class.md#cfiledialog) **사용자 지정** 대화 상자의 **도구** 탭의 **명령** 필드에 사용하는 기본 확장명을 반환합니다.|
|[CUserTools관리자::GetFilter](#getfilter)|**사용자 지정** 대화 상자의 **도구** 탭에서 명령 필드에 파일 **열기** 대화 [상자(CFileDialog 클래스)가](../../mfc/reference/cfiledialog-class.md)사용하는 **파일** 필터를 반환합니다.|
|[CUserTools관리자::GetInitial디르메뉴ID](#getinitialdirmenuid)|**사용자 지정** 대화 상자의 **도구** 탭에서 **초기 디렉터리** 메뉴와 연결된 리소스 ID를 반환합니다.|
|[CUserTools관리자::겟맥스툴](#getmaxtools)|응용 프로그램에 할당할 수 있는 최대 사용자 도구 수를 반환합니다.|
|[CUserTools관리자::겟툴엔트리Cmd](#gettoolsentrycmd)|사용자 도구에 대한 메뉴 항목 자리 표시자의 명령 ID를 반환합니다.|
|[CUserTools관리자::GetuserTools](#getusertools)|사용자 도구 목록에 대한 참조를 반환합니다.|
|[CUserTools관리자::호출도구](#invoketool)|지정된 명령 ID가 있는 사용자 도구와 연결된 응용 프로그램을 실행합니다.|
|[CUserTools관리자::이유저툴Cmd](#isusertoolcmd)|명령 ID가 사용자 도구와 연결되어 있는지 여부를 결정합니다.|
|[CUserTools관리자::로드스테이트](#loadstate)|Windows 레지스트리에서 사용자 도구에 대한 정보를 로드합니다.|
|[CUserTools관리자::이동툴다운](#movetooldown)|지정된 사용자 도구를 사용자 도구 목록에서 아래로 이동합니다.|
|[CUserTools관리자::무브툴업](#movetoolup)|지정된 사용자 도구를 사용자 도구 목록에서 위로 이동합니다.|
|[CUserTools관리자::제거도구](#removetool)|응용 프로그램에서 지정된 사용자 도구를 제거합니다.|
|[CUserTools관리자::저장 상태](#savestate)|Windows 레지스트리에 사용자 도구에 대한 정보를 저장합니다.|
|[CUserTools관리자::세트데프펙스트](#setdefext)|**파일 열기** 대화 [상자(CFileDialog 클래스)가](../../mfc/reference/cfiledialog-class.md) **사용자 지정** 대화 상자의 **도구** 탭의 **명령** 필드에 사용하는 기본 확장자를 지정합니다.|
|[CUserTools관리자::세트필터](#setfilter)|**사용자 지정** 대화 상자의 **도구** 탭에서 명령 필드에 파일 **열기** 대화 상자(CFileDialog [클래스)가](../../mfc/reference/cfiledialog-class.md)사용하는 **파일** 필터를 지정합니다.|

## <a name="remarks"></a>설명

사용자 도구를 응용 프로그램에 통합하려면 다음을 수행해야 합니다.

1. 사용자 도구 메뉴 항목에 대한 메뉴 항목 및 관련 명령 ID를 예약합니다.

2. 사용자가 응용 프로그램에서 정의할 수 있는 각 사용자 도구에 대해 순차 명령 ID를 예약합니다.

3. [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) 메서드를 호출 하 고 다음 매개 변수를 제공: 메뉴 명령 ID, 첫 번째 사용자 도구 명령 ID, 그리고 마지막 사용자 도구 명령 ID.

응용 프로그램당 전역 `CUserToolsManager` 개체가 하나만 있어야 합니다.

사용자 도구의 예는 VisualStudioDemo 샘플 프로젝트를 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CUserToolsManager` 개체에 대한 참조를 검색하는 방법과 새 사용자 도구를 만드는 방법을 보여 줍니다. 이 코드 조각은 Visual [Studio 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CUserToolsManager`

## <a name="requirements"></a>요구 사항

**헤더:** afxusertoolsmanager.h

## <a name="cusertoolsmanagercreatenewtool"></a><a name="createnewtool"></a>CUserToolsManager::만들기새 도구

새 사용자 도구를 만듭니다.

```
CUserTool* CreateNewTool();
```

### <a name="return-value"></a>Return Value

사용자 도구 수가 최대값을 초과한 경우 새로 만든 사용자 도구 또는 NULL에 대한 포인터입니다. 반환된 형식은 *pToolRTC* 매개 `CWinAppEx::EnableUserTools` 변수로 전달되는 형식과 동일합니다.

### <a name="remarks"></a>설명

이 메서드는 [CWinAppEx::EnableUserTools에](../../mfc/reference/cwinappex-class.md#enableusertools) 대 한 호출에서 제공 되는 범위에서 사용 가능한 첫 번째 메뉴 명령 ID를 찾아 사용자 도구이 ID를 할당 합니다.

도구 수가 최대값에 도달하면 메서드가 실패합니다. 이 문제는 범위 내의 모든 명령 아이디가 사용자 도구에 할당될 때 발생합니다. [CUserToolsManager::GetMaxTools](#getmaxtools)를 호출하여 최대 도구 수를 검색할 수 있습니다. [CUserToolsManager::GetUserTools](#getusertools) 메서드를 호출 하여 도구 목록에 액세스할 수 있습니다.

## <a name="cusertoolsmanagercusertoolsmanager"></a><a name="cusertoolsmanager"></a>CUserTools관리자::CUserToolsManager

`CUserToolsManager`를 생성합니다. 각 응용 프로그램에는 사용자 도구 관리자가 하나 이상 있어야 합니다.

```
CUserToolsManager();

CUserToolsManager(
    const UINT uiCmdToolsDummy,
    const UINT uiCmdFirst,
    const UINT uiCmdLast,
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),
    UINT uArgMenuID=0,
    UINT uInitDirMenuID=0);
```

### <a name="parameters"></a>매개 변수

*uiCmdTools더미*<br/>
【인】 프레임워크가 사용자 도구 메뉴의 명령 ID에 대한 자리 표시자로 사용하는 서명되지 않은 정수입니다.

*uiCmd첫 번째*<br/>
【인】 첫 번째 사용자 도구 명령에 대한 명령 ID입니다.

*uiCmdLast*<br/>
【인】 마지막 사용자 도구 명령에 대한 명령 ID입니다.

*pToolRTC*<br/>
【인】 [CUserToolsManager::CreateNewTools가](#createnewtool) 만드는 클래스입니다. 이 클래스를 사용 하 여 기본 구현 대신 [CUserTool 클래스의](../../mfc/reference/cusertool-class.md) 파생 된 형식을 사용할 수 있습니다.

*uArgMenuID*<br/>
【인】 인수 팝업 메뉴의 메뉴 리소스 ID입니다.

*uInitDirMenuID*<br/>
【인】 초기 디렉터리 팝업 메뉴의 메뉴 리소스 ID입니다.

### <a name="remarks"></a>설명

이 생성자라고 하지 마십시오. 대신 [CWinAppEx::EnableUserTools를](../../mfc/reference/cwinappex-class.md#enableusertools) 호출하여 사용자 도구를 사용하도록 설정하고 [CWinAppEx::GetUserToolsManager를](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) 호출하여 `CUserToolsManager`에 대한 포인터를 얻습니다. 자세한 내용은 [사용자 정의 도구](../../mfc/user-defined-tools.md)를 참조하십시오.

## <a name="cusertoolsmanagerfindtool"></a><a name="findtool"></a>CUserTools관리자::찾기 도구

지정된 명령 ID와 연결된 [CUserTool 클래스](../../mfc/reference/cusertool-class.md) 개체에 대한 포인터를 반환합니다.

```
CUserTool* FindTool(UINT uiCmdId) const;
```

### <a name="parameters"></a>매개 변수

*uiCmdId*<br/>
【인】 메뉴 명령 식별자입니다.

### <a name="return-value"></a>Return Value

성공하면 [CUserTool 클래스](../../mfc/reference/cusertool-class.md) `CUserTool`또는 -derived 개체에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

`FindTool` 성공하면 반환된 형식은 [CWinAppEx::EnableUserTools에](../../mfc/reference/cwinappex-class.md#enableusertools)대한 *pToolRTC* 매개 변수의 형식과 동일합니다.

## <a name="cusertoolsmanagergetargumentsmenuid"></a><a name="getargumentsmenuid"></a>CUserToolsManager::Get인수메뉴ID

**사용자 지정** 대화 상자의 **도구** 탭에서 **인수** 메뉴와 연결된 리소스 ID를 반환합니다.

```
UINT GetArgumentsMenuID() const;
```

### <a name="return-value"></a>Return Value

메뉴 리소스의 식별자입니다.

### <a name="remarks"></a>설명

[CWinAppEx::EnableUserTools의](../../mfc/reference/cwinappex-class.md#enableusertools) *uArgMenuID* 매개 변수는 리소스의 ID를 지정합니다.

## <a name="cusertoolsmanagergetdefext"></a><a name="getdefext"></a>CUserTools관리자::겟데프펙스트

**파일 열기** 대화 [상자(CFileDialog)가](../../mfc/reference/cfiledialog-class.md#cfiledialog) **사용자 지정** 대화 상자의 **도구** 탭의 **명령** 필드에 사용하는 기본 확장명을 반환합니다.

```
const CString& GetDefExt() const;
```

### <a name="return-value"></a>Return Value

확장이 `CString` 포함된 개체에 대한 참조입니다.

## <a name="cusertoolsmanagergetfilter"></a><a name="getfilter"></a>CUserTools관리자::GetFilter

**사용자 지정** 대화 상자의 **도구** 탭에서 명령 필드에 파일 **열기** 대화 [상자(CFileDialog 클래스)가](../../mfc/reference/cfiledialog-class.md)사용하는 **파일** 필터를 반환합니다.

```
const CString& GetFilter() const;
```

### <a name="return-value"></a>Return Value

필터를 `CString` 포함하는 개체에 대한 참조입니다.

## <a name="cusertoolsmanagergetinitialdirmenuid"></a><a name="getinitialdirmenuid"></a>CUserTools관리자::GetInitial디르메뉴ID

**사용자 지정** 대화 상자의 **도구** 탭에서 **초기 디렉터리** 메뉴와 연결된 리소스 ID를 반환합니다.

```
UINT GetInitialDirMenuID() const;
```

### <a name="return-value"></a>Return Value

메뉴 리소스 식별자입니다.

### <a name="remarks"></a>설명

반환된 ID는 [CWinAppEx::EnableUserTools의](../../mfc/reference/cwinappex-class.md#enableusertools) *uInitDirMenuID* 매개 변수에 지정됩니다.

## <a name="cusertoolsmanagergetmaxtools"></a><a name="getmaxtools"></a>CUserTools관리자::겟맥스툴

응용 프로그램에 할당할 수 있는 최대 사용자 도구 수를 반환합니다.

```
int GetMaxTools() const;
```

### <a name="return-value"></a>Return Value

할당할 수 있는 최대 사용자 도구 수입니다.

### <a name="remarks"></a>설명

응용 프로그램에 할당할 수 있는 최대 도구 수를 검색하려면 이 메서드를 호출합니다. 이 숫자는 *uiCmdFirst에서* [CWinAppEx::EnableUserTools에](../../mfc/reference/cwinappex-class.md#enableusertools)전달하는 *uiCmdLast* 매개 변수를 통해 범위의 아이디 수입니다.

## <a name="cusertoolsmanagergettoolsentrycmd"></a><a name="gettoolsentrycmd"></a>CUserTools관리자::겟툴엔트리Cmd

사용자 도구에 대한 메뉴 항목 자리 표시자의 명령 ID를 반환합니다.

```
UINT GetToolsEntryCmd() const;
```

### <a name="return-value"></a>Return Value

자리 표시자의 명령 ID입니다.

### <a name="remarks"></a>설명

사용자 도구를 사용하려면 [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)를 호출합니다. *uiCmdToolsDummy* 매개 변수는 도구 입력 명령의 명령 ID를 지정합니다. 이 메서드는 도구 항목 명령 ID를 반환합니다. 해당 ID가 메뉴에서 사용되는 모든 경우 메뉴가 표시되면 사용자 도구 목록으로 대체됩니다.

## <a name="cusertoolsmanagergetusertools"></a><a name="getusertools"></a>CUserTools관리자::GetuserTools

사용자 도구 목록에 대한 참조를 반환합니다.

```
const CObList& GetUserTools() const;
```

### <a name="return-value"></a>Return Value

사용자 도구 목록을 포함하는 [CObList 클래스](../../mfc/reference/coblist-class.md) 개체에 대한 const 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) 개체가 유지 관리하는 사용자 도구 목록을 검색합니다. 각 사용자 도구는 [CUserTool 클래스](../../mfc/reference/cusertool-class.md) 형식의 개체 또는 `CUserTool`에서 파생된 형식으로 표시됩니다. 유형은 [CWinAppEx::EnableUserTools사용자](../../mfc/reference/cwinappex-class.md#enableusertools) 도구를 호출할 때 *pToolRTC* 매개 변수에 의해 지정됩니다.

## <a name="cusertoolsmanagerinvoketool"></a><a name="invoketool"></a>CUserTools관리자::호출도구

지정된 명령 ID가 있는 사용자 도구와 연결된 응용 프로그램을 실행합니다.

```
BOOL InvokeTool(UINT uiCmdId);
```

### <a name="parameters"></a>매개 변수

*uiCmdId*<br/>
【인】 사용자 도구와 연결된 메뉴 명령 ID입니다.

### <a name="return-value"></a>Return Value

사용자 도구와 연결된 명령이 성공적으로 실행된 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

*uiCmdId에*의해 지정된 명령 ID가 있는 사용자 도구와 연결된 응용 프로그램을 실행하려면 이 메서드를 호출합니다.

## <a name="cusertoolsmanagerisusertoolcmd"></a><a name="isusertoolcmd"></a>CUserTools관리자::이유저툴Cmd

명령 ID가 사용자 도구와 연결되어 있는지 여부를 결정합니다.

```
BOOL IsUserToolCmd(UINT uiCmdId) const;
```

### <a name="parameters"></a>매개 변수

*uiCmdId*<br/>
【인】 메뉴 항목의 명령 ID입니다.

### <a name="return-value"></a>Return Value

지정된 명령 ID가 사용자 도구와 연결된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 지정된 명령 ID가 명령 ID 범위에 있는지 여부를 확인합니다. [CWinAppEx::EnableUserTools를](../../mfc/reference/cwinappex-class.md#enableusertools) 호출하여 사용자 도구를 사용하도록 설정할 때 범위를 지정합니다.

## <a name="cusertoolsmanagerloadstate"></a><a name="loadstate"></a>CUserTools관리자::로드스테이트

Windows 레지스트리에서 사용자 도구에 대한 정보를 로드합니다.

```
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 Windows 레지스트리 키의 경로입니다.

### <a name="return-value"></a>Return Value

상태가 성공적으로 로드된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 Windows `CUserToolsManager` 레지스트리에서 개체의 상태를 로드합니다.

일반적으로 이 메서드를 직접 호출하지 는 않습니다. [CWinAppEx::LoadState는](../../mfc/reference/cwinappex-class.md#loadstate) 작업 영역 초기화 프로세스의 일부로 호출합니다.

## <a name="cusertoolsmanagermovetooldown"></a><a name="movetooldown"></a>CUserTools관리자::이동툴다운

지정된 사용자 도구를 사용자 도구 목록에서 아래로 이동합니다.

```
BOOL MoveToolDown(CUserTool* pTool);
```

### <a name="parameters"></a>매개 변수

*pTool*<br/>
【인】 이동할 사용자 도구를 지정합니다.

### <a name="return-value"></a>Return Value

사용자 도구가 성공적으로 아래로 이동된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

*pTool에서* 지정한 도구가 내부 목록에 없거나 도구가 목록에 마지막인 경우 메서드가 실패합니다.

## <a name="cusertoolsmanagermovetoolup"></a><a name="movetoolup"></a>CUserTools관리자::무브툴업

지정된 사용자 도구를 사용자 도구 목록에서 위로 이동합니다.

```
BOOL MoveToolUp(CUserTool* pTool);
```

### <a name="parameters"></a>매개 변수

*pTool*<br/>
【인】 이동할 사용자 도구를 지정합니다.

### <a name="return-value"></a>Return Value

사용자 도구가 성공적으로 위로 이동된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

*pTool* 매개 변수가 지정하는 도구가 내부 목록에 없거나 도구가 목록의 첫 번째 도구 항목인 경우 메서드가 실패합니다.

## <a name="cusertoolsmanagerremovetool"></a><a name="removetool"></a>CUserTools관리자::제거도구

응용 프로그램에서 지정된 사용자 도구를 제거합니다.

```
BOOL RemoveTool(CUserTool* pTool);
```

### <a name="parameters"></a>매개 변수

*pTool*<br/>
【인, 아웃】 제거할 사용자 도구에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 도구가 성공적으로 제거된 경우 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

도구가 성공적으로 제거되면 이 메서드는 *pTool*을 삭제합니다.

## <a name="cusertoolsmanagersavestate"></a><a name="savestate"></a>CUserTools관리자::저장 상태

Windows 레지스트리에 사용자 도구에 대한 정보를 저장합니다.

```
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 Windows 레지스트리 키에 대한 경로입니다.

### <a name="return-value"></a>Return Value

상태가 성공적으로 저장된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

메서드는 Windows 레지스트리에 `CUserToolsManager` 개체의 현재 상태를 저장합니다.

일반적으로 이 메서드를 직접 호출할 [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) 필요가 없습니다.

## <a name="cusertoolsmanagersetdefext"></a><a name="setdefext"></a>CUserTools관리자::세트데프펙스트

**파일 열기** 대화 [상자(CFileDialog 클래스)가](../../mfc/reference/cfiledialog-class.md) **사용자 지정** 대화 상자의 **도구** 탭의 **명령** 필드에 사용하는 기본 확장자를 지정합니다.

```cpp
void SetDefExt(const CString& strDefExt);
```

### <a name="parameters"></a>매개 변수

*스트데프엑스트*<br/>
【인】 기본 파일 이름 확장명을 포함하는 텍스트 문자열입니다.

### <a name="remarks"></a>설명

사용자가 사용자 도구와 연결할 응용 프로그램을 선택할 때 표시되는 **파일 열기** 대화 상자에서 기본 파일 이름 확장자를 지정하려면 이 메서드를 호출합니다. 기본값은 "exe"입니다.

## <a name="cusertoolsmanagersetfilter"></a><a name="setfilter"></a>CUserTools관리자::세트필터

**사용자 지정** 대화 상자의 **도구** 탭에서 명령 필드에 파일 **열기** 대화 상자(CFileDialog [클래스)가](../../mfc/reference/cfiledialog-class.md)사용하는 **파일** 필터를 지정합니다.

```cpp
void SetFilter(const CString& strFilter);
```

### <a name="parameters"></a>매개 변수

*스트필터*<br/>
【인】 필터를 지정합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)<br/>
[CUserTool 클래스](../../mfc/reference/cusertool-class.md)
