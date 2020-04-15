---
title: C비트맵 클래스
ms.date: 11/04/2016
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
helpviewer_keywords:
- CBitmap [MFC], CBitmap
- CBitmap [MFC], CreateBitmap
- CBitmap [MFC], CreateBitmapIndirect
- CBitmap [MFC], CreateCompatibleBitmap
- CBitmap [MFC], CreateDiscardableBitmap
- CBitmap [MFC], FromHandle
- CBitmap [MFC], GetBitmap
- CBitmap [MFC], GetBitmapBits
- CBitmap [MFC], GetBitmapDimension
- CBitmap [MFC], LoadBitmap
- CBitmap [MFC], LoadMappedBitmap
- CBitmap [MFC], LoadOEMBitmap
- CBitmap [MFC], SetBitmapBits
- CBitmap [MFC], SetBitmapDimension
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
ms.openlocfilehash: 9a33a6e1bea601422e043d7f2a80029c72d97e50
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352738"
---
# <a name="cbitmap-class"></a>C비트맵 클래스

Windows GDI(그래픽 디바이스 인터페이스) 비트맵을 캡슐화하고 비트맵을 조작하는 멤버 함수를 제공합니다.

## <a name="syntax"></a>구문

```
class CBitmap : public CGdiObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C비트맵:::C비트맵](#cbitmap)|`CBitmap` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C비트맵::비트맵 만들기](#createbitmap)|지정된 너비, 높이 및 비트 패턴이 있는 장치 종속 메모리 비트맵으로 개체를 초기화합니다.|
|[C비트맵::만들기비트맵간접](#createbitmapindirect)|구조체에 지정된 너비, 높이 및 비트 패턴(지정된 경우)을 사용하여 오브젝트를 `BITMAP` 초기화합니다.|
|[C비트맵::호환비트맵 만들기](#createcompatiblebitmap)|지정된 장치와 호환되도록 개체를 비트맵으로 초기화합니다.|
|[C비트맵::폐기 가능 비트맵 만들기](#creatediscardablebitmap)|지정된 장치와 호환되는 삭제 가능한 비트맵으로 개체를 초기화합니다.|
|[C비트맵::From핸들](#fromhandle)|Windows `HBITMAP` 비트맵에 `CBitmap` 핸들이 지정되면 개체에 대한 포인터를 반환합니다.|
|[C비트맵::GetBitmap](#getbitmap)|비트맵에 `BITMAP` 대한 정보로 구조를 채웁니다.|
|[C비트맵::겟비트맵비트](#getbitmapbits)|지정된 비트맵의 비트를 지정된 버퍼에 복사합니다.|
|[C비트맵::겟비트맵차원](#getbitmapdimension)|비트맵의 너비와 높이를 반환합니다. 높이와 너비는 [SetBitmapDimension](#setbitmapdimension) 멤버 함수에 의해 이전에 설정된 것으로 가정합니다.|
|[C비트맵::로드비트맵](#loadbitmap)|응용 프로그램의 실행 파일에서 명명된 비트맵 리소스를 로드하고 개체에 비트맵을 연결하여 개체를 초기화합니다.|
|[C비트맵::로드맵비트맵](#loadmappedbitmap)|비트맵을 로드하고 현재 시스템 색상에 색상을 매핑합니다.|
|[비트맵::로드OEM비트맵](#loadoembitmap)|미리 정의된 Windows 비트맵을 로드하고 개체에 비트맵을 연결하여 개체를 초기화합니다.|
|[C비트맵::세트비트맵비트](#setbitmapbits)|비트맵의 비트를 지정된 비트 값으로 설정합니다.|
|[C비트맵::세트비트맵차원](#setbitmapdimension)|0.1mm 단위로 비트맵에 너비와 높이를 할당합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C비트맵::연산자 HBITMAP](#operator_hbitmap)|개체에 연결된 Windows `CBitmap` 핸들을 반환합니다.|

## <a name="remarks"></a>설명

개체를 `CBitmap` 사용하여 개체를 생성하고 초기화 멤버 함수 중 하나를 사용하여 비트맵 핸들을 연결한 다음 개체의 멤버 함수를 호출합니다.

다음과 같은 `CBitmap`그래픽 개체 사용에 대한 자세한 내용은 [그래픽 개체](../../mfc/graphic-objects.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBitmap`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cbitmapcbitmap"></a><a name="cbitmap"></a>C비트맵:::C비트맵

`CBitmap` 개체를 생성합니다.

