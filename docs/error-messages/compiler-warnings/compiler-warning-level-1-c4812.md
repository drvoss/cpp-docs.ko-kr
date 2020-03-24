---
title: 컴파일러 경고(수준 1) C4812
ms.date: 11/04/2016
f1_keywords:
- C4812
helpviewer_keywords:
- C4812
ms.assetid: a7f5721f-2019-44de-ad62-ed30bac8b1f3
ms.openlocfilehash: 9355886c3ec19e75cc1aa62f8cc41bba9f951d7c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174910"
---
# <a name="compiler-warning-level-1-c4812"></a>컴파일러 경고(수준 1) C4812

사용되지 않는 선언 스타일입니다. 대신 'new_syntax'를 사용하세요.

현재 릴리스의 Visual C++에서는 명시적 생성자 특수화가 지원되지만 이후 릴리스에서는 지원되지 않을 수 있습니다.

다음 샘플에서는 C4812를 생성합니다.

```cpp
// C4812.cpp
// compile with: /W1 /c
template <class T>
class MyClass;

template<class T>
class MyClass<T*> {
   MyClass();
};

template<class T>
MyClass<T*>::MyClass<T*>() {}   // C4812
// try the following line instead
// MyClass<T*>::MyClass() {}
```
