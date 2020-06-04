---
title: 컴파일러 경고(수준 1) C4160
ms.date: 08/27/2018
f1_keywords:
- C4160
helpviewer_keywords:
- C4160
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
ms.openlocfilehash: 8eb53d3f00c717df0e657ede3de6dd71d4a0bb47
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176171"
---
# <a name="compiler-warning-level-1-c4160"></a>컴파일러 경고(수준 1) C4160

> #<a name="pragma-pop--did-not-find-previously-pushed-identifier-identifier"></a>pragma (pop,...): 이전에 푸시한 '*identifier*' 식별자를 찾지 못했습니다.

## <a name="remarks"></a>주의

소스 코드의 pragma 문에서 푸시되지 않은 식별자를 표시하려고 합니다. 이 경고를 방지하려면 표시 중인 식별자가 올바르게 푸시되었는지 확인합니다.

## <a name="example"></a>예제

다음 예제에서는 C4160를 생성 하 고 수정 하는 방법을 보여 줍니다.

```cpp
// C4160.cpp
// compile with: /W1
#pragma pack(push)

#pragma pack(pop, id)   // C4160
// use identifier when pushing to resolve the warning
// #pragma pack(push, id)

int main() {
}
```
