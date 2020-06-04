---
title: length_is (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.length_is
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
ms.openlocfilehash: 2f252206f6e364b1a87ee3b7b88b14d0ea19bacb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214788"
---
# <a name="length_is"></a>length_is

전송할 배열 요소의 수를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ length_is("expression") ]
```

### <a name="parameters"></a>매개 변수

*expression*<br/>
하나 이상의 C 언어 식입니다. 빈 인수 슬롯을 사용할 수 있습니다.

## <a name="remarks"></a>주의

**Length_is** C++ 특성에는 [length_is](/windows/win32/Midl/length-is) MIDL 특성과 동일한 기능이 있습니다.

## <a name="example"></a>예제

배열의 섹션을 지정 하는 방법에 대 한 예제는 [first_is](first-is.md) 를 참조 하세요.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**구조체** 또는 **공용 구조체**의 필드, 인터페이스 매개 변수, 인터페이스 메서드|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[IDL 특성](idl-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[max_is](max-is.md)<br/>
[last_is](last-is.md)<br/>
[size_is](size-is.md)
