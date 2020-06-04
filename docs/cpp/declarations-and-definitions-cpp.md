---
title: 선언 및 정의 (C++)
ms.date: 12/12/2019
ms.assetid: 678f1424-e12f-45e0-a957-8169e5fef6cb
ms.openlocfilehash: 7aa9e07a471ed5a32ecc8f13690f1a1bf08b655f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077209"
---
# <a name="declarations-and-definitions-c"></a>선언 및 정의 (C++)

프로그램 C++ 은 변수, 함수, 형식 및 네임 스페이스와 같은 다양 한 엔터티로 구성 됩니다. 이러한 각 엔터티는 먼저 *선언* 되어야 사용할 수 있습니다. 선언은 해당 형식 및 기타 특성에 대 한 정보와 함께 엔터티의 고유 이름을 지정 합니다. 이름이 C++ 선언 되는 지점에서이 요소는 컴파일러에 표시 되는 지점입니다. 컴파일 단위에서 나중에 선언 된 함수 또는 클래스는 참조할 수 없습니다. 변수는 사용 되는 지점 보다 최대한 가깝게 선언 해야 합니다.

다음 예제에서는 몇 가지 선언을 보여 줍니다.

```cpp
#include <string>

void f(); // forward declaration

int main()
{
    const double pi = 3.14; //OK
    int i = f(2); //OK. f is forward-declared
    std::string str; // OK std::string is declared in <string> header
    C obj; // error! C not yet declared.
    j = 0; // error! No type specified.
    auto k = 0; // OK. type inferred as int by compiler.
}

int f(int i)
{
    return i + 42;
}

namespace N {
   class C{/*...*/};
}
```

줄 5에서는 `main` 함수가 선언 됩니다. 줄 7에서는 `pi` 이라는 **const** 변수를 선언 하 고 *초기화*합니다. 줄 8에서 정수 `i`는 함수 `f`생성 된 값을 사용 하 여 선언 되 고 초기화 됩니다. 이름 `f`은 줄 3의 *전방 선언* 으로 인해 컴파일러에 표시 됩니다.

9 번 줄에서 `C` 형식의 `obj` 라는 변수가 선언 되었습니다. 그러나이 선언에서는 `C`이 프로그램에서 나중에 선언 되지 않고 앞으로 선언 되지 않기 때문에 오류가 발생 합니다. 오류를 해결 하려면 `main` 하기 전에 `C`의 전체 *정의* 를 이동 하거나 앞으로 선언을 추가 합니다. 이 동작은 소스 파일의 선언 지점 앞에서 C#함수 및 클래스를 사용할 수 있는 등의 다른 언어와는 다릅니다.

줄 10에서는 `std::string` 형식의 `str` 라는 변수가 선언 됩니다. 이름 `std::string`은 줄 1의 소스 파일에 병합 되는 `string` [헤더 파일](header-files-cpp.md) 에 도입 되기 때문에 표시 됩니다. `std`은 `string` 클래스가 선언 되는 네임 스페이스입니다.

줄 11에서는 `j` 이름이 선언 되지 않았기 때문에 오류가 발생 합니다. JavaScript와 같은 다른 언어와 달리 선언은 형식을 제공 해야 합니다. 12 번 줄에는 `auto` 키워드가 사용 됩니다 .이 키워드는 초기화 된 값을 기준으로 `k` 형식을 유추 하도록 컴파일러에 지시 합니다. 이 경우 컴파일러는 형식에 대 한 `int`를 선택 합니다.  

## <a name="declaration-scope"></a>선언 범위

선언에 의해 도입 된 이름은 선언이 발생 하는 *범위* 내에서 유효 합니다. 이전 예제에서 `main` 함수 내에 선언 된 변수는 *지역 변수*입니다. *전역 범위*에서 기본이 아닌 `i` 이라는 다른 변수를 선언할 수 있으며 완전히 분리 된 엔터티입니다. 그러나 이러한 이름의 중복은 프로그래머의 혼동 및 오류를 일으킬 수 있으므로 피해 야 합니다. 21 줄에서 `C` 클래스는 네임 스페이스 `N`의 범위에서 선언 됩니다. 네임 스페이스를 사용 하면 *이름 충돌*을 방지할 수 있습니다. 대부분 C++ 의 표준 라이브러리 이름은 `std` 네임 스페이스 내에서 선언 됩니다. 범위 규칙이 선언과 상호 작용 하는 방법에 대 한 자세한 내용은 [범위](../cpp/scope-visual-cpp.md)를 참조 하세요.

