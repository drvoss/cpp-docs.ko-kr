---
title: C팔레트 클래스
ms.date: 11/04/2016
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
ms.openlocfilehash: f5740b3b073c4f564f9cac0fa04e5687ce1d8f00
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753681"
---
# <a name="cpalette-class"></a>C팔레트 클래스

Windows 색상표를 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CPalette : public CGdiObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C팔레트::C팔레트](#cpalette)|연결된 Windows `CPalette` 팔레트가 없는 개체를 생성합니다. 개체를 `CPalette` 사용하려면 먼저 초기화 멤버 함수 중 하나를 사용하여 개체를 초기화해야 합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C팔레트::애니메이트팔레트](#animatepalette)|개체로 식별된 논리 팔레트의 `CPalette` 항목을 바꿉습니다. Windows에서 새 항목을 시스템 팔레트에 즉시 매핑하므로 응용 프로그램을 업데이트할 필요가 없습니다.|
|[C팔레트::하프톤 팔레트 만들기](#createhalftonepalette)|장치 컨텍스트에 대한 하프톤 팔레트를 만들고 개체에 `CPalette` 연결합니다.|
|[C팔레트::만들기팔레트](#createpalette)|Windows 색상 팔레트를 만들고 개체에 `CPalette` 연결합니다.|
|[C팔레트::From핸들](#fromhandle)|Windows 팔레트 개체에 핸들을 `CPalette` 지정하면 개체에 대한 포인터를 반환합니다.|
|[C팔레트::GetEntryCount](#getentrycount)|논리 팔레트에서 팔레트 항목 수를 검색합니다.|
|[C팔레트:::GetNearest팔레트인덱스](#getnearestpaletteindex)|색상 값과 가장 밀접하게 일치하는 논리 팔레트에서 항목의 인덱스를 반환합니다.|
|[C팔레트::겟팔레트항목](#getpaletteentries)|논리 팔레트에서 다양한 팔레트 항목을 검색합니다.|
|[C팔레트::크기 조정팔레트](#resizepalette)|`CPalette` 개체가 지정한 논리 팔레트의 크기를 지정된 항목 수로 변경합니다.|
|[C팔레트::세팔레트항목](#setpaletteentries)|RGB 색상 값및 플래그를 논리 팔레트의 항목 범위에 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C팔레트::연산자 Hpalette](#operator_hpalette)|에 첨부된 HPALETTE를 반환합니다. `CPalette`|

## <a name="remarks"></a>설명

팔레트는 응용 프로그램과 색상 출력 장치(예: 디스플레이 장치) 간의 인터페이스를 제공합니다. 인터페이스를 사용하면 응용 프로그램이 다른 응용 프로그램에서 표시하는 색상을 심각하게 방해하지 않고 출력 장치의 색상 기능을 최대한 활용할 수 있습니다. Windows는 응용 프로그램의 논리 팔레트(필요한 색상 목록)와 시스템 팔레트(사용 가능한 색상을 정의)를 사용하여 사용된 색상을 결정합니다.

개체는 `CPalette` 개체에서 참조하는 팔레트를 조작하기 위한 멤버 함수를 제공합니다. 개체를 `CPalette` 구성하고 해당 멤버 함수를 사용하여 실제 팔레트, GDI(그래픽 장치 인터페이스) 개체를 만들고 해당 항목 및 기타 속성을 조작합니다.

사용에 `CPalette`대한 자세한 내용은 [그래픽 개체](../../mfc/graphic-objects.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cpaletteanimatepalette"></a><a name="animatepalette"></a>C팔레트::애니메이트팔레트

개체에 연결된 논리 팔레트의 항목을 `CPalette` 바꿉습니다.

```cpp
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>매개 변수

*n스타트 인덱스*<br/>
애니메이션할 팔레트의 첫 번째 항목을 지정합니다.

*nNumEntry*<br/>
애니메이션할 팔레트의 항목 수를 지정합니다.

*lp팔레트컬러*<br/>
*nStartIndex* 및 *nNumEntry로*식별된 팔레트 항목을 대체할 [PALETTEENTRY](/previous-versions/dd162769\(v=vs.85\)) 구조 배열의 첫 번째 멤버를 가리킵니다.

### <a name="remarks"></a>설명

응용 프로그램이 `AnimatePalette`호출할 때 Windows에서 새 항목을 시스템 팔레트에 즉시 매핑하므로 클라이언트 영역을 업데이트할 필요가 없습니다.

함수는 `AnimatePalette` `CPalette` 개체에 연결된 [LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette) 구조의 `palPaletteEntry` 해당 멤버에 PC_RESERVED 플래그가 설정된 항목만 변경합니다. 이 구조에 대한 자세한 내용은 Windows SDK의 LOGPALETTE를 참조하십시오.

## <a name="cpalettecpalette"></a><a name="cpalette"></a>C팔레트::C팔레트

`CPalette` 개체를 생성합니다.

```
CPalette();
```

### <a name="remarks"></a>설명

개체를 연결하기 위해 호출할 `CreatePalette` 때까지 개체에 연결된 팔레트가 없습니다.

## <a name="cpalettecreatehalftonepalette"></a><a name="createhalftonepalette"></a>C팔레트::하프톤 팔레트 만들기

장치 컨텍스트에 대한 하프톤 팔레트를 만듭니다.

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
장치 컨텍스트를 식별합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

장치 컨텍스트의 스트레칭 모드가 HALFTONE로 설정된 경우 응용 프로그램은 하프톤 팔레트를 만들어야 합니다. [CreateHalftone팔레트](/windows/win32/api/wingdi/nf-wingdi-createhalftonepalette) 멤버 함수에 의해 반환되는 논리적 하프톤 팔레트는 [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) 또는 [StretchDIBits](/windows/win32/api/wingdi/nf-wingdi-stretchdibits) 함수가 호출되기 전에 장치 컨텍스트에 선택되고 실현되어야 합니다.

에 대한 자세한 내용은 Windows `CreateHalftonePalette` SDK를 `StretchDIBits`참조하십시오.

## <a name="cpalettecreatepalette"></a><a name="createpalette"></a>C팔레트::만들기팔레트

Windows 논리 `CPalette` 색상 팔레트를 만들고 `CPalette` 개체에 연결하여 개체를 초기화합니다.

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>매개 변수

*lpLogPalette*<br/>
논리 팔레트의 색상에 대한 정보가 포함된 [LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

구조에 대한 자세한 내용은 Windows `LOGPALETTE` SDK를 참조하십시오.

## <a name="cpalettefromhandle"></a><a name="fromhandle"></a>C팔레트::From핸들

Windows 팔레트 개체에 핸들을 `CPalette` 지정하면 개체에 대한 포인터를 반환합니다.

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>매개 변수

*hPalette*<br/>
Windows GDI 색상 팔레트의 손잡이입니다.

### <a name="return-value"></a>Return Value

성공한 경우 `CPalette` 개체에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

개체가 `CPalette` Windows 팔레트에 아직 연결되어 있지 않으면 `CPalette` 임시 개체가 만들어지고 첨부됩니다. 이 `CPalette` 임시 개체는 다음에 응용 프로그램이 이벤트 루프에서 유휴 시간을 가지며 모든 임시 그래픽 개체가 삭제될 때까지만 유효합니다. 즉, 임시 개체는 하나의 창 메시지를 처리하는 동안에만 유효합니다.

## <a name="cpalettegetentrycount"></a><a name="getentrycount"></a>C팔레트::GetEntryCount

지정된 논리 팔레트에서 항목 수를 검색하려면 이 멤버 함수를 호출합니다.

```
int GetEntryCount();
```

### <a name="return-value"></a>Return Value

논리 팔레트의 항목 수입니다.

## <a name="cpalettegetnearestpaletteindex"></a><a name="getnearestpaletteindex"></a>C팔레트:::GetNearest팔레트인덱스

지정된 색상 값과 가장 밀접하게 일치하는 논리 팔레트에서 항목의 인덱스를 반환합니다.

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>매개 변수

*crColor*<br/>
일치할 색상을 지정합니다.

### <a name="return-value"></a>Return Value

논리 팔레트에 있는 항목의 인덱스입니다. 항목에는 지정된 색상과 거의 일치하는 색상이 포함되어 있습니다.

## <a name="cpalettegetpaletteentries"></a><a name="getpaletteentries"></a>C팔레트::겟팔레트항목

논리 팔레트에서 다양한 팔레트 항목을 검색합니다.

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>매개 변수

*n스타트 인덱스*<br/>
검색할 논리 팔레트의 첫 번째 항목을 지정합니다.

*nNumEntry*<br/>
검색할 논리 팔레트의 항목 수를 지정합니다.

*lp팔레트컬러*<br/>
팔레트 항목 항목을 수신할 [팔레트 항목](/previous-versions/dd162769\(v=vs.85\)) 데이터 구조의 배열을 가리킵니다. 배열에는 *nNumEntry*. 에 의해 지정된 만큼의 데이터 구조가 포함되어야 합니다.

### <a name="return-value"></a>Return Value

논리 팔레트에서 검색된 항목 수입니다. 함수가 실패한 경우 0입니다.

## <a name="cpaletteoperator-hpalette"></a><a name="operator_hpalette"></a>C팔레트::연산자 Hpalette

이 연산자를 사용하여 개체의 연결된 `CPalette` Windows GDI 핸들을 가져옵니다.

```
operator HPALETTE() const;
```

### <a name="return-value"></a>Return Value

성공하면 개체로 표시되는 Windows GDI 개체에 대한 핸들입니다. `CPalette` 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 연산자는 HPALETTE 개체의 직접 사용을 지원하는 캐스팅 연산자입니다.

그래픽 개체 사용에 대한 자세한 내용은 Windows SDK의 [그래픽 개체](/windows/win32/gdi/graphic-objects) 문서를 참조하십시오.

## <a name="cpaletteresizepalette"></a><a name="resizepalette"></a>C팔레트::크기 조정팔레트

`CPalette` 개체에 연결된 논리 팔레트의 크기를 *nNumEntry에서*지정한 항목 수로 변경합니다.

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>매개 변수

*nNumEntry*<br/>
팔레트의 크기를 조정한 후의 항목 수를 지정합니다.

### <a name="return-value"></a>Return Value

팔레트의 크기가 조정된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

응용 프로그램에서 `ResizePalette` 팔레트 크기를 줄이기 위해 호출하는 경우 크기 조정팔레트에 남아 있는 항목은 변경되지 않습니다. 응용 프로그램에서 `ResizePalette` 팔레트를 확대하도록 호출하면 추가 팔레트 항목이 검은색으로 설정되고(빨간색, 녹색 및 파란색 값은 모두 0) 모든 추가 항목에 대한 플래그가 0으로 설정됩니다.

Windows API에 `ResizePalette`대한 자세한 내용은 Windows SDK의 [크기 조정 팔레트를](/windows/win32/api/wingdi/nf-wingdi-resizepalette) 참조하십시오.

## <a name="cpalettesetpaletteentries"></a><a name="setpaletteentries"></a>C팔레트::세팔레트항목

RGB 색상 값및 플래그를 논리 팔레트의 항목 범위에 설정합니다.

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>매개 변수

*n스타트 인덱스*<br/>
설정할 논리 팔레트의 첫 번째 항목을 지정합니다.

*nNumEntry*<br/>
설정할 논리 팔레트의 항목 수를 지정합니다.

*lp팔레트컬러*<br/>
팔레트 항목 항목을 수신할 [팔레트 항목](/previous-versions/dd162769\(v=vs.85\)) 데이터 구조의 배열을 가리킵니다. 배열에는 *nNumEntry*. 에 의해 지정된 만큼의 데이터 구조가 포함되어야 합니다.

### <a name="return-value"></a>Return Value

논리 팔레트에 설정된 항목 수입니다. 함수가 실패한 경우 0입니다.

### <a name="remarks"></a>설명

응용 프로그램이 호출할 `SetPaletteEntries`때 논리 팔레트를 장치 컨텍스트로 선택하면 응용 프로그램이 [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette)를 호출할 때까지 변경 내용이 적용되지 않습니다.

자세한 내용은 Windows SDK의 [팔레트 항목을](/previous-versions/dd162769\(v=vs.85\)) 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 디브룩](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C팔레트::겟팔레트항목](#getpaletteentries)<br/>
[C팔레트::세팔레트항목](#setpaletteentries)
