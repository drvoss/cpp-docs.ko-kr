---
title: no_injected_text (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: 7e5c822c45888f41e8dd849f25658d0139e6fda0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87201247"
---
# <a name="no_injected_text"></a>no_injected_text

컴파일러가 특성 사용의 결과로 코드를 삽입 하지 않도록 합니다.

## <a name="syntax"></a>구문

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>매개 변수

*boolean*<br/>
(선택 사항) **`true`** 코드를 삽입 하지 않으려는 경우 코드를 삽입할 **`false`** 수 있습니다. **`true`** 가 기본값입니다.

## <a name="remarks"></a>설명

**No_injected_text** c + + 특성의 가장 일반적인 용도는 **no_injected_text** 특성을 .mrg 파일에 삽입 하는 [/fx](../../build/reference/fx-merge-injected-code.md) 컴파일러 옵션을 사용 하는 것입니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|원하는 위치|
|**불가능**|예|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고 항목

[컴파일러 특성](compiler-attributes.md)
