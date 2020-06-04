---
title: C웨이트커서 클래스
ms.date: 11/04/2016
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
ms.openlocfilehash: aaa60e26d0a9bf99076f29124097b0629ce6f5d0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754323"
---
# <a name="cwaitcursor-class"></a>C웨이트커서 클래스

사용자가 장기 작업을 수행하는 동안 대기 커서를 표시하는 한 가지 방법(일반적으로 모래시계로 표시됨)을 제공합니다.

## <a name="syntax"></a>구문

```
class CWaitCursor
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C웨이트커서::C웨이트커서](#cwaitcursor)|개체를 `CWaitCursor` 생성하고 대기 커서를 표시합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C웨이트커::복원](#restore)|대기 커서가 변경된 후 복원합니다.|

## <a name="remarks"></a>설명

`CWaitCursor`기본 클래스가 없습니다.

Windows 프로그래밍 방법은 눈에 띄는 시간이 걸리는 작업을 수행할 때마다 대기 커서를 표시해야 합니다.

대기 커서를 표시하려면 긴 `CWaitCursor` 작업을 수행하는 코드 앞에 변수를 정의하십시오. 개체의 생성자가 자동으로 대기 커서를 표시합니다.

개체가 범위를 `CWaitCursor` 벗어나면(개체가 선언되는 블록의 끝에서) 소멸자는 커서를 이전 커서로 설정합니다. 즉, 개체는 필요한 정리를 자동으로 수행합니다.

> [!NOTE]
> 생성자와 소멸자가 작동하는 방식 때문에 `CWaitCursor` 개체는 항상 로컬 변수로 선언되며 전역 변수로 선언되지 않으며 **새**변수로 할당되지 도 없습니다.

메시지 상자 또는 대화 상자 표시와 같이 커서를 변경할 수 있는 작업을 수행하는 경우 [Restore](#restore) member 함수를 호출하여 대기 커서를 복원합니다. 대기 커서가 `Restore` 현재 표시되는 경우에도 호출해도 괜찮습니다.

대기 커서를 표시하는 또 다른 방법은 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)및 아마도 [CCmdTarget::RestoreWaitCursor의](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)조합을 사용하는 것입니다. `CWaitCursor` 그러나 긴 작업이 완료되면 커서를 이전 커서로 설정할 필요가 없으므로 사용하기가 더 쉽습니다.

> [!NOTE]
> MFC는 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) 가상 함수를 사용하여 커서를 설정하고 복원합니다. 이 함수를 재정의하여 사용자 지정 동작을 제공할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CWaitCursor`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]

## <a name="cwaitcursorcwaitcursor"></a><a name="cwaitcursor"></a>C웨이트커서::C웨이트커서

대기 커서를 표시하려면 긴 `CWaitCursor` 작업을 수행하는 코드 앞에 개체를 선언하면 됩니다.

```
CWaitCursor();
```

### <a name="remarks"></a>설명

생성자가 자동으로 대기 커서를 표시합니다.

개체가 범위를 `CWaitCursor` 벗어나면(개체가 선언되는 블록의 끝에서) 소멸자는 커서를 이전 커서로 설정합니다. 즉, 개체는 필요한 정리를 자동으로 수행합니다.

소멸자가 블록의 끝(함수가 끝나기 전에 호출될 수 있음)에서 호출되어 대기 커서가 함수의 일부에서만 활성화되도록 할 수 있습니다. 이 기술은 아래 두 번째 예제에 나와 있습니다.

> [!NOTE]
> 생성자와 소멸자가 작동하는 방식 때문에 `CWaitCursor` 개체는 항상 로컬 변수로 선언되며 전역 변수로 선언되지 않으며 **새**변수로 할당되지도 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]

## <a name="cwaitcursorrestore"></a><a name="restore"></a>C웨이트커::복원

대기 커서를 복원하려면 대기 커서를 다른 커서로 변경할 수 있는 메시지 상자 또는 대화 상자 표시와 같은 작업을 수행한 후 이 함수를 호출합니다.

```cpp
void Restore();
```

### <a name="remarks"></a>설명

대기 커서가 `Restore` 현재 표시되는 경우에도 호출해도 됩니다.

`CWaitCursor` 개체가 선언된 함수 이외의 함수에 있는 동안 대기 커서를 복원해야 하는 경우 [CCmdTarget::RestoreWaitCursor를](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)호출할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)<br/>
[CCmdTarget::종료웨이트커서](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)<br/>
[CCmdTarget::복원대기커](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)<br/>
[CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)<br/>
[어떻게 합니까: 마이크로소프트 파운데이션 클래스 응용 프로그램에서 마우스 커서를 변경](https://go.microsoft.com/fwlink/p/?linkid=128044)
