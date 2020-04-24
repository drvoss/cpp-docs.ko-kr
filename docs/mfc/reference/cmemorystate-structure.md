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
ms.openlocfilehash: 94a2fb65a9a3030f9dc683d0eb30f476b9de1cad
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752607"
---
# <a name="cmemorystate-structure"></a>CMemoryState 구조체

프로그램에서 메모리 누수를 감지하는 편리한 방법을 제공합니다.

## <a name="syntax"></a>구문

```
struct CMemoryState
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C메모리스테이트::C메모리스테이트](#cmemorystate)|메모리 검사점을 제어하는 클래스와 같은 구조를 구성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C메모리스테이트::체크포인트](#checkpoint)|현재 메모리 상태의 스냅숏(검사점)을 가져옵니다.|
|[C메모리스테이트::D](#difference)|형식의 `CMemoryState`두 개체 간의 차이를 계산합니다.|
|[C메모리스테이트::D덤올오브젝트스이후](#dumpallobjectssince)|이전 검사점 이후 현재 할당된 모든 개체에 대한 요약을 덤프합니다.|
|[C메모리스테이트::D움프터통계](#dumpstatistics)|개체에 대한 메모리 `CMemoryState` 할당 통계를 인쇄합니다.|

## <a name="remarks"></a>설명

`CMemoryState`는 구조이며 기본 클래스가 없습니다.

"메모리 누수"는 개체에 대한 메모리가 힙에 할당되지만 더 이상 필요하지 않을 때 할당되지 않은 경우에 발생합니다. 이러한 메모리 누수는 결국 메모리 부족 오류로 이어질 수 있습니다. 프로그램에 메모리를 할당하고 할당하는 방법에는 여러 가지가 있습니다.

- 런타임 `malloc` /  `free` 라이브러리의 함수 패밀리를 사용합니다.

- Windows API 메모리 관리 기능 `LocalAlloc` /  `LocalFree` `GlobalAlloc` /  `GlobalFree`및 .

- C++ **신규** 및 **삭제** 연산자 사용.

진단은 `CMemoryState` **새** 연산자에서 할당된 메모리가 **delete를**사용하여 할당되지 않은 경우 발생하는 메모리 누수만 감지하는 데 도움이 됩니다. 다른 두 그룹 의 메모리 관리 기능은 C++ 이외의 프로그램에 대한 것이며 동일한 프로그램에서 **새** 프로그램과 **삭제하는** 것은 권장되지 않습니다. 메모리 할당의 파일 및 줄 번호 추적이 필요할 때 **새** 연산자 DEBUG_NEW 대체할 추가 매크로가 제공됩니다. DEBUG_NEW 일반적으로 **새** 연산자를 사용할 때마다 사용됩니다.

다른 진단 과 마찬가지로 `CMemoryState` 진단은 프로그램의 디버그 버전에서만 사용할 수 있습니다. 디버그 버전에는 _DEBUG 상수가 정의되어야 합니다.

프로그램에 메모리 누수가 의심되는 경우 `Checkpoint`에서 및 `Difference` `DumpStatistics` 기능을 사용하여 프로그램 실행의 두 가지 지점에서 메모리 상태(할당된 개체)의 차이를 검색할 수 있습니다. 이 정보는 함수가 할당하는 모든 개체를 정리하는지 여부를 결정하는 데 유용할 수 있습니다.

할당 및 할당 할당의 불균형이 발생하는 위치를 알면 충분한 정보를 `DumpAllObjectsSince` 제공하지 않는 경우 이 함수를 `Checkpoint`사용하여 이전 호출 이후 할당된 모든 개체를 덤프할 수 있습니다. 이 덤프는 할당 순서, 개체가 할당된 소스 파일 및 줄(할당에 DEBUG_NEW 사용하는 경우) 및 개체의 파생, 해당 주소 및 크기를 표시합니다. `DumpAllObjectsSince`또한 각 개체의 `Dump` 함수를 호출하여 현재 상태에 대한 정보를 제공합니다.

사용 `CMemoryState` 방법 및 기타 진단 방법에 대한 자세한 내용은 [MFC 응용 프로그램 디버깅을](/visualstudio/debugger/mfc-debugging-techniques)참조하십시오.

> [!NOTE]
> 형식의 `CMemoryState` 개체 및 멤버 함수에 대한 호출선언은 `#if defined(_DEBUG)/#endif` 지시문별로 괄호로 묶여야 합니다. 이렇게 하면 메모리 진단 프로그램 빌드 디버깅에만 포함 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CMemoryState`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="cmemorystatecheckpoint"></a><a name="checkpoint"></a>C메모리스테이트::체크포인트

