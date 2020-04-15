---
title: '연습: 정적 라이브러리 만들기 및 사용(C++)'
description: C++를 사용하여 Visual Studio에서 정적 라이브러리(.lib)를 만듭니다.
ms.custom: get-started-article
ms.date: 04/13/2020
helpviewer_keywords:
- libraries [C++], static
- static libraries [C++]
ms.assetid: 3cc36411-7d66-4240-851e-dacb9a8fd6ac
ms.openlocfilehash: 7148cc1de7c06ae57d61560311b342a1fc9dda1f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335144"
---
# <a name="walkthrough-create-and-use-a-static-library"></a>연습: 정적 라이브러리 만들기 및 사용

이 단계별 연습에서는 C++ 앱에 사용할 수 있도록 정적 라이브러리(.lib 파일)를 만드는 방법을 보여 줍니다. 정적 라이브러리를 사용하면 코드를 매우 편리하게 다시 사용할 수 있습니다. 기능이 필요한 모든 앱에서 동일한 루틴을 다시 구현하는 대신 정적 라이브러리에 한 번 작성한 다음 앱에서 참조합니다. 정적 라이브러리에서 연결된 코드는 앱의 일부가 되며 코드를 사용하기 위해 다른 파일을 설치할 필요가 없습니다.

이 연습에서는 다음 작업 방법을 배웁니다.

