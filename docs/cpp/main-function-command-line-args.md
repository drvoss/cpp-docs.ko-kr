---
title: 함수 및 명령줄 인수 main (C++)
description: main 함수는 C++ 프로그램의 진입점입니다.
ms.date: 01/15/2019
ms.assetid: c6568ee6-40ab-4ae8-aa44-c99e232f64ac
no-loc:
- main
- wmain
- inline
- static
- _tmain
- void
- exit
- argc
- argv
- envp
- CreateProcess
- GetModuleFileName
- char
- wchar_t
- extern
ms.openlocfilehash: 33753e30304a9bb63c135979d3f20098e6b6401a
ms.sourcegitcommit: e93f3e6a110fe38bc642055bdf4785e620d4220f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76123905"
---
# <a name="opno-locmain-function-and-command-line-arguments"></a>main 함수 및 명령줄 인수

모든 C++ 프로그램에는 `main` 기능이 있어야 합니다. main 함수 없이 C++ *.exe* 프로젝트를 컴파일하려는 경우 컴파일러에서 오류가 발생 합니다. (동적 연결 라이브러리 및 static 라이브러리에는 `main` 함수가 없습니다.) `main` 함수는 소스 코드의 실행을 시작 하지만 프로그램이 `main` 함수를 시작 하기 전에 명시적 이니셜라이저가 없는 모든 static 클래스 멤버가 0으로 설정 됩니다. Microsoft C++에서 전역 static 개체는 `main`를 시작 하기 전에도 초기화 됩니다. 다른 C++ 함수에는 적용 되지 않는 `main` 함수에는 몇 가지 제한 사항이 적용 됩니다. `main` 함수는 다음과 같습니다.

- 오버로드될 수 없습니다([오버로드](function-overloading.md) 참조).
- **inline** 로 선언할 수 없습니다.
- **static** 로 선언할 수 없습니다.
- 주소를 사용할 수 없습니다.
- 호출할 수 없습니다.

main 함수는 언어에 기본 제공 되므로 선언이 없습니다. 이 경우 `main`의 선언 구문은 다음과 같습니다.

```cpp
int main();
int main(int argc, char *argv[], char *envp[]);
```

**Microsoft 전용**

원본 파일에서 유니코드 와이드 문자를 사용 하는 경우 `main`의 와이드 문자 버전인 `wmain`를 사용할 수 있습니다. `wmain`의 선언 구문은 다음과 같습니다.

```cpp
int wmain( );
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);
```

Tchar.h에 정의 된 `_tmain`를 사용할 수도 있습니다. _UNICODE을 정의 하지 않으면 `_tmain` `main`으로 확인 됩니다. _UNICODE가 정의된 경우에는 `_tmain`이 `wmain`으로 확인됩니다.

반환 값이 지정 되지 않은 경우 컴파일러는 반환 값 0을 제공 합니다. 또는 `main` 및 `wmain` 함수를 **void** 반환 (반환 값 없음)으로 선언할 수 있습니다. `main` 또는 `wmain`를 **void** 반환 하는 것으로 선언 하는 경우에는 [return](../cpp/return-statement-in-program-termination-cpp.md) 문을 사용 하 여 부모 프로세스 또는 운영 체제에 exit 코드를 반환할 수 없습니다. `main` 또는 `wmain` **void** 으로 선언 될 때 exit 코드를 반환 하려면 [exit](../cpp/exit-function.md) 함수를 사용 해야 합니다.

**Microsoft 전용 종료**

## <a name="command-line-arguments"></a>명령줄 인수

`main` 또는 `wmain`에 대 한 인수를 사용 하면 인수를 편리 하 게 명령줄 구문 분석 하 고, 선택적으로 환경 변수에 액세스할 수 있습니다. `argc` 및 `argv`의 형식은 언어에서 정의됩니다. `argc`, `argv`및 `envp` 이름은 일반적인 이름 이지만 원하는 이름을 지정할 수 있습니다.

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

인수 정의는 다음과 같습니다.

