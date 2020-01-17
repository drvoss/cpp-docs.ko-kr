---
title: C++프로그램 종료
description: 언어 프로그램을 C++exit 하는 방법을 설명 합니다.
ms.date: 01/15/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
no-loc:
- exit
- abort
- return
- main
- atexit
- void
ms.openlocfilehash: f83c9d5da5b0a1127603a97fd7946e9cca43a7a5
ms.sourcegitcommit: e93f3e6a110fe38bc642055bdf4785e620d4220f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76123957"
---
# <a name="c-program-termination"></a>C++프로그램 종료

C++에서는 다음과 같은 방법으로 프로그램을 exit 수 있습니다.

- [exit](exit-function.md) 함수를 호출 합니다.
- [abort](abort-function.md) 함수를 호출 합니다.
- `main`에서 [return](return-statement-cpp.md) 문을 실행 합니다.

## <a name="opno-locexit-function"></a>exit 함수

\<stdlib.h >에 선언 된 [exit](../c-runtime-library/reference/exit-exit-exit.md) 함수는 C++ 프로그램을 종료 합니다. `exit` 인수로 제공 된 값은 프로그램의 return 코드 또는 exit 코드로 운영 체제에 반환 됩니다. 규칙에 따라 return 코드 0은 프로그램이 성공적으로 완료 되었음을 의미 합니다. \<stdlib.h >에 정의 된 상수 EXIT_FAILURE 및 EXIT_SUCCESS를 사용 하 여 프로그램의 성공 또는 실패를 나타낼 수 있습니다.

`main` 함수에서 **return** 문을 실행 하는 것은 return 값을 인수로 사용 하 여 `exit` 함수를 호출 하는 것과 같습니다.

## <a name="opno-locabort-function"></a>abort 함수

표준 포함 파일 \<stdlib.h >에도 선언 된 [abort](../c-runtime-library/reference/abort.md) 함수는 C++ 프로그램을 종료 합니다. `exit`와 `abort`의 차이점은 `exit` C++ 런타임 종료 처리를 수행할 수 있도록 하는 것입니다 (전역 개체 소멸자가 호출 됨). 반면 `abort`는 프로그램을 즉시 종료 합니다. `abort` 함수는 초기화 된 전역 정적 개체에 대 한 일반적인 소멸 프로세스를 무시 합니다. 또한 [atexit](../c-runtime-library/reference/atexit.md) 함수를 사용 하 여 지정 된 특별 한 처리를 무시 합니다.

## <a name="opno-locatexit-function"></a>atexit 함수

[atexit](../c-runtime-library/reference/atexit.md) 함수를 사용 하 여 프로그램 종료 전에 실행 되는 작업을 지정 합니다. **atexit** 를 호출 하기 전에 초기화 된 전역 정적 개체는 exit처리 함수를 실행 하기 전에 제거 됩니다.

## <a name="opno-locreturn-statement-in-opno-locmain"></a>main의 return 문

`main`에서 [return](return-statement-cpp.md) 문을 실행 하는 것은 `exit` 함수를 호출 하는 것과 기능적으로 동일 합니다. 다음 예제를 참조하세요.

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

위의 예제에서 `exit` 문과 **return** 문은 기능적으로 동일 합니다. 그러나에 C++ 는 **void** 이외의 return 형식이 포함 된 함수가 값을 return 해야 합니다. **return** 문을 사용 하면 `main`값을 return 수 있습니다.

## <a name="destruction-of-static-objects"></a>정적 개체 소멸

`exit`를 호출 하거나 `main`에서 **return** 문을 실행 하는 경우 정적 개체는 초기화 순서의 역순으로 소멸 됩니다 (있는 경우 `atexit`에 대 한 호출 후). 다음 예제에서는 이러한 초기화 및 정리가 작동하는 방법을 보여 줍니다.

### <a name="example"></a>예

다음 예에서는 `sd1` 및 `sd2` 정적 개체를 `main`항목 앞으로 만들고 초기화 합니다. 이 프로그램이 **return** 문을 사용 하 여 종료 된 후에는 먼저 `sd2` 제거 된 후 `sd1`합니다. `ShowData` 클래스에 대한 소멸자가 이 정적 개체와 연결된 파일을 닫습니다.

```cpp
// using_exit_or_return1.cpp
#include <stdio.h>
class ShowData {
public:
   // Constructor opens a file.
   ShowData( const char *szDev ) {
   errno_t err;
      err = fopen_s(&OutputDev, szDev, "w" );
   }

   // Destructor closes the file.
   ~ShowData() { fclose( OutputDev ); }

   // Disp function shows a string on the output device.
   void Disp( char *szData ) {
      fputs( szData, OutputDev );
   }
private:
   FILE *OutputDev;
};

//  Define a static object of type ShowData. The output device
//   selected is "CON" -- the standard output device.
ShowData sd1 = "CON";

//  Define another static object of type ShowData. The output
//   is directed to a file called "HELLO.DAT"
ShowData sd2 = "hello.dat";

int main() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

범위를 벗어나면 소멸되도록 블록 범위를 사용해 `ShowData` 개체를 선언하여 이 코드를 작성할 수도 있습니다.

```cpp
int main() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>참조

[main 함수 및 명령줄 인수](main-function-command-line-args.md)
