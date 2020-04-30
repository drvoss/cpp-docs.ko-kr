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
ms.openlocfilehash: 5858447602a28dcc5573aa3138e869d106b5aa23
ms.sourcegitcommit: 2f9ff2041d70c406df76c5053151192aad3937ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "82587370"
---
# <a name="switch-statement-c"></a>`switch`문 (C)

및 __`switch`__ __`case`__ 문은 복잡 한 조건부 및 분기 작업을 제어 하는 데 도움이 됩니다. __`switch`__ 문은 해당 본문 내의 문으로 제어를 전달 합니다.

## <a name="syntax"></a>구문

> *`selection-statement`*:<br/>
> &nbsp;&nbsp;&nbsp;&nbsp; __`switch (`__&nbsp;*`expression`* &nbsp;__`)`__&nbsp;*`statement`*

> *`labeled-statement`*:<br/>
> &nbsp;&nbsp;&nbsp;&nbsp; __`case`__&nbsp;*`constant-expression`*&nbsp;__`:`__&nbsp;*`statement`*<br/>
> &nbsp;&nbsp;&nbsp;&nbsp; __`default`__&nbsp;__`:`__&nbsp;*`statement`*

## <a name="remarks"></a>설명

__`switch`__ 문은의 *`expression`* 값에 따라 제어가 문 본문 *`labeled-statement`* 의 한로 전송 되도록 합니다.

및의 *`expression`* 값은 정수 *`constant-expression`* 계열 형식 이어야 합니다. 컴파일 *`constant-expression`* 시간에는 명확한 상수 정수 값이 있어야 합니다.

해당 **`case`** *`constant-expression`* 값이의 *`expression`* 값과 일치 하는 문으로 제어가 전달 됩니다. 문에 __`switch`__ 는 임의의 수의 __`case`__ 인스턴스가 포함 될 수 있습니다. 그러나 동일한 __`switch`__ 문 내의 *`constant-expression`* 두 값은 동일한 값을 가질 수 없습니다. __`switch`__ 문 본문의 실행은 일치 하 *`labeled-statement`* 는의 첫 번째 문에서 시작 합니다. 본문이 종료 될 때까지 또는 __`break`__ 문이 본문 밖으로 제어를 전송할 때까지 실행이 진행 됩니다.

__`switch`__ 문의 사용은 일반적으로 다음과 같습니다.

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

문을 사용 __`break`__ 하 여 __`switch`__ 문 내에서 레이블이 지정 된 특정 문의 처리를 종료할 수 있습니다. __`switch`__ 문의 끝 부분으로 분기 합니다. 를 __`break`__ 사용 하지 않으면 프로그램은 __`break`__ 또는 문의 끝에 도달할 때까지 문을 실행 하 여 다음 레이블이 지정 된 문을 계속 실행 합니다. 이 연속 작업은 일부 상황에서 적합할 수 있습니다.

값 __`default`__ 이이 아닌 경우 __`case`__ *`constant-expression`* 문이 실행 됩니다 *`expression`*. 문이 없고 __`default`__ 일치 항목을 찾을 수 없는 __`case`__ 경우 __`switch`__ 본문의 문이 실행 되지 않습니다. 문은 최대 하나만 __`default`__ 있을 수 있습니다. __`default`__ 문은 끝에 있을 필요가 없습니다. 이는 __`switch`__ 문의 본문 어디에 나 나타날 수 있습니다. __`case`__ 또는 __`default`__ 레이블은 __`switch`__ 문 내부에만 나타날 수 있습니다.

__`switch`__ *`expression`* 및 __`case`__ 의 *`constant-expression`* 형식은 정수 계열 이어야 합니다. 각각 __`case`__ *`constant-expression`* 의 값은 문 본문 내에서 고유 해야 합니다.

문 __`case`__ 본문 __`default`__ 의 __`switch`__ 및 레이블은 문 본문에서 실행이 시작 되는 위치를 결정 하는 초기 테스트 에서만 의미가 있습니다. __`switch`__ 문은 중첩 될 수 있습니다. 모든 정적 변수는 __`switch`__ 문을 실행 하기 전에 초기화 됩니다.

> [!NOTE]
> 선언은 __`switch`__ 본문을 형성 하는 복합 문의 헤드에 나타날 수 있지만 선언에 포함 된 초기화는 수행 되지 않습니다. __`switch`__ 문은 초기화가 포함 된 줄을 우회 하 여 본문 내의 실행 가능한 문으로 직접 제어를 전달 합니다.

다음 예에서는 문을 __`switch`__ 보여 줍니다.

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

이 예에서는 __`switch`__ 가 `c` `'A'`와 같은 경우 본문의 모든 세 문이 실행 됩니다 .이는 다음 __`break`__ __`case`__ 앞에 문이 표시 되지 않기 때문입니다. 실행 제어는 첫 번째 문(`capital_a++;`)으로 전달되고 본문의 나머지 부분에서 순서대로 계속됩니다. `c`가 `'a'`와 같은 경우 `letter_a` 및 `total`이 증가합니다. 가 `total` 또는 `'a'`와 같지 `c` `'A'` 않은 경우만 증가 합니다.

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

이 예제에서 __`break`__ 문은 __`switch`__ 본문의 각 문 뒤에 나옵니다. __`break`__ 문은 한 문이 실행 된 후 문 본문에서 강제로 종료 합니다. `i`가 –1과 같은 경우 `n`만 증가합니다. __`break`__ 다음 문은 `n++;` 실행 제어가 문 본문 밖으로 전달 되도록 하 여 나머지 문을 무시 합니다. 이와 마찬가지로 `i`가 0과 같은 경우 `z`만 증가하고, `i`가 1과 같은 경우에는 `p`만 증가합니다. 제어가 복합 __`break`__ 문의 끝에서 본문 밖으로 전달 되기 때문에 최종 문은 반드시 필요한 것은 아닙니다. 일관성을 위해 포함 되었습니다.

단일 문은 다음 예제와 같이 __`case`__ 여러 레이블을 사용할 수 있습니다.

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

Microsoft C는 __`case`__ __`switch`__ 문의 값 수를 제한 하지 않습니다. 이 수는 사용 가능한 메모리에 의해서만 제한됩니다. ANSI C를 사용 하려면 적어도 __`case`__ 257 개 이상의 레이블이 __`switch`__ 문에 허용 되어야 합니다.

Microsoft default C에 대 한는 microsoft 확장을 사용 하도록 설정 되어 있습니다. 이러한 확장을 사용 하지 않도록 설정 하려면 [/za](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 사용 합니다.

## <a name="see-also"></a>참고 항목

[switch문 (c + +)](../cpp/switch-statement-cpp.md)
