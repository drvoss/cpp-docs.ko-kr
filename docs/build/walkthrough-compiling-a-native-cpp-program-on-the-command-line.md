---
title: '연습: 명령줄에서 네이티브 C++ 프로그램 컴파일'
description: 명령 프롬프트에서 Microsoft C++ 컴파일러를 사용합니다.
ms.custom: conceptual
ms.date: 04/02/2020
helpviewer_keywords:
- native code [C++]
- Visual C++, native code
- compiling programs [C++]
- command-line applications [C++], native
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
ms.openlocfilehash: c24fdfdaef612059d5c2fbaaa58f10d83f5fe3a8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335239"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>연습: 명령줄에서 네이티브 C++ 프로그램 컴파일

Visual Studio에는 명령줄 C 및 C++ 컴파일러가 포함되어 있습니다. 이 도구를 사용하여 기본 콘솔 앱에서 유니버설 Windows 플랫폼 앱, 데스크톱 앱, 디바이스 드라이버 및 .NET 구성 요소에 이르기까지 모든 것을 만들 수 있습니다.

이 연습에서는 텍스트 편집기를 사용하여 기본적인 "Hello, World" 스타일 C++ 프로그램을 만들고 명령줄에서 컴파일합니다. 명령줄을 사용하는 대신 Visual Studio IDE를 사용하려는 경우 [연습: 프로젝트 및 솔루션 작업(C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) 또는 [C++ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)을 참조하세요.

이 연습에서는 표시되는 항목을 입력하는 대신 자체 C++ 프로그램을 사용할 수 있습니다. 또는 다른 도움말 문서의 C++ 코드 샘플을 사용할 수 있습니다.

## <a name="prerequisites"></a>사전 요구 사항

이 연습을 완료하려면 Visual Studio와 선택적 **C++를 사용한 데스크톱 개발** 워크로드 또는 Visual Studio용 명령줄 Build Tools가 설치되어 있어야 합니다.

Visual Studio는 *IDE*(통합 개발 환경)입니다. 다양한 언어 및 플랫폼에 대한 모든 기능을 갖춘 편집기, 리소스 관리자, 디버거 및 컴파일러를 지원합니다. 사용 가능한 버전에는 무료 Visual Studio Community 버전이 포함되며 모두 C 및 C++ 개발을 지원할 수 있습니다. Visual Studio를 다운로드 및 설치하는 방법에 대한 자세한 내용은 [Visual Studio에서 C++ 지원 설치](vscpp-step-0-installation.md)를 참조하세요.

Visual Studio용 Build Tools는 C 및 C++ 프로그램을 빌드하는 데 필요한 명령줄 컴파일러, 도구 및 라이브러리만 설치합니다. 빌드 랩 또는 강의실 연습에 매우 적합하며 비교적 빠르게 설치됩니다. 명령줄 도구만 설치하려면 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) 페이지에서 Visual Studio용 Build Tools를 찾습니다.

명령줄에서 C 또는 C++ 프로그램을 빌드하기 전에 해당 도구가 설치되어 있는지 확인하고 명령줄에서 액세스할 수 있는지 확인합니다. Visual C++에는 명령줄 환경이 사용하는 도구, 헤더 및 라이브러리를 찾는 복잡한 요구 사항이 있습니다. 일부 준비 작업을 수행하지 않으면 **일반 명령 프롬프트 창에서 Visual C++를 사용할 수 없습니다**. 다행히 Visual C++는 명령줄 빌드에 대한 환경이 설정된 개발자 명령 프롬프트를 시작할 수 있는 바로 가기를 설치합니다. 아쉽게도 개발자 명령 프롬프트 바로 가기의 이름 및 위치는 거의 모든 버전의 Visual C++와 다양한 버전의 Windows에서 서로 다릅니다. 첫 번째 연습은 사용할 올바른 항목을 찾는 것입니다.

