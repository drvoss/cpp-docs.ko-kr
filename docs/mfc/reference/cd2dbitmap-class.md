---
title: CD2DBitmap 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::Attach
- AFXRENDERTARGET/CD2DBitmap::CopyFromBitmap
- AFXRENDERTARGET/CD2DBitmap::CopyFromMemory
- AFXRENDERTARGET/CD2DBitmap::CopyFromRenderTarget
- AFXRENDERTARGET/CD2DBitmap::Create
- AFXRENDERTARGET/CD2DBitmap::Destroy
- AFXRENDERTARGET/CD2DBitmap::Detach
- AFXRENDERTARGET/CD2DBitmap::Get
- AFXRENDERTARGET/CD2DBitmap::GetDPI
- AFXRENDERTARGET/CD2DBitmap::GetPixelFormat
- AFXRENDERTARGET/CD2DBitmap::GetPixelSize
- AFXRENDERTARGET/CD2DBitmap::GetSize
- AFXRENDERTARGET/CD2DBitmap::IsValid
- AFXRENDERTARGET/CD2DBitmap::CommonInit
- AFXRENDERTARGET/CD2DBitmap::m_bAutoDestroyHBMP
- AFXRENDERTARGET/CD2DBitmap::m_hBmpSrc
- AFXRENDERTARGET/CD2DBitmap::m_lpszType
- AFXRENDERTARGET/CD2DBitmap::m_pBitmap
- AFXRENDERTARGET/CD2DBitmap::m_sizeDest
- AFXRENDERTARGET/CD2DBitmap::m_strPath
- AFXRENDERTARGET/CD2DBitmap::m_uiResID
helpviewer_keywords:
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], Attach
- CD2DBitmap [MFC], CopyFromBitmap
- CD2DBitmap [MFC], CopyFromMemory
- CD2DBitmap [MFC], CopyFromRenderTarget
- CD2DBitmap [MFC], Create
- CD2DBitmap [MFC], Destroy
- CD2DBitmap [MFC], Detach
- CD2DBitmap [MFC], Get
- CD2DBitmap [MFC], GetDPI
- CD2DBitmap [MFC], GetPixelFormat
- CD2DBitmap [MFC], GetPixelSize
- CD2DBitmap [MFC], GetSize
- CD2DBitmap [MFC], IsValid
- CD2DBitmap [MFC], CommonInit
- CD2DBitmap [MFC], m_bAutoDestroyHBMP
- CD2DBitmap [MFC], m_hBmpSrc
- CD2DBitmap [MFC], m_lpszType
- CD2DBitmap [MFC], m_pBitmap
- CD2DBitmap [MFC], m_sizeDest
- CD2DBitmap [MFC], m_strPath
- CD2DBitmap [MFC], m_uiResID
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
ms.openlocfilehash: a3cabb00ded7dbc5f9c396a1de767058443a4436
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754213"
---
# <a name="cd2dbitmap-class"></a>CD2DBitmap 클래스

