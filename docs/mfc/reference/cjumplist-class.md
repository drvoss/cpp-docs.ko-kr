---
title: 점프리스트 클래스
ms.date: 03/27/2019
f1_keywords:
- CJumpList
- AFXADV/CJumpList
- AFXADV/CJumpList::CJumpList
- AFXADV/CJumpList::AbortList
- AFXADV/CJumpList::AddDestination
- AFXADV/CJumpList::AddKnownCategory
- AFXADV/CJumpList::AddTask
- AFXADV/CJumpList::AddTasks
- AFXADV/CJumpList::AddTaskSeparator
- AFXADV/CJumpList::ClearAll
- AFXADV/CJumpList::ClearAllDestinations
- AFXADV/CJumpList::CommitList
- AFXADV/CJumpList::GetDestinationList
- AFXADV/CJumpList::GetMaxSlots
- AFXADV/CJumpList::GetRemovedItems
- AFXADV/CJumpList::InitializeList
- AFXADV/CJumpList::SetAppID
helpviewer_keywords:
- CJumpList [MFC], CJumpList
- CJumpList [MFC], AbortList
- CJumpList [MFC], AddDestination
- CJumpList [MFC], AddKnownCategory
- CJumpList [MFC], AddTask
- CJumpList [MFC], AddTasks
- CJumpList [MFC], AddTaskSeparator
- CJumpList [MFC], ClearAll
- CJumpList [MFC], ClearAllDestinations
- CJumpList [MFC], CommitList
- CJumpList [MFC], GetDestinationList
- CJumpList [MFC], GetMaxSlots
- CJumpList [MFC], GetRemovedItems
- CJumpList [MFC], InitializeList
- CJumpList [MFC], SetAppID
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
ms.openlocfilehash: 2e45e2e58bd51d36b6412940b7ed01aa119017ed
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754942"
---
# <a name="cjumplist-class"></a>점프리스트 클래스

A는 `CJumpList` 작업 표시줄에서 아이콘을 마우스 오른쪽 단추로 클릭할 때 표시되는 바로 가기 목록입니다.

## <a name="syntax"></a>구문

```
class CJumpList;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[점프리스트:::CJumplist](#cjumplist)|`CJumpList` 개체를 생성합니다.|
|[CJumpList::~CJumpList](#_dtorcjumplist)|`CJumpList` 개체를 제거합니다.|

|속성|Description|
|----------|-----------------|
|[CJumpList::중단 목록](#abortlist)|커밋하지 않고 목록 작성 트랜잭션을 중단합니다.|
|[CJumpList::추가 대상](#adddestination)|오버로드되었습니다. 대상을 목록에 추가합니다.|
|[CJumpList::알려진 추가 범주](#addknowncategory)|알려진 범주를 목록에 추가합니다.|
|[CJumpList::추가 작업](#addtask)|오버로드되었습니다. 표준 작업 범주에 항목을 추가합니다.|
|[CJumpList::추가 작업](#addtasks)|표준 작업 범주에 항목을 추가합니다.|
|[CJumpList::추가 작업세파레이터](#addtaskseparator)|작업 간에 구분 기호를 추가합니다.|
|[점프리스트::클리어올](#clearall)|`CJumpList` 지금까지의 현재 인스턴스에 추가된 모든 작업과 대상을 제거합니다.|
|[CJumpList::클리어모든대상](#clearalldestinations)|`CJumpList` 지금까지의 현재 인스턴스에 추가된 모든 대상을 제거합니다.|
|[CJumpList::커밋목록](#commitlist)|목록 작성 트랜잭션을 종료 하고 관련 된 저장소 (이 경우 레지스트리)에 보고 된 목록을 커밋합니다.|
|[CJumpList::GetDestinationList](#getdestinationlist)|대상 목록에 대한 인터페이스 포인터를 검색합니다.|
|[점프리스트::겟맥스슬롯](#getmaxslots)|호출 응용 프로그램의 대상 메뉴에 표시할 수 있는 범주 헤더를 포함하여 최대 항목 수를 검색합니다.|
|[CJumpList::제거항목](#getremoveditems)|제거된 대상을 나타내는 항목의 배열을 반환합니다.|
|[CJumpList::초기화 목록](#initializelist)|목록 작성 트랜잭션을 시작합니다.|
|[점프리스트::SetAppID](#setappid)|빌드할 목록에 대한 응용 프로그램 사용자 모델 ID를 설정합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CJumpList](../../mfc/reference/cjumplist-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxadv.h

## <a name="cjumplistcjumplist"></a><a name="_dtorcjumplist"></a>CJumpList::~CJumpList

`CJumpList` 개체를 제거합니다.

```
~CJumpList();
```

## <a name="cjumplistabortlist"></a><a name="abortlist"></a>CJumpList::중단 목록

커밋하지 않고 목록 작성 트랜잭션을 중단합니다.

```cpp
void AbortList();
```

### <a name="remarks"></a>설명

이 메서드를 호출하면 호출하지 `CJumpList` `CommitList`않고 파괴하는 것과 동일한 효과가 있습니다.

## <a name="cjumplistadddestination"></a><a name="adddestination"></a>CJumpList::추가 대상

대상을 목록에 추가합니다.

```
BOOL AddDestination(
    LPCTSTR lpcszCategoryName,
    LPCTSTR strDestinationPath);

