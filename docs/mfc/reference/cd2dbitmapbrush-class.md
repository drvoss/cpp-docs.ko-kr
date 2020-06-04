---
title: CD2DBitmapBrush 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::Attach
- AFXRENDERTARGET/CD2DBitmapBrush::Create
- AFXRENDERTARGET/CD2DBitmapBrush::Destroy
- AFXRENDERTARGET/CD2DBitmapBrush::Detach
- AFXRENDERTARGET/CD2DBitmapBrush::Get
- AFXRENDERTARGET/CD2DBitmapBrush::GetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::GetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::SetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::SetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::CommonInit
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrushProperties
helpviewer_keywords:
- CD2DBitmapBrush [MFC], CD2DBitmapBrush
- CD2DBitmapBrush [MFC], Attach
- CD2DBitmapBrush [MFC], Create
- CD2DBitmapBrush [MFC], Destroy
- CD2DBitmapBrush [MFC], Detach
- CD2DBitmapBrush [MFC], Get
- CD2DBitmapBrush [MFC], GetBitmap
- CD2DBitmapBrush [MFC], GetExtendModeX
- CD2DBitmapBrush [MFC], GetExtendModeY
- CD2DBitmapBrush [MFC], GetInterpolationMode
- CD2DBitmapBrush [MFC], SetBitmap
- CD2DBitmapBrush [MFC], SetExtendModeX
- CD2DBitmapBrush [MFC], SetExtendModeY
- CD2DBitmapBrush [MFC], SetInterpolationMode
- CD2DBitmapBrush [MFC], CommonInit
- CD2DBitmapBrush [MFC], m_pBitmap
- CD2DBitmapBrush [MFC], m_pBitmapBrush
- CD2DBitmapBrush [MFC], m_pBitmapBrushProperties
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
ms.openlocfilehash: 8d0804c094204bc0e8ab420e20c8b6a6a35dc70a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754283"
---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush 클래스

