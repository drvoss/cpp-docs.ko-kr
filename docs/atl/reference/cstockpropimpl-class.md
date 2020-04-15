---
title: CStockPropImpl 클래스
ms.date: 05/06/2019
f1_keywords:
- CStockPropImpl
- ATLCTL/ATL::CStockPropImpl
- ATLCTL/ATL::get_Appearance
- ATLCTL/ATL::get_AutoSize
- ATLCTL/ATL::get_BackColor
- ATLCTL/ATL::get_BackStyle
- ATLCTL/ATL::get_BorderColor
- ATLCTL/ATL::get_BorderStyle
- ATLCTL/ATL::get_BorderVisible
- ATLCTL/ATL::get_BorderWidth
- ATLCTL/ATL::get_Caption
- ATLCTL/ATL::get_DrawMode
- ATLCTL/ATL::get_DrawStyle
- ATLCTL/ATL::get_DrawWidth
- ATLCTL/ATL::get_Enabled
- ATLCTL/ATL::get_FillColor
- ATLCTL/ATL::get_FillStyle
- ATLCTL/ATL::get_Font
- ATLCTL/ATL::get_ForeColor
- ATLCTL/ATL::get_HWND
- ATLCTL/ATL::get_MouseIcon
- ATLCTL/ATL::get_MousePointer
- ATLCTL/ATL::get_Picture
- ATLCTL/ATL::get_ReadyState
- ATLCTL/ATL::get_TabStop
- ATLCTL/ATL::get_Text
- ATLCTL/ATL::getvalid
- ATLCTL/ATL::get_Window
- ATLCTL/ATL::put_Appearance
- ATLCTL/ATL::put_AutoSize
- ATLCTL/ATL::put_BackColor
- ATLCTL/ATL::put_BackStyle
- ATLCTL/ATL::put_BorderColor
- ATLCTL/ATL::put_BorderStyle
- ATLCTL/ATL::put_BorderVisible
- ATLCTL/ATL::put_BorderWidth
- ATLCTL/ATL::put_Caption
- ATLCTL/ATL::put_DrawMode
- ATLCTL/ATL::put_DrawStyle
- ATLCTL/ATL::put_DrawWidth
- ATLCTL/ATL::put_Enabled
- ATLCTL/ATL::put_FillColor
- ATLCTL/ATL::put_FillStyle
- ATLCTL/ATL::put_Font
- ATLCTL/ATL::put_ForeColor
- ATLCTL/ATL::put_HWND
- ATLCTL/ATL::put_MouseIcon
- ATLCTL/ATL::put_MousePointer
- ATLCTL/ATL::put_Picture
- ATLCTL/ATL::put_ReadyState
- ATLCTL/ATL::put_TabStop
- ATLCTL/ATL::put_Text
- ATLCTL/ATL::putvalid
- ATLCTL/ATL::put_Window
- ATLCTL/ATL::putref_Font
- ATLCTL/ATL::putref_MouseIcon
- ATLCTL/ATL::putref_Picture
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
ms.openlocfilehash: 0aaeb1b6de0febfd5fc0d41cbcc7bad41c607af4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330669"
---
# <a name="cstockpropimpl-class"></a>CStockPropImpl 클래스

이 클래스는 주식 속성 값을 지원하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <
    class T,
    class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0,
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE CStockPropImpl :
    public IDispatchImpl<InterfaceName, piid, plibid, wMajor, wMinor, tihclass>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컨트롤을 구현 하고 에서 `CStockPropImpl`파생 하는 클래스입니다.

*인터페이스 이름*<br/>
스톡 속성을 노출하는 이중 인터페이스입니다.

*piid*<br/>
의 IID에 대한 `InterfaceName`포인터입니다.

*plibid*<br/>
의 정의를 포함하는 형식 라이브러리의 LIBID에 `InterfaceName`대한 포인터입니다.

*wMajor*<br/>
형식 라이브러리의 주 버전입니다. 기본값은 1입니다.

*wMinor*<br/>
형식 라이브러리의 부 버전입니다. 기본값은 0입니다.

