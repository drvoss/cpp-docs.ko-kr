---
title: CFontHolder 클래스
ms.date: 11/04/2016
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
ms.openlocfilehash: 36fbebc39101c5534bd52d4f79fee5286487a6e0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754988"
---
# <a name="cfontholder-class"></a>CFontHolder 클래스

스톡 글꼴 속성을 구현하고 Windows 글꼴 개체 및 `IFont` 인터페이스의 기능을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CFontHolder
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C글꼴 홀더::C폰트 홀더](#cfontholder)|`CFontHolder` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C글꼴 홀더::GetDisplay스트](#getdisplaystring)|컨테이너의 속성 브라우저에 표시되는 문자열을 검색합니다.|
|[C글꼴 홀더::겟폰트 디스패치](#getfontdispatch)|글꼴의 `IDispatch` 인터페이스를 반환합니다.|
|[C글꼴 홀더::겟폰트 핸들](#getfonthandle)|핸들을 Windows 글꼴로 반환합니다.|
|[C글꼴 홀더::초기화글꼴](#initializefont)|`CFontHolder` 개체를 초기화합니다.|
|[C글꼴 홀더::쿼리텍스트메트릭](#querytextmetrics)|관련 글꼴에 대한 정보를 검색합니다.|
|[C글꼴 홀더::릴리스 글꼴](#releasefont)|및 인터페이스에서 개체연결을 `CFontHolder` 끊습니다. `IFontNotification` `IFont`|
|[C글꼴 홀더::선택](#select)|장치 컨텍스트에 글꼴 리소스를 선택합니다.|
|[C글꼴 홀더::세트폰트](#setfont)|개체를 `CFontHolder` 인터페이스에 `IFont` 연결합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C폰트 홀더::m_pFont](#m_pfont)|개체의 인터페이스에 `CFontHolder` 대한 `IFont` 포인터입니다.|

## <a name="remarks"></a>설명

`CFontHolder`기본 클래스가 없습니다.

이 클래스를 사용하여 컨트롤에 대한 사용자 지정 글꼴 속성을 구현합니다. 이러한 속성을 만드는 방법에 대한 자세한 내용은 [ActiveX 컨트롤: 글꼴 사용](../../mfc/mfc-activex-controls-using-fonts.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CFontHolder`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="cfontholdercfontholder"></a><a name="cfontholder"></a>C글꼴 홀더::C폰트 홀더

`CFontHolder` 개체를 생성합니다.

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>매개 변수

*pNotify*<br/>
글꼴의 `IPropertyNotifySink` 인터페이스에 대한 포인터입니다.

### <a name="remarks"></a>설명

결과 개체를 사용하기 전에 호출하여 `InitializeFont` 결과 개체를 초기화해야 합니다.

## <a name="cfontholdergetdisplaystring"></a><a name="getdisplaystring"></a>C글꼴 홀더::GetDisplay스트

컨테이너의 속성 브라우저에 표시할 수 있는 문자열을 검색합니다.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>매개 변수

*strValue*<br/>
표시 문자열을 보유하는 [CString에](../../atl-mfc-shared/reference/cstringt-class.md) 대한 참조입니다.

### <a name="return-value"></a>Return Value

문자열이 성공적으로 검색되는 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="cfontholdergetfontdispatch"></a><a name="getfontdispatch"></a>C글꼴 홀더::겟폰트 디스패치

이 함수를 호출하여 글꼴의 디스패치 인터페이스에 대한 포인터를 검색합니다.

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>Return Value

개체의 인터페이스에 `CFontHolder` 대한 `IFontDisp` 포인터입니다. 호출하는 `GetFontDispatch` 함수는 이 `IUnknown::Release` 인터페이스 포인터를 호출해야 합니다.

### <a name="remarks"></a>설명

전화하기 `GetFontDispatch`전에 전화하십시오. `InitializeFont`

## <a name="cfontholdergetfonthandle"></a><a name="getfonthandle"></a>C글꼴 홀더::겟폰트 핸들

이 함수를 호출하여 Windows 글꼴에 대한 핸들을 가져옵니다.

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>매개 변수

*사이로만그(것)*<br/>
컨트롤이 그려지는 사각형의 높이(논리 단위)입니다.

*시히메트릭*<br/>
컨트롤의 높이(MM_HIMETRIC 단위)입니다.

### <a name="return-value"></a>Return Value

글꼴 개체에 대한 핸들; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

*cyLogical* 및 *cyHimetric의* 비율은 MM_HIMETRIC 단위로 표현된 글꼴의 점 크기에 대해 논리적 단위로 적절한 표시 크기를 계산하는 데 사용됩니다.

디스플레이 크기 = *(cylogical* / *cyHimetric)* X 글꼴 크기

매개 변수가 없는 버전은 화면에 대해 올바르게 크기의 글꼴로 핸들을 반환합니다.

## <a name="cfontholderinitializefont"></a><a name="initializefont"></a>C글꼴 홀더::초기화글꼴

`CFontHolder` 개체를 초기화합니다.

```cpp
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>매개 변수

*pFontDesc*<br/>
글꼴의 특성을 지정하는 글꼴 설명 [구조(FONTDESC)에](/windows/win32/api/olectl/ns-olectl-fontdesc)대한 포인터입니다.

*pFontDispAmbient*<br/>
컨테이너의 주변 Font 속성에 대한 포인터입니다.

### <a name="remarks"></a>설명

*pFontDispAmbient가* NULL이 아닌 `CFontHolder` 경우 개체는 컨테이너의 `IFont` 주변 Font 속성에서 사용하는 인터페이스의 복제본에 연결됩니다.

*pFontDispAmbient가* NULL인 경우 새 글꼴 개체는 *pFontDesc이* 가리키는 글꼴 설명에서 만들어지거나 *pFontDesc이* NULL인 경우 기본 설명에서 만들어집니다.

개체를 생성한 후 `CFontHolder` 이 함수를 호출합니다.

## <a name="cfontholderm_pfont"></a><a name="m_pfont"></a>C폰트 홀더::m_pFont

개체의 인터페이스에 `CFontHolder` 대한 `IFont` 포인터입니다.

```
LPFONT m_pFont;
```

## <a name="cfontholderquerytextmetrics"></a><a name="querytextmetrics"></a>C글꼴 홀더::쿼리텍스트메트릭

개체로 표시되는 실제 글꼴에 `CFontHolder` 대한 정보를 검색합니다.

```cpp
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>매개 변수

*lptm*<br/>
정보를 수신하는 [TEXTMETRIC](/windows/win32/api/wingdi/ns-wingdi-textmetricw) 구조에 대한 포인터입니다.

## <a name="cfontholderreleasefont"></a><a name="releasefont"></a>C글꼴 홀더::릴리스 글꼴

이 함수는 `CFontHolder` 개체의 `IFont` 인터페이스연결을 끊습니다.

```cpp
void ReleaseFont();
```

## <a name="cfontholderselect"></a><a name="select"></a>C글꼴 홀더::선택

이 함수를 호출하여 지정된 장치 컨텍스트에 컨트롤의 글꼴을 선택합니다.

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
글꼴이 선택되는 장치 컨텍스트입니다.

*사이로만그(것)*<br/>
컨트롤이 그려지는 사각형의 높이(논리 단위)입니다.

*시히메트릭*<br/>
컨트롤의 높이(MM_HIMETRIC 단위)입니다.

### <a name="return-value"></a>Return Value

대체되는 글꼴에 대한 포인터입니다.

### <a name="remarks"></a>설명

*cylogical* 및 *cyHimetric* 매개 변수에 대한 설명은 [GetFontHandle을](#getfonthandle) 참조하십시오.

## <a name="cfontholdersetfont"></a><a name="setfont"></a>C글꼴 홀더::세트폰트

기존 글꼴을 해제하고 `CFontHolder` 개체를 `IFont` 인터페이스에 연결합니다.

```cpp
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>매개 변수

*p뉴폰트*<br/>
새 `IFont` 인터페이스에 대한 포인터입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[프롭익스체인지 클래스](../../mfc/reference/cpropexchange-class.md)