## <a name="definitions"></a>정의

함수, 클래스, 열거형 및 상수 변수를 비롯 한 일부 엔터티는 선언 되는 것 외에도 정의 해야 합니다. *정의* 는 엔터티가 프로그램에서 나중에 사용 될 때 기계어 코드를 생성 하는 데 필요한 모든 정보를 컴파일러에 제공 합니다. 앞의 예제에서 줄 3에는 함수 `f`에 대 한 선언이 포함 되어 있지만 함수에 대 한 *정의* 는 15 ~ 18 줄로 제공 됩니다. 21 번째 줄에서는 클래스가 정의 된 경우를 제외 하 고는 클래스 `C` 선언 되 고 정의 됩니다. 상수 변수는 선언 된 문과 동일한 문에서 값을 할당 한 경우에 정의 되어야 합니다. 컴파일러에서 할당할 공간의 크기를 알고 있으므로 `int`와 같은 기본 제공 형식의 선언이 자동으로 정의 됩니다.

다음 예제에서는 정의 인 선언도 보여 줍니다.

```cpp
// Declare and define int variables i and j.
int i;
int j = 10;

// Declare enumeration suits.
enum suits { Spades = 1, Clubs, Hearts, Diamonds };

// Declare class CheckBox.
class CheckBox : public Control
{
public:
    Boolean IsChecked();
    virtual int     ChangeState() = 0;
};
```

정의가 아닌 몇 가지 선언은 다음과 같습니다.

```cpp
extern int i;
char *strchr( const char *Str, const char Target );
```

## <a name="typedefs-and-using-statements"></a>Typedef 및 using 문

이전 버전의 C++에서는 [typedef](aliases-and-typedefs-cpp.md) 키워드를 사용 하 여 다른 이름의 *별칭인* 새 이름을 선언 합니다. 예를 들어 `std::string` 형식은 `std::basic_string<char>`의 또 다른 이름입니다. 프로그래머가 실제 이름이 아니라 typedef 이름을 사용 하는 이유는 명확 해야 합니다. 현대 C++에서 [using](aliases-and-typedefs-cpp.md) 키워드는 typedef 보다 선호 되지만 개념은 동일 합니다. 이미 선언 되 고 정의 된 엔터티에 대해 새 이름이 선언 됩니다.

## <a name="static-class-members"></a>정적 클래스 멤버

정적 클래스 데이터 멤버는 클래스의 모든 개체에서 공유 하는 불연속 변수 이므로 클래스 정의 외부에서 정의 되 고 초기화 되어야 합니다. 자세한 내용은 [클래스](../cpp/classes-and-structs-cpp.md)를 참조 하세요.

## <a name="extern-declarations"></a>extern 선언

프로그램 C++ 에는 둘 이상의 [컴파일 단위가](header-files-cpp.md)포함 될 수 있습니다. 별도의 컴파일 단위에 정의 된 엔터티를 선언 하려면 [extern](extern-cpp.md) 키워드를 사용 합니다. 선언에 있는 정보는 컴파일러에 충분 하지만 링크 단계에서 엔터티의 정의를 찾을 수 없는 경우 링커에서 오류가 발생 합니다.

## <a name="in-this-section"></a>섹션 내용

[스토리지 클래스](storage-classes-cpp.md)<br/>
[const](const-cpp.md)<br/>
[constexpr](constexpr-cpp.md)<br/>
[extern](extern-cpp.md)<br/>
[이니셜라이저](initializers.md)<br/>
[별칭 및 typedef](aliases-and-typedefs-cpp.md)<br/>
[선언 사용](using-declaration.md)<br/>
[volatile](volatile-cpp.md)<br/>
[decltype](decltype-cpp.md)<br/>
[의 특성C++](attributes.md)<br/>

## <a name="see-also"></a>참고 항목

[기본 개념](../cpp/basic-concepts-cpp.md)<br/>
