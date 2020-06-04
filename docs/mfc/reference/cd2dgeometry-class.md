---
title: CD2DGeometry 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::Attach
- AFXRENDERTARGET/CD2DGeometry::CombineWithGeometry
- AFXRENDERTARGET/CD2DGeometry::CompareWithGeometry
- AFXRENDERTARGET/CD2DGeometry::ComputeArea
- AFXRENDERTARGET/CD2DGeometry::ComputeLength
- AFXRENDERTARGET/CD2DGeometry::ComputePointAtLength
- AFXRENDERTARGET/CD2DGeometry::Destroy
- AFXRENDERTARGET/CD2DGeometry::Detach
- AFXRENDERTARGET/CD2DGeometry::FillContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Get
- AFXRENDERTARGET/CD2DGeometry::GetBounds
- AFXRENDERTARGET/CD2DGeometry::GetWidenedBounds
- AFXRENDERTARGET/CD2DGeometry::IsValid
- AFXRENDERTARGET/CD2DGeometry::Outline
- AFXRENDERTARGET/CD2DGeometry::Simplify
- AFXRENDERTARGET/CD2DGeometry::StrokeContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Tessellate
- AFXRENDERTARGET/CD2DGeometry::Widen
- AFXRENDERTARGET/CD2DGeometry::m_pGeometry
helpviewer_keywords:
- CD2DGeometry [MFC], CD2DGeometry
- CD2DGeometry [MFC], Attach
- CD2DGeometry [MFC], CombineWithGeometry
- CD2DGeometry [MFC], CompareWithGeometry
- CD2DGeometry [MFC], ComputeArea
- CD2DGeometry [MFC], ComputeLength
- CD2DGeometry [MFC], ComputePointAtLength
- CD2DGeometry [MFC], Destroy
- CD2DGeometry [MFC], Detach
- CD2DGeometry [MFC], FillContainsPoint
- CD2DGeometry [MFC], Get
- CD2DGeometry [MFC], GetBounds
- CD2DGeometry [MFC], GetWidenedBounds
- CD2DGeometry [MFC], IsValid
- CD2DGeometry [MFC], Outline
- CD2DGeometry [MFC], Simplify
- CD2DGeometry [MFC], StrokeContainsPoint
- CD2DGeometry [MFC], Tessellate
- CD2DGeometry [MFC], Widen
- CD2DGeometry [MFC], m_pGeometry
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
ms.openlocfilehash: 4727f7b1799604001134ee2f4d2d2e1ce6db87fa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754778"
---
# <a name="cd2dgeometry-class"></a>CD2DGeometry 클래스