*argc*<br/>
*argv* 에서 이어지는 인수의 개수를 포함 하는 정수입니다. *argc* 매개 변수는 항상 1 보다 크거나 같습니다.

*argv*<br/>
프로그램의 사용자가 입력한 명령줄 인수를 나타내는 null로 끝나는 문자열의 배열입니다. 규칙에 따라 `argv[0]`은 프로그램이 호출되는 명령이고, `argv[1]`은 첫 번째 명령줄 인수이며 `argv[argc]`는 항상 NULL입니다. 명렬줄 처리를 없애려고 한다면 [명령줄 처리 사용자 지정](../cpp/customizing-cpp-command-line-processing.md)을 참조합니다.

첫 번째 명령줄 인수는 항상 `argv[1]`이고 마지막 인수는 `argv[argc - 1]`입니다.

> [!NOTE]
> 규칙상 `argv[0]`은 프로그램이 호출되는 명령입니다. 그러나 [CreateProcess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) 를 사용 하 여 프로세스를 생성할 수 있으며 첫 번째 인수와 두 번째 인수 (*Lpapplicationname* 및 *lpapplicationname*)를 모두 사용 하는 경우 `argv[0]` 실행 이름이 아닐 수 있습니다. [GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) 를 사용 하 여 실행 파일 이름 및 정규화 된 경로를 검색 합니다.

**Microsoft 전용**

*envp*<br/>
많은 UNIX 시스템에서 일반적인 확장인 *envp* 배열은 Microsoft C++에서 사용 됩니다. 이는 사용자 환경에서 설정된 변수를 나타내는 문자열의 배열입니다. 이 배열은 NULL 항목으로 종료됩니다. **char** (`char *envp[]`)에 대 한 포인터의 배열 또는 **char** (`char **envp`) 포인터에 대 한 포인터로 선언할 수 있습니다. 프로그램에서 `main`대신 `wmain`를 사용 하는 경우 **char** 대신 **wchar_t** 데이터 형식을 사용 합니다. `main`이나 `wmain`에 전달된 환경 블록은 현재 환경의 "변경되지 않는" 복사본입니다. 이후에 `putenv` 또는 `_wputenv`에 대 한 호출을 통해 환경을 변경 하는 경우 현재 환경 (`getenv` 또는 `_wgetenv`에서 반환 되는 `_environ` 또는 `_wenviron` 변수에 의해 반환 됨)이 변경 되지만 envp에서 가리키는 블록은 변경 되지 않습니다. 환경 처리를 하지 않기 위한 정보는 [명령줄 처리 사용자 지정](../cpp/customizing-cpp-command-line-processing.md)을 참조하세요. 이 인수는 C에서는 ANSI와 호환되지만 C++에서는 호환되지 않습니다.

**Microsoft 전용 종료**

### <a name="example"></a>예

다음 예에서는 *argc* , *argv* 및 *envp* 인수를 사용 하 여 `main`하는 방법을 보여 줍니다.

```cpp
// argument_definitions.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;
int main( int argc, char *argv[], char *envp[] ) {
    int iNumberLines = 0;    // Default is no line numbers.

    // If /n is passed to the .exe, display numbered listing
    // of environment variables.

    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )
         iNumberLines = 1;

    // Walk through list of strings until a NULL is encountered.
    for( int i = 0; envp[i] != NULL; ++i ) {
        if( iNumberLines )
            cout << i << ": " << envp[i] << "\n";
    }
}
```

## <a name="parsing-c-command-line-arguments"></a>명령줄 C++ 인수 구문 분석

**Microsoft 전용**

Microsoft C/C++ 시작 코드는 운영 체제 명령줄에서 입력된 인수를 해석할 때 다음 규칙을 사용합니다.

- 인수를 공백이나 탭으로 구분합니다.

- 캐럿 문자(^)는 이스케이프 문자나 구분 기호로 인식되지 않습니다. 해당 문자는 프로그램에서 `argv` 배열로 전달되기 전에 운영 체제의 명령줄 구문 분석기에서 모두 처리됩니다.

