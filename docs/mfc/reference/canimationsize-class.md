---
title: CAnimationSize 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
ms.openlocfilehash: 1f4a5b8b52d8bd37d1ed83618e7451dd85f84c32
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755124"
---
# <a name="canimationsize-class"></a>CAnimationSize 클래스

차원에 애니메이션을 적용할 수 있는 크기 개체 기능을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationSize : public CAnimationBaseObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C애니메이션크기::C애니메이션크기](#canimationsize)|오버로드되었습니다. 애니메이션 크기 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션크기::추가 전환](#addtransition)|폭 및 높이에 대한 전환을 추가합니다.|
|[C애니메이션 크기 :: GetCX](#getcx)|너비를 나타내는 CAnimation변수에 대한 액세스를 제공합니다.|
|[C애니메이션 크기 :: GetCY](#getcy)|높이를 나타내는 CAnimation변수에 대한 액세스를 제공합니다.|
|[C애니메이션크기::Getdefaultvalue](#getdefaultvalue)|너비 및 높이에 대한 기본값을 반환합니다.|
|[C애니메이션 크기::GetValue](#getvalue)|현재 값을 반환합니다.|
|[C애니메이션크기::설정디폴값](#setdefaultvalue)|기본값을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C애니메이션크기::겟애니메이션변수리스트](#getanimationvariablelist)|캡슐화된 애니메이션 변수를 목록에 넣습니다. [(CAnimationBaseObject 재정의::GetAnimationVariablelist.)](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C애니메이션크기::연산자 CSize](#operator_csize)|CAnimationSize를 CSize로 변환합니다.|
|[C애니메이션크기::연산자=](#operator_eq)|SzSrc를 CAnimationSize에 할당합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C애니메이션크기:m_cxValue](#m_cxvalue)|애니메이션 크기의 너비를 나타내는 캡슐화된 애니메이션 변수입니다.|
|[C애니메이션크기:m_cyValue](#m_cyvalue)|애니메이션 크기의 높이를 나타내는 캡슐화된 애니메이션 변수입니다.|

## <a name="remarks"></a>설명

CAnimationSize 클래스는 두 개의 CAnimationVariable 개체를 캡슐화하며 응용 프로그램에서 크기로 나타낼 수 있습니다. 예를 들어 이 클래스를 사용하여 화면의 2차원 개체 크기(예: 사각형, 컨트롤 등)를 애니메이션할 수 있습니다. 응용 프로그램에서 이 클래스를 사용하려면 이 클래스의 개체를 인스턴스화하고 CAnimationController::AddAnimationObject를 사용하여 애니메이션 컨트롤러에 추가하고 각 전환이 너비 및/또는 높이에 적용될 경우 AddTransition를 호출합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[C애니메이션베이스오브젝트](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

## <a name="canimationsizeaddtransition"></a><a name="addtransition"></a>C애니메이션크기::추가 전환

폭 및 높이에 대한 전환을 추가합니다.

```cpp
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>매개 변수

*pCX트랜지션*<br/>
너비에 대해 전환할 포인터입니다.

*pCY 전환*<br/>
높이에 대한 전환포인터입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 너비 및 높이에 대한 애니메이션 변수에 적용할 전환의 내부 목록에 지정된 전환을 추가합니다. 전환을 추가하면 전환이 즉시 적용되지 않고 내부 목록에 저장됩니다. CAnimationController::AnimateGroup을 호출할 때 전환이 적용됩니다(특정 값에 대한 스토리보드에 추가). 차원 중 하나에 전환을 적용할 필요가 없는 경우 NULL을 전달할 수 있습니다.

## <a name="canimationsizecanimationsize"></a><a name="canimationsize"></a>C애니메이션크기::C애니메이션크기

애니메이션 크기 개체를 생성합니다.

```
CAnimationSize();

CAnimationSize(
    const CSize& szDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>매개 변수

*szDefault*<br/>
기본 크기를 지정합니다.

*n그룹 ID*<br/>
그룹 ID를 지정합니다.

*n개체 ID*<br/>
개체 ID를 지정합니다.

*dw사용자 데이터*<br/>
사용자 정의 데이터를 지정합니다.

### <a name="remarks"></a>설명

개체는 너비, 높이, 개체 ID 및 그룹 ID에 대한 기본값으로 생성되며, 이 값은 0으로 설정됩니다. 나중에 SetDefaultValue 및 SetID를 사용하여 런타임에 변경할 수 있습니다.

## <a name="canimationsizegetanimationvariablelist"></a><a name="getanimationvariablelist"></a>C애니메이션크기::겟애니메이션변수리스트

캡슐화된 애니메이션 변수를 목록에 넣습니다.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>매개 변수

*순*<br/>
함수가 반환되면 너비와 높이를 나타내는 두 개의 CAnimationVariable 개체에 대한 포인터가 포함됩니다.

## <a name="canimationsizegetcx"></a><a name="getcx"></a>C애니메이션 크기 :: GetCX

너비를 나타내는 CAnimation변수에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>Return Value

너비를 나타내는 캡슐화된 CAnimationVariable에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 너비를 나타내는 기본 CAnimationVariable에 직접 액세스할 수 있습니다.

## <a name="canimationsizegetcy"></a><a name="getcy"></a>C애니메이션 크기 :: GetCY

높이를 나타내는 CAnimation변수에 대한 액세스를 제공합니다.

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>Return Value

높이를 나타내는 캡슐화된 CAnimationVariable에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 높이를 나타내는 기본 CAnimationVariable에 직접 액세스할 수 있습니다.

## <a name="canimationsizegetdefaultvalue"></a><a name="getdefaultvalue"></a>C애니메이션크기::Getdefaultvalue

너비 및 높이에 대한 기본값을 반환합니다.

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>Return Value

기본값을 포함하는 CSize 개체입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 생성자 또는 SetDefaultValue에 의해 이전에 설정된 기본값을 검색합니다.

## <a name="canimationsizegetvalue"></a><a name="getvalue"></a>C애니메이션 크기::GetValue

현재 값을 반환합니다.

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>매개 변수

*sz값*<br/>
출력 이 메서드가 반환될 때 현재 값을 포함합니다.

### <a name="return-value"></a>Return Value

TRUE, 현재 값이 성공적으로 검색된 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 함수를 호출하여 애니메이션 크기의 현재 값을 검색합니다. 이 메서드가 실패하거나 너비 및 크기에 대한 기본 COM 개체가 초기화되지 않은 경우 szValue에는 생성자 또는 SetDefaultValue에 의해 이전에 설정된 기본값이 포함됩니다.

## <a name="canimationsizem_cxvalue"></a><a name="m_cxvalue"></a>C애니메이션크기:m_cxValue

애니메이션 크기의 너비를 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_cxValue;
```

## <a name="canimationsizem_cyvalue"></a><a name="m_cyvalue"></a>C애니메이션크기:m_cyValue

애니메이션 크기의 높이를 나타내는 캡슐화된 애니메이션 변수입니다.

```
CAnimationVariable m_cyValue;
```

## <a name="canimationsizeoperator-csize"></a><a name="operator_csize"></a>C애니메이션크기::연산자 CSize

CAnimationSize를 CSize로 변환합니다.

```
operator CSize();
```

### <a name="return-value"></a>Return Value

애니메이션 크기의 현재 값(CSize)입니다.

### <a name="remarks"></a>설명

이 함수는 내부적으로 GetValue를 호출합니다. 어떤 이유로 GetValue가 실패하면 반환된 크기에 너비 및 높이에 대한 기본값이 포함됩니다.

## <a name="canimationsizeoperator"></a><a name="operator_eq"></a>C애니메이션크기::연산자=

SzSrc를 CAnimationSize에 할당합니다.

```cpp
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>매개 변수

*szSrc*<br/>
CSize 또는 크기를 나타냅니다.

### <a name="remarks"></a>설명

SzSrc를 CAnimationSize에 할당합니다. 이 연산자는 SetDefaultValue를 호출하기 때문에 애니메이션을 시작하기 전에 이 작업을 수행하는 것이 좋습니다. 이 애니메이션 개체를 이벤트에 구독한 경우(ValueChanged 또는 IntegerValueChanged) 이러한 이벤트를 다시 활성화해야 합니다.

## <a name="canimationsizesetdefaultvalue"></a><a name="setdefaultvalue"></a>C애니메이션크기::설정디폴값

기본값을 설정합니다.

```cpp
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>매개 변수

*szDefault*<br/>
새 기본 크기를 지정합니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 기본값을 애니메이션 오브젝트로 설정합니다. 이 메서드는 기본값을 애니메이션 크기의 너비 및 높이에 할당합니다. 또한 기본 COM 개체가 생성된 경우 다시 만듭니다. 이 애니메이션 개체를 이벤트에 구독한 경우(ValueChanged 또는 IntegerValueChanged) 이러한 이벤트를 다시 활성화해야 합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
