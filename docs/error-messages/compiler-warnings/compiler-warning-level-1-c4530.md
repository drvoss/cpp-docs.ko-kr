---
title: 컴파일러 경고(수준 1) C4530
description: Microsoft C++ 컴파일러 경고 C4530에 대한 참조 가이드입니다.
ms.date: 04/02/2020
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: 9de88a4b0b6c7176ff82b68c92d09d9fe75a70b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369779"
---
# <a name="compiler-warning-level-1-c4530"></a>컴파일러 경고(수준 1) C4530

> C ++ 예외 처리기가 사용되지만 해제 의미 체계는 사용할 수 없습니다. 지정 /EHsc

코드는 C++ 예외 처리를 사용하지만 [/EHsc는](../../build/reference/eh-exception-handling-model.md) 컴파일러 옵션에 포함되지 않았습니다.

## <a name="remarks"></a>설명

컴파일러에는 **`/EHsc`** 예외 처리를 위해 C++ 표준을 따르는 C++ 코드를 빌드하는 옵션이 필요합니다. 표준 *C++는* 예외가 throw되는 위치와 예외가 발생한 위치 사이에 생성된 개체 및 스택 프레임을 삭제하고 해당 리소스를 복구해야 함을 지정합니다. 이 프로세스를 *스택 해제라고 합니다.*

이 **`/EHsc`** 옵션은 예외가 포함된 스택 프레임을 통과할 때 자동 저장소 개체에서 소멸자를 호출하는 코드를 생성하도록 컴파일러에 지시합니다. *자동 저장소* 개체는 로컬 변수와 같이 스택에 할당된 개체입니다. 함수가 호출될 때 자동으로 할당되고 함수가 반환될 때 자동으로 해제되기 때문에 자동 저장소라고 합니다. *스택 프레임은* 함수가 호출될 때 스택에 배치되는 데이터와 자동 저장소를 말합니다.

예외가 throw되면 여러 스택 프레임을 통해 이동한 후 catch할 수 있습니다. 이러한 스택 프레임은 예외가 역호출 순서로 통과할 때 해제되어야 합니다. 각 스택 프레임의 자동 저장소 개체는 리소스를 깨끗하게 복구하기 위해 소멸되어야 합니다. 함수가 정상적으로 반환될 때 자동으로 발생하는 것과 동일한 소멸 및 복구 프로세스입니다.

**`/EHsc`** 이 옵션을 사용할 수 없는 경우 throw 함수와 예외가 catch된 함수 사이의 스택 프레임에 있는 자동 저장소 개체가 소멸되지 않습니다. **try** 또는 **catch** 블록에서 생성된 자동 저장소 개체만 소멸되어 상당한 리소스 누수 및 기타 예기치 않은 동작이 발생할 수 있습니다.

실행 수에 예외를 throw할 수 없는 경우 이 경고를 무시해도 됩니다. 일부 코드에는 다른 예외 처리 옵션이 필요할 수 있습니다. 자세한 내용은 [/EH](../../build/reference/eh-exception-handling-model.md)를 참조하십시오.

## <a name="example"></a>예제

다음 샘플은 C4530을 생성합니다.

```cpp
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

경고를 해결하기 **`/EHsc`** 위해 샘플을 컴파일합니다.
