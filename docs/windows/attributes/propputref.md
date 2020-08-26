---
title: propputref (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propputref
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
ms.openlocfilehash: dbb5d5966fc82f69be0ed7d2fa0a66ad558a7915
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839909"
---
# <a name="propputref"></a>propputref

값 대신 참조를 사용 하는 속성 설정 함수를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[propputref]
```

## <a name="remarks"></a>설명

**Propputref** c + + 특성에는 [propputref](/windows/win32/Midl/propputref) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

**Propputref**의 샘플 사용에 대 한 [바인딩](bindable.md) 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

| 특성 컨텍스트 | 값 |
|-|-|
|**적용 대상**|메서드|
|**불가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|`propget`, `propput`|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propput](propput.md)