```
CBitmap();
```

### <a name="remarks"></a>설명

결과 개체는 초기화 멤버 함수 중 하나를 통해 초기화되어야 합니다.

## <a name="cbitmapcreatebitmap"></a><a name="createbitmap"></a>C비트맵::비트맵 만들기

너비, 높이 및 비트 패턴이 지정되어 있는 디바이스 종속적 메모리 비트맵을 초기화합니다.

```
BOOL CreateBitmap(
    int nWidth,
    int nHeight,
    UINT nPlanes,
    UINT nBitcount,
    const void* lpBits);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
비트맵의 너비(픽셀)를 지정합니다.

*nHeight*<br/>
비트맵의 높이(픽셀)를 지정합니다.

*n비행기*<br/>
비트맵에서 색 평면의 수를 지정합니다.

*n비트 카운트*<br/>
표시 픽셀당 색 비트의 수를 지정합니다.

*lpBits*<br/>
초기 비트맵 비트 값이 포함된 바이트 배열을 가리킵니다. NULL이면 새 비트맵이 초기화되어 있지 않습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

색상 비트맵의 경우 *nPlanes* 또는 *nBitcount* 매개 변수를 1로 설정해야 합니다. 이러한 매개 변수가 둘 다 1로 설정되면 `CreateBitmap` 은 단색 비트맵을 만듭니다.

디스플레이 디바이스에 대한 비트맵을 직접 선택할 수는 없지만 [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) 를 사용하여 “메모리 디바이스 컨텍스트"에 대한 현재 비트맵을 선택하고 [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) 함수를 사용하여 호환되는 디바이스 컨텍스트에 복사할 수 있습니다.

`CBitmap` 함수에서 만들어진 `CreateBitmap` 개체 사용을 완료하면 먼저 디바이스 컨텍스트에서 비트맵을 선택하고 나서 `CBitmap` 개체를 삭제합니다.

자세한 내용은 `bmBits` `BITMAP` 구조의 필드 설명을 참조하십시오. [BITMAP](/windows/win32/api/wingdi/ns-wingdi-bitmap) 구조체는 [CBitmap::CreateBitmapIndirect](#createbitmapindirect) 멤버 함수에서 설명합니다.

## <a name="cbitmapcreatebitmapindirect"></a><a name="createbitmapindirect"></a>C비트맵::만들기비트맵간접

lpBitmap으로 가리키는 구조에 주어진 너비, 높이 및 비트 패턴(지정된 경우)이 있는 *비트맵을*초기화합니다.

```
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```

### <a name="parameters"></a>매개 변수

*lpBitmap*<br/>
[비트맵에](/windows/win32/api/wingdi/ns-wingdi-bitmap) 대한 정보가 포함된 BITMAP 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

표시 장치에 대해 비트맵을 직접 선택할 수는 없지만 [CDC::SelectObject를](../../mfc/reference/cdc-class.md#selectobject) 사용하여 메모리 장치 컨텍스트의 현재 비트맵으로 선택하고 [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) 또는 [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) 기능을 사용하여 호환되는 장치 컨텍스트에 복사할 수 있습니다. [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) 함수는 현재 브러시의 비트맵을 디스플레이 장치 컨텍스트에 직접 복사할 수 있습니다.)

*lpBitmap* 매개 변수가 `GetObject` `BITMAP` 함수를 사용하여 채워진 구조가 있으면 비트맵의 비트가 지정되지 않고 비트맵이 초기화되지 않습니다. 비트맵을 초기화하기 위해 응용 프로그램은 [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) 또는 [SetDIBits와](/windows/win32/api/wingdi/nf-wingdi-setdibits) 같은 함수를 사용하여 `CGdiObject::GetObject` `CreateBitmapIndirect`에서 만든 비트맵의 첫 번째 매개 변수로 식별된 비트맵에서 비트를 복사할 수 있습니다.

함수로 만든 `CBitmap` 개체로 `CreateBitmapIndirect` 완료하면 먼저 장치 컨텍스트에서 비트맵을 선택한 `CBitmap` 다음 개체를 삭제합니다.

## <a name="cbitmapcreatecompatiblebitmap"></a><a name="createcompatiblebitmap"></a>C비트맵::호환비트맵 만들기

*pDC에서*지정한 장치와 호환되는 비트맵을 초기화합니다.

```
BOOL CreateCompatibleBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
장치 컨텍스트를 지정합니다.

