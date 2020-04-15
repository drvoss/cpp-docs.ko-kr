---
title: C폰트 클래스
ms.date: 11/04/2016
f1_keywords:
- CFont
- AFXWIN/CFont
- AFXWIN/CFont::CFont
- AFXWIN/CFont::CreateFont
- AFXWIN/CFont::CreateFontIndirect
- AFXWIN/CFont::CreatePointFont
- AFXWIN/CFont::CreatePointFontIndirect
- AFXWIN/CFont::FromHandle
- AFXWIN/CFont::GetLogFont
helpviewer_keywords:
- CFont [MFC], CFont
- CFont [MFC], CreateFont
- CFont [MFC], CreateFontIndirect
- CFont [MFC], CreatePointFont
- CFont [MFC], CreatePointFontIndirect
- CFont [MFC], FromHandle
- CFont [MFC], GetLogFont
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
ms.openlocfilehash: 36fd469b182d5f3e0d3449112d04c1a8623d7526
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373836"
---
# <a name="cfont-class"></a>C폰트 클래스

Windows GDI(그래픽 디바이스 인터페이스) 글꼴을 캡슐화하고 글꼴 조작을 위한 멤버 함수를 제공합니다.

## <a name="syntax"></a>구문

```
class CFont : public CGdiObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CFont::CFont](#cfont)|`CFont` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CFont::CreateFont](#createfont)|지정된 특성으로 `CFont` a를 초기화합니다.|
|[C글꼴::만들기글꼴 간접](#createfontindirect)|구조에 `CFont` 지정된 특성을 가진 객체를 `LOGFONT` 초기화합니다.|
|[C글꼴::만들기 포인트글꼴](#createpointfont)|지정된 높이로 `CFont` a를 초기화하고 점의 10분의 1로 측정하고 서체를 입력합니다.|
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|글꼴 `CreateFontIndirect` 높이가 논리적 단위가 아닌 점의 10분의 1로 측정된다는 점을 제외하면 동일합니다.|
|[C글꼴::에서 핸들](#fromhandle)|Windows HFONT가 `CFont` 지정되면 개체에 대한 포인터를 반환합니다.|
|[CFont::GetLogFont](#getlogfont)|개체에 `LOGFONT` 연결된 논리 글꼴에 대한 정보로 채웁니다. `CFont`|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C글꼴::연산자 HFONT](#operator_hfont)|개체에 연결된 Windows GDI `CFont` 글꼴 핸들을 반환합니다.|

## <a name="remarks"></a>설명

개체 `CFont`를 사용 하려면 `CFont` 개체를 생성하고 [createfont](#createfont), [CreateFontIndirect](#createfontindirect), [createpointfont](#createpointfont) 또는 [CreatePointFontIndirect](#createpointfontindirect)을 간접적으로 사용하여 Windows 글꼴을 연결하고 개체의 멤버를 사용합니다.

및 `CreatePointFontIndirect` 함수는 포인트 크기에서 `CreateFont` 논리 `CreateFontIndirect` 단위로 글꼴 높이를 자동으로 변환하기 때문에 사용이 더 쉽거나 사용하기 쉽습니다. `CreatePointFont`

자세한 `CFont`내용은 그래픽 [개체](../../mfc/graphic-objects.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cfontcfont"></a><a name="cfont"></a>C글꼴:::C글꼴

`CFont` 개체를 생성합니다.

```
CFont();
```

### <a name="remarks"></a>설명

결과 `CreateFont`개체를 `CreateFontIndirect`"를 `CreatePointFont`사용하거나 `CreatePointFontIndirect` 먼저 사용하려면 먼저 초기화해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

## <a name="cfontcreatefont"></a><a name="createfont"></a>C글꼴:::글꼴 만들기

지정된 특성을 `CFont` 가진 객체를 초기화합니다.

```
BOOL CreateFont(
    int nHeight,
    int nWidth,
    int nEscapement,
    int nOrientation,
    int nWeight,
    BYTE bItalic,
    BYTE bUnderline,
    BYTE cStrikeOut,
    BYTE nCharSet,
    BYTE nOutPrecision,
    BYTE nClipPrecision,
    BYTE nQuality,
    BYTE nPitchAndFamily,
    LPCTSTR lpszFacename);
