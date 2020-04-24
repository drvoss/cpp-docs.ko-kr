---
title: CMFCRibbonQuickAccessToolBarDefaultState 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
ms.openlocfilehash: eb6b36066f34036ae599a94f4d1c07b2c633e730
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753518"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState 클래스

리본 [막대(CMFCRibbonBar 클래스)에](../../mfc/reference/cmfcribbonbar-class.md)배치된 빠른 액세스 도구 모음의 기본 상태를 관리하는 도우미 클래스입니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonQuickAccessToolBarDefaultState
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC리본빠른액세스툴바기본상태::CMFC리본퀵액세스툴바기본상태](#cmfcribbonquickaccesstoolbardefaultstate)|`CMFCRibbonQuickAccessToolbarDefaultState` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC리본빠른액세스툴기본상태::추가 명령](#addcommand)|빠른 액세스 도구 모음의 기본 상태에 명령을 추가합니다. 도구 모음 자체는 변경되지 않습니다.|
|[CMFC리본빠른액세스툴기본상태::복사에서](#copyfrom)|한 빠른 액세스 도구 모음의 속성을 다른 도구 모음에 복사합니다.|
|[CMFC리본빠른액세스툴기본상태::모두 제거](#removeall)|빠른 액세스 도구 모음에서 모든 명령을 제거합니다. 도구 모음 자체는 변경되지 않습니다.|

## <a name="remarks"></a>설명

응용 프로그램에서 빠른 액세스 도구 모음을 만든 후 [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)를 호출하여 기본 상태를 설정하는 것이 좋습니다. 이 기본 상태는 사용자가 응용 프로그램의 **옵션** 대화 상자의 **사용자 지정** 페이지에서 **재설정** 단추를 클릭하면 복원됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMFC리본빠른액세스툴기본상태](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonQuickAccessToolbarDefaultState` 클래스의 개체를 생성 하는 방법과 빠른 액세스 도구 모음에 대 한 기본 상태에 명령을 추가 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxribbonquickaccesstoolbar.h

## <a name="cmfcribbonquickaccesstoolbardefaultstateaddcommand"></a><a name="addcommand"></a>CMFC리본빠른액세스툴기본상태::추가 명령

빠른 액세스 도구 모음의 기본 상태에 명령을 추가합니다.

```cpp
void AddCommand(
    UINT uiCmd,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>매개 변수

*[에서] uiCmd*<br/>
명령 ID를 지정합니다.

*[에서] 비시*<br/>
빠른 액세스 도구 모음이 기본 상태에 있을 때 명령의 가시성을 설정합니다.

### <a name="remarks"></a>설명

CMFC리본퀵액세스툴기본상태에 명령을 추가하면 세 가지 결과가 수행됩니다. 먼저 추가된 각 명령은 빠른 액세스 도구 모음의 오른쪽에 있는 드롭다운에 나열됩니다. 이러한 방식으로 사용자는 빠른 액세스 도구 모음에서 해당 명령을 쉽게 추가하거나 제거할 수 있습니다. 둘째, 빠른 액세스 도구 모음은 사용자가 **사용자 정의** 대화 상자에서 **재설정** 단추를 클릭할 때 기본 상태에 표시 되는 해당 명령만 표시 하도록 재설정 됩니다. 셋째, [CMFCRibbonBar::SetQuickAccessCommands를](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands)호출하지 않은 경우 빠른 액세스 도구 모음은 사용자가 응용 프로그램을 처음 실행할 때 기본 표시 명령으로 이 목록에서 표시되는 명령을 사용합니다. 원하는 모든 명령을 추가한 후 [CMFCRibbonBar::SetQuickAccessDefaultState를](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) 호출하여 이 인스턴스를 해당 리본 막대의 빠른 액세스 도구 모음의 기본 상태로 설정합니다.

## <a name="cmfcribbonquickaccesstoolbardefaultstatecopyfrom"></a><a name="copyfrom"></a>CMFC리본빠른액세스툴기본상태::복사에서

한 빠른 액세스 도구 모음의 속성을 다른 도구 모음에 복사합니다.

```cpp
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
【인】 복사할 소스 `CMFCRibbonQuickAccessToolBarDefaultState` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드는 `CMFCRibbonQuickAccessToolBarDefaultState` [CMFCRibbonQuickAccessBarDefaultState::AddCommand](#addcommand) 메서드를 사용 하 여 이 개체에 소스 개체에서 각 명령을 복사 합니다.

## <a name="cmfcribbonquickaccesstoolbardefaultstatecmfcribbonquickaccesstoolbardefaultstate"></a><a name="cmfcribbonquickaccesstoolbardefaultstate"></a>CMFC리본빠른액세스툴바기본상태::CMFC리본퀵액세스툴바기본상태

빠른 액세스 도구 모음 기본 상태 개체를 생성합니다.

```
CMFCRibbonQuickAccessToolBarDefaultState();
```

### <a name="remarks"></a>설명

기본적으로 [CMFRibbonQuickAccessBarDefaultState에](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) 포함된 새 인스턴스가 포함된 명령 목록은 비어 있습니다.

## <a name="cmfcribbonquickaccesstoolbardefaultstateremoveall"></a><a name="removeall"></a>CMFC리본빠른액세스툴기본상태::모두 제거

빠른 액세스 도구 모음에서 기본 명령 목록을 지웁울 수 있습니다.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>설명

이 함수는 이 인스턴스에서 [CMFCRibbonQuickAccessBarDefaultState::AddCommand추가에](#addcommand) 대해 이전 호출한 모든 명령을 제거합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본바 클래스](../../mfc/reference/cmfcribbonbar-class.md)
