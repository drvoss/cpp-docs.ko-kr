---
title: CD2DGeometrySink 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::AddArc
- AFXRENDERTARGET/CD2DGeometrySink::AddBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddBeziers
- AFXRENDERTARGET/CD2DGeometrySink::AddLine
- AFXRENDERTARGET/CD2DGeometrySink::AddLines
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBeziers
- AFXRENDERTARGET/CD2DGeometrySink::BeginFigure
- AFXRENDERTARGET/CD2DGeometrySink::Close
- AFXRENDERTARGET/CD2DGeometrySink::EndFigure
- AFXRENDERTARGET/CD2DGeometrySink::Get
- AFXRENDERTARGET/CD2DGeometrySink::IsValid
- AFXRENDERTARGET/CD2DGeometrySink::SetFillMode
- AFXRENDERTARGET/CD2DGeometrySink::SetSegmentFlags
- AFXRENDERTARGET/CD2DGeometrySink::m_pSink
helpviewer_keywords:
- CD2DGeometrySink [MFC], CD2DGeometrySink
- CD2DGeometrySink [MFC], AddArc
- CD2DGeometrySink [MFC], AddBezier
- CD2DGeometrySink [MFC], AddBeziers
- CD2DGeometrySink [MFC], AddLine
- CD2DGeometrySink [MFC], AddLines
- CD2DGeometrySink [MFC], AddQuadraticBezier
- CD2DGeometrySink [MFC], AddQuadraticBeziers
- CD2DGeometrySink [MFC], BeginFigure
- CD2DGeometrySink [MFC], Close
- CD2DGeometrySink [MFC], EndFigure
- CD2DGeometrySink [MFC], Get
- CD2DGeometrySink [MFC], IsValid
- CD2DGeometrySink [MFC], SetFillMode
- CD2DGeometrySink [MFC], SetSegmentFlags
- CD2DGeometrySink [MFC], m_pSink
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
ms.openlocfilehash: bb5d2b53fa5899ac84608dc4ace6a84a3e5a7575
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754768"
---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink 클래스

