---
title: 이벤트 싱크 맵
ms.date: 11/04/2016
helpviewer_keywords:
- event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
ms.openlocfilehash: 731ed2403aae3332e81702673d1181e9e52399a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365726"
---
# <a name="event-sink-maps"></a>이벤트 싱크 맵

포함된 OLE 컨트롤이 이벤트를 발생시면 컨트롤의 컨테이너는 MFC에서 제공하는 "이벤트 싱크 맵"이라는 메커니즘을 사용하여 이벤트를 수신합니다. 이 이벤트 싱크 맵은 각 특정 이벤트에 대한 처리기 함수와 해당 이벤트의 매개 변수를 지정합니다. 이벤트 싱크 맵에 대한 자세한 내용은 [ActiveX 제어 컨테이너](../../mfc/activex-control-containers.md)문서를 참조하십시오.

### <a name="event-sink-maps"></a>이벤트 싱크 맵

|||
|-|-|
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|이벤트 싱크 맵의 정의를 시작합니다.|
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|이벤트 싱크 맵을 선언합니다.|
|[END_EVENTSINK_MAP](#end_eventsink_map)|이벤트 싱크 맵의 정의를 종료합니다.|
|[ON_EVENT](#on_event)|특정 이벤트에 대한 이벤트 처리기를 정의합니다.|
|[ON_EVENT_RANGE](#on_event_range)|OLE 컨트롤 집합에서 발생 된 특정 이벤트에 대 한 이벤트 처리기를 정의 합니다.|
|[ON_EVENT_REFLECT](#on_event_reflect)|컨트롤의 컨테이너에서 처리하기 전에 컨트롤에 의해 발생한 이벤트를 수신합니다.|
|[ON_PROPNOTIFY](#on_propnotify)|OLE 컨트롤에서 속성 알림을 처리하기 위한 처리기를 정의합니다.|
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|OLE 컨트롤 집합에서 속성 알림을 처리하기 위한 처리기를 정의합니다.|
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|컨트롤의 컨테이너에서 처리하기 전에 컨트롤에서 보낸 속성 알림을 받습니다.|

## <a name="begin_eventsink_map"></a><a name="begin_eventsink_map"></a>BEGIN_EVENTSINK_MAP

이벤트 싱크 맵의 정의를 시작합니다.

```
BEGIN_EVENTSINK_MAP(theClass, baseClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이벤트 싱크 맵이 있는 컨트롤 클래스의 이름을 지정합니다.

*베이스 클래스*<br/>
의 기본 클래스의 이름을 *지정합니다Class*.

### <a name="remarks"></a>설명

클래스의 멤버 함수를 정의하는 구현(.cpp) 파일에서 BEGIN_EVENTSINK_MAP 매크로로 이벤트 싱크 맵을 시작한 다음 알림을 받을 각 이벤트에 대한 매크로 항목을 추가하고 END_EVENTSINK_MAP 매크로로 이벤트 싱크 맵을 완료합니다.

이벤트 싱크 맵 및 OLE 제어 컨테이너에 대한 자세한 내용은 [ActiveX 제어 컨테이너](../../mfc/activex-control-containers.md)문서를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="declare_eventsink_map"></a><a name="declare_eventsink_map"></a>DECLARE_EVENTSINK_MAP

OLE 컨테이너는 이벤트 싱크 맵을 제공하여 컨테이너에 통보되는 이벤트를 지정할 수 있습니다.

```
DECLARE_EVENTSINK_MAP()
```

### <a name="remarks"></a>설명

클래스 선언의 끝에 DECLARE_EVENTSINK_MAP 매크로를 사용합니다. 그런 다음 에서 . 클래스에 대 한 멤버 함수를 정의 하는 CPP 파일, BEGIN_EVENTSINK_MAP 매크로, 각 이벤트에 대 한 매크로 항목을 사용 하 여 알림을 받을, 그리고 END_EVENTSINK_MAP 매크로 이벤트 싱크 목록의 끝을 선언 합니다.

이벤트 싱크 맵에 대한 자세한 내용은 [ActiveX 제어 컨테이너](../../mfc/activex-control-containers.md)문서를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="end_eventsink_map"></a><a name="end_eventsink_map"></a>END_EVENTSINK_MAP

이벤트 싱크 맵의 정의를 종료합니다.

```
END_EVENTSINK_MAP()
```

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="on_event"></a><a name="on_event"></a>ON_EVENT

ON_EVENT 매크로를 사용하여 OLE 컨트롤에서 발생되는 이벤트에 대한 이벤트 처리기 함수를 정의합니다.

```
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵이 속한 클래스입니다.

*id*<br/>
OLE 컨트롤의 제어 ID입니다.

*디스피드 (것)들*<br/>
컨트롤에서 발생 하는 이벤트의 디스패치 ID입니다.

*pfnHandler*<br/>
이벤트를 처리하는 멤버 함수에 대한 포인터입니다. 이 함수에는 BOOL 반환 형식과 이벤트의 매개 변수와 일치하는 매개 변수 유형이 있어야 *합니다(vtsParams*참조). 함수는 TRUE를 반환하여 이벤트가 처리되었음을 나타내야 합니다. 그렇지 않으면 거짓.

*vtsParams*<br/>
이벤트에 대한 매개 변수 의 형식을 지정하는 **VTS_** 상수 시퀀스입니다. 이러한 상수는 DISP_FUNCTION 디스패치 맵 항목에 사용되는 상수입니다.

### <a name="remarks"></a>설명

*vtsParams* 인수는 **VTS_** 상수에서 값의 공간으로 구분된 목록입니다. 쉼표가 아닌 공백으로 구분된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

짧은 정수 뒤에 BOOL이 포함된 목록을 지정합니다.

**VTS_** 상수 목록은 [EVENT_CUSTOM](event-maps.md#event_custom)를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="on_event_range"></a><a name="on_event_range"></a>ON_EVENT_RANGE

ON_EVENT_RANGE 매크로를 사용하여 연속범위 의 ID 를 갖는 모든 OLE 컨트롤에서 발생되는 이벤트에 대한 이벤트 처리기 함수를 정의합니다.

```
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵이 속한 클래스입니다.

*idFirst*<br/>
범위에서 첫 번째 OLE 컨트롤의 제어 ID입니다.

*idLast*<br/>
범위에서 마지막 OLE 컨트롤의 제어 ID입니다.

*디스피드 (것)들*<br/>
컨트롤에서 발생 하는 이벤트의 디스패치 ID입니다.

*pfnHandler*<br/>
이벤트를 처리하는 멤버 함수에 대한 포인터입니다. 이 함수에는 BOOL 반환 형식, UINT 형식의 첫 번째 매개 변수(제어 ID)와 이벤트의 매개 변수와 일치하는 추가 매개 변수 형식이 있어야 *합니다(vtsParams*참조). 함수는 TRUE를 반환하여 이벤트가 처리되었음을 나타내야 합니다. 그렇지 않으면 거짓.

*vtsParams*<br/>
이벤트에 대한 매개 변수 의 형식을 지정하는 **VTS_** 상수 시퀀스입니다. 첫 번째 상수는 컨트롤 ID에 대해 VTS_I4 형식이어야 합니다. 이러한 상수는 DISP_FUNCTION 디스패치 맵 항목에 사용되는 상수입니다.

### <a name="remarks"></a>설명

*vtsParams* 인수는 **VTS_** 상수에서 값의 공간으로 구분된 목록입니다. 쉼표가 아닌 공백으로 구분된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

짧은 정수 뒤에 BOOL이 포함된 목록을 지정합니다.

**VTS_** 상수 목록은 [EVENT_CUSTOM](event-maps.md#event_custom)를 참조하십시오.

### <a name="example"></a>예제

다음 예제에서는 세 가지 컨트롤에 대해 구현된 MouseDown 이벤트에 대해 이벤트 처리기(IDC_MYCTRL1~IDC_MYCTRL3)를 보여 줍니다. 이벤트 처리기 `OnRangeMouseDown`함수는 대화 상자 클래스()의 `CMyDlg`헤더 파일에 다음과 같이 선언됩니다.

[!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]

아래 코드는 대화 상자 클래스의 구현 파일에 정의되어 있습니다.

[!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="on_event_reflect"></a><a name="on_event_reflect"></a>ON_EVENT_REFLECT

ON_EVENT_REFLECT 매크로는 OLE 컨트롤의 래퍼 클래스의 이벤트 싱크 맵에 사용될 때 컨트롤의 컨테이너에서 처리되기 전에 컨트롤에 의해 발생된 이벤트를 수신합니다.

```
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵이 속한 클래스입니다.

*디스피드 (것)들*<br/>
컨트롤에서 발생 하는 이벤트의 디스패치 ID입니다.

*pfnHandler*<br/>
이벤트를 처리하는 멤버 함수에 대한 포인터입니다. 이 함수에는 이벤트의 매개 변수와 일치하는 BOOL 반환 형식 및 매개 변수 형식이 있어야 *합니다(vtsParams*참조). 함수는 TRUE를 반환하여 이벤트가 처리되었음을 나타내야 합니다. 그렇지 않으면 거짓.

*vtsParams*<br/>
이벤트에 대한 매개 변수 의 형식을 지정하는 **VTS_** 상수 시퀀스입니다. 이러한 상수는 DISP_FUNCTION 디스패치 맵 항목에 사용되는 상수입니다.

### <a name="remarks"></a>설명

*vtsParams* 인수는 **VTS_** 상수에서 값의 공간으로 구분된 목록입니다.

쉼표가 아닌 공백으로 구분된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

짧은 정수 뒤에 BOOL이 포함된 목록을 지정합니다.

**VTS_** 상수 목록은 [EVENT_CUSTOM](event-maps.md#event_custom)를 참조하십시오.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="on_propnotify"></a><a name="on_propnotify"></a>ON_PROPNOTIFY

ON_PROPNOTIFY 매크로를 사용하여 OLE 컨트롤에서 속성 알림을 처리하기 위한 이벤트 싱크 맵 항목을 정의합니다.

```
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵이 속한 클래스입니다.

*id*<br/>
OLE 컨트롤의 제어 ID입니다.

*디스피드 (것)들*<br/>
알림에 관련된 속성의 디스패치 ID입니다.

*pfnRequest*<br/>
이 속성에 대 한 `OnRequestEdit` 알림을 처리 하는 멤버 함수에 대 한 포인터입니다. 이 함수에는 BOOL 반환 형식과 **BOOL** <strong>\*</strong> 매개 변수가 있어야 합니다. 이 함수는 속성이 변경될 수 있도록 매개 변수를 TRUE로 설정하고 FALSE를 허용하지 않도록 해야 합니다. 함수는 TRUE를 반환하여 알림이 처리되었음을 나타내야 합니다. 그렇지 않으면 거짓.

*pfn변경*<br/>
이 속성에 대 한 `OnChanged` 알림을 처리 하는 멤버 함수에 대 한 포인터입니다. 함수에는 BOOL 반환 형식과 UINT 매개 변수가 있어야 합니다. 함수는 TRUE를 반환하여 알림이 처리되었음을 나타내야 합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

*vtsParams* 인수는 **VTS_** 상수에서 값의 공간으로 구분된 목록입니다. 쉼표가 아닌 공백으로 구분된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

짧은 정수 뒤에 BOOL이 포함된 목록을 지정합니다.

**VTS_** 상수 목록은 [EVENT_CUSTOM](event-maps.md#event_custom)를 참조하십시오.

## <a name="on_propnotify_range"></a><a name="on_propnotify_range"></a>ON_PROPNOTIFY_RANGE

ON_PROPNOTIFY_RANGE 매크로를 사용하여 연속범위 의 ID를 갖는 모든 OLE 컨트롤에서 속성 알림을 처리하기 위한 이벤트 싱크 맵 항목을 정의합니다.

```

ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵이 속한 클래스입니다.

*idFirst*<br/>
범위에서 첫 번째 OLE 컨트롤의 제어 ID입니다.

*idLast*<br/>
범위에서 마지막 OLE 컨트롤의 제어 ID입니다.

*디스피드 (것)들*<br/>
알림에 관련된 속성의 디스패치 ID입니다.

*pfnRequest*<br/>
이 속성에 대 한 `OnRequestEdit` 알림을 처리 하는 멤버 함수에 대 한 포인터입니다. 이 함수에는 `BOOL` 반환 형식 `UINT` `BOOL*` 및 매개 변수가 있어야 합니다. 함수는 속성이 변경될 수 있도록 매개 변수를 TRUE로 설정하고 FALSE를 허용하지 않도록 해야 합니다. 함수는 TRUE를 반환하여 알림이 처리되었음을 나타내야 합니다. 그렇지 않으면 거짓.

*pfn변경*<br/>
이 속성에 대 한 `OnChanged` 알림을 처리 하는 멤버 함수에 대 한 포인터입니다. 함수에는 `BOOL` 반환 형식과 매개 `UINT` 변수가 있어야 합니다. 함수는 TRUE를 반환하여 알림이 처리되었음을 나타내야 합니다. 그렇지 않으면 거짓.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="on_propnotify_reflect"></a><a name="on_propnotify_reflect"></a>ON_PROPNOTIFY_REFLECT

ON_PROPNOTIFY_REFLECT 매크로는 OLE 컨트롤의 래퍼 클래스의 이벤트 싱크 맵에 사용될 때 컨트롤의 컨테이너에서 처리되기 전에 컨트롤에서 보낸 속성 알림을 받습니다.

```

ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
이 이벤트 싱크 맵이 속한 클래스입니다.

*디스피드 (것)들*<br/>
알림에 관련된 속성의 디스패치 ID입니다.

*pfnRequest*<br/>
이 속성에 대 한 `OnRequestEdit` 알림을 처리 하는 멤버 함수에 대 한 포인터입니다. 이 함수에는 BOOL 반환 형식과 **BOOL** <strong>\*</strong> 매개 변수가 있어야 합니다. 이 함수는 속성이 변경될 수 있도록 매개 변수를 TRUE로 설정하고 FALSE를 허용하지 않도록 해야 합니다. 함수는 TRUE를 반환하여 알림이 처리되었음을 나타내야 합니다. 그렇지 않으면 거짓.

*pfn변경*<br/>
이 속성에 대 한 `OnChanged` 알림을 처리 하는 멤버 함수에 대 한 포인터입니다. 함수에는 BOOL 반환 형식과 매개 변수가 없어야 합니다. 함수는 TRUE를 반환하여 알림이 처리되었음을 나타내야 합니다. 그렇지 않으면 거짓.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
