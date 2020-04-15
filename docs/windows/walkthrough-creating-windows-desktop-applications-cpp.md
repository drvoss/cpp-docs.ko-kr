---
title: '연습: 기존 Windows 데스크톱 응용 프로그램 만들기(C++)'
description: Visual Studio, C++및 Win32 API를 사용하여 최소한의 기존 Windows 데스크톱 응용 프로그램을 만드는 방법
ms.custom: get-started-article
ms.date: 11/03/2019
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.openlocfilehash: da74778e79a08dd3ed2b5be0675981425264bdc0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351845"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>연습: 기존 Windows 데스크톱 응용 프로그램 만들기(C++)

이 연습에서는 Visual Studio에서 기존 Windows 데스크톱 응용 프로그램을 만드는 방법을 보여 주며 이 연습에서는 만드는 예제 응용 프로그램은 Windows API를 사용하여 "안녕하세요, Windows 데스크톱"을 표시합니다. 줍니다. 이 연습에서 개발하는 코드를 패턴으로 사용하여 다른 Windows 데스크톱 애플리케이션을 만들 수 있습니다.

Windows API(Win32 API, Windows 데스크톱 API 및 Windows 클래식 API라고도 함)는 Windows 응용 프로그램을 만들기 위한 C 언어 기반 프레임워크입니다. 그것은 1980 년대부터 존재하고 수십 년 동안 Windows 응용 프로그램을 만드는 데 사용되어왔다. Windows API 위에 고급 및 프로그래밍하기 쉬운 프레임워크가 구축되었습니다. 예를 들어 MFC, ATL, .NET 프레임워크를 예로 들 수 있습니다. C++/WinRT로 작성된 UWP 및 스토어 앱에 대한 가장 현대적인 Windows 런타임 코드도 아래Windows API를 사용합니다. Windows API에 대한 자세한 내용은 [Windows API 인덱스를](/windows/win32/apiindex/windows-api-list)참조하십시오. Windows 응용 프로그램을 만드는 방법에는 여러 가지가 있지만 위의 프로세스는 첫 번째입니다.