*nWidth*<br/>
비트맵의 너비(픽셀)를 지정합니다.

*nHeight*<br/>
비트맵의 높이(픽셀)를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

비트맵은 색상 평면 수가 같거나 픽셀당 비트 형식이 지정된 장치 컨텍스트와 동일합니다. *pDC에서*지정한 메모리 장치와 호환되는 모든 메모리 장치에 대한 현재 비트맵으로 선택할 수 있습니다.

*pDC가* 메모리 장치 컨텍스트인 경우 반환된 비트맵의 형식은 해당 장치 컨텍스트에서 현재 선택된 비트맵과 동일합니다. "메모리 장치 컨텍스트"는 디스플레이 표면을 나타내는 메모리 블록입니다. 호환되는 장치의 실제 디스플레이 표면에 이미지를 복사하기 전에 메모리에 이미지를 준비하는 데 사용할 수 있습니다.

메모리 장치 컨텍스트가 만들어지면 GDI는 자동으로 흑백 스톡 비트맵을 선택합니다.

색상 메모리 장치 컨텍스트에 색상 또는 흑백 비트맵이 선택되어 있을 수 `CreateCompatibleBitmap` 있기 때문에 함수에서 반환되는 비트맵 형식이 항상 동일하지는 않습니다. 그러나 비메모리 장치 컨텍스트에 대한 호환되는 비트맵 형식은 항상 장치의 형식입니다.

함수로 만든 `CBitmap` 개체로 완료하면 먼저 장치 컨텍스트에서 비트맵을 선택한 다음 개체를 삭제합니다. `CBitmap` `CreateCompatibleBitmap`

## <a name="cbitmapcreatediscardablebitmap"></a><a name="creatediscardablebitmap"></a>C비트맵::폐기 가능 비트맵 만들기

*pDC로*식별된 장치 컨텍스트와 호환되는 삭제 가능한 비트맵을 초기화합니다.

```
BOOL CreateDiscardableBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
장치 컨텍스트를 지정합니다.

*nWidth*<br/>
비트맵의 너비(비트)를 지정합니다.

*nHeight*<br/>
비트맵의 높이(비트)를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

비트맵은 색상 평면 수가 같거나 픽셀당 비트 형식이 지정된 장치 컨텍스트와 동일합니다. 응용 프로그램은 이 비트맵을 *pDC에서*지정한 비트맵과 호환되는 메모리 장치의 현재 비트맵으로 선택할 수 있습니다.

Windows는 응용 프로그램이 디스플레이 컨텍스트로 선택하지 않은 경우에만 이 함수에서 만든 비트맵을 삭제할 수 있습니다. Windows가 선택되지 않은 경우 비트맵을 삭제하고 나중에 응용 프로그램이 비트맵을 선택하려고 하면 [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) 함수가 NULL을 반환합니다.

함수로 만든 `CBitmap` 개체로 완료하면 먼저 장치 컨텍스트에서 비트맵을 선택한 다음 개체를 삭제합니다. `CBitmap` `CreateDiscardableBitmap`

## <a name="cbitmapfromhandle"></a><a name="fromhandle"></a>C비트맵::From핸들

Windows GDI `CBitmap` 비트맵에 핸들이 지정되면 개체에 대한 포인터를 반환합니다.

```
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```

### <a name="parameters"></a>매개 변수

*hBitmap*<br/>
Windows GDI 비트맵을 지정합니다.

### <a name="return-value"></a>Return Value

성공한 경우 `CBitmap` 개체에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

개체가 `CBitmap` 핸들에 아직 연결되어 있지 않으면 `CBitmap` 임시 개체가 만들어지고 첨부됩니다. 이 `CBitmap` 임시 개체는 다음에 응용 프로그램이 이벤트 루프에서 유휴 시간을 가지며 모든 임시 그래픽 개체가 삭제될 때까지만 유효합니다. 이 것을 말하는 또 다른 방법은 임시 개체가 하나의 창 메시지를 처리하는 동안에만 유효하다는 것입니다.

## <a name="cbitmapgetbitmap"></a><a name="getbitmap"></a>C비트맵::GetBitmap

연결된 비트맵에 대한 이미지 속성을 검색합니다.

```
int GetBitmap(BITMAP* pBitMap);
```

### <a name="parameters"></a>매개 변수

*비트맵*<br/>
이미지 속성을 수신하는 [BITMAP](/windows/win32/api/wingdi/ns-wingdi-bitmap) 구조에 대한 포인터입니다. 이 매개 변수는 NULL이 아니어야 합니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

## <a name="cbitmapgetbitmapbits"></a><a name="getbitmapbits"></a>C비트맵::겟비트맵비트

연결된 비트맵의 비트 패턴을 지정된 버퍼에 복사합니다.

```
DWORD GetBitmapBits(
    DWORD dwCount,
    LPVOID lpBits) const;
