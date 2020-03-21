---
title: '연습: 명령줄에서 C 프로그램 컴파일'
ms.custom: conceptual
ms.date: 04/25/2019
helpviewer_keywords:
- command-line applications [C++], C programs
- Visual C, compiling
- compiling programs [C++]
- C program compiling [C++]
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
ms.openlocfilehash: 1b4e7f0f188ce7b3003f12cb7acafaf15a03d86a
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078249"
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>연습: 명령줄에서 C 프로그램 컴파일

Visual C++에는 전체 Windows 데스크톱 응용 프로그램, 모바일 앱 등 기본적인 콘솔 프로그램에서 모든이 만드는 데 사용할 수 있는 C 컴파일러가 포함 됩니다.

이 연습에서는 텍스트 편집기를 사용 하 여 기본, "Hello, 세계" 스타일 C 프로그램을 만들고 명령줄에서 컴파일하는 방법을 보여 줍니다. 명령줄에서 작업 C++ 하는 경우 [연습: 명령줄에서 C++ 네이티브 프로그램 컴파일](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)을 참조 하세요. 명령줄을 사용 하는 대신 visual studio ide를 사용 하려는 경우 [연습: 프로젝트 및 솔루션 작업 (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) 또는 [ C++ 데스크톱 개발용 visual Studio ide 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)을 참조 하세요.

## <a name="prerequisites"></a>필수 조건

이 연습을 완료 하려면 설치 해야 Visual Studio 및 선택적 Visual C++ 구성 요소 또는 Build Tools for Visual Studio입니다.

Visual Studio는 다양 한 언어 및 플랫폼에 대 한 모든 기능을 갖춘 편집기, 리소스 관리자, 디버거 및 컴파일러를 지 원하는 강력한 통합 개발 환경입니다. 이러한 기능 및 visual Studio를 다운로드 하 고 설치 하는 방법에 대 한 자세한 내용은 visual studio [설치](/visualstudio/install/install-visual-studio)를 참조 하세요.

명령줄 도구 집합, 컴파일러, 도구,만 C 및 C++ 프로그램을 작성 하는 데 필요한 라이브러리가 Visual Studio 버전의 Visual Studio Build Tools를 설치 합니다. 빌드 실습실 또는 교실 연습에 완벽 하 게 사용할 수 있으며 비교적 빠르게 설치 됩니다. 명령줄 도구 집합만 설치 하려면 [Visual studio 다운로드](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) 페이지에서 visual Studio 용 빌드 도구를 다운로드 하 고 설치 관리자를 실행 합니다. Visual Studio 설치 관리자에서  **C++ 빌드 도구** 워크 로드를 선택 하 고 **설치**를 선택 합니다.

명령줄에서 C 또는 C++ 프로그램을 빌드할 수 있습니다, 전에 명령줄에서 액세스할 수 있습니다 및 도구가 설치 되어 있는지 확인 해야 합니다. Visual C++에는 도구, 헤더 및 라이브러리를 사용 하 여 찾으려는 명령줄 환경에 대 한 복잡 한 요구 사항이 있습니다. **시각적 개체 C++ 를 준비 하지 않고 일반 명령 프롬프트 창에서 사용할 수 없습니다** . 모든 필수 환경 변수를 설정 하는 일반 명령 프롬프트 창인 *개발자 명령 프롬프트* 창이 필요 합니다. 다행히 Visual C++ 명령줄 빌드에 대 한 설정 환경을 설정 하는 개발자 명령 프롬프트를 시작할 수에 대 한 바로 가기 키를 설치 합니다. 그러나 개발자 명령 프롬프트 바로 가기 및를 위치 이름은 거의 모든 버전의 Visual C++ 및 다른 버전의 Windows에서 서로 다릅니다. 첫 번째 연습 작업은 사용할 올바른 바로 가기를 찾는 것입니다.

> [!NOTE]
> 개발자 명령 프롬프트 바로 가기는 컴파일러 및 도구, 필요한 헤더 및 라이브러리에 대 한 올바른 경로를 자동으로 설정 합니다. 이러한 값 중 일부는 빌드 구성 마다 다릅니다. 바로 가기 중 하나를 사용 하지 않는 경우 이러한 환경 값을 직접 설정 해야 합니다. 자세한 내용은 [명령줄 빌드에 맞는 경로 및 환경 변수 설정](setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하세요. 빌드 환경이 복잡 하기 때문에 직접 빌드하는 대신 개발자 명령 프롬프트 바로 가기를 사용 하는 것이 좋습니다.

이러한 지침은 사용 중인 Visual Studio 버전에 따라 달라 집니다. 계속 하기 전에이 페이지의 왼쪽 위에 있는 버전 선택기를 올바르게 설정 해야 합니다.

::: moniker range="vs-2019"

## <a name="open-a-developer-command-prompt-in-visual-studio-2019"></a>Visual Studio 2019에서 개발자 명령 프롬프트를 엽니다.

Windows 10에 Visual Studio 2019을 설치한 경우 시작 메뉴를 열고 아래로 스크롤하여 visual studio **2019** 폴더 (visual studio 2019 앱 아님)를 엽니다. **VS 2019에 대 한 개발자 명령 프롬프트** 를 선택 하 여 명령 프롬프트 창을 엽니다.

다른 버전의 Windows를 사용 하는 경우 시작 메뉴 또는 시작 페이지에서 개발자 명령 프롬프트 바로 가기를 포함 하는 Visual Studio tools 폴더를 확인 합니다. Windows search 함수를 사용 하 여 "개발자 명령 프롬프트"를 검색 하 고 설치 된 버전의 Visual Studio와 일치 하는 항목을 선택할 수도 있습니다. 바로 가기를 사용 하 여 명령 프롬프트 창을 엽니다.

::: moniker-end

::: moniker range="vs-2017"

## <a name="open-a-developer-command-prompt-in-visual-studio-2017"></a>Visual Studio 2017에서 개발자 명령 프롬프트를 엽니다.

Windows 10에 Visual Studio 2017을 설치한 경우 시작 메뉴를 열고 아래로 스크롤하여 visual studio **2017** 폴더 (visual studio 2017 앱 아님)를 엽니다. **VS 2017에 대 한 개발자 명령 프롬프트** 를 선택 하 여 명령 프롬프트 창을 엽니다.

다른 버전의 Windows를 실행 하는 경우 시작 메뉴 또는 시작 페이지에서 개발자 명령 프롬프트 바로 가기를 포함 하는 Visual Studio tools 폴더를 확인 합니다. Windows search 함수를 사용 하 여 "개발자 명령 프롬프트"를 검색 하 고 설치 된 버전의 Visual Studio와 일치 하는 항목을 선택할 수도 있습니다. 바로 가기를 사용 하 여 명령 프롬프트 창을 엽니다.

::: moniker-end

::: moniker range="vs-2015"

## <a name="open-a-developer-command-prompt-in-visual-studio-2015"></a>Visual Studio 2015에서 개발자 명령 프롬프트를 엽니다.

Windows 10에서 Microsoft Visual C++ Build Tools 2015을 설치한 경우 **시작** 메뉴를 열고 아래로 스크롤하여 **Visual C++ build tools** 폴더를 엽니다. **C++ Visual 2015 x86 Native Tools 명령 프롬프트** 를 선택 하 여 명령 프롬프트 창을 엽니다.

다른 버전의 Windows를 실행 하는 경우 시작 메뉴 또는 시작 페이지에서 개발자 명령 프롬프트 바로 가기를 포함 하는 Visual Studio tools 폴더를 확인 합니다. Windows search 함수를 사용 하 여 "개발자 명령 프롬프트"를 검색 하 고 설치 된 버전의 Visual Studio와 일치 하는 항목을 선택할 수도 있습니다. 바로 가기를 사용 하 여 명령 프롬프트 창을 엽니다.

::: moniker-end

다음으로, Visual C++ 개발자 명령 프롬프트를 올바르게 설정 되어 있는지 확인 합니다. 명령 프롬프트 창에서 `cl`을 입력 하 고 다음과 같은 출력이 표시 되는지 확인 합니다.

```Output
C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
Copyright (C) Microsoft Corporation.  All rights reserved.

usage: cl [ option... ] filename... [ /link linkoption... ]
```

현재 디렉터리 또는 Visual C++ 및 설치 된 업데이트의 버전에 따라 버전 번호가 차이점이 있을 수 있습니다. 위의 출력은 표시 되는 항목을 다음 경우 명령줄에서 C 또는 C++ 프로그램을 빌드할 준비가 됩니다.

> [!NOTE]
> **Cl** 명령을 실행할 때 "cl '이 내부 또는 외부 명령, 실행할 수 있는 프로그램 또는 배치 파일" 오류 C1034 또는 오류 LNK1104로 인식 되지 않습니다 .와 같은 오류가 발생 하는 경우 개발자 명령 프롬프트를 사용 하 고 있지 않거나 시각적 개체 C++설치에 문제가 있는 것입니다. 계속 하려면 먼저이 문제를 해결 해야 합니다.

개발자 명령 프롬프트 바로 가기를 찾을 수 없거나 `cl`입력할 때 오류 메시지가 표시 되는 경우 시각적 개체 C++ 설치에 문제가 있을 수 있습니다. Visual studio 2017 이상을 사용 하는 경우 visual studio 설치 관리자에서 워크 로드를 **사용 하 C++ 여 데스크톱 개발** 을 다시 설치 해 보세요. 자세한 내용은 [Visual Studio에서 C++ 지원 설치](vscpp-step-0-installation.md)를 참조 하세요. 또는 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/) 페이지에서 빌드 도구를 다시 설치 합니다. 작동 될 때까지 다음 섹션으로 하지 마십시오. Visual Studio를 설치 하 고 문제를 해결 하는 방법에 대 한 자세한 내용은 [Visual Studio 설치](/visualstudio/install/install-visual-studio)를 참조 하세요.

> [!NOTE]
> 컴퓨터의 Windows 버전 및 시스템 보안 구성에 따라 마우스 오른쪽 단추를 클릭 하 여 개발자 명령 프롬프트 바로 가기에 대 한 바로 가기 메뉴를 열고 **관리자 권한으로 실행** 을 선택 하 여이 연습을 수행 하 여 만든 프로그램을 성공적으로 빌드하고 실행 해야 할 수 있습니다.

## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>C 소스 파일을 만들고 명령줄에서 컴파일합니다.

1. 개발자 명령 프롬프트 창에서 현재 작업 디렉터리를 C: 드라이브의 루트로 변경 하려면 `cd c:\`를 입력 합니다. 그런 다음 `md c:\simple`를 입력 하 여 디렉터리를 만든 다음 `cd c:\simple`를 입력 하 여 해당 디렉터리로 변경 합니다. 이 디렉터리는 원본 파일 및 컴파일된 프로그램을 포함 합니다.

1. 개발자 명령 프롬프트에 `notepad simple.c`을 입력 합니다. 표시 되는 메모장 경고 대화 상자에서 **예** 를 선택 하 여 작업 디렉터리에 새 간단한 .c 파일을 만듭니다.

1. 메모장에서 다음 코드 줄을 입력 합니다.

    ```C
    #include <stdio.h>

    int main()
    {
        printf("Hello, World! This is a native C program compiled on the command line.\n");
        return 0;
    }
    ```

1. 메모장 메뉴 모음에서 **파일** > **저장** 을 선택 하 여 작업 디렉터리에 간단 하 게 c. c를 저장 합니다.

1. 개발자 명령 프롬프트 창으로 다시 전환 합니다. 명령 프롬프트에 `dir`를 입력 하 여 c:\simple 디렉터리의 내용을 나열 합니다. 다음과 같이 표시 되는 디렉터리 목록에 소스 파일을 간단 하 게 표시 해야 합니다.

    ```Output
    C:\simple>dir
     Volume in drive C has no label.
     Volume Serial Number is CC62-6545

     Directory of C:\simple

    10/02/2017  03:46 PM    <DIR>          .
    10/02/2017  03:46 PM    <DIR>          ..
    10/02/2017  03:36 PM               143 simple.c
                   1 File(s)            143 bytes
                   2 Dir(s)  514,900,566,016 bytes free

    ```

   날짜 및 기타 세부 정보는 컴퓨터에서 다를 수 있습니다. 소스 코드 파일 (simple. c)이 표시 되지 않으면 만든 c:\simple 디렉터리로 변경 했는지 확인 하 고 메모장에서 원본 파일을이 디렉터리에 저장 했는지 확인 합니다. 또한 .txt 확장명이 아닌 .c 파일 이름 확장명을 사용 하 여 소스 코드를 저장 했는지 확인 합니다.

1. 프로그램을 컴파일하려면 개발자 명령 프롬프트에 `cl simple.c`을 입력 합니다.

   컴파일러가 표시 하는 출력 정보 줄에서 실행 프로그램 이름 (simple .exe)을 볼 수 있습니다.

    ```Output
    c:\simple>cl simple.c
    Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
    Copyright (C) Microsoft Corporation.  All rights reserved.

    simple.c
    Microsoft (R) Incremental Linker Version 14.10.25017.0
    Copyright (C) Microsoft Corporation.  All rights reserved.

    /out:simple.exe
    simple.obj
    ```

   > [!NOTE]
   > "Cl '이 내부 또는 외부 명령, 실행할 수 있는 프로그램 또는 배치 파일," 오류 C1034 또는 오류 LNK1104 "와 같은 오류가 발생 하는 경우 개발자 명령 프롬프트가 올바르게 설정 되지 않은 것입니다. 이 문제를 해결 하는 방법에 대 한 자세한 내용을 보려면 **개발자 명령 프롬프트 열기** 섹션으로 돌아갑니다.

   > [!NOTE]
   > 다른 컴파일러 또는 링커 오류 또는 경고가 발생 하는 경우 소스 코드를 검토 하 여 오류를 수정한 다음 저장 하 고 컴파일러를 다시 실행 합니다. 특정 오류에 대 한 자세한 내용을 보려면이 페이지 맨 위에 있는 검색 상자를 사용 하 여 오류 번호를 확인 하십시오.

1. 프로그램을 실행 하려면 명령 프롬프트에 `simple`을 입력 합니다.

   프로그램이 다음 텍스트를 표시하고 종료됩니다.

    ```Output
    Hello, World! This is a native C program compiled on the command line.
    ```

   축 하 합니다. 명령줄을 사용 하 여 C 프로그램을 컴파일하고 실행 했습니다.

## <a name="next-steps"></a>다음 단계

이 "Hello, 세계" 예제는 C 프로그램에서 가져올 수 있는 것과 관련 된 것입니다. 실제 프로그램은 헤더 파일 및 더 많은 소스 파일, 라이브러리의 링크 및 유용한 작업을 수행 합니다.

이 연습의 단계를 사용 하 여 표시 된 샘플 코드를 입력 하는 대신 사용자 고유의 C 코드를 빌드할 수 있습니다. 다른 곳에서 찾을 수 있는 많은 C 코드 샘플 프로그램을 빌드할 수도 있습니다. 추가 소스 코드 파일이 있는 프로그램을 컴파일하려면 명령줄에 다음과 같이 모두 입력 합니다.

`cl file1.c file2.c file3.c`

컴파일러는 file1 이라는 프로그램을 출력 합니다. 이름을 program1로 변경 하려면 [/out](reference/out-output-file-name.md) 링커 옵션을 추가 합니다.

`cl file1.c file2.c file3.c /link /out:program1.exe`

프로그래밍 실수를 자동으로 catch 하려면 [/W3](reference/compiler-option-warning-level.md) 또는 [/W4](reference/compiler-option-warning-level.md) 경고 수준 옵션을 사용 하 여 컴파일하는 것이 좋습니다.

`cl /W4 file1.c file2.c file3.c /link /out:program1.exe`

컴파일러에서 cl.exe에 더 많은 옵션을 빌드, 최적화, 디버그, 적용 하 고 코드를 분석할 수 있습니다. 빠른 목록을 보려면 개발자 명령 프롬프트에서 `cl /?`를 입력 합니다. 또한 컴파일 및 연결할 수 별도로 있으며 더 복잡 한 빌드 시나리오에서 링커 옵션을 적용 합니다. 컴파일러 및 링커 옵션 및 사용에 대 한 자세한 내용은 [C/C++ 빌드 참조](reference/c-cpp-building-reference.md)를 참조 하세요.

NMAKE와 메이크파일 또는 MSBuild 및 프로젝트 파일을 사용 하 여 명령줄에서 더 복잡 한 프로젝트를 구성 하 고 빌드할 수 있습니다. 이러한 도구를 사용 하는 방법에 대 한 자세한 내용은 [NMAKE 참조](reference/nmake-reference.md) 및 [MSBuild](msbuild-visual-cpp.md)를 참조 하세요.

C 및 C++ 언어는 유사 하지만 동일 하지는 않습니다. Microsoft C/C++ 컴파일러 (MSVC)는 간단한 규칙을 사용 하 여 코드를 컴파일할 때 사용할 언어를 결정 합니다. 기본적으로 MSVC 컴파일러는 .c로 끝나는 모든 파일을 C 소스 코드로 처리 하 고 .cpp로 끝나는 모든 파일을 C++ 소스 코드로 처리 합니다. 컴파일러가 모든 파일을 C 파일 이름 확장명에 종속 되지 않은 것으로 처리 하도록 하려면 [/tc](reference/tc-tp-tc-tp-specify-source-file-type.md) 컴파일러 옵션을 사용 합니다.

MSVC는 ISO C99 표준과 호환 되지만 엄격 하 게 호환 되지 않습니다. 대부분의 경우에서 이식 가능한 C 코드 컴파일 및 예상 대로 실행 합니다. Visual C++ ISO C11의 변경 사항 중 대부분을 지원 하지 않습니다. 특정 라이브러리 함수 및 POSIX 함수 이름은 MSVC에서 더 이상 사용 되지 않습니다. 함수는 지원 되지만 기본 이름이 변경 되었습니다. 자세한 내용은 [CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md) 및 [컴파일러 경고 (수준 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)를 참조 하세요.

## <a name="see-also"></a>참고 항목

[연습: 표준 C++ 프로그램 만들기(C++)](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)<br/>
[C 언어 참조](../c-language/c-language-reference.md)<br/>
[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)<br/>
[호환성](../c-runtime-library/compatibility.md)
