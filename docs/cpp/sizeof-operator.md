---
title: sizeof 연산자
ms.date: 11/04/2016
f1_keywords:
- sizeof_cpp
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
ms.openlocfilehash: c9ae581b1b3bea522f2c1557b8be44ee1f32eef1
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032293"
---
# <a name="sizeof-operator"></a>sizeof 연산자

**문자**문자의 크기에 대한 그 산모의 크기를 산출합니다.

> [!NOTE]
> 연산자에 `sizeof ...` 대한 자세한 내용은 [타원 및 다변 템플릿을](../cpp/ellipses-and-variadic-templates.md)참조하십시오.

## <a name="syntax"></a>구문

```
sizeof unary-expression
sizeof  ( type-name )
```

## <a name="remarks"></a>설명

**sizeof** 연산자의 결과는 형식이며, `size_t`포함 파일 \<stddef.h> 정의된 적분 형식입니다. 이 연산자를 사용하면 프로그램에서 컴퓨터 종속 데이터 크기를 지정하지 않아도 됩니다.

이연산자에서 **sizeof까지는** 다음 중 하나가 될 수 있습니다.

- 형식 이름. **sizeof를** 형식 이름과 함께 사용하려면 이름을 괄호로 묶어야 합니다.

- 식입니다. 식과 함께 사용할 경우 **괄호** 안의 유무에 관계없이 sizeof를 지정할 수 있습니다. 식은 계산되지 않습니다.

**sizeof** 연산자가 **문자**문자의 개체에 적용되면 1을 생성합니다. **sizeof** 연산자가 배열에 적용되면 배열 식별자로 표시되는 포인터의 크기가 아니라 해당 배열의 총 바이트 수를 생성합니다. 배열 식별자로 표시되는 포인터의 크기를 얻으려면 **sizeof를**사용하는 함수에 매개 변수로 전달합니다. 다음은 그 예입니다.

## <a name="example"></a>예제

```cpp
#include <iostream>
using namespace std;

size_t getPtrSize( char *ptr )
{
   return sizeof( ptr );
}

int main()
{
   char szHello[] = "Hello, world!";

   cout  << "The size of a char is: "
         << sizeof( char )
         << "\nThe length of " << szHello << " is: "
         << sizeof szHello
         << "\nThe size of the pointer is "
         << getPtrSize( szHello ) << endl;
}
```

## <a name="sample-output"></a>샘플 출력

```Output
The size of a char is: 1
The length of Hello, world! is: 14
The size of the pointer is 4
```

**sizeof** 연산자가 **클래스,** **구조체**또는 **공용 구조체** 유형에 적용되면 결과는 해당 형식의 개체에 바이트 수와 단어 경계에 멤버를 정렬하기 위해 추가된 모든 패딩입니다. 결과는 개별 멤버의 스토리지 요구 사항을 추가하여 계산된 크기와 일치하지 않을 수도 있습니다. [/Zp](../build/reference/zp-struct-member-alignment.md) 컴파일러 옵션과 [팩](../preprocessor/pack.md) pragma는 멤버의 정렬 경계에 영향을 미칩니다.

**sizeof** 연산자는 빈 클래스에 대해서도 0을 생성하지 않습니다.

**sizeof** 연산자는 다음 나연산자와 함께 사용할 수 없습니다.

- 함수 (그러나 **sizeof** 함수에 대한 포인터에 적용할 수 있습니다.)

- 비트 필드

- 정의되지 않은 클래스

- 형식 **void**.

- 동적으로 할당된 배열

- 외부 배열

- 불완전한 형식

- 괄호로 묶인 불완전한 형식의 이름

**sizeof** 연산자가 참조에 적용되면 결과는 개체 자체에 **sizeof가** 적용된 경우와 동일합니다.

크기가 없는 배열이 구조의 마지막 요소인 경우 **sizeof** 연산자는 배열 없이 구조의 크기를 반환합니다.

**sizeof** 연산자는 종종 양식의 식을 사용하여 배열의 요소 수를 계산하는 데 사용됩니다.

```cpp
sizeof array / sizeof array[0]
```

## <a name="see-also"></a>참조

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[키워드](../cpp/keywords-cpp.md)