> [!NOTE]
> 개발자 명령 프롬프트 바로 가기는 컴파일러 및 도구에 대한 올바른 경로와 필요한 헤더 및 라이브러리에 대한 올바른 경로를 자동으로 설정합니다. 일반 **명령 프롬프트** 창을 사용하는 경우 이러한 환경 값을 직접 설정해야 합니다. 자세한 내용은 [명령줄 빌드에 맞는 경로 및 환경 변수 설정](setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하세요. 직접 작성하는 대신 개발자 명령 프롬프트 바로 가기를 사용하는 것이 좋습니다.

### <a name="open-a-developer-command-prompt"></a>개발자 명령 프롬프트 열기

1. Windows 10에 Visual Studio 2017 이상을 설치한 경우 시작 메뉴를 열고 **모든 앱**을 선택합니다. 아래로 스크롤하여 Visual Studio 애플리케이션이 아니라 **Visual Studio** 폴더를 엽니다. **VS용 개발자 명령 프롬프트**를 선택하여 명령 프롬프트 창을 엽니다.

   Windows 10에 Microsoft Visual C++ Build Tools 2015를 설치한 경우 **시작** 메뉴를 열고 **모든 앱**을 선택합니다. 아래로 스크롤하여 **Visual C++ Build Tools** 폴더를 엽니다. **Visual C++ 2015 x86 Native Tools 명령 프롬프트**를 선택하여 명령 프롬프트 창을 엽니다.

   Windows 검색 기능을 사용하여 "개발자 명령 프롬프트"를 검색하고 설치된 버전의 Visual Studio와 일치하는 항목을 선택할 수도 있습니다. 바로 가기를 사용하여 명령 프롬프트 창을 엽니다.

1. 다음으로, Visual C++ 개발자 명령 프롬프트가 올바르게 설정되어 있는지 확인합니다. 명령 프롬프트 창에서 `cl`을 입력하고 다음과 같이 출력되는지 확인합니다.

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   현재 디렉터리 또는 버전 번호는 차이가 있을 수 있습니다. 이러한 값은 Visual C++ 버전 및 설치된 업데이트에 따라 달라집니다. 위의 출력과 비슷하게 표시되는 경우 명령줄에서 C 또는 C++ 프로그램을 빌드할 준비가 된 것입니다.

   > [!NOTE]
   > **`cl`** 명령을 실행할 때 "'cl'이 내부 또는 외부 명령, 실행 가능한 프로그램 또는 일괄 처리 파일로 인식되지 않습니다." 같은 오류, 오류 C1034 또는 오류 LNK1104가 표시되면 개발자 명령 프롬프트를 사용하고 있지 않거나 Visual C++ 설치에 문제가 발생한 것입니다. 계속하려면 이 문제를 해결해야 합니다.

   개발자 명령 프롬프트 바로 가기를 찾을 수 없거나 `cl`을 입력할 때 오류 메시지가 표시되는 경우 Visual C++ 설치에 문제가 있을 수 있습니다. Visual Studio에서 Visual C++ 구성 요소를 다시 설치하거나 Microsoft Visual C++ Build Tools를 다시 설치해 보세요. **`cl`** 명령이 작동할 때까지 다음 섹션으로 이동하지 마세요. Visual C++ 설치 및 문제 해결에 대한 자세한 내용은 [Visual Studio 설치](/visualstudio/install/install-visual-studio)를 참조하세요.

   > [!NOTE]
   > 컴퓨터의 Windows 버전 및 시스템 보안 구성에 따라, 이 연습을 수행하여 만드는 프로그램을 빌드하고 실행하려면 마우스 오른쪽 단추를 클릭하여 개발자 명령 프롬프트의 바로 가기 메뉴를 열고 **관리자 권한으로 실행**을 선택해야 할 수도 있습니다.

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Visual C++ 소스 파일을 만들고 명령줄에서 컴파일

1. 개발자 명령 프롬프트 창에서 `md c:\hello`를 입력하여 디렉터리를 만든 다음 `cd c:\hello`를 입력하여 해당 디렉터리로 변경합니다. 이 디렉터리에서 소스 파일 및 컴파일된 프로그램을 만듭니다.

1. 명령 프롬프트 창에 `notepad hello.cpp`를 입력합니다.

   메모장에서 파일을 만들라는 메시지가 표시되면 **예**를 선택합니다. 이 단계에서는 빈 메모장 창을 열어 hello.exe라는 파일에 코드를 입력할 준비를 합니다.

1. 메모장에 다음 코드 줄을 입력합니다.

   ```cpp
   #include <iostream>
   using namespace std;
   int main()
   {
       cout << "Hello, world, from Visual C++!" << endl;
   }
   ```

   이 코드는 화면에 한 줄의 텍스트를 쓴 다음 종료되는 간단한 프로그램입니다. 오류를 최소화하기 위해 이 코드를 복사하여 메모장에 붙여넣습니다.

1. 작업을 저장합니다. 메모장의 **파일** 메뉴에서 **저장**을 선택합니다.

   축하합니다. C++ 소스 파일 hello.cpp를 만들었으며 컴파일할 준비가 되었습니다.

1. 개발자 명령 프롬프트 창으로 다시 전환합니다. 명령 프롬프트에 `dir`를 입력하여 c:\hello 디렉터리의 내용을 나열합니다. 다음과 비슷한 디렉터리 목록에 소스 파일 hello.exe가 표시되어야 합니다.

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

   날짜 및 기타 세부 정보는 컴퓨터마다 다를 수 있습니다. 소스 코드 파일 *hello.cpp*가 표시되지 않는 경우 만든 *c:\\hello* 디렉터리로 변경했는지 확인합니다. 메모장에서 소스 파일을 이 디렉터리에 저장했는지 확인합니다. 또한 소스 코드를 *`.txt`* 파일 이름 확장명이 아닌 *`.cpp`* 확장명을 사용하여 저장했는지 확인합니다.

1. 개발자 명령 프롬프트에 `cl /EHsc hello.cpp`를 입력하여 프로그램을 컴파일합니다.

   cl.exe 컴파일러는 컴파일된 코드가 포함된 .obj 파일을 만든 다음 링커를 실행하여 실행 프로그램인 hello.exe를 만듭니다. 이 이름은 컴파일러에서 표시하는 출력 정보 줄에 나타납니다. 컴파일러 출력은 다음과 비슷합니다.

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
   > "'cl'이 내부 또는 외부 명령, 실행 가능한 프로그램 또는 일괄 처리 파일로 인식되지 않습니다." 같은 오류, 오류 C1034 또는 오류 LNK1104가 표시되면 개발자 명령 프롬프트가 올바로 설정되지 않은 것입니다. 이 문제를 해결하는 방법을 보려면 **개발자 명령 프롬프트 열기** 섹션으로 돌아갑니다.

   > [!NOTE]
   > 다른 컴파일러 또는 링커 오류나 경고가 표시되면 소스 코드를 검토하여 오류를 수정한 다음 저장하고 컴파일러를 다시 실행합니다. 특정 오류에 대한 자세한 내용을 보려면 이 MSDN 페이지의 검색 상자를 사용하여 오류 번호를 확인하세요.

1. hello.exe 프로그램을 실행하려면 명령 프롬프트에서 `hello`를 입력합니다.

   프로그램이 다음 텍스트를 표시하고 종료됩니다.

   ```Output
   Hello, world, from Visual C++!
   ```

   축하합니다. 명령줄 도구를 사용하여 C++ 프로그램을 컴파일하고 실행했습니다.

## <a name="next-steps"></a>다음 단계

이 "Hello, World" 예제는 가장 간단한 C++ 프로그램입니다. 실제 프로그램에는 일반적으로 헤더 파일, 추가 소스 파일, 라이브러리 링크가 있습니다.

이 연습의 단계를 사용하여 표시된 샘플 코드를 입력하는 대신 자체 C++ 코드를 빌드할 수 있습니다. 또한 이러한 단계를 통해 다른 곳에서 구할 수 있는 많은 C++ 코드 샘플 프로그램을 빌드할 수도 있습니다. 쓰기 가능한 모든 디렉터리에서 소스 코드를 배치하고 앱을 빌드할 수 있습니다. 기본적으로 Visual Studio IDE는 *source\\repos* 하위 폴더의 사용자 폴더에 프로젝트를 만듭니다. 이전 버전에서는 *Documents\\Visual Studio \<버전>\\* Projects* 폴더에 프로젝트가 배치될 수도 있습니다.

추가 소스 코드 파일이 있는 프로그램을 컴파일하려면 다음과 같이 명령줄에 모두 입력합니다.

`cl /EHsc file1.cpp file2.cpp file3.cpp`

`/EHsc` 명령줄 옵션은 컴파일러에 표준 C++ 예외 처리 동작을 사용하도록 지시합니다. 이 옵션이 없으면 throw된 예외 때문에 소멸되지 않는 개체와 리소스 누수가 발생할 수 있습니다. 자세한 내용은 [/EH(예외 처리 모델)](reference/eh-exception-handling-model.md)를 참조하세요.

추가 소스 파일을 제공하는 경우 컴파일러는 첫 번째 입력 파일을 사용하여 프로그램 이름을 만듭니다. 이 경우에는 file1.exe라는 프로그램을 출력합니다. 이름을 program1.exe로 변경하려면 [/out](reference/out-output-file-name.md) 링커 옵션을 추가합니다.

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

프로그래밍 실수를 자동으로 포착하려면 [/W3](reference/compiler-option-warning-level.md) 또는 [/W4](reference/compiler-option-warning-level.md) 경고 수준 옵션을 사용하여 컴파일하는 것이 좋습니다.

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

컴파일러 cl.exe에는 더 많은 옵션이 있습니다. 코드를 빌드, 최적화, 디버그 및 분석하는 데 이러한 옵션을 적용할 수 있습니다. 빠른 목록을 보려면 개발자 명령 프롬프트에서 `cl /?`를 입력합니다. 더 복잡한 빌드 시나리오에서 별도로 컴파일 및 연결하고 링커 옵션을 적용할 수도 있습니다. 컴파일러 및 링커 옵션과 사용에 대한 자세한 내용은 [C/C++ 빌드 참조](reference/c-cpp-building-reference.md)를 참조하세요.

NMAKE 및 메이크파일, MSBuild 및 프로젝트 파일 또는 CMake를 사용하여 명령줄에서 더 복잡한 프로젝트를 구성하고 빌드할 수 있습니다. 이러한 도구를 사용하는 방법에 대한 자세한 내용은 [NMAKE 참조](reference/nmake-reference.md), [MSBuild](msbuild-visual-cpp.md) 및 [Visual Studio의 CMake 프로젝트](cmake-projects-in-visual-studio.md)를 참조하세요.

C 언어와 C++ 언어는 비슷하지만 동일하지는 않습니다. MSVC 컴파일러는 간단한 규칙을 사용하여 코드를 컴파일할 때 사용할 언어를 결정합니다. 기본적으로 MSVC 컴파일러는 *`.c`* 로 끝나는 파일은 C 소스 코드로 처리하고 *`.cpp`* 로 끝나는 파일은 C++ 소스 코드로 처리합니다. 컴파일러가 파일 이름 확장명에 관계없이 모든 파일을 C++로 처리하도록 하려면 [/TP](reference/tc-tp-tc-tp-specify-source-file-type.md) 컴파일러 옵션을 사용합니다.

MSVC 컴파일러에는 사소한 예외를 제외하고 ISO C99 표준을 준수하는 CRT(C 런타임 라이브러리)가 포함되어 있습니다. 이식 가능 코드는 일반적으로 정상적으로 컴파일되고 실행됩니다. 일부 사용되지 않는 라이브러리 함수와 여러 POSIX 함수 이름은 MSVC 컴파일러에서 더 이상 사용되지 않습니다. 함수는 지원되지만 기본 설정 이름이 변경되었습니다. 자세한 내용은 [CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md) 및 [컴파일러 경고(수준 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)를 참조하세요.

## <a name="see-also"></a>참조

[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)<br/>
[MSVC 컴파일러 옵션](reference/compiler-options.md)
