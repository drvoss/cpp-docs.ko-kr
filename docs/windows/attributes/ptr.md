---
title: ptr (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.ptr
helpviewer_keywords:
- ptr attribute
ms.assetid: 95eaea57-a5be-45f6-a612-ba2c9bc4645a
ms.openlocfilehash: e56d4e56135c0f32a1796ac98565a990c7225705
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166421"
---
# <a name="ptr"></a>ptr

포인터를 전체 포인터로 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ptr]
```

## <a name="remarks"></a>설명

**Ptr** C++ 특성에는 [ptr](/windows/win32/Midl/ptr) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

**Ptr**의 샘플 사용에 대해서는 [defaultvalue](defaultvalue.md) 의 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|인터페이스 매개 변수, 인터페이스 메서드, **typedef**|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|None|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)
