---
title: 컴파일러 오류 C2714
ms.date: 07/22/2020
f1_keywords:
- C2714
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
ms.openlocfilehash: d3f733f065af5b3217dc19d46b46e504d39151f4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225412"
---
# <a name="compiler-error-c2714"></a>컴파일러 오류 C2714

> `alignof(void)`허용 되지 않음

잘못 된 값이 연산자에 전달 되었습니다.

## <a name="remarks"></a>설명

자세한 내용은 [ `alignof` operator](../../cpp/alignof-operator.md) 를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C2714를 생성 합니다.

```cpp
// C2714.cpp
int main() {
   return alignof(void);   // C2714
   return alignof(char);   // OK
}
```
