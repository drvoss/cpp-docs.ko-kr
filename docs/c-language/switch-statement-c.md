---
title: switch문 (C)
ms.date: 04/25/2020
f1_keywords:
- switch
helpviewer_keywords:
- switch keyword [C]
ms.assetid: fbede014-23bd-4ab1-8094-c8d9d9cb963a
no-loc:
- switch
- case
- default
- break
ms.openlocfilehash: 12163e85110092e3e372fa496cf42efd7574ea8d
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167678"
---
# <a name="opno-locswitch-statement-c"></a>switch문 (C)

및 **switch** **case** 문은 복잡 한 조건부 및 분기 작업을 제어 하는 데 도움이 됩니다. **switch** 문은 해당 본문 내의 문으로 제어를 전달 합니다.

## <a name="syntax"></a>구문

*selection-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`switch (`***식* **`)`** *문*

*레이블-문*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`case`**  *상수 식*  **`:`**  *문*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`default :`**  *선언문*

**case** *상수 식이* ** switch (** *식* **)** 의 값과 일치 하는 문으로 제어가 전달 됩니다. 문에 **switch** 는 임의의 수의 **case** 인스턴스가 포함 될 수 있습니다. 그러나 동일한 **switch** 문 내의 case 두 상수는 동일한 값을 가질 수 없습니다. 문 본문의 실행은 선택 된 문에서 시작 합니다. 본문이 종료 될 때까지 또는 **break** 문이 본문 밖으로 제어를 전송할 때까지 진행 됩니다.

**switch** 문의 사용은 일반적으로 다음과 같습니다.

```C
switch ( expression )
{
    // declarations
    // . . .
    case constant_expression:
        // statements executed if the expression equals the
        // value of this constant_expression
        break;
    default:
        // statements executed if expression does not equal
        // any case constant_expression
}
```

문을 사용 **break** 하 여 **switch** 문 내에서 레이블이 지정 된 특정 문의 처리를 종료할 수 있습니다. **switch** 문의 끝 부분으로 분기 합니다. 를 **break** 사용 하지 않으면 프로그램은 **break** 또는 문의 끝에 도달할 때까지 문을 실행 하 여 다음 레이블이 지정 된 문을 계속 실행 합니다. 이 연속 작업은 일부 상황에서 적합할 수 있습니다.

**default** **case** *상수 식이* ** switch (** *식* **)** 의 값과 일치 하지 않는 경우 문이 실행 됩니다. 문이 없고 **default** 일치 항목을 찾을 수 없는 **case** 경우 **switch** 본문의 문이 실행 되지 않습니다. 문은 최대 하나만 **default** 있을 수 있습니다. **default** 문은 끝에 있을 필요가 없습니다. 이는 **switch** 문의 본문 어디에 나 나타날 수 있습니다. **case** 또는 **default** 레이블은 **switch** 문 내부에만 나타날 수 있습니다.

**switch** *식* 의 형식 및 **case** *상수 식은* 정수 계열 이어야 합니다. 각 **case** *상수 식* 의 값은 문 본문 내에서 고유 해야 합니다.

문 **case** 본문 **default** 의 **switch** 및 레이블은 문 본문에서 실행이 시작 되는 위치를 결정 하는 초기 테스트 에서만 의미가 있습니다. **switch** 문은 중첩 될 수 있습니다. 모든 정적 변수는 **switch** 문을 실행 하기 전에 초기화 됩니다.

> [!NOTE]
> 선언은 **switch** 본문을 형성 하는 복합 문의 헤드에 나타날 수 있지만 선언에 포함 된 초기화는 수행 되지 않습니다. **switch** 문은 초기화가 포함 된 줄을 우회 하 여 본문 내의 실행 가능한 문으로 직접 제어를 전달 합니다.

다음 예에서는 문을 **switch** 보여 줍니다.

```C
switch( c )
{
    case 'A':
        capital_a++;
    case 'a':
        letter_a++;
    default :
        total++;
}
```

이 예에서는 **switch** 가 `c` `'A'`와 같은 경우 본문의 모든 세 문이 실행 됩니다 .이는 다음 **break** case앞에 문이 표시 되지 않기 때문입니다. 실행 제어는 첫 번째 문(`capital_a++;`)으로 전달되고 본문의 나머지 부분에서 순서대로 계속됩니다. `c`가 `'a'`와 같은 경우 `letter_a` 및 `total`이 증가합니다. 가 `total` 또는 `'a'`와 같지 `c` `'A'` 않은 경우만 증가 합니다.

```C
switch( i )
{
    case -1:
        n++;
        break;
    case 0 :
        z++;
        break;
    case 1 :
        p++;
        break;
}
```

이 예제에서 **break** 문은 **switch** 본문의 각 문 뒤에 나옵니다. **break** 문은 한 문이 실행 된 후 문 본문에서 강제로 종료 합니다. `i`가 –1과 같은 경우 `n`만 증가합니다. **break** 다음 문은 `n++;` 실행 제어가 문 본문 밖으로 전달 되도록 하 여 나머지 문을 무시 합니다. 이와 마찬가지로 `i`가 0과 같은 경우 `z`만 증가하고, `i`가 1과 같은 경우에는 `p`만 증가합니다. 제어가 복합 **break** 문의 끝에서 본문 밖으로 전달 되기 때문에 최종 문은 반드시 필요한 것은 아닙니다. 일관성을 위해 포함 되었습니다.

단일 문은 다음 예제와 같이 **case** 여러 레이블을 사용할 수 있습니다.

```C
switch( c )
{
    case 'a' :
    case 'b' :
    case 'c' :
    case 'd' :
    case 'e' :
    case 'f' :  convert_hex(c);
}
```

이 예제에서 *constant-expression*이 `'a'`와 `'f'` 사이의 문자와 같은 경우 `convert_hex` 함수가 호출됩니다.

### <a name="microsoft-specific"></a>Microsoft 전용

Microsoft C는 case **switch** 문의 값 수를 제한 하지 않습니다. 이 수는 사용 가능한 메모리에 의해서만 제한됩니다. ANSI C를 사용 하려면 적어도 case 257 개 이상의 레이블이 **switch** 문에 허용 되어야 합니다.

Microsoft default C에 대 한는 microsoft 확장을 사용 하도록 설정 되어 있습니다. 이러한 확장을 사용 하지 않도록 설정 하려면 [/za](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 사용 합니다.

## <a name="see-also"></a>참고 항목

[switch문 (c + +)](../cpp/switch-statement-cpp.md)