ID2D1비트맵브러시용 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DBitmapBrush : public CD2DBrush;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D비트맵 브러쉬::CD2D비트맵브러쉬](#cd2dbitmapbrush)|오버로드되었습니다. 파일에서 CD2DBitmapBrush 개체를 생성합니다.|
|[CD2D비트맵 브러시::~CD2D비트맵브러쉬](#dtor)|소멸자입니다. D2D 비트맵 브러시 오브젝트가 파괴될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D비트맵 브러시::연결](#attach)|기존 리소스 인터페이스를 개체에 연결합니다.|
|[CD2D비트맵 브러시::만들기](#create)|CD2D비트맵 브러시를 만듭니다. [(CD2DResource::만들기](../../mfc/reference/cd2dresource-class.md#create)재정의.)|
|[CD2D비트맵브러쉬::D에스트로이](#destroy)|CD2DBitmap브러시 오브젝트를 삭제합니다. [(CD2D브러시::D에스트로이](../../mfc/reference/cd2dbrush-class.md#destroy)재사용.|
|[CD2D비트맵브러쉬::D에타치](#detach)|개체에서 리소스 인터페이스 분리|
|[CD2D비트맵 브러시::Get](#get)|ID2D1비트맵 브러시 인터페이스 반환|
|[CD2D비트맵 브러시::겟비트맵](#getbitmap)|이 브러시가 페인트하는 데 사용하는 비트맵 소스를 가져옵니다.|
|[CD2D비트맵 브러시::겟익스텐데모덱스](#getextendmodex)|브러시가 비트맵을 지나 확장되는 영역을 가로로 바게 하는 메서드를 가져옵니다.|
|[CD2D비트맵 브러시::겟익스텐드모드](#getextendmodey)|브러시가 비트맵을 지나 확장되는 영역을 수직으로 바게 하는 메서드를 가져옵니다.|
|[CD2D비트맵 브러시::게인터폴레이션 모드](#getinterpolationmode)|브러시 비트맵의 배율이 조정되거나 회전할 때 사용되는 보간 메서드를 가져옵니다.|
|[CD2D비트맵 브러시::세트비트맵](#setbitmap)|이 브러시가 페인트하는 데 사용하는 비트맵 소스를 지정합니다.|
|[CD2D비트맵 브러시::세트익확장모드X](#setextendmodex)|브러시가 비트맵을 지나 확장되는 영역을 가로로 바함 지정|
|[CD2D비트맵 브러시::세트확장모드](#setextendmodey)|브러시가 비트맵을 지나 확장되는 영역을 수직으로 바함 지정|
|[CD2D비트맵 브러시::세트인터폴레이션 모드](#setinterpolationmode)|브러시 비트맵의 배율이 조정되거나 회전할 때 사용되는 보간 모드를 지정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CD2D비트맵 브러시::커먼이니트](#commoninit)|개체 초기화|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2D비트맵 브러시::연산자 ID2D1비트맵브러시*](#operator_id2d1bitmapbrush_star)|ID2D1비트맵 브러시 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D비트맵 브러시:m_pBitmap](#m_pbitmap)|CD2DBitmap 개체에 대한 포인터를 저장합니다.|
|[CD2D비트맵 브러시::m_pBitmapBrush](#m_pbitmapbrush)|ID2D1BitmapBrush 개체에 대한 포인터를 저장합니다.|
|[CD2D비트맵 브러시::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|비트맵 브러시 속성입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

[CD2D브러시](../../mfc/reference/cd2dbrush-class.md)

`CD2DBitmapBrush`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="dtor"></a>CD2D비트맵 브러시::~CD2D비트맵브러쉬

소멸자입니다. D2D 비트맵 브러시 오브젝트가 파괴될 때 호출됩니다.

```
virtual ~CD2DBitmapBrush();
```

## <a name="cd2dbitmapbrushattach"></a><a name="attach"></a>CD2D비트맵 브러시::연결

기존 리소스 인터페이스를 개체에 연결합니다.

```cpp
void Attach(ID2D1BitmapBrush* pResource);
```

### <a name="parameters"></a>매개 변수

*Presource*<br/>
기존 리소스 인터페이스입니다. NULL일 수 없음

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="cd2dbitmapbrush"></a>CD2D비트맵 브러쉬::CD2D비트맵브러쉬

CD2DBitmap브러시 오브젝트를 생성합니다.

```
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszImagePath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*p비트맵브러쉬프로퍼티*<br/>
비트맵 브러시의 확장 모드 및 보간 모드에 대한 포인터입니다.

*p브러시프로퍼티*<br/>
브러시의 불투명도 및 변환에 대한 포인터입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

*uiResID*<br/>
리소스의 리소스 ID 번호입니다.

*lpszType*<br/>
리소스 형식을 포함하는 null-종단 문자열에 대한 포인터입니다.

*크기 가장*<br/>
비트맵의 대상 크기입니다.

*lpsz이미지패스*<br/>
파일 의 이름을 포함하는 null 종료 된 문자열에 대한 포인터입니다.

## <a name="cd2dbitmapbrushcommoninit"></a><a name="commoninit"></a>CD2D비트맵 브러시::커먼이니트

개체 초기화

```cpp
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```

### <a name="parameters"></a>매개 변수

*p비트맵브러쉬프로퍼티*<br/>
비트맵 브러시 속성에 대한 포인터입니다.

## <a name="cd2dbitmapbrushcreate"></a><a name="create"></a>CD2D비트맵 브러시::만들기

CD2D비트맵 브러시를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
렌더 대상에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dbitmapbrushdestroy"></a><a name="destroy"></a>CD2D비트맵브러쉬::D에스트로이

CD2DBitmap브러시 오브젝트를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dbitmapbrushdetach"></a><a name="detach"></a>CD2D비트맵브러쉬::D에타치

개체에서 리소스 인터페이스 분리

```
ID2D1BitmapBrush* Detach();
```

### <a name="return-value"></a>Return Value

분리된 리소스 인터페이스에 대한 포인터입니다.

## <a name="cd2dbitmapbrushget"></a><a name="get"></a>CD2D비트맵 브러시::Get

ID2D1비트맵 브러시 인터페이스 반환

```
ID2D1BitmapBrush* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1BitmapBrush 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dbitmapbrushgetbitmap"></a><a name="getbitmap"></a>CD2D비트맵 브러시::겟비트맵

이 브러시가 페인트하는 데 사용하는 비트맵 소스를 가져옵니다.

```
CD2DBitmap* GetBitmap();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 CD2DBitmap 개체 또는 NULL에 대한 포인터입니다.

## <a name="cd2dbitmapbrushgetextendmodex"></a><a name="getextendmodex"></a>CD2D비트맵 브러시::겟익스텐데모덱스

브러시가 비트맵을 지나 확장되는 영역을 가로로 바게 하는 메서드를 가져옵니다.

```
D2D1_EXTEND_MODE GetExtendModeX() const;
```

### <a name="return-value"></a>Return Value

브러시가 비트맵을 지나 확장되는 영역을 가로로 바함 하는 방법을 지정하는 값입니다.

## <a name="cd2dbitmapbrushgetextendmodey"></a><a name="getextendmodey"></a>CD2D비트맵 브러시::겟익스텐드모드

브러시가 비트맵을 지나 확장되는 영역을 수직으로 바게 하는 메서드를 가져옵니다.

```
D2D1_EXTEND_MODE GetExtendModeY() const;
```

### <a name="return-value"></a>Return Value

브러시가 비트맵을 지나 확장되는 영역을 수직으로 지정하는 값입니다.

## <a name="cd2dbitmapbrushgetinterpolationmode"></a><a name="getinterpolationmode"></a>CD2D비트맵 브러시::게인터폴레이션 모드

브러시 비트맵의 배율이 조정되거나 회전할 때 사용되는 보간 메서드를 가져옵니다.

```
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;
```

### <a name="return-value"></a>Return Value

브러시 비트맵의 배율이 조정되거나 회전할 때 사용되는 보간 방법

## <a name="cd2dbitmapbrushm_pbitmap"></a><a name="m_pbitmap"></a>CD2D비트맵 브러시:m_pBitmap

CD2DBitmap 개체에 대한 포인터를 저장합니다.

```
CD2DBitmap* m_pBitmap;
```

## <a name="cd2dbitmapbrushm_pbitmapbrush"></a><a name="m_pbitmapbrush"></a>CD2D비트맵 브러시::m_pBitmapBrush

ID2D1BitmapBrush 개체에 대한 포인터를 저장합니다.

```
ID2D1BitmapBrush* m_pBitmapBrush;
```

## <a name="cd2dbitmapbrushm_pbitmapbrushproperties"></a><a name="m_pbitmapbrushproperties"></a>CD2D비트맵 브러시::m_pBitmapBrushProperties

비트맵 브러시 속성입니다.

```
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;
```

## <a name="cd2dbitmapbrushoperator-id2d1bitmapbrush"></a><a name="operator_id2d1bitmapbrush_star"></a>CD2D비트맵 브러시::연산자 ID2D1비트맵브러시*

ID2D1비트맵 브러시 인터페이스 반환

```
operator ID2D1BitmapBrush*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1BitmapBrush 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dbitmapbrushsetbitmap"></a><a name="setbitmap"></a>CD2D비트맵 브러시::세트비트맵

이 브러시가 페인트하는 데 사용하는 비트맵 소스를 지정합니다.

```cpp
void SetBitmap(CD2DBitmap* pBitmap);
```

### <a name="parameters"></a>매개 변수

*pBitmap*<br/>
브러시에서 사용하는 비트맵 소스

## <a name="cd2dbitmapbrushsetextendmodex"></a><a name="setextendmodex"></a>CD2D비트맵 브러시::세트익확장모드X

브러시가 비트맵을 지나 확장되는 영역을 가로로 바함 지정

```cpp
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```

### <a name="parameters"></a>매개 변수

*익스텐드모드X*<br/>
브러시가 비트맵을 지나 확장되는 영역을 가로로 바함 하는 방법을 지정하는 값입니다.

## <a name="cd2dbitmapbrushsetextendmodey"></a><a name="setextendmodey"></a>CD2D비트맵 브러시::세트확장모드

브러시가 비트맵을 지나 확장되는 영역을 수직으로 바함 지정

```cpp
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```

### <a name="parameters"></a>매개 변수

*익스텐드모드*<br/>
브러시가 비트맵을 지나 확장되는 영역을 수직으로 지정하는 값입니다.

## <a name="cd2dbitmapbrushsetinterpolationmode"></a><a name="setinterpolationmode"></a>CD2D비트맵 브러시::세트인터폴레이션 모드

브러시 비트맵의 배율이 조정되거나 회전할 때 사용되는 보간 모드를 지정합니다.

```cpp
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```

### <a name="parameters"></a>매개 변수

*보간 모드*<br/>
브러시 비트맵의 배율이 조정되거나 회전할 때 사용되는 보간 모드

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
