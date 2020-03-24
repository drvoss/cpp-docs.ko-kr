---
title: 컴파일러 오류 C2144
ms.date: 11/04/2016
f1_keywords:
- C2144
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
ms.openlocfilehash: b917c0a2c15aeb70222c948bce9a6fb275c91068
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207248"
---
# <a name="compiler-error-c2144"></a>컴파일러 오류 C2144

> 구문 오류: '*type*' 앞에는 '*token*'이와 야 합니다.

컴파일러가 *토큰* 을 예상 했으며 대신 *형식을* 찾았습니다.

이 오류는 닫는 중괄호, 오른쪽 괄호 또는 세미콜론이 누락 된 경우에 발생할 수 있습니다.

C2144는 공백 문자가 포함 된 CLR 키워드에서 매크로를 만들려고 할 때에도 발생할 수 있습니다.

형식 전달을 수행 하려는 경우 C2144이 표시 될 수도 있습니다. 자세한 내용은 [형식 전달C++(/cli)](../../extensions/type-forwarding-cpp-cli.md) 을 참조 하세요.

## <a name="examples"></a>예

다음 샘플에서는 C2144를 생성 하 고 수정 하는 방법을 보여 줍니다.

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

다음 샘플에서는 C2144를 생성 하 고 수정 하는 방법을 보여 줍니다.

```cpp
// C2144_2.cpp
// compile with: /clr /c
ref struct X {

   property double MultiDimProp[,,] {   // C2144
   // try the following line instead
   // property double MultiDimProp[int , int, int] {
      double get(int, int, int) { return 1; }
      void set(int i, int j, int k, double l) {}
   }

   property double MultiDimProp2[] {   // C2144
   // try the following line instead
   // property double MultiDimProp2[int] {
      double get(int) { return 1; }
      void set(int i, double l) {}
   }
};
```