ID2D1비트맵용 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DBitmap : public CD2DResource;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D비트맵::CD2D비트맵](#cd2dbitmap)|오버로드되었습니다. HBITMAP에서 CD2DBitmap 개체를 생성합니다.|
|[CD2D비트맵::~CD2D비트맵](#_dtorcd2dbitmap)|소멸자입니다. D2D 비트맵 개체가 파괴될 때 호출됩니다.|

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CD2D비트맵::CD2D비트맵](#cd2dbitmap)|오버로드되었습니다. CD2DBitmap 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D비트맵::연결](#attach)|기존 리소스 인터페이스를 개체에 연결합니다.|
|[CD2D비트맵::카피From비트맵](#copyfrombitmap)|지정된 비트맵에서 현재 비트맵으로 지정된 영역복사|
|[CD2D비트맵::카피From메모리](#copyfrommemory)|메모리에서 지정된 영역을 현재 비트맵으로 복사합니다.|
|[CD2D비트맵::카피From렌더대상](#copyfromrendertarget)|지정된 렌더링 대상에서 현재 비트맵으로 지정된 영역복사|
|[CD2D비트맵::만들기](#create)|CD2D비트맵을 만듭니다. [(CD2DResource::만들기](../../mfc/reference/cd2dresource-class.md#create)재정의.)|
|[CD2D비트맵::D에스트로이](#destroy)|CD2DBitmap 개체를 삭제합니다. [(CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy)재정의.)|
|[CD2D비트맵::D에타치](#detach)|개체에서 리소스 인터페이스 분리|
|[CD2D비트맵::Get](#get)|ID2D1비트맵 인터페이스 반환|
|[CD2D비트맵::GetDPI](#getdpi)|비트맵의 인치당 점 반환(DPI)|
|[CD2D비트맵::겟픽셀포맷](#getpixelformat)|비트맵의 픽셀 형식 및 알파 모드를 검색합니다.|
|[CD2D비트맵::겟픽셀사이즈](#getpixelsize)|비트맵의 장치 종속 단위(픽셀)에서 크기를 반환합니다.|
|[CD2D비트맵::겟사이즈](#getsize)|비트맵의 장치 독립 픽셀(DIP)에서 크기를 반환합니다.|
|[CD2D비트맵::유효하지 않음](#isvalid)|리소스 유효성 [검사(CD2DResource 재정의::유효합니다.)](../../mfc/reference/cd2dresource-class.md#isvalid)|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CD2D비트맵::커먼이니트](#commoninit)|개체 초기화|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2D비트맵::연산자 ID2D1비트맵*](#operator_id2d1bitmap_star)|ID2D1비트맵 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D비트맵:m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|m_hBmpSrc 파괴해야하는 경우 TRUE; 그렇지 않으면 거짓.|
|[CD2D비트맵:m_hBmpSrc](#m_hbmpsrc)|소스 비트맵 핸들입니다.|
|[CD2D비트맵:m_lpszType](#m_lpsztype)|리소스 유형입니다.|
|[CD2D비트맵:m_pBitmap](#m_pbitmap)|ID2D1Bitmap 개체에 대한 포인터를 저장합니다.|
|[CD2D비트맵:m_sizeDest](#m_sizedest)|비트맵 대상 크기입니다.|
|[CD2D비트맵:m_strPath](#m_strpath)|봇맵 파일 경로입니다.|
|[CD2D비트맵:m_uiResID](#m_uiresid)|비트맵 리소스 ID.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

`CD2DBitmap`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dbitmapcd2dbitmap"></a><a name="_dtorcd2dbitmap"></a>CD2D비트맵::~CD2D비트맵

소멸자입니다. D2D 비트맵 개체가 파괴될 때 호출됩니다.

```
virtual ~CD2DBitmap();
```

## <a name="cd2dbitmapattach"></a><a name="attach"></a>CD2D비트맵::연결

기존 리소스 인터페이스를 개체에 연결합니다.

```cpp
void Attach(ID2D1Bitmap* pResource);
```

### <a name="parameters"></a>매개 변수

*Presource*<br/>
기존 리소스 인터페이스입니다. NULL이 될 수 없습니다.

## <a name="cd2dbitmapcd2dbitmap"></a><a name="cd2dbitmap"></a>CD2D비트맵::CD2D비트맵

리소스에서 CD2DBitmap 개체를 생성합니다.

```
CD2DBitmap(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszPath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    HBITMAP hbmpSrc,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*uiResID*<br/>
리소스의 리소스 ID 번호입니다.

*lpszType*<br/>
리소스 형식을 포함하는 null-종단 문자열에 대한 포인터입니다.

*크기 가장*<br/>
비트맵의 대상 크기입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

*lpszPath*<br/>
파일 의 이름을 포함하는 null 종료 된 문자열에 대한 포인터입니다.

*hbmpSrc*<br/>
비트맵을 처리합니다.

## <a name="cd2dbitmapcommoninit"></a><a name="commoninit"></a>CD2D비트맵::커먼이니트

개체를 초기화합니다.

```cpp
void CommonInit();
```

## <a name="cd2dbitmapcopyfrombitmap"></a><a name="copyfrombitmap"></a>CD2D비트맵::카피From비트맵

지정된 비트맵에서 지정된 영역을 현재 비트맵으로 복사합니다.

```
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>매개 변수

*pBitmap*<br/>
복사할 비트맵입니다.

*데스트 포인트*<br/>
현재 비트맵에서 srcRect가 지정한 영역이 복사되는 영역의 왼쪽 위 모서리입니다.

*srcRect*<br/>
복사할 비트맵 영역입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dbitmapcopyfrommemory"></a><a name="copyfrommemory"></a>CD2D비트맵::카피From메모리

메모리에서 지정된 영역을 현재 비트맵으로 복사합니다.

```
HRESULT CopyFromMemory(
    const void* srcData,
    UINT32 pitch,
    const CD2DRectU* destRect = NULL);
```

### <a name="parameters"></a>매개 변수

*srcData*<br/>
복사할 데이터입니다.

*피치*<br/>
srcData에 저장된 소스 비트맵의 보폭 또는 피치입니다. 보폭은 스캔라인의 바이트 수입니다(메모리의 한 행 픽셀). 보폭은 다음 수식에서 계산할 \* 수 있습니다: 픽셀당 픽셀 너비 바이트 + 메모리 패딩.

*데스트렉트*<br/>
현재 비트맵에서 srcRect가 지정한 영역이 복사되는 영역의 왼쪽 위 모서리입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dbitmapcopyfromrendertarget"></a><a name="copyfromrendertarget"></a>CD2D비트맵::카피From렌더대상

지정된 렌더링 대상에서 현재 비트맵으로 지정된 영역을 복사합니다.

```
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
복사할 영역이 포함된 렌더 대상입니다.

*데스트 포인트*<br/>
현재 비트맵에서 srcRect가 지정한 영역이 복사되는 영역의 왼쪽 위 모서리입니다.

*srcRect*<br/>
복사할 renderTarget의 영역입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dbitmapcreate"></a><a name="create"></a>CD2D비트맵::만들기

CD2D비트맵을 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*p렌더대상*<br/>
렌더 대상에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dbitmapdestroy"></a><a name="destroy"></a>CD2D비트맵::D에스트로이

CD2DBitmap 개체를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dbitmapdetach"></a><a name="detach"></a>CD2D비트맵::D에타치

개체에서 리소스 인터페이스를 분리합니다.

```
ID2D1Bitmap* Detach();
```

### <a name="return-value"></a>Return Value

분리된 리소스 인터페이스에 대한 포인터입니다.

## <a name="cd2dbitmapget"></a><a name="get"></a>CD2D비트맵::Get

ID2D1비트맵 인터페이스를 반환합니다.

```
ID2D1Bitmap* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1Bitmap 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dbitmapgetdpi"></a><a name="getdpi"></a>CD2D비트맵::GetDPI

비트맵의 인치당 점(DPI)을 반환합니다.

```
CD2DSizeF GetDPI() const;
```

### <a name="return-value"></a>Return Value

비트맵의 수평 및 세로 DPI입니다.

## <a name="cd2dbitmapgetpixelformat"></a><a name="getpixelformat"></a>CD2D비트맵::겟픽셀포맷

비트맵의 픽셀 형식 및 알파 모드를 검색합니다.

```
D2D1_PIXEL_FORMAT GetPixelFormat() const;
```

### <a name="return-value"></a>Return Value

비트맵의 픽셀 형식 및 알파 모드입니다.

## <a name="cd2dbitmapgetpixelsize"></a><a name="getpixelsize"></a>CD2D비트맵::겟픽셀사이즈

비트맵의 장치 종속 단위(픽셀)에서 크기를 반환합니다.

```
CD2DSizeU GetPixelSize() const;
```

### <a name="return-value"></a>Return Value

비트맵의 크기(픽셀 단위)입니다.

## <a name="cd2dbitmapgetsize"></a><a name="getsize"></a>CD2D비트맵::겟사이즈

비트맵의 장치 독립 픽셀(DIP)에서 크기를 반환합니다.

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Return Value

비트맵의 크기(DIP)입니다.

## <a name="cd2dbitmapisvalid"></a><a name="isvalid"></a>CD2D비트맵::유효하지 않음

리소스 유효성을 확인합니다.

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Return Value

TRUE 리소스가 유효한 경우; 그렇지 않으면 거짓.

## <a name="cd2dbitmapm_bautodestroyhbmp"></a><a name="m_bautodestroyhbmp"></a>CD2D비트맵:m_bAutoDestroyHBMP

m_hBmpSrc 파괴해야하는 경우 TRUE; 그렇지 않으면 거짓.

```
BOOL m_bAutoDestroyHBMP;
```

## <a name="cd2dbitmapm_hbmpsrc"></a><a name="m_hbmpsrc"></a>CD2D비트맵:m_hBmpSrc

소스 비트맵 핸들입니다.

```
HBITMAP m_hBmpSrc;
```

## <a name="cd2dbitmapm_lpsztype"></a><a name="m_lpsztype"></a>CD2D비트맵:m_lpszType

리소스 유형입니다.

```
LPCTSTR m_lpszType;
```

## <a name="cd2dbitmapm_pbitmap"></a><a name="m_pbitmap"></a>CD2D비트맵:m_pBitmap

ID2D1Bitmap 개체에 대한 포인터를 저장합니다.

```
ID2D1Bitmap* m_pBitmap;
```

## <a name="cd2dbitmapm_sizedest"></a><a name="m_sizedest"></a>CD2D비트맵:m_sizeDest

비트맵 대상 크기입니다.

```
CD2DSizeU m_sizeDest;
```

## <a name="cd2dbitmapm_strpath"></a><a name="m_strpath"></a>CD2D비트맵:m_strPath

봇맵 파일 경로입니다.

```
CString m_strPath;
```

## <a name="cd2dbitmapm_uiresid"></a><a name="m_uiresid"></a>CD2D비트맵:m_uiResID

비트맵 리소스 ID.

```
UINT m_uiResID;
```

## <a name="cd2dbitmapoperator-id2d1bitmap"></a><a name="operator_id2d1bitmap_star"></a>CD2D비트맵::연산자 ID2D1비트맵*

ID2D1비트맵 인터페이스 반환

```
operator ID2D1Bitmap*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 ID2D1Bitmap 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
