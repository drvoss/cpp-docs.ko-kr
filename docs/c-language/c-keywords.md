---
title: C 키워드
ms.date: 10/09/2018
helpviewer_keywords:
- keywords [C]
- redefining keywords
- Microsoft-specific keywords
ms.assetid: 2d932335-97bf-45cd-b367-4ae00db0ff42
ms.openlocfilehash: 92704572c40812141911e151faf1a8d331a1ed38
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520437"
---
# <a name="c-keywords"></a>C 키워드

"키워드"는 C 컴파일러에서 특별한 의미를 가진 단어입니다. 7번째 및 8번째 변환 단계에서는 식별자가 C 키워드와 같은 철자 및 대/소문자를 사용할 수 없습니다. 자세한 내용은 *전처리기 참조*의 [변환 단계](../preprocessor/phases-of-translation.md) 설명을 참조하세요. 식별자에 대한 자세한 내용은 [식별자](../c-language/c-identifiers.md)를 참조하세요. C 언어는 다음의 키워드를 사용합니다.

:::row:::
    :::column:::
        **`auto`**<br/>
        **`double`**<br/>
        **`int`**<br/>
        **`struct`**<br/>
        **`break`**<br/>
        **`else`**<br/>
        **`long`**<br/>
        **`switch`**<br/>
    :::column-end:::
    :::column:::
        **`case`**<br/>
        **`enum`**<br/>
        **`register`**<br/>
        **`typedef`**<br/>
        **`char`**<br/>
        **`extern`**<br/>
        **`return`**<br/>
        **`union`**<br/>
    :::column-end:::
    :::column:::
        **`const`**<br/>
        **`float`**<br/>
        **`short`**<br/>
        **`unsigned`**<br/>
        **`continue`**<br/>
        **`for`**<br/>
        **`signed`**<br/>
        **`void`**<br/>
    :::column-end:::
    :::column:::
        **`default`**<br/>
        **`goto`**<br/>
        **`sizeof`**<br/>
        **`volatile`**<br/>
        **`do`**<br/>
        **`if`**<br/>
        **`static`**<br/>
        **`while`**<br/>
    :::column-end:::
:::row-end:::

키워드를 다시 정의할 수는 없습니다. 그러나 컴파일 전에 C [전처리기 지시문](../preprocessor/preprocessor-directives.md)을 사용하여 키워드를 대체할 텍스트를 지정할 수 있습니다.

**Microsoft 전용**

ANSI C 표준을 사용하면 두 개의 선행 밑줄이 쳐진 식별자를 컴파일러의 구현용으로 예약할 수 있습니다. 따라서 Microsoft 규칙은 이중 밑줄이 쳐진 Microsoft 전용 키워드 이름 앞에 있게 됩니다. 이들 단어는 식별자 이름으로 사용할 수 없습니다. 두 개의 밑줄을 사용하는 경우를 포함하여 명명 식별자의 ANSI 규칙에 대한 자세한 내용은 [식별자](../c-language/c-identifiers.md)를 참조하세요.

Microsoft C 컴파일러에서 다음 키워드 및 특수 식별자가 인식됩니다.

:::row:::
    :::column:::
        **`__asm`** <sup>3</sup><br/>
        **`dllimport`** <sup>2</sup><br/>
        **`__int8`** <sup>3</sup><br/>
        **`naked`** <sup>2</sup><br/>
        **`__based`** <sup>1, 3</sup><br/>
    :::column-end:::
    :::column:::
        **`__except`** <sup>3</sup><br/>
        **`__int16`** <sup>3</sup><br/>
        **`__stdcall`** <sup>3</sup><br/>
        **`__cdecl`** <sup>3</sup><br/>
        **`__fastcall`**<br/>
    :::column-end:::
    :::column:::
        **`__int32`** <sup>3</sup><br/>
        **`thread`** <sup>2</sup><br/>
        **`__declspec`** <sup>3</sup><br/>
        **`__finally`** <sup>3</sup><br/>
        **`__int64`** <sup>3</sup><br/>
    :::column-end:::
    :::column:::
        **`__try`** <sup>3</sup><br/>
        **`dllexport`** <sup>2</sup><br/>
        **`__inline`** <sup>3</sup><br/>
        **`__leave`** <sup>3</sup><br/>
    :::column-end:::
:::row-end:::

<sup>1</sup> **`__based`** 키워드의 경우 32 비트 및 64 비트 대상 컴파일에서 제한적으로 사용됩니다.

<sup>2</sup> 이들은 **`__declspec`** 과 함께 사용되는 특수 식별자이며 다른 컨텍스트에서는 사용이 제한되지 않습니다.

<sup>3</sup> 이전 버전과의 호환성을 위해 이러한 키워드는 Microsoft 확장이 사용하도록 설정된 경우 두 개의 선행 밑줄과 단일 선행 밑줄 둘 다와 함께 사용할 수 있습니다.

Microsoft 확장은 기본적으로 사용하도록 설정됩니다. 프로그램이 완전하게 이식 가능하도록 컴파일하는 동안 [/Za\(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 옵션을 지정하여 Microsoft 확장을 사용하지 않을 수 있습니다. 이렇게 하면 몇 가지 Microsoft 관련 키워드를 사용할 수 없습니다.

Microsoft 확장을 사용하면 위에 나열된 키워드를 프로그램에서 사용할 수 있습니다. ANSI 규격에 따라 이러한 키워드의 대부분에는 두 개의 밑줄이 앞에 옵니다. 네 가지 예외 사항인 **`dllexport`** , **`dllimport`** , **`naked`** 및 **`thread`** 는 **`__declspec`** 과 함께만 사용되므로 선행 밑줄이 필요하지 않습니다. 이전 버전과의 호환성을 위해 나머지 키워드에는 밑줄 한 개가 옵니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[C 요소](../c-language/elements-of-c.md)
