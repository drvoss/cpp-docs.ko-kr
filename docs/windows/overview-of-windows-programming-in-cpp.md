---
title: C++의 Windows 프로그래밍 개요
ms.date: 09/17/2019
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
ms.openlocfilehash: 8ab7fbf7c955b1c828ef583aa639eda7409cf167
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359939"
---
# <a name="overview-of-windows-programming-in-c"></a>C++의 Windows 프로그래밍 개요

C++로 만들 수 있는 몇 가지 광범위한 Windows 응용 프로그램 범주가 있습니다. 각각 고유한 프로그래밍 모델과 Windows 관련 라이브러리 집합을 가지고 있지만 C++ 표준 라이브러리 및 타사 C++ 라이브러리를 사용할 수 있습니다.

이 섹션에서는 Visual Studio 및 MFC/ATL 래퍼 라이브러리를 사용하여 Windows 프로그램을 만드는 방법에 대해 설명합니다. Windows 플랫폼 자체에 대한 설명서에는 [Windows 설명서를](/windows/index)참조하십시오.

## <a name="command-line-console-applications"></a>명령줄(콘솔) 응용 프로그램

C++ 콘솔 응용 프로그램은 콘솔 창의 명령줄에서 실행되며 텍스트 출력만 표시할 수 있습니다. 자세한 내용은 [C++ 콘솔 앱 프로젝트 만들기를](../get-started/tutorial-console-cpp.md)참조하십시오.

## <a name="native-desktop-CLIent-applications"></a>네이티브 데스크톱 클라이언트 응용 프로그램

*네이티브 데스크톱 클라이언트 응용 프로그램은* 원래 네이티브 Windows C API [또는 COM(구성 요소 개체 모델) API를](/windows/win32/apiindex/windows-api-list) 사용하여 운영 체제에 액세스하는 C 또는 C++ 창응용 프로그램입니다. 이러한 API는 대부분 C로 작성됩니다. 네이티브 데스크톱 앱을 만드는 방법은 운영 체제 이벤트를 처리하는 C 스타일 메시지 루프를 사용하여 Win32 API를 사용하여 직접 프로그래밍할 수 있습니다. 또는 Win32를 래핑하는 가볍게 개체 지향 C++ 라이브러리인 *Microsoft 파운데이션* 클래스(MFC)를 사용하여 프로그래밍할 수 있습니다. 두 방법 모두 유니버설 Windows 플랫폼(UWP)에 비해 "최신"으로 간주되지는 않지만 둘 다 여전히 완벽하게 지원되며 오늘날 전 세계에서 수백만 줄의 코드가 실행되고 있습니다. 창에서 실행되는 Win32 응용 프로그램은 개발자가 Windows 프로시저 함수 내에서 Windows 메시지와 함께 명시적으로 작업해야 합니다. 이름에도 불구하고 Win32 응용 프로그램은 32비트(x86) 또는 64비트(x64) 바이너리로 컴파일할 수 있습니다. 비주얼 스튜디오 IDE에서 x86 및 Win32는 동의어입니다.
기존 Windows C++ 프로그래밍을 시작하려면 [Win32 및 C++로 시작하기를](/windows/win32/LearnWin32/learn-to-program-for-windows)참조하십시오. Win32에 대한 이해를 얻은 후에는 [MFC 데스크톱 응용 프로그램에](../mfc/mfc-desktop-applications.md)대해 더 쉽게 알아볼 수 있습니다. 정교한 그래픽을 사용하는 기존 C++ 데스크톱 응용 프로그램의 예는 [Hilo: Windows용 C++ 응용 프로그램 개발을](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)참조하십시오.

### <a name="c-or-net"></a>C ++ 또는 .NET?

일반적으로 C#의 .NET 프로그래밍은 덜 복잡하고 오류가 발생하기 쉬우며 Win32 또는 MFC보다 더 현대적인 개체 지향 API를 가합니다. 대부분의 경우 성능이 적절하지 않습니다. .NET은 풍부한 그래픽을 위한 WPF(Windows 프레젠테이션 파운데이션)를 갖추고 있으며 Win32와 최신 Windows 런타임 API를 모두 사용할 수 있습니다. 일반적으로 다음이 필요한 경우 데스크톱 응용 프로그램에 C++를 사용하는 것이 좋습니다.

