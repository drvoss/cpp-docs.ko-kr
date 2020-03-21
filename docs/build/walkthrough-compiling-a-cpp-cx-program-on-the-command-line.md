---
title: '연습: 명령줄에서 C++/CX 프로그램 컴파일'
ms.date: 04/23/2019
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
ms.openlocfilehash: 83369fc7b458463ea1f44a347bbcd0ca4eb32224
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078203"
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>연습: 명령줄에서 C++/CX 프로그램 컴파일

> [!NOTE]
> 새 UWP 앱 및 구성 요소의 경우 Windows 런타임 api에 대 한 표준 c + + 17 언어 프로젝션 인 [ C++/winrt](/windows/uwp/cpp-and-winrt-apis/)를 사용 하는 것이 좋습니다. C++/WinRT는 Windows 10 SDK에서 버전 1803 이후 버전으로 제공 됩니다. C++/WinRT는 헤더 파일에 완전히 구현 되며 최신 Windows API에 대 한 최고 수준의 액세스를 제공 하도록 설계 되었습니다.

Microsoft C++ 컴파일러 (MSVC)는 Windows 런타임 C++ 프로그래밍 모델을C++대상으로 하는 추가 형식 및 연산자가 있는/cx (구성 요소 확장)를 지원 합니다. /Cx를 사용 C++하 여 UWP (유니버설 Windows 플랫폼 용 앱) 및 Windows 데스크톱을 빌드할 수 있습니다. 자세한 내용은 런타임 플랫폼의 [ C++/Cx](https://msdn.microsoft.com/magazine/dn166929.aspx) 및 [구성 요소 확장](../extensions/component-extensions-for-runtime-platforms.md)둘러보기를 참조 하세요.

이 연습에서는 텍스트 편집기를 사용하여 기본적인 C++/CX 프로그램을 만든 다음 명령줄에서 컴파일합니다. 여기에 나와 있는 내용을 입력하는 대신 C++/CX 프로그램을 직접 사용할 수도 있고 다른 도움말 문서의 C++/CX 코드 샘플을 사용할 수도 있습니다. 이 기술은 UI 요소가 없는 작은 모듈을 빌드하고 테스트 하는 데 유용 합니다.

> [!NOTE]
> 또한 Visual Studio IDE를 사용하여 C++/CX 프로그램을 컴파일할 수 있습니다. IDE는 명령줄에서 사용할 수 없는 디자인, 디버깅, 에뮬레이션 및 배포 지원을 포함 하기 때문에 IDE를 사용 하 여 UWP (유니버설 Windows 플랫폼) 앱을 빌드하는 것이 좋습니다. 자세한 내용은 [에서 C++UWP 앱 만들기 ](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)를 참조 하세요.

## <a name="prerequisites"></a>필수 조건

C++ 언어의 기본적인 사항을 알고 있습니다.

## <a name="compiling-a-ccx-program"></a>C++/CX 프로그램 컴파일

/Cx에 대해 C++컴파일을 사용 하도록 설정 하려면 [/zw](reference/zw-windows-runtime-compilation.md) 컴파일러 옵션을 사용 해야 합니다. MSVC 컴파일러는 Windows 런타임를 대상으로 하는 .exe 파일을 생성 하 고 필요한 라이브러리에 대 한 링크를 제공 합니다.

#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>명령줄에서 C++/CX 애플리케이션을 컴파일하려면

1. **개발자 명령 프롬프트** 창을 엽니다. **시작** 창에서 **앱**을 엽니다. 해당 버전의 Visual Studio에서 **Visual Studio Tools** 폴더를 열고 **개발자 명령 프롬프트** 바로 가기를 선택 합니다.) 개발자 명령 프롬프트 창을 여는 방법에 대 한 자세한 내용은 [명령줄에서 MSVC 도구 집합 사용](building-on-the-command-line.md)을 참조 하세요.

   컴퓨터 운영 체제 및 구성에 따라 코드를 정상적으로 컴파일하려면 관리자 자격 증명이 필요할 수 있습니다. 관리자 권한으로 명령 프롬프트 창을 실행 하려면 **개발자 명령 프롬프트** 에 대 한 바로 가기 메뉴를 연 다음 **관리자 권한으로 실행**을 선택 합니다.

1. 명령 프롬프트에서 **notepad basiccx .cpp**를 입력 합니다.

   파일을 만들지 묻는 메시지가 표시 되 면 **예** 를 선택 합니다.

1. 메모장에 다음 줄을 입력합니다.

    ```cpp
    using namespace Platform;

    int main(Platform::Array<Platform::String^>^ args)
    {
        Platform::Details::Console::WriteLine("This is a C++/CX program.");
    }
    ```

1. 메뉴 모음에서 **파일** > **저장**을 선택 합니다.

   Windows 런타임 [Platform 네임](../cppcx/platform-namespace-c-cx.md) 스페이스 C++ 네임 스페이스를 사용 하는 소스 파일을 만들었습니다.

1. 명령 프롬프트에서 **cl/ehsc/ZW basiccx. .cpp/LINK/SUBSYSTEM: CONSOLE**을 입력 합니다. cl.exe 컴파일러는 이 소스 파일을 .obj 파일로 컴파일한 다음 링커를 실행하여 실행 프로그램인 basiccx.exe를 생성합니다. [/Ehsc](reference/eh-exception-handling-model.md) 컴파일러 옵션은 C++ 예외 처리 모델을 지정 하 고 [/link](reference/link-pass-options-to-linker.md) 플래그는 콘솔 응용 프로그램을 지정 합니다.

1. Basiccx.exe .exe 프로그램을 실행 하려면 명령 프롬프트에서 **basiccx.exe**를 입력 합니다.

   프로그램이 다음 텍스트를 표시하고 종료됩니다.

    ```Output
    This is a C++/CX program.
    ```

## <a name="see-also"></a>참고 항목

[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)<br/>
[MSVC 컴파일러 옵션](reference/compiler-options.md)