*tihclass*<br/>
*T에*대 한 형식 정보를 관리 하는 데 사용 하는 클래스입니다. 기본값은 `CComTypeInfoHolder`.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|[get_Appearance](#get_appearance)|이 메서드를 호출하여 컨트롤에서 사용되는 페인트 스타일(예: 평면 또는 3D)을 가져옵니다.|
|[get_AutoSize](#get_autosize)|컨트롤이 다른 크기일 수 없는지 나타내는 플래그 의 상태를 얻으려면 이 메서드를 호출합니다.|
|[get_BackColor](#get_backcolor)|컨트롤의 배경색을 얻으려면이 메서드를 호출합니다.|
|[get_BackStyle](#get_backstyle)|투명또는 불투명한 컨트롤의 배경 스타일을 얻으려면 이 메서드를 호출합니다.|
|[get_BorderColor](#get_bordercolor)|컨트롤의 테두리 색상을 얻으려면이 메서드를 호출 합니다.|
|[get_BorderStyle](#get_borderstyle)|컨트롤의 테두리 스타일을 얻으려면이 메서드를 호출 합니다.|
|[get_BorderVisible](#get_bordervisible)|컨트롤의 테두리가 표시되는지 아닌지를 나타내는 플래그 상태를 얻으려면 이 메서드를 호출합니다.|
|[get_BorderWidth](#get_borderwidth)|이 메서드를 호출하여 컨트롤 테두리의 너비(픽셀)를 가져옵니다.|
|[get_Caption](#get_caption)|이 메서드를 호출하여 개체의 캡션에 지정된 텍스트를 가져옵니다.|
|[get_DrawMode](#get_drawmode)|이 메서드를 호출하여 컨트롤의 그리기 모드(예: XOR 펜 또는 색상 반전)를 가져옵니다.|
|[get_DrawStyle](#get_drawstyle)|이 메서드를 호출하여 컨트롤의 그리기 스타일(예: 솔리드, 파선 또는 점선)을 가져옵니다.|
|[get_DrawWidth](#get_drawwidth)|이 메서드를 호출하여 컨트롤의 그리기 메서드에서 사용되는 도면 폭(픽셀)을 가져옵니다.|
|[get_Enabled](#get_enabled)|컨트롤이 활성화되어 있는지 나타내는 플래그의 상태를 얻으려면 이 메서드를 호출합니다.|
|[get_FillColor](#get_fillcolor)|컨트롤의 채우기 색상을 얻으려면이 메서드를 호출합니다.|
|[get_FillStyle](#get_fillstyle)|이 메서드를 호출하여 컨트롤의 채우기 스타일(예: 솔리드, 투명 또는 교차 해치)을 가져옵니다.|
|[get_Font](#get_font)|컨트롤의 글꼴 속성에 대 한 포인터를 얻으려면이 메서드를 호출 합니다.|
|[get_ForeColor](#get_forecolor)|컨트롤의 전경 색상을 얻으려면이 메서드를 호출 합니다.|
|[get_HWND](#get_hwnd)|이 메서드를 호출하여 컨트롤과 연결된 창 핸들을 가져옵니다.|
|[get_MouseIcon](#get_mouseicon)|이 메서드를 호출하여 마우스가 컨트롤 위에 있을 때 표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성을 가져옵니다.|
|[get_MousePointer](#get_mousepointer)|이 메서드를 호출하여 마우스가 컨트롤 위에 있을 때 표시되는 마우스 포인터 유형(예: 화살표, 교차 또는 모래 시계)을 가져옵니다.|
|[get_Picture](#get_picture)|표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성에 대한 포인터를 얻으려면 이 메서드를 호출합니다.|
|[get_ReadyState](#get_readystate)|이 메서드를 호출하여 컨트롤의 준비 상태(예: 로드 또는 로드)를 가져옵니다.|
|[get_TabStop](#get_tabstop)|컨트롤이 탭 중지인지 아닌지를 나타내는 플래그를 얻으려면 이 메서드를 호출합니다.|
|[get_Text](#get_text)|컨트롤과 함께 표시되는 텍스트를 얻으려면 이 메서드를 호출합니다.|
|[유효하지 않음](#get_valid)|컨트롤이 유효한지 아닌지를 나타내는 플래그의 상태를 가져오려면 이 메서드를 호출합니다.|
|[get_Window](#get_window)|이 메서드를 호출하여 컨트롤과 연결된 창 핸들을 가져옵니다. [CStockPropImpl::get_HWND](#get_hwnd)동일합니다.|
|[put_Appearance](#put_appearance)|이 메서드를 호출하여 컨트롤에서 사용하는 페인트 스타일(예: 플랫 또는 3D)을 설정합니다.|
|[put_AutoSize](#put_autosize)|컨트롤이 다른 크기일 수 없는지 나타내는 플래그 값을 설정하려면 이 메서드를 호출합니다.|
|[put_BackColor](#put_backcolor)|컨트롤의 배경색을 설정하려면 이 메서드를 호출합니다.|
|[put_BackStyle](#put_backstyle)|컨트롤의 배경 스타일을 설정 하려면이 메서드를 호출 합니다.|
|[put_BorderColor](#put_bordercolor)|이 메서드를 호출하여 컨트롤의 테두리 색상을 설정합니다.|
|[put_BorderStyle](#put_borderstyle)|이 메서드를 호출하여 컨트롤의 테두리 스타일을 설정합니다.|
|[put_BorderVisible](#put_bordervisible)|이 메서드를 호출하여 컨트롤의 테두리가 표시되는지 아닌지 나타내는 플래그 값을 설정합니다.|
|[put_BorderWidth](#put_borderwidth)|이 메서드를 호출하여 컨트롤 테두리의 너비를 설정합니다.|
|[put_Caption](#put_caption)|컨트롤과 함께 표시할 텍스트를 설정하려면 이 메서드를 호출합니다.|
|[put_DrawMode](#put_drawmode)|이 메서드를 호출하여 컨트롤의 그리기 모드(예: XOR 펜 또는 색상 반전)를 설정합니다.|
|[put_DrawStyle](#put_drawstyle)|이 메서드를 호출하여 컨트롤의 그리기 스타일(예: 솔리드, 파선 또는 점선)을 설정합니다.|
|[put_DrawWidth](#put_drawwidth)|이 메서드를 호출하여 컨트롤의 그리기 메서드에서 사용되는 너비(픽셀)를 설정합니다.|
|[put_Enabled](#put_enabled)|이 메서드를 호출하여 컨트롤이 활성화되어 있는지 를 나타내는 플래그를 설정합니다.|
|[put_FillColor](#put_fillcolor)|컨트롤의 채우기 색상을 설정하려면 이 메서드를 호출합니다.|
|[put_FillStyle](#put_fillstyle)|이 메서드를 호출하여 컨트롤의 채우기 스타일(예: 솔리드, 투명 또는 교차 해치)을 설정합니다.|
|[put_Font](#put_font)|이 메서드를 호출하여 컨트롤의 글꼴 속성을 설정합니다.|
|[put_ForeColor](#put_forecolor)|이 메서드를 호출하여 컨트롤의 전경 색상을 설정합니다.|
|[put_HWND](#put_hwnd)|이 메서드는 E_FAIL 반환합니다.|
|[put_MouseIcon](#put_mouseicon)|이 메서드를 호출하여 마우스가 컨트롤 위에 있을 때 표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성을 설정합니다.|
|[put_MousePointer](#put_mousepointer)|이 메서드를 호출하여 마우스가 컨트롤 위에 있을 때 표시되는 마우스 포인터 유형(예: 화살표, 교차 또는 모래 시계)을 설정합니다.|
|[put_Picture](#put_picture)|이 메서드를 호출하여 표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성을 설정합니다.|
|[put_ReadyState](#put_readystate)|이 메서드를 호출하여 컨트롤의 준비 상태(예: 로드 또는 로드)를 설정합니다.|
|[put_TabStop](#put_tabstop)|컨트롤이 탭 중지인지 아닌지를 나타내는 플래그 값을 설정하려면 이 메서드를 호출합니다.|
|[put_Text](#put_text)|컨트롤과 함께 표시되는 텍스트를 설정하려면 이 메서드를 호출합니다.|
|[putvalid](#put_valid)|컨트롤이 유효한지 아닌지를 나타내는 플래그를 설정하려면 이 메서드를 호출합니다.|
|[put_Window](#put_window)|이 메서드는 [CStockPropImpl::put_HWND를](#put_hwnd)호출하여 E_FAIL 반환합니다.|
|[putref_Font](#putref_font)|참조 수를 사용하여 컨트롤의 글꼴 속성을 설정하려면 이 메서드를 호출합니다.|
|[putref_MouseIcon](#putref_mouseicon)|이 메서드를 호출하여 마우스가 컨트롤 위에 있을 때 참조 수를 사용하여 표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성을 설정합니다.|
|[putref_Picture](#putref_picture)|참조 개수와 함께 표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성을 설정하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

`CStockPropImpl`각 주식 속성에 대한 방법을 **제공하고** **얻을 수** 있습니다. 이러한 메서드는 각 속성과 연결된 데이터 멤버를 설정하거나 저장하고 속성이 변경될 때 컨테이너에 알리고 동기화하는 데 필요한 코드를 제공합니다.

Visual Studio는 마법사를 통해 스톡 속성에 대한 지원을 제공합니다. 컨트롤에 스톡 속성을 추가하는 자세한 내용은 [ATL 자습서를](../../atl/active-template-library-atl-tutorial.md)참조하십시오.

이전 버전과의 `CStockPropImpl` 호환성을 `get_Window` `put_Window` 위해 각각 `get_HWND` 호출하고 호출하는 메서드도 노출됩니다. `put_HWND` HWND는 `put_HWND` 읽기 전용 속성이어야 하므로 반환의 기본 구현은 E_FAIL.

다음 속성에는 **putref** 구현도 있습니다.

- 글꼴

- 마우스 아이콘

- Picture

동일한 세 스톡 속성은 해당 데이터 멤버가 할당 연산자를 통해 올바른 인터페이스 참조 카운트를 제공하는 형식 `CComPtr` 또는 다른 클래스여야 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`T`

[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)

`CStockPropImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="cstockpropimplget_appearance"></a><a name="get_appearance"></a>CStockPropImpl::get_Appearance

이 메서드를 호출하여 컨트롤에서 사용되는 페인트 스타일(예: 평면 또는 3D)을 가져옵니다.

```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```

### <a name="parameters"></a>매개 변수

*pn 모양*<br/>
컨트롤의 페인트 스타일을 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_autosize"></a><a name="get_autosize"></a>CStockPropImpl::get_AutoSize

컨트롤이 다른 크기일 수 없는지 나타내는 플래그 의 상태를 얻으려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```

### <a name="parameters"></a>매개 변수

*pbAutoSize*<br/>
플래그 상태를 받는 변수입니다. TRUE는 컨트롤이 다른 크기일 수 없음을 나타냅니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_backcolor"></a><a name="get_backcolor"></a>CStockPropImpl::get_BackColor

컨트롤의 배경색을 얻으려면이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```

### <a name="parameters"></a>매개 변수

*pclr백컬러*<br/>
컨트롤의 배경색을 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_backstyle"></a><a name="get_backstyle"></a>CStockPropImpl::get_BackStyle

투명또는 불투명한 컨트롤의 배경 스타일을 얻으려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```

### <a name="parameters"></a>매개 변수

*pn백 스타일*<br/>
컨트롤의 배경 스타일을 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_bordercolor"></a><a name="get_bordercolor"></a>CStockPropImpl::get_BorderColor

컨트롤의 테두리 색상을 얻으려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```

### <a name="parameters"></a>매개 변수

*pclr국경색상*<br/>
컨트롤의 테두리 색상을 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_borderstyle"></a><a name="get_borderstyle"></a>CStockPropImpl::get_BorderStyle

컨트롤의 테두리 스타일을 얻으려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```

### <a name="parameters"></a>매개 변수

*pnBorder스타일*<br/>
컨트롤의 테두리 스타일을 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_bordervisible"></a><a name="get_bordervisible"></a>CStockPropImpl::get_BorderVisible

컨트롤의 테두리가 표시되는지 아닌지를 나타내는 플래그 상태를 얻으려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```

### <a name="parameters"></a>매개 변수

*pbBordervisible*<br/>
플래그 상태를 받는 변수입니다. TRUE는 컨트롤의 테두리가 표시되고 있음을 나타냅니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_borderwidth"></a><a name="get_borderwidth"></a>CStockPropImpl::get_BorderWidth

이 메서드를 호출하여 컨트롤 테두리의 너비를 가져옵니다.

```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```

### <a name="parameters"></a>매개 변수

*pn국경폭*<br/>
컨트롤의 테두리 너비를 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_caption"></a><a name="get_caption"></a>CStockPropImpl::get_Caption

이 메서드를 호출하여 개체의 캡션에 지정된 텍스트를 가져옵니다.

```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```

### <a name="parameters"></a>매개 변수

*pbstrCaption*<br/>
컨트롤과 함께 표시할 텍스트입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_drawmode"></a><a name="get_drawmode"></a>CStockPropImpl::get_DrawMode

이 메서드를 호출하여 컨트롤의 그리기 모드(예: XOR 펜 또는 색상 반전)를 가져옵니다.

```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```

### <a name="parameters"></a>매개 변수

*pn드로우 모드*<br/>
컨트롤의 그리기 모드를 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_drawstyle"></a><a name="get_drawstyle"></a>CStockPropImpl::get_DrawStyle

이 메서드를 호출하여 컨트롤의 그리기 스타일(예: 솔리드, 파선 또는 점선)을 가져옵니다.

```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```

### <a name="parameters"></a>매개 변수

*pnDraw 스타일*<br/>
컨트롤의 그리기 스타일을 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_drawwidth"></a><a name="get_drawwidth"></a>CStockPropImpl::get_DrawWidth

이 메서드를 호출하여 컨트롤의 그리기 메서드에서 사용되는 도면 폭(픽셀)을 가져옵니다.

```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```

### <a name="parameters"></a>매개 변수

*pnDraw폭*<br/>
컨트롤의 너비 값을 픽셀 단위로 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_enabled"></a><a name="get_enabled"></a>CStockPropImpl::get_Enabled

컨트롤이 활성화되어 있는지 나타내는 플래그의 상태를 얻으려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```

### <a name="parameters"></a>매개 변수

*pbEnabled*<br/>
플래그 상태를 받는 변수입니다. TRUE는 컨트롤이 활성화되어 있음을 나타냅니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_fillcolor"></a><a name="get_fillcolor"></a>CStockPropImpl::get_FillColor

컨트롤의 채우기 색상을 얻으려면이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```

### <a name="parameters"></a>매개 변수

*pclrFillColor*<br/>
컨트롤의 채우기 색상을 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_fillstyle"></a><a name="get_fillstyle"></a>CStockPropImpl::get_FillStyle

이 메서드를 호출하여 컨트롤의 채우기 스타일(예: 솔리드, 투명 또는 크로스해칭)을 가져옵니다.

```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```

### <a name="parameters"></a>매개 변수

*pnFill스타일*<br/>
컨트롤의 채우기 스타일을 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_font"></a><a name="get_font"></a>CStockPropImpl::get_Font

컨트롤의 글꼴 속성에 대 한 포인터를 얻으려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```

### <a name="parameters"></a>매개 변수

*ppFont*<br/>
컨트롤의 글꼴 속성에 대한 포인터를 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_forecolor"></a><a name="get_forecolor"></a>CStockPropImpl::get_ForeColor

컨트롤의 전경 색상을 얻으려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```

### <a name="parameters"></a>매개 변수

*pclrForeColor*<br/>
컨트롤 전경 색상을 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_hwnd"></a><a name="get_hwnd"></a>CStockPropImpl::get_HWND

이 메서드를 호출하여 컨트롤과 연결된 창 핸들을 가져옵니다.

```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```

### <a name="parameters"></a>매개 변수

*phwnd*<br/>
컨트롤과 연결된 창 핸들입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_mouseicon"></a><a name="get_mouseicon"></a>CStockPropImpl::get_MouseIcon

이 메서드를 호출하여 마우스가 컨트롤 위에 있을 때 표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성을 가져옵니다.

```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>매개 변수

*pp사진*<br/>
그래픽의 그림 속성에 대한 포인터를 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_mousepointer"></a><a name="get_mousepointer"></a>CStockPropImpl::get_MousePointer

이 메서드를 호출하여 마우스가 컨트롤 위에 있을 때 표시되는 마우스 포인터 유형(예: 화살표, 교차 또는 모래 시계)을 가져옵니다.

```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```

### <a name="parameters"></a>매개 변수

*pn마우스 포인터*<br/>
마우스 포인터 의 형식을 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_picture"></a><a name="get_picture"></a>CStockPropImpl::get_Picture

표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성에 대한 포인터를 얻으려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>매개 변수

*pp사진*<br/>
그림의 속성에 대한 포인터를 받는 변수입니다. 자세한 내용은 [IPictureDisp를](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) 참조하십시오.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_readystate"></a><a name="get_readystate"></a>CStockPropImpl::get_ReadyState

이 메서드를 호출하여 컨트롤의 준비 상태(예: 로드 또는 로드)를 가져옵니다.

```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```

### <a name="parameters"></a>매개 변수

*pnReadyState*<br/>
컨트롤의 준비 상태를 받는 변수입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_tabstop"></a><a name="get_tabstop"></a>CStockPropImpl::get_TabStop

컨트롤이 탭 중지인지 아닌지를 나타내는 플래그 상태를 얻으려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```

### <a name="parameters"></a>매개 변수

*pbTabStop*<br/>
플래그 상태를 받는 변수입니다. TRUE는 컨트롤이 탭 중지임을 나타냅니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_text"></a><a name="get_text"></a>CStockPropImpl::get_Text

컨트롤과 함께 표시되는 텍스트를 얻으려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```

### <a name="parameters"></a>매개 변수

*pbstrText*<br/>
컨트롤과 함께 표시되는 텍스트입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplgetvalid"></a><a name="get_valid"></a>CStockPropImpl::getvalid

컨트롤이 유효한지 아닌지를 나타내는 플래그의 상태를 가져오려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```

### <a name="parameters"></a>매개 변수

*pbValid*<br/>
플래그 상태를 받는 변수입니다. TRUE는 컨트롤이 유효하다는 것을 나타냅니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplget_window"></a><a name="get_window"></a>CStockPropImpl::get_Window

이 메서드를 호출하여 컨트롤과 연결된 창 핸들을 가져옵니다. [CStockPropImpl::get_HWND](#get_hwnd)동일합니다.

```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```

### <a name="parameters"></a>매개 변수

*phwnd*<br/>
컨트롤과 연결된 창 핸들입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_appearance"></a><a name="put_appearance"></a>CStockPropImpl::put_외관

이 메서드를 호출하여 컨트롤에서 사용하는 페인트 스타일(예: 플랫 또는 3D)을 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```

### <a name="parameters"></a>매개 변수

*nAppearance*<br/>
컨트롤에서 사용할 새 페인트 스타일입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_autosize"></a><a name="put_autosize"></a>CStockPropImpl::put_AutoSize

컨트롤이 다른 크기일 수 없는지 나타내는 플래그 값을 설정하려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```

### <a name="parameters"></a>매개 변수

*b자동 크기*<br/>
컨트롤이 다른 크기일 수 없는 경우 TRUE입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_backcolor"></a><a name="put_backcolor"></a>CStockPropImpl::put_BackColor

컨트롤의 배경색을 설정하려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```

### <a name="parameters"></a>매개 변수

*clrBackColor*<br/>
새 컨트롤 배경색입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_backstyle"></a><a name="put_backstyle"></a>CStockPropImpl::put_BackStyle

컨트롤의 배경 스타일을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```

### <a name="parameters"></a>매개 변수

*n백 스타일*<br/>
새 컨트롤 배경 스타일입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_bordercolor"></a><a name="put_bordercolor"></a>CStockPropImpl::put_BorderColor

이 메서드를 호출하여 컨트롤의 테두리 색상을 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```

### <a name="parameters"></a>매개 변수

*clrBorderColor*<br/>
새 테두리 색상입니다. OLE_COLOR 데이터 형식은 내부적으로 32비트 긴 정수로 표시됩니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_borderstyle"></a><a name="put_borderstyle"></a>CStockPropImpl::put_BorderStyle

이 메서드를 호출하여 컨트롤의 테두리 스타일을 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```

### <a name="parameters"></a>매개 변수

*n보더스타일*<br/>
새 테두리 스타일입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_bordervisible"></a><a name="put_bordervisible"></a>CStockPropImpl::put_BorderVisible

이 메서드를 호출하여 컨트롤의 테두리가 표시되는지 아닌지 나타내는 플래그 값을 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```

### <a name="parameters"></a>매개 변수

*b테두리가 시사용*<br/>
테두리가 표시될 경우 TRUE입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_borderwidth"></a><a name="put_borderwidth"></a>CStockPropImpl::put_BorderWidth

이 메서드를 호출하여 컨트롤 테두리의 너비를 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```

### <a name="parameters"></a>매개 변수

*n테두리폭*<br/>
컨트롤 테두리의 새 너비입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_caption"></a><a name="put_caption"></a>CStockPropImpl::put_Caption

컨트롤과 함께 표시할 텍스트를 설정하려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```

### <a name="parameters"></a>매개 변수

*bstrCaption*<br/>
컨트롤과 함께 표시할 텍스트입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_drawmode"></a><a name="put_drawmode"></a>CStockPropImpl::put_DrawMode

이 메서드를 호출하여 컨트롤의 그리기 모드(예: XOR 펜 또는 색상 반전)를 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```

### <a name="parameters"></a>매개 변수

*n그리기 모드*<br/>
컨트롤에 대한 새 그리기 모드입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_drawstyle"></a><a name="put_drawstyle"></a>CStockPropImpl::put_DrawStyle

이 메서드를 호출하여 컨트롤의 그리기 스타일(예: 솔리드, 파선 또는 점선)을 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```

### <a name="parameters"></a>매개 변수

*n그리기 스타일*<br/>
컨트롤의 새 도면 스타일입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_drawwidth"></a><a name="put_drawwidth"></a>CStockPropImpl::put_Draw폭

이 메서드를 호출하여 컨트롤의 그리기 메서드에서 사용되는 너비(픽셀)를 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```

### <a name="parameters"></a>매개 변수

*n그리기 폭*<br/>
컨트롤의 그리기 메서드에서 사용할 새 너비입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_enabled"></a><a name="put_enabled"></a>CStockPropImpl::put_사용 가능

컨트롤이 활성화되어 있는지 나타내는 플래그 값을 설정하려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```

### <a name="parameters"></a>매개 변수

*bEnabled*<br/>
컨트롤이 활성화된 경우 TRUE입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_fillcolor"></a><a name="put_fillcolor"></a>CStockPropImpl::put_fillColor

컨트롤의 채우기 색상을 설정하려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```

### <a name="parameters"></a>매개 변수

*클라필 컬러*<br/>
컨트롤의 새 채우기 색상입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_fillstyle"></a><a name="put_fillstyle"></a>CStockPropImpl::put_FillStyle

이 메서드를 호출하여 컨트롤의 채우기 스타일(예: 솔리드, 투명 또는 교차 해치)을 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```

### <a name="parameters"></a>매개 변수

*n필 스타일*<br/>
컨트롤의 새 채우기 스타일입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_font"></a><a name="put_font"></a>CStockPropImpl::putut_글꼴

이 메서드를 호출하여 컨트롤의 글꼴 속성을 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
컨트롤의 글꼴 속성에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_forecolor"></a><a name="put_forecolor"></a>CStockPropImpl::put_포어컬러

이 메서드를 호출하여 컨트롤의 전경 색상을 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```

### <a name="parameters"></a>매개 변수

*클러포컬러*<br/>
컨트롤의 새 전경 색상입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_hwnd"></a><a name="put_hwnd"></a>CStockPropImpl::put_HWND

이 메서드는 E_FAIL 반환합니다.

```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
예약되어 있습니다.

### <a name="return-value"></a>Return Value

E_FAIL 반환합니다.

### <a name="remarks"></a>설명

창 핸들은 읽기 전용 값입니다.

## <a name="cstockpropimplput_mouseicon"></a><a name="put_mouseicon"></a>CStockPropImpl::put_MouseIcon

이 메서드를 호출하여 마우스가 컨트롤 위에 있을 때 표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성을 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>매개 변수

*p 그림*<br/>
그래픽의 그림 속성에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_mousepointer"></a><a name="put_mousepointer"></a>CStockPropImpl::put_마우스포인터

이 메서드를 호출하여 마우스가 컨트롤 위에 있을 때 표시되는 마우스 포인터 유형(예: 화살표, 교차 또는 모래 시계)을 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```

### <a name="parameters"></a>매개 변수

*n마우스 포인터*<br/>
마우스 포인터의 유형입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_picture"></a><a name="put_picture"></a>CStockPropImpl::put_picture

이 메서드를 호출하여 표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성을 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>매개 변수

*p 그림*<br/>
그림의 속성에 대한 포인터입니다. 자세한 내용은 [IPictureDisp를](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) 참조하십시오.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_readystate"></a><a name="put_readystate"></a>CStockPropImpl::put_ReadyState

이 메서드를 호출하여 컨트롤의 준비 상태(예: 로드 또는 로드)를 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```

### <a name="parameters"></a>매개 변수

*n레디스테이트*<br/>
컨트롤의 준비 상태입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_tabstop"></a><a name="put_tabstop"></a>CStockPropImpl::put_TabStop

이 메서드를 호출하여 컨트롤이 탭 중지인지 아닌지를 나타내는 플래그를 설정합니다.

```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```

### <a name="parameters"></a>매개 변수

*b탭스탑*<br/>
컨트롤이 탭 중지인 경우 TRUE입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_text"></a><a name="put_text"></a>CStockPropImpl::put_Text

컨트롤과 함께 표시되는 텍스트를 설정하려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```

### <a name="parameters"></a>매개 변수

*bstrText*<br/>
컨트롤과 함께 표시되는 텍스트입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplputvalid"></a><a name="put_valid"></a>CStockPropImpl::p유효

컨트롤이 유효한지 아닌지를 나타내는 플래그를 설정하려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```

### <a name="parameters"></a>매개 변수

*b 유효*<br/>
컨트롤이 유효한 경우 TRUE입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

## <a name="cstockpropimplput_window"></a><a name="put_window"></a>CStockPropImpl::put_Window

이 메서드는 [CStockPropImpl::put_HWND를](#put_hwnd)호출하여 E_FAIL 반환합니다.

```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
창 핸들입니다.

### <a name="return-value"></a>Return Value

E_FAIL 반환합니다.

### <a name="remarks"></a>설명

창 핸들은 읽기 전용 값입니다.

## <a name="cstockpropimplputref_font"></a><a name="putref_font"></a>CStockPropImpl::putref_글꼴

참조 수를 사용하여 컨트롤의 글꼴 속성을 설정하려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
컨트롤의 글꼴 속성에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[CStockPropImpl::put_Font와](#put_font)동일하지만 참조 수가 있습니다.

## <a name="cstockpropimplputref_mouseicon"></a><a name="putref_mouseicon"></a>CStockPropImpl::putref_MouseIcon

이 메서드를 호출하여 마우스가 컨트롤 위에 있을 때 참조 수를 사용하여 표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성을 설정합니다.

```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>매개 변수

*p 그림*<br/>
그래픽의 그림 속성에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[CStockPropImpl::put_MouseIcon과](#put_mouseicon)동일하지만 참조 수가 있습니다.

## <a name="cstockpropimplputref_picture"></a><a name="putref_picture"></a>CStockPropImpl::putref_사진

참조 개수와 함께 표시할 그래픽(아이콘, 비트맵 또는 메타파일)의 그림 속성을 설정하려면 이 메서드를 호출합니다.

```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>매개 변수

*p 그림*<br/>
그림의 속성에 대한 포인터입니다. 자세한 내용은 [IPictureDisp를](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) 참조하십시오.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

[CStockPropImpl::put_Picture와](#put_picture)동일하지만 참조 수가 있습니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[IDispatchImpl 클래스](../../atl/reference/idispatchimpl-class.md)
