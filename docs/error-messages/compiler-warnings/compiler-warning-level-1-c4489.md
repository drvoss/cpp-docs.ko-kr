---
title: 컴파일러 경고(수준 1) C4489
ms.date: 11/04/2016
f1_keywords:
- C4489
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
ms.openlocfilehash: e9811e9f9c17463fdcd550ffd82af4f81a40bb34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186610"
---
# <a name="compiler-warning-level-1-c4489"></a>컴파일러 경고(수준 1) C4489

' 지정자 ': 인터페이스 메서드 ' method '에 사용할 수 없습니다. 재정의 지정자는 ref 클래스 및 값 클래스 메서드에만 사용할 수 있습니다.

인터페이스 메서드에서 지정자 키워드를 잘못 사용 했습니다.

자세한 내용은 [Override 지정자](../../extensions/override-specifiers-cpp-component-extensions.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4489를 생성 합니다.

```cpp
// C4489.cpp
// compile with: /clr /c /W1
public interface class I {
   void f() new;   // C4489
   virtual void b() override;   // C4489

   void g();   // OK
};
```
