---
title: DHTML 이벤트 맵
ms.date: 11/04/2016
f1_keywords:
- vc.macros.shared
helpviewer_keywords:
- event map macros [MFC]
- DHTML [MFC], event map macros
- macros [MFC], DHTML event map
- DHTML events [MFC], event map
- DHTML events [MFC]
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
ms.openlocfilehash: 30c755b2901374cffab3ce91d0683811ef6624b6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365802"
---
# <a name="dhtml-event-maps"></a>DHTML 이벤트 맵

다음 매크로를 사용하여 DHTML 이벤트를 처리할 수 있습니다.

## <a name="dhtml-event-map-macros"></a>DHTML 이벤트 맵 매크로

다음 매크로는 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-derived 클래스에서 DHTML 이벤트를 처리하는 데 사용할 수 있습니다.

|||
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|DHTML 이벤트 맵의 시작을 표시합니다.|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|DHTML 이벤트 맵의 시작을 표시합니다.|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|DHTML 이벤트 맵을 선언합니다.|
|[DHTML_EVENT](#dhtml_event)|단일 HTML 요소에 대한 문서 수준에서 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|ActiveX 컨트롤에 의해 발생한 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|특정 CSS 클래스가 있는 모든 HTML 요소에 대해 문서 수준에서 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|요소 수준에서 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|HTML 요소에서 `onafterupdate` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|HTML 요소에서 `onbeforeupdate` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|HTML 요소에서 `onblur` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|HTML 요소에서 `onchange` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|HTML 요소에서 `onclick` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|HTML 요소에서 `ondataavailable` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|HTML 요소에서 `ondatasetchanged` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|HTML 요소에서 `ondatasetcomplete` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|HTML 요소에서 `ondblclick` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|HTML 요소에서 `ondragstart` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|HTML 요소에서 `onerrorupdate` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|HTML 요소에서 `onfilterchange` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|HTML 요소에서 `onfocus` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|HTML 요소에서 `onhelp` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|HTML 요소에서 `onkeydown` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|HTML 요소에서 `onkeypress` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|HTML 요소에서 `onkeyup` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|HTML 요소에서 `onmousedown` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|HTML 요소에서 `onmousemove` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|HTML 요소에서 `onmouseout` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|HTML 요소에서 `onmouseover` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|HTML 요소에서 `onmouseup` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|HTML 요소에서 `onresize` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|HTML 요소에서 `onrowenter` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|HTML 요소에서 `onrowexit` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|HTML 요소에서 `onselectstart` 이벤트를 처리하는 데 사용됩니다.|
|[DHTML_EVENT_TAG](#dhtml_event_tag)|특정 HTML 태그가 있는 모든 요소에 대해 문서 수준에서 이벤트를 처리하는 데 사용됩니다.|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|DHTML 이벤트 맵의 끝을 표시합니다.|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|DHTML 이벤트 맵의 끝을 표시합니다. |

## <a name="url-event-map-macros"></a>URL 이벤트 맵 매크로

다음 매크로는 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-파생 클래스에서 DHTML 이벤트를 처리하는 데 사용할 수 있습니다.

|||
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|다중 페이지 DHTML 및 URL 이벤트 맵의 시작을 표시합니다.|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|포함된 DHTML 이벤트 맵의 시작을 표시합니다.|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|URL 이벤트 항목 맵의 시작을 표시합니다.|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|다중 페이지 DHTML 및 URL 이벤트 맵을 선언합니다.|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|다중 페이지 DHTML 및 URL 이벤트 맵의 끝을 표시합니다.|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|포함된 DHTML 이벤트 맵의 끝을 표시합니다.|
|[END_URL_ENTRIES](#end_url_entries)|URL 이벤트 항목 맵의 끝을 표시합니다.|
|[URL_EVENT_ENTRY](#url_event_entry)|여러 페이지 대화 상자의 페이지에 URL 또는 HTML 리소스를 매핑합니다.|

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="begin_dhtml_event_map"></a><a name="begin_dhtml_event_map"></a>BEGIN_DHTML_EVENT_MAP

`className`에서 식별된 클래스의 소스 파일에 배치할 때 DHTML 이벤트 맵의 시작을 표시합니다.

```cpp
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>매개 변수

*Classname*<br/>
DHTML 이벤트 맵을 포함하는 클래스의 이름입니다. 이 클래스는 [CDHtmlDialog에서](../../mfc/reference/cdhtmldialog-class.md) 직접 또는 간접적으로 파생되어야 하며 클래스 정의 내에 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 매크로를 포함해야 합니다.

### <a name="remarks"></a>설명

클래스에 DHTML 이벤트 맵을 추가하여 `CDHtmlDialog` HTML 요소또는 웹 페이지의 ActiveX 컨트롤에서 발생되는 이벤트를 클래스의 처리기 함수로 라우팅하는 데 사용할 수 있는 정보를 제공합니다.

클래스의 구현(.cpp) 파일에 BEGIN_DHTML_EVENT_MAP 매크로를 배치하고 클래스가 처리할 이벤트(예: 마우스 오버 이벤트의 경우 DHTML_EVENT_ONMOUSEOVER)에 대한 DHTML_EVENT 매크로를 배치합니다. [END_DHTML_EVENT_MAP](#end_dhtml_event_map) 매크로를 사용하여 이벤트 맵의 끝을 표시합니다. 이러한 매크로는 다음 기능을 구현합니다.

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="begin_dhtml_event_map_inline"></a><a name="begin_dhtml_event_map_inline"></a>BEGIN_DHTML_EVENT_MAP_INLINE

*클래스 Name에*대 한 클래스 정의 내에서 DHTML 이벤트 맵의 시작 부분을 표시 합니다.

```cpp
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>매개 변수

*Classname*<br/>
DHTML 이벤트 맵을 포함하는 클래스의 이름입니다. 이 클래스는 [CDHtmlDialog에서](../../mfc/reference/cdhtmldialog-class.md) 직접 또는 간접적으로 파생되어야 하며 클래스 정의 내에 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 매크로를 포함해야 합니다.

### <a name="remarks"></a>설명

클래스에 DHTML 이벤트 맵을 추가하여 `CDHtmlDialog` HTML 요소또는 웹 페이지의 ActiveX 컨트롤에서 발생되는 이벤트를 클래스의 처리기 함수로 라우팅하는 데 사용할 수 있는 정보를 제공합니다.

클래스의 정의(.h) 파일에 BEGIN_DHTML_EVENT_MAP 매크로를 배치하고 클래스가 처리할 이벤트에 대한 DHTML_EVENT 매크로를 배치합니다(예: 마우스오버 이벤트의 경우 DHTML_EVENT_ONMOUSEOVER). [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline) 매크로를 사용하여 이벤트 맵의 끝을 표시합니다. 이러한 매크로는 다음 기능을 구현합니다.

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="declare_dhtml_event_map"></a><a name="declare_dhtml_event_map"></a>DECLARE_DHTML_EVENT_MAP

클래스 정의에서 DHTML 이벤트 맵을 선언합니다.

```cpp
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>설명

이 매크로는 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-derived 클래스의 정의에 사용됩니다.

[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) 또는 [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) 사용하여 맵을 구현합니다.

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 다음 함수를 선언합니다.

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event"></a><a name="dhtml_event"></a>DHTML_EVENT

문서 수준에서 *elemName로*식별된 HTML 요소에서 시작된 *dispid로* 식별된 이벤트를 처리합니다.

```cpp
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>매개 변수

*디스피드 (것)들*<br/>
처리할 이벤트의 DISPID입니다.

*엘렘 네임*<br/>
HTML 요소의 ID를 보유 하는 LPCWSTR 이벤트를 소싱 또는 NULL 문서 이벤트를 처리 합니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_axcontrol"></a><a name="dhtml_event_axcontrol"></a>DHTML_EVENT_AXCONTROL

*controlName.* *dispid*

```cpp
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>매개 변수

*디스피드 (것)들*<br/>
처리할 이벤트의 디스패치 ID입니다.

*컨트롤 이름*<br/>
이벤트를 발생 하는 컨트롤의 HTML ID를 들고 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_class"></a><a name="dhtml_event_class"></a>DHTML_EVENT_CLASS

처리 (문서 수준에서) *elemName로*식별 된 CSS 클래스와 모든 HTML 요소에 의해 시작 된 *dispid에* 의해 식별 된 이벤트 .

```cpp
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>매개 변수

*디스피드 (것)들*<br/>
처리할 이벤트의 디스패치 ID입니다.

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 CSS 클래스를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_element"></a><a name="dhtml_event_element"></a>DHTML_EVENT_ELEMENT

처리 *(elemName에*의해 식별 된 요소) *dispid에*의해 식별 된 이벤트 .

```cpp
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>매개 변수

*디스피드 (것)들*<br/>
처리할 이벤트의 디스패치 ID입니다.

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

이 매크로가 버블링되지 않는 이벤트를 처리하는 데 사용되는 경우 이벤트의 소스는 *elemName*로 식별된 요소입니다.

이 매크로가 버블링 이벤트를 처리하는 데 사용되는 경우 *elemName로* 식별된 요소가 이벤트의 원본이 아닐 수 있습니다(원본은 *elemName에*포함된 모든 요소일 수 있음).

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onafterupdate"></a><a name="dhtml_event_onafterupdate"></a>DHTML_EVENT_ONAFTERUPDATE

*elemName*로 식별된 `onafterupdate` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a>DHTML_EVENT_ONBEFOREUPDATE

*elemName*로 식별된 `onbeforeupdate` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onblur"></a><a name="dhtml_event_onblur"></a>DHTML_EVENT_ONBLUR

(요소 수준에서) 이벤트를 처리합니다. `onblur` 이 이벤트는 버블링되지 않습니다.

```cpp
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onchange"></a><a name="dhtml_event_onchange"></a>DHTML_EVENT_ONCHANGE

(요소 수준에서) 이벤트를 처리합니다. `onchange` 이 이벤트는 버블링되지 않습니다.

```cpp
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onclick"></a><a name="dhtml_event_onclick"></a>DHTML_EVENT_ONCLICK

*elemName*로 식별된 `onclick` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_ondataavailable"></a><a name="dhtml_event_ondataavailable"></a>DHTML_EVENT_ONDATAAVAILABLE

*elemName*로 식별된 `ondataavailable` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_ondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a>DHTML_EVENT_ONDATASETCHANGED

*elemName*로 식별된 `ondatasetchanged` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_ondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a>DHTML_EVENT_ONDATASETCOMPLETE

문서 수준에서 `ondatasetcomplete` 에서 식별된 `elemName`HTML 요소에서 시작된 이벤트를 처리합니다.

```cpp
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_ondblclick"></a><a name="dhtml_event_ondblclick"></a>DHTML_EVENT_ONDBLCLICK

*elemName*로 식별된 `ondblclick` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_ondragstart"></a><a name="dhtml_event_ondragstart"></a>DHTML_EVENT_ONDRAGSTART

*elemName*로 식별된 `ondragstart` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a>DHTML_EVENT_ONERRORUPDATE

*elemName*로 식별된 `onerrorupdate` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onfilterchange"></a><a name="dhtml_event_onfilterchange"></a>DHTML_EVENT_ONFILTERCHANGE

*elemName*로 식별된 `onfilterchange` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onfocus"></a><a name="dhtml_event_onfocus"></a>DHTML_EVENT_ONFOCUS

(요소 수준에서) 이벤트를 처리합니다. `onfocus` 이 이벤트는 버블링되지 않습니다.

```cpp
DHTML_EVENT_ONFOCUS(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onhelp"></a><a name="dhtml_event_onhelp"></a>DHTML_EVENT_ONHELP

*elemName*로 식별된 `onhelp` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONHELP(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onkeydown"></a><a name="dhtml_event_onkeydown"></a>DHTML_EVENT_ONKEYDOWN

*elemName*로 식별된 `onkeydown` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onkeypress"></a><a name="dhtml_event_onkeypress"></a>DHTML_EVENT_ONKEYPRESS

*elemName*로 식별된 `onkeypress` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onkeyup"></a><a name="dhtml_event_onkeyup"></a>DHTML_EVENT_ONKEYUP

*elemName*로 식별된 `onkeyup` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONKEYUP(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onmousedown"></a><a name="dhtml_event_onmousedown"></a>DHTML_EVENT_ONMOUSEDOWN

*elemName*로 식별된 `onmousedown` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onmousemove"></a><a name="dhtml_event_onmousemove"></a>DHTML_EVENT_ONMOUSEMOVE

*elemName*로 식별된 `onmousemove` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onmouseout"></a><a name="dhtml_event_onmouseout"></a>DHTML_EVENT_ONMOUSEOUT

*elemName*로 식별된 `onmouseout` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onmouseover"></a><a name="dhtml_event_onmouseover"></a>DHTML_EVENT_ONMOUSEOVER

*elemName*로 식별된 `onmouseover` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onmouseup"></a><a name="dhtml_event_onmouseup"></a>DHTML_EVENT_ONMOUSEUP

*elemName*로 식별된 `onmouseup` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onresize"></a><a name="dhtml_event_onresize"></a>DHTML_EVENT_ONRESIZE

(요소 수준에서) 이벤트를 처리합니다. `onresize` 이 이벤트는 버블링되지 않습니다.

```cpp
DHTML_EVENT_ONRESIZE(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onrowenter"></a><a name="dhtml_event_onrowenter"></a>DHTML_EVENT_ONROWENTER

*elemName*로 식별된 `onrowenter` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONROWENTER(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onrowexit"></a><a name="dhtml_event_onrowexit"></a>DHTML_EVENT_ONROWEXIT

*elemName*로 식별된 `onrowexit` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_onselectstart"></a><a name="dhtml_event_onselectstart"></a>DHTML_EVENT_ONSELECTSTART

*elemName*로 식별된 `onselectstart` HTML 요소에서 시작된 이벤트를 문서 수준에서 처리합니다.

```cpp
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)
```

### <a name="parameters"></a>매개 변수

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 ID를 보유한 LPCWSTR입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="dhtml_event_tag"></a><a name="dhtml_event_tag"></a>DHTML_EVENT_TAG

*elemName로*식별된 HTML 태그가 `dispid` 있는 HTML 요소에서 시작된 이벤트(문서 수준에서)를 처리합니다.

```cpp
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>매개 변수

*디스피드 (것)들*<br/>
처리할 이벤트의 디스패치 ID입니다.

*엘렘 네임*<br/>
이벤트를 소싱하는 HTML 요소의 HTML 태그입니다.

*멤버Fxn*<br/>
이벤트에 대 한 처리기 함수입니다.

### <a name="remarks"></a>설명

이 매크로를 사용하여 클래스의 [DHTML 이벤트 맵에](#begin_dhtml_event_map_inline) 항목을 추가합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="end_dhtml_event_map"></a><a name="end_dhtml_event_map"></a>END_DHTML_EVENT_MAP

DHTML 이벤트 맵의 끝을 표시합니다.

```cpp
END_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>설명

[BEGIN_DHTML_EVENT_MAP.](#begin_dhtml_event_map)

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="begin_dhtml_url_event_map"></a><a name="begin_dhtml_url_event_map"></a>BEGIN_DHTML_URL_EVENT_MAP

다중 페이지 대화 상자에서 DHTML 및 URL 이벤트 맵의 정의를 시작합니다.

```cpp
BEGIN_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>설명

[CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-파생 클래스의 구현 파일에 BEGIN_DHTML_URL_EVENT_MAP 넣습니다. [포함된 DHTML 이벤트 맵](#begin_embed_dhtml_event_map) 및 URL [항목으로](#begin_url_entries)팔로우한 다음 [END_DHTML_URL_EVENT_MAP.](#end_dhtml_url_event_map) 클래스 정의 내에서 [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) 매크로를 포함합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="begin_embed_dhtml_event_map"></a><a name="begin_embed_dhtml_event_map"></a>BEGIN_EMBED_DHTML_EVENT_MAP

다중 페이지 대화 상자에서 포함된 DHTML 이벤트 맵의 정의를 시작합니다.

```cpp
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)
```

### <a name="parameters"></a>매개 변수

*Classname*<br/>
이벤트 맵을 포함하는 클래스의 이름입니다. 이 클래스는 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)에서 직접 또는 간접적으로 파생되어야 합니다. 포함된 DHTML 이벤트 맵은 [DHTML 및 URL 이벤트 맵](#begin_dhtml_url_event_map)내에 있어야 합니다.

*mapName*<br/>
이벤트 맵이 있는 페이지를 지정합니다. 이는 실제로 URL 또는 HTML 리소스를 정의하는 [URL_EVENT_ENTRY](#url_event_entry) 매크로의 *mapName과* 일치합니다.

### <a name="remarks"></a>설명

다중 페이지 DHTML 대화 상자는 DHTML 이벤트를 발생시킬 수 있는 여러 HTML 페이지로 구성되므로 포함된 이벤트 맵은 페이지를 페이지별로 처리기에 매핑하는 데 사용됩니다.

DHTML 및 URL 이벤트 맵 내에 포함된 이벤트 맵은 BEGIN_EMBED_DHTML_EVENT_MAP 매크로와 [DHTML_EVENT](#dhtml_event) 매크로, [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) 매크로로 구성됩니다.

각 포함된 이벤트 맵에는 *맵이름(BEGIN_EMBED_DHTML_EVENT_MAP* 지정됨)을 URL 또는 HTML 리소스에 매핑하기 위한 해당 URL [이벤트 항목이](#url_event_entry) 필요합니다.

### <a name="example"></a>예제

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="begin_url_entries"></a><a name="begin_url_entries"></a>BEGIN_URL_ENTRIES

다중 페이지 대화 상자에서 URL 이벤트 항목 맵 정의를 시작합니다.

```cpp
BEGIN_URL_ENTRIES(className)
```

### <a name="parameters"></a>매개 변수

*Classname*<br/>
URL 이벤트 항목 맵을 포함하는 클래스의 이름입니다. 이 클래스는 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)에서 직접 또는 간접적으로 파생되어야 합니다. URL 이벤트 항목 맵은 [DHTML 및 URL 이벤트 맵](#begin_dhtml_url_event_map)내에 있어야 합니다.

### <a name="remarks"></a>설명

다중 페이지 DHTML 대화 상자는 여러 HTML 페이지로 구성되므로 URL 이벤트 항목은 URL 또는 HTML 리소스를 [포함된 DHTML 이벤트 맵에](#begin_embed_dhtml_event_map)매핑하는 데 사용됩니다. BEGIN_URL_ENTRIES [END_URL_ENTRIES](#end_url_entries) 매크로 사이에 URL_EVENT_ENTRY 매크로를 넣습니다.

### <a name="example"></a>예제

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="declare_dhtml_url_event_map"></a><a name="declare_dhtml_url_event_map"></a>DECLARE_DHTML_URL_EVENT_MAP

클래스 정의에서 DHTML 및 URL 이벤트 맵을 선언합니다.

```cpp
DECLARE_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>설명

이 매크로는 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-파생 클래스의 정의에 사용됩니다.

DHTML 및 URL 이벤트 맵에는 [DHTML 이벤트 맵과](#begin_embed_dhtml_event_map) [URL 이벤트 항목이](#begin_url_entries) 포함되어 DHTML 이벤트를 페이지별로 처리기에 매핑합니다. [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) 사용하여 맵을 구현합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="end_dhtml_url_event_map"></a><a name="end_dhtml_url_event_map"></a>END_DHTML_URL_EVENT_MAP

DHTML 및 URL 이벤트 맵의 끝을 표시합니다.

```cpp
END_DHTML_URL_EVENT_MAP(className)
```

### <a name="parameters"></a>매개 변수

*Classname*<br/>
이벤트 맵을 포함하는 클래스의 이름입니다. 이 클래스는 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)에서 직접 또는 간접적으로 파생되어야 합니다. 해당 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) 매크로에서 *className을* 일치시켜야 합니다.

### <a name="example"></a>예제

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="end_embed_dhtml_event_map"></a><a name="end_embed_dhtml_event_map"></a>END_EMBED_DHTML_EVENT_MAP

포함된 DHTML 이벤트 맵의 끝을 표시합니다.

```cpp
END_EMBED_DHTML_EVENT_MAP()
```

### <a name="example"></a>예제

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="end_url_entries"></a><a name="end_url_entries"></a>END_URL_ENTRIES

URL 이벤트 항목 맵의 끝을 표시합니다.

```cpp
END_URL_ENTRIES()
```

### <a name="example"></a>예제

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="url_event_entry"></a><a name="url_event_entry"></a>URL_EVENT_ENTRY

여러 페이지 대화 상자의 페이지에 URL 또는 HTML 리소스를 매핑합니다.

```cpp
URL_EVENT_ENTRY(className, url,  mapName)
```

### <a name="parameters"></a>매개 변수

*Classname*<br/>
URL 이벤트 항목 맵을 포함하는 클래스의 이름입니다. 이 클래스는 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)에서 직접 또는 간접적으로 파생되어야 합니다. URL 이벤트 항목 맵은 [DHTML 및 URL 이벤트 맵](#begin_dhtml_url_event_map)내에 있어야 합니다.

*url*<br/>
페이지의 URL 또는 HTML 리소스입니다.

*mapName*<br/>
URL이 *URL인*페이지를 지정합니다. 이 페이지에서 이벤트를 매핑 하는 [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) 매크로에서 *mapName* 일치 합니다.

### <a name="remarks"></a>설명

페이지가 HTML 리소스인 경우 *url은* 리소스ID 번호의 문자열 표현이어야 합니다(즉, "123", 123 또는 ID_HTMLRES1 아님).

페이지 식별자 인 *mapName은*포함된 DHTML 이벤트 맵을 URL 이벤트 항목 맵에 연결하는 데 사용되는 임의 기호입니다. DHTML 및 URL 이벤트 맵에 대한 범위가 제한됩니다.

### <a name="example"></a>예제

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>요구 사항

  **헤더** afxdhtml.h

## <a name="end_dhtml_event_map_inline"></a><a name="end_dhtml_event_map_inline"></a>END_DHTML_EVENT_MAP_INLINE

DHTML 이벤트 맵의 끝을 표시합니다.

### <a name="syntax"></a>구문

```cpp
END_DHTML_EVENT_MAP_INLINE( )
```

### <a name="remarks"></a>설명

[BEGIN_DHTML_EVENT_MAP_INLINE.](#begin_dhtml_event_map_inline)

### <a name="requirements"></a>요구 사항

**헤더:** afxdhtml.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](mfc-macros-and-globals.md)
