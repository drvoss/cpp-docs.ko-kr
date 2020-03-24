---
title: propget (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propget
helpviewer_keywords:
- propget attribute
ms.assetid: c9d4a97f-36dd-4b61-8eb0-b1a217598f14
ms.openlocfilehash: d2c0ebab1630634ddd4fc81e7c9c8364f7fad46f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166461"
---
# <a name="propget"></a>propget

속성 접근자 함수를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[propget]
```

## <a name="remarks"></a>설명

**Propget** C++ 특성은 [propget](/windows/win32/Midl/propget) MIDL 특성과 동일한 기능을 포함 합니다.

## <a name="example"></a>예제

**Propget**의 샘플 사용에 대 한 [바인딩](bindable.md) 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|방법|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|`propput`, `propputref`|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[propput](propput.md)<br/>
[propputref](propputref.md)
