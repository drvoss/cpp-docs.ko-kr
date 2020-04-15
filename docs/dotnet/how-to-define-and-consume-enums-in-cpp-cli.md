---
title: '방법: C++/CLI에서 열거형 정의 및 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: cf3bb23069b2692c0ca4ce270a5b8060195becf7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370168"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>방법: C++/CLI에서 열거형 정의 및 사용

이 항목에서는 C++/CLI의 열거형에 대해 설명합니다.

## <a name="specifying-the-underlying-type-of-an-enum"></a>열거형의 기본 형식 지정

기본적으로 열거형의 기본 형식은 `int`입니다.  그러나 서명할 형식이나 서명되지 않은 형식의 `int` `short`을 `long` `__int32` `__int64`지정할 수 있습니다.  또한 `char`을 사용할 수 있습니다.

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

## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>관리되는 것과 표준 열거형 간에 변환하는 방법

열거형과 정수 유형 간에는 표준 변환이 없습니다. 캐스트가 필요합니다.

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

다음 연산자는 C++/CLI의 열거형에서 유효합니다.

|연산자|
|--------------|
|== != \<  >  \<= >=|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

&#124; ^& ~ ++ -- bool을 포함하지 않는 정수 기본 형식의 열거형에 대해서만 정의됩니다.  두 가지 모두 열거 형이어야 합니다.

컴파일러는 열거형 작업의 결과를 정적 또는 동적 검사하지 않습니다. 연산은 열거형의 유효한 열거형의 범위에 속하지 않는 값을 초래할 수 있습니다.

> [!NOTE]
> C++11은 C++/CLI에서 관리되는 열거형 클래스와 크게 다른 관리되지 않는 코드의 열거형 클래스 형식을 소개합니다. 특히 C++11 열거형 클래스 형식은 C++/CLI에서 관리되는 열거형 클래스 유형과 동일한 연산을 지원하지 않으며, C++/CLI 소스 코드는 관리되지 않는(C++11) 열거형 클래스 선언과 구별하기 위해 관리되는 열거형 클래스 선언에서 접근성 지정기를 제공해야 합니다. C++/CLI, C++/CX 및 C++11의 열거형 클래스에 대한 자세한 내용은 [열거형 클래스를](../extensions/enum-class-cpp-component-extensions.md)참조하십시오.

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
