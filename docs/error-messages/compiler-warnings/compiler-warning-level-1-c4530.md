---
title: 컴파일러 경고(수준 1) C4530
ms.date: 11/04/2016
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: 69ca60e2cba338bf1bd1ac3470e583739e72a68e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186454"
---
# <a name="compiler-warning-level-1-c4530"></a>컴파일러 경고(수준 1) C4530

C++예외 처리기를 사용 했지만 해제 의미 체계가 활성화 되지 않았습니다. /EHsc 지정

C++예외 처리를 사용 했지만 [/ehsc](../../build/reference/eh-exception-handling-model.md) 를 선택 하지 않았습니다.

/EHsc 옵션을 사용 하도록 설정 하지 않은 경우에는 throw를 수행 하는 함수와 throw를 catch 하는 함수 사이에서 프레임에 자동 저장소가 있는 개체가 제거 되지 않습니다. 그러나 **try** 또는 **catch** 블록에서 자동 저장소가 생성 된 개체는 삭제 됩니다.

다음 샘플에서는 C4530를 생성 합니다.

```cpp
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

이 경고를 해결 하려면/EHsc를 사용 하 여 샘플을 컴파일합니다.