- 메모리 사용량에 대한 정밀한 제어
- 전력 소비에서 최고의 경제
- 일반 컴퓨팅을 위한 GPU 사용
- 다이렉트X에 대한 액세스
- 표준 C++ 라이브러리의 사용량이 많은 경우

C++의 힘과 효율성을 .NET 프로그래밍과 결합할 수도 있습니다. C#에서 사용자 인터페이스를 만들고 C++/CLI를 사용하여 응용 프로그램에서 기본 C++ 라이브러리를 사용할 수 있습니다. 자세한 내용은 [C++/CLI가 있는 .NET 프로그래밍을](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)참조하십시오.

## <a name="com-components"></a>COM 구성 요소

[구성 요소 개체 모델(COM)은](/windows/win32/com/the-component-object-model) 서로 다른 언어로 작성된 프로그램이 서로 통신할 수 있도록 하는 사양입니다. 많은 Windows 구성 요소는 COM 개체로 구현되며 개체 만들기, 인터페이스 검색 및 개체 소멸에 대한 표준 COM 규칙을 따릅니다.  C++ 데스크톱 응용 프로그램에서 COM 개체를 사용하는 것은 비교적 간단하지만 사용자 고유의 COM 개체를 작성하는 것이 더 좋습니다. [ATL(활성 템플릿 라이브러리)은](../atl/atl-com-desktop-components.md) COM 개발을 간소화하는 매크로 및 도우미 기능을 제공합니다. 자세한 내용은 [ATL COM 데스크톱 구성 요소를](../atl/atl-com-desktop-components.md)참조하십시오.

## <a name="universal-windows-platform-apps"></a>유니버설 Windows 플랫폼 앱

유니버설 윈도우 플랫폼(UWP)은 최신 Windows API입니다. UWP 앱은 모든 Windows 10 장치에서 실행되고 사용자 인터페이스에 XAML을 사용하며 완전히 터치가 가능합니다. UWP에 대한 자세한 내용은 [유니버설 Windows 플랫폼(UWP) 앱](/windows/uwp/get-started/whats-a-uwp) 및 Windows 유니버설 앱 [안내서를](/windows/uwp/get-started/universal-application-platform-guide)참조하십시오.

UWP에 대한 원래 C++ 지원은 (1) C++/CX, 구문 확장이 있는 C++의 방언 또는 (2) 표준 C++ 및 COM을 기반으로 하는 Windows 런타임 라이브러리(WRL)로 구성되었습니다. C++/CX 및 WRL은 모두 계속 지원됩니다. 새 프로젝트의 경우 전적으로 표준 C++를 기반으로 하며 더 빠른 성능을 제공하는 [C++/WinRT를](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)권장합니다.

## <a name="desktop-bridge"></a>데스크톱 브리지

Windows 10에서는 기존 데스크톱 응용 프로그램 또는 COM 개체를 UWP 앱으로 패키징하고 터치와 같은 UWP 기능을 추가하거나 최신 Windows API 집합에서 API를 호출할 수 있습니다. 또한 Visual Studio의 데스크톱 솔루션에 UWP 앱을 추가하고 단일 패키지에 함께 패키징하고 Windows API를 사용하여 앱 간에 통신할 수 있습니다.

Visual Studio 2017 버전 15.4 이상에서는 Windows 응용 프로그램 패키지 프로젝트를 만들어 기존 데스크톱 응용 프로그램을 패키징하는 작업을 크게 간소화할 수 있습니다. 레지스트리 호출 또는 데스크톱 응용 프로그램에서 사용할 수 있는 API에는 몇 가지 제한 사항이 적용됩니다. 그러나 대부분의 경우 앱 패키지에서 실행하는 동안 유사한 기능을 달성하기 위해 대체 코드 경로를 만들 수 있습니다. 자세한 내용은 [데스크톱 브리지](/windows/uwp/porting/desktop-to-uwp-root)를 참조하세요.

## <a name="games"></a>게임

