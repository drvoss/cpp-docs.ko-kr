---
title: -CLR을 지정하는 경우 예외 처리 동작의 차이점
ms.date: 11/04/2016
helpviewer_keywords:
- EXCEPTION_CONTINUE_EXECUTION macro
- set_se_translator function
ms.assetid: 2e7e8daf-d019-44b0-a51c-62d7aaa89104
ms.openlocfilehash: 940d297ff77248ba9e9980f7032b5d722d95c7eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364370"
---
# <a name="differences-in-exception-handling-behavior-under-clr"></a>/CLR을 지정하는 경우 예외 처리 동작의 차이점

[관리되는 예외 사용의 기본 개념은](../dotnet/basic-concepts-in-using-managed-exceptions.md) 관리되는 응용 프로그램의 예외 처리에 대해 설명합니다. 이 항목에서는 예외 처리의 표준 동작과 몇 가지 제한 사항에 대해 자세히 설명합니다. 자세한 내용은 [_set_se_translator 함수를](../c-runtime-library/reference/set-se-translator.md)참조하십시오.

## <a name="jumping-out-of-a-finally-block"></a><a name="vcconjumpingoutofafinallyblock"></a>마침내 블록에서 점프

네이티브 C/C++ 코드에서는 경고를 생성하지만 구조화된 예외 처리(SEH)를 사용하여 __**finally** 블록밖으로 점프할 수 있습니다.  [/clr에서](../build/reference/clr-common-language-runtime-compilation.md) **마지막으로** 블록밖으로 점프하면 오류가 발생합니다.

```cpp
// clr_exception_handling_4.cpp
// compile with: /clr
int main() {
   try {}
   finally {
      return 0;   // also fails with goto, break, continue
    }
}   // C3276
```

## <a name="raising-exceptions-within-an-exception-filter"></a><a name="vcconraisingexceptionswithinanexceptionfilter"></a>예외 필터 내에서 예외 발생

관리 코드 내에서 [예외 필터를](../cpp/writing-an-exception-filter.md) 처리하는 동안 예외가 발생하면 예외가 catch되고 필터가 0을 반환하는 것처럼 처리됩니다.

이는 중첩된 예외가 발생하는 네이티브 코드의 동작과 는 대조적으로, **EXCEPTION_RECORD** 구조의 **ExceptionRecord** 필드(GetExceptionInformation에서 반환됨)가 설정되고 [GetExceptionInformation](/windows/win32/Debug/getexceptioninformation) **ExceptionFlags** 필드가 0x10 비트를 설정합니다. 다음 예제에서는 이러한 동작의 차이를 보여 줍니다.

```cpp
// clr_exception_handling_5.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

#ifndef false
#define false 0
#endif

int *p;

int filter(PEXCEPTION_POINTERS ExceptionPointers) {
   PEXCEPTION_RECORD ExceptionRecord =
                     ExceptionPointers->ExceptionRecord;

   if ((ExceptionRecord->ExceptionFlags & 0x10) == 0) {
      // not a nested exception, throw one
      *p = 0; // throw another AV
   }
   else {
      printf("Caught a nested exception\n");
      return 1;
    }

   assert(false);

   return 0;
}

void f(void) {
   __try {
      *p = 0;   // throw an AV
   }
   __except(filter(GetExceptionInformation())) {
      printf_s("We should execute this handler if "
                 "compiled to native\n");
    }
}

int main() {
   __try {
      f();
   }
   __except(1) {
      printf_s("The handler in main caught the "
               "exception\n");
    }
}
```

### <a name="output"></a>출력

```Output
Caught a nested exception
We should execute this handler if compiled to native
```

## <a name="disassociated-rethrows"></a><a name="vccondisassociatedrethrows"></a>연관되지 제거된 재throw

**/clr는** catch 처리기 외부에서 예외를 다시 throw하는 것을 지원하지 않습니다(연결이 해제된 다시 throw라고 함). 이 유형의 예외는 표준 C++ 다시 throw로 처리됩니다. 활성 관리되는 예외가 있을 때 연결이 해제된 다시 throw가 발생하면 예외가 C++ 예외로 래핑된 다음 다시 throw됩니다. 이 형식의 예외는 형식의 <xref:System.Runtime.InteropServices.SEHException>예외로만 catch할 수 있습니다.

다음 예제에서는 관리되는 예외를 C++ 예외로 다시 throw보여 줍니다.

