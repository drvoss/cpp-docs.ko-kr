---
title: CKeyFrame 클래스
ms.date: 11/04/2016
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
helpviewer_keywords:
- CKeyFrame [MFC], CKeyFrame
- CKeyFrame [MFC], AddToStoryboard
- CKeyFrame [MFC], AddToStoryboardAfterTransition
- CKeyFrame [MFC], AddToStoryboardAtOffset
- CKeyFrame [MFC], GetExistingKeyframe
- CKeyFrame [MFC], GetOffset
- CKeyFrame [MFC], GetTransition
- CKeyFrame [MFC], m_offset
- CKeyFrame [MFC], m_pExistingKeyFrame
- CKeyFrame [MFC], m_pTransition
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
ms.openlocfilehash: f535503338a82c7cc70455ae6a08cdab0f13c624
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372287"
---
# <a name="ckeyframe-class"></a>CKeyFrame 클래스

애니메이션 키프레임을 나타냅니다.

## <a name="syntax"></a>구문

```
class CKeyFrame : public CBaseKeyFrame;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[키프레임::키프레임](#ckeyframe)|오버로드되었습니다. 다른 키프레임에 종속된 키프레임을 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C키프레임::스토리보드 추가](#addtostoryboard)|스토리보드에 키프레임을 추가합니다. [(재정의 CBaseKeyFrame::AddToStoryboard.)](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard)|
|[CKeyFrame::추가 스토리 보드 애프터 트랜지션](#addtostoryboardaftertransition)|전환 후 스토리보드에 키프레임을 추가합니다.|
|[C키프레임::스토리 보드 추가오프셋](#addtostoryboardatoffset)|오프셋에서 스토리보드에 키프레임을 추가합니다.|
|[CKeyFrame::기존 키프레임](#getexistingkeyframe)|이 키프레임에 종속된 키프레임에 대한 포인터를 반환합니다.|
|[C키프레임::오프셋](#getoffset)|다른 키프레임에서 오프셋을 반환합니다.|
|[CKeyFrame::GetTransition](#gettransition)|이 키프레임에 종속된 전환에 대한 포인터를 반환합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C키프레임::m_offset](#m_offset)|m_pExistingKeyFrame 저장된 키프레임에서 이 키프레임의 오프셋을 지정합니다.|
|[C키프레임:m_pExistingKeyFrame](#m_pexistingkeyframe)|기존 keframe에 대한 포인터를 저장합니다. 이 키프레임은 기존 키프레임에 m_offset 스토리보드에 추가됩니다.|
|[C키프레임:m_pTransition](#m_ptransition)|이 키프레임에서 시작되는 트랜스토션에 대한 포인터를 저장합니다.|

## <a name="remarks"></a>설명

이 클래스는 애니메이션 키프레임을 구현합니다. 키프레임은 스토리보드 내에서 의 시간을 나타내며 전환의 시작 및 종료 시간을 지정하는 데 사용할 수 있습니다. 키프레임은 다른 키프레임을 기반으로 하며 오프셋(초)을 갖거나 전환을 기반으로 할 수 있으며 이 전환이 끝나는 순간을 나타낼 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C베이스키프레임](../../mfc/reference/cbasekeyframe-class.md)

[키프레임](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="ckeyframeaddtostoryboard"></a><a name="addtostoryboard"></a>C키프레임::스토리보드 추가

스토리보드에 키프레임을 추가합니다.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>매개 변수

*p스토리보드*<br/>
스토리보드에 대한 포인터입니다.

*b딥애드*<br/>
키프레임을 다시 추가할지 또는 전환을 재귀적으로 추가할지 지정합니다.

### <a name="return-value"></a>Return Value

TRUE, 키프레임이 성공적으로 추가된 경우.

### <a name="remarks"></a>설명

이 메서드는 스토리보드에 키프레임을 추가합니다. 다른 키프레임 또는 전환에 따라 다르고 bDeepAdd가 TRUE인 경우 이 메서드는 재귀적으로 추가하려고 시도합니다.

## <a name="ckeyframeaddtostoryboardaftertransition"></a><a name="addtostoryboardaftertransition"></a>CKeyFrame::추가 스토리 보드 애프터 트랜지션

전환 후 스토리보드에 키프레임을 추가합니다.

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>매개 변수

*p스토리보드*<br/>
스토리보드에 대한 포인터입니다.

*b딥애드*<br/>
전환을 재귀적으로 추가할지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE, 키프레임이 성공적으로 추가된 경우.

### <a name="remarks"></a>설명

이 함수는 전환 후 스토리보드에 키프레임을 추가하기 위해 프레임워크에서 호출됩니다.

## <a name="ckeyframeaddtostoryboardatoffset"></a><a name="addtostoryboardatoffset"></a>C키프레임::스토리 보드 추가오프셋

오프셋에서 스토리보드에 키프레임을 추가합니다.

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>매개 변수

*p스토리보드*<br/>
스토리보드에 대한 포인터입니다.

*b딥애드*<br/>
이 키프레임은 재귀에 따라 달라지는 키프레임을 추가할지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE, 키프레임이 성공적으로 추가된 경우.

### <a name="remarks"></a>설명

이 함수는 오프셋에서 스토리보드에 키프레임을 추가하기 위해 프레임워크에서 호출됩니다.

## <a name="ckeyframeckeyframe"></a><a name="ckeyframe"></a>키프레임::키프레임

전환에 종속된 키프레임을 생성합니다.

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>매개 변수

*p전환*<br/>
전환에 대한 포인터입니다.

*pKeyframe*<br/>
키프레임에 대한 포인터입니다.

*offset*<br/>
pKeyframe에서 지정한 키프레임에서 초 단위로 오프셋합니다.

### <a name="remarks"></a>설명

생성된 키프레임은 지정된 전환이 끝날 때 스토리보드 내에서 시간의 순간을 나타냅니다.

## <a name="ckeyframegetexistingkeyframe"></a><a name="getexistingkeyframe"></a>CKeyFrame::기존 키프레임

이 키프레임에 종속된 키프레임에 대한 포인터를 반환합니다.

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>Return Value

이 키프레임이 다른 키프레임에 종속되지 않는 경우 키프레임 또는 NULL에 대한 유효한 포인터입니다.

### <a name="remarks"></a>설명

이 키프레임에 따라 달라지는 키프레임에 대한 접근자입니다.

## <a name="ckeyframegetoffset"></a><a name="getoffset"></a>C키프레임::오프셋

다른 키프레임에서 오프셋을 반환합니다.

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>Return Value

다른 키프레임에서 초 단위로 오프셋합니다.

### <a name="remarks"></a>설명

이 메서드는 다른 키프레임에서 초 단위로 오프셋을 결정하기 위해 호출되어야 합니다.

## <a name="ckeyframegettransition"></a><a name="gettransition"></a>CKeyFrame::GetTransition

이 키프레임에 종속된 전환에 대한 포인터를 반환합니다.

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>Return Value

이 키프레임이 전환에 종속되지 않는 경우 전환또는 NULL에 대한 유효한 포인터입니다.

### <a name="remarks"></a>설명

이 키프레임이 종속된 전환에 대한 접근자입니다.

## <a name="ckeyframem_offset"></a><a name="m_offset"></a>C키프레임::m_offset

m_pExistingKeyFrame 저장된 키프레임에서 이 키프레임의 오프셋을 지정합니다.

```
UI_ANIMATION_SECONDS m_offset;
```

## <a name="ckeyframem_pexistingkeyframe"></a><a name="m_pexistingkeyframe"></a>C키프레임:m_pExistingKeyFrame

기존 keframe에 대한 포인터를 저장합니다. 이 키프레임은 기존 키프레임에 m_offset 스토리보드에 추가됩니다.

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

## <a name="ckeyframem_ptransition"></a><a name="m_ptransition"></a>C키프레임:m_pTransition

이 키프레임에서 시작되는 트랜스토션에 대한 포인터를 저장합니다.

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