ID2D1지오메트리에 대한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D지오메트리: :CD2D지오메트리](#cd2dgeometry)|CD2D지오메트리 오브젝트를 생성합니다.|
|[CD2D 지오메트리: :~CD2D지오메트리](#_dtorcd2dgeometry)|소멸자입니다. D2D 형상 객체가 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D 지오메트리::연결](#attach)|기존 리소스 인터페이스를 개체에 연결합니다.|
|[CD2D 지오메트리::결합형상](#combinewithgeometry)|이 형상을 지정된 형상과 결합하고 결과를 ID2D1단순화지오메스티싱크에 저장합니다.|
|[CD2D 지오메트리::비교With지오메트리](#comparewithgeometry)|이 형상과 지정된 형상 간의 교차를 설명합니다. 비교는 지정된 평탄화 공차를 사용하여 수행됩니다.|
|[CD2D 지오메트리::계산 영역](#computearea)|지정된 행렬에 의해 변환되고 지정된 공차를 사용하여 병합된 후 형상의 면적을 계산합니다.|
|[CD2D 지오메트리::계산 길이](#computelength)|각 세그먼트가 선으로 언롤된 것처럼 형상의 길이를 계산합니다.|
|[CD2D 지오메트리::계산포인트길이](#computepointatlength)|지정된 행렬에 의해 변환되고 지정된 공차를 사용하여 평평해진 후 형상을 따라 지정된 거리에서 점및 접선 벡터를 계산합니다.|
|[CD2D지오메트리::D에스트로이](#destroy)|CD2D지오메트리 오브젝트를 삭제합니다. [(CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy)재정의.)|
|[CD2D지오메트리: :D](#detach)|개체에서 리소스 인터페이스 분리|
|[CD2D 지오메트리::채우기포함점](#fillcontainspoint)|형상으로 채워진 영역에 지정된 평탄화 공차가 주어진 지정된 점이 포함될지 여부를 나타냅니다.|
|[CD2D 지오메트리 : : Get](#get)|ID2D1 지오메트리 인터페이스 반환|
|[CD2D지오메트리::겟바운드](#getbounds)||
|[CD2D지오메트리: :GetWidened바운드](#getwidenedbounds)|지정된 스트로크 너비및 스타일에 의해 넓혀지고 지정된 행렬에 의해 변환된 후 형상의 경계를 가져옵니다.|
|[CD2D 지오메트리::유효하지 않음](#isvalid)|리소스 유효성 [검사(CD2DResource 재정의::유효합니다.)](../../mfc/reference/cd2dresource-class.md#isvalid)|
|[CD2D 지오메트리::윤곽선](#outline)|지오메트리의 윤곽을 계산하고 결과를 ID2D1단순화지오메스티싱크에 씁니다.|
|[CD2D 지오메트리::단순화](#simplify)|선만 포함하고(선택적으로) 입방 베지어 곡선을 포함하는 형상의 단순화된 버전을 작성하고 그 결과를 ID2D1단순화된 지오메트리싱크에 씁니다.|
|[CD2D 지오메트리::스트로크포함포인트](#strokecontainspoint)|지정된 획 두께, 스타일 및 변환에 지정된 점이 지오메트리의 획에 포함되는지 여부를 결정합니다.|
|[CD2D지오메트리: 테셀레이트](#tessellate)|지정한 행렬을 사용하여 변환되고 지정한 허용 오차를 사용하여 평면화된 기하 도형을 포괄하는 시계 방향으로 돌아가는 삼각형 집합을 만듭니다.|
|[CD2D 지오메트리: :확대](#widen)|지정된 스트로크로 형상을 넓히고 지정된 행렬에 의해 변환되고 지정된 공차를 사용하여 병합된 후 ID2D1단순화된 GeometryySink에 결과를 씁니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2D 지오메트리::연산자 ID2D1 지오메트리*](#operator_id2d1geometry_star)|ID2D1 지오메트리 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D 지오메트리:m_pGeometry](#m_pgeometry)|ID2D1Geometry에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

`CD2DGeometry`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dgeometrycd2dgeometry"></a><a name="_dtorcd2dgeometry"></a>CD2D 지오메트리: :~CD2D지오메트리

소멸자입니다. D2D 형상 객체가 소멸될 때 호출됩니다.

```
virtual ~CD2DGeometry();
```

## <a name="cd2dgeometryattach"></a><a name="attach"></a>CD2D 지오메트리::연결

기존 리소스 인터페이스를 개체에 연결합니다.

```cpp
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>매개 변수

*Presource*<br/>
기존 리소스 인터페이스입니다. NULL일 수 없음

## <a name="cd2dgeometrycd2dgeometry"></a><a name="cd2dgeometry"></a>CD2D지오메트리: :CD2D지오메트리

CD2D지오메트리 오브젝트를 생성합니다.

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

## <a name="cd2dgeometrycombinewithgeometry"></a><a name="combinewithgeometry"></a>CD2D 지오메트리::결합형상

이 형상을 지정된 형상과 결합하고 결과를 ID2D1단순화지오메스티싱크에 저장합니다.

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*입력 지오메트리*<br/>
이 인스턴스와 결합할 형상입니다.

*결합 모드*<br/>
수행할 결합 작업의 유형입니다.

*입력지오메지오메트리 변환*<br/>
결합하기 전에 입력지오메트리에 적용할 변환입니다.

*지오메트리 싱크*<br/>
결합 작업의 결과입니다.

*평탄화내성*<br/>
기하 도형의 다각형 근사에서 각 점들 사이의 거리에 허용되는 최대 범위입니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dgeometrycomparewithgeometry"></a><a name="comparewithgeometry"></a>CD2D 지오메트리::비교With지오메트리

이 형상과 지정된 형상 간의 교차를 설명합니다. 비교는 지정된 평탄화 공차를 사용하여 수행됩니다.

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*입력 지오메트리*<br/>
테스트할 형상입니다.

*입력지오메지오메트리 변환*<br/>
입력에 적용할 변환Geometry입니다.

*평탄화내성*<br/>
기하 도형의 다각형 근사에서 각 점들 사이의 거리에 허용되는 최대 범위입니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dgeometrycomputearea"></a><a name="computearea"></a>CD2D 지오메트리::계산 영역

지정된 행렬에 의해 변환되고 지정된 공차를 사용하여 병합된 후 형상의 면적을 계산합니다.

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*월드 트랜스포메이션*<br/>
해당 영역을 계산하기 전에 이 형상에 적용할 변환입니다.

*영역*<br/>
이 메서드가 반환되면 이 형상의 변형되고 병합된 버전의 영역에 대한 포인터가 포함됩니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*평탄화내성*<br/>
기하 도형의 다각형 근사에서 각 점 사이의 거리에 허용되는 최대 범위입니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dgeometrycomputelength"></a><a name="computelength"></a>CD2D 지오메트리::계산 길이

각 세그먼트가 선으로 언롤된 것처럼 형상의 길이를 계산합니다.

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*월드 트랜스포메이션*<br/>
길이를 계산하기 전에 형상에 적용할 변환입니다.

*length*<br/>
이 메서드가 반환되면 형상 길이에 대한 포인터가 포함됩니다. 닫힌 형상의 경우 길이에 암시적 닫는 세그먼트가 포함됩니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*평탄화내성*<br/>
기하 도형의 다각형 근사에서 각 점 사이의 거리에 허용되는 최대 범위입니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dgeometrycomputepointatlength"></a><a name="computepointatlength"></a>CD2D 지오메트리::계산포인트길이

지정된 행렬에 의해 변환되고 지정된 공차를 사용하여 평평해진 후 형상을 따라 지정된 거리에서 점및 접선 벡터를 계산합니다.

```
BOOL ComputePointAtLength(
    FLOAT length,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DPointF& point,
    CD2DPointF& unitTangentVector,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*length*<br/>
찾을 점과 접선의 지오메트리를 따라 가는 거리입니다. 이 거리가 0이 아니라면 이 방법은 형상의 첫 번째 점을 계산합니다. 이 거리가 형상의 길이보다 크면 이 방법은 형상의 마지막 점을 계산합니다.

*월드 트랜스포메이션*<br/>
지정된 점과 접선을 계산하기 전에 형상에 적용할 변환입니다.

*지점*<br/>
형상을 따라 지정된 거리의 위치입니다. 형상이 비어 있으면 이 점에는 NaN을 x 및 y 값으로 포함합니다.

*단위탄젠트벡터*<br/>
이 메서드가 반환되면 지오메트리를 따라 지정된 거리에 있는 접선 벡터에 대한 포인터가 포함됩니다. 형상이 비어 있으면 이 벡터에는 NaN이 x 및 y 값으로 포함됩니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*평탄화내성*<br/>
기하 도형의 다각형 근사에서 각 점 사이의 거리에 허용되는 최대 범위입니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dgeometrydestroy"></a><a name="destroy"></a>CD2D지오메트리::D에스트로이

CD2D지오메트리 오브젝트를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dgeometrydetach"></a><a name="detach"></a>CD2D지오메트리: :D

개체에서 리소스 인터페이스 분리

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>Return Value

분리된 리소스 인터페이스에 대한 포인터입니다.

## <a name="cd2dgeometryfillcontainspoint"></a><a name="fillcontainspoint"></a>CD2D 지오메트리::채우기포함점

형상으로 채워진 영역에 지정된 평탄화 공차가 주어진 지정된 점이 포함될지 여부를 나타냅니다.

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
테스트할 점입니다.

*월드 트랜스포메이션*<br/>
구속을 테스트하기 전에 형상에 적용할 변환입니다.

*포함*<br/>
이 메서드가 반환될 때 형상으로 채워진 영역에 점이 포함된 경우 TRUE인 bool 값이 포함됩니다. 그렇지 않으면 false입니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*평탄화내성*<br/>
정확한 기하학적 경로 및 경로 교차가 계산되는 숫자 정확도입니다. 점분이 허용오차보다 적게 누락된 점은 여전히 내부로 간주됩니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dgeometryget"></a><a name="get"></a>CD2D 지오메트리 : : Get

ID2D1 지오메트리 인터페이스 반환

```
ID2D1Geometry* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1Geometry 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dgeometrygetbounds"></a><a name="getbounds"></a>CD2D지오메트리::겟바운드

```
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,
CD2DRectF& bounds) const;
```

### <a name="parameters"></a>매개 변수

*월드 트랜스포메이션*<br/>
*범위*

### <a name="return-value"></a>Return Value

## <a name="cd2dgeometrygetwidenedbounds"></a><a name="getwidenedbounds"></a>CD2D지오메트리: :GetWidened바운드

지정된 스트로크 너비및 스타일에 의해 넓혀지고 지정된 행렬에 의해 변환된 후 형상의 경계를 가져옵니다.

```
BOOL GetWidenedBounds(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DRectF& bounds,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*스트로크 폭*<br/>
윤곽선을 쓰다듬어 형상을 넓게 하는 양입니다.

*스트로크 스타일*<br/>
형상을 넓혀주는 획의 스타일입니다.

*월드 트랜스포메이션*<br/>
형상이 변형된 후 형상이 스트로크된 후 형상에 적용할 변환입니다.

*범위*<br/>
이 메서드가 반환되면 확대된 형상의 경계가 포함됩니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*평탄화내성*<br/>
기하 도형의 다각형 근사에서 각 점들 사이의 거리에 허용되는 최대 범위입니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dgeometryisvalid"></a><a name="isvalid"></a>CD2D 지오메트리::유효하지 않음

리소스 유효성 검사

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Return Value

TRUE 리소스가 유효한 경우; 그렇지 않으면 거짓.

## <a name="cd2dgeometrym_pgeometry"></a><a name="m_pgeometry"></a>CD2D 지오메트리:m_pGeometry

ID2D1Geometry에 대한 포인터입니다.

```
ID2D1Geometry* m_pGeometry;
```

## <a name="cd2dgeometryoperator-id2d1geometry"></a><a name="operator_id2d1geometry_star"></a>CD2D 지오메트리::연산자 ID2D1 지오메트리*

ID2D1 지오메트리 인터페이스 반환

```
operator ID2D1Geometry*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1Geometry 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dgeometryoutline"></a><a name="outline"></a>CD2D 지오메트리::윤곽선

지오메트리의 윤곽을 계산하고 결과를 ID2D1단순화지오메스티싱크에 씁니다.

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*월드 트랜스포메이션*<br/>
형상 윤곽선에 적용할 변환입니다.

*지오메트리 싱크*<br/>
형상 변환 윤곽선이 추가되는 ID2D1단순화지오메스티시싱크.

*평탄화내성*<br/>
기하 도형의 다각형 근사에서 각 점 사이의 거리에 허용되는 최대 범위입니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dgeometrysimplify"></a><a name="simplify"></a>CD2D 지오메트리::단순화

선만 포함하고(선택적으로) 입방 베지어 곡선을 포함하는 형상의 단순화된 버전을 작성하고 그 결과를 ID2D1단순화된 지오메트리싱크에 씁니다.

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*단순화 옵션*<br/>
단순화된 형상에 곡선이 포함되어야 하는지 여부를 지정하는 값입니다.

*월드 트랜스포메이션*<br/>
단순화된 형상에 적용할 변환입니다.

*지오메트리 싱크*<br/>
단순화된 형상이 추가되는 ID2D1단순화지오메스티시싱크.

*평탄화내성*<br/>
기하 도형의 다각형 근사에서 각 점 사이의 거리에 허용되는 최대 범위입니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dgeometrystrokecontainspoint"></a><a name="strokecontainspoint"></a>CD2D 지오메트리::스트로크포함포인트

지정된 획 두께, 스타일 및 변환에 지정된 점이 지오메트리의 획에 포함되는지 여부를 결정합니다.

```
BOOL StrokeContainsPoint(
    CD2DPointF point,
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
포함 여부를 테스트할 점입니다.

*스트로크 폭*<br/>
적용할 스트로크의 두께입니다.

*스트로크 스타일*<br/>
적용할 스트로크 스타일입니다.

*월드 트랜스포메이션*<br/>
획이 된 형상에 적용할 변환입니다.

*포함*<br/>
이 메서드가 반환될 때 형상의 스트로크에 지정된 점이 포함된 경우 TRUE로 설정된 부울 값이 포함됩니다. 그렇지 않으면 false입니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*평탄화내성*<br/>
정확한 기하학적 경로 및 경로 교차가 계산되는 숫자 정확도입니다. 공차보다 적은 획이 누락된 점은 여전히 내부로 간주됩니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dgeometrytessellate"></a><a name="tessellate"></a>CD2D지오메트리: 테셀레이트

지정한 행렬을 사용하여 변환되고 지정한 허용 오차를 사용하여 평면화된 기하 도형을 포괄하는 시계 방향으로 돌아가는 삼각형 집합을 만듭니다.

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*월드 트랜스포메이션*<br/>
이 형상 또는 NULL에 적용할 변환입니다.

*테셀레이션싱크*<br/>
테셀레이션이 추가되는 ID2D1테셀레이션싱크입니다.

*평탄화내성*<br/>
기하 도형의 다각형 근사에서 각 점 사이의 거리에 허용되는 최대 범위입니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dgeometrywiden"></a><a name="widen"></a>CD2D 지오메트리: :확대

지정된 스트로크로 형상을 넓히고 지정된 행렬에 의해 변환되고 지정된 공차를 사용하여 병합된 후 ID2D1단순화된 GeometryySink에 결과를 씁니다.

```
BOOL Widen(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*스트로크 폭*<br/>
형상을 넓을 수 있는 양입니다.

*스트로크 스타일*<br/>
형상 또는 NULL에 적용할 스트로크 스타일입니다.

*월드 트랜스포메이션*<br/>
확대한 후 형상에 적용할 변환입니다.

*지오메트리 싱크*<br/>
ID2D1단순화된 형상이 추가되는 형상싱크.

*평탄화내성*<br/>
기하 도형의 다각형 근사에서 각 점 사이의 거리에 허용되는 최대 범위입니다. 값이 작을수록 결과가 정확해지지만 실행 속도는 느려집니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
