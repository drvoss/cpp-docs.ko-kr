---
title: ABI 경계의 이식성
description: 인터페이스 C++ 를 이진 인터페이스 경계에서 C 호출 규칙으로 평면화 합니다.
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
ms.openlocfilehash: b3b2b217739ff5900c8ef0329ff3e8909a3fe036
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303313"
---
# <a name="portability-at-abi-boundaries"></a>ABI 경계의 이식성

이진 인터페이스 경계에서 충분히 이식 가능한 형식과 규칙을 사용합니다. "이식 가능한 형식"은 c 기본 제공 형식 또는 C 기본 제공 형식만 포함 하는 구조체입니다. 클래스 형식은 호출자와 호출 수신자가 레이아웃, 호출 규칙 등에 동의 하는 경우에만 사용할 수 있습니다. 이는 둘 다 동일한 컴파일러 및 컴파일러 설정을 사용 하 여 컴파일되는 경우에만 가능 합니다.

## <a name="how-to-flatten-a-class-for-c-portability"></a>C 이식성을 위해 클래스를 평면화하는 방법

다른 컴파일러/언어를 사용 하 여 호출자를 컴파일할 수 있는 경우 특정 호출 규칙을 사용 하 여 **extern "C"** API에 "평면화" 합니다.

```cpp
// class widget {
//   widget();
//   ~widget();
//   double method( int, gadget& );
// };
extern "C" {        // functions using explicit "this"
   struct widget;   // opaque type (forward declaration only)
   widget* STDCALL widget_create();      // constructor creates new "this"
   void STDCALL widget_destroy(widget*); // destructor consumes "this"
   double STDCALL widget_method(widget*, int, gadget*); // method uses "this"
}
```

## <a name="see-also"></a>참고 항목

[다시 시작C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)