```cpp
// clr_exception_handling_6.cpp
// compile with: /clr
using namespace System;
#include <assert.h>
#include <stdio.h>

void rethrow( void ) {
   // This rethrow is a dissasociated rethrow.
   // The exception would be masked as SEHException.
   throw;
}

int main() {
   try {
      try {
         throw gcnew ApplicationException;
      }
      catch ( ApplicationException^ ) {
         rethrow();
         // If the call to rethrow() is replaced with
         // a throw statement within the catch handler,
         // the rethrow would be a managed rethrow and
         // the exception type would remain
         // System::ApplicationException
      }
   }

    catch ( ApplicationException^ ) {
      assert( false );

      // This will not be executed since the exception
      // will be masked as SEHException.
    }
   catch ( Runtime::InteropServices::SEHException^ ) {
      printf_s("caught an SEH Exception\n" );
    }
}
```

### <a name="output"></a>출력

```Output
caught an SEH Exception
```

## <a name="exception-filters-and-exception_continue_execution"></a><a name="vcconexceptionfiltersandexception_continue_execution"></a>예외 필터 및 EXCEPTION_CONTINUE_EXECUTION

필터가 관리되는 응용 프로그램에서 반환되는 `EXCEPTION_CONTINUE_EXECUTION` 경우 필터가 `EXCEPTION_CONTINUE_SEARCH`반환된 것처럼 처리됩니다. 이러한 상수에 대한 자세한 내용은 [try-except 문을](../cpp/try-except-statement.md)참조하십시오.

다음 예제에서는 이러한 차이점을 보여 줍니다.

```cpp
// clr_exception_handling_7.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

int main() {
   int Counter = 0;
   __try {
      __try  {
         Counter -= 1;
         RaiseException (0xe0000000|'seh',
                         0, 0, 0);
         Counter -= 2;
      }
      __except (Counter) {
         // Counter is negative,
         // indicating "CONTINUE EXECUTE"
         Counter -= 1;
      }
    }
    __except(1) {
      Counter -= 100;
   }

   printf_s("Counter=%d\n", Counter);
}
```

### <a name="output"></a>출력

```Output
Counter=-3
```

## <a name="the-_set_se_translator-function"></a><a name="vcconthe_set_se_translatorfunction"></a>_set_se_translator 기능

`_set_se_translator`에 대한 호출로 설정된 변환기 함수는 관리되지 않는 코드에서만 catch에 영향을 줍니다. 다음 예제에서는 이러한 제한을 보여 줍니다.

```cpp
// clr_exception_handling_8.cpp
// compile with: /clr /EHa
#include <iostream>
#include <windows.h>
#include <eh.h>
#pragma warning (disable: 4101)
using namespace std;
using namespace System;

#define MYEXCEPTION_CODE 0xe0000101

class CMyException {
public:
   unsigned int m_ErrorCode;
   EXCEPTION_POINTERS * m_pExp;

   CMyException() : m_ErrorCode( 0 ), m_pExp( NULL ) {}

   CMyException( unsigned int i, EXCEPTION_POINTERS * pExp )
         : m_ErrorCode( i ), m_pExp( pExp ) {}

   CMyException( CMyException& c ) : m_ErrorCode( c.m_ErrorCode ),
                                      m_pExp( c.m_pExp ) {}

   friend ostream& operator <<
                 ( ostream& out, const CMyException& inst ) {
      return out <<  "CMyException[\n" <<
             "Error Code: " << inst.m_ErrorCode <<  "]";
    }
};

#pragma unmanaged
void my_trans_func( unsigned int u, PEXCEPTION_POINTERS pExp ) {
   cout <<  "In my_trans_func.\n";
   throw CMyException( u, pExp );
}

#pragma managed
void managed_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE, 0, 0, 0 );
   }
   catch ( CMyException x ) {}
   catch ( ... ) {
      printf_s("This is invoked since "
               "_set_se_translator is not "
               "supported when /clr is used\n" );
    }
}

#pragma unmanaged
void unmanaged_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE,
                      0, 0, 0 );
   }
   catch ( CMyException x ) {
      printf("Caught an SEH exception with "
             "exception code: %x\n", x.m_ErrorCode );
    }
    catch ( ... ) {}
}

// #pragma managed
int main( int argc, char ** argv ) {
   _set_se_translator( my_trans_func );

   // It does not matter whether the translator function
   // is registered in managed or unmanaged code
   managed_func();
   unmanaged_func();
}
```

### <a name="output"></a>출력

```Output
This is invoked since _set_se_translator is not supported when /clr is used
In my_trans_func.
Caught an SEH exception with exception code: e0000101
```

## <a name="see-also"></a>참고 항목

[예외 처리](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[MSVC의 예외 처리](../cpp/exception-handling-in-visual-cpp.md)
