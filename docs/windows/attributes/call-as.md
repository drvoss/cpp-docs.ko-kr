---
title: call_as (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.call_as
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
ms.openlocfilehash: 755741faec6c0ba702d372ca8dee486edcb72ef3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167338"
---
# <a name="call_as"></a>call_as

원격 함수가 호출 될 때 로컬 함수가 호출 되도록 [로컬](local-cpp.md) 함수를 원격 함수에 매핑할 수 있도록 합니다.

## <a name="syntax"></a>구문

```cpp
[ call_as(function) ]
```

### <a name="parameters"></a>매개 변수

*function*<br/>
원격 함수가 호출 될 때 호출 하려는 로컬 함수입니다.

## <a name="remarks"></a>설명

**Call_as** C++ 특성에는 [call_as](/windows/win32/Midl/call-as) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

다음 코드는 **call_as** 를 사용 하 여 원격화 할 수 없는 함수 (`f1`)를 원격 가능 함수 (`Remf1`)에 매핑하는 방법을 보여 줍니다.

```cpp
// cpp_attr_ref_call_as.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMInterface {
   [local] HRESULT f1 ( int i );
   [call_as(f1)] HRESULT Remf1 ( int i );
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|인터페이스 메서드|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|None|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[local](local-cpp.md)
