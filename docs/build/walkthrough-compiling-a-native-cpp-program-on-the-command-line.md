---
title: '연습: 명령줄에서 네이티브 C++ 프로그램 컴파일'
description: 명령 프롬프트에서 C++ Microsoft 컴파일러를 사용 합니다.
ms.custom: conceptual
ms.date: 04/23/2019
helpviewer_keywords:
- native code [C++]
- Visual C++, native code
- compiling programs [C++]
- command-line applications [C++], native
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
ms.openlocfilehash: d002fd4c4edc99775e62023dda7998fba2c6a44f
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518176"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>연습: 명령줄에서 네이티브 C++ 프로그램 컴파일

Visual Studio에는 기본 콘솔 앱 C++ 에서 유니버설 Windows 플랫폼 앱, 데스크톱 앱, 장치 드라이버 및 .net 구성 요소에 이르기까지 모든 항목을 만드는 데 사용할 수 있는 명령줄 컴파일러가 포함 되어 있습니다.

이 연습에서는 basic, "Hello, World" 만든-편집기에서 텍스트를 사용 하 여 C++ 프로그램을 스타일 및 다음 명령줄에서 컴파일합니다. 내용은 명령줄을 사용 하는 대신 Visual Studio IDE를 시도 하려는 경우 [연습: 프로젝트 및 솔루션 (C++)를 사용 하 여 작업](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) 하거나 [C++ 데스크톱 개발에 Visual Studio IDE를 사용 하 여](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)입니다.

이 연습에서는 표시되는 내용을 입력하는 대신 Visual C++ 프로그램을 사용하거나 다른 도움말 문서의 Visual C++ 코드 샘플을 사용할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료 하려면 설치 해야 Visual Studio 및 선택적인 **C++를 사용한 데스크톱 개발** 워크 로드 또는 Visual Studio에 대 한 명령줄 빌드 도구입니다.

Visual Studio는 다양 한 언어 및 플랫폼에 대 한 모든 기능을 갖춘 편집기, 리소스 관리자, 디버거 및 컴파일러를 지 원하는 강력한 IDE (통합 개발 환경)입니다. 다운로드 무료 Visual Studio Community edition 등 Visual Studio를 설치 하 고 C/C++ 개발에 대 한 지원을 포함 하는 방법에 대 한 자세한 내용은 [Visual Studio에서 C++ 설치 지원](vscpp-step-0-installation.md)합니다.

명령줄 컴파일러, 도구 및 C 및 C++ 프로그램을 작성 하는 데 필요한 라이브러리가 Visual studio Build Tools를 설치 합니다. 빌드 실습실 또는 교실 연습에 완벽 하 게 사용할 수 있으며 비교적 빠르게 설치 됩니다. 명령줄 도구만 설치 하려면 [visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) 페이지에서 visual Studio 용 빌드 도구를 찾습니다.

명령줄에서 C 또는 C++ 프로그램을 빌드할 수 있습니다, 전에 명령줄에서 액세스할 수 있습니다 및 도구가 설치 되어 있는지 확인 해야 합니다. Visual C++에는 도구, 헤더 및 라이브러리를 사용 하 여 찾으려는 명령줄 환경에 대 한 복잡 한 요구 사항이 있습니다. **일반 명령 프롬프트 창에서 Visual C++를 사용할 수 없습니다** 몇 가지 준비를 수행 하지 않고 있습니다. 다행히 Visual C++ 명령줄 빌드에 대 한 설정 환경에 있는 개발자 명령 프롬프트를 시작할 수에 대 한 바로 가기 키를 설치 합니다. 그러나 개발자 명령 프롬프트 바로 가기 및를 위치 이름은 거의 모든 버전의 Visual C++ 및 다른 버전의 Windows에서 서로 다릅니다. 첫 번째 연습 작업에서 사용할 올바른 항목을 찾고 있습니다.

