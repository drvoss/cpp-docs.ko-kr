---
title: 컴파일러 오류 C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 48012c0fe31b2017cad29cc98992c9b1121efa7c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221187"
---
# <a name="compiler-error-c2390"></a>컴파일러 오류 C2390

' identifier ': ' 지정자 ' 저장소 클래스가 잘못 되었습니다.

저장소 클래스가 전역 범위 식별자에 적합 하지 않습니다. 기본 저장소 클래스가 잘못 된 클래스 대신 사용 됩니다.

가능한 해결 방법은 다음과 같습니다.

- 식별자가 함수인 경우 저장소를 사용 하 여 선언 **`extern`** 합니다.

- 식별자가 정식 매개 변수 또는 지역 변수인 경우 자동 저장소를 사용 하 여 선언 합니다.

- 식별자가 전역 변수인 경우 저장소 클래스 (자동 저장소)를 사용 하지 않고 선언 합니다.

## <a name="example"></a>예제

- 다음 샘플에서는 C2390를 생성 합니다.

```cpp
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```
