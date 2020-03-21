---
title: C++를 이용한 Windows 프로그래밍 개요
ms.date: 09/17/2019
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
ms.openlocfilehash: cd95332721f51ed2d17c3205cba5f1456a1037b9
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075496"
---
# <a name="overview-of-windows-programming-in-c"></a>C++를 이용한 Windows 프로그래밍 개요

C++를 사용하면 다양한 종류의 Windows 응용 프로그램을 만들 수 있습니다. 각각 고유한 프로그래밍 모델과 Windows 관련 라이브러리 집합이 있지만 C++ 표준 라이브러리나 타사 C++ 라이브러리도 사용할 수 있습니다.

이 섹션에서는 Visual Studio 및 MFC/ATL 래퍼 라이브러리를 사용하여 Windows 프로그램을 만드는 방법을 설명합니다. Windows 플랫폼 자체에 대 한 설명서는 [windows 설명서](/windows/index)를 참조 하십시오.

## <a name="command-line-console-applications"></a>명령줄(콘솔) 응용 프로그램

C++ 콘솔 응용 프로그램은 콘솔 창의 명령줄에서 실행되고 텍스트 출력만 표시할 수 있습니다. 자세한 내용은 [ C++ 콘솔 응용 프로그램 프로젝트 만들기](../get-started/tutorial-console-cpp.md)를 참조 하세요.

## <a name="native-desktop-client-applications"></a>네이티브 데스크톱 클라이언트 응용 프로그램

*네이티브 데스크톱 클라이언트 응용 프로그램* 은 원래 네이티브 C++ [Windows c Api 또는 COM (구성 요소 개체 모델) api](/windows/win32/apiindex/windows-api-list) 를 사용 하 여 운영 체제에 액세스 하는 C 또는 창 응용 프로그램입니다. 이러한 Api는 대부분 C로 작성 됩니다. 네이티브 데스크톱 응용 프로그램을 만드는 방법에는 여러 가지가 있습니다. 즉, 운영 체제 이벤트를 처리 하는 C 스타일 메시지 루프를 사용 하 여 Win32 Api를 직접 사용할 수 있습니다. 또는 Win32를 래핑하는 약간 *Microsoft Foundation Classes* 의 개체 지향 C++ 라이브러리인 Microsoft Foundation Classes (MFC)를 사용 하 여 프로그래밍할 수 있습니다. 이러한 접근법은 유니버설 Windows 플랫폼(UWP)과 비교하여 "현대적"이라고 간주되지는 않지만, 두 방법 모두 여전히 완전하게 지원되며 지금도 전 세계적으로 수백만 줄의 코드가 실행되고 있습니다. 윈도우에서 실행되는 Win32 응용 프로그램의 경우 개발자는 Windows 프로시저 함수 내에서 Windows 메시지를 명시적으로 사용해야 합니다. 이름과는 달리 Win32 응용 프로그램은 32비트(x86) 또는 64비트(x64) 바이너리로 컴파일될 수 있습니다. Visual Studio IDE에서 x86 및 Win32라는 용어는 동의어입니다.

기존 Windows C++ 프로그래밍을 시작 하려면 [Win32 및 C++시작 ](/windows/win32/LearnWin32/learn-to-program-for-windows)을 참조 하세요. Win32를 이해 하 고 나면 [MFC 데스크톱 응용 프로그램](../mfc/mfc-desktop-applications.md)에 대해 더 쉽게 알아볼 수 있습니다. 정교한 그래픽을 사용 하는 C++ 기존 데스크톱 응용 프로그램의 예는 [Hilo: Windows 용 C++ 응용 프로그램 개발](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)을 참조 하세요.

### <a name="c-or-net"></a>C++? .NET?

일반적으로의 C# .NET 프로그래밍은 덜 복잡하고 오류가 덜 발생하며 WIN32 또는 MFC 보다 최신 객체 지향 API를 포함합니다. 대부분의 상황에서 적합한 성능을 얻을 수 있기 때문입니다. .NET은 다양한 그래픽을 위한 Windows Presentation Foundation(WPF) 기능을 제공하며, Win32 및 최신 Windows 런타임 API를 모두 사용할 수 있습니다. 아래의 경우 일반적으로 데스크탑 응용 프로그램에 C++를 사용할 것을 권장합니다.