ID2D1 지오메트리싱크의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DGeometrySink;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D 지오메트리싱크::CD2D지오메지오메트리싱크](#cd2dgeometrysink)|CD2DPathGeometry 개체에서 CD2DGeometrySink 개체를 생성합니다.|
|[CD2D 지오메트리싱크::~CD2D지오메지오메트리싱크](#_dtorcd2dgeometrysink)|소멸자입니다. D2D 지오메트리 싱크 오브젝트가 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D 지오메트리싱크::애드아크](#addarc)|경로 형상에 단일 호 추가|
|[CD2D지오메지오메트리싱크::애드베지어](#addbezier)|현재 점과 지정된 끝점 간에 입방형 3차원 곡선을 만듭니다.|
|[CD2D지오메지오메트리싱크::애드베지어](#addbeziers)|입방 베지어 곡선의 시퀀스를 만들고 지오메트리 싱크에 추가합니다.|
|[CD2D 지오메트리싱크::추가 줄](#addline)|현재 점과 지정된 끝점 사이에 선 세그먼트를 작성하여 형상 싱크에 추가합니다.|
|[CD2D 지오메트리싱크::추가줄](#addlines)|지정된 점을 사용하여 선 시퀀스를 작성하고 지오메트리 싱크에 추가합니다.|
|[CD2D지오메지오메트리싱크::애드쿼드라틱베지어](#addquadraticbezier)|현재 점과 지정된 끝점 간에 정방형 3차원 곡선을 만듭니다.|
|[CD2D지오메지오메트리싱크::애드쿼드라틱베지어스](#addquadraticbeziers)|단일 호출에서 이차 Bezier 세그먼트 시퀀스를 배열로 추가합니다.|
|[CD2D 지오메트리싱크::시작그림](#beginfigure)|지정된 점에서 새 그림을 시작합니다.|
|[CD2D 지오메트리싱크::닫기](#close)|지오메트리 싱크를 닫습니다.|
|[CD2D 지오메트리싱크::끝 그림](#endfigure)|현재 그림을 종료합니다. 선택적으로 닫습니다.|
|[CD2D 지오메트리싱크::Get](#get)|ID2D1 지오메트리싱크 인터페이스 반환|
|[CD2D 지오메트리싱크::유효하지 않음](#isvalid)|지오메트리 싱크 타당성 확인|
|[CD2D 지오메트리싱크::세트필모드](#setfillmode)|이 지오메트리 싱크에서 설명하는 형상 내부에 있는 점과 외부에 있는 점을 결정하는 데 사용되는 방법을 지정합니다.|
|[CD2D 지오메트리싱크::세트세그먼트 플래그](#setsegmentflags)|형상 싱크에 추가된 새 세그먼트에 적용할 획 및 결합 옵션을 지정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2D 지오메트리싱크::연산자 ID2D1 지오메트리싱크*](#operator_id2d1geometrysink_star)|ID2D1 지오메트리싱크 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D 지오메트리싱크::m_pSink](#m_psink)|ID2D1 Geometry싱크에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CD2DGeometrySink`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="_dtorcd2dgeometrysink"></a>CD2D 지오메트리싱크::~CD2D지오메지오메트리싱크

소멸자입니다. D2D 지오메트리 싱크 오브젝트가 소멸될 때 호출됩니다.

```
virtual ~CD2DGeometrySink();
```

## <a name="cd2dgeometrysinkaddarc"></a><a name="addarc"></a>CD2D 지오메트리싱크::애드아크

경로 형상에 단일 호 추가

```cpp
void AddArc(const D2D1_ARC_SEGMENT& arc);
```

### <a name="parameters"></a>매개 변수

*아크*<br/>
그림에 추가할 호 세그먼트

## <a name="cd2dgeometrysinkaddbezier"></a><a name="addbezier"></a>CD2D지오메지오메트리싱크::애드베지어

현재 점과 지정된 끝점 간에 입방형 3차원 곡선을 만듭니다.

```cpp
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>매개 변수

*3 차원*<br/>
추가할 Bezier 곡선의 제어점과 끝점을 설명하는 구조입니다.

## <a name="cd2dgeometrysinkaddbeziers"></a><a name="addbeziers"></a>CD2D지오메지오메트리싱크::애드베지어

입방 베지어 곡선의 시퀀스를 만들고 지오메트리 싱크에 추가합니다.

```cpp
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,
    D2D1_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>매개 변수

*베지어*<br/>
만들 수 있는 베지어 곡선을 설명하는 베지어 세그먼트의 배열입니다. 곡선은 형상 싱크의 현재 점(마지막 세그먼트의 끝점 또는 BeginFigure에 의해 지정된 위치)에서 배열의 첫 번째 베지어 세그먼트의 끝점까지 그려집니다. 배열에 추가 Bezier 세그먼트가 포함된 경우 각 후속 Bezier 세그먼트는 이전 Bezier 세그먼트의 끝점을 시작점으로 사용합니다.

## <a name="cd2dgeometrysinkaddline"></a><a name="addline"></a>CD2D 지오메트리싱크::추가 줄

현재 점과 지정된 끝점 사이에 선 세그먼트를 작성하여 형상 싱크에 추가합니다.

```cpp
void AddLine(CD2DPointF point);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
그릴 선의 끝점입니다.

## <a name="cd2dgeometrysinkaddlines"></a><a name="addlines"></a>CD2D 지오메트리싱크::추가줄

지정된 점을 사용하여 선 시퀀스를 작성하고 지오메트리 싱크에 추가합니다.

```cpp
void AddLines(
    const CArray<CD2DPointF,
    CD2DPointF>& points);
```

### <a name="parameters"></a>매개 변수

*포인트*<br/>
그릴 선을 설명하는 하나 이상의 점의 배열입니다. 선은 형상 싱크의 현재 점(마지막으로 그려진 마지막 세그먼트의 끝점 또는 BeginFigure에 의해 지정된 위치)에서 배열의 첫 번째 점으로 그려집니다. 배열에 추가 점이 포함된 경우 배열의 첫 번째 점에서 두 번째 점까지, 두 번째 점에서 세 번째 점까지의 선이 그려집니다. 그릴 선의 끝점 시퀀스의 배열입니다.

## <a name="cd2dgeometrysinkaddquadraticbezier"></a><a name="addquadraticbezier"></a>CD2D지오메지오메트리싱크::애드쿼드라틱베지어

현재 점과 지정된 끝점 간에 정방형 3차원 곡선을 만듭니다.

```cpp
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>매개 변수

*3 차원*<br/>
추가할 이차 Bezier 곡선의 제어점과 끝점을 설명하는 구조입니다.

## <a name="cd2dgeometrysinkaddquadraticbeziers"></a><a name="addquadraticbeziers"></a>CD2D지오메지오메트리싱크::애드쿼드라틱베지어스

단일 호출에서 이차 Bezier 세그먼트 시퀀스를 배열로 추가합니다.

```cpp
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>매개 변수

*베지어*<br/>
이차 베지어 세그먼트의 시퀀스의 배열.

## <a name="cd2dgeometrysinkbeginfigure"></a><a name="beginfigure"></a>CD2D 지오메트리싱크::시작그림

지정된 점에서 새 그림을 시작합니다.

```cpp
void BeginFigure(
    CD2DPointF startPoint,
    D2D1_FIGURE_BEGIN figureBegin);
```

### <a name="parameters"></a>매개 변수

*startPoint*<br/>
새 그림을 시작할 지점입니다.

*피규어시작*<br/>
새 그림이 비어 있어야 하는지 또는 채워야 하는지 여부입니다.

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="cd2dgeometrysink"></a>CD2D 지오메트리싱크::CD2D지오메지오메트리싱크

CD2DPathGeometry 개체에서 CD2DGeometrySink 개체를 생성합니다.

```
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```

### <a name="parameters"></a>매개 변수

*Pathgeometry*<br/>
기존 CD2DPathGeometry 개체입니다.

## <a name="cd2dgeometrysinkclose"></a><a name="close"></a>CD2D 지오메트리싱크::닫기

지오메트리 싱크를 닫습니다.

```
BOOL Close();
```

### <a name="return-value"></a>Return Value

성공하면 영하지 않은; 그렇지 않으면 거짓.

## <a name="cd2dgeometrysinkendfigure"></a><a name="endfigure"></a>CD2D 지오메트리싱크::끝 그림

현재 그림을 종료합니다. 선택적으로 닫습니다.

```cpp
void EndFigure(D2D1_FIGURE_END figureEnd);
```

### <a name="parameters"></a>매개 변수

*피겨엔드*<br/>
현재 그림이 닫혀 있는지 여부를 나타내는 값입니다. 그림이 닫히면 현재 점과 BeginFigure에서 지정한 시작점 사이에 선이 그려집니다.

## <a name="cd2dgeometrysinkget"></a><a name="get"></a>CD2D 지오메트리싱크::Get

ID2D1 지오메트리싱크 인터페이스 반환

```
ID2D1GeometrySink* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1GeometrySink 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dgeometrysinkisvalid"></a><a name="isvalid"></a>CD2D 지오메트리싱크::유효하지 않음

지오메트리 싱크 타당성 확인

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Return Value

형상 싱크가 유효한 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cd2dgeometrysinkm_psink"></a><a name="m_psink"></a>CD2D 지오메트리싱크::m_pSink

ID2D1 Geometry싱크에 대한 포인터입니다.

```
ID2D1GeometrySink* m_pSink;
```

## <a name="cd2dgeometrysinkoperator-id2d1geometrysink"></a><a name="operator_id2d1geometrysink_star"></a>CD2D 지오메트리싱크::연산자 ID2D1 지오메트리싱크*

ID2D1 지오메트리싱크 인터페이스 반환

```
operator ID2D1GeometrySink*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1GeometrySink 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dgeometrysinksetfillmode"></a><a name="setfillmode"></a>CD2D 지오메트리싱크::세트필모드

이 지오메트리 싱크에서 설명하는 형상 내부에 있는 점과 외부에 있는 점을 결정하는 데 사용되는 방법을 지정합니다.

```cpp
void SetFillMode(D2D1_FILL_MODE fillMode);
```

### <a name="parameters"></a>매개 변수

*채우기 모드*<br/>
지정된 점이 형상의 일부인지 여부를 확인하는 데 사용되는 메서드입니다.

## <a name="cd2dgeometrysinksetsegmentflags"></a><a name="setsegmentflags"></a>CD2D 지오메트리싱크::세트세그먼트 플래그

형상 싱크에 추가된 새 세그먼트에 적용할 획 및 결합 옵션을 지정합니다.

```cpp
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```

### <a name="parameters"></a>매개 변수

*정점 플래그*<br/>
지오메트리 싱크에 추가된 새 세그먼트에 적용할 획 및 결합 옵션을 사용할 수 있습니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