- [정적 라이브러리 프로젝트 만들기](#CreateLibProject)

- [정적 라이브러리에 클래스 추가](#AddClassToLib)

- [정적 라이브러리를 참조하는 C++ 콘솔 앱 만들기](#CreateAppToRefTheLib)

- [앱의 정적 라이브러리의 기능 사용](#UseLibInApp)

- [앱 실행](#RunApp)

## <a name="prerequisites"></a>사전 요구 사항

C++ 언어의 기본적인 사항을 알고 있어야 합니다.

## <a name="create-a-static-library-project"></a><a name="CreateLibProject"></a>정적 라이브러리 프로젝트 만들기

프로젝트를 만드는 방법에 대한 지침은 Visual Studio 버전에 따라 다릅니다. 선호하는 버전의 Visual Studio에 대한 설명서를 보려면 **버전** 선택기 컨트롤을 사용합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker range="vs-2019"

### <a name="to-create-a-static-library-project-in-visual-studio-2019"></a>Visual Studio 2019에서 정적 라이브러리 프로젝트를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트 만들기** 대화 상자를 엽니다.

1. 대화 상자 맨 위에서 **언어**를 **C++** 로 설정하고 **플랫폼**을 **Windows**로 설정하고 **프로젝트 형식**을 **라이브러리**로 설정합니다.

1. 필터링된 프로젝트 유형 목록에서 **Windows 데스크톱 마법사를**선택한 다음 **다음을**선택합니다.

1. 새 **프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 *MathLibrary를* 입력하여 프로젝트의 이름을 지정합니다. **솔루션 이름** 상자에 *StaticMath를* 입력합니다. 만들기 **단추를** 선택하여 Windows 데스크톱 프로젝트 대화 상자를 **엽니다.**

1. Windows **데스크톱 프로젝트** 대화 상자에서 **응용 프로그램 유형에서** **정적 라이브러리(.lib)를 선택합니다.**

1. **추가 옵션에서**미리 **컴파일된 헤더** 확인란을 선택 취소합니다. 빈 **프로젝트** 상자를 선택합니다.

1. 프로젝트를 만들려면 **확인을** 선택합니다.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-static-library-project-in-visual-studio-2017"></a>Visual Studio 2017에서 정적 라이브러리 프로젝트를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

1. 새 **프로젝트** 대화 상자에서 **설치된** > **시각적 C++** > **Windows 데스크톱을**선택합니다. 가운데 창에서 **Windows 데스크톱 마법사**를 선택합니다.

1. **이름** 상자에 프로젝트의 이름을 지정합니다.예: *MathLibrary-이름*상자에 있습니다. 솔루션 이름 상자에 *StaticMath와*같은 **솔루션이름을** 지정합니다. **확인** 단추를 선택합니다.

1. Windows **데스크톱 프로젝트** 대화 상자에서 **응용 프로그램 유형에서** **정적 라이브러리(.lib)를 선택합니다.**

1. **추가 옵션에서**미리 **컴파일된 헤더** 확인란을 선택 취소합니다. 빈 **프로젝트** 상자를 선택합니다.

1. 프로젝트를 만들려면 **확인을** 선택합니다.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-static-library-project-in-visual-studio-2015"></a>Visual Studio 2015에서 정적 라이브러리 프로젝트를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

1. 새 **프로젝트** 대화 상자에서 **설치된** > **템플릿** > **시각적 C++** > **Win32를**선택합니다. 가운데 창에서 **Win32 콘솔 애플리케이션**을 선택합니다.

1. **이름** 상자에 프로젝트의 이름을 지정합니다.예: *MathLibrary-이름*상자에 있습니다. 솔루션 이름 상자에 *StaticMath와*같은 **솔루션이름을** 지정합니다. **확인** 단추를 선택합니다.

1. **Win32 응용 프로그램 마법사에서** **다음을 선택합니다.**

1. 응용 **프로그램 설정** 페이지에서 **응용 프로그램 유형**에서 정적 **라이브러리를**선택합니다. **추가 옵션에서**미리 컴파일된 헤더 확인란을 선택 **취소합니다.** 프로젝트를 작성하려면 **완료를** 선택합니다.

::: moniker-end

## <a name="add-a-class-to-the-static-library"></a><a name="AddClassToLib"></a>정적 라이브러리에 클래스 추가

### <a name="to-add-a-class-to-the-static-library"></a>정적 라이브러리에 클래스를 추가하려면

1. 새 클래스에 대한 헤더 파일을 만들려면 마우스 오른쪽 단추를 클릭하여 솔루션 **탐색기에서** **MathLibrary** 프로젝트의 바로 가기 메뉴를 연 다음**새 항목** **추가를** > 선택합니다.

1. 새 **항목 추가** 대화 상자에서 **Visual C++** > **코드를**선택합니다. 가운데 창에서 **헤더 파일 (.h)** 을 선택합니다. 헤더 파일의 이름을 지정합니다(예: *MathLibrary.h)를*선택한 다음 **추가** 단추를 선택합니다. 거의 빈 헤더 파일이 표시됩니다.

1. 덧셈, 뺄셈, `Arithmetic` 곱셈 및 분할과 같은 일반적인 수학 연산을 수행하도록 명명된 클래스에 대한 선언을 추가합니다. 코드는 다음과 유사해야 합니다.

    ```cpp
    // MathLibrary.h
    #pragma once

    namespace MathLibrary
    {
        class Arithmetic
        {
        public:
            // Returns a + b
            static double Add(double a, double b);

            // Returns a - b
            static double Subtract(double a, double b);

            // Returns a * b
            static double Multiply(double a, double b);

            // Returns a / b
            static double Divide(double a, double b);
        };
    }
    ```

1. 새 클래스에 대한 소스 파일을 만들려면 **솔루션 탐색기에서** **MathLibrary** 프로젝트의 바로 가기 메뉴를 연 다음**새 항목** **추가를** > 선택합니다.

1. 새 **항목 추가** 대화 상자에서 중앙 창에서 **C++ 파일(.cpp)을 선택합니다.** 소스 파일의 이름을 지정합니다(예: *MathLibrary.cpp)를*선택한 다음 **추가** 단추를 선택합니다. 빈 소스 파일이 표시됩니다.

1. 이 소스 파일을 사용하여 클래스에 `Arithmetic`대한 기능을 구현합니다. 코드는 다음과 유사해야 합니다.

    ```cpp
    // MathLibrary.cpp
    // compile with: cl /c /EHsc MathLibrary.cpp
    // post-build command: lib MathLibrary.obj

    #include "MathLibrary.h"

    namespace MathLibrary
    {
        double Arithmetic::Add(double a, double b)
        {
            return a + b;
        }

        double Arithmetic::Subtract(double a, double b)
        {
            return a - b;
        }

        double Arithmetic::Multiply(double a, double b)
        {
            return a * b;
        }

        double Arithmetic::Divide(double a, double b)
        {
            return a / b;
        }
    }
    ```

1. 정적 라이브러리를 빌드하려면 메뉴 모음에서 > **솔루션** **빌드빌드를**선택합니다. 빌드는 다른 프로그램에서 사용할 수 있는 정적 라이브러리인 *MathLibrary.lib를*만듭니다.

   > [!NOTE]
   > Visual Studio 명령줄에서 빌드하는 경우 프로그램을 빌드하는 데 두 단계를 거쳐야 합니다. 먼저 코드를 `cl /c /EHsc MathLibrary.cpp` 컴파일하고 *MathLibrary.obj라는*이름의 개체 파일을 만듭니다. 명령 `cl` (명령은 컴파일러, Cl.exe를 호출하고 `/c` 옵션은 연결하지 않고 컴파일을 지정합니다. 자세한 내용은 [/c(연결 하지 않고 컴파일)를](../build/reference/c-compile-without-linking.md)참조하십시오. 둘째, `lib MathLibrary.obj` 코드를 연결하고 정적 라이브러리 *MathLibrary.lib를*만들 실행합니다. `lib` 명령은 Lib.exe 라이브러리 관리자를 호출합니다. 자세한 내용은 [LIB Reference](../build/reference/lib-reference.md)를 참조하세요.

## <a name="create-a-c-console-app-that-references-the-static-library"></a><a name="CreateAppToRefTheLib"></a>정적 라이브러리를 참조하는 C++ 콘솔 앱 만들기

::: moniker range="vs-2019"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2019"></a>Visual Studio 2019에서 정적 라이브러리를 참조하는 C++ 콘솔 앱을 만들려면

1. **솔루션 탐색기에서**맨 위 노드인 **솔루션 'StaticMath'를**마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다. **새 프로젝트** **추가를** > 선택하여 새 프로젝트 추가 대화 상자를 **엽니다.**

1. 대화 상자 맨 위에 프로젝트 **유형** 필터를 **콘솔**로 설정합니다.

1. 필터링된 프로젝트 형식 목록에서 **콘솔 앱**을 선택한 후 **다음**을 선택합니다. 다음 페이지에서 **이름** 상자에 *MathClient를* 입력하여 프로젝트의 이름을 지정합니다.

1. **만들기** 단추를 선택하여 클라이언트 프로젝트를 만듭니다.

1. 콘솔 응용 프로그램을 만들면 빈 프로그램이 만들어집니다. 소스 파일의 이름은 앞에서 선택한 이름과 동일하게 설정됩니다. 이 예제에서는 이름이 지정됩니다. `MathClient.cpp`

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2017"></a>Visual Studio 2017에서 정적 라이브러리를 참조하는 C++ 콘솔 앱을 만들려면

1. **솔루션 탐색기에서**맨 위 노드인 **솔루션 'StaticMath'를**마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다. **새 프로젝트** **추가를** > 선택하여 새 프로젝트 추가 대화 상자를 **엽니다.**

1. 새 **프로젝트 추가** 대화 상자에서 **설치된** > **Visual C++** > **Windows 데스크톱을**선택합니다. 가운데 창에서 **Windows 데스크톱 마법사**를 선택합니다.

1. **이름** 상자에 프로젝트의 이름을 지정합니다.예: *MathClient-이름*상자에 있습니다. **확인** 단추를 선택합니다.

1. Windows **데스크톱 프로젝트** 대화 상자에서 **응용 프로그램 유형에서** **콘솔 응용 프로그램(.exe)을 선택합니다.**

1. **추가 옵션에서**미리 **컴파일된 헤더** 확인란을 선택 취소합니다.

1. 프로젝트를 만들려면 **확인을** 선택합니다.

1. 콘솔 응용 프로그램을 만들면 빈 프로그램이 만들어집니다. 소스 파일의 이름은 앞에서 선택한 이름과 동일하게 설정됩니다. 이 예제에서는 이름이 지정됩니다. `MathClient.cpp`

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-c-console-app-that-references-the-static-library-in-visual-studio-2015"></a>Visual Studio 2015에서 정적 라이브러리를 참조하는 C++ 콘솔 앱을 만들려면

1. **솔루션 탐색기에서**맨 위 노드인 **솔루션 'StaticMath'를**마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다. **새 프로젝트** **추가를** > 선택하여 새 프로젝트 추가 대화 상자를 **엽니다.**

1. 새 **프로젝트 추가** 대화 상자에서 **설치된** > **시각적 C++** > **Win32를**선택합니다. 가운데 창에서 **Win32 콘솔 애플리케이션**을 선택합니다.

1. **이름** 상자에 프로젝트의 이름을 지정합니다.예: *MathClient-이름*상자에 있습니다. **확인** 단추를 선택합니다.

1. **Win32 응용 프로그램 마법사** 대화 상자에서 **다음을**선택합니다.

1. 응용 **프로그램 설정** 페이지에서 **응용 프로그램 유형**에서 콘솔 응용 **프로그램이** 선택되어 있는지 확인합니다. **추가 옵션에서** **미리 컴파일된 헤더를**선택 취소한 다음 **빈 프로젝트** 확인란을 선택합니다. 프로젝트를 작성하려면 **완료를** 선택합니다.

1. 빈 프로젝트에 소스 파일을 추가하려면 마우스 오른쪽 단추를 클릭하여 **솔루션 탐색기에서** **MathClient** 프로젝트의 바로 가기 메뉴를 연 다음 **새 항목** **추가를** > 선택합니다.

1. 새 **항목 추가** 대화 상자에서 **Visual C++** > **코드를**선택합니다. 가운데 창에서 **C++ 파일 (.cpp)** 을 선택합니다. 소스 파일의 이름을 지정합니다(예: *MathClient.cpp)를*선택한 다음 **추가** 단추를 선택합니다. 빈 소스 파일이 표시됩니다.

::: moniker-end

## <a name="use-the-functionality-from-the-static-library-in-the-app"></a><a name="UseLibInApp"></a>앱의 정적 라이브러리의 기능 사용

### <a name="to-use-the-functionality-from-the-static-library-in-the-app"></a>앱에서 정적 라이브러리의 기능을 사용하려면

1. 정적 라이브러리에서 수학 루틴을 사용하기 전에 이를 참조해야 합니다. **솔루션 탐색기에서** **MathClient** 프로젝트의 바로 가기 메뉴를 연 다음**참조** **추가를** > 선택합니다.

1. **참조 추가** 대화 상자에는 참조할 수 있는 라이브러리의 목록이 표시됩니다. **프로젝트** 탭에는 현재 솔루션의 프로젝트와 해당 라이브러리가 참조하는 라이브러리가 나열됩니다. **프로젝트** 탭을 열고 **MathLibrary** 확인란을 선택한 다음 **확인** 단추를 선택합니다.

1. `MathLibrary.h` 헤더 파일을 참조하려면 포함된 디렉터리 경로를 수정해야 합니다. **솔루션 탐색기에서** **MathClient를** 마우스 오른쪽 버튼으로 클릭하여 바로 가기 메뉴를 엽니다. **MathClient 속성** **페이지** 대화 상자를 열려면 속성을 선택합니다.

1. **MathClient 속성 페이지** 대화 상자에서 **구성** 드롭다운을 **모든 구성으로 설정합니다.** **플랫폼** 드롭다운을 **모든 플랫폼으로**설정합니다.

1. 구성 **속성** > **C/C++** > **일반** 속성 페이지를 선택합니다. 추가 **디렉터리** 속성에서 **MathLibrary** 디렉터리 경로를 지정하거나 찾아봅을 지정합니다.

   디렉터리 경로를 찾아보려면 다음을 수행하십시오.

   1. 추가 **디렉터리 속성** 값 드롭다운 목록을 연 다음 **편집을**선택합니다.

   1. **디렉터리 추가** 대화 상자에서 텍스트 상자 상단을 두 번 클릭합니다. 그런 다음 줄 끝에 있는 타원 단추 **(...**) 를 선택합니다.

   1. **디렉터리 선택** 대화 상자에서 레벨을 탐색한 다음 **MathLibrary** 디렉터리를 선택합니다. 그런 다음 **폴더 선택** 단추를 선택하여 선택 항목을 저장합니다.

   1. **디렉터리 추가** 대화 상자에서 **확인** 단추를 선택합니다.

   1. 속성 **페이지** 대화 상자에서 **확인** 단추를 선택하여 변경 내용을 프로젝트에 저장합니다.

1. 이제 코드에 `Arithmetic` 헤더를 포함하여이 응용 `#include "MathLibrary.h"` 프로그램에서 클래스를 사용할 수 있습니다. 다음 `MathClient.cpp` 의 내용을 이 코드로 바꿉니다.

    ```cpp
    // MathClient.cpp
    // compile with: cl /EHsc MathClient.cpp /link MathLibrary.lib

    #include <iostream>
    #include "MathLibrary.h"

    int main()
    {
        double a = 7.4;
        int b = 99;

        std::cout << "a + b = " <<
            MathLibrary::Arithmetic::Add(a, b) << std::endl;
        std::cout << "a - b = " <<
            MathLibrary::Arithmetic::Subtract(a, b) << std::endl;
        std::cout << "a * b = " <<
            MathLibrary::Arithmetic::Multiply(a, b) << std::endl;
        std::cout << "a / b = " <<
            MathLibrary::Arithmetic::Divide(a, b) << std::endl;

        return 0;
    }
    ```

1. 실행 을 빌드하려면 메뉴 모음에서**빌드 솔루션** **빌드를** > 선택합니다.

## <a name="run-the-app"></a><a name="RunApp"></a>앱 실행

### <a name="to-run-the-app"></a>앱을 실행하려면

1. **MathClient가** 기본 프로젝트로 선택되어 있는지 확인합니다. 이를 선택하려면 마우스 오른쪽 단추를 클릭하여 **솔루션 탐색기에서** **MathClient의** 바로 가기 메뉴를 연 다음 **시작 프로젝트로 설정을**선택합니다.

1. 프로젝트를 실행하려면 메뉴 모음에서 디버깅 없이 **디버그** > **시작을 선택합니다.** 출력은 다음과 유사해야 합니다.

    ```Output
    a + b = 106.4
    a - b = -91.6
    a * b = 732.6
    a / b = 0.0747475
    ```

## <a name="see-also"></a>참고 항목

[연습: 동적 링크 라이브러리 만들기 및 사용(C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
[데스크톱 애플리케이션(Visual C++)](../windows/desktop-applications-visual-cpp.md)<br/>
