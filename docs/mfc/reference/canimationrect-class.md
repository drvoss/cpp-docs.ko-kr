---
title: CAnimationRect 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
helpviewer_keywords:
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
ms.openlocfilehash: 273ea2b548d35722ebf937d2db2b589fef5e69fa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755127"
---
# <a name="canimationrect-class"></a>CAnimationRect 클래스

면에 애니메이션을 적용할 수 있는 사각형 기능을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationRect : public CAnimationBaseObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션렉트::C애니메이션렉트](#canimationrect)|오버로드되었습니다. 애니메이션 직사각형 오브젝트를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션렉트::추가 전환](#addtransition)|왼쪽, 위쪽, 오른쪽 및 아래쪽 좌표에 대한 전환을 추가합니다.|
|[C애니메이션렉트::GetBottom](#getbottom)|아래쪽 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|
|[C애니메이션렉트::Getdefaultvalue](#getdefaultvalue)|사각형의 경계에 대한 기본값을 반환합니다.|
|[C애니메이션렉트::겟레프트](#getleft)|왼쪽 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|
|[C애니메이션렉트::겟라이트](#getright)|오른쪽 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|
|[C애니메이션렉트::겟탑](#gettop)|최상위 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|
|[C애니메이션렉트::GetValue](#getvalue)|현재 값을 반환합니다.|
|[C애니메이션렉트::설정디폴값](#setdefaultvalue)|기본값을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션렉트::겟애니메이션변수리스트](#getanimationvariablelist)|캡슐화된 애니메이션 변수를 목록에 넣습니다. [(CAnimationBaseObject 재정의::GetAnimationVariablelist.)](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C애니메이션렉트::연산자 RECT](#operator_rect)|CAnimationRect를 RECT로 변환합니다.|
|[C애니메이션렉트::연산자=](#operator_eq)|CAnimationRect에 정사각형을 할당합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C애니메이션렉트::m_bFixedSize](#m_bfixedsize)|사각형의 크기가 고정되어 있는지 여부를 지정합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C애니메이션렉트::m_bottomValue](#m_bottomvalue)|애니메이션 사각형의 아래쪽 경계를 나타내는 캡슐화된 애니메이션 변수입니다.|
|[C애니메이션렉트::m_leftValue](#m_leftvalue)|애니메이션 사각형의 왼쪽 경계를 나타내는 캡슐화된 애니메이션 변수입니다.|
|[C애니메이션렉트::m_rightValue](#m_rightvalue)|애니메이션 사각형의 오른쪽 경계를 나타내는 캡슐화된 애니메이션 변수입니다.|
|[C애니메이션렉트::m_szInitial](#m_szinitial)|애니메이션 사각형의 초기 크기를 지정합니다.|
|[C애니메이션렉트:m_topValue](#m_topvalue)|애니메이션 사각형의 맨 위 경계를 나타내는 캡슐화된 애니메이션 변수입니다.|

## <a name="remarks"></a>설명

CAnimationRect 클래스는 4개의 CAnimationVariable 개체를 캡슐화하며 응용 프로그램에서 사각형을 나타낼 수 있습니다. 응용 프로그램에서 이 클래스를 사용하려면 이 클래스의 개체를 인스턴스화하고 CAnimationController::AddAnimationObject를 사용하여 애니메이션 컨트롤러에 추가하고 각 전환이 왼쪽, 오른쪽 상단 및 아래쪽 좌표에 적용될 경우 AddTransition를 호출합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C애니메이션베이스오브젝트](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationrectaddtransition"></a><a name="addtransition"></a>C애니메이션렉트::추가 전환

왼쪽, 위쪽, 오른쪽 및 아래쪽 좌표에 대한 전환을 추가합니다.

```cpp
void AddTransition(
    CBaseTransition* pLeftTransition,
    CBaseTransition* pTopTransition,
    CBaseTransition* pRightTransition,
    CBaseTransition* pBottomTransition);
```

### <a name="parameters"></a>매개 변수

*pLeft전환*<br/>
왼쪽에 대한 전환을 지정합니다.

*pTopTransition*<br/>
위쪽 면에 대한 전환을 지정합니다.

*pRightTransition*<br/>
오른쪽에 대한 전환을 지정합니다.

*p바텀트랜지션*<br/>
아래쪽에 대한 전환을 지정합니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 각 사각형 면의 애니메이션 변수에 적용할 내부 전환 목록에 지정된 전환을 추가합니다. 전환을 추가하면 전환이 즉시 적용되지 않고 내부 목록에 저장됩니다. CAnimationController::AnimateGroup을 호출할 때 전환이 적용됩니다(특정 값에 대한 스토리보드에 추가). 사각형 측면 중 하나에 전환을 적용할 필요가 없는 경우 NULL을 전달할 수 있습니다.

## <a name="canimationrectcanimationrect"></a><a name="canimationrect"></a>C애니메이션렉트::C애니메이션렉트

CAnimationRect 개체를 생성합니다.

```
CAnimationRect();

CAnimationRect(
    const CRect& rect,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    const CPoint& pt,
    const CSize& sz,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    int nLeft,
    int nTop,
    int nRight,
    int nBottom,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
기본 사각형을 지정합니다.

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

*n개체 ID*<br/>
개체 ID를 지정합니다.

*dw사용자 데이터*<br/>
사용자 정의 데이터를 지정합니다.

*pt*<br/>
왼쪽 상단 모서리의 좌표.

*Sz*<br/>
사각형의 크기입니다.

*n왼쪽*<br/>
왼쪽 바운드 좌표를 지정합니다.

*Ntop*<br/>
맨 위 바운드좌표를 지정합니다.

*nRight*<br/>
오른쪽 바운드좌표를 지정합니다.

*n 바텀*<br/>
하단 바운드의 좌표를 지정합니다.

### <a name="remarks"></a>설명

오브젝트는 왼쪽, 위쪽, 오른쪽 및 아래쪽, 개체 ID 및 그룹 ID에 대한 기본값으로 생성되며, 이 값은 0으로 설정됩니다. 나중에 SetDefaultValue 및 SetID를 사용하여 런타임에 변경할 수 있습니다.

## <a name="canimationrectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>C애니메이션렉트::겟애니메이션변수리스트

캡슐화된 애니메이션 변수를 목록에 넣습니다.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>매개 변수

*순*<br/>
함수가 반환되면 사각형의 좌표를 나타내는 4개의 CAnimationVariable 개체에 대한 포인터가 포함됩니다.

## <a name="canimationrectgetbottom"></a><a name="getbottom"></a>C애니메이션렉트::GetBottom

아래쪽 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>Return Value

하단 좌표를 나타내는 캡슐화된 CAnimationVariable에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 아래쪽 좌표를 나타내는 기본 CAnimationVariable에 직접 액세스할 수 있습니다.

## <a name="canimationrectgetdefaultvalue"></a><a name="getdefaultvalue"></a>C애니메이션렉트::Getdefaultvalue

사각형의 경계에 대한 기본값을 반환합니다.

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>Return Value

왼쪽, 오른쪽, 위쪽 및 하단에 대한 기본값을 포함하는 CRect 값입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 생성자 또는 SetDefaultValue에 의해 이전에 설정된 기본값을 검색합니다.

## <a name="canimationrectgetleft"></a><a name="getleft"></a>C애니메이션렉트::겟레프트

왼쪽 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>Return Value

왼쪽 좌표를 나타내는 캡슐화된 CAnimationVariable에 대한 참조입니다.

### <a name="remarks"></a>설명

왼쪽 좌표를 나타내는 기본 CAnimationVariable에 직접 액세스하려면 이 메서드를 호출할 수 있습니다.

## <a name="canimationrectgetright"></a><a name="getright"></a>C애니메이션렉트::겟라이트

오른쪽 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>Return Value

오른쪽 좌표를 나타내는 캡슐화된 CAnimationVariable에 대한 참조입니다.

### <a name="remarks"></a>설명

올바른 좌표를 나타내는 기본 CAnimationVariable에 직접 액세스하려면 이 메서드를 호출할 수 있습니다.

## <a name="canimationrectgettop"></a><a name="gettop"></a>C애니메이션렉트::겟탑

최상위 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>Return Value

상단 좌표를 나타내는 캡슐화된 CAnimationVariable에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 상단 좌표를 나타내는 기본 CAnimationVariable에 직접 액세스할 수 있습니다.

## <a name="canimationrectgetvalue"></a><a name="getvalue"></a>C애니메이션렉트::GetValue

현재 값을 반환합니다.

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
출력 이 메서드가 반환될 때 현재 값을 포함합니다.

### <a name="return-value"></a>Return Value

TRUE, 현재 값이 성공적으로 검색된 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 함수를 호출하여 애니메이션 사각형의 현재 값을 검색합니다. 이 메서드가 실패하거나 왼쪽, 위쪽, 오른쪽 및 아래쪽에 대한 기본 COM 개체가 초기화되지 않은 경우 rect에는 생성자 또는 SetDefaultValue에 의해 이전에 설정된 기본 값이 포함됩니다.

## <a name="canimationrectm_bfixedsize"></a><a name="m_bfixedsize"></a>C애니메이션렉트::m_bFixedSize

사각형의 크기가 고정되어 있는지 여부를 지정합니다.

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>설명

이 멤버가 true이면 사각형의 크기가 고정되고 왼쪽 위 모서리가 고정 된 크기에 따라 이동할 때마다 오른쪽 및 아래쪽 값이 다시 계산됩니다. 화면 주위의 사각형을 쉽게 이동할 수 있도록 이 값을 TRUE로 설정합니다. 이 경우 오른쪽 및 하단 좌표에 적용된 전환은 무시됩니다. 크기는 개체를 생성하거나 SetDefaultValue를 호출할 때 내부적으로 저장됩니다. 기본적으로 이 멤버는 FALSE로 설정됩니다.

## <a name="canimationrectm_bottomvalue"></a><a name="m_bottomvalue"></a>C애니메이션렉트::m_bottomValue

애니메이션 사각형의 아래쪽 경계를 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_bottomValue;
```

## <a name="canimationrectm_leftvalue"></a><a name="m_leftvalue"></a>C애니메이션렉트::m_leftValue

애니메이션 사각형의 왼쪽 경계를 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_leftValue;
```

## <a name="canimationrectm_rightvalue"></a><a name="m_rightvalue"></a>C애니메이션렉트::m_rightValue

애니메이션 사각형의 오른쪽 경계를 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_rightValue;
```

## <a name="canimationrectm_szinitial"></a><a name="m_szinitial"></a>C애니메이션렉트::m_szInitial

애니메이션 사각형의 초기 크기를 지정합니다.

```
CSize m_szInitial;
```

## <a name="canimationrectm_topvalue"></a><a name="m_topvalue"></a>C애니메이션렉트:m_topValue

애니메이션 사각형의 맨 위 경계를 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_topValue;
```

## <a name="canimationrectoperator-rect"></a><a name="operator_rect"></a>C애니메이션렉트::연산자 RECT

CAnimationRect를 RECT로 변환합니다.

```
operator RECT();
```

### <a name="return-value"></a>Return Value

애니메이션 사각형의 현재 값입니다.

### <a name="remarks"></a>설명

이 함수는 내부적으로 GetValue를 호출합니다. 어떤 이유로 GetValue가 실패하면 반환된 RECT에는 모든 사각형 좌표에 대한 기본값이 포함됩니다.

## <a name="canimationrectoperator"></a><a name="operator_eq"></a>C애니메이션렉트::연산자=

CAnimationRect에 정사각형을 할당합니다.

```cpp
void operator=(const RECT& rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
애니메이션 사각형의 새 값입니다.

### <a name="remarks"></a>설명

이 연산자는 SetDefaultValue를 호출하기 때문에 애니메이션을 시작하기 전에 이 작업을 수행하는 것이 좋습니다. 이 애니메이션 개체를 이벤트에 구독한 경우(ValueChanged 또는 IntegerValueChanged) 이러한 이벤트를 다시 활성화해야 합니다.

## <a name="canimationrectsetdefaultvalue"></a><a name="setdefaultvalue"></a>C애니메이션렉트::설정디폴값

기본값을 설정합니다.

```cpp
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
왼쪽, 위쪽, 오른쪽 및 하단에 대한 새 기본값을 지정합니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 기본값을 애니메이션 오브젝트로 설정합니다. 이 메서드는 사각형의 경계에 기본값을 할당합니다. 또한 기본 COM 개체가 생성된 경우 다시 만듭니다. 이 애니메이션 개체를 이벤트에 구독한 경우(ValueChanged 또는 IntegerValueChanged) 이러한 이벤트를 다시 활성화해야 합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
