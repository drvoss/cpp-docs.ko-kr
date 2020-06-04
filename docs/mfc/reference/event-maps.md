---
title: 이벤트 맵
ms.date: 09/07/2019
helpviewer_keywords:
- event maps [MFC]
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
ms.openlocfilehash: c79d2fb1ac73947ddb13adcbd444ff7b5d50bdb4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365745"
---
# <a name="event-maps"></a>이벤트 맵

컨트롤이 컨테이너에 일부 작업(예: 키 입력, 마우스 클릭 또는 컨트롤의 상태 변경)이 발생했다는 것을 컨테이너에 알리려고 할 때마다 이벤트 발생 함수를 호출합니다. 이 함수는 관련 이벤트를 발생시켜 몇 가지 중요한 작업이 발생했음을 컨트롤 컨테이너에 보온합니다.

Microsoft 파운데이션 클래스 라이브러리는 이벤트 발생에 최적화된 프로그래밍 모델을 제공합니다. 이 모델에서 "이벤트 맵"은 특정 컨트롤에 대해 어떤 이벤트를 발생시키는지 지정하는 데 사용됩니다. 이벤트 맵에는 각 이벤트에 대해 하나의 매크로가 포함되어 있습니다. 예를 들어 스톡 Click 이벤트를 발생시키는 이벤트 맵은 다음과 같습니다.

[!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]

매크로는 `EVENT_STOCK_CLICK` 컨트롤이 마우스 클릭을 감지할 때마다 스톡 클릭 이벤트를 발생시음을 나타냅니다. 다른 주식 이벤트에 대한 자세한 목록은 [ActiveX 컨트롤: 이벤트](../../mfc/mfc-activex-controls-events.md)문서를 참조하십시오. 매크로는 사용자 지정 이벤트를 나타내는 데도 사용할 수 있습니다.

이벤트 맵 매크로도 중요하지만 일반적으로 직접 삽입하지는 않습니다. 이는 **클래스 보기의** **속성** 창이 이벤트 발생 함수를 이벤트와 연결하는 데 사용할 때 소스 파일에 이벤트 맵 항목을 자동으로 생성하기 때문입니다. 이벤트 맵 항목을 편집하거나 추가하려는 경우 언제든지 **속성** 창을 사용할 수 있습니다.

이벤트 맵을 지원하기 위해 MFC는 다음과 같은 매크로를 제공합니다.

## <a name="event-map-macros"></a>이벤트 맵 매크로

### <a name="event-map-declaration-and-demarcation"></a>이벤트 맵 선언 및 경계