- 메모리 사용량에 대한 정밀한 제어
- 전력 소비 효율의 극대화
- GPU 사용한 일반 연산
- DirectX에 대한 액세스
- 표준 C++ 라이브러리의 대량 사용

또한 C++의 기능과 효율성을 .NET 프로그래밍과 결합할 수 있습니다. C#에서 사용자 인터페이스를 만들고 C++/CLI를 사용하여 응용 프로그램에서 네이티브 C++ 라이브러리를 사용할 수 있습니다. 자세한 내용은 [/cli를 C++사용한 .net 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)을 참조 하세요.

## <a name="com-components"></a>COM 구성 요소

[COM (구성 요소 개체 모델)](/windows/win32/com/the-component-object-model) 은 서로 다른 언어로 작성 된 프로그램이 서로 통신할 수 있도록 하는 사양입니다. 많은 Windows 구성 요소가 COM 개체로 구현되며 개체 만들기, 인터페이스 검색 및 개체 소멸에 대한 표준 COM 규칙을 따릅니다.  C++ 데스크톱 응용 프로그램에서 COM 개체를 사용하는 것은 비교적 간단하지만 고유한 COM 개체를 작성하는 것에는 더 높은 수준의 지식이 필요합니다. [ATL (액티브 템플릿 라이브러리)](../atl/atl-com-desktop-components.md) 은 COM 개발을 간소화 하는 매크로 및 도우미 함수를 제공 합니다. 자세한 내용은 [ATL COM 데스크톱 구성 요소](../atl/atl-com-desktop-components.md)를 참조 하세요.

## <a name="universal-windows-platform-apps"></a>유니버설 Windows 플랫폼 앱

유니버설 Windows 플랫폼(UWP)은 최신 Windows API입니다. UWP 응용 프로그램은 Windows 10이 설치된 장치라면 모두 실행 가능하며 사용자 인터페이스에 XAML을 사용하고, 터치 동작을 완전하게 지원합니다. UWP에 대 한 자세한 내용은 [uwp (유니버설 Windows 플랫폼) 앱 이란?](/windows/uwp/get-started/whats-a-uwp) 및 [Windows 유니버설 앱에](/windows/uwp/get-started/universal-application-platform-guide)대 한 가이드를 참조 하세요.

UWP에 C++ 대 한 원래 지원은 (1) C++/cx, 구문 확장이 C++ 포함 된 언어 또는 (2) 표준 C++ 및 COM을 기반으로 하는 WRL (Windows 런타임 라이브러리)로 구성 되었습니다. C++/CX와 WRL은 계속 사용할 수 있지만, 새 프로젝트의 경우 표준을 C++ 기반으로 하 고 더 빠른 성능을 제공 하는 [ C++/winrt](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)를 사용 하는 것이 좋습니다.

## <a name="desktop-bridge"></a>데스크톱 브리지

Windows 10에서는 기존 데스크톱 응용 프로그램 또는 COM 개체를 UWP 앱으로 패키지하고, 터치와 같은 UWP 기능을 추가하거나, 최신 Windows API 집합에서 API를 호출할 수 있습니다. 또한 Visual Studio의 데스크톱 솔루션에 UWP 응용 프로그램을 추가하고 단일 패키지로 함께 패키지화하고 Windows API를 사용하여 UWP 응용 프로그램 간 통신이 가능합니다.

Visual Studio 2017 버전 15.4 이상에서는 기존 데스크톱 응용 프로그램을 패키지하는 작업을 크게 간소화할 수 있도록 Windows 응용 프로그램 패키지 프로젝트를 만들 수 있습니다. 데스크톱 응용 프로그램에서 사용할 수 있는 레지스트리 호출 또는 API에는 몇 가지 제한 사항이 적용됩니다. 그러나 대부분의 경우 응용 프로그램 패키지에서 실행되는 동안 유사한 기능을 얻기 위해 대체 코드 경로를 만들 수 있습니다. 자세한 내용은 [데스크톱 브리지](/windows/uwp/porting/desktop-to-uwp-root)를 참조하세요.

## <a name="games"></a>게임