BOOL AddDestination(
    LPCTSTR strCategoryName,
    IShellItem* pShellItem);

BOOL AddDestination(
    LPCTSTR strCategoryName,
    IShellLink* pShellLink);
```

### <a name="parameters"></a>매개 변수

*lpcsz범주이름*<br/>
범주 이름을 지정합니다. 지정된 범주가 없으면 해당 범주가 만들어집니다.

*스트데스티네이션패스*<br/>
대상 파일에 대한 경로를 지정합니다.

*str범주이름*<br/>
범주 이름을 지정합니다. 지정된 범주가 없으면 해당 범주가 만들어집니다.

*p셸 항목*<br/>
추가되는 대상을 나타내는 셸 항목을 지정합니다.

*p셸링크*<br/>
추가되는 대상을 나타내는 셸 링크를 지정합니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

`CJumpList` 내부적으로 추가된 대상을 누적한 다음 에서 `CommitList`커밋합니다.

## <a name="cjumplistaddknowncategory"></a><a name="addknowncategory"></a>CJumpList::알려진 추가 범주

알려진 범주를 목록에 추가합니다.

```
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```

### <a name="parameters"></a>매개 변수

*category*<br/>
알려진 범주 유형을 지정합니다. KDC_RECENT 또는 KDC_KNOWN 수 있습니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

알려진 범주는 사용하는 모든 응용 프로그램에 대해 자동으로 계산되는 `SHAddToRecentDocs` 빈도 및 최근 범주입니다(또는 쉘이 일부 시나리오에서 응용 프로그램을 대신하여 호출할 때 간접적으로 사용합니다).

## <a name="cjumplistaddtask"></a><a name="addtask"></a>CJumpList::추가 작업

표준 작업 범주에 항목을 추가합니다.

```
BOOL AddTask(
    LPCTSTR strTargetExecutablePath,
    LPCTSTR strCommandLineArgs,
    LPCTSTR strTitle,
    LPCTSTR strIconLocation,
    int iIconIndex);

BOOL AddTask(IShellLink* pShellLink);
```

### <a name="parameters"></a>매개 변수

*스트라타깃익스패스*<br/>
대상 작업 경로를 지정합니다.

*스트커맨드라이너그스*<br/>
*strTarget실행형Path*에서 지정한 실행 가능한 실행 의 명령줄 인수를 지정합니다.

*스트제목*<br/>
대상 목록에 표시될 작업 이름입니다.

*strIcon위치*<br/>
제목과 함께 대상 목록에 표시될 아이콘의 위치입니다.

*아이아이콘인덱스*<br/>
아이콘 인덱스입니다.

*p셸링크*<br/>
추가할 작업을 나타내는 셸 링크입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

지정된 작업을 `CJumpList` 누적하고 동안 `CommitList`대상 목록에 추가합니다. 작업 항목은 응용 프로그램의 대상 메뉴 하단에 있는 범주에 나타납니다. 이 범주는 UI에 채워지면 다른 모든 범주보다 우선합니다.

## <a name="cjumplistaddtasks"></a><a name="addtasks"></a>CJumpList::추가 작업

표준 작업 범주에 항목을 추가합니다.

```
BOOL AddTasks(IObjectArray* pObjectCollection);
```

### <a name="parameters"></a>매개 변수

*p오브젝트 컬렉션*<br/>
추가할 작업 컬렉션입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

CJumpList의 인스턴스는 지정된 작업을 누적하고 동안 `CommitList`대상 목록에 추가합니다. 작업 항목은 응용 프로그램의 대상 메뉴 하단에 있는 범주에 나타납니다. 이 범주는 UI에 채워지면 다른 모든 범주보다 우선합니다.

## <a name="cjumplistaddtaskseparator"></a><a name="addtaskseparator"></a>CJumpList::추가 작업세파레이터

작업 간에 구분 기호를 추가합니다.

```
BOOL AddTaskSeparator();
```

### <a name="return-value"></a>Return Value

성공하지 못하면 0이 아닌 경우 0이 됩니다.

## <a name="cjumplistcjumplist"></a><a name="cjumplist"></a>점프리스트:::CJumplist

`CJumpList` 개체를 생성합니다.

```
CJumpList(BOOL bAutoCommit = TRUE);
```

### <a name="parameters"></a>매개 변수

*b자동커밋*<br/>
이 매개 변수가 FALSE이면 목록은 소멸자에서 자동으로 커밋되지 않습니다.

## <a name="cjumplistclearall"></a><a name="clearall"></a>점프리스트::클리어올

`CJumpList` 지금까지의 현재 인스턴스에 추가된 모든 작업과 대상을 제거합니다.

```cpp
void ClearAll();
```

### <a name="remarks"></a>설명

이 메서드는 모든 데이터와 내부 인터페이스를 지우고 해제합니다.

## <a name="cjumplistclearalldestinations"></a><a name="clearalldestinations"></a>CJumpList::클리어모든대상

지금까지 CJumpList의 현재 인스턴스에 추가된 모든 대상을 제거합니다.

```cpp
void ClearAllDestinations();
```

### <a name="remarks"></a>설명

대상 목록 빌드의 현재 세션에서 지금까지 추가된 모든 대상을 제거하고 다른 대상을 다시 추가해야 하는 경우 이 함수를 호출합니다. 내부가 `ICustomDestinationList` 초기화되면 살아 남게 됩니다.

## <a name="cjumplistcommitlist"></a><a name="commitlist"></a>CJumpList::커밋목록

목록 작성 트랜잭션을 종료 하고 관련 된 저장소 (이 경우 레지스트리)에 보고 된 목록을 커밋합니다.

```
BOOL CommitList();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

