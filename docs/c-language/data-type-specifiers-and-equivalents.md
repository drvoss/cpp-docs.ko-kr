---
title: 데이터 형식 지정자 및 해당 항목
ms.date: 11/04/2016
helpviewer_keywords:
- type specifiers [C++], list
- widening integers
- data types [C++], equivalents
- sign-extending integral types
- zero-extending
- identifiers, data type
- data types [C++], specifiers
- simple types, names
- type names [C++], simple
ms.assetid: 0d4b515a-4f68-4786-83cf-a5d43c7cb6f3
ms.openlocfilehash: cc8ba746bea7f6ea885beb625de414d83367b53f
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520683"
---
# <a name="data-type-specifiers-and-equivalents"></a>데이터 형식 지정자 및 해당 항목

이 책에서는 일반적으로 긴 형태보다 다음 표에 나열되어 있는 형식 지정자의 형태를 사용하며, 기본적으로 **`char`** 형식은 부호가 있다고 가정합니다. 따라서 이 책에 나오는 **`char`** 는 **`signed char`** 와 동일합니다.

## <a name="type-specifiers-and-equivalents"></a>형식 지정자 및 해당 값

| 형식 지정자 | 해당 값 |
|--|--|
| **`signed char`** <sup>1</sup> | **`char`** |
| **`signed int`** | **`signed`** , **`int`** |
| **`signed short int`** | **`short`** , **`signed short`** |
| **`signed long int`** | **`long`** , **`signed long`** |
| **`unsigned char`** | — |
| **`unsigned int`** | **`unsigned`** |
| **`unsigned short int`** | **`unsigned short`** |
| **`unsigned long int`** | **`unsigned long`** |
| **`float`** | — |
| **`long double`** <sup>2</sup> | — |

<sup>1</sup> 기본적으로 **`char`** 형식을 만들면( **`/J`** 컴파일러 옵션 지정) **`signed char`** 를 **`char`** 로 줄여 표현할 수 없습니다.

<sup>2</sup> 32비트 및 64비트 운영 체제에서 Microsoft C 컴파일러는 **`long double`** 을 **`double`** 형식에 매핑합니다.

**Microsoft 전용**

**`/J`** 컴파일러 옵션을 지정하여 기본 **`char`** 형식을 **`signed char`** 에서 **`unsigned char`** 로 변경할 수 있습니다. 이 옵션이 적용되면, **`char`** 는 **`unsigned char`** 와 같은 의미가 되기 때문에, 부호 있는 문자 값을 선언하려면 **`signed`** 키워드를 사용해야 합니다. **`char`** 값이 명시적으로 **`signed`** 로 선언되면, **`/J`** 옵션은 이 값에 영향을 주지 않으며, 이 값이 **`int`** 형식으로 확장되는 경우에는 부호 확장됩니다. **`char`** 형식은 **`int`** 형식으로 확장되면 제로 확장됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[C 형식 지정자](../c-language/c-type-specifiers.md)
