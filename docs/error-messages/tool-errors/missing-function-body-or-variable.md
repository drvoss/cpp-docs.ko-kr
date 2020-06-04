---
title: 함수 본문 또는 변수 누락
ms.date: 11/04/2016
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
ms.openlocfilehash: 6d2ef22b90009d320485fb6fe3f7e308ae05c442
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173623"
---
# <a name="missing-function-body-or-variable"></a>함수 본문 또는 변수 누락

함수 프로토타입을 사용 하는 경우 컴파일러는 오류 없이 계속 될 수 있지만 함수 코드 또는 예약 된 가변 공간이 없기 때문에 링커에서 주소에 대 한 호출을 확인할 수 없습니다. 링커가 확인 해야 하는 함수에 대 한 호출을 만들 때까지이 오류가 표시 되지 않습니다.

## <a name="example"></a>예제

프로토타입이 있으면 컴파일러가 함수를 사용할 수 있다고 생각할 수 있으므로 main의 함수 호출은 LNK2019를 발생 시킵니다.  링커가이를 찾지 못합니다.

```cpp
// LNK2019_MFBV.cpp
// LNK2019 expected
void DoSomething(void);
int main() {
   DoSomething();
}
```

## <a name="example"></a>예제

에서는 C++클래스 정의의 프로토타입이 아니라 클래스에 대 한 특정 함수 구현을 포함 해야 합니다. 헤더 파일 외부에 클래스를 정의 하는 경우에는 함수 앞에 클래스 이름을 포함 해야 합니다 (`Classname::memberfunction`).

```cpp
// LNK2019_MFBV_2.cpp
// LNK2019 expected
struct A {
   static void Test();
};

// Should be void A::Test() {}
void Test() {}

int main() {
   A AObject;
   AObject.Test();
}
```

## <a name="see-also"></a>참고 항목

[링커 도구 오류 LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
