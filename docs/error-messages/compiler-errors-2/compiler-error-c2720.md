---
title: 컴파일러 오류 C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: 24f4329ee631eafc7c2670d9ebf28609c22e7592
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202137"
---
# <a name="compiler-error-c2720"></a>컴파일러 오류 C2720

> '*identifier*': 멤버에는 '*지정자*' 저장소 클래스 지정자를 사용할 때 안 됩니다.

선언 외부의 클래스 멤버에서 스토리지 클래스를 사용할 수 없습니다. 이 오류를 해결 하려면 클래스 선언 외부의 멤버 정의에서 불필요 한 [저장소 클래스](../../cpp/storage-classes-cpp.md) 지정자를 제거 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2720 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```
