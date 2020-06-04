---
title: CMenuTearOff관리자 클래스
ms.date: 10/18/2018
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
ms.openlocfilehash: 6aef644cb7364184df91a6e8caee18cac65af4cc
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751802"
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOff관리자 클래스

분리 메뉴를 관리합니다. 분리 메뉴는 메뉴 모음의 메뉴입니다. 사용자는 메뉴 모음에서 분리 메뉴를 제거하여 이동 가능한 상태로 만들 수 있습니다.

   자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMenuTearOffManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMenuTearOff관리자::CMenuTearOff매니저](#cmenutearoffmanager)|`CMenuTearOffManager` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMenuTearOff관리자::빌드](#build)||
|[CMenuTearOff관리자::겟레그패스](#getregpath)||
|[CMenuTearOff관리자::초기화](#initialize)|`CMenuTearOffManager` 개체를 초기화합니다.|
|[CMenuTearOff관리자::이역학ID](#isdynamicid)||
|[CMenuTearOff관리자::P](#parse)||
|[CMenuTearOff관리자::재설정](#reset)||
|[CMenuTearOff관리자::세팅유스](#setinuse)||
|[CMenuTearOff관리자::셋업티어오프메뉴](#setuptearoffmenus)||

## <a name="remarks"></a>설명

응용 프로그램에서 해제 메뉴를 사용하려면 개체가 `CMenuTearOffManager` 있어야 합니다. 대부분의 경우 `CMenuTearOffManager` 개체를 직접 만들거나 초기화하지 않습니다. 이것은 [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) 함수를 호출할 때 처리됩니다.

## <a name="example"></a>예제

다음 예제에서는 `CMenuTearOffManager` `CWinAppEX::EnableTearOffMenus` 메서드를 호출하여 개체를 생성하고 초기화하는 방법을 보여 줍니다. 이 코드 조각은 [워드 패드 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMenuTearOffManager`

## <a name="requirements"></a>요구 사항

**헤더:** afxmenutearoffmanager.h

## <a name="cmenutearoffmanagerbuild"></a><a name="build"></a>CMenuTearOff관리자::빌드

```cpp
void Build(
    UINT uiTearOffBarID,
    CString& strText);
```

### <a name="parameters"></a>매개 변수

【인】 *uiTearOffBarID*<br/>

【인】 *스트라텍스트*<br/>

### <a name="remarks"></a>설명

## <a name="cmenutearoffmanagercmenutearoffmanager"></a><a name="cmenutearoffmanager"></a>CMenuTearOff관리자::CMenuTearOff매니저

[CMenuTearOffOffManager](../../mfc/reference/cmenutearoffmanager-class.md) 개체를 생성합니다.

```
CMenuTearOffManager();
```

### <a name="remarks"></a>설명

대부분의 경우 수동으로 만들지 않아야 `CMenuTearOffManager` 합니다. 응용 프로그램의 프레임 워크는 CWinAppEx를 `CMenuTearOffManager` 호출 할 때 [개체를 만듭니다::인에이블티어티오프메뉴](../../mfc/reference/cwinappex-class.md#enabletearoffmenus).

## <a name="cmenutearoffmanagergetregpath"></a><a name="getregpath"></a>CMenuTearOff관리자::겟레그패스

```
LPCTSTR GetRegPath() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmenutearoffmanagerinitialize"></a><a name="initialize"></a>CMenuTearOff관리자::초기화

[CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) 개체를 초기화합니다.

```
BOOL Initialize(
    LPCTSTR lpszRegEntry,
    UINT uiTearOffMenuFirst,
    UINT uiTearOffMenuLast);
```

### <a name="parameters"></a>매개 변수

*lpsz레엔트리*<br/>
【인】 레지스트리 항목의 경로를 포함하는 문자열입니다. 응용 프로그램은 이 레지스트리 항목에 찢어짐 막대에 대한 설정을 저장합니다.

*uiTearOff메뉴첫 번째*<br/>
【인】 찢어짐 메뉴의 첫 번째 메뉴 ID입니다.

*uiTearOff메뉴마지막*<br/>
【인】 찢어짐 메뉴의 마지막 메뉴 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

*uiTearOffMenu첫에서* *uiTearOffMenuLast에* 메뉴 아이디의 범위는 연속 간격이어야합니다. 간격은 응용 프로그램에서 동시에 나타날 수 있는 해제 메뉴의 수를 정의합니다.

## <a name="cmenutearoffmanagerisdynamicid"></a><a name="isdynamicid"></a>CMenuTearOff관리자::이역학ID

```
BOOL IsDynamicID(UINT uiID) const;
```

### <a name="parameters"></a>매개 변수

【인】 *UIID*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmenutearoffmanagerparse"></a><a name="parse"></a>CMenuTearOff관리자::P

```
UINT Parse(CString& str);
```

### <a name="parameters"></a>매개 변수

【인】 *str*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmenutearoffmanagerreset"></a><a name="reset"></a>CMenuTearOff관리자::재설정

```cpp
void Reset(HMENU hmenu);
```

### <a name="parameters"></a>매개 변수

【인】 *허메뉴*<br/>

### <a name="remarks"></a>설명

## <a name="cmenutearoffmanagersetinuse"></a><a name="setinuse"></a>CMenuTearOff관리자::세팅유스

```cpp
void SetInUse(
    UINT uiCmdId,
    BOOL bUse = TRUE);
```

### <a name="parameters"></a>매개 변수

【인】 *uiCmdId*<br/>

【인】 *buse*<br/>

### <a name="remarks"></a>설명

## <a name="cmenutearoffmanagersetuptearoffmenus"></a><a name="setuptearoffmenus"></a>CMenuTearOff관리자::셋업티어오프메뉴

```cpp
void SetupTearOffMenus(HMENU hMenu);
```

### <a name="parameters"></a>매개 변수

【인】 *h메뉴*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)
