---
title: C브러시 클래스
ms.date: 11/04/2016
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
helpviewer_keywords:
- CBrush [MFC], CBrush
- CBrush [MFC], CreateBrushIndirect
- CBrush [MFC], CreateDIBPatternBrush
- CBrush [MFC], CreateHatchBrush
- CBrush [MFC], CreatePatternBrush
- CBrush [MFC], CreateSolidBrush
- CBrush [MFC], CreateSysColorBrush
- CBrush [MFC], FromHandle
- CBrush [MFC], GetLogBrush
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
ms.openlocfilehash: 15132bb5497886638edfe431ae769dd446785df8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352485"
---
# <a name="cbrush-class"></a>C브러시 클래스

Windows GDI(그래픽 디바이스 인터페이스) 브러시를 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CBrush : public CGdiObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CBrush::CBrush](#cbrush)|`CBrush` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CBrush::CreateBrushIndirect](#createbrushindirect)|[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) 구조에 지정된 스타일, 색상 및 패턴으로 브러시를 초기화합니다.|
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|장치 독립 비트맵(DIB)에 의해 지정된 패턴으로 브러시를 초기화합니다.|
|[C브러시:::해치 브러쉬 만들기](#createhatchbrush)|지정된 해치 된 패턴 및 색상으로 브러시를 초기화합니다.|
|[C브러시::패턴 브러쉬 만들기](#createpatternbrush)|비트맵에 의해 지정된 패턴으로 브러시를 초기화합니다.|
|[C브러시::솔리드 브러쉬 만들기](#createsolidbrush)|지정된 단색으로 브러시를 초기화합니다.|
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|기본 시스템 색상인 브러시를 만듭니다.|
|[C브러시::에서 핸들](#fromhandle)|Windows `HBRUSH` 개체에 `CBrush` 핸들을 지정하면 개체에 대한 포인터를 반환합니다.|
|[CBrush::GetLogBrush](#getlogbrush)|[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) 구조를 가져옵니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C브러시::연산자 H브러시](#operator_hbrush)|개체에 연결된 Windows `CBrush` 핸들을 반환합니다.|

## <a name="remarks"></a>설명

개체를 `CBrush` 사용하려면 개체를 `CBrush` 생성하고 브러시가 필요한 멤버 `CDC` 함수에 전달합니다.

브러시는 솔리드, 해치 또는 패턴일 수 있습니다.

자세한 `CBrush`내용은 그래픽 [개체](../../mfc/graphic-objects.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBrush`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cbrushcbrush"></a><a name="cbrush"></a>C 브러시 :: C 브러시

`CBrush` 개체를 생성합니다.

```
CBrush();
CBrush(COLORREF crColor);
CBrush(int nIndex, COLORREF crColor);
explicit CBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>매개 변수

*crColor*<br/>
브러시의 전경 색상을 RGB 색상으로 지정합니다. 브러시가 해치된 경우 이 매개변수는 해칭의 색상을 지정합니다.

*nIndex*<br/>
브러시의 해치 스타일을 지정합니다. 다음 값 중 하나일 수 있습니다.

- HS_BDIAGONAL 하향 해치(왼쪽에서 오른쪽)를 45도에서

- HS_CROSS 수평 및 수직 크로스해치

- 45도에서 크로스해치 HS_DIAGCROSS

- HS_FDIAGONAL 위쪽 해치(왼쪽에서 오른쪽)를 45도에서

- HS_HORIZONTAL 수평 해치

- HS_VERTICAL 수직 해치

*pBitmap*<br/>
브러시가 `CBitmap` 페인트하는 비트맵을 지정하는 개체를 가리킵니다.

### <a name="remarks"></a>설명

`CBrush`오버로드된 생성자 4개가 있습니다. 인수가 없는 생성자는 초기화되지 `CBrush` 않은 개체를 생성한 후 사용할 수 있습니다.

인수없이 생성물을 사용하는 경우 `CBrush` [SolidBrush 만들기, CreateHatchBrush,](#createsolidbrush) [CreateBrush직접](#createbrushindirect)만들기, [CreatePatternBrush](#createpatternbrush)또는 [CreateDIBPatternBrush](#createdibpatternbrush)를 사용하여 결과 개체를 초기화해야 합니다. [CreateHatchBrush](#createhatchbrush) 인수를 사용하는 생성자 중 하나를 사용하는 경우 추가 초기화가 필요하지 않습니다. 인수가 있는 생성자는 오류가 발생하면 예외를 throw할 수 있지만 인수가 없는 생성자는 항상 성공합니다.

단일 [COLORREF](/windows/win32/gdi/colorref) 매개 변수가 있는 생성자는 지정된 색상으로 솔리드 브러시를 구성합니다. 색상은 RGB 값을 지정하고 WINDOWS에서 RGB 매크로로 구성할 수 있습니다. H.

두 매개변수가 있는 생성자는 해치 브러시를 생성합니다. *nIndex* 매개 변수는 해치된 패턴의 인덱스를 지정합니다. *crColor* 매개 변수는 색상을 지정합니다.

매개 변수가 `CBitmap` 있는 생성자는 패턴브러시를 생성합니다. 매개 변수는 비트맵을 식별합니다. 비트맵은 [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap,](../../mfc/reference/cbitmap-class.md#loadbitmap)또는 [CBitmap::Create CompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)을 사용하여 생성된 것으로 가정합니다. 채우기 패턴에 사용할 비트맵의 최소 크기는 8x8픽셀입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]

## <a name="cbrushcreatebrushindirect"></a><a name="createbrushindirect"></a>C브러시::브러시 간접 만들기

[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) 구조에 지정된 스타일, 색상 및 패턴으로 브러시를 초기화합니다.

```
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```

### <a name="parameters"></a>매개 변수

*lpLogBrush*<br/>
브러시에 대한 정보가 포함된 [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이후에 브러시를 모든 장치 컨텍스트의 현재 브러시로 선택할 수 있습니다.

현재 텍스트 및 배경 색을 사용하여 흑백(평면 1개, 픽셀당 1비트) 비트맵을 사용하여 만든 브러시가 그려집니다. 비트로 표시된 픽셀은 0으로 설정되어 현재 텍스트 색상으로 그려집니다. 비트로 표시되는 픽셀은 1로 설정되어 현재 배경색으로 그려집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]

## <a name="cbrushcreatedibpatternbrush"></a><a name="createdibpatternbrush"></a>C브러시::만들기디비패턴브러쉬

장치 독립 비트맵(DIB)에 의해 지정된 패턴으로 브러시를 초기화합니다.

```
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,
    UINT nUsage);

BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,
    UINT nUsage);
```

### <a name="parameters"></a>매개 변수

*hPackedDIB*<br/>
압축된 장치 독립 비트맵(DIB)을 포함하는 전역 메모리 개체를 식별합니다.

*nUsage*<br/>
[BITMAPINFO](/windows/win32/api/wingdi/ns-wingdi-bitmapinfo) 데이터 구조의 `bmiColors[]` 필드 ("압축 된 DIB"의 일부)에 명시적 RGB 값이나 인덱스가 현재 인식되는 논리 색상표에 포함되는지 여부를 지정합니다. 매개 변수는 다음 값 중 하나여야 합니다.

- DIB_PAL_COLORS 색상 테이블은 16비트 인덱스 배열로 구성됩니다.

- DIB_RGB_COLORS 색상 테이블에리터럴 RGB 값이 포함되어 있습니다.

*lpPackedDIB*<br/>
`BITMAPINFO` 구조로 구성된 압축된 DIB를 가리키고 비트맵의 픽셀을 정의하는 바이트 배열이 바로 뒤따릅니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

래스터 작업을 지원하는 모든 장치 컨텍스트에 대해 이후에 브러시를 선택할 수 있습니다.

두 버전은 DIB를 처리하는 방식이 다릅니다.

- 첫 번째 버전에서는 DIB에 대한 핸들을 얻으려면 `GlobalAlloc` Windows 함수를 호출하여 전역 메모리 블록을 할당한 다음 압축된 DIB로 메모리를 채웁니다.

- 두 번째 버전에서는 압축된 DIB에 대한 메모리 할당을 호출할 `GlobalAlloc` 필요가 없습니다.

압축된 DIB는 `BITMAPINFO` 비트맵의 픽셀을 정의하는 바이트 배열 다음에 바로 뒤에 있는 데이터 구조로 구성됩니다. 채우기 패턴으로 사용되는 비트맵은 8x8픽셀이어야 합니다. 비트맵이 큰 경우 Windows는 비트맵의 왼쪽 위 모서리에 있는 처음 8행과 8개의 픽셀 열에 해당하는 비트만 사용하여 채우기 패턴을 만듭니다.

응용 프로그램이 단색 장치 컨텍스트로 2색 DIB 패턴 브러시를 선택하면 Windows는 DIB에 지정된 색상을 무시하고 대신 장치 컨텍스트의 현재 텍스트 및 배경 색을 사용하여 패턴 브러시를 표시합니다. DIB의 첫 번째 색상(DIB 색상 표의 오프셋 0)에 매핑된 픽셀은 텍스트 색상을 사용하여 표시됩니다. 두 번째 색상에 매핑된 픽셀(색상 표의 오프셋 1에서)은 배경색을 사용하여 표시됩니다.

다음 Windows 함수 사용에 대한 자세한 내용은 Windows SDK를 참조하십시오.

- [CreateDIBPatternBrush](/windows/win32/api/wingdi/nf-wingdi-createdibpatternbrush) (이 함수는 3.0 `CreateDIBPatternBrushPt` 이전 Windows 버전에 대해 작성된 응용 프로그램과의 호환성을 위해서만 제공됩니다.

- [CreateDIBPatternBrushPt(이](/windows/win32/api/wingdi/nf-wingdi-createdibpatternbrushpt) 함수는 Win32 기반 응용 프로그램에 사용해야 합니다.)

- [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc)

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]

## <a name="cbrushcreatehatchbrush"></a><a name="createhatchbrush"></a>C브러시:::해치 브러쉬 만들기

지정된 해치 된 패턴 및 색상으로 브러시를 초기화합니다.

```
BOOL CreateHatchBrush(
    int nIndex,
    COLORREF crColor);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
브러시의 해치 스타일을 지정합니다. 다음 값 중 하나일 수 있습니다.

- HS_BDIAGONAL 하향 해치(왼쪽에서 오른쪽)를 45도에서

- HS_CROSS 수평 및 수직 크로스해치

- 45도에서 크로스해치 HS_DIAGCROSS

- HS_FDIAGONAL 위쪽 해치(왼쪽에서 오른쪽)를 45도에서

- HS_HORIZONTAL 수평 해치

- HS_VERTICAL 수직 해치

*crColor*<br/>
브러시의 전경 색상을 RGB 색상(해치의 색상)으로 지정합니다. 자세한 내용은 Windows SDK의 [COLORREF를](/windows/win32/gdi/colorref) 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이후에 브러시를 모든 장치 컨텍스트의 현재 브러시로 선택할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]

## <a name="cbrushcreatepatternbrush"></a><a name="createpatternbrush"></a>C브러시::패턴 브러쉬 만들기

비트맵에 의해 지정된 패턴으로 브러시를 초기화합니다.

```
BOOL CreatePatternBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>매개 변수

*pBitmap*<br/>
비트맵을 식별합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

래스터 작업을 지원하는 모든 장치 컨텍스트에 대해 이후에 브러시를 선택할 수 있습니다. *pBitmap으로* 식별 된 비트 맵은 일반적으로 [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmapIndirect :](../../mfc/reference/cbitmap-class.md#createbitmapindirect) [CBitmap : CBitmap ::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), 또는 [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) 함수를 사용하여 초기화됩니다.

채우기 패턴으로 사용되는 비트맵은 8x8픽셀이어야 합니다. 비트맵이 큰 경우 Windows는 비트맵의 왼쪽 위 모서리에 있는 처음 8행 및 픽셀 열에 해당하는 비트만 사용합니다.

패턴 브러시는 연결된 비트맵에 영향을 주지 않고 삭제할 수 있습니다. 즉, 비트맵을 사용하여 임의의 수의 패턴 브러시를 만들 수 있습니다.

현재 텍스트 및 배경 색을 사용하여 흑백 비트맵(1색 평면, 픽셀당 1비트)을 사용하여 만든 브러시가 그려집니다. 비트로 표시된 픽셀은 0으로 설정되어 현재 텍스트 색상으로 그려집니다. 비트로 표시되는 픽셀은 1로 설정되어 현재 배경색으로 그려집니다.

Windows 함수인 [CreatePatternBrush](/windows/win32/api/wingdi/nf-wingdi-createpatternbrush)사용에 대한 자세한 내용은 Windows SDK를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]

## <a name="cbrushcreatesolidbrush"></a><a name="createsolidbrush"></a>C브러시::솔리드 브러쉬 만들기

지정된 단색으로 브러시를 초기화합니다.

```
BOOL CreateSolidBrush(COLORREF crColor);
```

### <a name="parameters"></a>매개 변수

*crColor*<br/>
브러시의 색상을 지정하는 [COLORREF](/windows/win32/gdi/colorref) 구조입니다. 색상은 RGB 값을 지정하고 WINDOWS에서 RGB 매크로로 구성할 수 있습니다. H.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이후에 브러시를 모든 장치 컨텍스트의 현재 브러시로 선택할 수 있습니다.

응용 프로그램이 `CreateSolidBrush`만든 브러시를 사용하여 완료되면 장치 컨텍스트에서 브러시를 선택해야 합니다.

### <a name="example"></a>예제

  [CBrush::CBrush에](#cbrush)대한 예제를 참조하십시오.

## <a name="cbrushcreatesyscolorbrush"></a><a name="createsyscolorbrush"></a>C브러시::만들기SYsColor브러쉬

브러시 색상을 초기화합니다.

```
BOOL CreateSysColorBrush(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
색상 인덱스를 지정합니다. 이 값은 21개의 창 요소 중 하나를 페인칠하는 데 사용되는 색상에 해당합니다. 값 목록은 Windows SDK의 [GetSysColor를](/windows/win32/api/winuser/nf-winuser-getsyscolor) 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이후에 브러시를 모든 장치 컨텍스트의 현재 브러시로 선택할 수 있습니다.

응용 프로그램이 `CreateSysColorBrush`만든 브러시를 사용하여 완료되면 장치 컨텍스트에서 브러시를 선택해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]

## <a name="cbrushfromhandle"></a><a name="fromhandle"></a>C브러시::에서 핸들

Windows [HBRUSH](#operator_hbrush) `CBrush` 개체에 핸들을 지정하면 개체에 대한 포인터를 반환합니다.

```
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```

### <a name="parameters"></a>매개 변수

*hBrush*<br/>
Windows GDI 브러시를 처리합니다.

### <a name="return-value"></a>Return Value

성공한 경우 `CBrush` 개체에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

개체가 `CBrush` 핸들에 아직 연결되어 있지 않으면 `CBrush` 임시 개체가 만들어지고 첨부됩니다. 이 `CBrush` 임시 개체는 다음에 응용 프로그램이 이벤트 루프에 유휴 시간을 가지는 때까지만 유효합니다. 이 때 모든 임시 그래픽 개체가 삭제됩니다. 즉, 임시 개체는 하나의 창 메시지를 처리하는 동안에만 유효합니다.

그래픽 개체 사용에 대한 자세한 내용은 Windows SDK의 [그래픽 개체를](/windows/win32/gdi/graphic-objects) 참조하십시오.

### <a name="example"></a>예제

  [CBrush::CBrush에](#cbrush)대한 예제를 참조하십시오.

## <a name="cbrushgetlogbrush"></a><a name="getlogbrush"></a>C브러시::겟로그브러쉬

구조를 검색하려면 이 `LOGBRUSH` 멤버 함수를 호출합니다.

```
int GetLogBrush(LOGBRUSH* pLogBrush);
```

### <a name="parameters"></a>매개 변수

*pLogBrush*<br/>
브러시에 대한 정보가 포함된 [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

함수가 성공하고 *pLogBrush가* 유효한 포인터인 경우 반환 값은 버퍼에 저장된 바이트 수입니다.

함수가 성공하고 *pLogBrush가* NULL인 경우 반환 값은 함수가 버퍼에 저장할 정보를 보유하는 데 필요한 바이트 수입니다.

함수가 실패하면 반환 값은 0입니다.

### <a name="remarks"></a>설명

구조는 `LOGBRUSH` 브러시의 스타일, 색상 및 패턴을 정의합니다.

예를 들어 `GetLogBrush` 비트맵의 특정 색상 이나 패턴과 일치 하도록 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]

## <a name="cbrushoperator-hbrush"></a><a name="operator_hbrush"></a>C브러시::연산자 H브러시

이 연산자를 사용하여 개체의 연결된 `CBrush` Windows GDI 핸들을 가져옵니다.

```
operator HBRUSH() const;
```

### <a name="return-value"></a>Return Value

성공하면 개체로 표시되는 Windows GDI 개체에 대한 핸들입니다. `CBrush` 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 연산자는 HBRUSH 개체의 직접 사용을 지원하는 캐스팅 연산자입니다.

그래픽 개체 사용에 대한 자세한 내용은 Windows SDK의 [그래픽 개체를](/windows/win32/gdi/graphic-objects) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]

## <a name="see-also"></a>참고 항목

[MFC 샘플 PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C비트맵 클래스](../../mfc/reference/cbitmap-class.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)
