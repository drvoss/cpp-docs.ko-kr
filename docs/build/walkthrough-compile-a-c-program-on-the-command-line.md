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
ms.openlocfilehash: d807fa75b32b515c2222fec9ea9d070266303e33
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335258"
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>연습: 명령줄에서 C 프로그램 컴파일

Visual C++에는 기본 콘솔 프로그램부터 전체 Windows 데스크톱 응용 프로그램, 모바일 앱 등에 이르기까지 모든 것을 만드는 데 사용할 수 있는 C 컴파일러가 포함되어 있습니다.

이 연습에서는 텍스트 편집기를 사용하여 기본 "Hello, World" 스타일 C 프로그램을 만든 다음 명령줄에서 컴파일하는 방법을 보여 주십습니다. 명령줄에서 C++에서 작업하려는 경우 [연습: 명령줄에서 네이티브 C++ 프로그램 컴파일을](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)참조하십시오. 명령줄을 사용하는 대신 Visual Studio IDE를 사용하려면 [연습: 프로젝트 및 솔루션 작업(C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) 또는 [C++ 데스크톱 개발에 사용할 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)참조.

## <a name="prerequisites"></a>사전 요구 사항

이 연습을 완료하려면 Visual Studio및 선택적 Visual C++ 구성 요소 또는 Visual Studio용 도구 빌드를 설치해야 합니다.

Visual Studio는 다양한 언어 및 플랫폼에 대한 모든 기능을 갖춘 편집기, 리소스 관리자, 디버거 및 컴파일러를 지원하는 강력한 통합 개발 환경입니다. 이러한 기능 및 무료 Visual Studio 커뮤니티 버전을 포함하여 Visual Studio를 다운로드하고 설치하는 방법에 대한 자세한 내용은 [Visual Studio 설치를](/visualstudio/install/install-visual-studio)참조하십시오.

Visual Studio의 Visual Studio용 도구 빌드는 C 및 C++ 프로그램을 빌드하는 데 필요한 명령줄 도구 집합, 컴파일러, 도구 및 라이브러리만 설치합니다. 랩이나 강의실 을 구축하거나 비교적 빠르게 설치할 수 있습니다. 명령줄 도구 집합만 설치하려면 Visual Studio 다운로드 페이지에서 Visual Studio용 도구 [빌드를 다운로드하고](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) 설치 관리자를 실행합니다. Visual Studio 설치 관리자에서 **C++ 빌드 도구** 워크로드를 선택하고 **설치를**선택합니다.

명령줄에서 C 또는 C++ 프로그램을 빌드하려면 먼저 도구가 설치되어 있는지, 명령줄에서 액세스할 수 있는지 확인해야 합니다. Visual C++에는 사용하는 도구, 헤더 및 라이브러리를 찾기 위해 명령줄 환경에 대한 복잡한 요구 사항이 있습니다. 일부 준비 **없이는 일반 명령 프롬프트 창에서 Visual C++를 사용할 수 없습니다.** 필요한 모든 환경 변수가 설정된 일반 명령 프롬프트 창인 *개발자 명령 프롬프트* 창이 필요합니다. 다행히 Visual C++는 명령줄 빌드에 대해 환경이 설정된 개발자 명령 프롬프트를 시작할 수 있도록 바로 가기를 설치합니다. 안타깝게도 개발자 명령 바로 가기의 이름과 위치가 있는 위치는 거의 모든 버전의 Visual C++와 다른 Windows 버전에서 다릅니다. 첫 번째 연습 작업은 사용할 올바른 바로 가기를 찾는 것입니다.

> [!NOTE]
> 개발자 명령 프롬프트 바로 가기는 컴파일러 및 도구및 필요한 헤더 및 라이브러리에 대한 올바른 경로를 자동으로 설정합니다. 이러한 값 중 일부는 빌드 구성마다 다릅니다. 바로 가기 중 하나를 사용하지 않는 경우 이러한 환경 값을 직접 설정해야 합니다. 자세한 내용은 [명령줄 빌드에 맞는 경로 및 환경 변수 설정](setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하세요. 빌드 환경은 복잡하기 때문에 직접 빌드하는 대신 개발자 명령 프롬프트 바로 가기를 사용하는 것이 좋습니다.

이 지침은 사용 중인 Visual Studio 버전에 따라 다릅니다. 선호하는 버전의 Visual Studio에 대한 설명서를 보려면 **버전** 선택기 컨트롤을 사용합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker range="vs-2019"

## <a name="open-a-developer-command-prompt-in-visual-studio-2019"></a>Visual Studio 2019에서 개발자 명령 프롬프트 열기

Windows 10에 Visual Studio 2019를 설치한 경우 시작 메뉴를 열고 아래로 스크롤하여 **Visual Studio 2019** 폴더(Visual Studio 2019 앱이 아님)를 엽니다. **VS 2019에 대한 개발자 명령 프롬프트를** 선택하여 명령 프롬프트 창을 엽니다.

다른 버전의 Windows를 사용하는 경우 시작 메뉴 또는 시작 페이지에서 개발자 명령 프롬프트 바로 가기를 포함하는 Visual Studio 도구 폴더를 찾습니다. 또한 Windows 검색 기능을 사용하여 "개발자 명령 프롬프트"를 검색하고 설치된 버전의 Visual Studio와 일치하는 것을 선택할 수도 있습니다. 바로 가기를 사용하여 명령 프롬프트 창을 엽니다.

::: moniker-end

::: moniker range="vs-2017"

## <a name="open-a-developer-command-prompt-in-visual-studio-2017"></a>Visual Studio 2017에서 개발자 명령 프롬프트 열기

Windows 10에 Visual Studio 2017을 설치한 경우 시작 메뉴를 열고 아래로 스크롤하여 **Visual Studio 2017** 폴더(Visual Studio 2017 앱아님)를 엽니다. **VS 2017에 대한 개발자 명령 프롬프트를** 선택하여 명령 프롬프트 창을 엽니다.

다른 버전의 Windows를 실행하는 경우 시작 메뉴 또는 시작 페이지에서 개발자 명령 프롬프트 바로 가기를 포함하는 Visual Studio 도구 폴더를 찾습니다. 또한 Windows 검색 기능을 사용하여 "개발자 명령 프롬프트"를 검색하고 설치된 버전의 Visual Studio와 일치하는 것을 선택할 수도 있습니다. 바로 가기를 사용하여 명령 프롬프트 창을 엽니다.

::: moniker-end

::: moniker range="vs-2015"

## <a name="open-a-developer-command-prompt-in-visual-studio-2015"></a>Visual Studio 2015에서 개발자 명령 프롬프트 열기

Windows 10에서 Microsoft Visual C++ 빌드 도구 2015를 설치한 경우 **시작** 메뉴를 열고 아래로 스크롤하여 **Visual C++ 빌드 도구** 폴더를 엽니다. **Visual C++ 2015 x86 기본 도구 명령 프롬프트를** 선택하여 명령 프롬프트 창을 엽니다.

다른 버전의 Windows를 실행하는 경우 시작 메뉴 또는 시작 페이지에서 개발자 명령 프롬프트 바로 가기를 포함하는 Visual Studio 도구 폴더를 찾습니다. 또한 Windows 검색 기능을 사용하여 "개발자 명령 프롬프트"를 검색하고 설치된 버전의 Visual Studio와 일치하는 것을 선택할 수도 있습니다. 바로 가기를 사용하여 명령 프롬프트 창을 엽니다.

::: moniker-end

그런 다음 Visual C++ 개발자 명령 프롬프트가 올바르게 설정되어 있는지 확인합니다. 명령 프롬프트 창에서 `cl` 출력이 다음과 같은 지 확인합니다.

```Output
C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
Copyright (C) Microsoft Corporation.  All rights reserved.

usage: cl [ option... ] filename... [ /link linkoption... ]
```

현재 디렉터리 또는 버전 번호는 Visual C++ 버전 및 설치된 업데이트에 따라 다를 수 있습니다. 위의 출력이 표시되는 것과 유사하다면 명령줄에서 C 또는 C ++ 프로그램을 빌드할 준비가 된 것입니다.

> [!NOTE]
> "'cl'이 내부 또는 외부 명령, 작동 가능한 프로그램 또는 배치 파일로 인식되지 않음", C1034 오류 또는 cl 명령을 실행할 때 오류 LNK1104와 같은 오류가 발생하면 **개발자** 명령 프롬프트를 사용하지 않거나 Visual C++의 설치에 문제가 있는 경우. 계속하려면 먼저 이 문제를 해결해야 합니다.

개발자 명령 프롬프트 바로 가기를 찾을 수 없거나 입력할 `cl`때 오류 메시지가 표시되면 Visual C++ 설치에 문제가 있을 수 있습니다. Visual Studio 2017 이상을 사용하는 경우 Visual Studio 설치 관리자에서 **C++** 워크로드를 사용하여 데스크톱 개발을 다시 설치해 보십시오. 자세한 내용은 [Visual Studio에서 C++ 지원 설치를](vscpp-step-0-installation.md)참조하십시오. 또는 Visual Studio 다운로드 페이지에서 빌드 도구를 다시 [설치합니다.](https://visualstudio.microsoft.com/downloads/) 이 작동 할 때까지 다음 섹션으로 이동하지 마십시오. Visual Studio 설치 및 문제 해결에 대한 자세한 내용은 [Visual Studio 설치를](/visualstudio/install/install-visual-studio)참조하십시오.

> [!NOTE]
> 컴퓨터의 Windows 버전 및 시스템 보안 구성에 따라 마우스 오른쪽 단추로 클릭하여 개발자 명령 프롬프트 바로 가기의 바로 가기 메뉴를 연 다음 **관리자로 실행을** 선택하여 이 연습에 따라 만든 프로그램을 성공적으로 빌드하고 실행해야 할 수 있습니다.

## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>C 소스 파일을 만들고 명령줄에서 컴파일합니다.

1. 개발자 명령 프롬프트 `cd c:\` 창에서 입력하여 현재 작업 중인 디렉터리를 C: 드라이브의 루트로 변경합니다. 그런 다음 `md c:\simple` 입력하여 디렉터리를 만든 `cd c:\simple` 다음 입력하여 해당 디렉터리로 변경합니다. 이 디렉터리에는 소스 파일과 컴파일된 프로그램이 저장됩니다.

1. 개발자 `notepad simple.c` 명령 프롬프트에 입력합니다. 팝업메모장 경고 대화 상자에서 **예를** 선택하여 작업 디렉토리에 새 simple.c 파일을 만듭니다.

1. 메모장에 다음 코드 줄을 입력합니다.

    ```C
    #include <stdio.h>

    int main()
    {
        printf("Hello, World! This is a native C program compiled on the command line.\n");
        return 0;
    }
    ```

1. 메모장 메뉴 모음에서 **파일** > **저장을** 선택하여 작업 디렉토리에 simple.c를 저장합니다.

1. 개발자 명령 프롬프트 창으로 다시 전환합니다. 명령 `dir` 프롬프트에 입력하여 c:\단순 디렉터리의 내용을 나열합니다. 디렉터리 목록에서 simple.c 소스 파일이 표시됩니다.

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

   날짜 및 기타 세부 정보는 컴퓨터에 따라 다릅니다. simple.c의 소스 코드 파일이 표시되지 않으면 만든 c:\단순 디렉토리로 변경했는지 확인하고 메모장에 이 디렉토리에 소스 파일을 저장했는지 확인합니다. 또한 .txt 확장자가 아닌 .c 파일 이름 확장명으로 소스 코드를 저장했는지 확인합니다.

1. 프로그램을 컴파일하려면 개발자 `cl simple.c` 명령 프롬프트를 입력합니다.

   컴파일러가 표시하는 출력 정보 줄에서 실행 프로그램 이름 simple.exe를 볼 수 있습니다.

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
   > "'cl'이 내부 또는 외부 명령, 작동 가능한 프로그램 또는 배치 파일로 인식되지 않음"과 같은 오류가 발생하면 오류 C1034 또는 오류 LNK1104가 올바르게 설정되지 않습니다. 이 문제를 해결하는 방법에 대한 자세한 내용은 **개발자 명령 프롬프트 열기 섹션으로** 돌아갑니다.

   > [!NOTE]
   > 다른 컴파일러 또는 링커 오류 또는 경고가 발생하면 소스 코드를 검토하여 오류를 수정한 다음 저장하고 컴파일러를 다시 실행합니다. 특정 오류에 대한 자세한 내용은 이 페이지 상단의 검색 상자를 사용하여 오류 번호를 찾습니다.

1. 프로그램을 실행하려면 명령 `simple` 프롬프트를 입력합니다.

   프로그램이 다음 텍스트를 표시하고 종료됩니다.

    ```Output
    Hello, World! This is a native C program compiled on the command line.
    ```

   축하합니다, 당신은 컴파일하고 명령 줄을 사용하여 C 프로그램을 실행했습니다.

## <a name="next-steps"></a>다음 단계

이 "안녕하세요, 세계"의 예는 C 프로그램이 얻을 수있는 만큼 간단합니다. 실제 프로그램에는 헤더 파일과 더 많은 소스 파일이 있고 라이브러리에 링크되어 유용한 작업을 수행합니다.

이 연습의 단계를 사용하여 표시된 샘플 코드를 입력하는 대신 고유한 C 코드를 빌드할 수 있습니다. 다른 곳에서 찾을 수 있는 많은 C 코드 샘플 프로그램을 빌드할 수도 있습니다. 추가 소스 코드 파일이 있는 프로그램을 컴파일하려면 다음과 같이 명령줄에 모두 입력합니다.

`cl file1.c file2.c file3.c`

컴파일러는 file1.exe라는 프로그램을 출력합니다. 이름을 program1.exe로 변경하려면 [/out](reference/out-output-file-name.md) 링커 옵션을 추가합니다.

`cl file1.c file2.c file3.c /link /out:program1.exe`

그리고 자동으로 더 많은 프로그래밍 실수를 잡으려면 [/W3](reference/compiler-option-warning-level.md) 또는 [/W4](reference/compiler-option-warning-level.md) 경고 수준 옵션을 사용하여 컴파일하는 것이 좋습니다.

`cl /W4 file1.c file2.c file3.c /link /out:program1.exe`

컴파일러 cl.exe에는 코드를 빌드, 최적화, 디버깅 및 분석하기 위해 적용할 수 있는 더 많은 옵션이 있습니다. 빠른 목록을 보려면 `cl /?` 개발자 명령 프롬프트를 입력합니다. 또한 개별적으로 컴파일 및 연결하고 보다 복잡한 빌드 시나리오에서 링커 옵션을 적용할 수도 있습니다. 컴파일러 및 링커 옵션 및 사용법에 대한 자세한 내용은 [C/C++ 건물 참조를](reference/c-cpp-building-reference.md)참조하십시오.

NMAKE 및 makefiles 또는 MSBuild 및 프로젝트 파일을 사용하여 명령줄에서 보다 복잡한 프로젝트를 구성하고 빌드할 수 있습니다. 이러한 도구 사용에 대한 자세한 내용은 [NMAKE 참조](reference/nmake-reference.md) 및 [MSBuild](msbuild-visual-cpp.md)를 참조하십시오.

C 및 C++ 언어는 비슷하지만 동일하지는 않습니다. MSVC(Microsoft C/C++ 컴파일러)는 간단한 규칙을 사용하여 코드를 컴파일할 때 사용할 언어를 결정합니다. 기본적으로 MSVC 컴파일러는 .c로 끝나는 모든 파일과 .cpp로 끝나는 모든 파일을 C++ 소스 코드로 처리합니다. 컴파일러가 모든 파일을 파일 이름 확장명에 종속되지 않는 C로 처리하도록 하려면 [/Tc](reference/tc-tp-tc-tp-specify-source-file-type.md) 컴파일러 옵션을 사용합니다.

MSVC는 ISO C99 표준과 호환되지만 엄격하게 준수하지는 않습니다. 대부분의 경우 이식 가능한 C 코드가 예상대로 컴파일되고 실행됩니다. Visual C++는 ISO C11의 대부분의 변경 내용을 지원하지 않습니다. 특정 라이브러리 함수 및 POSIX 함수 이름은 MSVC에서 더 이상 사용되지 않습니다. 함수가 지원되지만 기본 설정 이름이 변경되었습니다. 자세한 내용은 [CRT](../c-runtime-library/security-features-in-the-crt.md) 및 [컴파일러 경고(수준 3) C4996의](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)보안 기능을 참조하십시오.

## <a name="see-also"></a>참고 항목

[연습: 표준 C++ 프로그램 만들기(C++)](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)<br/>
[C 언어 참조](../c-language/c-language-reference.md)<br/>
[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)<br/>
[호환성](../c-runtime-library/compatibility.md)
