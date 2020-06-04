---
title: 컴파일러 오류 C3205
ms.date: 11/04/2016
f1_keywords:
- C3205
helpviewer_keywords:
- C3205
ms.assetid: 802d306e-5ff3-4491-8a22-c5f1c072d005
ms.openlocfilehash: e7cb38a687daed93f72655337cd7cd3f25aaa08d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176431"
---
# <a name="compiler-error-c3205"></a>컴파일러 오류 C3205

템플릿 매개 변수 'parameter'의 인수 목록이 없습니다.

[템플릿](../../cpp/templates-cpp.md) 매개 변수가 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3205를 생성합니다.

```cpp
// C3205.cpp
template<template<class> class T> struct A {
   typedef T unparameterized_type;   // C3205
   // try the following line instead
   // typedef T<int> unparameterized_type;
};

template <class T>
struct B {
   typedef int value_type;
};

int main() {
   A<B> x;
}
```