|||
|-|-|
|[DECLARE_EVENT_MAP](#declare_event_map)|이벤트 맵이 클래스에서 이벤트 발생 함수에 이벤트를 매핑하는 데 사용됩니다(클래스 선언에 사용해야 합니다).|
|[BEGIN_EVENT_MAP](#begin_event_map)|이벤트 맵의 정의를 시작합니다(클래스 구현에서 사용해야 합니다).|
|[END_EVENT_MAP](#end_event_map)|이벤트 맵의 정의를 종료합니다(클래스 구현에서 사용해야 합니다).|

### <a name="event-mapping-macros"></a>이벤트 매핑 매크로

|||
|-|-|
|[EVENT_CUSTOM](#event_custom)|지정된 이벤트를 발생시킬 이벤트 발생 함수를 나타냅니다.|
|[EVENT_CUSTOM_ID](#event_custom_id)|지정된 디스패치 ID를 통해 지정된 이벤트를 발생시킬 이벤트 발생 함수를 나타냅니다.|

### <a name="message-mapping-macros"></a>메시지 매핑 매크로

|||
|-|-|
|[ON_OLEVERB](#on_oleverb)|OLE 컨트롤에서 처리하는 사용자 지정 동사를 나타냅니다.|
|[ON_STDOLEVERB](#on_stdoleverb)|OLE 컨트롤의 표준 동사 매핑을 재정의합니다.|

## <a name="declare_event_map"></a><a name="declare_event_map"></a>DECLARE_EVENT_MAP

프로그램의 `COleControl`각 파생 클래스는 컨트롤이 발사할 이벤트를 지정하는 이벤트 맵을 제공할 수 있습니다.

```cpp
DECLARE_EVENT_MAP()
```

### <a name="remarks"></a>설명

클래스 선언의 끝에 DECLARE_EVENT_MAP 매크로를 사용합니다. 그런 다음 클래스의 멤버 함수를 정의하는 .cpp 파일에서 BEGIN_EVENT_MAP 매크로, 각 컨트롤의 이벤트에 대한 매크로 항목 및 END_EVENT_MAP 매크로를 사용하여 이벤트 목록의 끝을 선언합니다.

이벤트 맵에 대한 자세한 내용은 [ActiveX 컨트롤: 이벤트](../../mfc/mfc-activex-controls-events.md)문서를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더** afxctl.h

## <a name="begin_event_map"></a><a name="begin_event_map"></a>BEGIN_EVENT_MAP

이벤트 맵의 정의를 시작합니다.

```cpp
BEGIN_EVENT_MAP(theClass,  baseClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이벤트 맵이 있는 컨트롤 클래스의 이름을 지정합니다.

*베이스 클래스*<br/>
의 기본 클래스의 이름을 *지정합니다Class*.

### <a name="remarks"></a>설명

클래스의 멤버 함수를 정의하는 구현(.cpp) 파일에서 BEGIN_EVENT_MAP 매크로로 이벤트 맵을 시작한 다음 각 이벤트에 대한 매크로 항목을 추가하고 END_EVENT_MAP 매크로로 이벤트 맵을 완료합니다.

이벤트 맵 및 BEGIN_EVENT_MAP 매크로에 대한 자세한 내용은 [ActiveX 컨트롤: 이벤트](../../mfc/mfc-activex-controls-events.md)문서를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더** afxctl.h

## <a name="end_event_map"></a><a name="end_event_map"></a>END_EVENT_MAP

END_EVENT_MAP 매크로를 사용하여 이벤트 맵의 정의를 종료합니다.

```cpp
END_EVENT_MAP()
```

### <a name="requirements"></a>요구 사항

**헤더** afxctl.h

## <a name="event_custom"></a><a name="event_custom"></a>EVENT_CUSTOM

사용자 지정 이벤트에 대한 이벤트 맵 항목을 정의합니다.

```cpp
EVENT_CUSTOM(pszName, pfnFire,  vtsParams)
```

### <a name="parameters"></a>매개 변수

*pszName*<br/>
이벤트의 이름입니다.

*pfnFire*<br/>
이벤트 발생 함수의 이름입니다.

*vtsParams*<br/>
함수의 매개 변수 목록을 지정하는 하나 이상의 상수의 공간으로 구분된 목록입니다.

### <a name="remarks"></a>설명

*vtsParams* 매개 변수는 `VTS_` 상수에서 값의 공간 분리 된 목록입니다. 쉼표가 아닌 공백으로 구분된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

RGB 색상 값을 나타내는 32비트 정수를 포함하는 목록을 지정한 다음 OLE 글꼴 개체의 인터페이스에 대한 `IFontDisp` 포인터를 지정합니다.

`VTS_` 상수와 그 의미는 다음과 같습니다.

|기호|매개 변수 형식|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**긴**|
|VTS_R4|**플 로트**|
|VTS_R8|**double**|
|VTS_COLOR|OLE_COLOR|
|VTS_CY|Currency|
|VTS_DATE|DATE|
|VTS_BSTR|**const** __\* char__|
|VTS_DISPATCH|LP디스패치|
|VTS_FONT|`IFontDispatch*`|
|VTS_HANDLE|HANDLE|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_UNKNOWN|LP알 수 없음|
|VTS_OPTEXCLUSIVE|OLE_OPTEXCLUSIVE|
|VTS_PICTURE|`IPictureDisp*`|
|VTS_TRISTATE|OLE_TRISTATE|
|VTS_XPOS_PIXELS|OLE_XPOS_PIXELS|
|VTS_YPOS_PIXELS|OLE_YPOS_PIXELS|
|VTS_XSIZE_PIXELS|OLE_XSIZE_PIXELS|
|VTS_YSIZE_PIXELS|OLE_YSIZE_PIXELS|
|TS_XPOS_HIMETRIC|OLE_XPOS_HIMETRIC|
|VTS_YPOS_HIMETRIC|OLE_YPOS_HIMETRIC|
|VTS_XSIZE_HIMETRIC|OLE_XSIZE_HIMETRIC|
|VTS_YSIZE_HIMETRIC|OLE_YSIZE_HIMETRIC|

> [!NOTE]
> 변형 데이터 상수에 대한 포인터를 제공하는 VTS_FONT 및 VTS_PICTURE 제외한 모든 변형 형식에 대해 추가 변형 상수가 정의되었습니다. 이러한 상수는 `VTS_Pconstantname` 규칙을 사용하여 명명됩니다. 예를 들어 VTS_PCOLOR VTS_COLOR 상수에 대한 포인터입니다.

### <a name="requirements"></a>요구 사항

**헤더** afxctl.h

## <a name="event_custom_id"></a><a name="event_custom_id"></a>EVENT_CUSTOM_ID

dispid에서 지정한 디스패치 ID에 속하는 사용자 지정 이벤트에 대한 이벤트 발생 *함수를 정의합니다.*

```cpp
EVENT_CUSTOM_ID(
    pszName,
    dispid,
    pfnFire,
    vtsParams)
```

### <a name="parameters"></a>매개 변수

*pszName*<br/>
이벤트의 이름입니다.

*디스피드 (것)들*<br/>
이벤트를 발생 시 컨트롤에서 사용하는 디스패치 ID입니다.

*pfnFire*<br/>
이벤트 발생 함수의 이름입니다.

*vtsParams*<br/>
이벤트가 발생될 때 컨트롤 컨테이너에 전달된 매개 변수 의 변수 목록입니다.

### <a name="remarks"></a>설명

*vtsParams* 인수는 `VTS_` 상수에서 값의 공간 분리 된 목록입니다. 쉼표가 아닌 공백으로 구분된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

RGB 색상 값을 나타내는 32비트 정수를 포함하는 목록을 지정한 다음 OLE 글꼴 개체의 인터페이스에 대한 `IFontDisp` 포인터를 지정합니다.

`VTS_` 상수 목록은 [EVENT_CUSTOM](#event_custom)를 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더** afxctl.h

## <a name="on_oleverb"></a><a name="on_oleverb"></a>ON_OLEVERB

이 매크로는 사용자 지정 동사를 컨트롤의 특정 멤버 함수에 매핑하는 메시지 맵 항목을 정의합니다.

```cpp
ON_OLEVERB(idsVerbName,  memberFxn)
```

### <a name="parameters"></a>매개 변수

*idsVerbName*<br/>
동사 이름의 문자열 리소스 ID입니다.

*멤버Fxn*<br/>
동사가 호출될 때 프레임워크에서 호출되는 함수입니다.

### <a name="remarks"></a>설명

리소스 편집기를 사용하여 문자열 테이블에 추가되는 사용자 지정 동사 이름을 만들 수 있습니다.

*memberFxn의* 함수 프로토타입은 다음과 입니다.

```cpp
BOOL memberFxn(
   LPMSG    lpMsg,
   HWND     hWndParent,
   LPCRECT  lpRect);
```

*lpMsg,* *hWndParent*및 *lpRect* 매개 변수의 값은 `IOleObject::DoVerb` 멤버 함수의 해당 매개 변수에서 가져온 값입니다.

### <a name="requirements"></a>요구 사항

**헤더** afxole.h

## <a name="on_stdoleverb"></a><a name="on_stdoleverb"></a>ON_STDOLEVERB

이 매크로를 사용하여 표준 동사의 기본 동작을 재정의합니다.

```cpp
ON_STDOLEVERB(iVerb, memberFxn)
```

### <a name="parameters"></a>매개 변수

*iVerb*<br/>
재정의된 동사에 대한 표준 동사 인덱스입니다.

*멤버Fxn*<br/>
동사가 호출될 때 프레임워크에서 호출되는 함수입니다.

### <a name="remarks"></a>설명

표준 동사 인덱스는 양식이며 `OLEIVERB_`그 다음에 동작이 있습니다. OLEIVERB_SHOW, OLEIVERB_HIDE 및 OLEIVERB_UIACTIVATE 표준 동사에 대한 몇 가지 예입니다.

*memberFxn* 매개 변수로 사용할 함수 프로토타입에 대한 설명은 [ON_OLEVERB](#on_oleverb) 참조하십시오.

### <a name="requirements"></a>요구 사항

**헤더** afxole.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
