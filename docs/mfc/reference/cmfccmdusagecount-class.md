---
title: CMFCCmdUsageCount 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
helpviewer_keywords:
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
ms.openlocfilehash: 02b302ec38922128190a6f20ce2f156b52383b55
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752585"
---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount 클래스

사용자가 메뉴에서 항목을 선택하는 경우와 같은 Windows 메시지의 사용 수를 추적합니다.

## <a name="syntax"></a>구문

```
class CMFCCmdUsageCount : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|기본 생성자입니다.|
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[CMFCCmd사용카운트::애드Cmd](#addcmd)|지정된 명령과 연결된 카운터를 하나씩 증분합니다.|
|[CMFCCmd사용카운트::겟카운트](#getcount)|지정된 명령 ID와 연결된 사용 수를 검색합니다.|
|[CMFCCmd사용카운트::하스충분한정보](#hasenoughinformation)|이 개체가 최소 추적 데이터를 수집했는지 여부를 확인합니다.|
|[CMFCCmd사용카운트::이스프렌트(IsFreqeuntly)를 사용했습니다.](#isfreqeuntlyusedcmd)|지정된 명령이 자주 사용되는지 여부를 결정합니다.|
|[CMFCCmd사용카운트::리셋](#reset)|모든 명령의 사용 수를 지웁습니다.|
|[CMFCCmd사용카운트::직렬화](#serialize)|이 개체를 아카이브에서 읽거나 아카이브에 씁니다. ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)를 재정의합니다.)|
|[CMFCCmd사용카운트::설정옵션](#setoptions)|공유 `CMFCCmdUsageCount` 클래스 데이터 멤버의 값을 설정합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|속성|Description|
|`m_CmdUsage`|명령을 `CMap` 사용 개수에 매핑하는 개체입니다.|
|`m_nMinUsagePercentage`|자주 사용할 명령의 최소 사용률입니다.|
|`m_nStartCount`|이 개체가 최소 추적 데이터를 수집했는지 여부를 확인하는 데 사용되는 시작 카운터입니다.|
|`m_nTotalUsage`|추적된 모든 명령의 개수입니다.|

### <a name="remarks"></a>설명

클래스는 `CMFCCmdUsageCount` 각 숫자 Windows 메시지 식별자를 32비트 서명되지 않은 정수 카운터에 매핑합니다. `CMFCToolBar`에서는 이 클래스를 사용하여 자주 사용하는 도구 모음 항목을 표시합니다. 자세한 `CMFCToolBar`내용은 [CMFCToolBar 클래스를](../../mfc/reference/cmfctoolbar-class.md)참조하십시오.

프로그램의 실행 `CMFCCmdUsageCount` 간에 클래스 데이터를 유지시킬 수 있습니다. [CMFCCmdUsageCountCount::Serialize](#serialize) 메서드를 사용하여 클래스 멤버 데이터와 [CMFCCmdUsageCountCount::SetOptions](#setoptions) 메서드를 사용하여 공유 멤버 데이터를 설정합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCmd사용카운트](../../mfc/reference/cmfccmdusagecount-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxcmdusecount.h

## <a name="cmfccmdusagecountaddcmd"></a><a name="addcmd"></a>CMFCCmd사용카운트::애드Cmd

지정된 명령과 연결된 카운터를 하나씩 증분합니다.

```cpp
void AddCmd(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*uiCmd*|【인】 명령 카운터가 증분하도록 지정합니다.|

### <a name="remarks"></a>설명

이 메서드는 항목이 아직 없는 경우 `m_CmdUsage`명령 개수의 맵 구조에 새 항목을 추가합니다.

이 메서드는 다음과 같은 경우에는 아무 것도 수행하지 않습니다.

- 도구 모음 프레임워크는 사용자 지정 모드에 [있습니다(CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) 메서드는 영하지 않은 값을 반환합니다).

- 명령은 하위 메뉴 또는 메뉴 구분 *기호(uiCmd는* 0 또는 -1)를 나타냅니다.

- *uiCmd는* 표준 명령을 나타냅니다(전역 `IsStandardCommand` 함수는 영하지 않은 값을 반환함).

## <a name="cmfccmdusagecountgetcount"></a><a name="getcount"></a>CMFCCmd사용카운트::겟카운트

지정된 명령 ID와 연결된 사용 수를 검색합니다.

```
UINT GetCount(UINT uiCmd) const;
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*uiCmd*|【인】 검색할 명령 카운터의 ID입니다.|

### <a name="return-value"></a>Return Value

지정된 명령 ID와 연결된 사용 횟수입니다.

## <a name="cmfccmdusagecounthasenoughinformation"></a><a name="hasenoughinformation"></a>CMFCCmd사용카운트::하스충분한정보

이 개체가 최소 추적 데이터를 받았는지 여부를 확인합니다.

```
BOOL HasEnoughInformation() const;
```

### <a name="return-value"></a>Return Value

이 개체가 최소 추적 데이터를 받은 경우 Nonzero; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 추적된 모든 명령의 `m_nTotalUsage`총 개수(?)가 초기 개수와 `m_nStartCount`같거나 큰 경우 zero가 아닌 값을 반환합니다. 기본적으로 프레임워크는 초기 개수 0을 설정합니다. [CMFCCmdUsageCountCount::SetOptions](#setoptions) 메서드를 사용 하 여이 값을 재정의할 수 있습니다.

이 메서드는 [CMFCMenuBar::IsShowAllCommands에서](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) 사용 가능한 모든 메뉴 명령을 표시할지 여부를 결정하는 데 사용됩니다.

## <a name="cmfccmdusagecountisfreqeuntlyusedcmd"></a><a name="isfreqeuntlyusedcmd"></a>CMFCCmd사용카운트::이스프렌트(IsFreqeuntly)를 사용했습니다.

지정된 명령이 자주 사용되는지 여부를 결정합니다.

```
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*uiCmd*|【인】 검사할 명령을 지정합니다.|

### <a name="return-value"></a>Return Value

명령이 자주 사용되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 총 명령 사용량이 `m_nTotalUsage`0인 경우 0을 반환합니다. 그렇지 않으면 지정된 명령이 사용되는 백분율이 최소 백분율보다 큰 경우 이 `m_nMinUsagePercentage`메서드는 0이 아닌 것을 반환합니다. 기본적으로 프레임워크는 최소 백분율을 5로 설정합니다. [CMFCCmdUsageCountCount::SetOptions](#setoptions) 메서드를 사용 하 여이 값을 재정의할 수 있습니다. 최소 백분율이 0이면 지정된 명령 수가 0보다 큰 경우 이 메서드는 0이 아닌 것을 반환합니다.

[CMFCToolBar::IsCommand사용되지 않습니다명령이](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) 거의 사용되지 않는지 여부를 결정하기 위해이 메서드를 사용합니다.

## <a name="cmfccmdusagecountreset"></a><a name="reset"></a>CMFCCmd사용카운트::리셋

모든 명령의 사용 수를 지웁습니다.

```cpp
void Reset();
```

### <a name="remarks"></a>설명

이 메서드를 호출하여 명령 수의 `m_CmdUsage`맵 구조에서 모든 항목을 지우고 `m_nTotalUsage`총 명령 사용량을 0으로 재설정합니다.

## <a name="cmfccmdusagecountserialize"></a><a name="serialize"></a>CMFCCmd사용카운트::직렬화

이 개체를 아카이브에서 읽거나 아카이브에 씁니다.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*ar*|【인】 에서 `CArchive` 또는 에 직렬화할 개체입니다.|

### <a name="remarks"></a>설명

이 메서드는 명령 수의 맵 `m_CmdUsage`구조와 총 명령 `m_nTotalUsage`사용, 및 지정된 아카이브에서 또는 지정된 아카이브에 대한 카운터를 직렬화합니다.

직렬화 예제는 [직렬화: 개체 직렬화를](../../mfc/serialization-serializing-an-object.md)참조하십시오.

## <a name="cmfccmdusagecountsetoptions"></a><a name="setoptions"></a>CMFCCmd사용카운트::설정옵션

공유 `CMFCCmdUsageCount` 클래스 데이터 멤버의 값을 설정합니다.

```
static BOOL __stdcall SetOptions(
    UINT nStartCount,
    UINT nMinUsagePercentage);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*n스타트카운트*|【인】 추적된 모든 명령의 새 초기 개수입니다.|
|*nMinUsage백분율*|【인】 새 최소 사용률입니다.|

### <a name="return-value"></a>Return Value

TRUE 메서드가 성공하면 false *if nMinUsagePercentage* 매개 변수가 100보다 크거나 같습니다.

### <a name="remarks"></a>설명

이 메서드는 `CMFCCmdUsageCount` 공유 클래스 `m_nStartCount` `m_nMinUsagePercentage` 데이터 멤버와 *nStartCount* 및 *nMinUsagePercentage,* 각각 설정 합니다. `m_nStartCount`[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) 메서드에서 이 개체가 최소 추적 데이터를 수집했는지 여부를 확인합니다. `m_nMinUsagePercentage`[CMFCCmdUsageCountCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) 메서드에서 지정된 명령이 자주 사용되는지 여부를 결정합니다.

디버그 빌드에서 이 메서드는 *nMinUsagePercentage* 매개 변수가 100보다 크거나 같으면 어설션 오류를 생성합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC툴바 클래스](../../mfc/reference/cmfctoolbar-class.md)