DirectX 게임은 PC 또는 Xbox에서 실행할 수 있습니다. 자세한 내용은 [DirectX 그래픽 및 게임](/windows/win32/directx)을 참조하십시오.

## <a name="sql-server-database-CLIents"></a>SQL Server 데이터베이스 클라이언트

네이티브 코드에서 SQL Server 데이터베이스에 액세스하려면 ODBC 또는 OLE DB를 사용합니다. 자세한 내용은 [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc)를 참조하세요.

## <a name="windows-device-drivers"></a>Windows 디바이스 드라이버

드라이버는 하드웨어 장치의 데이터를 응용 프로그램 및 기타 운영 체제 구성 요소에 액세스할 수 있도록 하는 하위 수준 구성 요소입니다. 자세한 내용은 [WDK(Windows 드라이버 키트)를](/windows-hardware/drivers/index)참조하십시오.

## <a name="windows-services"></a>Windows 서비스

Windows *서비스는* 사용자 상호 작용이 거의 또는 전혀 없이 백그라운드에서 실행할 수 있는 프로그램입니다. 이러한 프로그램을 UNIX 시스템에서 *데몬이라고* 합니다. 자세한 내용은 [서비스](/windows/win32/services/services)를 참조하세요.

## <a name="sdks-libraries-and-header-files"></a>SDK, 라이브러리 및 헤더 파일

Visual Studio에는 C 런타임 라이브러리(CRT), C++ 표준 라이브러리 및 기타 Microsoft 관련 라이브러리가 포함됩니다. 이러한 라이브러리에 대한 헤더 파일이 포함된 폴더의 대부분은 \VC\ 폴더 아래의 Visual Studio 설치 디렉토리에 있습니다. Windows 및 CRT 헤더 파일은 Windows SDK 설치 폴더에 있습니다.

[Vcpkg 패키지 관리자를](../build/vcpkg.md) 사용하면 Windows용 수백 개의 타사 오픈 소스 라이브러리를 편리하게 설치할 수 있습니다.

Microsoft 라이브러리는 다음과 같습니다.

- MFC(Microsoft Foundation Class): 단추, 목록 상자, 트리 뷰 및 기타 컨트롤이 있는 다양한 기능의 사용자 인터페이스가 있는 일반적인 Windows 프로그램, 특히 엔터프라이즈 애플리케이션을 만들기 위한 개체 지향 프레임워크입니다. 자세한 내용은 [MFC Desktop Applications](../mfc/mfc-desktop-applications.md)을 참조하세요.

- ATL(Active Template Library): COM 구성 요소를 만들기 위한 강력한 도우미 라이브러리입니다. 자세한 내용은 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)을 참조하세요.

- C++ AMP(C++ Accelerated Massive Parallelism): GPU에서 고성능 일반 계산 작업에 사용할 수 있는 라이브러리입니다. 자세한 내용은 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)을 참조하세요.

- 동시성 런타임: 다중 코어 및 다중 코어 디바이스에 대한 병렬 및 비동기 프로그래밍 작업을 간소화하는 라이브러리입니다. 자세한 내용은 [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md)을 참조하세요.

