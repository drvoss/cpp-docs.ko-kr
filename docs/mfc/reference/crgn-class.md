---
title: CRgn 클래스
ms.date: 11/04/2016
f1_keywords:
- CRgn
- AFXWIN/CRgn
- AFXWIN/CRgn::CRgn
- AFXWIN/CRgn::CombineRgn
- AFXWIN/CRgn::CopyRgn
- AFXWIN/CRgn::CreateEllipticRgn
- AFXWIN/CRgn::CreateEllipticRgnIndirect
- AFXWIN/CRgn::CreateFromData
- AFXWIN/CRgn::CreateFromPath
- AFXWIN/CRgn::CreatePolygonRgn
- AFXWIN/CRgn::CreatePolyPolygonRgn
- AFXWIN/CRgn::CreateRectRgn
- AFXWIN/CRgn::CreateRectRgnIndirect
- AFXWIN/CRgn::CreateRoundRectRgn
- AFXWIN/CRgn::EqualRgn
- AFXWIN/CRgn::FromHandle
- AFXWIN/CRgn::GetRegionData
- AFXWIN/CRgn::GetRgnBox
- AFXWIN/CRgn::OffsetRgn
- AFXWIN/CRgn::PtInRegion
- AFXWIN/CRgn::RectInRegion
- AFXWIN/CRgn::SetRectRgn
helpviewer_keywords:
- CRgn [MFC], CRgn
- CRgn [MFC], CombineRgn
- CRgn [MFC], CopyRgn
- CRgn [MFC], CreateEllipticRgn
- CRgn [MFC], CreateEllipticRgnIndirect
- CRgn [MFC], CreateFromData
- CRgn [MFC], CreateFromPath
- CRgn [MFC], CreatePolygonRgn
- CRgn [MFC], CreatePolyPolygonRgn
- CRgn [MFC], CreateRectRgn
- CRgn [MFC], CreateRectRgnIndirect
- CRgn [MFC], CreateRoundRectRgn
- CRgn [MFC], EqualRgn
- CRgn [MFC], FromHandle
- CRgn [MFC], GetRegionData
- CRgn [MFC], GetRgnBox
- CRgn [MFC], OffsetRgn
- CRgn [MFC], PtInRegion
- CRgn [MFC], RectInRegion
- CRgn [MFC], SetRectRgn
ms.assetid: d904da84-76aa-481e-8780-b09485f49e64
ms.openlocfilehash: e84526eec8f4fd4b1935fa39bc7f4ed3c4d5dd71
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754484"
---
# <a name="crgn-class"></a>CRgn 클래스

