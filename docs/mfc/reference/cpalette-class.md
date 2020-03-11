---
title: CPalette 클래스
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
ms.openlocfilehash: 27f4f14c9e93091728e256c890dcffee26a43de4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855536"
---
# <a name="cpalette-class"></a>CPalette 클래스

Windows 색상표를 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CPalette : public CGdiObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[CPalette:: CPalette](#cpalette)|연결 된 Windows 색상표를 사용 하 여 `CPalette` 개체를 생성 합니다. 초기화 멤버 함수 중 하나를 사용 하 여 `CPalette` 개체를 초기화 한 후에 야 사용할 수 있습니다.|

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[CPalette:: AnimatePalette](#animatepalette)|`CPalette` 개체로 식별 되는 논리 색상표의 항목을 바꿉니다. Windows는 새 항목을 시스템 팔레트에 즉시 매핑하기 때문에 응용 프로그램은 클라이언트 영역을 업데이트할 필요가 없습니다.|
|[CPalette:: CreateHalftonePalette](#createhalftonepalette)|장치 컨텍스트에 대 한 하프톤 색상표를 만들어 `CPalette` 개체에 연결 합니다.|
|[CPalette:: CreatePalette](#createpalette)|Windows 색상표를 만들어 `CPalette` 개체에 연결 합니다.|
|[CPalette:: FromHandle](#fromhandle)|Windows 색상표 개체에 대 한 핸들을 지정 하는 경우 `CPalette` 개체에 대 한 포인터를 반환 합니다.|
|[CPalette:: GetEntryCount](#getentrycount)|논리 색상표에 있는 색상표 항목 수를 검색 합니다.|
|[CPalette:: GetNearestPaletteIndex](#getnearestpaletteindex)|색 값과 가장 가깝게 일치 하는 논리 색상표의 항목 인덱스를 반환 합니다.|
|[CPalette:: GetPaletteEntries](#getpaletteentries)|논리 색상표에서 색상표 항목의 범위를 검색 합니다.|
|[CPalette:: ResizePalette](#resizepalette)|`CPalette` 개체에서 지정 하는 논리 색상표의 크기를 지정 된 항목 수로 변경 합니다.|
|[CPalette:: SetPaletteEntries](#setpaletteentries)|논리 색상표의 항목 범위에서 RGB 색 값과 플래그를 설정 합니다.|

### <a name="public-operators"></a>Public 연산자

|name|설명|
|----------|-----------------|
|[CPalette:: operator HPALETTE](#operator_hpalette)|`CPalette`에 연결 된 HPALETTE를 반환 합니다.|

## <a name="remarks"></a>설명

색상표는 응용 프로그램과 컬러 출력 장치 (예: 디스플레이 장치) 간의 인터페이스를 제공 합니다. 인터페이스를 사용 하면 응용 프로그램에서 다른 응용 프로그램에 표시 된 색을 심각 하 게 방해 하지 않고 출력 장치의 색 기능을 최대한 활용할 수 있습니다. Windows에서는 응용 프로그램의 논리 색상표 (필요한 색 목록)와 사용 가능한 색을 정의 하는 시스템 팔레트를 사용 하 여 사용 되는 색을 결정 합니다.

`CPalette` 개체는 개체에서 참조 하는 색상표를 조작 하기 위한 멤버 함수를 제공 합니다. `CPalette` 개체를 생성 하 고 해당 멤버 함수를 사용 하 여 실제 색상표, GDI (그래픽 장치 인터페이스) 개체를 만들고 해당 항목 및 기타 속성을 조작 합니다.

`CPalette`사용에 대 한 자세한 내용은 [그래픽 개체](../../mfc/graphic-objects.md)를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="animatepalette"></a>CPalette:: AnimatePalette

`CPalette` 개체에 연결 된 논리 색상표의 항목을 바꿉니다.

```
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>매개 변수

*nStartIndex*<br/>
애니메이션을 적용할 색상표의 첫 번째 항목을 지정 합니다.

*nNumEntries*<br/>
애니메이션을 적용할 색상표의 항목 수를 지정 합니다.

*lpPaletteColors*<br/>
[PALETTEENTRY](/previous-versions/dd162769\(v=vs.85\)) 구조체 배열의 첫 번째 멤버를 가리키면 *Nstartindex* 및 *nNumEntries*로 식별 되는 색상표 항목이 바뀝니다.

### <a name="remarks"></a>설명

응용 프로그램이 `AnimatePalette`를 호출할 때 Windows는 새 항목을 시스템 팔레트에 즉시 매핑하기 때문에 클라이언트 영역을 업데이트할 필요가 없습니다.

`AnimatePalette` 함수는 `CPalette` 개체에 연결 된 [Logpalette](/windows/win32/api/wingdi/ns-wingdi-logpalette) 구조의 해당 `palPaletteEntry` 멤버에 설정 된 PC_RESERVED 플래그를 사용 하는 항목만 변경 합니다. 이 구조에 대 한 자세한 내용은 Windows SDK의 LOGPALETTE를 참조 하세요.

##  <a name="cpalette"></a>CPalette:: CPalette

`CPalette` 개체를 생성합니다.

```
CPalette();
```

### <a name="remarks"></a>설명

`CreatePalette`를 호출 하 여 연결 하기 전 까지는 개체에 연결 된 색상표가 없습니다.

##  <a name="createhalftonepalette"></a>CPalette:: CreateHalftonePalette

장치 컨텍스트에 대 한 하프톤 색상표를 만듭니다.

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
장치 컨텍스트를 식별 합니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

장치 컨텍스트의 늘이기 모드가 하프톤으로 설정 된 경우 응용 프로그램에서 하프톤 색상표를 만들어야 합니다. 그런 다음 [CreateHalftonePalette](/windows/win32/api/wingdi/nf-wingdi-createhalftonepalette) 멤버 함수에서 반환 된 논리적 하프톤 색상표를 선택 하 고 [CDC:: StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) 또는 [StretchDIBits](/windows/win32/api/wingdi/nf-wingdi-stretchdibits) 함수를 호출 하기 전에 장치 컨텍스트로 인식 해야 합니다.

`CreateHalftonePalette` 및 `StretchDIBits`에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

##  <a name="createpalette"></a>CPalette:: CreatePalette

Windows 논리 색상표를 만든 다음 `CPalette` 개체에 연결 하 여 `CPalette` 개체를 초기화 합니다.

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>매개 변수

*lpLogPalette*<br/>
논리 색상표의 색에 대 한 정보를 포함 하는 [Logpalette](/windows/win32/api/wingdi/ns-wingdi-logpalette) 구조를 가리킵니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`LOGPALETTE` 구조에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

##  <a name="fromhandle"></a>CPalette:: FromHandle

Windows 색상표 개체에 대 한 핸들을 지정 하는 경우 `CPalette` 개체에 대 한 포인터를 반환 합니다.

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>매개 변수

*hPalette*<br/>
Windows GDI 색상표에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

성공 하는 경우 `CPalette` 개체에 대 한 포인터입니다. 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

`CPalette` 개체가 아직 Windows 색상표에 연결 되지 않은 경우 임시 `CPalette` 개체가 만들어지고 연결 됩니다. 이 임시 `CPalette` 개체는 다음에 응용 프로그램이 이벤트 루프에서 유휴 시간을 초과 하 여 모든 임시 그래픽 개체가 삭제 될 때 까지만 유효 합니다. 즉, 임시 개체는 하나의 창 메시지를 처리 하는 동안에만 유효 합니다.

##  <a name="getentrycount"></a>CPalette:: GetEntryCount

지정 된 논리 색상표의 항목 수를 검색 하려면이 멤버 함수를 호출 합니다.

```
int GetEntryCount();
```

### <a name="return-value"></a>반환 값

논리 색상표의 항목 수입니다.

##  <a name="getnearestpaletteindex"></a>CPalette:: GetNearestPaletteIndex

지정 된 색 값과 가장 근접 하 게 일치 하는 논리 색상표의 항목 인덱스를 반환 합니다.

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>매개 변수

*crColor*<br/>
일치 시킬 색을 지정 합니다.

### <a name="return-value"></a>반환 값

논리 색상표에 있는 항목의 인덱스입니다. 항목에는 지정 된 색과 가장 일치 하는 색이 포함 되어 있습니다.

##  <a name="getpaletteentries"></a>CPalette:: GetPaletteEntries

논리 색상표에서 색상표 항목의 범위를 검색 합니다.

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>매개 변수

*nStartIndex*<br/>
검색할 논리 색상표의 첫 번째 항목을 지정 합니다.

*nNumEntries*<br/>
검색할 논리 색상표의 항목 수를 지정 합니다.

*lpPaletteColors*<br/>
[PALETTEENTRY](/previous-versions/dd162769\(v=vs.85\)) 데이터 구조의 배열을 가리키면 색상표 항목이 수신 됩니다. 배열에는 적어도 *nNumEntries*에 지정 된 것과 같은 수의 데이터 구조가 포함 되어야 합니다.

### <a name="return-value"></a>반환 값

논리 색상표에서 검색 된 항목 수입니다. 함수가 실패 한 경우 0입니다.

##  <a name="operator_hpalette"></a>CPalette:: operator HPALETTE

이 연산자를 사용 하 여 `CPalette` 개체의 연결 된 Windows GDI 핸들을 가져옵니다.

```
operator HPALETTE() const;
```

### <a name="return-value"></a>반환 값

성공 하면 `CPalette` 개체가 나타내는 Windows GDI 개체에 대 한 핸들입니다. 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

이 연산자는 HPALETTE 개체의 직접 사용을 지 원하는 캐스팅 연산자입니다.

그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 Windows SDK의 [그래픽 개체](/windows/win32/gdi/graphic-objects) 문서를 참조 하세요.

##  <a name="resizepalette"></a>CPalette:: ResizePalette

`CPalette` 개체에 연결 된 논리 색상표의 크기를 *nNumEntries*에 지정 된 항목 수에 맞게 변경 합니다.

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>매개 변수

*nNumEntries*<br/>
색상표의 크기를 조정한 후의 항목 수를 지정 합니다.

### <a name="return-value"></a>반환 값

색상표의 크기가 조정 되 면 0이 아닌 값으로 조정 됩니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램이 팔레트의 크기를 줄이기 위해 `ResizePalette`를 호출 하는 경우 크기가 조정 된 색상표에 남아 있는 항목은 변경 되지 않습니다. 응용 프로그램이 팔레트를 확대 하기 위해 `ResizePalette`를 호출 하는 경우 추가 색상표 항목은 black (빨강, 녹색 및 파랑 값 모두 0)로 설정 되 고 모든 추가 항목에 대 한 플래그는 0으로 설정 됩니다.

Windows API `ResizePalette`에 대 한 자세한 내용은 Windows SDK의 [ResizePalette](/windows/win32/api/wingdi/nf-wingdi-resizepalette) 를 참조 하세요.

##  <a name="setpaletteentries"></a>CPalette:: SetPaletteEntries

논리 색상표의 항목 범위에서 RGB 색 값과 플래그를 설정 합니다.

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>매개 변수

*nStartIndex*<br/>
설정할 논리 색상표의 첫 번째 항목을 지정 합니다.

*nNumEntries*<br/>
설정할 논리 색상표의 항목 수를 지정 합니다.

*lpPaletteColors*<br/>
[PALETTEENTRY](/previous-versions/dd162769\(v=vs.85\)) 데이터 구조의 배열을 가리키면 색상표 항목이 수신 됩니다. 배열에는 적어도 *nNumEntries*에 지정 된 것과 같은 수의 데이터 구조가 포함 되어야 합니다.

### <a name="return-value"></a>반환 값

논리 색상표에 설정 된 항목 수입니다. 함수가 실패 한 경우 0입니다.

### <a name="remarks"></a>설명

응용 프로그램이 `SetPaletteEntries`를 호출할 때 논리 색상표를 장치 컨텍스트로 선택 하면 응용 프로그램에서 [CDC:: RealizePalette](../../mfc/reference/cdc-class.md#realizepalette)를 호출할 때까지 변경 내용이 적용 되지 않습니다.

자세한 내용은 Windows SDK에서 [PALETTEENTRY](/previous-versions/dd162769\(v=vs.85\)) 을 참조 하세요.

## <a name="see-also"></a>참고 항목

[MFC 샘플 DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CPalette:: GetPaletteEntries](#getpaletteentries)<br/>
[CPalette:: SetPaletteEntries](#setpaletteentries)
