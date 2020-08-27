---
title: '방법: 네이티브 코드에서 MSIL이 throw한 예외 catch'
description: MSIL에서 throw 된 네이티브 코드에서 예외를 catch 하는 방법의 예입니다.
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions, catching
- catching exceptions, thrown from MSIL
- MSIL, catching exceptions in native code
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
ms.openlocfilehash: b68a771d27e091f86331703b55bc2eb52dfbb41b
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898580"
---
# <a name="how-to-catch-exceptions-in-native-code-thrown-from-msil"></a>방법: 네이티브 코드에서 MSIL이 throw한 예외 catch

네이티브 코드에서는 MSIL에서 네이티브 c + + 예외를 catch 할 수 있습니다.  및를 사용 하 여 CLR 예외를 catch 할 수 있습니다 **`__try`** **`__except`** .

자세한 내용은 [구조적 예외 처리 (C/c + +)](../cpp/structured-exception-handling-c-cpp.md) 및 [예외 및 오류 처리에 대 한 최신 c + + 모범 사례](../cpp/errors-and-exception-handling-modern-cpp.md)를 참조 하세요.

## <a name="example-1"></a>예 1

다음 샘플에서는 두 개의 함수, 즉 네이티브 예외를 throw 하는 모듈과 MSIL 예외를 throw 하는 함수를 정의 합니다.

```cpp
// catch_MSIL_in_native.cpp
// compile with: /clr /c
void Test() {
   throw ("error");
}

void Test2() {
   throw (gcnew System::Exception("error2"));
}
```

## <a name="example-2"></a>예제 2

다음 샘플에서는 네이티브 및 MSIL 예외를 catch 하는 모듈을 정의 합니다.

```cpp
// catch_MSIL_in_native_2.cpp
// compile with: /clr catch_MSIL_in_native.obj
#include <iostream>
using namespace std;
void Test();
void Test2();

void Func() {
   // catch any exception from MSIL
   // should not catch Visual C++ exceptions like this
   // runtime may not destroy the object thrown
   __try {
      Test2();
   }
   __except(1) {
      cout << "caught an exception" << endl;
   }

}

int main() {
   // catch native C++ exception from MSIL
   try {
      Test();
   }
   catch(char * S) {
      cout << S << endl;
   }
   Func();
}
```

```Output
error
caught an exception
```

## <a name="see-also"></a>참조

[예외 처리](../extensions/exception-handling-cpp-component-extensions.md)