Windows GDI(그래픽 디바이스 인터페이스) 영역을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CRgn : public CGdiObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CRgn::CRgn](#crgn)|`CRgn` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRgn::콤바인](#combinergn)|지정된 `CRgn` `CRgn` 두 객체의 결합과 동일하도록 객체를 설정합니다.|
|[CRgn::복사Rgn](#copyrgn)|지정된 `CRgn` `CRgn` 개체의 복사본이 되도록 개체를 설정합니다.|
|[CRgn::만들기EllipticRgn](#createellipticrgn)|타원형 영역으로 `CRgn` 오브젝트를 초기화합니다.|
|[CRgn::CreateEllipticRgnIndirect](#createellipticrgnindirect)|[RECT](/windows/win32/api/windef/ns-windef-rect) 구조체로 정의 된 타원 영역을 사용 하 여 `CRgn`개체를 초기화합니다.|
|[CRgn::생성데이터](#createfromdata)|지정된 지역 및 변환 데이터에서 영역을 만듭니다.|
|[CRgn::만들기FromPath](#createfrompath)|지정된 장치 컨텍스트로 선택된 경로에서 영역을 만듭니다.|
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|다각형 `CRgn` 영역으로 오브젝트를 초기화합니다. 시스템은 마지막 정점에서 첫 번째 정점으로 선을 그려 필요한 경우 다각형을 자동으로 닫습니다.|
|[CRgn::CreatePolyPolygonRgn](#createpolypolygonrgn)|일련의 닫힌 `CRgn` 다각형으로 구성된 영역으로 오브젝트를 초기화합니다. 다각형은 분리되거나 겹칠 수 있습니다.|
|[CRgn::CreateRectRgn](#createrectrgn)|직사각형 영역으로 `CRgn` 오브젝트를 초기화합니다.|
|[CRgn::창조RectRgn간접](#createrectrgnindirect)|[RECT](/windows/win32/api/windef/ns-windef-rect) 구조에서 정의된 사각형 영역을 사용하여 `CRgn` 개체를 초기화합니다.|
|[CRgn::만들기라운드렉트Rgn](#createroundrectrgn)|둥근 모서리가 `CRgn` 있는 직사각형 영역으로 오브젝트를 초기화합니다.|
|[CRgn::이퀄라이저그](#equalrgn)|두 `CRgn` 개체를 검사하여 객체가 동일한지 확인합니다.|
|[CRgn::에서 핸들](#fromhandle)|Windows 영역에 핸들이 `CRgn` 지정되면 개체에 대한 포인터를 반환합니다.|
|[CRgn::GetRegionData](#getregiondata)|지정된 버퍼에 지정된 영역을 설명하는 데이터로 채웁니다.|
|[CRgn:::GetRgnBox](#getrgnbox)|개체의 경계 사각형의 좌표를 검색합니다. `CRgn`|
|[CRgn::OffsetRgn](#offsetrgn)|지정된 `CRgn` 오프셋으로 오브젝트를 이동합니다.|
|[CRgn::PtInRegion](#ptinregion)|지정된 점이 영역에 있는지 여부를 결정합니다.|
|[CRgn::RectInRegion](#rectinregion)|지정된 사각형의 일부가 영역의 경계 내에 있는지 여부를 결정합니다.|
|[CRgn::SetRectRgn](#setrectrgn)|객체를 `CRgn` 지정된 직사각형 영역으로 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CRgn::연산자 HRGN](#operator_hrgn)|개체에 포함된 Windows `CRgn` 핸들을 반환합니다.|

## <a name="remarks"></a>설명

영역은 창 내의 타원형 또는 다각형 영역입니다. 영역을 사용하려면 클래스의 `CRgn` 멤버 로 정의된 클리핑 함수와 클래스의 `CDC`멤버 함수를 사용합니다.

멤버 함수는 `CRgn` 호출되는 지역 개체에 대한 정보를 생성, 변경 및 검색합니다.

사용에 `CRgn`대한 자세한 내용은 [그래픽 개체](../../mfc/graphic-objects.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CRgn`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="crgncombinergn"></a><a name="combinergn"></a>CRgn::콤바인

두 개의 기존 영역을 결합하여 새 GDI 영역을 만듭니다.

```
int CombineRgn(
    CRgn* pRgn1,
    CRgn* pRgn2,
    int nCombineMode);
```

### <a name="parameters"></a>매개 변수

*pRgn1*<br/>
기존 지역을 식별합니다.

*pRgn2*<br/>
기존 지역을 식별합니다.

*nCombineMode*<br/>
두 소스 영역을 결합할 때 수행할 작업을 지정합니다. 다음 값 중 하나일 수 있습니다.

- RGN_AND 두 영역(교차)의 겹치는 영역을 사용합니다.

- RGN_COPY 영역 1의 복사본을 *만듭니다(pRgn1로*식별).

- RGN_DIFF 영역 2의 일부가 아닌 영역 *1(pRgn1로*식별)의 영역으로 구성된 영역을 *만듭니다(pRgn2로*식별).

- RGN_OR 두 지역을 전체(공용 구조)로 결합합니다.

- RGN_XOR 두 영역을 결합하지만 겹치는 영역을 제거합니다.

### <a name="return-value"></a>Return Value

결과 영역의 유형을 지정합니다. 다음 값 중 하나일 수 있습니다.

- COMPLEXREGION 새 지역에는 겹치는 테두리가 있습니다.

- 오류 새 영역이 생성되지 않았습니다.

- NULLREGION 새 영역이 비어 있습니다.

- SIMPLEREGION 새 지역에는 겹치는 테두리가 없습니다.

### <a name="remarks"></a>설명

영역은 *nCombineMode*에 의해 지정된 대로 결합됩니다.

지정된 두 영역이 결합되고 결과 영역 핸들이 `CRgn` 개체에 저장됩니다. 따라서 `CRgn` 개체에 저장되는 모든 영역은 결합된 영역으로 대체됩니다.

영역의 크기는 32,767 x 32,767 논리 단위 또는 64K 메모리 중 더 작은 값으로 제한됩니다.

[CopyRgn을](#copyrgn) 사용하여 한 영역을 다른 지역으로 복사하면 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]

## <a name="crgncopyrgn"></a><a name="copyrgn"></a>CRgn::복사Rgn

*pRgnSrc에* 의해 정의된 영역을 `CRgn` 개체에 복사합니다.

```
int CopyRgn(CRgn* pRgnSrc);
```

### <a name="parameters"></a>매개 변수

*pRgnSrc*<br/>
기존 지역을 식별합니다.

### <a name="return-value"></a>Return Value

결과 영역의 유형을 지정합니다. 다음 값 중 하나일 수 있습니다.

- COMPLEXREGION 새 지역에는 겹치는 테두리가 있습니다.

- 오류 새 영역이 생성되지 않았습니다.

- NULLREGION 새 영역이 비어 있습니다.

- SIMPLEREGION 새 지역에는 겹치는 테두리가 없습니다.

### <a name="remarks"></a>설명

새 영역은 이전에 개체에 저장된 `CRgn` 영역을 대체합니다. 이 함수는 [CombineRgn](#combinergn) 멤버 함수의 특수한 경우입니다.

### <a name="example"></a>예제

  [CRgn::CreateEllipticRgn에](#createellipticrgn)대한 예제를 참조하십시오.

## <a name="crgncreateellipticrgn"></a><a name="createellipticrgn"></a>CRgn::만들기EllipticRgn

타원형 영역을 만듭니다.

```
BOOL CreateEllipticRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>매개 변수

*x1*<br/>
타원의 경계 사각형의 왼쪽 위 모서리의 논리적 x 좌표를 지정합니다.

*y1*<br/>
타원의 경계 사각형의 왼쪽 위 모서리의 논리적 y 좌표를 지정합니다.

*x2*<br/>
타원의 경계 사각형의 오른쪽 아래 모서리의 논리적 x 좌표를 지정합니다.

*y2*<br/>
타원의 경계 사각형의 오른쪽 아래 모서리의 논리적 y 좌표를 지정합니다.

### <a name="return-value"></a>Return Value

작업이 성공한 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

영역은 *x1,* *y1*, *x2*및 *y2로*지정된 경계 사각형으로 정의됩니다. 영역이 개체에 `CRgn` 저장됩니다.

영역의 크기는 32,767 x 32,767 논리 단위 또는 64K 메모리 중 더 작은 값으로 제한됩니다.

`CreateEllipticRgn` 함수를 사용하여 만든 영역을 사용하여 완료되면 응용 프로그램은 장치 컨텍스트에서 영역을 `DeleteObject` 선택하고 이 기능을 사용하여 제거해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]

## <a name="crgncreateellipticrgnindirect"></a><a name="createellipticrgnindirect"></a>CRgn:만들기EllipticRgn간접

타원형 영역을 만듭니다.

```
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
타원의 `RECT` 경계 사각형의 왼쪽 위 및 오른쪽 아래 모서리의 논리적 좌표를 포함하는 구조체 또는 `CRect` 객체를 가리킵니다.

### <a name="return-value"></a>Return Value

작업이 성공한 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

영역은 *lpRect에* 의해 가리키는 구조 또는 개체에 `CRgn` 의해 정의되며 개체에 저장됩니다.

영역의 크기는 32,767 x 32,767 논리 단위 또는 64K 메모리 중 더 작은 값으로 제한됩니다.

`CreateEllipticRgnIndirect` 함수를 사용하여 만든 영역을 사용하여 완료되면 응용 프로그램은 장치 컨텍스트에서 영역을 `DeleteObject` 선택하고 이 기능을 사용하여 제거해야 합니다.

### <a name="example"></a>예제

  [CRgn::CreateRectRgnIndirect에](#createrectrgnindirect)대한 예제를 참조하십시오.

## <a name="crgncreatefromdata"></a><a name="createfromdata"></a>CRgn::생성데이터

지정된 지역 및 변환 데이터에서 영역을 만듭니다.

```
BOOL CreateFromData(
    const XFORM* lpXForm,
    int nCount,
    const RGNDATA* pRgnData);
```

### <a name="parameters"></a>매개 변수

*lpXForm*<br/>
영역에서 수행할 변환을 정의하는 [XFORM](/windows/win32/api/wingdi/ns-wingdi-xform)ata 구조를 가리킵니다. 이 포인터가 NULL이면 ID 변환이 사용됩니다.

*nCount*<br/>
*pRgnData에*의해 가리키는 바이트 수를 지정합니다.

*pRgnData*<br/>
영역 데이터가 포함된 [RGNDATA](/windows/win32/api/wingdi/ns-wingdi-rgndata) 데이터 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램은 함수를 호출하여 지역에 `CRgn::GetRegionData` 대한 데이터를 검색할 수 있습니다.

## <a name="crgncreatefrompath"></a><a name="createfrompath"></a>CRgn::만들기FromPath

지정된 장치 컨텍스트로 선택된 경로에서 영역을 만듭니다.

```
BOOL CreateFromPath(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
닫힌 된 경로 포함 하는 장치 컨텍스트를 식별 합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

*pDC* 매개 변수로 식별되는 장치 컨텍스트에는 닫힌 경로가 포함되어야 합니다. 경로를 `CreateFromPath` 영역으로 변환한 후 Windows는 장치 컨텍스트에서 닫힌 경로를 삭제합니다.

## <a name="crgncreatepolygonrgn"></a><a name="createpolygonrgn"></a>CRgn::만들기PolygonRgn

다각형 영역을 만듭니다.

```
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,
    int nCount,
    int nMode);
```

### <a name="parameters"></a>매개 변수

*lpPoints*<br/>
구조의 `POINT` 배열 또는 개체 배열을 `CPoint` 가리킵니다. 각 구조는 다각형의 한 정점의 x 좌표와 y 좌표를 지정합니다. 구조에는 `POINT` 다음과 같은 양식이 있습니다.

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*nCount*<br/>
*lpPoints로*가리키는 `POINT` 배열의 `CPoint` 구조 또는 개체 수를 지정합니다.

*nMode*<br/>
영역의 충전 모드를 지정합니다. 이 매개변수는 대체 매개 변수이거나 권선될 수 있습니다.

### <a name="return-value"></a>Return Value

작업이 성공한 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

시스템은 마지막 정점에서 첫 번째 정점으로 선을 그려 필요한 경우 다각형을 자동으로 닫습니다. 결과 영역이 개체에 `CRgn` 저장됩니다.

영역의 크기는 32,767 x 32,767 논리 단위 또는 64K 메모리 중 더 작은 값으로 제한됩니다.

다각형 채우기 모드가 대체모드인 경우 시스템은 각 스캔 라인에서 홀수 번호와 짝수 다각형 측면 사이의 영역을 채웁니다. 즉, 시스템은 제1측과 제2면, 제3면과 제4면 사이의 면적을 채웁니다.

다각형 채우기 모드가 WINDING인 경우 시스템은 그림이 그려진 방향을 사용하여 영역을 채울지 여부를 결정합니다. 다각형의 각 선 세그먼트는 시계 방향 또는 시계 반대 방향으로 그려집니다. 동봉된 영역에서 그림의 바깥쪽으로 그려진 가상 선이 시계 방향 선 세그먼트를 통과할 때마다 개수가 증가합니다. 선이 시계 반대 방향으로 선 세그먼트를 통과하면 개수가 감소됩니다. 선이 그림의 바깥쪽에 도달하면 개수가 0이 아닌 경우 영역이 채워집니다.

응용 프로그램이 `CreatePolygonRgn` 함수로 만든 영역을 사용하여 완료되면 장치 컨텍스트에서 영역을 선택하고 `DeleteObject` 이 기능을 사용하여 제거해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]

## <a name="crgncreatepolypolygonrgn"></a><a name="createpolypolygonrgn"></a>CRgn::만들기PolyPolygonRgn

닫힌 다각형 시리즈로 구성된 영역을 만듭니다.

```
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,
    LPINT lpPolyCounts,
    int nCount,
    int nPolyFillMode);
```

### <a name="parameters"></a>매개 변수

*lpPoints*<br/>
다각형의 `POINT` 정점을 정의하는 `CPoint` 구조의 배열 또는 개체 배열을 가리킵니다. 시스템이 자동으로 닫히지 않으므로 각 다각형을 명시적으로 닫아야 합니다. 다각형은 연속적으로 지정됩니다. 구조에는 `POINT` 다음과 같은 양식이 있습니다.

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*lpPolyCounts*<br/>
정수 배열을 가리킵니다. 첫 번째 정수는 *lpPoints* 배열의 첫 번째 다각형의 정점 수를 지정하고 두 번째 정수는 두 번째 다각형의 정점 수를 지정합니다.

*nCount*<br/>
*lpPolyCounts* 배열의 총 정수 수를 지정합니다.

*nPolyFillMode*<br/>
다각형 채우기 모드를 지정합니다. 이 값은 대체 값이거나 권선될 수 있습니다.

### <a name="return-value"></a>Return Value

작업이 성공한 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

결과 영역이 개체에 `CRgn` 저장됩니다.

다각형은 분리되거나 겹칠 수 있습니다.

영역의 크기는 32,767 x 32,767 논리 단위 또는 64K 메모리 중 더 작은 값으로 제한됩니다.

다각형 채우기 모드가 대체모드인 경우 시스템은 각 스캔 라인에서 홀수 번호와 짝수 다각형 측면 사이의 영역을 채웁니다. 즉, 시스템은 제1측과 제2면, 제3면과 제4면 사이의 면적을 채웁니다.

다각형 채우기 모드가 WINDING인 경우 시스템은 그림이 그려진 방향을 사용하여 영역을 채울지 여부를 결정합니다. 다각형의 각 선 세그먼트는 시계 방향 또는 시계 반대 방향으로 그려집니다. 동봉된 영역에서 그림의 바깥쪽으로 그려진 가상 선이 시계 방향 선 세그먼트를 통과할 때마다 개수가 증가합니다. 선이 시계 반대 방향으로 선 세그먼트를 통과하면 개수가 감소됩니다. 선이 그림의 바깥쪽에 도달하면 개수가 0이 아닌 경우 영역이 채워집니다.

응용 프로그램이 `CreatePolyPolygonRgn` 함수로 만든 영역을 사용하여 완료되면 장치 컨텍스트에서 영역을 선택하고 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) 멤버 함수를 사용하여 제거해야 합니다.

## <a name="crgncreaterectrgn"></a><a name="createrectrgn"></a>CRgn::CreateRectRgn

개체에 저장된 직사각형 영역을 `CRgn` 만듭니다.

```
BOOL CreateRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>매개 변수

*x1*<br/>
영역의 왼쪽 위 모서리의 논리적 x 좌표를 지정합니다.

*y1*<br/>
영역의 왼쪽 위 모서리의 논리적 y 좌표를 지정합니다.

*x2*<br/>
영역의 오른쪽 아래 모서리의 논리적 x 좌표를 지정합니다.

*y2*<br/>
영역의 오른쪽 아래 모서리의 논리적 y 좌표를 지정합니다.

### <a name="return-value"></a>Return Value

작업이 성공한 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

영역의 크기는 32,767 x 32,767 논리 단위 또는 64K 메모리 중 더 작은 값으로 제한됩니다.

`CreateRectRgn`에서 만든 영역을 사용 하 여 완료 되 면 응용 프로그램은 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) 멤버 함수를 사용 하 여 영역을 제거 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]

추가 예제는 [CRgn::CombineRgn](#combinergn)을 참조하십시오.

## <a name="crgncreaterectrgnindirect"></a><a name="createrectrgnindirect"></a>CRgn::창조RectRgn간접

개체에 저장된 직사각형 영역을 `CRgn` 만듭니다.

```
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
영역의 `RECT` 왼쪽 `CRect` 위 및 오른쪽 아래 모서리의 논리적 좌표를 포함하는 구조또는 오브젝트를 가리킵니다. 구조에는 `RECT` 다음과 같은 양식이 있습니다.

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Return Value

작업이 성공한 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

영역의 크기는 32,767 x 32,767 논리 단위 또는 64K 메모리 중 더 작은 값으로 제한됩니다.

`CreateRectRgnIndirect`에서 만든 영역을 사용 하 여 완료 되 면 응용 프로그램은 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) 멤버 함수를 사용 하 여 영역을 제거 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]

## <a name="crgncreateroundrectrgn"></a><a name="createroundrectrgn"></a>CRgn::만들기라운드렉트Rgn

오브젝트에 저장된 둥근 모서리가 있는 직사각형 `CRgn` 영역을 만듭니다.

```
BOOL CreateRoundRectRgn(
    int x1,
    int y1,
    int x2,
    int y2,
    int x3,
    int y3);
```

### <a name="parameters"></a>매개 변수

*x1*<br/>
영역의 왼쪽 위 모서리의 논리적 x 좌표를 지정합니다.

*y1*<br/>
영역의 왼쪽 위 모서리의 논리적 y 좌표를 지정합니다.

*x2*<br/>
영역의 오른쪽 아래 모서리의 논리적 x 좌표를 지정합니다.

*y2*<br/>
영역의 오른쪽 아래 모서리의 논리적 y 좌표를 지정합니다.

*x3*<br/>
둥근 모서리를 만드는 데 사용되는 타원의 너비를 지정합니다.

*y3*<br/>
둥근 모서리를 만드는 데 사용되는 타원의 높이를 지정합니다.

### <a name="return-value"></a>Return Value

작업이 성공한 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

영역의 크기는 32,767 x 32,767 논리 단위 또는 64K 메모리 중 더 작은 값으로 제한됩니다.

응용 프로그램이 `CreateRoundRectRgn` 함수로 만든 영역을 사용하여 완료되면 장치 컨텍스트에서 영역을 선택하고 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) 멤버 함수를 사용하여 제거해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]

## <a name="crgncrgn"></a><a name="crgn"></a>CRgn::CRgn

`CRgn` 개체를 생성합니다.

```
CRgn();
```

### <a name="remarks"></a>설명

`m_hObject` 개체가 하나 이상의 다른 `CRgn` 멤버 함수로 초기화될 때까지 데이터 멤버는 유효한 Windows GDI 영역을 포함하지 않습니다.

### <a name="example"></a>예제

  [CRgn::CreateRoundRectRgn에](#createroundrectrgn)대한 예제를 참조하십시오.

## <a name="crgnequalrgn"></a><a name="equalrgn"></a>CRgn::이퀄라이저그

지정된 영역이 `CRgn` 개체에 저장된 영역과 동일한지 여부를 결정합니다.

```
BOOL EqualRgn(CRgn* pRgn) const;
```

### <a name="parameters"></a>매개 변수

*pRgn*<br/>
지역을 식별합니다.

### <a name="return-value"></a>Return Value

두 영역이 동일한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]

## <a name="crgnfromhandle"></a><a name="fromhandle"></a>CRgn::에서 핸들

Windows 영역에 핸들이 `CRgn` 지정되면 개체에 대한 포인터를 반환합니다.

```
static CRgn* PASCAL FromHandle(HRGN hRgn);
```

### <a name="parameters"></a>매개 변수

*hRgn*<br/>
Windows 영역에 대한 핸들을 지정합니다.

### <a name="return-value"></a>Return Value

`CRgn` 개체에 대한 포인터입니다. 함수가 성공하지 못하면 반환 값은 NULL입니다.

### <a name="remarks"></a>설명

개체가 `CRgn` 핸들에 아직 연결되어 있지 않으면 `CRgn` 임시 개체가 만들어지고 첨부됩니다. 이 `CRgn` 임시 개체는 다음에 응용 프로그램이 이벤트 루프에서 유휴 시간을 가지며 모든 임시 그래픽 개체가 삭제될 때까지만 유효합니다. 이 것을 말하는 또 다른 방법은 임시 개체가 하나의 창 메시지를 처리하는 동안에만 유효하다는 것입니다.

## <a name="crgngetregiondata"></a><a name="getregiondata"></a>CRgn::GetRegionData

지정된 버퍼에 영역을 설명하는 데이터로 채웁니다.

```
int GetRegionData(
    LPRGNDATA lpRgnData,
    int nCount) const;
```

### <a name="parameters"></a>매개 변수

*lpRgnData*<br/>
정보를 수신하는 [RGNDATA](/windows/win32/api/wingdi/ns-wingdi-rgndata) 데이터 구조를 가리킵니다. 이 매개 변수가 NULL이면 return 값에는 지역 데이터에 필요한 바이트 수가 포함됩니다.

*nCount*<br/>
*lpRgnData* 버퍼의 크기를 바이트별로 지정합니다.

### <a name="return-value"></a>Return Value

함수가 성공하고 *nCount가* 적절한 바이트 수를 지정하면 반환 값은 항상 *nCount*입니다. 함수가 실패하거나 *nCount가* 적절한 바이트 수 미만을 지정하는 경우 반환 값은 0(오류)입니다.

### <a name="remarks"></a>설명

이 데이터에는 영역을 구성하는 사각형의 차원이 포함됩니다. 이 함수는 `CRgn::CreateFromData` 함수와 함께 사용됩니다.

## <a name="crgngetrgnbox"></a><a name="getrgnbox"></a>CRgn:::GetRgnBox

개체의 경계 사각형의 좌표를 검색합니다. `CRgn`

```
int GetRgnBox(LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
경계 사각형의 `RECT` `CRect` 좌표를 수신할 구조체 또는 객체를 가리킵니다. 구조에는 `RECT` 다음과 같은 양식이 있습니다.

`typedef struct tagRECT {`

`int left;`

`int top;`

`int right;`

`int bottom;`

`} RECT;`

### <a name="return-value"></a>Return Value

영역의 유형을 지정합니다. 다음 값 중 하나일 수 있습니다.

- COMPLEXREGION 지역은 겹치는 테두리가 있습니다.

- NULLREGION 영역이 비어 있습니다.

- ERROR `CRgn` 개체가 유효한 영역을 지정하지 않습니다.

- SIMPLEREGION 지역에는 겹치는 테두리가 없습니다.

### <a name="example"></a>예제

  [CRgn::CreatePolygonRgn에](#createpolygonrgn)대한 예제를 참조하십시오.

## <a name="crgnoffsetrgn"></a><a name="offsetrgn"></a>CRgn::오프셋Rgn

`CRgn` 지정된 간격띄우기별로 오브젝트에 저장된 영역을 이동합니다.

```
int OffsetRgn(
    int x,
    int y);

int OffsetRgn(POINT point);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
왼쪽 또는 오른쪽으로 이동할 단위 수를 지정합니다.

*Y*<br/>
위 또는 아래로 이동할 단위 수를 지정합니다.

*지점*<br/>
*점의* x 좌표는 왼쪽 또는 오른쪽으로 이동할 단위 수를 지정합니다. *점의* y 좌표는 위 또는 아래로 이동할 단위 수를 지정합니다. *점* 매개변수는 `POINT` 구조체 또는 `CPoint` 객체일 수 있습니다.

### <a name="return-value"></a>Return Value

새 지역의 형식입니다. 다음 값 중 하나일 수 있습니다.

- COMPLEXREGION 지역은 겹치는 테두리가 있습니다.

- 오류 지역 핸들이 잘못되었습니다.

- NULLREGION 영역이 비어 있습니다.

- SIMPLEREGION 지역에는 겹치는 테두리가 없습니다.

### <a name="remarks"></a>설명

이 함수는 y축을 따라 x축 및 *y* 단위를 따라 영역 *x* 단위를 이동합니다.

영역의 좌표 값은 32,767보다 크거나 -32,768보다 커야 합니다. 잘못된 영역 좌표를 방지하기 위해 *x* 및 *y* 매개변수를 신중하게 선택해야 합니다.

### <a name="example"></a>예제

  [CRgn::CreateEllipticRgn에](#createellipticrgn)대한 예제를 참조하십시오.

## <a name="crgnoperator-hrgn"></a><a name="operator_hrgn"></a>CRgn::연산자 HRGN

이 연산자를 사용하여 개체의 연결된 `CRgn` Windows GDI 핸들을 가져옵니다.

```
operator HRGN() const;
```

### <a name="return-value"></a>Return Value

성공하면 개체로 표시되는 Windows GDI 개체에 대한 핸들입니다. `CRgn` 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 연산자는 HRGN 개체의 직접 사용을 지원하는 캐스팅 연산자입니다.

그래픽 개체 사용에 대한 자세한 내용은 Windows SDK의 [그래픽 개체](/windows/win32/gdi/graphic-objects) 문서를 참조하십시오.

## <a name="crgnptinregion"></a><a name="ptinregion"></a>CRgn::PtInRegion

*x* 및 *y가* 지정한 점이 `CRgn` 개체에 저장된 영역에 있는지 확인합니다.

```
BOOL PtInRegion(
    int x,
    int y) const;

BOOL PtInRegion(POINT point) const;
```

### <a name="parameters"></a>매개 변수

*x*<br/>
테스트할 점의 논리적 x 좌표를 지정합니다.

*Y*<br/>
테스트할 점의 논리적 y 좌표를 지정합니다.

*지점*<br/>
*점의* x-및 y 좌표는 값을 테스트하기 위해 점의 x-및 y 좌표를 지정합니다. *점* 매개변수는 구조체 `POINT` 또는 `CPoint` 객체일 수 있습니다.

### <a name="return-value"></a>Return Value

점이 영역에 있는 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="crgnrectinregion"></a><a name="rectinregion"></a>CRgn::정류 지역

*lpRect에* 의해 지정된 사각형의 일부가 `CRgn` 개체에 저장된 영역의 경계 내에 있는지 여부를 결정합니다.

```
BOOL RectInRegion(LPCRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
구조또는객체를가리킵니요. `RECT` `CRect` 구조에는 `RECT` 다음과 같은 양식이 있습니다.

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Return Value

지정된 사각형의 일부가 영역의 경계 내에 있는 경우 비영입니다. 그렇지 않으면 0.

## <a name="crgnsetrectrgn"></a><a name="setrectrgn"></a>CRgn::SetRectRgn

사각형 영역을 만듭니다.

```cpp
void SetRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);

void SetRectRgn(LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*x1*<br/>
직사각형 영역의 왼쪽 위 모서리의 x 좌표를 지정합니다.

*y1*<br/>
직사각형 영역의 왼쪽 위 모서리의 y 좌표를 지정합니다.

*x2*<br/>
직사각형 영역의 오른쪽 아래 모서리의 x 좌표를 지정합니다.

*y2*<br/>
직사각형 영역의 오른쪽 아래 모서리의 y 좌표를 지정합니다.

*Lprect*<br/>
직사각형 영역을 지정합니다. `RECT` 구조체 또는 개체에 대한 `CRect` 포인터일 수 있습니다.

### <a name="remarks"></a>설명

[그러나 CreateRectRgn과](#createrectrgn)달리 로컬 Windows 응용 프로그램 힙에서 추가 메모리를 할당하지 는 않습니다. 대신 `CRgn` 개체에 저장된 영역에 할당된 공간을 사용합니다. 즉, 개체를 `CRgn` 호출하기 `SetRectRgn`전에 유효한 Windows 영역으로 이미 초기화되어 있어야 합니다. *x1,* *y1*, *x2*및 *y2로* 지정된 점은 할당된 공간의 최소 크기를 지정합니다.

로컬 메모리 관리자에 `CreateRectRgn` 대한 호출을 방지하려면 멤버 함수 대신 이 함수를 사용합니다.

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
