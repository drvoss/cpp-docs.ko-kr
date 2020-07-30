---
title: C + + 프로그램 종료
description: :::no-loc(exit):::C + + 언어 프로그램의 방법을 설명 합니다.
ms.date: 01/15/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- :::no-loc(exit):::ing applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
no-loc:
- ':::no-loc(exit):::'
- ':::no-loc(abort):::'
- ':::no-loc(return):::'
- ':::no-loc(main):::'
- ':::no-loc(atexit):::'
- ':::no-loc(void):::'
ms.openlocfilehash: 216aef5dbe8d110f9d75d43b5009b89fc5bfda51
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227181"
---
# <a name="c-program-termination"></a>C + + 프로그램 종료

C + +에서는 :::no-loc(exit)::: 다음과 같은 방법으로 프로그램을 수행할 수 있습니다.

- 함수를 호출 [:::no-loc(exit):::](:::no-loc(exit):::-function.md) 합니다.
- 함수를 호출 [:::no-loc(abort):::](:::no-loc(abort):::-function.md) 합니다.
- [:::no-loc(return):::](:::no-loc(return):::-statement-cpp.md)에서 문을 실행 `:::no-loc(main):::` 합니다.

## <a name="no-locexit-function"></a>:::no-loc(exit)::: 함수

[:::no-loc(exit):::](../c-runtime-library/reference/:::no-loc(exit):::-:::no-loc(exit):::-:::no-loc(exit):::.md)에 선언 된 함수는 \<stdlib.h> c + + 프로그램을 종료 합니다. 에 대 한 인수로 제공 되는 값은 `:::no-loc(exit):::` :::no-loc(return)::: 프로그램의 :::no-loc(return)::: 코드 또는 코드로 운영 체제에 적용 됩니다 :::no-loc(exit)::: . 규칙에 따라 :::no-loc(return)::: 코드 0은 프로그램이 성공적으로 완료 되었음을 의미 합니다. 에 정의 된 상수 EXIT_FAILURE 및 EXIT_SUCCESS를 사용 \<stdlib.h> 하 여 프로그램의 성공 또는 실패를 나타낼 수 있습니다.

**`:::no-loc(return):::`** 함수에서 문을 실행 `:::no-loc(main):::` 하는 것은 값을 인수로 사용 하 여 함수를 호출 하는 것과 같습니다 `:::no-loc(exit):::` :::no-loc(return)::: .

## <a name="no-locabort-function"></a>:::no-loc(abort)::: 함수

[:::no-loc(abort):::](../c-runtime-library/reference/:::no-loc(abort):::.md)표준 포함 파일에도 선언 된 함수는 \<stdlib.h> c + + 프로그램을 종료 합니다. 와의 차이점 `:::no-loc(exit):::` 은 `:::no-loc(abort):::` `:::no-loc(exit):::` c + + 런타임 종료 처리를 수행할 수 있도록 하는 것입니다 (전역 개체 소멸자가 호출 됨). 반면는 `:::no-loc(abort):::` 프로그램을 즉시 종료 합니다. `:::no-loc(abort):::`함수는 초기화 된 전역 정적 개체에 대 한 일반적인 소멸 프로세스를 무시 합니다. 또한 함수를 사용 하 여 지정 된 특별 한 처리를 무시 [:::no-loc(atexit):::](../c-runtime-library/reference/:::no-loc(atexit):::.md) 합니다.

## <a name="no-locatexit-function"></a>:::no-loc(atexit)::: 함수

[:::no-loc(atexit):::](../c-runtime-library/reference/:::no-loc(atexit):::.md)프로그램 종료 전에 실행 되는 작업을 지정 하려면 함수를 사용 합니다. 를 호출 하기 전에 초기화 된 전역 정적 개체 **:::no-loc(atexit):::** 는 처리 함수를 실행 하기 전에 제거 되지 않습니다 :::no-loc(exit)::: .

## <a name="no-locreturn-statement-in-no-locmain"></a>:::no-loc(return):::문:::no-loc(main):::

[:::no-loc(return):::](:::no-loc(return):::-statement-cpp.md)에서 문을 실행 하는 것 `:::no-loc(main):::` 은 함수를 호출 하는 것과 기능적으로 동일 `:::no-loc(exit):::` 합니다. 다음과 같은 예제를 참조하세요.

```cpp
// :::no-loc(return):::_statement.cpp
#include <stdlib.h>
int :::no-loc(main):::()
{
    :::no-loc(exit):::( 3 );
    :::no-loc(return)::: 3;
}
```

`:::no-loc(exit):::` **`:::no-loc(return):::`** 위의 예제에서 및 문은 기능적으로 동일 합니다. 그러나 c + +에서는 값이 아닌 형식이 포함 된 함수가 필요 :::no-loc(return)::: **`:::no-loc(void):::`** :::no-loc(return)::: 합니다. **`:::no-loc(return):::`** 문은의 값을 사용할 수 있습니다 :::no-loc(return)::: `:::no-loc(main):::` .

## <a name="destruction-of-static-objects"></a>정적 개체 소멸

`:::no-loc(exit):::`에서 문을 호출 하거나 실행 하는 경우 **`:::no-loc(return):::`** `:::no-loc(main):::` 정적 개체는 초기화 (있는 경우)의 역순으로 소멸 됩니다 `:::no-loc(atexit):::` . 다음 예제에서는 이러한 초기화 및 정리가 작동하는 방법을 보여 줍니다.

### <a name="example"></a>예제

다음 예제에서는 `sd1` `sd2` 로 진입 하기 전에 정적 개체 및가 만들어지고 초기화 됩니다 `:::no-loc(main):::` . 이 프로그램은 문을 사용 하 여 종료 된 후 **`:::no-loc(return):::`** 에 `sd2` 는 먼저 소멸 된 후에 제거 됩니다 `sd1` . `ShowData` 클래스에 대한 소멸자가 이 정적 개체와 연결된 파일을 닫습니다.

```cpp
// using_:::no-loc(exit):::_or_:::no-loc(return):::1.cpp
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
   :::no-loc(void)::: Disp( char *szData ) {
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

int :::no-loc(main):::() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

범위를 벗어나면 소멸되도록 블록 범위를 사용해 `ShowData` 개체를 선언하여 이 코드를 작성할 수도 있습니다.

```cpp
int :::no-loc(main):::() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>참고 항목

[:::no-loc(main):::함수 및 명령줄 인수](:::no-loc(main):::-function-command-line-args.md)
