---
title: event_source (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.event_source
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
ms.openlocfilehash: bea90020c3ec570149e11db95ff6d6f8fd0a5507
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845304"
---
# <a name="event_source"></a>event_source

이벤트 소스를 만듭니다.

## <a name="syntax"></a>구문

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>매개 변수

*type*<br/>
다음 값 중 하나의 열거형:

- `native` - 관리되지 않는 C/C++ 코드용(관리되지 않는 클래스에 대한 기본값).

- `com` - COM 코드용. When를 사용 해야 합니다 `coclass` `type` = `com` . 이 값을 사용하려면 다음 헤더 파일을 포함해야 합니다.

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*optimize*<br/>
*형식이* 인 경우 `native` `optimize=size` 클래스의 모든 이벤트에 대해 4 바이트의 저장소 (최소)가 있음을 나타내거나 `optimize=speed` (기본값), 4 * (이벤트 수) 바이트의 저장소가 있음을 나타내려면를 지정할 수 있습니다.

*decorate*<br/>
*형식이* 인 경우 `native` `decorate=false` 병합 된 (. .mrg) 파일의 확장 된 이름에 바깥쪽 클래스 이름을 포함 하지 않도록 지정할 수 있습니다. [/Fx](../../build/reference/fx-merge-injected-code.md) 로는 .mrg 파일을 생성할 수 있습니다. `decorate=false`(기본값) 이면 병합 된 파일에 정규화 된 형식 이름이 생성 됩니다.

## <a name="remarks"></a>설명

**event_source** C++ 특성은, 이 특성이 적용되는 클래스 또는 구조가 이벤트 소스가 될 것임을 지정합니다.

**event_source** 는 [event_receiver](event-receiver.md) 특성 및 [__event](../../cpp/event.md) 키워드와 함께 사용됩니다. `event_receiver`를 사용 하 여 이벤트 수신기를 만듭니다. **`__event`** 이벤트 원본 내에서 메서드를 사용 하 여 해당 메서드를 이벤트로 지정 합니다.

> [!NOTE]
> 템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.

## <a name="requirements"></a>요구 사항

| 특성 컨텍스트 | 값 |
|-|-|
|**적용 대상**|**`class`**, **`struct`**|
|**불가능**|아니요|
|**필수 특성**|**coclass** 인 경우 `type`=`com`|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[컴파일러 특성](compiler-attributes.md)<br/>
[event_receiver](event-receiver.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[클래스 특성](class-attributes.md)
