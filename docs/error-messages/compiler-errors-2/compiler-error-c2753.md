---
title: 컴파일러 오류 C2753
ms.date: 11/04/2016
f1_keywords:
- C2753
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
ms.openlocfilehash: ea2901c998ac1a44ad142779e7ce48bfffff66c2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202156"
---
# <a name="compiler-error-c2753"></a>컴파일러 오류 C2753

'*template*': 부분 특수화는 기본 템플릿의 인수 목록과 일치할 수 없습니다.

템플릿 인수 목록이 매개 변수 목록과 일치 하는 경우 컴파일러는이를 동일한 템플릿으로 처리 합니다. 동일한 템플릿을 두 번 정의할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2753를 생성 하 고 수정 하는 방법을 보여 줍니다.

```cpp
// C2753.cpp
// compile with: cl /c C2753.cpp
template<class T>
struct A {};

template<class T>
struct A<T> {};   // C2753
// try the following line instead
// struct A<int> {};

template<class T, class U, class V, class W, class X>
struct B {};
```