- 큰 따옴표로 묶은 문자열("*string*")은 공백의 포함과 상관 없이 단일 인수로 해석됩니다. 따옴표로 묶은 문자열은 인수에 포함될 수 있습니다.

- 백슬래시 다음의 큰따옴표(\\")는 리터럴 큰따옴표 문자(")로 해석됩니다.

- 백슬래시는 큰따옴표 바로 앞에 있지 않으면 리터럴로 해석됩니다.

- 짝수 개의 백슬래시 뒤에 큰 따옴표가 오는 경우 각 쌍의 백슬래시에 대해 하나의 백슬래시가 `argv` 배열에 배치되고 큰 따옴표는 문자열 구분 기호로 해석됩니다.

- 홀수 개의 백슬래시 뒤에 큰 따옴표가 있으면 각 쌍의 백슬래시에 대해 하나의 백슬래시가 `argv` 배열에 배치되고 큰 따옴표는 나머지 백슬래시에 의해 "닫히지 않게"되어 리터럴 이중 인용 부호(")를 `argv`에 넣어야 합니다.

### <a name="example"></a>예

다음 프로그램은 명령줄 인수가 전달되는 방법을 보여줍니다.

```cpp
// command_line_arguments.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
int main( int argc,      // Number of strings in array argv
          char *argv[],   // Array of command-line argument strings
          char *envp[] )  // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    cout << "\nCommand-line arguments:\n";
    for( count = 0; count < argc; count++ )
         cout << "  argv[" << count << "]   "
                << argv[count] << "\n";
}
```

다음 표에서는 앞의 목록에 있는 규칙을 보여주는 예제와 예상 출력을 보여줍니다.

### <a name="results-of-parsing-command-lines"></a>명령줄 구문 분석 결과

|명령줄 입력|argv[1]|argv[2]|argv[3]|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**Microsoft 전용 종료**

## <a name="wildcard-expansion"></a>와일드카드 식

**Microsoft 전용**

명령줄에서 파일 이름과 경로 인수를 지정하기 위해 와일드카드, 즉 물음표(?)와 별표(*)를 사용할 수 있습니다.

명령줄 인수는 `argv` 문자열 배열에서 기본적으로 별도의 문자열로 와일드카드를 확장하지 않는 `_setargv`(와이드 문자 환경에서는 `_wsetargv`)라는 루틴에 의해 처리됩니다. 와일드카드 확장 사용에 대한 자세한 내용은 [와일드카드 인수 확장](../c-language/expanding-wildcard-arguments.md)을 참조하십시오.

**Microsoft 전용 종료**

## <a name="customizing-c-command-line-processing"></a>C++ 명령줄 처리 사용자 지정

**Microsoft 전용**

프로그램에서 명령줄 인수를 사용하지 않는 경우 명령줄 처리를 수행하는 라이브러리 루틴의 사용을 억제하여 약간의 공간을 절약할 수 있습니다. 이 루틴은 `_setargv`라고 하며 [와일드카드 확장](../cpp/wildcard-expansion.md)에서 설명합니다. 루틴의 사용을 억제하기 위해 `main` 함수를 포함하는 파일에서 아무 작업도 하지 않는 루틴을 정의하고 `_setargv`를 명명합니다. `_setargv`에 대한 호출은 `_setargv`의 정의로 충족되며 라이브러리 버전이 로드되지 않습니다.

마찬가지로 `envp` 인수를 통해 환경 테이블에 액세스하지 않을 경우 환경 처리 루틴인 `_setenvp` 대신 사용할 수 있는 사용자 고유의 빈 루틴을 제공할 수 있습니다. `_setargv` 함수와 마찬가지로 `_setenvp` **extern "C"** 로 선언 해야 합니다.

프로그램은 C 런타임 라이브러리의 루틴 중 `spawn` 또는 `exec` 제품군에 대해 호출할 수 있습니다. 이 루틴이 부모 프로세스에서 자식 프로세스로 환경을 전달 하는 데 사용 되므로 환경 처리 루틴을 억제 해서는 안 됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[기본 개념](../cpp/basic-concepts-cpp.md)
