---
title: size_is (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.size_is
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
ms.openlocfilehash: 36b960982d1f88cd30bab707dfe7aec73381dfab
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213842"
---
# <a name="size_is"></a>size_is

크기가 지정 된 포인터에 대해 할당 된 메모리 크기, 크기가 지정 된 포인터에 대 한 포인터 크기 및 단일 또는 다차원 배열을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ size_is("expression") ]
```

### <a name="parameters"></a>매개 변수

*expression*<br/>
크기 조정 포인터에 할당 된 메모리의 크기입니다.

## <a name="remarks"></a>설명

**Size_is** c + + 특성에는 [size_is](/windows/win32/Midl/size-is) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

배열의 섹션을 지정 하는 방법에 대 한 샘플은 [first_is](first-is.md) 의 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|또는의 **`struct`** 필드 **`union`** , 인터페이스 매개 변수, 인터페이스 메서드|
|**불가능**|예|
|**필수 특성**|없음|
|**잘못된 특성**|`max_is`|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)
