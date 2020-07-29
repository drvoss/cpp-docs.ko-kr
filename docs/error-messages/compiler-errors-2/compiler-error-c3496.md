---
title: 컴파일러 오류 C3496
ms.date: 11/04/2016
f1_keywords:
- C3496
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
ms.openlocfilehash: 993d391f28a59afc8926748f2e6f34ab441657dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228858"
---
# <a name="compiler-error-c3496"></a>컴파일러 오류 C3496

'this'는 항상 값으로 캡처됩니다. '&'가 무시되었습니다.

포인터를 참조로 캡처할 수 없습니다 **`this`** .

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- **`this`** 값으로 포인터를 캡처합니다.

## <a name="example"></a>예제

다음 예제에서는 포인터에 대 한 참조가 **`this`** 람다 식의 캡처 목록에 나타나기 때문에 C3496를 생성 합니다.

```cpp
// C3496.cpp
// compile with: /c

class C
{
   void f()
   {
      [&this] {}(); // C3496
   }
};
```

## <a name="see-also"></a>참고 항목

[람다 식](../../cpp/lambda-expressions-in-cpp.md)
