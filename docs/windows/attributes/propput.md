---
title: propput (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propput
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
ms.openlocfilehash: 8817d0042c3055b5bbf9b111e6f02b9d9a4c152c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166447"
---
# <a name="propput"></a>propput

속성 설정 함수를 지정합니다.

## <a name="syntax"></a>구문

```cpp
[propput]
```

## <a name="remarks"></a>설명

**Propput** C++ 특성은 [propput](/windows/win32/Midl/propput) MIDL 특성과 동일한 기능을 포함 합니다.

## <a name="example"></a>예제

**Propput**의 샘플 사용에 대 한 [바인딩](bindable.md) 예제를 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|방법|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|`propget`, `propputref`|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propputref](propputref.md)
