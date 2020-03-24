---
title: no_injected_text (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: 5f98be3478b2e1eeb4b464f1784f3f4ece22d8a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166616"
---
# <a name="no_injected_text"></a>no_injected_text

컴파일러가 특성 사용의 결과로 코드를 삽입 하지 않도록 합니다.

## <a name="syntax"></a>구문

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>매개 변수

*boolean*<br/>
필드 코드를 삽입 하지 않으려면 **true** 이 고, 코드를 삽입할 수 있도록 하려면 **false** 입니다. 기본값은 **true** 입니다.

## <a name="remarks"></a>설명

**No_injected_text** C++ 특성의 가장 일반적인 용도는 **no_injected_text** 특성을 .mrg 파일에 삽입 하는 [/fx](../../build/reference/fx-merge-injected-code.md) 컴파일러 옵션을 사용 하는 것입니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|원하는 위치|
|**반복 가능**|예|
|**필수 특성**|None|
|**잘못된 특성**|None|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[컴파일러 특성](compiler-attributes.md)
