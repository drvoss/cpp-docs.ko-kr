---
title: C 열거형 선언
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, enumerations
- define directive (#define), alternative to
- enumerators, declaring
- '#define directive, alternative to'
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: bd18f673-4dda-4bc1-92fd-d1ce10074910
ms.openlocfilehash: bc238dd0088558233d84f8bbd15d06743e133449
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326016"
---
# <a name="c-enumeration-declarations"></a>C 열거형 선언

열거형은 명명된 정수 상수의 집합으로 구성됩니다. 열거형 형식 선언은 (선택적) 열거형 태그의 이름을 제공하고 명명된 정수 식별자의 집합("열거형 집합", "열거자 상수", "열거자" 또는 "멤버"라고 함)을 정의합니다. 열거형 형식의 변수는 해당 형식으로 정의된 열거형 집합의 값 중 하나를 저장합니다.

`enum` 형식의 변수를 인덱싱 식에서 사용할 수 있으며 모든 산술 및 관계형 연산자의 피연산자로 사용할 수 있습니다. 열거형은 `#define` 전처리기 지시문 대신 사용할 수 있으며 값이 자동으로 생성되고 일반 범위 지정 규칙을 따를 수 있다는 이점을 제공합니다.

ANSI C에서 열거자 상수의 값을 정의하는 식의 형식은 항상 `int`이므로 열거형 변수와 연결된 스토리지는 단일 `int` 값에 필요한 스토리지입니다. 열거형 상수 또는 열거형 형식의 값은 C 언어에서 정수 식을 허용하는 모든 곳에서 사용할 수 있습니다.

## <a name="syntax"></a>구문

*enum-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**enum** *identifier*<sub>opt</sub> **{** *enumerator-list* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**enum** *identifier*

선택적 *identifier*는 *enumerator-list*로 정의된 열거형 형식의 이름을 지정합니다. 일반적으로 이 식별자를 목록으로 지정된 열거형의 "태그"라고 합니다. 다음 형태의 형식 지정자는

```
enum identifier
{
    enumerator-list
}
```

*identifier*를 *enumerator-list* 비터미널로 지정된 열거형의 태그로 선언합니다. *enumerator-list*는 "열거자 내용"을 정의합니다. *enumerator-list*는 아래에서 자세히 설명합니다.

태그의 선언이 표시되는 경우 태그를 사용하지만 *enumerator-list*를 생략하는 이후 선언에서는 이전에 선언된 열거형 형식을 지정합니다. 태그는 정의된 열거형 형식을 참조해야 하며 해당 열거형 형식은 현재 범위에 있어야 합니다. 열거형 형식이 다른 곳에서 정의되므로 *enumerator-list*는 이 선언에서 나타나지 않습니다. 열거형에서 파생된 형식의 선언과 열거형 형식에 대한 `typedef` 선언에서는 열거형 형식이 정의되기 전에 열거형 태그를 사용할 수 있습니다.

## <a name="syntax"></a>구문

*enumerator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enumerator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enumerator-list* **,** *enumerator*

*enumerator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enumeration-constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enumeration-constant* **=** *constant-expression*

*enumeration-constant*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*

*enumeration-list*에 있는 각 *enumeration-constant*는 열거형 집합의 값에 대한 이름을 지정합니다. 기본적으로 첫 번째 *enumeration-constant*는 값 0과 연결됩니다. 목록의 다음 *enumeration-constant*는 명시적으로 다른 값과 연결되지 않는 한 (*constant-expression* + 1)의 값과 연결됩니다. *enumeration-constant*의 이름은 해당 값과 동일합니다.

*enumeration-constant = constant-expression*을 사용하여 값의 기본 시퀀스를 재정의할 수 있습니다. 따라서 *enumeration-constant = constant-expression*이 *enumerator-list*에 나타나는 경우 *enumeration-constant*는 *constant-expression*으로 제공된 값과 연결됩니다. *constant-expression*은 `int` 형식이어야 하며 음수일 수 있습니다.

다음 규칙은 열거형 집합의 멤버에 적용됩니다.

- 열거형 집합에는 중복된 상수 값이 포함될 수 있습니다. 예를 들어 값 0을 동일한 집합에 있는 `null` 및 `zero`라는 두 가지 식별자와 연결할 수 있습니다.

- 열거형 목록의 식별자는 표시 유형이 같은 동일한 범위에 있는 다른 식별자(다른 열거형 목록의 일반 변수 이름 및 식별자 포함)와 구별되어야 합니다.

- 열거형 태그는 일반 범위 지정 규칙을 따르며, 표시 유형이 동일한 다른 열거형, 구조체 및 공용 구조체 태그와 구별되어야 합니다.

## <a name="examples"></a>예

다음 예제에서는 열거형 선언을 보여 줍니다.

```
enum DAY            /* Defines an enumeration type    */
{
    saturday,       /* Names day and declares a       */
    sunday = 0,     /* variable named workday with    */
    monday,         /* that type                      */
    tuesday,
    wednesday,      /* wednesday is associated with 3 */
    thursday,
    friday
} workday;
```

값 0은 기본적으로 `saturday`와 연결됩니다. `sunday` 식별자는 명시적으로 0으로 설정됩니다. 나머지 식별자에는 1부터 5까지의 값이 기본적으로 제공됩니다.

이 예제에서 `DAY` 집합의 값은 `today` 변수에 할당됩니다.

```
enum DAY today = wednesday;
```

열거형 상수의 이름은 값을 할당하는 데 사용됩니다. `DAY` 열거형 형식이 이전에 선언되었으므로 `DAY` 열거형 태그만 필요합니다.

정수 값을 열거형 데이터 형식의 변수에 명시적으로 할당하려면 다음과 같이 형식 캐스팅을 사용합니다.

```
workday = ( enum DAY ) ( day_value - 1 );
```

이 캐스팅은 C에서 권장되지만 필수 사항은 아닙니다.

```
enum BOOLEAN  /* Declares an enumeration data type called BOOLEAN */
{
    false,     /* false = 0, true = 1 */
    true
};

enum BOOLEAN end_flag, match_flag; /* Two variables of type BOOLEAN */
```

이 선언은 다음과 같이 지정될 수도 있습니다.

```
enum BOOLEAN { false, true } end_flag, match_flag;\
```

또는 다음과 같이 지정될 수도 있습니다.

```
enum BOOLEAN { false, true } end_flag;
enum BOOLEAN match_flag;
```

이러한 변수를 사용하는 예제는 다음과 같습니다.

```
if ( match_flag == false )
    {
     .
     .   /* statement */
     .
    }
    end_flag = true;
```

명명되지 않은 열거자 데이터 형식도 선언할 수 있습니다. 데이터 형식의 이름이 생략되었지만 변수를 선언할 수 있습니다. `response` 변수는 다음과 같이 정의된 형식의 변수입니다.

```
enum { yes, no } response;
```

## <a name="see-also"></a>참조

[열거형](../cpp/enumerations-cpp.md)
