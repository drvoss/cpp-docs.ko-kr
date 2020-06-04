---
title: CBaseKeyFrame 클래스
ms.date: 11/04/2016
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
helpviewer_keywords:
- CBaseKeyFrame [MFC], CBaseKeyFrame
- CBaseKeyFrame [MFC], AddToStoryboard
- CBaseKeyFrame [MFC], GetAnimationKeyframe
- CBaseKeyFrame [MFC], IsAdded
- CBaseKeyFrame [MFC], IsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_bAdded
- CBaseKeyFrame [MFC], m_bIsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_keyframe
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
ms.openlocfilehash: 3fcd55f6a157f4b837090a3608fb509b870aae5d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352984"
---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame 클래스

키프레임의 기본 기능을 구현합니다.

## <a name="syntax"></a>구문

```
class CBaseKeyFrame : public CObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CBaseKey프레임::CBaseKeyFrame](#cbasekeyframe)|키프레임 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CBaseKey프레임::스토리보드 추가](#addtostoryboard)|스토리보드에 키프레임을 추가합니다.|
|[CBaseKey프레임::겟애니메이션키프레임](#getanimationkeyframe)|기본 키프레임 값을 반환합니다.|
|[CBaseKey프레임::추가되었습니다.](#isadded)|키프레임이 스토리보드에 추가되었는지 여부를 알려줍니다.|
|[CBaseKey프레임::이스키프레임At오프셋](#iskeyframeatoffset)|키프레임을 오프셋 시 또는 전환 후 스토리보드에 추가할지 여부를 지정합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CBaseKey프레임::m_bAdded](#m_badded)|이 키프레임이 스토리보드에 추가되었는지 여부를 지정합니다.|
|[CBaseKey프레임::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|이 키프레임을 다른 기존 키프레임의 오프셋에서 스토리보드에 추가할지 또는 일부 전환이 끝날 때 스토리보드에 추가할지 여부를 지정합니다.|
|[CBaseKey프레임::m_keyframe](#m_keyframe)|Windows 애니메이션 API 키프레임을 나타냅니다. 키프레임이 초기화되지 않은 경우 미리 정의된 값UI_ANIMATION_KEYFRAME_STORYBOARD_START으로 설정됩니다.|

## <a name="remarks"></a>설명

변수를 UI_ANIMATION_KEYFRAME 캡슐화합니다. 모든 키프레임 구현에 대한 기본 클래스역할을 합니다. 키프레임은 스토리보드 내에서 의 시간을 나타내며 전환의 시작 및 종료 시간을 지정하는 데 사용할 수 있습니다. 키프레임에는 지정된 오프셋(시간)에 스토리보드에 추가된 키프레임 또는 지정된 전환 후에 추가된 키프레임의 두 가지 유형이 있습니다. 애니메이션이 시작되기 전에는 일부 전환의 기간을 알 수 없으므로 일부 키프레임의 실제 값은 런타임시에만 결정됩니다. 키프레임은 차례로 키프레임에 따라 달라지도록 전환에 따라 달라질 수 있으므로 키프레임 체인을 작성할 때 무한재가 발생하지 않도록 하는 것이 중요합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CBaseKeyFrame`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="cbasekeyframeaddtostoryboard"></a><a name="addtostoryboard"></a>CBaseKey프레임::스토리보드 추가

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
이 매개 변수가 TRUE이고 추가되는 키프레임이 다른 키프레임 또는 전환에 따라 달라지는 경우 이 메서드는 먼저 이 키프레임 또는 전환을 스토리보드에 추가하려고 시도합니다.

### <a name="return-value"></a>Return Value

TRUE 키프레임이 스토리보드에 성공적으로 추가된 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 스토리보드에 키프레임을 추가하기 위해 호출됩니다.

## <a name="cbasekeyframecbasekeyframe"></a><a name="cbasekeyframe"></a>CBaseKey프레임::CBaseKeyFrame

키프레임 개체를 생성합니다.

```
CBaseKeyFrame();
```

## <a name="cbasekeyframegetanimationkeyframe"></a><a name="getanimationkeyframe"></a>CBaseKey프레임::겟애니메이션키프레임

기본 키프레임 값을 반환합니다.

```
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;
```

### <a name="return-value"></a>Return Value

현재 키프레임입니다. 기본값은 UI_ANIMATION_KEYFRAME_STORYBOARD_START.

### <a name="remarks"></a>설명

기본 키프레임 값에 대한 접근자입니다.

## <a name="cbasekeyframeisadded"></a><a name="isadded"></a>CBaseKey프레임::추가되었습니다.

키프레임이 스토리보드에 추가되었는지 여부를 알려줍니다.

```
BOOL IsAdded() const;
```

### <a name="return-value"></a>Return Value

키프레임이 스토리보드에 추가된 경우 TRUE입니다. 오테와이즈 거짓.

### <a name="remarks"></a>설명

기본 클래스에서 IsAdded 항상 TRUE를 반환 하지만 파생 된 클래스에서 재정의 됩니다.

## <a name="cbasekeyframeiskeyframeatoffset"></a><a name="iskeyframeatoffset"></a>CBaseKey프레임::이스키프레임At오프셋

키프레임을 오프셋 시 또는 전환 후 스토리보드에 추가할지 여부를 지정합니다.

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>Return Value

TRUE 키프레임을 지정된 일부 오프셋에서 스토리보드에 추가해야 하는 경우. 일부 전환 후 키프레임을 스토리보드에 추가해야 하는 경우 FALSE입니다.

### <a name="remarks"></a>설명

오프셋시 키프레임을 스토리보드에 추가할지 여부를 지정합니다. 오프셋 또는 전환은 파생 클래스에 지정해야 합니다.

## <a name="cbasekeyframem_badded"></a><a name="m_badded"></a>CBaseKey프레임::m_bAdded

이 키프레임이 스토리보드에 추가되었는지 여부를 지정합니다.

```
BOOL m_bAdded;
```

## <a name="cbasekeyframem_biskeyframeatoffset"></a><a name="m_biskeyframeatoffset"></a>CBaseKey프레임::m_bIsKeyframeAtOffset

이 키프레임을 다른 기존 키프레임의 오프셋에서 스토리보드에 추가할지 또는 일부 전환이 끝날 때 스토리보드에 추가할지 여부를 지정합니다.

```
BOOL m_bIsKeyframeAtOffset;
```

## <a name="cbasekeyframem_keyframe"></a><a name="m_keyframe"></a>CBaseKey프레임::m_keyframe

Windows 애니메이션 API 키프레임을 나타냅니다. 키프레임이 초기화되지 않은 경우 미리 정의된 값UI_ANIMATION_KEYFRAME_STORYBOARD_START으로 설정됩니다.

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
