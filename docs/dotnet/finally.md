---
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: 2574ba5a10bbf5eddc68d6e0265d5dfc99c6d8fc
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545098"
---
# <a name="finally"></a>finally

`try` 및 `catch` 절 외에도 CLR 예외 처리는 `finally` 절을 지원 합니다. 의미 체계는 SEH (구조적 예외 처리)의 `__finally` 블록과 동일 합니다. `__finally` 블록은 `try` 또는 `catch` 블록 뒤에 올 수 있습니다.

## <a name="remarks"></a>주의

`finally` 블록의 목적은 예외가 발생 한 후 남은 리소스를 정리 하는 것입니다. 예외가 throw 되지 않은 경우에도 `finally` 블록은 항상 실행 됩니다. `catch` 블록은 연결 된 `try` 블록 내에서 관리 되는 예외가 throw 되는 경우에만 실행 됩니다.

`finally`는 상황에 맞는 키워드입니다. 자세한 내용은 상황에 맞는 [키워드](../extensions/context-sensitive-keywords-cpp-component-extensions.md) 를 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는 간단한 `finally` 블록을 보여 줍니다.

```cpp
// keyword__finally.cpp
// compile with: /clr
using namespace System;

ref class MyException: public System::Exception{};

void ThrowMyException() {
   throw gcnew MyException;
}

int main() {
   try {
      ThrowMyException();
   }
   catch ( MyException^ e ) {
      Console::WriteLine(  "in catch" );
      Console::WriteLine( e->GetType() );
   }
   finally {
      Console::WriteLine(  "in finally" );
   }
}
```

```Output
in catch
MyException
in finally
```

## <a name="see-also"></a>참고 항목

[예외 처리](../extensions/exception-handling-cpp-component-extensions.md)
