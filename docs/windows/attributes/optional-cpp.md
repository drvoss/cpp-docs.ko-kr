---
title: optional (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.optional
helpviewer_keywords:
- optional attribute
ms.assetid: 86656a66-8e11-4589-8e30-9b0f34eeed03
ms.openlocfilehash: 31e2dbac988cdbac8aca2d01a70177825d764a5b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842171"
---
# <a name="optional-c"></a>optional(C++)

멤버 함수에 대 한 선택적 매개 변수를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[optional]
```

## <a name="remarks"></a>설명

**선택적** c + + 특성에는 [선택적](/windows/win32/Midl/optional) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

다음 코드에서는 **옵션** 을 사용할 수 있는 방법을 보여 줍니다.

```cpp
// cpp_attr_ref_optional.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl : IDispatch
{
   [id(1)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>요구 사항

| 특성 컨텍스트 | 값 |
|-|-|
|**적용 대상**|인터페이스 매개 변수|
|**불가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)
