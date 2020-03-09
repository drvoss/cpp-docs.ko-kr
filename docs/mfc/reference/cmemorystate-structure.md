---
title: CMemoryState 구조체
ms.date: 11/04/2016
f1_keywords:
- CMemoryState
helpviewer_keywords:
- CMemoryState structure [MFC]
- memory leaks [MFC], detecting
- detecting memory leaks [MFC]
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
ms.openlocfilehash: a110e1345cb970c117de125bd8105e1bc86eaf94
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855347"
---
# <a name="cmemorystate-structure"></a>CMemoryState 구조체

프로그램의 메모리 누수를 편리 하 게 감지 하는 방법을 제공 합니다.

## <a name="syntax"></a>구문

```
struct CMemoryState
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMemoryState:: CMemoryState](#cmemorystate)|메모리 검사점을 제어 하는 클래스와 비슷한 구조를 생성 합니다.|

### <a name="public-methods"></a>공용 방법

|이름|설명|
|----------|-----------------|
|[CMemoryState:: Checkpoint](#checkpoint)|현재 메모리 상태의 스냅숏 (검사점)을 가져옵니다.|
|[CMemoryState::D ifference](#difference)|`CMemoryState`형식의 두 개체 간의 차이를 계산 합니다.|
|[CMemoryState::D umpAllObjectsSince](#dumpallobjectssince)|이전 검사점 이후 현재 할당 된 모든 개체의 요약을 덤프 합니다.|
|[CMemoryState::D umpStatistics](#dumpstatistics)|`CMemoryState` 개체에 대 한 메모리 할당 통계를 인쇄 합니다.|

## <a name="remarks"></a>주의

`CMemoryState` 구조체 이며 기본 클래스가 없습니다.

"메모리 누수"는 개체에 대 한 메모리가 힙에 할당 되지만 더 이상 필요 하지 않은 경우 할당이 취소 되지 않을 때 발생 합니다. 이러한 메모리 누수는 결국 메모리 부족 오류가 발생할 수 있습니다. 프로그램에서 메모리를 할당 및 할당 취소 하는 방법에는 여러 가지가 있습니다.

- `malloc`를 사용 하 여 런타임 라이브러리의 함수 패밀리를 `free` / .

- Windows API 메모리 관리 함수를 사용 하 여 / `LocalFree` 및 `GlobalAlloc`/ `GlobalFree`를 `LocalAlloc`합니다.

- C++ **New** 및 **delete** 연산자 사용

`CMemoryState` 진단은 **new** 연산자를 사용 하 여 할당 된 메모리가 **삭제**를 사용 하 여 할당 취소 되지 않은 경우 발생 하는 메모리 누수를 탐지 하는 데만 다른 두 개의 메모리 관리 함수 그룹은 비C++ 프로그램에 사용 되며, 동일한 프로그램에서 **새로 만들기** 및 **삭제** 와 혼합 하는 것은 권장 되지 않습니다. 메모리 할당에 대 한 파일 및 줄 번호 추적을 필요로 할 때 **NEW** 연산자를 대체 하는 추가 매크로 DEBUG_NEW 제공 됩니다. DEBUG_NEW은 일반적으로 **NEW** 연산자를 사용할 때마다 사용 됩니다.

다른 진단과 마찬가지로 `CMemoryState` 진단은 프로그램의 디버그 버전 에서만 사용할 수 있습니다. 디버그 버전에는 _DEBUG 상수가 정의 되어 있어야 합니다.

프로그램에 메모리 누수가 있다고 의심 되는 경우 `Checkpoint`, `Difference`및 `DumpStatistics` 함수를 사용 하 여 프로그램 실행의 서로 다른 두 지점에서 메모리 상태 (할당 된 개체) 사이의 차이를 검색할 수 있습니다. 이 정보는 함수가 할당 하는 모든 개체를 정리 하 고 있는지 여부를 확인 하는 데 유용할 수 있습니다.

할당 및 할당 취소의 불균형에서 충분 한 정보를 제공 하지 않는 경우에만 `DumpAllObjectsSince` 함수를 사용 하 여 `Checkpoint`에 대 한 이전 호출 이후 할당 된 모든 개체를 덤프할 수 있습니다. 이 덤프는 할당 순서, 개체가 할당 된 원본 파일 및 줄 (할당을 위해 DEBUG_NEW를 사용 하는 경우), 개체의 주소 및 크기를 표시 합니다. 또한 `DumpAllObjectsSince`는 각 개체의 `Dump` 함수를 호출 하 여 현재 상태에 대 한 정보를 제공 합니다.

`CMemoryState` 및 기타 진단을 사용 하는 방법에 대 한 자세한 내용은 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)을 참조 하세요.

> [!NOTE]
>  `CMemoryState` 형식 및 멤버 함수에 대 한 호출의 개체 선언은 `#if defined(_DEBUG)/#endif` 지시문으로 묶어야 합니다. 이로 인해 메모리 진단은 프로그램의 빌드 디버그에만 포함 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`CMemoryState`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="checkpoint"></a>CMemoryState:: Checkpoint

