---
title: 집계 가능한C++ (COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.aggregatable
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
ms.openlocfilehash: d929543f699dcd20471ff9a9b45f54119f82a40a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168527"
---
# <a name="aggregatable"></a>aggregatable

클래스가 집계를 지원함을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
[ aggregatable(value) ]
```

### <a name="parameters"></a>매개 변수

*value*<br/>
필드 COM 개체를 집계할 수 있는 시기를 나타내는 매개 변수입니다.

- `never` COM 개체를 집계할 수 없습니다.

- COM 개체를 직접 만들거나 집계할 수 `allowed`. 이것이 기본값입니다.

- `always` COM 개체를 직접 만들 수 없으며 집계할 수도 있습니다. 이 개체에 대 한 `CoCreateInstance`를 호출 하는 경우 집계 개체의 `IUnknown` 인터페이스 (제어 `IUnknown`)를 지정 해야 합니다.

## <a name="remarks"></a>설명

**집계할** C++ 때의 특성에는 [집계할](/windows/win32/Midl/aggregatable) 때 발생 하는 MIDL 특성과 동일한 기능이 있습니다. 즉, 컴파일러가 생성 된 .idl 파일에 **집계** 된 특성을 전달 합니다.

이 특성을 사용하려면 [coclass](coclass.md), [progid](progid.md)또는 [vi_progid](vi-progid.md) 특성(또는 이 중 하나를 암시하는 다른 특성)을 동일한 요소에 적용해야 합니다. 단일 특성을 사용하는 경우 다른 두 특성도 자동으로 적용됩니다. 예를 들어 `progid` 적용 되는 경우 `vi_progid` 및 `coclass`도 적용 됩니다.

### <a name="atl-projects"></a>ATL 프로젝트

ATL을 사용하는 프로젝트 내에서 이 특성을 사용하는 경우 특성의 동작이 변경됩니다. 특성은 앞에서 설명한 동작 외에도 대상 클래스에 다음 매크로 중 하나를 추가 합니다.

|매개 변수 값|삽입 된 매크로|
|---------------------|--------------------|
|`Never`|[DECLARE_NOT_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|
|`Allowed`|[DECLARE_POLY_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|
|`Always`|[DECLARE_ONLY_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|

## <a name="example"></a>예제

```cpp
// cpp_attr_ref_aggregatable.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="MyModule")];

[ coclass, aggregatable(allowed),
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]
class CMyClass {};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**클래스**, **구조체**|
|**반복 가능**|예|
|**필수 특성**|`coclass`, `progid`또는 `vi_progid`중 하나 이상입니다.|
|**잘못된 특성**|None|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[집계](/windows/win32/com/aggregation)
