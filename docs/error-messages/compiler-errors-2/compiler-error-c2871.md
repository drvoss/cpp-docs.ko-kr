---
title: 컴파일러 오류 C2871
ms.date: 11/04/2016
f1_keywords:
- C2871
helpviewer_keywords:
- C2871
ms.assetid: 44aeb84d-61f0-45e0-8dad-22a3cd46b7f8
ms.openlocfilehash: cc24e5fefe9ffd67dc6b01520ea32805a22f70c3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201684"
---
# <a name="compiler-error-c2871"></a>컴파일러 오류 C2871

' name ':이 이름을 가진 네임 스페이스가 없습니다.

이 오류는 네임 스페이스가 아닌 식별자를 [using](../../cpp/namespaces-cpp.md#using_directives) 지시문에 전달할 때 발생 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2871를 생성 합니다.

```cpp
// C2871.cpp
// compile with: /c
namespace a {
   int fn(int i) { return i; }
}
namespace b {
   using namespace d;   // C2871 because d is not a namespace
   using namespace a;   // OK
}
```