DirectX 게임은 PC 또는 Xbox에서 실행할 수 있습니다. 자세한 내용은 [DirectX Graphics And 게이밍](/windows/win32/directx)를 참조 하세요.

## <a name="sql-server-database-clients"></a>SQL Server 데이터베이스 클라이언트

네이티브 코드에서 SQL Server 데이터베이스에 액세스하려면 ODBC 또는 OLE DB를 사용합니다. 자세한 내용은 [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc)를 참조하세요.

## <a name="windows-device-drivers"></a>Windows 장치 드라이버

드라이버는 응용 프로그램 및 기타 운영 체제 구성 요소가 액세스할 수 있는 하드웨어 장치의 데이터를 만드는 하위 수준의 구성 요소입니다. 자세한 내용은 [WDK (Windows 드라이버 키트)](/windows-hardware/drivers/index)를 참조 하세요.

## <a name="windows-services"></a>Windows 서비스

Windows *서비스* 는 사용자 조작이 거의 없이 백그라운드에서 실행할 수 있는 프로그램입니다. 이러한 프로그램을 UNIX 시스템의 *디먼* 이라고 합니다. 자세한 내용은 [서비스](/windows/win32/services/services)를 참조 하세요.

## <a name="sdks-libraries-and-header-files"></a>SDK, 라이브러리 및 헤더 파일

Visual Studio에는 C 런타임 라이브러리(CRT), C++ 표준 라이브러리 및 기타 Microsoft 전용 라이브러리가 포함되어 있습니다. 이러한 라이브러리에 대한 헤더 파일을 포함하는 대부분의 포함 폴더는 Visual Studio 설치 디렉터리의 \VC\ 폴더에 있습니다. Windows 및 CRT 헤더 파일은 Windows SDK 설치 폴더에 있습니다.

[Vcpkg 패키지 관리자](../build/vcpkg.md) 를 사용 하면 Windows 용 수백 개의 타사 오픈 소스 라이브러리를 편리 하 게 설치할 수 있습니다.

Microsoft 라이브러리에는 다음이 포함됩니다.

- MFC(Microsoft Foundation Class): 단추, 목록 상자, 트리 뷰 및 기타 컨트롤이 있는 풍부한 사용자 인터페이스를 갖춘 전통적인 Windows 프로그램(특히 엔터프라이즈 응용 프로그램)을 만들기 위한 개체 지향 프레임워크입니다. 자세한 내용은 [MFC Desktop Applications](../mfc/mfc-desktop-applications.md)을 참조하세요.

- ATL(Active Template Library): COM 구성 요소를 만들기 위한 강력한 도우미 라이브러리입니다. 자세한 내용은 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)을 참조하세요.

- C++ AMP(C++ Accelerated Massive Parallelism): GPU를 고성능 일반 계산 작업에 사용할 수 있는 라이브러리입니다. 자세한 내용은 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)을 참조하세요.

- 동시성 런타임(Concurrency Runtime): 멀티 코어 및 많은 코어 장치에 대한 병렬 및 비동기 프로그래밍 작업을 간소화하는 라이브러리입니다. 자세한 내용은 [동시성 런타임](../parallel/concrt/concurrency-runtime.md)을 참조하세요.