```

### <a name="parameters"></a>매개 변수

*nHeight*<br/>
글꼴의 원하는 높이(논리 단위)를 지정합니다. 설명은 `lfHeight` Windows SDK의 [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)구조의 멤버를 참조하십시오. *nHeight의* 절대값은 변환된 후 장치 단위16,384를 초과해서는 안 됩니다. 모든 높이 비교의 경우 글꼴 매퍼는 요청된 크기를 초과하지 않는 가장 큰 글꼴 또는 요청된 크기를 초과하는 경우 가장 작은 글꼴을 찾습니다.

*nWidth*<br/>
글꼴에 있는 문자의 평균 너비(논리 단위)를 지정합니다. *nWidth가* 0이면 장치의 가로 세로 비율이 사용 가능한 글꼴의 디지털화 종횡비와 일치하여 가장 가까운 일치를 찾을 수 있으며, 이는 차이의 절대 값에 의해 결정됩니다.

*nEscapement*<br/>
이스케이프먼트 벡터와 디스플레이 표면의 x축 사이의 각도(0.1도 단위)를 지정합니다. 이스케이프먼트 벡터는 줄의 첫 번째 및 마지막 문자의 원통과를 통과하는 선입니다. 각도는 x축에서 시계 반대 방향으로 측정됩니다. 자세한 `lfEscapement` 내용은 Windows `LOGFONT` SDK의 구조에 있는 멤버를 참조하십시오.

*nOrientation*<br/>
문자의 기준선과 x축 사이의 각도(0.1도 단위)를 지정합니다. 각도는 y 방향이 다운되고 y 방향이 위로 있는 좌표계의 경우 x축에서 시계 방향으로 시계 방향으로 측정됩니다.

*nWeight*<br/>
글꼴 가중치를 지정합니다(1000개당 잉크픽셀). 자세한 내용은 Windows SDK의 구조에 `LOGFONT` 있는 *lfWeight* 멤버를 참조하십시오. 설명된 값은 근사치입니다. 실제 모양은 서체에 따라 다릅니다. 일부 글꼴에는 FW_NORMAL, FW_REGULAR 및 FW_BOLD 가중치만 있습니다. FW_DONTCARE 지정하면 기본 가중치가 사용됩니다.

*bItalic*<br/>
글꼴이 기울임꼴인지 여부를 지정합니다.

*bUnderline*<br/>
글꼴에 밑줄이 그어져 있는지 여부를 지정합니다.

*cStrikeOut*<br/>
글꼴의 문자가 삼진으로 처리되는지 여부를 지정합니다. 영이 아닌 값으로 설정된 경우 스트라이크아웃 글꼴을 지정합니다.

*nCharSet*<br/>
글꼴의 문자 집합을 지정Windows `lfCharSet` SDK의 `LOGFONT` 구조에 있는 멤버를 값 목록에 대 한 지정 합니다.

OEM 문자 집합은 시스템에 따라 다릅니다.

다른 문자 집합이 있는 글꼴이 시스템에 있을 수 있습니다. 알 수 없는 문자 집합이 있는 글꼴을 사용하는 응용 프로그램은 해당 글꼴로 렌더링할 문자열을 번역하거나 해석해서는 안 됩니다. 대신 문자열을 출력 장치 드라이버로 직접 전달해야 합니다.

글꼴 매퍼는 DEFAULT_CHARSET 값을 사용하지 않습니다. 응용 프로그램은 이 값을 사용하여 글꼴의 이름과 크기를 사용하여 논리 글꼴을 완전히 설명할 수 있습니다. 지정된 이름의 글꼴이 없는 경우 모든 문자 집합의 글꼴을 지정된 글꼴로 대체할 수 있습니다. 예기치 않은 결과를 방지하려면 응용 프로그램에서 DEFAULT_CHARSET 값을 아껴서 사용해야 합니다.

*nOutPrecision*<br/>
원하는 출력 정밀도를 지정합니다. 출력 정밀도는 출력이 요청된 글꼴의 높이, 너비, 문자 방향, 이스케이프먼트 및 피치와 얼마나 가깝게 일치해야 하는지 정의합니다. 값 `lfOutPrecision` 및 자세한 `LOGFONT` 내용은 Windows SDK의 구조에 있는 멤버를 참조하십시오.

*nClipPrecision*<br/>
원하는 클리핑 정밀도를 지정합니다. 클리핑 정밀도는 클리핑 영역 외부에 있는 문자를 클립하는 방법을 정의합니다. 값 `lfClipPrecision` 목록은 Windows `LOGFONT` SDK의 구조에 있는 멤버를 참조하십시오.

포함된 읽기 전용 글꼴을 사용하려면 응용 프로그램에서 CLIP_ENCAPSULATE 지정해야 합니다.

장치, TrueType 및 벡터 글꼴의 일관된 회전을 달성하기 위해 응용 프로그램은 OR 연산자에서 CLIP_LH_ANGLES 값을 다른 *nClipPrecision* 값과 결합할 수 있습니다. CLIP_LH_ANGLES 비트가 설정된 경우 모든 글꼴의 회전은 좌표계의 방향이 왼손잡이인지 오른손잡이인지에 따라 달라집니다. 좌표계 의 방향에 대한 자세한 내용은 *nOrientation* 매개변수설명을 참조하십시오. CLIP_LH_ANGLES 설정되지 않은 경우 장치 글꼴은 항상 시계 반대 방향으로 회전하지만 다른 글꼴의 회전은 좌표계의 방향에 따라 달라집니다.

*nQuality*<br/>
GDI가 논리 글꼴 속성을 실제 실제 글꼴의 특성과 일치시키려고 얼마나 신중하게 시도해야 하는지 정의하는 글꼴의 출력 품질을 지정합니다. 값 `lfQuality` 목록은 Windows `LOGFONT` SDK의 구조에 있는 멤버를 참조하십시오.

*nPitchAndFamily*<br/>
글꼴의 피치와 패밀리를 지정합니다. 값 `lfPitchAndFamily` 및 자세한 `LOGFONT` 내용은 Windows SDK의 구조에 있는 멤버를 참조하십시오.

*lpszFacename*<br/>
글꼴의 서체 이름을 지정하는 null 종료 된 문자열에 대한 포인터 `CString` 또는 포인터입니다. 이 문자열의 길이는 30자를 초과해서는 안 됩니다. Windows [EnumFontFamily](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesw) 함수를 사용하여 현재 사용 가능한 모든 글꼴을 열거할 수 있습니다. *lpszFacename이* NULL이면 GDI는 장치 독립적인 서체를 사용합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이후에 글꼴을 모든 장치 컨텍스트의 글꼴로 선택할 수 있습니다.

이 `CreateFont` 함수는 새 Windows GDI 글꼴을 만들지 않습니다. GDI에서 사용할 수 있는 실제 글꼴에서 가장 가까운 일치를 선택합니다.

응용 프로그램은 논리 글꼴을 만들 때 대부분의 매개 변수에 대한 기본 설정을 사용할 수 있습니다. 항상 특정 값을 지정해야 하는 매개 변수는 *nHeight* 및 *lpszFacename*입니다. *nHeight* 및 *lpszFacename이* 응용 프로그램에서 설정되지 않은 경우 생성되는 논리 글꼴은 장치에 따라 다릅니다.

함수에서 `CFont` 만든 개체로 완료하면 장치 컨텍스트에 다른 글꼴을 선택한 다음 `CFont` 더 이상 필요하지 않은 개체를 삭제하는 데 사용합니다. `CDC::SelectObject` `CreateFont`

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

## <a name="cfontcreatefontindirect"></a><a name="createfontindirect"></a>C글꼴::만들기글꼴 간접

[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 구조체에 지정된 특성을 사용하여 `CFont` 개체를 초기화합니다.

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>매개 변수

*lpLogFont*<br/>
논리 글꼴의 `LOGFONT` 특성을 정의하는 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이후에 글꼴을 모든 장치의 현재 글꼴로 선택할 수 있습니다.

이 글꼴은 [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 구조에 지정된 특성을 가지고 있습니다. [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) 멤버 함수를 사용하여 글꼴을 선택하면 GDI 글꼴 매퍼가 논리 글꼴을 기존 실제 글꼴과 일치시키려고 시도합니다. 글꼴 매퍼가 논리 글꼴과 정확히 일치하지 않는 경우 가능한 한 많은 특성과 일치하는 대체 글꼴을 제공합니다.

함수에서 만든 `CFont` 개체가 더 이상 필요하지 않은 경우 장치 컨텍스트에 다른 글꼴을 선택한 다음 더 이상 필요하지 않은 `CFont` 개체를 삭제하는 데 사용합니다. `CDC::SelectObject` `CreateFontIndirect`

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

## <a name="cfontcreatepointfont"></a><a name="createpointfont"></a>C글꼴::만들기 포인트글꼴

이 함수는 지정된 서체 및 점 크기의 글꼴을 만드는 간단한 방법을 제공합니다.

```
BOOL CreatePointFont(
    int nPointSize,
    LPCTSTR lpszFaceName,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>매개 변수

*nPointSize*<br/>
포인트의 10분의 1에 글꼴 높이를 요청했습니다. 예를 들어 120을 통과하여 12포인트 글꼴을 요청합니다.

*lpszFace네임*<br/>
글꼴의 서체 이름을 지정하는 null 종료 된 문자열에 대한 포인터 `CString` 또는 포인터입니다. 이 문자열의 길이는 30자를 초과해서는 안 됩니다. Windows 'EnumFontFamily 함수는 현재 사용 가능한 모든 글꼴을 열거하는 데 사용할 수 있습니다. *lpszFaceName이* NULL이면 GDI는 장치 독립적인 서체를 사용합니다.

*pDC*<br/>
*nPointSize의* 높이를 논리 단위로 변환하는 데 사용할 [CDC](../../mfc/reference/cdc-class.md) 개체에 대한 포인터입니다. NULL인 경우 변환에 화면 장치 컨텍스트가 사용됩니다.

### <a name="return-value"></a>Return Value

성공하지 못하면 0이 아닌 0입니다.

### <a name="remarks"></a>설명

*pDC가*가리키는 CDC 개체를 사용하여 *nPointSize의* 높이를 논리 단위로 자동으로 변환합니다.

함수에 `CFont` 의해 생성된 개체로 완료하면 먼저 장치 컨텍스트에서 글꼴을 선택한 다음 개체를 삭제합니다. `CFont` `CreatePointFont`

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

## <a name="cfontcreatepointfontindirect"></a><a name="createpointfontindirect"></a>CFont::만들기포인트폰트간접

이 함수는 [CreateFontIndirect와](#createfontindirect) 동일하지만 `lfHeight` 의 `LOGFONT` 멤버는 장치 단위가 아닌 점의 10분의 1로 해석됩니다.

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>매개 변수

*lpLogFont*<br/>
논리 글꼴의 특성을 정의하는 [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 구조를 가리킵니다. 구조의 `lfHeight` `LOGFONT` 멤버는 논리적 단위가 아닌 점의 10분의 1로 측정됩니다. 예를 들어 120으로 설정하여 `lfHeight` 12포인트 글꼴을 요청합니다.

*pDC*<br/>
높이를 [CDC](../../mfc/reference/cdc-class.md) 논리 단위로 변환하는 데 사용할 `lfHeight` CDC 개체에 대한 포인터입니다. NULL인 경우 변환에 화면 장치 컨텍스트가 사용됩니다.

### <a name="return-value"></a>Return Value

성공하지 못하면 0이 아닌 0입니다.

### <a name="remarks"></a>설명

이 함수는 `lfHeight` `LOGFONT` 구조를 Windows에 전달하기 전에 *pDC가* 가리키는 CDC 개체를 사용하여 높이를 논리 단위로 자동으로 변환합니다.

함수에 `CFont` 의해 생성된 개체로 완료하면 먼저 장치 컨텍스트에서 글꼴을 선택한 다음 개체를 삭제합니다. `CFont` `CreatePointFontIndirect`

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

## <a name="cfontfromhandle"></a><a name="fromhandle"></a>C글꼴::에서 핸들

Windows GDI `CFont` 글꼴 개체에 HFONT 핸들을 지정하면 개체에 대한 포인터를 반환합니다.

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>매개 변수

*hFont*<br/>
Windows 글꼴에 대한 HFONT 핸들입니다.

### <a name="return-value"></a>Return Value

성공한 경우 `CFont` 개체에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

개체가 `CFont` 핸들에 아직 연결되어 있지 않으면 `CFont` 임시 개체가 만들어지고 첨부됩니다. 이 `CFont` 임시 개체는 다음에 응용 프로그램이 이벤트 루프에서 유휴 시간을 가지며 모든 임시 그래픽 개체가 삭제될 때까지만 유효합니다. 이 것을 말하는 또 다른 방법은 임시 개체가 하나의 창 메시지를 처리하는 동안에만 유효하다는 것입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

## <a name="cfontgetlogfont"></a><a name="getlogfont"></a>C글꼴:::겟로그폰트

이 함수를 호출하여 에 `LOGFONT` 대한 `CFont`구조의 복사본을 검색합니다.

```
int GetLogFont(LOGFONT* pLogFont);
```

### <a name="parameters"></a>매개 변수

*pLogFont*<br/>
글꼴 정보를 수신하려면 [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닌 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]

## <a name="cfontoperator-hfont"></a><a name="operator_hfont"></a>C글꼴::연산자 HFONT

이 연산자를 사용하여 개체에 연결된 글꼴의 Windows GDI 핸들을 `CFont` 가져옵니다.

```
operator HFONT() const;
```

### <a name="return-value"></a>Return Value

`CFont` 성공하면 연결된 Windows GDI 글꼴 개체의 핸들입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 연산자는 `CFont` [글꼴 및 텍스트로](/windows/win32/gdi/fonts-and-text)변환하는 데 자동으로 `CFont` 사용되므로 HFONT를 기대하는 함수에 개체를 전달할 수 있습니다.

그래픽 개체 사용에 대한 자세한 내용은 Windows SDK의 [그래픽 개체를](/windows/win32/gdi/graphic-objects) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>참고 항목

[MFC 샘플 HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
