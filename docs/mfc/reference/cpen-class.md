---
title: CPen 클래스
ms.date: 11/04/2016
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
ms.openlocfilehash: e15dc53fafa0d80f1b52b3fe77f3635c592a4346
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364075"
---
# <a name="cpen-class"></a>CPen 클래스

Windows GDI(그래픽 디바이스 인터페이스) 펜을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CPen : public CGdiObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CPen:::CPen](#cpen)|`CPen` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPen:::만들기펜](#createpen)|지정된 스타일, 너비 및 브러시 특성을 사용하여 논리적 코스메틱 또는 기하학적 펜을 만들고 오브젝트에 `CPen` 연결합니다.|
|[CPen::생성펜간접](#createpenindirect)|[LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen) 구조에 제공된 스타일, 너비 및 색상이 있는 펜을 만들고 `CPen` 개체에 연결합니다.|
|[CPen::From핸들](#fromhandle)|Windows HPEN이 `CPen` 지정되면 개체에 대한 포인터를 반환합니다.|
|[CPen::GetExtLogPen](#getextlogpen)|[EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen) 기본 구조를 가져옵니다.|
|[CPen::GetLogPen](#getlogpen)|[LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen) 기본 구조를 가져옵니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CPen::연산자 HPEN](#operator_hpen)|개체에 연결된 Windows `CPen` 핸들을 반환합니다.|

## <a name="remarks"></a>설명

사용에 `CPen`대한 자세한 내용은 [그래픽 개체](../../mfc/graphic-objects.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cpencpen"></a><a name="cpen"></a>CPen:::CPen

`CPen` 개체를 생성합니다.

```
CPen();

CPen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

CPen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>매개 변수

*nPenStyle*<br/>
펜 스타일을 지정합니다. 생성자의 첫 번째 버전에서 이 매개 변수는 다음 값 중 하나가 될 수 있습니다.

- PS_SOLID 단단한 펜을 만듭니다.

- PS_DASH 파선 펜을 만듭니다. 장치 단위에서 펜 너비가 1 이하인 경우에만 유효합니다.

- PS_DOT 점선 펜을 만듭니다. 장치 단위에서 펜 너비가 1 이하인 경우에만 유효합니다.

- PS_DASHDOT 번갈아 대시와 점이 있는 펜을 만듭니다. 장치 단위에서 펜 너비가 1 이하인 경우에만 유효합니다.

- PS_DASHDOTDOT 번갈아 대시와 이중 점이 있는 펜을 만듭니다. 장치 단위에서 펜 너비가 1 이하인 경우에만 유효합니다.

- PS_NULL null 펜을 만듭니다.

- PS_INSIDEFRAME 경계 `Ellipse`사각형(예: , 의 및 `Rectangle` `RoundRect` `Pie` `Chord` 멤버 함수)을 지정하는 Windows GDI 출력 함수에서 생성된 닫힌 셰이프 프레임 내부에 선을 그리는 펜을 만듭니다. 이 스타일을 경계 사각형(예: `LineTo` 멤버 함수)을 지정하지 않는 Windows GDI 출력 함수와 함께 사용되는 경우 펜의 드로잉 영역은 프레임에 의해 제한되지 않습니다.

`CPen` 생성자의 두 번째 버전은 형식, 스타일, 끝 캡 및 조인 특성의 조합을 지정합니다. 각 범주의 값은 비트별 OR 연산자(&#124;)를 사용하여 결합해야 합니다. 펜 유형은 다음 값 중 하나일 수 있습니다.

- PS_GEOMETRIC 기하학적 펜을 작성합니다.

- PS_COSMETIC 화장품 펜을 만듭니다.

   `CPen` 생성자의 두 번째 버전은 *nPenStyle에*대해 다음 펜 스타일을 추가합니다.

- PS_ALTERNATE 다른 모든 픽셀을 설정하는 펜을 만듭니다. (이 스타일은 코스메틱 펜에만 적용됩니다.)

- PS_USERSTYLE 사용자가 제공한 스타일 배열을 사용하는 펜을 만듭니다.

   끝 캡은 다음 값 중 하나일 수 있습니다.

- PS_ENDCAP_ROUND 엔드 캡은 둥글게 됩니다.

- PS_ENDCAP_SQUARE 엔드 캡은 정사각형입니다.

- PS_ENDCAP_FLAT 엔드 캡은 평평합니다.

   조인은 다음 값 중 하나일 수 있습니다.

- PS_JOIN_BEVEL 조인이 절로 나타냈습니다.

- PS_JOIN_MITER 조인은 [SetMiterLimit](/windows/win32/api/wingdi/nf-wingdi-setmiterlimit) 함수에서 설정한 현재 제한 내에 있을 때 마이터됩니다. 조인이 이 제한을 초과하면 절이 됩니다.

- PS_JOIN_ROUND 조인은 둥글다.

*nWidth*<br/>
펜의 너비를 지정합니다.

- 생성자의 첫 번째 버전에서 이 값이 0이면 매핑 모드에 관계없이 장치 단위의 너비는 항상 1픽셀입니다.

- 생성자의 두 번째 버전의 경우 *nPenStyle이* PS_GEOMETRIC 경우 너비는 논리 단위로 지정됩니다. *nPenStyle이* PS_COSMETIC 경우 너비를 1로 설정해야 합니다.

*crColor*<br/>
펜에 대한 RGB 색상이 포함되어 있습니다.

*pLogBrush*<br/>
구조를 가리킵니다. `LOGBRUSH` *nPenStyle이* PS_COSMETIC 경우 `LOGBRUSH` 구조의 *lbColor* 멤버는 펜의 색상을 지정하고 구조의 `LOGBRUSH` *lbStyle* 멤버를 BS_SOLID 설정해야 합니다. *nPenStyle이* PS_GEOMETRIC 경우 모든 멤버를 사용하여 펜의 브러시 속성을 지정해야 합니다.

*n스타일카운트*<br/>
*lpStyle* 배열의 길이(이중 단어 단위)를 지정합니다. *nPenStyle이* PS_USERSTYLE 않은 경우 이 값은 0이어야 합니다.

*lp스타일*<br/>
이중 단어 값의 배열을 가리킵니다. 첫 번째 값은 사용자 정의 스타일에서 첫 번째 대시의 길이를 지정하고 두 번째 값은 첫 번째 공간의 길이 등을 지정합니다. *nPenStyle이* PS_USERSTYLE 않은 경우 이 포인터는 NULL이어야 합니다.

### <a name="remarks"></a>설명

인수 없이 생성자 사용 하는 `CPen` 경우 `CreatePen`는 을 사용 하 `CreatePenIndirect`여 `CreateStockObject` 결과 개체를 초기화 해야 합니다.

인수를 사용하는 생성자(생성자)를 사용하는 경우 추가 초기화가 필요하지 않습니다. 인수가 있는 생성자는 오류가 발생하면 예외를 throw할 수 있지만 인수가 없는 생성자는 항상 성공합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

## <a name="cpencreatepen"></a><a name="createpen"></a>CPen:::만들기펜

지정된 스타일, 너비 및 브러시 특성을 사용하여 논리적 코스메틱 또는 기하학적 펜을 만들고 오브젝트에 `CPen` 연결합니다.

```
BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>매개 변수

*nPenStyle*<br/>
펜의 스타일을 지정합니다. 가능한 값 목록은 [CPen](#cpen) 생성자의 *nPenStyle* 매개 변수를 참조하십시오.

*nWidth*<br/>
펜의 너비를 지정합니다.

- 의 첫 번째 `CreatePen`버전에서 이 값이 0이면 매핑 모드에 관계없이 장치 단위의 너비는 항상 1픽셀입니다.

- 의 두 번째 `CreatePen`버전에 대 한 *nPenStyle* PS_GEOMETRIC 경우 너비 논리 단위로 지정 됩니다. *nPenStyle이* PS_COSMETIC 경우 너비를 1로 설정해야 합니다.

*crColor*<br/>
펜에 대한 RGB 색상이 포함되어 있습니다.

*pLogBrush*<br/>
[로그브러시](/windows/win32/api/wingdi/ns-wingdi-logbrush) 구조를 가리킵니다. *nPenStyle이* PS_COSMETIC 경우 `lbColor` `LOGBRUSH` 구조의 멤버는 펜의 색상을 지정하고 구조체의 `LOGBRUSH` *lbStyle* 멤버를 BS_SOLID 설정해야 합니다. nPenStyle이 PS_GEOMETRIC 경우 모든 멤버를 사용하여 펜의 브러시 속성을 지정해야 합니다.

*n스타일카운트*<br/>
*lpStyle* 배열의 길이(이중 단어 단위)를 지정합니다. *nPenStyle이* PS_USERSTYLE 않은 경우 이 값은 0이어야 합니다.

*lp스타일*<br/>
이중 단어 값의 배열을 가리킵니다. 첫 번째 값은 사용자 정의 스타일에서 첫 번째 대시의 길이를 지정하고 두 번째 값은 첫 번째 공간의 길이 등을 지정합니다. *nPenStyle이* PS_USERSTYLE 않은 경우 이 포인터는 NULL이어야 합니다.

### <a name="return-value"></a>Return Value

성공한 경우 0이 아닌 경우, 메서드가 실패하면 0입니다.

### <a name="remarks"></a>설명

첫 번째 `CreatePen` 버전에서는 지정된 스타일, 너비 및 색상으로 펜을 초기화합니다. 이후에 펜을 모든 장치 컨텍스트의 현재 펜으로 선택할 수 있습니다.

너비가 1픽셀보다 큰 펜은 항상 PS_NULL, PS_SOLID 또는 PS_INSIDEFRAME 스타일을 가져야 합니다.

펜에 PS_INSIDEFRAME 스타일과 논리적 색상 표의 색상과 일치하지 않는 색상이 있는 경우 펜은 디더색상으로 그려집니다. PS_SOLID 펜 스타일은 디더 색상의 펜을 만드는 데 사용할 수 없습니다. PS_INSIDEFRAME 스타일이 펜 너비가 1보다 낮거나 같으면 PS_SOLID 동일합니다.

두 번째 `CreatePen` 버전의 경우 지정된 스타일, 너비 및 브러시 특성이 있는 논리 적 장식 또는 기하학적 펜을 초기화합니다. 코스메틱 펜의 너비는 항상 1입니다. 기하학적 펜의 너비는 항상 표준 단위로 지정됩니다. 응용 프로그램이 논리 펜을 생성한 후 [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) 함수를 호출하여 해당 펜을 장치 컨텍스트로 선택할 수 있습니다. 펜을 장치 컨텍스트로 선택한 후 선과 곡선을 그리는 데 사용할 수 있습니다.

- *nPenStyle이* PS_COSMETIC PS_USERSTYLE 경우 *lpStyle* 배열의 항목은 스타일 단위로 대시 및 공백의 길이를 지정합니다. 스타일 단위는 펜이 선을 그리는 데 사용되는 장치에 의해 정의됩니다.

- *nPenStyle이* PS_GEOMETRIC PS_USERSTYLE 경우 *lpStyle* 배열의 항목은 논리 단위로 대시 및 공백의 길이를 지정합니다.

- *nPenStyle이* PS_ALTERNATE 스타일 단위는 무시되고 다른 모든 픽셀이 설정됩니다.

응용 프로그램에 지정된 펜이 더 이상 필요하지 않은 경우 [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) 멤버 함수를 호출하거나 리소스가 더 이상 사용되지 않도록 `CPen` 개체를 삭제해야 합니다. 응용 프로그램은 장치 컨텍스트에서 펜을 선택할 때 펜을 삭제해서는 안 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

## <a name="cpencreatepenindirect"></a><a name="createpenindirect"></a>CPen::생성펜간접

*lpLogPen으로*가리키는 구조에 주어진 스타일, 너비 및 색상이 있는 펜을 초기화합니다.

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>매개 변수

*lpLogPen*<br/>
펜에 대한 정보가 포함된 Windows [LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

너비가 1픽셀보다 큰 펜은 항상 PS_NULL, PS_SOLID 또는 PS_INSIDEFRAME 스타일을 가져야 합니다.

펜에 PS_INSIDEFRAME 스타일과 논리적 색상 표의 색상과 일치하지 않는 색상이 있는 경우 펜은 디더색상으로 그려집니다. PS_INSIDEFRAME 스타일은 펜 너비가 1보다 낮거나 같으면 PS_SOLID 동일합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

## <a name="cpenfromhandle"></a><a name="fromhandle"></a>CPen::From핸들

Windows GDI `CPen` 펜 개체에 핸들이 지정된 개체에 대한 포인터를 반환합니다.

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>매개 변수

*hPen*<br/>
`HPEN`윈도우 GDI 펜에 핸들.

### <a name="return-value"></a>Return Value

성공한 경우 `CPen` 개체에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

`CPen` 개체가 핸들에 연결되지 않은 경우 임시 `CPen` 개체를 만들어 연결합니다. 이 `CPen` 임시 개체는 다음에 응용 프로그램이 이벤트 루프에서 유휴 시간을 가지며 모든 임시 그래픽 개체가 삭제될 때까지만 유효합니다. 즉, 임시 개체는 하나의 창 메시지를 처리하는 동안에만 유효합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

## <a name="cpengetextlogpen"></a><a name="getextlogpen"></a>CPen::GetExtLogPen

`EXTLOGPEN` 기본 구조를 가져옵니다.

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>매개 변수

*pLogPen*<br/>
펜에 대한 정보가 포함된 [EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 `EXTLOGPEN` 구조는 펜의 스타일, 너비 및 브러시 속성을 정의합니다. 예를 들어 `GetExtLogPen` 펜의 특정 스타일과 일치하도록 호출합니다.

펜 속성에 대한 자세한 내용은 Windows SDK의 다음 항목을 참조하십시오.

- [Getobject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [엑스로그펜](/windows/win32/api/wingdi/ns-wingdi-extlogpen)

- [로그펜 (것)과 함께](/windows/win32/api/wingdi/ns-wingdi-logpen)

- [엑스트만들기펜](/windows/win32/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>예제

다음 코드 예제에서는 `GetExtLogPen` 펜의 특성을 검색한 다음 동일한 색상의 새 장식 펜을 만드는 호출을 보여 줍니다.

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

## <a name="cpengetlogpen"></a><a name="getlogpen"></a>CPen::GetLogPen

`LOGPEN` 기본 구조를 가져옵니다.

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>매개 변수

*pLogPen*<br/>
펜에 대한 정보를 포함하는 [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 `LOGPEN` 구조는 펜의 스타일, 색상 및 패턴을 정의합니다.

예를 들어 `GetLogPen` 특정 펜 스타일과 일치하도록 호출합니다.

펜 속성에 대한 자세한 내용은 Windows SDK의 다음 항목을 참조하십시오.

- [Getobject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [로그펜 (것)과 함께](/windows/win32/api/wingdi/ns-wingdi-logpen)

### <a name="example"></a>예제

다음 코드 예제에서는 `GetLogPen` 펜 문자를 검색한 다음 동일한 색상의 새 단색 펜을 만드는 호출을 보여 줍니다.

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

## <a name="cpenoperator-hpen"></a><a name="operator_hpen"></a>CPen::연산자 HPEN

개체의 연결된 Windows GDI `CPen` 핸들을 가져옵니다.

```
operator HPEN() const;
```

### <a name="return-value"></a>Return Value

성공하면 개체로 표시되는 Windows GDI 개체에 대한 핸들입니다. `CPen` 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 연산자는 HPEN 개체의 직접 사용을 지원하는 캐스팅 연산자입니다.

그래픽 개체 사용에 대한 자세한 내용은 Windows SDK의 [그래픽 개체](/windows/win32/gdi/graphic-objects) 문서를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>참고 항목

[CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C브러시 클래스](../../mfc/reference/cbrush-class.md)
