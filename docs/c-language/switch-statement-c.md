---
title: ':::no-loc(switch):::  Statement (C)'
ms.date: 04/25/2020
f1_keywords:
- ':::no-loc(switch):::'
helpviewer_keywords:
- ':::no-loc(switch)::: keyword [C]'
ms.assetid: fbede014-23bd-4ab1-8094-c8d9d9cb963a
no-loc:
- ':::no-loc(switch):::'
- ':::no-loc(case):::'
- ':::no-loc(default):::'
- ':::no-loc(break):::'
ms.openlocfilehash: bdd6885f67728a3c81e395f05c33191156896ad9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220784"
---
# <a name="no-locswitch-statement-c"></a>`:::no-loc(switch):::` Statement (C)

**`:::no-loc(switch):::`** 및 **`:::no-loc(case):::`** 문은 복잡한 조건부 및 분기 작업을 제어하는 데 도움이 됩니다. **`:::no-loc(switch):::`** 문은 해당 본문 내의 문으로 제어를 전달합니다.

## <a name="syntax"></a>구문

> *`selection-statement`* :\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(switch)::: (`** &nbsp; *`expression`* &nbsp; **`)`** &nbsp; *`statement`*

> *`labeled-statement`* :\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(case):::`** &nbsp; *`constant-expression`* &nbsp; **`:`** &nbsp; *`statement`* \
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(default):::`** &nbsp; **`:`** &nbsp; *`statement`*

## <a name="remarks"></a>설명

**`:::no-loc(switch):::`** 문을 통해 컨트롤은 *`expression`* 의 값에 따라 문 본문에서 하나의 *`labeled-statement`* 로 전송됩니다.

*`expression`* 및 각 *`constant-expression`* 의 값은 정수 데이터 형식이어야 합니다. 컴파일 시간에는 *`constant-expression`* 에 명확한 상수 정수 값이 있어야 합니다.

제어는 *`constant-expression`* 값이 *`expression`* 의 값과 일치하는 **`:::no-loc(case):::`** 문으로 전달됩니다. **`:::no-loc(switch):::`** 문에는 임의의 수의 **`:::no-loc(case):::`** 인스턴스가 포함될 수 있습니다. 그러나 동일한 **`:::no-loc(switch):::`** 문 내의 *`constant-expression`* 값 2개가 동일한 값일 수는 없습니다. **`:::no-loc(switch):::`** 문 본문의 실행은 일치하는 *`labeled-statement`* 안에 있는 또는 뒤에 오는 첫 번째 문에서 시작합니다. 본문이 끝날 때까지 또는 **`:::no-loc(break):::`** 문이 본문 밖으로 컨트롤을 전송할 때까지 실행이 진행됩니다.

**`:::no-loc(switch):::`** 문의 사용은 대개 다음과 같습니다.

```C
:::no-loc(switch)::: ( expression )
{
    // declarations
    // . . .
    :::no-loc(case)::: constant_expression:
        // statements executed if the expression equals the
        // value of this constant_expression
        :::no-loc(break):::;
    :::no-loc(default)::::
        // statements executed if expression does not equal
        // any :::no-loc(case)::: constant_expression
}
```

**`:::no-loc(break):::`** 문을 사용하여 **`:::no-loc(switch):::`** 문 내의 레이블이 지정된 특정 문의 처리를 종료할 수 있습니다. **`:::no-loc(switch):::`** 문의 끝으로 분기됩니다. **`:::no-loc(break):::`** 가 없는 경우 프로그램은 레이블이 지정된 다음 문으로 지속되어 **`:::no-loc(break):::`** 또는 문의 끝에 도달할 때까지 문을 실행합니다. 어떤 상황에서는 이러한 지속이 바람직할 수 있습니다.

**`:::no-loc(case):::`** *`constant-expression`* 값이 *`expression`* 의 값과 같지 않으면 **`:::no-loc(default):::`** 문이 실행됩니다. **`:::no-loc(default):::`** 문이 없고 **`:::no-loc(case):::`** 일치를 찾을 수 없으면 **`:::no-loc(switch):::`** 본문의 문이 전혀 실행되지 않습니다. **`:::no-loc(default):::`** 문은 하나만 존재할 수 있습니다. **`:::no-loc(default):::`** 문은 끝에 올 필요가 없고, **`:::no-loc(switch):::`** 문의 본문 어디에나 나타날 수 있습니다. **`:::no-loc(case):::`** 또는 **`:::no-loc(default):::`** 레이블은 **`:::no-loc(switch):::`** 문 안에만 나타날 수 있습니다.

**`:::no-loc(switch):::`** *`expression`* 및 **`:::no-loc(case):::`** *`constant-expression`* 의 형식은 정수이어야 합니다. 각 **`:::no-loc(case):::`** *`constant-expression`* 의 값은 문 본문 내에서 고유해야 합니다.

**`:::no-loc(switch):::`** 문 본문의 **`:::no-loc(case):::`** 및 **`:::no-loc(default):::`** 레이블은 문 본문에서 실행이 시작되는 위치를 결정하는 초기 테스트에서만 의미가 있습니다. **`:::no-loc(switch):::`** 문은 중첩될 수 있습니다. 모든 정적 변수는 **`:::no-loc(switch):::`** 문으로 실행하기 전에 초기화됩니다.

> [!NOTE]
> 선언은 **`:::no-loc(switch):::`** 본문을 형성하는 복합 문의 위쪽에 나타날 수 있지만 선언에 포함된 초기화는 수행되지 않습니다. **`:::no-loc(switch):::`** 문은 초기화가 포함된 줄을 우회하여 본문 내의 실행 문으로 제어를 직접 전달합니다.

다음 예제에서는 **`:::no-loc(switch):::`** 문을 보여 줍니다.

```C
:::no-loc(switch):::( c )
{
    :::no-loc(case)::: 'A':
        capital_a++;
    :::no-loc(case)::: 'a':
        letter_a++;
    :::no-loc(default)::: :
        total++;
}
```

이 예제에서는 **`:::no-loc(break):::`** 문이 다음 **`:::no-loc(case):::`** 앞에 나타나지 않으므로 `c`가 `'A'`와 같은 경우 **`:::no-loc(switch):::`** 본문의 모든 세 문이 실행됩니다. 실행 제어는 첫 번째 문(`capital_a++;`)으로 전달되고 본문의 나머지 부분에서 순서대로 계속됩니다. `c`가 `'a'`와 같은 경우 `letter_a` 및 `total`이 증가합니다. `c`가 `'A'` 또는 `'a'`와 같지 않을 경우에만 `total`이 증가합니다.

```C
:::no-loc(switch):::( i )
{
    :::no-loc(case)::: -1:
        n++;
        :::no-loc(break):::;
    :::no-loc(case)::: 0 :
        z++;
        :::no-loc(break):::;
    :::no-loc(case)::: 1 :
        p++;
        :::no-loc(break):::;
}
```

이 예제에서 **`:::no-loc(break):::`** 문은 **`:::no-loc(switch):::`** 본문의 각 문 뒤에 나옵니다. **`:::no-loc(break):::`** 문은 한 문이 실행된 후 문 본문에서 강제로 빠져나옵니다. `i`가 –1과 같은 경우 `n`만 증가합니다. `n++;` 문 다음에 오는 **`:::no-loc(break):::`** 는 실행 제어가 문 본문 밖으로 전달되고 나머지 문들을 우회하도록 합니다. 이와 마찬가지로 `i`가 0과 같은 경우 `z`만 증가하고, `i`가 1과 같은 경우에는 `p`만 증가합니다. 제어가 복합 문의 끝에서 본문 밖으로 전달되므로 마지막 **`:::no-loc(break):::`** 문이 반드시 필요하지는 않습니다. 이 문은 일관성을 위해 포함되었습니다.

다음 예제와 같이 단일 문이 여러 **`:::no-loc(case):::`** 레이블을 수행할 수 있습니다.

```C
:::no-loc(switch):::( c )
{
    :::no-loc(case)::: 'a' :
    :::no-loc(case)::: 'b' :
    :::no-loc(case)::: 'c' :
    :::no-loc(case)::: 'd' :
    :::no-loc(case)::: 'e' :
    :::no-loc(case)::: 'f' :  convert_hex(c);
}
```

이 예제에서 *constant-expression*이 `'a'`와 `'f'` 사이의 문자와 같은 경우 `convert_hex` 함수가 호출됩니다.

### <a name="microsoft-specific"></a>Microsoft 전용

Microsoft C는 **`:::no-loc(switch):::`** 문의 **`:::no-loc(case):::`** 값 수를 제한하지 않습니다. 이 수는 사용 가능한 메모리에 의해서만 제한됩니다. ANSI C의 경우 **`:::no-loc(switch):::`** 문에서 257개 이상의 **`:::no-loc(case):::`** 레이블이 허용되어야 합니다.

Microsoft C에 대한 :::no-loc(default):::는 Microsoft 확장을 사용하도록 설정되어 있다는 것입니다. 이러한 확장을 사용하지 않도록 설정하려면 [/Za](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 사용하세요.

## <a name="see-also"></a>참조

[:::no-loc(switch)::: Statement (C++)](../cpp/:::no-loc(switch):::-statement-cpp.md)
