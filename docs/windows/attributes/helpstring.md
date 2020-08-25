---
title: helpstring (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstring
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
ms.openlocfilehash: 57f7a5bfd5bd0e7a6509797ec34e88531304ec92
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831036"
---
# <a name="helpstring"></a>helpstring

적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.

## <a name="syntax"></a>구문

```cpp
[ helpstring("string") ]
```

### <a name="parameters"></a>매개 변수

*string*<br/>
도움말 문자열의 텍스트입니다.

## <a name="remarks"></a>설명

**Helpstring** c + + 특성에는 [helpstring](/windows/win32/Midl/helpstring) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

**Helpstring**를 사용 하는 방법에 대 한 예제는 [defaultvalue](defaultvalue.md) 의 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

| 특성 컨텍스트 | 값 |
|-|-|
|**적용 대상**|**인터페이스**, **`typedef`** , **`class`** , 메서드, 속성|
|**불가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpcontext](helpcontext.md)
