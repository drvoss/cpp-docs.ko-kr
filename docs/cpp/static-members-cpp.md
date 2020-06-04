---
title: 정적 멤버(C++)
ms.date: 11/04/2016
helpviewer_keywords:
- class members [C++], static
- instance constructors, static members
- class members [C++], shared
- members [C++], static data members
- static members [C++], data members
- static data members [C++]
- data members [C++], static data members
- class instances [C++], shared members
- instance constructors, shared members
- class instances [C++], static members
ms.assetid: 9cc8cf0f-d74c-46f2-8e83-42d4e42c8370
ms.openlocfilehash: c18b29cf69c2f899fbf06c7cb75ebbd2242ab427
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178563"
---
# <a name="static-members-c"></a>정적 멤버(C++)

클래스는 정적 멤버 데이터와 멤버 함수를 포함할 수 있습니다. 데이터 멤버가 **정적**으로 선언 되 면 클래스의 모든 개체에 대해 데이터의 복사본 하나만 유지 관리 됩니다.

정적 데이터 멤버는 지정된 클래스 형식의 개체에 속하지 않습니다. 결과적으로, 정적 데이터 멤버 선언은 정의로 간주되지 않습니다. 데이터 멤버는 클래스 범위에서 선언되지만 정의는 파일 범위에서 수행됩니다. 이러한 정적 멤버에는 외부 링크가 있습니다. 다음 예제에서는 이에 대해 설명합니다.

```cpp
// static_data_members.cpp
class BufferedOutput
{
public:
   // Return number of bytes written by any object of this class.
   short BytesWritten()
   {
      return bytecount;
   }

   // Reset the counter.
   static void ResetCount()
   {
      bytecount = 0;
   }

   // Static member declaration.
   static long bytecount;
};

// Define bytecount in file scope.
long BufferedOutput::bytecount;

int main()
{
}
```

앞의 코드에서 `bytecount` 멤버는 `BufferedOutput` 클래스에서 선언되었지만 클래스 선언 밖에서 정의되어야 합니다.

클래스 형식의 개체를 참조하지 않고 정적 데이터 멤버를 참조할 수 있습니다. `BufferedOutput` 개체를 사용하여 쓴 바이트 수는 다음과 같이 확인할 수 있습니다.

```cpp
long nBytes = BufferedOutput::bytecount;
```

정적 멤버가 존재하기 위해 클래스 형식의 개체가 있어야 하는 것은 아닙니다. 멤버 선택 ()을 사용 하 여 정적 멤버에 액세스할 수도 있습니다 **.** 및 **->** ) 연산자 예를 들면 다음과 같습니다.

```cpp
BufferedOutput Console;

long nBytes = Console.bytecount;
```

앞의 경우에서 개체(`Console`)에 대한 참조는 평가되지 않습니다. 반환된 값은 정적 개체 `bytecount`의 값입니다.

정적 데이터 멤버에는 클래스 멤버 액세스 규칙이 적용되므로 정적 데이터 멤버에 대한 전용 액세스는 클래스 멤버 함수 및 friend에만 허용됩니다. 이러한 규칙은 [멤버 Access Control](../cpp/member-access-control-cpp.md)에 설명 되어 있습니다. 예외는 정적 데이터 멤버가 해당 액세스 제한에 관계없이 파일 범위에서 정의되어야 한다는 것입니다. 데이터 멤버를 명시적으로 초기화하는 경우 이니셜라이저에 정의를 제공해야 합니다.

정적 멤버의 형식은 클래스 이름으로 한정되지 않습니다. 따라서 `BufferedOutput::bytecount`의 형식은 **깁니다**.

## <a name="see-also"></a>참고 항목

[클래스 및 구조체](../cpp/classes-and-structs-cpp.md)
