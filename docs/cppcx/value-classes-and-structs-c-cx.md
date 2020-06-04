---
title: 값 클래스 및 구조체(C++/CX)
ms.date: 12/30/2016
helpviewer_keywords:
- value struct
- value class
ms.assetid: 262a0992-9721-4c02-8297-efc07d90e5a4
ms.openlocfilehash: 4a4897f0a3b5c95ffb58e5c9666a2d764d71b3ec
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752900"
---
# <a name="value-classes-and-structs-ccx"></a>값 클래스 및 구조체(C++/CX)

*값 구조체* 또는 *값 클래스는* Windows 런타임 호환 POD("일반 이전 데이터 구조")입니다. 크기가 고정되어 있고 필드로만 구성되어 있으며 ref 클래스와는 달리 속성이 없습니다.

다음 예제에서는 값 구조체를 선언하고 초기화하는 방법을 보여 줍니다.

```

// in mainpage.xaml.h:
    value struct TestStruct
    {
        Platform::String^ str;
        int i;
    };

    value struct TestStruct2
    {
        TestStruct ts;
        Platform::String^ str;
        int i;
    };

// in mainpage.cpp:
    // Initialize a value struct with an int and String
    TestStruct ts = {"I am a TestStruct", 1};

    // Initialize a value struct that contains
    // another value struct, an int and a String
    TestStruct2 ts2 = {{"I am a TestStruct", 1}, "I am a TestStruct2", 2};

    // Initialize value struct members individually.
    TestStruct ts3;
    ts3.i = 108;
    ts3.str = "Another way to init a value struct.";
```

값 형식의 변수가 다른 변수에 할당되면 두 변수가 각각 고유한 데이터 복사본을 갖도록 값이 복사됩니다. *값 구조체* 는 공용 데이터 필드만 포함된 고정된 크기의 구조체이고, `value struct` 키워드를 사용하여 선언됩니다.

*값 클래스* 는 필드에 public 액세스 가능성이 명시적으로 부여되어야 한다는 점을 제외하고 `value struct` 와 비슷합니다. `value class` 키워드를 사용하여 선언됩니다.

값 구조체 또는 값 클래스는 기본 숫자 형식, 열거형 `Platform::String^`클래스 또는 [플랫폼::IBox \<T>^](../cppcx/platform-ibox-interface.md) 여기서 T는 숫자 형식 또는 열거형 클래스 또는 값 클래스 또는 구조체로만 필드로 포함될 수 있습니다. `IBox<T>^` 필드의 값은 `nullptr`로 지정할 수 있습니다. 이는 *null 허용 형식*개념이 C++에서 구현되는 방법입니다.

`Platform::String^` 또는 `IBox<T>^` 형식을 멤버로 포함하는 값 클래스 또는 값 구조체는 `memcpy`할 수 없습니다.

`value class` 또는 `value struct` 의 모든 멤버가 공용이고 메타데이터로 내보내지기 때문에 표준 C++ 형식은 멤버로 허용되지 않습니다. 이것은 `private` 또는 `internal` 표준 C++ 형식을 포함할 수 있는 ref 클래스와 다릅니다.

다음 코드 조각은 `Coordinates` 및 `City` 형식을 값 구조체로 선언합니다. `City` 데이터 멤버 중 하나는 `GeoCoordinates` 형식입니다. `value struct` 에는 다른 값 구조체가 멤버로 포함될 수 있습니다.

[!code-cpp[cx_classes#07](../cppcx/codesnippet/CPP/classesstructs/class1.h#07)]

## <a name="parameter-passing-for-value-types"></a>값 형식에 대해 전달되는 매개 변수

값 형식을 함수 또는 메서드 매개 변수로 사용하는 경우 일반적으로 값으로 전달됩니다. 따라서 개체가 큰 경우 성능 문제가 발생할 수 있습니다. Visual Studio2013 이하 버전에서는 C++/CX의 값 형식이 항상 값으로 전달되었습니다. Visual Studio 2015 이상 버전에서는 값 형식을 참조 또는 값으로 전달할 수 있습니다.

값 형식을 값으로 전달하는 매개 변수를 선언하려면 다음과 같은 코드를 사용하세요.

```cpp
void Method1(MyValueType obj);
```

값 형식을 참조로 전달하는 매개 변수를 선언하려면 다음과 같이 참조 기호(&)를 사용하세요.

```cpp
void Method2(MyValueType& obj);
```

Method2 내의 형식은 MyValueType에 대한 참조이며 표준 C++의 참조 형식과 동일한 방식으로 작동합니다.

C#과 같은 다른 언어에서 Method1을 호출하는 경우 `ref` 또는 `out` 키워드를 사용할 필요가 없습니다. Method2를 호출하는 경우에는 `ref` 키워드를 사용하세요.

```
Method2(ref obj);
```

또한 포인터 기호(*)를 사용하여 값 형식을 참조로 전달할 수 있습니다. 다른 언어의 호출자와 비교하여 동작은 동일(C#의 호출자는 `ref` 키워드 사용)하지만 메서드에서의 형식은 값 형식에 대한 포인터입니다.

## <a name="nullable-value-types"></a>Nullable 값 형식

앞에서 설명한 것처럼 값 클래스 또는 값 구조체에는 [플랫폼::IBox\<T>^와](../cppcx/platform-ibox-interface.md)같은 형식의 필드가 있을 수 `IBox<int>^`있습니다. 이러한 필드에는 `int` 형식에 대해 유효한 모든 숫자 값 또는 `nullptr`값을 지정할 수 있습니다. 매개 변수가 선택적으로 선언되었거나 값 형식에 값이 지정될 필요가 없는 메서드에 nullable 필드를 인수로 전달할 수 있습니다.

다음 예제에서는 null 허용 필드가 있는 구조체를 초기화하는 방법을 보여 줍니다.

```
public value struct Student
{
    Platform::String^ Name;
    int EnrollmentYear;
    Platform::IBox<int>^ GraduationYear; // Null if not yet graduated.
};
//To create a Student struct, one must populate the nullable type.
MainPage::MainPage()
{
    InitializeComponent();

    Student A;
    A.Name = "Alice";
    A.EnrollmentYear = 2008;
    A.GraduationYear = ref new Platform::Box<int>(2012);

    Student B;
    B.Name = "Bob";
    B.EnrollmentYear = 2011;
    B.GraduationYear = nullptr;

    IsCurrentlyEnrolled(A);
    IsCurrentlyEnrolled(B);
}
bool MainPage::IsCurrentlyEnrolled(Student s)
{
    if (s.GraduationYear == nullptr)
    {
        return true;
    }
    return false;
}
```

여기에서 볼 수 있는 것과 같이 값 구조체 자체를 동일한 방식으로 null 허용 개체로 만들 수 있습니다.

```

public value struct MyStruct
{
public:
    int i;
    Platform::String^ s;
};

public ref class MyClass sealed
{
public:
    property Platform::IBox<MyStruct>^ myNullableStruct;
};
```

## <a name="see-also"></a>참조

[유형 시스템(C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[C++/CX 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)<br/>
[Ref 클래스 및 구조체(C++/CX)](../cppcx/ref-classes-and-structs-c-cx.md)
