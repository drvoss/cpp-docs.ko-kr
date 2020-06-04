---
title: CAnimationColor 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
ms.openlocfilehash: 7c1c98d739aa1c17bb30df2d9d4ce8c41558c76d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750197"
---
# <a name="canimationcolor-class"></a>CAnimationColor 클래스

빨강, 녹색 및 파랑 구성 요소에 애니메이션을 적용할 수 있는 색 기능을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationColor : public CAnimationBaseObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션컬러::C애니메이션컬러](#canimationcolor)|오버로드되었습니다. 애니메이션 색상 오브젝트를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션컬러::추가전환](#addtransition)|빨간색, 녹색 및 파란색 구성 요소에 대한 전환을 추가합니다.|
|[C애니메이션컬러::겟비](#getb)|파란색 구성 요소를 나타내는 CAnimation변수에 대한 액세스를 제공합니다.|
|[C애니메이션컬러::Getdefaultvalue](#getdefaultvalue)|색상 구성 요소에 대한 기본값을 반환합니다.|
|[C애니메이션컬러::겟G](#getg)|녹색 구성 요소를 나타내는 CAnimation변수에 대한 액세스를 제공합니다.|
|[C애니메이션컬러::게터](#getr)|빨간색 구성 요소를 나타내는 CAnimation변수에 대한 액세스를 제공합니다.|
|[C애니메이션컬러::겟밸류](#getvalue)|현재 값을 반환합니다.|
|[C애니메이션컬러::설정디폴값](#setdefaultvalue)|기본값을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션컬러::겟애니메이션변수리스트](#getanimationvariablelist)|캡슐화된 애니메이션 변수를 목록에 넣습니다. [(CAnimationBaseObject 재정의::GetAnimationVariablelist.)](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C애니메이션컬러::연산자 COLORREF](#operator_colorref)||
|[C애니메이션컬러::연산자=](#operator_eq)|CAnimationColor에 색상을 할당합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C애니메이션컬러::m_bValue](#m_bvalue)|애니메이션 색상의 파란색 구성 요소를 나타내는 캡슐화된 애니메이션 변수입니다.|
|[C애니메이션컬러:m_gValue](#m_gvalue)|애니메이션 색상의 녹색 구성 요소를 나타내는 캡슐화된 애니메이션 변수입니다.|
|[C애니메이션컬러:m_rValue](#m_rvalue)|애니메이션 색상의 빨간색 구성 요소를 나타내는 캡슐화된 애니메이션 변수입니다.|

## <a name="remarks"></a>설명

CAnimationColor 클래스는 세 개의 CAnimationVariable 개체를 캡슐화하고 응용 프로그램에서 색상을 나타낼 수 있습니다. 예를 들어 이 클래스를 사용하여 화면의 모든 개체의 색상(예: 텍스트 색상, 배경색 등)을 애니메이션할 수 있습니다. 응용 프로그램에서 이 클래스를 사용하려면 이 클래스의 개체를 인스턴스화하고 CAnimationController::AddAnimationObject를 사용하여 애니메이션 컨트롤러에 추가하고 각 전환이 빨간색, 녹색 및 파란색 구성 요소에 적용될 경우 AddTransition를 호출합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C애니메이션베이스오브젝트](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationColor`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationcoloraddtransition"></a><a name="addtransition"></a>C애니메이션컬러::추가전환

빨간색, 녹색 및 파란색 구성 요소에 대한 전환을 추가합니다.

```cpp
void AddTransition(
    CBaseTransition* pRTransition,
    CBaseTransition* pGTransition,
    CBaseTransition* pBTransition);
```

### <a name="parameters"></a>매개 변수

*pR 전환*<br/>
빨간색 구성 요소에 대한 전환입니다.

*pG트랜지션*<br/>
녹색 구성요소에 대한 전환입니다.

*pB 트랜지션*<br/>
파란색 구성 요소에 대한 전환입니다.

### <a name="remarks"></a>설명

색상 구성 요소를 나타내는 애니메이션 변수에 적용할 전환의 내부 목록에 지정된 전환을 추가하려면 이 함수를 호출합니다. 전환을 추가하면 전환이 즉시 적용되지 않고 내부 목록에 저장됩니다. CAnimationController::AnimateGroup을 호출할 때 전환이 적용됩니다(특정 값에 대한 스토리보드에 추가). 색상 구성 요소 중 하나에 전환을 적용할 필요가 없는 경우 NULL을 전달할 수 있습니다.

## <a name="canimationcolorcanimationcolor"></a><a name="canimationcolor"></a>C애니메이션컬러::C애니메이션컬러

CAnimationColor 개체를 생성합니다.

```
CAnimationColor();

CAnimationColor(
    COLORREF color,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
기본 색상을 지정합니다.

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

*n개체 ID*<br/>
개체 ID를 지정합니다.

*dw사용자 데이터*<br/>
사용자 정의 데이터를 지정합니다.

### <a name="remarks"></a>설명

오브젝트는 빨간색, 녹색, 파란색, 개체 ID 및 그룹 ID에 대한 기본값으로 생성되며, 이 값은 0으로 설정됩니다. 나중에 SetDefaultValue 및 SetID를 사용하여 런타임에 변경할 수 있습니다.

## <a name="canimationcolorgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>C애니메이션컬러::겟애니메이션변수리스트

캡슐화된 애니메이션 변수를 목록에 넣습니다.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```

### <a name="parameters"></a>매개 변수

*순*<br/>
함수가 반환되면 빨간색, 녹색 및 파란색 구성 요소를 나타내는 세 개의 CAnimationVariable 개체에 대한 포인터가 포함되어 있습니다.

## <a name="canimationcolorgetb"></a><a name="getb"></a>C애니메이션컬러::겟비

파란색 구성 요소를 나타내는 CAnimation변수에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetB();
```

### <a name="return-value"></a>Return Value

파란색 구성 요소를 나타내는 캡슐화된 CAnimationVariable에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 파란색 구성 요소를 나타내는 기본 CAnimationVariable에 직접 액세스할 수 있습니다.

## <a name="canimationcolorgetdefaultvalue"></a><a name="getdefaultvalue"></a>C애니메이션컬러::Getdefaultvalue

색상 구성 요소에 대한 기본값을 반환합니다.

```
COLORREF GetDefaultValue();
```

### <a name="return-value"></a>Return Value

RGB 구성 요소에 대한 기본값을 포함하는 COLORREF 값입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 생성자 또는 SetDefaultValue에 의해 이전에 설정된 기본값을 검색합니다.

## <a name="canimationcolorgetg"></a><a name="getg"></a>C애니메이션컬러::겟G

녹색 구성 요소를 나타내는 CAnimation변수에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetG();
```

### <a name="return-value"></a>Return Value

녹색 구성 요소를 나타내는 캡슐화된 CAnimationVariable에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 녹색 구성 요소를 나타내는 기본 CAnimationVariable에 직접 액세스할 수 있습니다.

## <a name="canimationcolorgetr"></a><a name="getr"></a>C애니메이션컬러::게터

빨간색 구성 요소를 나타내는 CAnimation변수에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetR();
```

### <a name="return-value"></a>Return Value

빨간색 구성 요소를 나타내는 캡슐화된 CAnimationVariable에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 빨간색 구성 요소를 나타내는 기본 CAnimationVariable에 직접 액세스할 수 있습니다.

## <a name="canimationcolorgetvalue"></a><a name="getvalue"></a>C애니메이션컬러::겟밸류

현재 값을 반환합니다.

```
BOOL GetValue(COLORREF& color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
출력 이 메서드가 반환될 때 현재 값을 포함합니다.

### <a name="return-value"></a>Return Value

TRUE, 현재 값이 성공적으로 검색된 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 함수를 호출하여 애니메이션 색상의 현재 값을 검색합니다. 이 메서드가 실패하거나 색상 구성 요소에 대한 기본 COM 개체가 초기화되지 않은 경우 색상에는 이전에 생성자 또는 SetDefaultValue에 의해 설정된 기본값이 포함됩니다.

## <a name="canimationcolorm_bvalue"></a><a name="m_bvalue"></a>C애니메이션컬러::m_bValue

애니메이션 색상의 파란색 구성 요소를 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_bValue;
```

## <a name="canimationcolorm_gvalue"></a><a name="m_gvalue"></a>C애니메이션컬러:m_gValue

애니메이션 색상의 녹색 구성 요소를 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_gValue;
```

## <a name="canimationcolorm_rvalue"></a><a name="m_rvalue"></a>C애니메이션컬러:m_rValue

애니메이션 색상의 빨간색 구성 요소를 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_rValue;
```

## <a name="canimationcoloroperator-colorref"></a><a name="operator_colorref"></a>C애니메이션컬러::연산자 COLORREF

```
operator COLORREF();
```

### <a name="return-value"></a>Return Value

## <a name="canimationcoloroperator"></a><a name="operator_eq"></a>C애니메이션컬러::연산자=

CAnimationColor에 색상을 할당합니다.

```cpp
void operator=(COLORREF color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
새 값 애니메이션 색상을 지정합니다.

### <a name="remarks"></a>설명

이 연산자는 SetDefaultValue를 호출하기 때문에 애니메이션을 시작하기 전에 이 작업을 수행하는 것이 좋습니다. 이 애니메이션 개체를 이벤트에 구독한 경우(ValueChanged 또는 IntegerValueChanged) 이러한 이벤트를 다시 활성화해야 합니다.

## <a name="canimationcolorsetdefaultvalue"></a><a name="setdefaultvalue"></a>C애니메이션컬러::설정디폴값

기본값을 설정합니다.

```cpp
void SetDefaultValue(COLORREF color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
빨간색, 녹색 및 파랑 구성요소에 대한 새 기본값을 지정합니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 기본값을 애니메이션 오브젝트로 설정합니다. 이 메서드는 애니메이션 색상의 색상 구성 요소에 기본값을 할당합니다. 또한 기본 COM 개체가 생성된 경우 다시 만듭니다. 이 애니메이션 개체를 이벤트에 구독한 경우(ValueChanged 또는 IntegerValueChanged) 이러한 이벤트를 다시 활성화해야 합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