```

### <a name="parameters"></a>매개 변수

*dwCount*<br/>
버퍼에 복사할 바이트 수입니다.

*lpBits*<br/>
비트맵을 수신할 버퍼에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 버퍼에 복사된 바이트 수입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

[CBitmap::GetBitmap을](#getbitmap) 사용하여 필요한 버퍼 크기를 결정합니다.

## <a name="cbitmapgetbitmapdimension"></a><a name="getbitmapdimension"></a>C비트맵::겟비트맵차원

비트맵의 너비와 높이를 반환합니다.

```
CSize GetBitmapDimension() const;
```

### <a name="return-value"></a>Return Value

0.1mm 단위로 측정된 비트맵의 너비와 높이입니다. 높이는 `cy` `CSize` 개체의 멤버에 있고 너비는 멤버에 `cx` 있습니다. 를 사용하여 `SetBitmapDimension`비트맵 너비와 높이를 설정하지 않은 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

높이와 너비는 [SetBitmapDimension](#setbitmapdimension) 멤버 함수를 사용하여 이전에 설정된 것으로 가정합니다.

## <a name="cbitmaploadbitmap"></a><a name="loadbitmap"></a>C비트맵::로드비트맵

*lpszResourceName또는* 응용 프로그램의 실행 파일에서 *nIDResource의* ID 번호로 식별된 비트맵 리소스를 로드합니다.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
비트맵 리소스의 이름을 포함하는 null 종료 된 문자열을 가리킵니다.

*nIDResource*<br/>
비트맵 리소스의 리소스 ID 번호를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

로드된 비트맵이 개체에 `CBitmap` 연결됩니다.

*lpszResourceName로* 식별된 비트맵이 존재하지 않거나 비트맵을 로드할 메모리가 부족한 경우 함수는 0을 반환합니다.

[CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) 함수를 사용하여 함수에 로드된 `LoadBitmap` 비트맵을 `CBitmap` 삭제하거나 소멸자가 객체를 삭제합니다.

> [!CAUTION]
> 객체를 삭제하기 전에 객체가 장치 컨텍스트로 선택되지 않았는지 확인합니다.

다음 비트맵은 Windows 버전 3.1 이상에 추가되었습니다.

OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI

이러한 비트맵은 Windows 버전 3.0 이상용 장치 드라이버에서 찾을 수 없습니다. 비트맵의 전체 목록과 모양 표시는 Windows SDK를 참조하십시오.

## <a name="cbitmaploadmappedbitmap"></a><a name="loadmappedbitmap"></a>C비트맵::로드맵비트맵

이 멤버 함수를 호출하여 비트맵을 로드하고 색상을 현재 시스템 색상에 매핑합니다.

```
BOOL LoadMappedBitmap(
    UINT nIDBitmap,
    UINT nFlags = 0,
    LPCOLORMAP lpColorMap = NULL,
    int nMapSize = 0);
