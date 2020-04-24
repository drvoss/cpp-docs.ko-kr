---
title: CDockState 클래스
ms.date: 11/04/2016
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
ms.openlocfilehash: 9850486407ee7550ee866a10e656d45ad18fc196
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753264"
---
# <a name="cdockstate-class"></a>CDockState 클래스

영구 메모리(파일)에서 하나 이상의 도킹 컨트롤 막대의 상태를 로드, 언로드 또는 지우는 serialize된 `CObject` 클래스입니다.

## <a name="syntax"></a>구문

```
class CDockState : public CObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDockState::지우기](#clear)|도크 상태 정보를 지웁습니다.|
|[CDockState::GetVersion](#getversion)|저장된 막대 상태의 버전 번호를 검색합니다.|
|[CDockState::로드스테이트](#loadstate)|레지스트리 또는 에서 상태 정보를 검색합니다. INI 파일입니다.|
|[CDockState::저장 상태](#savestate)|상태 정보를 레지스트리 또는 INI 파일에 저장합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|저장된 도크 상태 정보에 대한 포인터 배열로 각 컨트롤 막대에 대해 하나의 항목이 있습니다.|

## <a name="remarks"></a>설명

도크 상태에는 막대의 크기와 위치 및 도킹 여부가 포함됩니다. 저장된 도크 상태를 검색할 때 막대의 위치를 `CDockState` 확인하고 현재 화면 설정에서 막대가 `CDockState` 표시되지 않으면 막대의 위치를 배율 조정하여 표시합니다. 주요 `CDockState` 목적은 여러 컨트롤 바의 전체 상태를 유지하고 해당 상태를 레지스트리에 저장하고 로드할 수 있도록 하는 것입니다. INI 파일 또는 `CArchive` 개체 내용의 일부로 이진 형식으로 표시됩니다.

막대는 도구 모음, 상태 표시줄 또는 대화 상자 막대를 포함하여 도킹 가능한 컨트롤 막대일 수 있습니다. `CDockState`개체는 `CArchive` 객체를 통해 파일로 쓰여지고 읽습니다.

[CFrameWnd:GetDockState는](../../mfc/reference/cframewnd-class.md#getdockstate) 모든 프레임 창의 `CControlBar` 개체의 상태 정보를 검색하여 `CDockState` 개체에 넣습니다. 그런 다음 `CDockState` [직렬화](../../mfc/reference/cobject-class.md#serialize) 또는 [CDockState::SaveState](#savestate)를 사용하여 개체의 내용을 저장소에 쓸 수 있습니다. 나중에 프레임 창에서 컨트롤 막대의 상태를 복원하려는 경우 `Serialize` [CDockState::LoadState를](#loadstate)사용하여 상태를 로드한 다음 [CFrameWnd::SetDockState를](../../mfc/reference/cframewnd-class.md#setdockstate) 사용하여 저장된 상태를 프레임 창의 컨트롤 막대에 적용할 수 있습니다.

도킹 컨트롤 막대에 대한 자세한 내용은 [컨트롤 모음,](../../mfc/control-bars.md) [도구 모음: 도킹 및 부동](../../mfc/docking-and-floating-toolbars.md)및 [프레임 창](../../mfc/frame-windows.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>요구 사항

**헤더:** afxadv.h

## <a name="cdockstateclear"></a><a name="clear"></a>CDockState::지우기

`CDockState` 이 함수를 호출하여 개체에 저장된 모든 도킹 정보를 지웁히 지웁습니다.

```cpp
void Clear();
```

### <a name="remarks"></a>설명

여기에는 막대가 도킹되었는지 여부뿐만 아니라 막대의 크기와 위치 및 표시 여부도 포함됩니다.

## <a name="cdockstategetversion"></a><a name="getversion"></a>CDockState::GetVersion

저장된 막대 상태의 버전 번호를 검색하려면 이 함수를 호출합니다.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Return Value

1 저장된 막대 정보가 현재 막대 상태보다 오래된 경우; 2 저장된 막대 정보가 현재 막대 상태와 동일한 경우.

### <a name="remarks"></a>설명

버전 지원을 사용하면 수정된 막대를 사용하여 새 영구 속성을 추가하고 이전 버전의 막대에서 만든 영구 상태를 검색하고 로드할 수 있습니다.

## <a name="cdockstateloadstate"></a><a name="loadstate"></a>CDockState::로드스테이트

이 함수를 호출하여 레지스트리 또는 에서 상태 정보를 검색합니다. INI 파일입니다.

```cpp
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
초기화 파일의 섹션 이름을 지정하는 null teminated 문자열 또는 상태 정보가 저장되는 Windows 레지스트리의 키를 가리킵니다.

### <a name="remarks"></a>설명

프로필 이름은 응용 프로그램의 의 섹션입니다. INI 파일 또는 막대의 상태 정보가 포함된 레지스트리입니다. 컨트롤 막대 상태 정보를 레지스트리 또는 에 저장할 수 있습니다. INI 파일 `SaveState`.

## <a name="cdockstatem_arrbarinfo"></a><a name="m_arrbarinfo"></a>CDockState::m_arrBarInfo

`CPtrArray` 개체에 상태 정보를 저장 한 각 컨트롤 막대에 대 한 저장된 컨트롤 막대 정보에 대 한 포인터의 배열인 개체입니다. `CDockState`

```
CPtrArray m_arrBarInfo;
```

## <a name="cdockstatesavestate"></a><a name="savestate"></a>CDockState::저장 상태

이 함수를 호출하여 상태 정보를 레지스트리 또는 에 저장합니다. INI 파일입니다.

```cpp
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
초기화 파일의 섹션 이름을 지정하는 null teminated 문자열 또는 상태 정보가 저장되는 Windows 레지스트리의 키를 가리킵니다.

### <a name="remarks"></a>설명

프로필 이름은 응용 프로그램의 의 섹션입니다. INI 파일 또는 컨트롤 막대의 상태 정보를 포함하는 레지스트리입니다. `SaveState`또한 현재 화면 크기를 저장합니다. 레지스트리 또는 에서 컨트롤 막대 정보를 검색할 수 있습니다. INI 파일 `LoadState`.

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
