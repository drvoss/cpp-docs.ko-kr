---
title: 제한 됨C++ (COM 특성)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.restricted
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
ms.openlocfilehash: a47c56673e19f891b24ff433b9c614804f0bd51c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166369"
---
# <a name="restricted"></a>restricted

모듈, 인터페이스 또는 인터페이스의 멤버를 임의로 호출할 수 없도록 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ restricted(
   interfaces
) ]
```

### <a name="parameters"></a>매개 변수

*인터페이스로*<br/>
COM 개체에서 임의로 호출할 수 없는 하나 이상의 인터페이스입니다. 이 매개 변수는 클래스에 적용 된 경우에만 유효 합니다.

## <a name="remarks"></a>설명

**제한** C++ 된 특성에는 [제한](/windows/win32/Midl/restricted) 된 MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

다음 코드는 **제한** 된 특성을 사용 하는 방법을 보여 줍니다.

```cpp
// cpp_attr_ref_restricted.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface b
{
};

[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]
class c : public a, public b
{
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|인터페이스 메서드, **인터페이스**, **클래스**, **구조체**|
|**반복 가능**|예|
|**필수 특성**|**coclass** ( **클래스** 또는 **구조체**에 적용 된 경우)|
|**잘못된 특성**|None|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)<br/>
[메서드 특성](method-attributes.md)
