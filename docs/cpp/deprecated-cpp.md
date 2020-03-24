---
title: 사용되지 않음 (C++)
ms.date: 03/28/2017
f1_keywords:
- deprecated_cpp
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
ms.openlocfilehash: e4689d3cb1a1757e2ac3bf4ca9eef7670ad5c655
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189483"
---
# <a name="deprecated-c"></a>사용되지 않음 (C++)

이 항목에서는 사용 되지 않는 Microsoft 전용 declspec 선언에 대해 설명 합니다. C + + 14 `[[deprecated]]` 특성에 대 한 정보 및 해당 특성을 사용 하는 시기에 대 한 지침과 Microsoft 관련 declspec 또는 pragma에 대 한 자세한 내용은 [ C++ 표준 특성](attributes.md)을 참조 하세요.

아래에 설명 된 예외를 제외 하 고 **사용 되지 않는** 선언은 [사용 되지 않는](../preprocessor/deprecated-c-cpp.md) pragma와 동일한 기능을 제공 합니다.

- **사용 되지 않는** 선언을 사용 하면 특정 형식의 함수 오버 로드를 사용 되지 않는 것으로 지정할 수 있지만, pragma 폼은 모든 오버 로드 된 형식의 함수 이름에 적용 됩니다.

- **사용 되지 않는** 선언에서는 컴파일 타임에 표시 되는 메시지를 지정할 수 있습니다. 메시지의 텍스트는 매크로에서 제공될 수 있습니다.

- 매크로는 **사용 되지 않는 pragma에서** 사용 되지 않는 것으로 표시 될 수 있습니다.

컴파일러가 사용 되지 않는 식별자 또는 표준 [`[[deprecated]]`](attributes.md) 특성을 사용 하는 경우 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 경고가 throw 됩니다.

## <a name="example"></a>예제

다음 샘플에서는 함수를 사용되지 않는 것으로 표시하는 방법과 사용되지 않는 함수가 사용되는 경우 컴파일 타임에 표시될 메시지를 지정하는 방법을 보여 줍니다.

```cpp
// deprecated.cpp
// compile with: /W3
#define MY_TEXT "function is deprecated"
void func1(void) {}
__declspec(deprecated) void func1(int) {}
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}
__declspec(deprecated(MY_TEXT)) void func3(int) {}

int main() {
   func1();
   func1(1);   // C4996
   func2(1);   // C4996
   func3(1);   // C4996
}
```

## <a name="example"></a>예제

다음 샘플에서는 클래스를 사용되지 않는 것으로 표시하는 방법과 사용되지 않는 클래스가 사용되는 경우 컴파일 타임에 표시될 메시지를 지정하는 방법을 보여 줍니다.

```cpp
// deprecate_class.cpp
// compile with: /W3
struct __declspec(deprecated) X {
   void f(){}
};

struct __declspec(deprecated("** X2 is deprecated **")) X2 {
   void f(){}
};

int main() {
   X x;   // C4996
   X2 x2;   // C4996
}
```

## <a name="see-also"></a>참고 항목

[__declspec](../cpp/declspec.md)<br/>
[키워드](../cpp/keywords-cpp.md)