메모리의 스냅샷 요약을 만들고 이 `CMemoryState` 개체에 저장합니다.

```cpp
void Checkpoint();
```

### <a name="remarks"></a>설명

`CMemoryState` 멤버 함수 [차이](#difference) 및 [DumpAllObjects이후이](#dumpallobjectssince) 스냅샷 데이터를 사용합니다.

### <a name="example"></a>예제

  [CMemoryState](#cmemorystate) 생성자의 예제를 참조하십시오.

## <a name="cmemorystatecmemorystate"></a><a name="cmemorystate"></a>C메모리스테이트::C메모리스테이트

[검사점](#checkpoint) 또는 `CMemoryState` [Difference](#difference) 멤버 함수에 의해 채워야 하는 빈 개체를 생성합니다.

```
CMemoryState();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

## <a name="cmemorystatedifference"></a><a name="difference"></a>C메모리스테이트::D

두 `CMemoryState` 개체를 비교한 다음 차이를 `CMemoryState` 이 개체에 저장합니다.

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>매개 변수

*올드스테이트*<br/>
`CMemoryState` 검사점에 정의된 초기 메모리 상태입니다.

*newState*<br/>
`CMemoryState` 검사점에 정의된 새 메모리 상태입니다.

### <a name="return-value"></a>Return Value

두 메모리 상태가 다른 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

두 메모리 상태 매개 변수 각각에 대해 [검사점이](#checkpoint) 호출되어야 합니다.

### <a name="example"></a>예제

  [CMemoryState](#cmemorystate) 생성자의 예제를 참조하십시오.

## <a name="cmemorystatedumpallobjectssince"></a><a name="dumpallobjectssince"></a>C메모리스테이트::D덤올오브젝트스이후

마지막 `Dump` [Checkpoint에서](#checkpoint) 이 `CMemoryState` 개체를 호출한 `CObject` 이후 할당된 클래스에서 파생된 형식의 모든 개체에 대해 함수를 호출합니다.

```cpp
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>설명

초기화되지 `DumpAllObjectsSince` `CMemoryState` 않은 개체를 호출하면 현재 메모리에 있는 모든 개체가 덤프됩니다.

### <a name="example"></a>예제

  [CMemoryState](#cmemorystate) 생성자의 예제를 참조하십시오.

## <a name="cmemorystatedumpstatistics"></a><a name="dumpstatistics"></a>C메모리스테이트::D움프터통계

`CMemoryState` [Difference](#difference) 멤버 함수로 채워진 개체에서 간결한 메모리 통계 보고서를 인쇄합니다.

```cpp
void DumpStatistics() const;
```

### <a name="remarks"></a>설명

[afxDump](diagnostic-services.md#afxdump) 장치에 인쇄된 보고서에는 다음이 표시됩니다.

샘플 보고서는 다음의 수(또는 금액)에 대한 정보를 제공합니다.

- 무료 블록

- 일반 블록

- CRT 블록

- 블록 무시

- 클라이언트 블록

- 한 번에 프로그램에서 사용하는 최대 메모리(바이트)

- 프로그램에서 현재 사용하는 총 메모리(바이트)

무료 블록은 로 설정된 경우 `afxMemDF` 할당 설정이 지연된 블록의 수입니다. `delayFreeMemDF` 자세한 내용은 "MFC 매크로 및 글로벌" 섹션에서 [afxMemDF를](diagnostic-services.md#afxmemdf)참조하십시오.

### <a name="example"></a>예제

  다음 코드는 *projname*App.cpp에 배치되어야 합니다. 다음 전역 변수를 정의합니다.

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

함수에서 `InitInstance` 다음 을 추가합니다.

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

`ExitInstance` 함수에 대한 처리기를 추가하고 다음 코드를 사용합니다.

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

이제 디버그 모드에서 프로그램을 실행하여 함수의 출력을 `DumpStatistics` 볼 수 있습니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)