> [!NOTE]
> 개발자 명령 프롬프트 바로 가기는 컴파일러 및 도구, 필요한 헤더 및 라이브러리에 대 한 올바른 경로를 자동으로 설정 합니다. 일반 **명령 프롬프트** 창을 사용 하는 경우 이러한 환경 값을 직접 설정 해야 합니다. 자세한 내용은 [명령줄 빌드에 맞는 경로 및 환경 변수 설정](setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하세요. 개발자 명령 프롬프트 바로 가기를 직접 작성 하는 대신 사용 하는 것이 좋습니다.

### <a name="open-a-developer-command-prompt"></a>개발자 명령 프롬프트 열기

1. Windows 10에 Visual Studio 2017 이상을 설치한 경우 시작 메뉴를 열고 **모든 앱**을 선택 합니다. 아래로 스크롤하여 visual studio 응용 프로그램이 아닌 **Visual studio** 폴더를 엽니다. **VS에 대해 개발자 명령 프롬프트** 를 선택 하 여 명령 프롬프트 창을 엽니다.

   Windows 10에서 Microsoft Visual C++ Build Tools 2015를 설치한 경우 엽니다는 **시작** 메뉴 선택 **모든 앱**합니다. 아래로 스크롤하여 엽니다는 **Visual C++ Build Tools** 폴더입니다. 선택할 **Visual C++ 2015 x86 Native Tools 명령 프롬프트** 명령 프롬프트 창을 엽니다.

   Windows search 함수를 사용 하 여 "개발자 명령 프롬프트"를 검색 하 고 설치 된 버전의 Visual Studio와 일치 하는 항목을 선택할 수도 있습니다. 바로 가기를 사용 하 여 명령 프롬프트 창을 엽니다.

1. 다음으로, Visual C++ 개발자 명령 프롬프트를 올바르게 설정 되어 있는지 확인 합니다. 명령 프롬프트 창에서 `cl`을 입력 하 고 다음과 같은 출력이 표시 되는지 확인 합니다.

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   현재 디렉터리 또는 Visual C++ 및 설치 된 업데이트의 버전에 따라 버전 번호가 차이점이 있을 수 있습니다. 위의 출력은 표시 되는 항목을 다음 경우 명령줄에서 C 또는 C++ 프로그램을 빌드할 준비가 됩니다.

   > [!NOTE]
   > "'C l' is not recognized as는 내부 또는 외부 명령, 실행할 수 있는 프로그램 또는 배치 파일"와 같은 오류가 발생할 경우 오류 C1034 또는 오류 LNK1104 실행할 때 합니다 **cl** 하거나 개발자 명령 프롬프트를 사용 하지 않는 명령을 또는 Visual C++ 설치를 사용 하 여 문제가 발생 했습니다. 계속 하려면 먼저이 문제를 해결 해야 합니다.

   개발자 명령 프롬프트 바로 가기를 찾을 수 없으면 또는 입력 하면 오류 메시지를 받게 되 면 `cl`, 다음 Visual C++ 설치에 문제가 있을 수 있습니다. Visual Studio에서 Visual C++ 구성 요소를 다시 설치 하거나 Microsoft Visual C++ Build Tools를 다시 설치 하십시오. 작동 될 때까지 다음 섹션으로 하지 마십시오. 설치 및 Visual C++ 문제 해결에 대 한 자세한 내용은 참조 하세요. [Visual Studio 설치](/visualstudio/install/install-visual-studio)합니다.

   > [!NOTE]
   > 컴퓨터의 Windows 버전 및 시스템 보안 구성에 따라 마우스 오른쪽 단추를 클릭 하 여 개발자 명령 프롬프트 바로 가기에 대 한 바로 가기 메뉴를 열고 **관리자 권한으로 실행** 을 선택 하 여이 연습을 수행 하 여 만든 프로그램을 성공적으로 빌드하고 실행 해야 할 수 있습니다.

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Visual C++ 소스 파일을 만들고 명령줄에서 컴파일하십시오.

1. 개발자 명령 프롬프트 창에서 `md c:\hello`를 입력 하 여 디렉터리를 만든 다음 `cd c:\hello`를 입력 하 여 해당 디렉터리로 변경 합니다. 이 디렉터리는에서 소스 파일 및 컴파일된 프로그램을 만듭니다.

1. 명령 프롬프트 창에 `notepad hello.cpp`을 입력 합니다.

   메모장에서 파일을 만들라는 메시지가 표시 되 면 **예** 를 선택 합니다. 이 단계에서는 이름이 hello.exe 인 파일에 코드를 입력할 준비가 된 빈 메모장 창이 열립니다.

1. 메모장에서 다음 코드 줄을 입력 합니다.

   ```cpp
   #include <iostream>
   using namespace std;
   int main()
   {
       cout << "Hello, world, from Visual C++!" << endl;
   }
   ```

   이 코드는 화면에 한 줄의 텍스트를 쓴 다음 종료 하는 간단한 프로그램입니다. 오류를 최소화하기 위해 이 코드를 복사하여 메모장에 붙여넣습니다.

1. 작업을 저장합니다. 메모장의 **파일** 메뉴에서 **저장**을 선택합니다.

   축 하 합니다. 컴파일할 준비가 C++ 된 소스 파일인 hello .cpp를 만들었습니다.

1. 개발자 명령 프롬프트 창으로 다시 전환 합니다. 명령 프롬프트에 `dir`를 입력 하 여 c:\hello 디렉터리의 내용을 나열 합니다. 다음과 같이 표시 되는 디렉터리 목록에 소스 파일 hello.exe가 표시 되어야 합니다.

   ```Output
   c:\hello>dir
    Volume in drive C has no label.
    Volume Serial Number is CC62-6545

    Directory of c:\hello

   05/24/2016  05:36 PM    <DIR>          .
   05/24/2016  05:36 PM    <DIR>          ..
   05/24/2016  05:37 PM               115 hello.cpp
                  1 File(s)            115 bytes
                  2 Dir(s)  571,343,446,016 bytes free

   ```

   날짜 및 기타 세부 정보는 컴퓨터에서 다를 수 있습니다. 소스 코드 파일 hello.exe가 표시 되지 않으면 만든 c:\hello 디렉터리로 변경 했는지 확인 하 고 메모장에서 원본 파일을이 디렉터리에 저장 했는지 확인 합니다. 또한 .txt 확장명이 아닌 .cpp 파일 이름 확장명을 사용 하 여 소스 코드를 저장 했는지 확인 합니다.

1. 개발자 명령 프롬프트에서 `cl /EHsc hello.cpp`를 입력 하 여 프로그램을 컴파일합니다.

   cl.exe 컴파일러는 컴파일된 코드가 포함된 .obj 파일을 만든 다음 링커를 실행하여 실행 프로그램인 hello.exe를 만듭니다. 이 이름은 컴파일러에서 표시하는 출력 정보 줄에 나타납니다. 컴파일러의 출력은 다음과 같습니다.

   ```Output
   c:\hello>cl /EHsc hello.cpp
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   hello.cpp
   Microsoft (R) Incremental Linker Version 14.10.25017.0
   Copyright (C) Microsoft Corporation.  All rights reserved.

   /out:hello.exe
   hello.obj
   ```

   > [!NOTE]
   > "Cl '이 내부 또는 외부 명령, 실행할 수 있는 프로그램 또는 배치 파일," 오류 C1034 또는 오류 LNK1104 "와 같은 오류가 발생 하는 경우 개발자 명령 프롬프트가 올바르게 설정 되지 않은 것입니다. 이 문제를 해결 하는 방법에 대 한 자세한 내용을 보려면 **개발자 명령 프롬프트 열기** 섹션으로 돌아갑니다.

   > [!NOTE]
   > 다른 컴파일러 또는 링커 오류 또는 경고가 발생 하는 경우 소스 코드를 검토 하 여 오류를 수정한 다음 저장 하 고 컴파일러를 다시 실행 합니다. 특정 오류에 대 한 자세한 내용을 보려면이 MSDN 페이지의 검색 상자를 사용 하 여 오류 번호를 확인 하십시오.

1. hello.exe 프로그램을 실행하려면 명령 프롬프트에서 `hello`를 입력합니다.

   프로그램이 다음 텍스트를 표시하고 종료됩니다.

   ```Output
   Hello, world, from Visual C++!
   ```

   축, 컴파일 및 명령줄 도구를 사용 하 여 C++ 프로그램을 실행 했습니다.

## <a name="next-steps"></a>다음 단계

이 "Hello, World" 예제는 간단 C++ 프로그램을 가져올 수 있습니다. 실제 프로그램은 헤더 파일 및 더 많은 소스 파일, 라이브러리의 링크 및 유용한 작업을 수행 합니다.

표시 된 예제 코드를 입력 하는 대신 사용자 고유의 C++ 코드를 빌드하려면이 연습의 단계를 사용할 수 있습니다. 다른 곳에서 검색 하는 많은 C++ 코드 샘플 프로그램을 빌드할 수 있습니다. 소스 코드를 배치 하 고 쓰기 가능한 모든 디렉터리에서 앱을 빌드할 수 있습니다. 기본적으로 Visual Studio IDE는 사용자의 Visual studio 버전에 대해 이라는 Visual Studio 폴더의 프로젝트 하위 폴더에 있는 Documents 폴더에 프로젝트를 만듭니다.

추가 소스 코드 파일이 있는 프로그램을 컴파일하려면 명령줄에 다음과 같이 모두 입력 합니다.

`cl /EHsc file1.cpp file2.cpp file3.cpp`

`/EHsc` 명령줄 옵션은 컴파일러에 C++ 예외 처리를 사용하도록 지시합니다. 자세한 내용은 [/EH(예외 처리 모델)](reference/eh-exception-handling-model.md)를 참조하세요.

추가 소스 파일을 제공 하는 경우 컴파일러는 첫 번째 입력 파일을 사용 하 여 프로그램 이름을 만듭니다. 이 경우에는 file1 이라는 프로그램을 출력 합니다. 이름을 program1로 변경 하려면 [/out](reference/out-output-file-name.md) 링커 옵션을 추가 합니다.

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

프로그래밍 실수를 자동으로 catch 하려면 [/W3](reference/compiler-option-warning-level.md) 또는 [/W4](reference/compiler-option-warning-level.md) 경고 수준 옵션을 사용 하 여 컴파일하는 것이 좋습니다.

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

컴파일러에서 cl.exe에 더 많은 옵션을 빌드, 최적화, 디버그, 적용 하 고 코드를 분석할 수 있습니다. 빠른 목록을 입력 `cl /?` 개발자 명령 프롬프트에서. 또한 컴파일 및 연결할 수 별도로 있으며 더 복잡 한 빌드 시나리오에서 링커 옵션을 적용 합니다. 컴파일러 및 링커 옵션 및 사용에 대 한 자세한 내용은 참조 하세요. [C/C++ 빌드 참조](reference/c-cpp-building-reference.md)합니다.

NMAKE와 메이크파일 또는 MSBuild 및 프로젝트 파일을 사용 하 여 명령줄에서 더 복잡 한 프로젝트를 구성 하 고 빌드할 수 있습니다. 이러한 도구를 사용 하는 방법에 대 한 자세한 내용은 [NMAKE 참조](reference/nmake-reference.md) 및 [MSBuild](msbuild-visual-cpp.md)를 참조 하세요.

C 및 C++ 언어는 유사 하지만 동일 하지는 않습니다. MSVC 컴파일러는 간단한 규칙을 사용 하 여 코드를 컴파일할 때 사용할 언어를 결정 합니다. 기본적으로 MSVC 컴파일러는 .c로 끝나는 모든 파일을 C 소스 코드로 처리 하 고 .cpp로 끝나는 모든 파일을 C++ 소스 코드로 처리 합니다. 컴파일러가 모든 파일을 파일 이름 확장명에 종속 C++ 되지 않은 것으로 처리 하도록 하려면 [/tp](reference/tc-tp-tc-tp-specify-source-file-type.md) 컴파일러 옵션을 사용 합니다.

MSVC 컴파일러에는 ISO C99 표준과 호환 되지만 엄격 하 게 호환 되는 CRT (C 런타임 라이브러리)가 포함 되어 있습니다. 대부분의 경우 이식 가능한 코드는 정상적으로 컴파일되고 실행 됩니다. Visual C++ ISO C11의 CRT 변경 내용 중 일부를 지원 하지 않습니다. 특정 라이브러리 함수 및 POSIX 함수 이름은 MSVC 컴파일러에서 더 이상 사용 되지 않습니다. 함수는 지원 되지만 기본 이름이 변경 되었습니다. 자세한 내용은 [CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md) 하 고 [컴파일러 경고 (수준 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)합니다.

## <a name="see-also"></a>참조

[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)<br/>
[MSVC 컴파일러 옵션](reference/compiler-options.md)
