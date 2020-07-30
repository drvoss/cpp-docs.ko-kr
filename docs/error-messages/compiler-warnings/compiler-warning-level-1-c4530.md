---
title: 컴파일러 경고(수준 1) C4530
description: Microsoft c + + 컴파일러 경고 C4530에 대 한 참조 가이드입니다.
ms.date: 04/02/2020
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: fe0a2b4c8eb881327f3e59d66e7e6941f0a2cad8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230664"
---
# <a name="compiler-warning-level-1-c4530"></a>컴파일러 경고(수준 1) C4530

> C + + 예외 처리기를 사용 했지만 해제 의미 체계가 활성화 되지 않았습니다. /EHsc 지정

이 코드는 c + + 예외 처리를 사용 하지만, [/ehsc](../../build/reference/eh-exception-handling-model.md) 는 컴파일러 옵션에 포함 되지 않았습니다.

## <a name="remarks"></a>설명

컴파일러는 **`/EHsc`** 예외 처리를 위해 c + + 표준에 따라 c + + 코드를 빌드하는 옵션이 필요 합니다. 표준 c + + *해제 의미 체계* 는 예외가 throw 되는 위치와 catch 된 위치 간에 생성 된 개체 및 스택 프레임을 제거 하 고 해당 리소스를 복구 하도록 지정 합니다. 이 프로세스는 스택을 해제 *하*는 것으로 알려져 있습니다.

**`/EHsc`** 옵션은 포함 하는 스택 프레임을 통해 예외가 전달 될 때 자동 저장소 개체에서 소멸자를 호출 하는 코드를 생성 하도록 컴파일러에 지시 합니다. *자동 저장소* 개체는 지역 변수와 같이 스택에 할당 되는 개체입니다. 함수가 호출 될 때 자동으로 할당 되 고 반환 될 때 자동으로 해제 되기 때문에 자동 저장소 라고 합니다. *스택 프레임* 은 함수가 호출 될 때 해당 자동 저장소와 함께 스택에 배치 되는 데이터입니다.

예외가 throw 되 면 catch 되기 전에 여러 스택 프레임을 통과할 수 있습니다. 이러한 스택 프레임은 예외를 통해 역방향 호출 순서로 전달 될 때 해제 해야 합니다. 리소스를 완전히 복구 하려면 각 스택 프레임의 자동 저장소 개체를 제거 해야 합니다. 함수는 정상적으로 반환 될 때 자동으로 발생 하는 동일한 소멸 및 복구 프로세스입니다.

**`/EHsc`** 이 옵션을 사용 하도록 설정 하지 않으면 throw 함수와 예외가 catch 되는 함수 사이의 스택 프레임에서 자동 저장소 개체가 제거 되지 않습니다. 또는 블록에서 만든 자동 저장소 개체만 **`try`** **`catch`** 소멸 되며,이로 인해 심각한 리소스 누수 및 기타 예기치 않은 동작이 발생할 수 있습니다.

실행 파일에서 예외가 발생할 수 있는 경우이 경고를 무시 해도 됩니다. 일부 코드에는 다른 예외 처리 옵션이 필요할 수 있습니다. 자세한 내용은 [/Eh](../../build/reference/eh-exception-handling-model.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4530를 생성 합니다.

```cpp
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

을 사용 하 여 샘플을 컴파일하여 **`/EHsc`** 경고를 해결 합니다.