커밋은 원자성입니다. 커밋이 실패하면 오류가 반환됩니다.  `CommitList` 호출되면 제거된 항목의 현재 목록이 정리됩니다. 이 메서드를 호출하면 활성 목록 작성 트랜잭션이 없도록 개체가 다시 설정됩니다. 목록을 업데이트하려면 `BeginList` 다시 호출해야 합니다.

## <a name="cjumplistgetdestinationlist"></a><a name="getdestinationlist"></a>CJumpList::GetDestinationList

대상 목록에 대한 인터페이스 포인터를 검색합니다.

```
ICustomDestinationList* GetDestinationList();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

점프 목록이 초기화되지 않았거나 커밋되거나 중단된 경우 반환된 값은 NULL이 됩니다.

## <a name="cjumplistgetmaxslots"></a><a name="getmaxslots"></a>점프리스트::겟맥스슬롯

호출 응용 프로그램의 대상 메뉴에 표시할 수 있는 범주 헤더를 포함하여 최대 항목 수를 검색합니다.

```
UINT GetMaxSlots() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

응용 프로그램은 이 값까지 결합된 여러 항목 및 범주 헤더만 보고할 수 있습니다. 에 대한 `AppendCategory` `AppendKnownCategory`호출또는 `AddUserTasks` 이 수를 초과하면 오류가 반환됩니다.

## <a name="cjumplistgetremoveditems"></a><a name="getremoveditems"></a>CJumpList::제거항목

제거된 대상을 나타내는 항목의 배열을 반환합니다.

```
IObjectArray* GetRemovedItems();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

제거된 대상은 점프 목록을 초기화하는 동안 검색됩니다. 새 대상 목록을 생성할 때 응용 프로그램은 먼저 제거된 대상 목록을 처리하여 제거된 목록 열거자가 반환하는 항목에 대한 추적 데이터를 지워야 합니다. 응용 프로그램이 현재 호출이 `BeginList` 시작된 트랜잭션에서 방금 제거된 항목을 제공하려고 하면 해당 항목을 다시 추가한 메서드 호출이 실패하여 응용 프로그램이 제거된 목록을 준수하도록 합니다.

## <a name="cjumplistinitializelist"></a><a name="initializelist"></a>CJumpList::초기화 목록

목록 작성 트랜잭션을 시작합니다.

```
BOOL InitializeList();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

을 `ICustomDestinationList` 사용하는 `GetDestinationList`포인터를 검색하지 않는 한 이 메서드를 `GetMaxSlots`명시적으로 호출할 필요가 없습니다. `GetRemovedItems`

## <a name="cjumplistsetappid"></a><a name="setappid"></a>점프리스트::SetAppID

빌드할 목록에 대한 응용 프로그램 사용자 모델 ID를 설정합니다.

```cpp
void SetAppID(LPCTSTR strAppID);
```

### <a name="parameters"></a>매개 변수

*스트라피드*<br/>
응용 프로그램 사용자 모델 ID를 지정하는 문자열입니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