```

### <a name="parameters"></a>매개 변수

*니드비트맵*<br/>
비트맵 리소스의 ID입니다.

*nFlags*<br/>
비트맵의 플래그입니다. 0 또는 CMB_MASKED 될 수 있습니다.

*lpColorMap*<br/>
비트맵을 `COLORMAP` 매핑하는 데 필요한 색상 정보가 포함된 구조체에 대한 포인터입니다. 이 매개 변수가 NULL이면 함수는 기본 색상 맵을 사용합니다.

*n맵 사이즈*<br/>
*lpColorMap에*의해 가리키는 색상 맵의 수입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본적으로 `LoadMappedBitmap` 단추 문말에서 일반적으로 사용되는 색상을 매핑합니다.

매핑된 비트맵 을 만드는 자세한 내용은 Windows 함수 [CreateMappedBitmap](https://go.microsoft.com/fwlink/p/?linkid=230562) 및 Windows SDK의 [COLORMAP](/windows/win32/api/commctrl/ns-commctrl-colormap) 구조를 참조하십시오.

## <a name="cbitmaploadoembitmap"></a><a name="loadoembitmap"></a>비트맵::로드OEM비트맵

Windows에서 사용하는 미리 정의된 비트맵을 로드합니다.

```
BOOL LoadOEMBitmap(UINT nIDBitmap);
```

### <a name="parameters"></a>매개 변수

*니드비트맵*<br/>
미리 정의된 Windows 비트맵의 ID 번호입니다. 가능한 값은 WINDOWS에서 아래에 나열됩니다. H:

|||
|-|-|
|OBM_BTNCORNERS|OBM_OLD_RESTORE|
|OBM_BTSIZE|OBM_OLD_RGARROW|
|OBM_CHECK|OBM_OLD_UPARROW|
|OBM_CHECKBOXES|OBM_OLD_ZOOM|
|OBM_CLOSE|OBM_REDUCE|
|OBM_COMBO|OBM_REDUCED|
|OBM_DNARROW|OBM_RESTORE|
|OBM_DNARROWD|OBM_RESTORED|
|OBM_DNARROWI|OBM_RGARROW|
|OBM_LFARROW|OBM_RGARROWD|
|OBM_LFARROWD|OBM_RGARROWI|
|OBM_LFARROWI|OBM_SIZE|
|OBM_MNARROW|OBM_UPARROW|
|OBM_OLD_CLOSE|OBM_UPARROWD|
|OBM_OLD_DNARROW|OBM_UPARROW|
|OBM_OLD_LFARROW|OBM_ZOOM|
|OBM_OLD_REDUCE|OBM_ZOOMD|

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

OBM_OLD 시작하는 비트맵 이름은 3.0 이전에 Windows 버전에서 사용하는 비트맵을 나타냅니다.

WINDOWS를 포함하기 전에 상수 OEMRESOURCE를 정의해야 합니다. **OBM_** 상수 중 어느 것을 사용하기 위해 H.

## <a name="cbitmapoperator-hbitmap"></a><a name="operator_hbitmap"></a>C비트맵::연산자 HBITMAP

이 연산자를 사용하여 개체의 연결된 `CBitmap` Windows GDI 핸들을 가져옵니다.

```
operator HBITMAP() const;
```

### <a name="return-value"></a>Return Value

성공하면 개체로 표시되는 Windows GDI 개체에 대한 핸들입니다. `CBitmap` 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 연산자는 개체의 직접 사용을 `HBITMAP` 지원하는 캐스팅 연산자입니다.

그래픽 개체 사용에 대한 자세한 내용은 Windows SDK의 [그래픽 개체를](/windows/win32/gdi/graphic-objects) 참조하십시오.

## <a name="cbitmapsetbitmapbits"></a><a name="setbitmapbits"></a>C비트맵::세트비트맵비트

비트맵의 비트를 *lpBits에서*제공하는 비트 값으로 설정합니다.

```
DWORD SetBitmapBits(
    DWORD dwCount,
    const void* lpBits);
```

### <a name="parameters"></a>매개 변수

*dwCount*<br/>
*lpBits로*가리키는 바이트 수를 지정합니다.

*lpBits*<br/>
개체에 복사할 픽셀 값이 포함된 BYTE 배열을 `CBitmap` 가리킵니다. 비트맵이 이미지를 올바르게 렌더링하려면 CBitmap 인스턴스를 만들 때 지정한 높이, 너비 및 색상 깊이 값을 준수하도록 값을 서식을 지정해야 합니다. 자세한 내용은 [CBitmap::CreateBitmap](#createbitmap)을 참조하십시오.

### <a name="return-value"></a>Return Value

비트맵 비트를 설정하는 데 사용되는 바이트 수입니다. 함수가 실패하면 0입니다.

## <a name="cbitmapsetbitmapdimension"></a><a name="setbitmapdimension"></a>C비트맵::세트비트맵차원

0.1mm 단위로 비트맵에 너비와 높이를 할당합니다.

```
CSize SetBitmapDimension(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
비트맵의 너비를 지정합니다(0.1mm 단위).

*nHeight*<br/>
비트맵의 높이를 지정합니다(0.1mm 단위).

### <a name="return-value"></a>Return Value

이전 비트맵 차원입니다. 높이는 `cy` `CSize` 개체의 멤버 변수에 있고 너비는 `cx` 멤버 변수에 있습니다.

### <a name="remarks"></a>설명

GDI는 응용 프로그램이 [GetBitmapDimension](#getbitmapdimension) 멤버 함수를 호출할 때 반환하는 것을 제외하고는 이러한 값을 사용하지 않습니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
