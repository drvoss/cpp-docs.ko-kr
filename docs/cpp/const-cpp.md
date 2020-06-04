---
title: const (C++)
ms.date: 11/04/2016
f1_keywords:
- const_cpp
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
ms.openlocfilehash: cc1f117cc5f26edf9cd85461281b925c97fa5225
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180306"
---
# <a name="const-c"></a>const (C++)

데이터 선언을 수정할 때 **const** 키워드는 개체 또는 변수를 수정할 수 없도록 지정 합니다.

## <a name="syntax"></a>구문

```
const declaration ;
member-function const ;
```

## <a name="const-values"></a>const 값

**Const** 키워드는 변수의 값이 상수 임을 지정 하 고 프로그래머에 게이를 수정 하지 않도록 컴파일러에 지시 합니다.

```cpp
// constant_values1.cpp
int main() {
   const int i = 5;
   i = 10;   // C3892
   i++;   // C2105
}
```

에서는 C++ [#define](../preprocessor/hash-define-directive-c-cpp.md) 전처리기 지시문 대신 **const** 키워드를 사용 하 여 상수 값을 정의할 수 있습니다. **Const** 를 사용 하 여 정의 된 값에는 형식 검사가 적용 되며 상수 식 대신 사용할 수 있습니다. 에서는 C++다음과 같이 **const** 변수를 사용 하 여 배열의 크기를 지정할 수 있습니다.

```cpp
// constant_values2.cpp
// compile with: /c
const int maxarray = 255;
char store_char[maxarray];  // allowed in C++; not allowed in C
```

C에서 상수 값은 기본적으로 외부 링크로 설정되므로 소스 파일에만 나타날 수 있습니다. C++에서 상수 값은 기본적으로 내부 링크로 설정되므로 헤더 파일에 나타날 수 있습니다.

**Const** 키워드는 포인터 선언에도 사용할 수 있습니다.

```cpp
// constant_values3.cpp
int main() {
   char *mybuf = 0, *yourbuf;
   char *const aptr = mybuf;
   *aptr = 'a';   // OK
   aptr = yourbuf;   // C3892
}
```

**Const** 로 선언 된 변수에 대 한 포인터는 **const**로도 선언 된 포인터에만 할당할 수 있습니다.

```cpp
// constant_values4.cpp
#include <stdio.h>
int main() {
   const char *mybuf = "test";
   char *yourbuf = "test2";
   printf_s("%s\n", mybuf);

   const char *bptr = mybuf;   // Pointer to constant data
   printf_s("%s\n", bptr);

   // *bptr = 'a';   // Error
}
```

상수 데이터에 대한 포인터를 함수 매개 변수로 사용하여 함수가 포인터를 통해 전달된 매개 변수를 수정하지 못하게 할 수 있습니다.

**Const**로 선언 된 개체의 경우 상수 멤버 함수를 호출할 수 있습니다. 이렇게 하면 상수 개체가 절대로 수정되지 않습니다.

```cpp
birthday.getMonth();    // Okay
birthday.setMonth( 4 ); // Error
```

비상수 개체의 경우에는 상수 또는 비상수 멤버 함수를 호출할 수 있습니다. **Const** 키워드를 사용 하 여 멤버 함수를 오버 로드할 수도 있습니다. 이렇게 하면 상수 및 비상수 개체에 대해 다른 버전의 함수를 호출할 수 있습니다.

**Const** 키워드를 사용 하 여 생성자 또는 소멸자를 선언할 수 없습니다.

## <a name="const-member-functions"></a>const 멤버 함수

**Const** 키워드를 사용 하 여 멤버 함수를 선언 하면 함수가 호출 되는 개체를 수정 하지 않는 "읽기 전용" 함수 임을 지정 합니다. 상수 멤버 함수는 비정적 데이터 멤버를 수정 하거나 상수가 아닌 멤버 함수를 호출할 수 없습니다. 상수 멤버 함수를 선언 하려면 인수 목록에서 닫는 괄호 뒤에 **const** 키워드를 추가 합니다. **Const** 키워드는 선언 및 정의 모두에 필요 합니다.

```cpp
// constant_member_function.cpp
class Date
{
public:
   Date( int mn, int dy, int yr );
   int getMonth() const;     // A read-only function
   void setMonth( int mn );   // A write function; can't be const
private:
   int month;
};

int Date::getMonth() const
{
   return month;        // Doesn't modify anything
}
void Date::setMonth( int mn )
{
   month = mn;          // Modifies data member
}
int main()
{
   Date MyDate( 7, 4, 1998 );
   const Date BirthDate( 1, 18, 1953 );
   MyDate.setMonth( 4 );    // Okay
   BirthDate.getMonth();    // Okay
   BirthDate.setMonth( 4 ); // C2662 Error
}
```

## <a name="c-and-c-const-differences"></a>C 및 C++ const 차이점

C 소스 코드 파일에서 변수를 **const** 로 선언 하는 경우 다음 작업을 수행 합니다.

```cpp
const int i = 2;
```

그런 다음 이 변수를 아래와 같이 다른 모듈에서 사용할 수 있습니다.

```cpp
extern const int i;
```

그러나에서 C++동일한 동작을 얻으려면 **const** 변수를 다음과 같이 선언 해야 합니다.

```cpp
extern const int i = 2;
```

C 소스 코드 파일에서 사용 **extern** 하기 위해 C++ 소스 코드 파일에 extern 변수를 선언 하려는 경우 다음을 사용 합니다.

```cpp
extern "C" const int x=10;
```

C++ 컴파일러에 의한 이름 변환을 방지해야 합니다.

## <a name="remarks"></a>설명

멤버 함수의 매개 변수 목록 다음에 나오는 **const** 키워드는 함수가 호출 되는 개체를 수정 하지 않도록 지정 합니다.

**Const**에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

- [const 및 volatile 포인터](../cpp/const-and-volatile-pointers.md)

- [형식 한정자 (C 언어 참조)](../c-language/type-qualifiers.md)

- [volatile](../cpp/volatile-cpp.md)

- [#define](../preprocessor/hash-define-directive-c-cpp.md)

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)