많은 Windows 프로그래밍 시나리오에는 Windows 운영 체제 구성 요소에 액세스할 수 있는 헤더 파일을 포함하는 Windows SDK도 필요합니다. 기본적으로 Visual Studio는 유니버설 Windows 앱을 개발할 수 있도록 하는 C++ 데스크톱 워크로드의 구성 요소로 Windows SDK를 설치합니다. UWP 앱을 개발하려면 Windows 10 버전의 Windows SDK가 필요합니다. 자세한 내용은 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)를 참조 하세요. 이전 버전의 Windows 용 Windows Sdk에 대 한 자세한 내용은 [Windows SDK 보관](https://developer.microsoft.com/windows/downloads/sdk-archive))을 참조 하세요.

**Program Files (x86) \windows** kit는 설치한 모든 버전의 Windows SDK에 대 한 기본 위치입니다.

Xbox, Azure 등 다른 플랫폼은 설치가 필요한 고유의 SDK가 있습니다. 자세한 내용은 DirectX 개발자 센터 및 Azure 개발자 센터를 참조하세요.

## <a name="development-tools"></a>개발 도구

Visual Studio는 네이티브 코드에 대한 강력한 디버거, 정적 분석 도구, 그래픽 디버깅 도구, 완벽한 기능을 갖춘 코드 편집기, 유닛 테스트 지원 및 다른 많은 도구와 유틸리티를 포함합니다. 자세한 내용은 [Visual studio를 사용 하 여 개발 시작](/visualstudio/ide/get-started-developing-with-visual-studio)및 [visual Studio C++ 의 개발 개요](../overview/overview-of-cpp-development.md)를 참조 하세요.

## <a name="in-this-section"></a>섹션 내용
|제목|설명|
|-----------|-----------------|
|[연습: 표준 C++ 프로그램 만들기](walkthrough-creating-a-standard-cpp-program-cpp.md)| Windows 콘솔 응용 프로그램을 만듭니다.|
|[연습: Windows 데스크톱 애플리케이션 만들기(C++)](walkthrough-creating-windows-desktop-applications-cpp.md)|네이티브 Windows 데스크톱 응용 프로그램을 만듭니다.|
|[Windows 데스크톱 마법사](windows-desktop-wizard.md)|마법사를 사용하여 새 Windows 프로젝트를 만듭니다.|
|[ATL(액티브 템플릿 라이브러리)](../atl/atl-com-desktop-components.md)|C++에서 COM 구성 요소를 만들려면 ATL 라이브러리를 사용합니다.|
|[MFC(Microsoft Foundation Class)](../mfc/mfc-desktop-applications.md)|MFC를 사용하여 대화상자 및 컨트롤이 포함된 크고 작은 Windows 응용 프로그램을 만드는 방법입니다.|
|[ATL 및 MFC 공유 클래스](../atl-mfc-shared/atl-mfc-shared-classes.md)|CString 같은 ATL 및 MFC에서 공유하는 클래스를 사용합니다.|
|[데이터 액세스](../data/data-access-in-cpp.md)| OLE DB 및 ODBC|
|[텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)|Windows의 다양 한 문자열 형식입니다.|
|[DirectX를 사용하여 게임을 만들기 위한 리소스](resources-for-creating-a-game-using-directx.md)
|[방법: Windows 데스크톱 애플리케이션에서 Windows 10 SDK 사용](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows SDK|
|[리소스 파일 작업](working-with-resource-files.md)|데스크톱 응용 프로그램에 이미지, 아이콘, 문자열 테이블 및 기타 리소스를 추가 하는 방법입니다.|
|[DirectX를 사용 하 여 게임을 만들기C++위한 리소스 ()](resources-for-creating-a-game-using-directx.md)|에서 C++게임을 만들기 위한 콘텐츠에 대 한 링크입니다.|
|[방법: Windows 데스크톱 애플리케이션에서 Windows 10 SDK 사용](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK를 사용하여 빌드할 프로젝트를 설정하는 단계를 설명합니다.|
|[네이티브 데스크톱 애플리케이션 배포](deploying-native-desktop-applications-visual-cpp.md)|Windows에서 네이티브 응용 프로그램을 배포 합니다.|

## <a name="related-articles"></a>관련 문서

|제목|설명|
|-----------|-----------------|
|[Visual Studio의 C++](../overview/visual-cpp-in-visual-studio.md)|Visual C++ 개발자 콘텐츠에 대한 부모 항목입니다.|
[C++/CLI를 사용한 .NET 개발](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|.NET 응용 프로그램 및 구성 요소와의 상호 운용이 가능하도록 네이티브 C++ 라이브러리의 래퍼를 만듭니다.|
|[.NET 및 UWP용 구성 요소 확장](../extensions/component-extensions-for-runtime-platforms.md)|C++/CX 및 C++/CLI에서 공유하는 구문요소에 대한 참조입니다.|
|[유니버설 Windows 앱(C++)](../cppcx/universal-windows-apps-cpp.md)|C++/CX 또는 Windows 런타임 템플릿 라이브러리(WRL)를 이용한 UWP 응용 프로그램 개발하기.|
|[COM 및 .NET에 대한 C++ 특성](attributes/cpp-attributes-com-net.md)|.NET 또는 COM을 사용할 때의 Windows 전용 프로그래밍용 비표준 특성|
