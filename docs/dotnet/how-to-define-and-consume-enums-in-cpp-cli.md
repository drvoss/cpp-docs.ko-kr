---
title: '방법: C++/CLI에서 열거형 정의 및 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: 68f8e113f6199d3b320bc6d241ee3396d2b70a1a
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544984"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>방법: C++/CLI에서 열거형 정의 및 사용

이 항목에서는/Cli의 C++열거형에 대해 설명 합니다.

## <a name="specifying-the-underlying-type-of-an-enum"></a>열거형의 기본 형식 지정

기본적으로 열거형의 기본 형식은 `int`입니다.  그러나 `int`, `short`, `long`, `__int32`또는 `__int64`의 서명 또는 서명 되지 않은 형식을 지정할 수 있습니다.  또한 `char`을 사용할 수 있습니다.

```cpp
// mcppv2_enum_3.cpp
// compile with: /clr
public enum class day_char : char {sun, mon, tue, wed, thu, fri, sat};

int main() {
   // fully qualified names, enumerator not injected into scope
   day_char d = day_char::sun, e = day_char::mon;
   System::Console::WriteLine(d);
   char f = (char)d;
   System::Console::WriteLine(f);
   f = (char)e;
   System::Console::WriteLine(f);
   e = day_char::tue;
   f = (char)e;
   System::Console::WriteLine(f);
}
```

**출력**

```Output
sun
0
1
2
```

## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>관리 되는 열거형과 표준 열거형 간에 변환 하는 방법

열거형과 정수 계열 형식 간의 표준 변환은 없습니다. 캐스트가 필요 합니다.

```cpp
// mcppv2_enum_4.cpp
// compile with: /clr
enum class day {sun, mon, tue, wed, thu, fri, sat};
enum {sun, mon, tue, wed, thu, fri, sat} day2; // unnamed std enum

int main() {
   day a = day::sun;
   day2 = sun;
   if ((int)a == day2)
   // or...
   // if (a == (day)day2)
      System::Console::WriteLine("a and day2 are the same");
   else
      System::Console::WriteLine("a and day2 are not the same");
}
```

**출력**

```Output
a and day2 are the same
```

## <a name="operators-and-enums"></a>연산자 및 열거형

다음 연산자는/Cli의 C++열거형에서 유효 합니다.

|연산자|
|--------------|
|= =! = \< > \<= > =|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

연산자 &#124; ^ & ~ + +--는 bool을 포함 하지 않는 정수 계열 기본 형식의 열거형에 대해서만 정의 됩니다.  두 피연산자는 모두 열거형 형식 이어야 합니다.

컴파일러는 열거형 작업의 결과를 정적 또는 동적으로 검사 하지 않습니다. 작업으로 인해 열거형의 유효한 열거자 범위에 없는 값이 발생할 수 있습니다.

> [!NOTE]
>  C + + 11에서는/Cli의 C++관리 되는 열거형 클래스와 크게 다른 비관리 코드의 enum 클래스 형식을 소개 합니다. 특히 c + + 11 enum 클래스 형식은/Cli에서 C++관리 되는 열거형 클래스 형식과 같은 연산자를 지원 하지 않으며, C++/cli 소스 코드는 관리 되는 열거형 클래스 선언에서 accessibility 지정자를 제공 하 여 관리 되지 않는 (c + + 11) 열거형 클래스 선언과 구분 해야 합니다. /Cli, C++/Cx 및 c + + C++11의 enum 클래스에 대 한 자세한 내용은 [enum 클래스](../extensions/enum-class-cpp-component-extensions.md)를 참조 하세요.

```cpp
// mcppv2_enum_5.cpp
// compile with: /clr
private enum class E { a, b } e, mask;
int main() {
   if ( e & mask )   // C2451 no E->bool conversion
      ;

   if ( ( e & mask ) != 0 )   // C3063 no operator!= (E, int)
      ;

   if ( ( e & mask ) != E() )   // OK
      ;
}
```

```cpp
// mcppv2_enum_6.cpp
// compile with: /clr
private enum class day : int {sun, mon};
enum : bool {sun = true, mon = false} day2;

int main() {
   day a = day::sun, b = day::mon;
   day2 = sun;

   System::Console::WriteLine(sizeof(a));
   System::Console::WriteLine(sizeof(day2));
   a++;
   System::Console::WriteLine(a == b);
}
```

**출력**

```Output
4
1
True
```

## <a name="see-also"></a>참고 항목

[Enum 클래스](../extensions/enum-class-cpp-component-extensions.md)