> [!IMPORTANT]
> 간결하게 하기 위해 일부 코드 문은 텍스트에서 생략됩니다. 이 문서의 끝에 있는 [코드 빌드](#build-the-code) 섹션에는 전체 코드가 표시됩니다.

## <a name="prerequisites"></a>사전 요구 사항

- Microsoft Windows 7 이상 버전을 실행하는 컴퓨터. 최상의 개발 환경을 위해서는 Windows 10이 권장됩니다.

- Visual Studio. Visual Studio를 다운로드 및 설치하는 방법에 대한 자세한 내용은 [Visual Studio 설치](/visualstudio/install/install-visual-studio)를 참조하세요. 설치 관리자를 실행할 때 **C++를 사용한 데스크톱 개발** 워크로드를 선택해야 합니다. Visual Studio를 설치할 때 이 워크로드를 설치하지 않은 경우 걱정하지 마세요. 설치 관리자를 다시 실행하고 바로 설치할 수 있습니다.

   ![C++를 사용한 데스크톱 개발](../build/media/desktop-development-with-cpp.png "C++를 사용한 데스크톱 개발")

- Visual Studio IDE 사용의 기본 사항에 대한 이해. 이전에 Windows 데스크톱 앱을 사용한 경우 내용을 따라갈 수 있습니다. 소개 내용을 살펴보려면 [Visual Studio IDE 기능 둘러보기](/visualstudio/ide/visual-studio-ide)를 참조하세요.

- 내용을 따라가기에 충분한 C++ 언어의 기본 사항에 대한 이해. 너무 복잡한 내용을 다루지는 않으므로 걱정하지 마세요.

## <a name="create-a-windows-desktop-project"></a>Windows 데스크톱 프로젝트 만들기

다음 단계에 따라 첫 번째 Windows 데스크톱 프로젝트를 만듭니다. 이동 하면서 작업 Windows 데스크톱 응용 프로그램에 대 한 코드를 입력 합니다. 선호하는 버전의 Visual Studio에 대한 설명서를 보려면 **버전** 선택기 컨트롤을 사용합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker range="vs-2019"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2019"></a>Visual Studio 2019에서 Windows 데스크톱 프로젝트를 만들려면

1. 주 메뉴에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트 만들기** 대화 상자를 엽니다.

1. 대화 상자 맨 위에 **있는 언어를** **C++로**설정하고 **플랫폼을** **Windows로**설정하고 **프로젝트 유형을** **데스크톱으로**설정합니다.

1. 필터링된 프로젝트 유형 목록에서 **Windows 데스크톱 마법사를** 선택한 다음 **다음**을 선택합니다. 다음 페이지에서 프로젝트의 이름을 입력합니다(예: *DesktopApp.*

1. **만들기** 단추를 선택하여 프로젝트를 만듭니다.

1. 이제 **Windows 데스크톱 프로젝트** 대화 상자가 나타납니다. **응용 프로그램 유형에서** **데스크톱 응용 프로그램(.exe)을 선택합니다.** **추가 옵션**에서 **빈 프로젝트**를 선택합니다. 프로젝트를 만들려면 **확인을** 선택합니다.

1. **솔루션 탐색기에서** **DesktopApp** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **에서 추가를**선택한 다음 **새 항목을**선택합니다.

   ![DesktopApp 프로젝트에 새 항목 추가](../build/media/desktop-app-project-add-new-item-153.gif "DesktopApp 프로젝트에 새 항목 추가")

1. **새 항목 추가** 대화 상자에서 **C++ 파일(.cpp)** 을 선택합니다. **이름** 상자에 파일의 이름을 입력합니다(예: *HelloWindowsDesktop.cpp.* 추가 를 **선택합니다.**

   ![데스크톱 앱 프로젝트에 .cpp 파일 추가](../build/media/desktop-app-add-cpp-file-153.png "데스크톱 앱 프로젝트에 .cpp 파일 추가")

이제 프로젝트가 만들어지고 소스 파일이 편집기에서 열립니다. 계속하려면 앞으로 건너뛰고 [코드 만들기](#create-the-code)를 합니다.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017"></a>Visual Studio 2017에서 Windows 데스크톱 프로젝트를 만들려면

1. **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.

1. 새 **프로젝트** 대화 상자에서 왼쪽 창에서 **설치된** > **Visual C++를**확장한 다음 **Windows 데스크톱을**선택합니다. 중간 창에서 Windows **데스크톱 마법사를**선택합니다.

   **이름** 상자에 프로젝트의 이름을 입력합니다(예: *DesktopApp.* **확인을**선택합니다.

   ![데스크톱 앱 프로젝트 이름 지정](../build/media/desktop-app-new-project-name-153.png "데스크톱 앱 프로젝트 이름 지정")

1. Windows **데스크톱 프로젝트** 대화 상자에서 **응용 프로그램 유형에서** **Windows 응용 프로그램(.exe)을 선택합니다.** **추가 옵션**에서 **빈 프로젝트**를 선택합니다. 미리 **컴파일된 헤더가** 선택되어 있지 않은지 확인합니다. 프로젝트를 만들려면 **확인을** 선택합니다.

1. **솔루션 탐색기에서** **DesktopApp** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **에서 추가를**선택한 다음 **새 항목을**선택합니다.

   ![DesktopApp 프로젝트에 새 항목 추가](../build/media/desktop-app-project-add-new-item-153.gif "DesktopApp 프로젝트에 새 항목 추가")

1. **새 항목 추가** 대화 상자에서 **C++ 파일(.cpp)** 을 선택합니다. **이름** 상자에 파일의 이름을 입력합니다(예: *HelloWindowsDesktop.cpp.* 추가 를 **선택합니다.**

   ![데스크톱 앱 프로젝트에 .cpp 파일 추가](../build/media/desktop-app-add-cpp-file-153.png "데스크톱 앱 프로젝트에 .cpp 파일 추가")

이제 프로젝트가 만들어지고 소스 파일이 편집기에서 열립니다. 계속하려면 앞으로 건너뛰고 [코드 만들기](#create-the-code)를 합니다.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2015"></a>Visual Studio 2015에서 Windows 데스크톱 프로젝트를 만들려면

1. **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.

1. 새 **프로젝트** 대화 상자에서 왼쪽 창에서 **설치된** > **템플릿** > **시각적 C++를**확장한 다음 **Win32를**선택합니다. 가운데 창에서 **Win32 프로젝트**를 선택합니다.

   **이름** 상자에 프로젝트의 이름을 입력합니다(예: *DesktopApp.* **확인을**선택합니다.

   ![데스크톱 앱 프로젝트 이름 지정](../build/media/desktop-app-new-project-name-150.png "데스크톱 앱 프로젝트 이름 지정")

1. **Win32 응용 프로그램 마법사의** **개요** 페이지에서 **다음을 선택합니다.**

   ![Win32 응용 프로그램 마법사 개요에서 데스크톱 앱 만들기](../build/media/desktop-app-win32-wizard-overview-150.png "Win32 응용 프로그램 마법사 개요에서 데스크톱 앱 만들기")

1. 응용 **프로그램 설정** 페이지에서 응용 프로그램 **유형**에서 Windows **응용 프로그램을**선택합니다. **추가 옵션에서** **미리 컴파일된 헤더를**선택 취소한 다음 **빈 프로젝트를**선택합니다. 프로젝트를 작성하려면 **완료를** 선택합니다.

1. **솔루션 탐색기에서**DesktopApp 프로젝트를 마우스 오른쪽 단추로 클릭하고 **에서 추가를**선택한 다음 **새 항목을**선택합니다.

   ![DesktopApp 프로젝트에 새 항목 추가](../build/media/desktop-app-project-add-new-item-150.gif "DesktopApp 프로젝트에 새 항목 추가")

1. **새 항목 추가** 대화 상자에서 **C++ 파일(.cpp)** 을 선택합니다. **이름** 상자에 파일의 이름을 입력합니다(예: *HelloWindowsDesktop.cpp.* 추가 를 **선택합니다.**

   ![데스크톱 앱 프로젝트에 .cpp 파일 추가](../build/media/desktop-app-add-cpp-file-150.png "데스크톱 앱 프로젝트에 .cpp 파일 추가")

이제 프로젝트가 만들어지고 소스 파일이 편집기에서 열립니다.

::: moniker-end

## <a name="create-the-code"></a>코드 만들기

다음으로 Visual Studio에서 Windows 데스크톱 응용 프로그램에 대한 코드를 만드는 방법을 알아봅니다.

### <a name="to-start-a-windows-desktop-application"></a>Windows 데스크톱 애플리케이션을 시작하려면

1. 모든 C 응용 프로그램과 C++ 응용 `main` 프로그램에 는 시작 점으로 함수가 있어야 `WinMain` 하는 것처럼 모든 Windows 데스크톱 응용 프로그램에는 함수가 있어야 합니다. `WinMain` 에는 다음 구문이 있습니다.

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_opt_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   이 함수의 매개 변수 및 반환 값에 대한 자세한 내용은 [WinMain 진입점을](/windows/win32/api/winbase/nf-winbase-winmain)참조하십시오.

   > [!NOTE]
   > `CALLBACK` `HINSTANCE` `_In_` 기존 Windows API는 typedefs 및 전처리기 매크로를 광범위하게 사용하여 호출 규칙, **__declspec** 선언 및 컴파일러 pragmas와 같은 형식 및 플랫폼 별 코드의 세부 정보를 추상화합니다. Visual Studio에서 IntelliSense 빠른 [정보](/visualstudio/ide/using-intellisense#quick-info) 기능을 사용하여 이러한 형식 및 매크로가 정의하는 내용을 확인할 수 있습니다. 관심 있는 단어 위에 마우스를 가리키거나 선택하여 **Ctrl**+**K**, **Ctrl**+**I을** 눌러 정의가 포함된 작은 팝업 창을 확인합니다. 자세한 내용은 [Using IntelliSense](/visualstudio/ide/using-intellisense)을 참조하세요. 매개 변수 및 반환 형식은 종종 프로그래밍 오류를 catch하는 데 도움이 되는 *SAL 주석을* 사용합니다. 자세한 내용은 [SAL 주석 사용을 사용하여 C/C++ 코드 결함을 줄입니다.](/cpp/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects)

1. Windows 데스크톱 &lt;프로그램에는 windows.h> 필요합니다. &lt;tchar.h> `TCHAR` 매크로를 정의하며, 궁극적으로 UNICODE 기호가 프로젝트에 정의되어 있는 경우 **wchar_t** 확인하며, 그렇지 않으면 **char로**확인됩니다.  항상 UNICODE를 사용하도록 설정한 상태로 빌드하는 경우 TCHAR가 필요하지 않으며 **직접 wchar_t** 사용할 수 있습니다.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. `WinMain` 기능과 함께 모든 Windows 데스크톱 응용 프로그램에는 창 프로시저 기능도 있어야 합니다. 이 함수는 `WndProc`일반적으로 이름이 지정되지만 원하는 대로 이름을 지정할 수 있습니다. `WndProc` 에는 다음 구문이 있습니다.

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hWnd,
      _In_ UINT   message,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   이 함수에서는 *이벤트가* 발생할 때 응용 프로그램이 Windows에서 받는 *메시지를* 처리하는 코드를 작성합니다. 예를 들어 사용자가 응용 프로그램에서 확인 단추를 선택하면 Windows에서 사용자에게 메시지를 보내고 함수 내에서 `WndProc` 적절한 작업을 수행하는 코드를 작성할 수 있습니다. 이를 이벤트 *처리라고* 합니다. 응용 프로그램과 관련된 이벤트만 처리합니다.

   자세한 내용은 [창 프로시저](/windows/win32/winmsg/window-procedures)를 참조하세요.

### <a name="to-add-functionality-to-the-winmain-function"></a>WinMain 함수에 기능을 추가하려면

1. 함수에서 `WinMain` [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw)형식의 구조를 채웁니다. 구조에는 창에 대한 정보가 포함되어 있습니다: 응용 프로그램 아이콘, 창의 배경색, 제목 표시줄에 표시할 이름 등입니다. 중요한 것은 창 프로시저에 대한 함수 포인터가 포함되어 있습니다. 다음 예제에서는 일반적인 `WNDCLASSEX` 구조를 보여 줍니다.

   ```cpp
   WNDCLASSEX wcex;

   wcex.cbSize         = sizeof(WNDCLASSEX);
   wcex.style          = CS_HREDRAW | CS_VREDRAW;
   wcex.lpfnWndProc    = WndProc;
   wcex.cbClsExtra     = 0;
   wcex.cbWndExtra     = 0;
   wcex.hInstance      = hInstance;
   wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
   wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
   wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
   wcex.lpszMenuName   = NULL;
   wcex.lpszClassName  = szWindowClass;
   wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);
   ```

   위의 구조 필드에 대한 자세한 내용은 [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw)를 참조하십시오.

1. Windows에 `WNDCLASSEX` 등록하여 창과 메시지를 보내는 방법을 알 수 있습니다. [RegisterClassEx](/windows/win32/api/winuser/nf-winuser-registerclassexw) 함수를 사용하고 창 클래스 구조를 인수로 전달합니다. 매크로는 `_T` 형식을 사용하기 때문에 `TCHAR` 사용됩니다.

   ```cpp
   if (!RegisterClassEx(&wcex))
   {
      MessageBox(NULL,
         _T("Call to RegisterClassEx failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

1. 이제 창을 만들 수 있습니다. [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 함수를 사용합니다.

   ```cpp
   static TCHAR szWindowClass[] = _T("DesktopApp");
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   // The parameters to CreateWindow explained:
   // szWindowClass: the name of the application
   // szTitle: the text that appears in the title bar
   // WS_OVERLAPPEDWINDOW: the type of window to create
   // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
   // 500, 100: initial size (width, length)
   // NULL: the parent of this window
   // NULL: this application does not have a menu bar
   // hInstance: the first parameter from WinMain
   // NULL: not used in this application
   HWND hWnd = CreateWindow(
      szWindowClass,
      szTitle,
      WS_OVERLAPPEDWINDOW,
      CW_USEDEFAULT, CW_USEDEFAULT,
      500, 100,
      NULL,
      NULL,
      hInstance,
      NULL
   );
   if (!hWnd)
   {
      MessageBox(NULL,
         _T("Call to CreateWindow failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

   이 함수는 `HWND`창에 대한 핸들인 를 반환합니다. 핸들은 Windows에서 열린 창을 추적하는 데 사용하는 포인터와 다소 비슷합니다. 자세한 내용은 [Windows 데이터 형식](/windows/win32/WinProg/windows-data-types)을 참조하세요.

1. 이 시점에서 창이 만들어졌지만 Windows에 표시되도록 알려야 합니다. 이 코드는 다음과 같은 작업을 수행합니다.

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   아직 함수를 구현하지 않았기 때문에 표시된 창에는 `WndProc` 많은 콘텐츠가 없습니다. 즉, 응용 프로그램은 Windows에서 보내는 메시지를 아직 처리하지 않습니다.

1. 메시지를 처리하려면 먼저 메시지 루프를 추가하여 Windows에서 보내는 메시지를 수신합니다. 응용 프로그램이 메시지를 받으면 이 루프는 처리할 `WndProc` 함수로 메시지를 전달합니다. 메시지 루프는 다음 코드와 유사합니다.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   메시지 루프의 구조 및 함수에 대한 자세한 내용은 [MSG](/windows/win32/api/winuser/ns-winuser-msg), [GetMessage](/windows/win32/api/winuser/nf-winuser-getmessage), [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)를 참조하세요.

   이때 `WinMain` 함수는 다음 코드와 유사합니다.

   ```cpp
   int WINAPI WinMain(HINSTANCE hInstance,
                      HINSTANCE hPrevInstance,
                      LPSTR lpCmdLine,
                      int nCmdShow)
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application dows not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }
   ```

### <a name="to-add-functionality-to-the-wndproc-function"></a>WndProc 함수에 기능을 추가하려면

1. `WndProc` 함수에서 애플리케이션이 받는 메시지를 처리하게 하려면 switch 문을 구현합니다.

   처리해야 할 중요한 메시지 중 하나는 [WM_PAINT](/windows/win32/gdi/wm-paint) 메시지입니다. 응용 프로그램은 `WM_PAINT` 표시된 창의 일부를 업데이트해야 하는 경우 메시지를 수신합니다. 이 이벤트는 사용자가 창 앞에서 창을 이동한 다음 다시 이동할 때 발생할 수 있습니다. 응용 프로그램에서 이러한 이벤트가 발생하는 시기를 알 수 없습니다. Windows만 알고 있으므로 앱에 메시지를 알수 있습니다. `WM_PAINT` 창이 처음 표시되면 모든 창을 업데이트해야 합니다.

   `WM_PAINT` 메시지를 처리하려면 먼저 [BeginPaint](/windows/win32/api/winuser/nf-winuser-beginpaint)를 호출하고, 모든 논리를 처리하여 창에 텍스트, 단추 및 기타 컨트롤을 배치하고, [EndPaint](/windows/win32/api/winuser/nf-winuser-endpaint)를 호출합니다. 응용 프로그램의 경우 시작 호출과 끝 호출 사이의 논리는 "안녕하세요, Windows 데스크톱!" 문자열을 표시하는 것입니다. 것입니다. 다음 코드에서 [TextOut](/windows/win32/api/wingdi/nf-wingdi-textoutw) 함수는 문자열을 표시하는 데 사용됩니다.

   ```cpp
   PAINTSTRUCT ps;
   HDC hdc;
   TCHAR greeting[] = _T("Hello, Windows desktop!");

   switch (message)
   {
   case WM_PAINT:
      hdc = BeginPaint(hWnd, &ps);

      // Here your application is laid out.
      // For this introduction, we just print out "Hello, Windows desktop!"
      // in the top left corner.
      TextOut(hdc,
         5, 5,
         greeting, _tcslen(greeting));
      // End application-specific layout section.

      EndPaint(hWnd, &ps);
      break;
   }
   ```

   `HDC`코드에는 Windows에서 응용 프로그램이 그래픽 하위 시스템과 통신할 수 있도록 하는 데 사용하는 데이터 구조인 장치 컨텍스트에 대한 핸들이 있습니다. `BeginPaint` 및 `EndPaint` 기능은 응용 프로그램이 좋은 시민처럼 행동하게하고 필요한 것보다 더 오랫동안 장치 컨텍스트를 사용하지 않습니다. 이 기능은 그래픽 하위 시스템을 다른 응용 프로그램에서 사용할 수 있도록 하는 데 도움이 됩니다.

1. 응용 프로그램은 일반적으로 다른 많은 메시지를 처리합니다. 예를 [들어](/windows/win32/winmsg/wm-create) 창이 처음 생성되는 WM_CREATE 창이 닫히면 [WM_DESTROY.](/windows/win32/winmsg/wm-destroy) 다음 코드에서는 기본적인 전체 `WndProc` 함수를 보여 줍니다.

   ```cpp
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

## <a name="build-the-code"></a>코드 빌드

약속대로 작업 중인 응용 프로그램에 대한 전체 코드는 다음과 같습니다.

### <a name="to-build-this-example"></a>이 예제를 빌드하려면

1. 편집기에서 *HelloWindowsDesktop.cpp에* 입력한 코드를 모두 삭제합니다. 이 예제 코드를 복사 한 다음 *HelloWindowsDesktop.cpp에*붙여 넣습니다.

   ```cpp
   // HelloWindowsDesktop.cpp
   // compile with: /D_UNICODE /DUNICODE /DWIN32 /D_WINDOWS /c

   #include <windows.h>
   #include <stdlib.h>
   #include <string.h>
   #include <tchar.h>

   // Global variables

   // The main window class name.
   static TCHAR szWindowClass[] = _T("DesktopApp");

   // The string that appears in the application's title bar.
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   HINSTANCE hInst;

   // Forward declarations of functions included in this code module:
   LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);

   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_opt_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   )
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application does not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }

   //  FUNCTION: WndProc(HWND, UINT, WPARAM, LPARAM)
   //
   //  PURPOSE:  Processes messages for the main window.
   //
   //  WM_PAINT    - Paint the main window
   //  WM_DESTROY  - post a quit message and return
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application-specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

1. **빌드** 메뉴에서 **솔루션 빌드를**선택합니다. 컴파일 결과는 Visual Studio의 **출력** 창에 나타납니다.

   ![데스크톱 앱 프로젝트 빌드](../build/media/desktop-app-project-build-150.gif "데스크톱 앱 프로젝트 빌드")

1. 응용 프로그램을 실행하려면 **F5** 키를 누릅니다. "안녕하세요, Windows 바탕 화면!" 텍스트가 들어 있는 창입니다. 디스플레이의 왼쪽 위에 표시됩니다.

   ![데스크톱 앱 프로젝트 실행](../build/media/desktop-app-project-run-157.PNG "데스크톱 앱 프로젝트 실행")

축하합니다! 이 연습을 완료하고 기존 Windows 데스크톱 응용 프로그램을 빌드했습니다.

## <a name="see-also"></a>참고 항목

[Windows 데스크톱 응용 프로그램](../windows/windows-desktop-applications-cpp.md)
