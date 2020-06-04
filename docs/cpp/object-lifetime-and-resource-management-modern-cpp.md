---
title: 개체 수명 및 리소스 관리(RAII)
description: 리소스 누수를 방지 하려면 최신 C++ RAII의 원칙을 따릅니다.
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
ms.openlocfilehash: d30b5296b35bec7f8949057becfaeeea61ef09a0
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078026"
---
# <a name="object-lifetime-and-resource-management-raii"></a>개체 수명 및 리소스 관리(RAII)

관리 되는 언어 C++ 와 달리에는 자동 *가비지 컬렉션이*없습니다. 프로그램이 실행 될 때 힙 메모리 및 기타 리소스를 해제 하는 내부 프로세스입니다. C++ 프로그램은 가져온 모든 리소스를 운영 체제에 반환 해야 합니다. 사용 하지 않는 리소스를 해제 하는 데 실패 하는 것을 *누출*이라고 합니다. 프로세스가 종료 될 때까지 다른 프로그램에서 유출 된 리소스를 사용할 수 없습니다. 특히 메모리 누수는 C 스타일 프로그래밍에서 발생 하는 버그의 일반적인 원인입니다.

최신 C++ 에서는 스택에 개체를 선언 하 여 최대한 많은 힙 메모리를 사용 하지 않도록 방지 합니다. 스택에 대 한 리소스가 너무 크면 개체가 *소유* 해야 합니다. 개체는 초기화 될 때 소유 하 고 있는 리소스를 가져옵니다. 그런 다음 개체는 해당 소멸자에서 리소스를 해제 해야 합니다. 소유 하는 개체 자체가 스택에 선언 됩니다. *리소스를 소유* 하는 개체를 "리소스 획득이 초기화" 또는 RAII 이라고 합니다.

리소스 소유 스택 개체가 범위를 벗어나면 해당 소멸자가 자동으로 호출 됩니다. 이러한 방식으로의 C++ 가비지 수집은 개체 수명과 밀접 하 게 관련 되며 결정적입니다. 리소스는 항상 프로그램의 알려진 지점에서 해제 되므로 사용자가 제어할 수 있습니다. 만 C++에서와 같이 결정적 소멸자 메모리 및 메모리 내 리소스를 균등 하 게 처리할 수 있습니다.

다음 예에서는 `w`간단한 개체를 보여 줍니다. 함수 범위에서 스택에 선언 되며 함수 블록의 끝에서 제거 됩니다. 개체 `w`는 *리소스* (예: 힙 할당 메모리)를 소유 하지 않습니다. 유일한 멤버 `g`은 스택에 선언 되 고 `w`와 함께 범위에서 제외 됩니다. `widget` 소멸자에는 특별 한 코드가 필요 하지 않습니다.

```cpp
class widget {
private:
    gadget g;   // lifetime automatically tied to enclosing object
public:
    void draw();
};

void functionUsingWidget () {
    widget w;   // lifetime automatically tied to enclosing scope
                // constructs w, including the w.g gadget member
    // ...
    w.draw();
    // ...
} // automatic destruction and deallocation for w and w.g
  // automatic exception safety,
  // as if "finally { w.dispose(); w.g.dispose(); }"
```

다음 예제에서 `w`는 메모리 리소스를 소유 하므로 메모리를 삭제 하려면 해당 소멸자에 코드가 있어야 합니다.

```cpp
class widget
{
private:
    int* data;
public:
    widget(const int size) { data = new int[size]; } // acquire
    ~widget() { delete[] data; } // release
    void do_something() {}
};

void functionUsingWidget() {
    widget w(1000000);   // lifetime automatically tied to enclosing scope
                        // constructs w, including the w.data member
    w.do_something();

} // automatic destruction and deallocation for w and w.data

```

C + + 11부터 표준 라이브러리의 스마트 포인터를 사용 하 여 이전 예제를 작성 하는 것이 더 좋은 방법입니다. 스마트 포인터는 소유 하 고 있는 메모리의 할당 및 삭제를 처리 합니다. 스마트 포인터를 사용 하면 `widget` 클래스에서 명시적 소멸자가 필요 하지 않습니다.

```cpp
#include <memory>
class widget
{
private:
    std::unique_ptr<int> data;
public:
    widget(const int size) { data = std::make_unique<int>(size); }
    void do_something() {}
};

void functionUsingWidget() {
    widget w(1000000);   // lifetime automatically tied to enclosing scope
                // constructs w, including the w.data gadget member
    // ...
    w.do_something();
    // ...
} // automatic destruction and deallocation for w and w.data

```

메모리 할당을 위한 스마트 포인터를 사용 하 여 메모리 누수 가능성을 없앨 수 있습니다. 이 모델은 파일 핸들 또는 소켓과 같은 다른 리소스에 대해 작동 합니다. 클래스에서 비슷한 방법으로 리소스를 관리할 수 있습니다. 자세한 내용은 [스마트 포인터](smart-pointers-modern-cpp.md)를 참조 하세요.

디자인은 개체가 C++ 범위를 벗어날 때 소멸 되도록 합니다. 즉, 블록이 종료 될 때 생성의 역순으로 소멸 됩니다. 개체 소멸 될 때 해당 기본 항목 및 멤버는 특정 순서로 삭제 됩니다. 전역 범위에서 블록 외부에 선언 된 개체는 문제를 일으킬 수 있습니다. 전역 개체의 생성자가 예외를 throw 하는 경우 디버깅 하기 어려울 수 있습니다.

## <a name="see-also"></a>참고 항목

[다시 시작C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)
