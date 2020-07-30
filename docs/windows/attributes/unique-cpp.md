---
title: unique (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.unique
helpviewer_keywords:
- unique attribute
ms.assetid: abd7ed14-5ae7-44a8-8333-0058e9c92b2f
ms.openlocfilehash: a46d607ef03fcb75fea31835726d0e2d95e71df8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87201026"
---
# <a name="unique-c"></a>unique(C++)

고유 포인터를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[unique]
```

## <a name="remarks"></a>설명

**고유한** c + + 특성에는 [고유한](/windows/win32/Midl/unique) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

**고유한**의 샘플 [사용에 대 한 참조 예제를](ref-cpp.md) 참조 하십시오.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**`typedef`**, **`struct`** , **`union`** , interface 매개 변수, interface 메서드|
|**불가능**|예|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)