메모리의 스냅숏 요약을 가져와이 `CMemoryState` 개체에 저장 합니다.

```
void Checkpoint();
```

### <a name="remarks"></a>주의

`CMemoryState` 멤버 함수 [차이점](#difference) 및 [DumpAllObjectsSince](#dumpallobjectssince) 이 스냅숏 데이터를 사용 합니다.

### <a name="example"></a>예제

  [Cmemorystate](#cmemorystate) 생성자의 예제를 참조 하세요.

##  <a name="cmemorystate"></a>CMemoryState:: CMemoryState

[Checkpoint](#checkpoint) 또는 [차이](#difference) 멤버 함수로 채워야 하는 빈 `CMemoryState` 개체를 생성 합니다.

```
CMemoryState();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

##  <a name="difference"></a>CMemoryState::D ifference

두 `CMemoryState` 개체를 비교한 다음이 `CMemoryState` 개체에 대 한 차이를 저장 합니다.

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>매개 변수

*oldState*<br/>
`CMemoryState` 검사점에서 정의한 초기 메모리 상태입니다.

*newState*<br/>
`CMemoryState` 검사점에 정의 된 새 메모리 상태입니다.

### <a name="return-value"></a>반환 값

두 메모리 상태가 서로 다르면 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>주의

두 개의 메모리 상태 매개 변수에 대해 [검사점](#checkpoint) 이 호출 되어야 합니다.

### <a name="example"></a>예제

  [Cmemorystate](#cmemorystate) 생성자의 예제를 참조 하세요.

##  <a name="dumpallobjectssince"></a>CMemoryState::D umpAllObjectsSince

이 `CMemoryState` 개체에 대 한 마지막 [검사점](#checkpoint) 호출 이후 할당 된 (그리고 여전히 할당 된) 클래스 `CObject`에서 파생 된 형식의 모든 개체에 대해 `Dump` 함수를 호출 합니다.

```
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>주의

초기화 되지 않은 `CMemoryState` 개체를 사용 하 여 `DumpAllObjectsSince`를 호출 하면 현재 메모리에 있는 모든 개체를 덤프 합니다.

### <a name="example"></a>예제

  [Cmemorystate](#cmemorystate) 생성자의 예제를 참조 하세요.

##  <a name="dumpstatistics"></a>CMemoryState::D umpStatistics

[차이](#difference) 멤버 함수에 의해 채워지는 `CMemoryState` 개체에서 간결한 메모리 통계 보고서를 인쇄 합니다.

```
void DumpStatistics() const;
```

### <a name="remarks"></a>주의

[AfxDump](diagnostic-services.md#afxdump) 장치에 인쇄 되는 보고서에는 다음이 표시 됩니다.

예제 보고서는의 수 또는 양에 대 한 정보를 제공 합니다.

- 사용 가능한 블록

- 일반 블록

- CRT 블록

- 블록 무시

- 클라이언트 블록

- 한 번에 프로그램에서 사용 하는 최대 메모리 (바이트)

- 프로그램에서 현재 사용 하는 총 메모리 (바이트)

사용 가능한 블록은 `afxMemDF` `delayFreeMemDF`설정 된 경우 할당 취소가 지연 된 블록 수입니다. 자세한 내용은 "MFC 매크로 및 전역" 섹션의 [afxMemDF](diagnostic-services.md#afxmemdf)를 참조 하세요.

### <a name="example"></a>예제

  다음 코드는 *projname*app-v에 배치 해야 합니다. 다음 전역 변수를 정의 합니다.

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

`InitInstance` 함수에서 줄을 추가 합니다.

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

`ExitInstance` 함수에 대 한 처리기를 추가 하 고 다음 코드를 사용 합니다.

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

이제 디버그 모드에서 프로그램을 실행 하 여 `DumpStatistics` 함수의 출력을 볼 수 있습니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)