많은 Windows 프로그래밍 시나리오에는 Windows 운영 체제 구성 요소에 액세스할 수 있는 헤더 파일을 포함하는 Windows SDK도 필요합니다. 기본적으로 Visual Studio는 Windows SDK를 C++ 데스크톱 워크로드의 구성 요소로 설치하여 유니버설 Windows 앱을 개발할 수 있도록 합니다. UWP 앱을 개발하려면 Windows 10 버전의 Windows SDK가 필요합니다. 자세한 내용은 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)를 참조하십시오. (이전 버전의 Windows에 대한 Windows SDK에 대한 자세한 내용은 [Windows SDK 아카이브를](https://developer.microsoft.com/windows/downloads/sdk-archive)참조하십시오.)

**프로그램 파일(x86)\Windows 키트는** 설치한 모든 버전의 Windows SDK의 기본 위치입니다.

Xbox, Azure 등 다른 플랫폼은 설치가 필요한 고유의 SDK가 있습니다. 자세한 내용은 DirectX 개발자 센터 및 Azure 개발자 센터를 참조하세요.

## <a name="development-tools"></a>개발 도구

Visual Studio는 네이티브 코드에 대한 강력한 디버거, 정적 분석 도구, 그래픽 디버깅 도구, 완벽한 기능을 갖춘 코드 편집기, 유닛 테스트 지원 및 다른 많은 도구와 유틸리티를 포함합니다. 자세한 내용은 [Visual Studio에서 개발을 시작하고](/visualstudio/ide/get-started-developing-with-visual-studio) [Visual Studio에서 C++ 개발 개요를](../overview/overview-of-cpp-development.md)참조하세요.

## <a name="in-this-section"></a>섹션 내용

|제목|설명|
|-----------|-----------------|
|[연습: 표준 C++ 프로그램 만들기](walkthrough-creating-a-standard-cpp-program-cpp.md)| Windows 콘솔 응용 프로그램을 만듭니다.|
|[연습: Windows 데스크톱 애플리케이션 만들기(C++)](walkthrough-creating-windows-desktop-applications-cpp.md)|네이티브 Windows 데스크톱 응용 프로그램을 만듭니다.|
|[Windows 데스크톱 마법사](windows-desktop-wizard.md)|마법사를 사용하여 새 Windows 프로젝트를 만듭니다.|
|[ATL(Active Template Library)](../atl/atl-com-desktop-components.md)|ATL 라이브러리를 사용하여 C++에서 COM 구성 요소를 만듭니다.|
|[MFC(Microsoft Foundation Class)](../mfc/mfc-desktop-applications.md)|MFC를 사용하여 대화 상자 및 컨트롤이 있는 크거나 작은 Windows 응용 프로그램을 만듭니다.|
|[ATL 및 MFC 공유 클래스](../atl-mfc-shared/atl-mfc-shared-classes.md)|ATL 및 MFC에서 공유되는 CString과 같은 클래스를 사용합니다.|
|[데이터 액세스](../data/data-access-in-cpp.md)| 올레 DB 및 ODBC|
|[텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)|Windows에서 다양한 문자열 유형.|
|[DirectX를 사용하여 게임을 만들기 위한 리소스](resources-for-creating-a-game-using-directx.md)
|[방법: Windows 데스크톱 애플리케이션에서 Windows 10 SDK 사용](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows SDK|
|[리소스 파일 작업](working-with-resource-files.md)|이미지, 아이콘, 문자열 테이블 및 기타 리소스를 데스크톱 응용 프로그램에 추가하는 방법.|
|[DirectX를 사용하여 게임을 만들기 위한 리소스(C++)](resources-for-creating-a-game-using-directx.md)|C++에서 게임을 만들기 위한 콘텐츠에 대한 링크입니다.|
|[방법: Windows 데스크톱 애플리케이션에서 Windows 10 SDK 사용](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK를 사용하여 빌드할 프로젝트를 설정하는 단계를 설명합니다.|
|[네이티브 데스크톱 애플리케이션 배포](deploying-native-desktop-applications-visual-cpp.md)|Windows에서 네이티브 응용 프로그램을 배포합니다.|

## <a name="related-articles"></a>관련 문서

|제목|설명|
|-----------|-----------------|
|[비주얼 스튜디오의 C++](../overview/visual-cpp-in-visual-studio.md)|Visual C++ 개발자 콘텐츠에 대한 상위 항목입니다.|
[C++/CLI를 갖춘 .NET 개발](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|.NET 응용 프로그램 및 구성 요소와 통신할 수 있는 네이티브 C++ 라이브러리용 래퍼를 만듭니다.|
|[.NET 및 UWP용 구성 요소 확장](../extensions/component-extensions-for-runtime-platforms.md)|C++/CX 및 C++/CLI에서 공유하는 구문 요소에 대한 참조입니다.|
|[유니버설 Windows 앱(C++)](../cppcx/universal-windows-apps-cpp.md)|C++/CX 또는 WINDOWS 런타임 템플릿 라이브러리(WRL)를 사용하여 UWP 응용 프로그램을 작성합니다.|
|[COM 및 .NET의 C++ 특성](attributes/cpp-attributes-com-net.md)|.NET 또는 COM을 사용하는 Windows 전용 프로그래밍에 대한 비표준 특성입니다.|
