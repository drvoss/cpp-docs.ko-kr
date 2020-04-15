---
title: Visual Studio의 CMake 프로젝트
description: 비주얼 스튜디오에서 CMake를 사용하여 C++ 프로젝트를 만들고 빌드하는 방법
ms.date: 01/08/2020
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 49ba53eaa8ac075ab6d3b2a66f33160c5c3ec410
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329167"
---
# <a name="cmake-projects-in-visual-studio"></a>Visual Studio의 CMake 프로젝트

CMake는 여러 플랫폼에서 실행되는 빌드 프로세스를 정의하는 플랫폼 간 오픈 소스 도구입니다. 이 문서에서는 CMake에 익숙하다고 가정합니다. [CMake로 소프트웨어 빌드, 테스트 및 패키징](https://cmake.org/)에서 자세히 알아볼 수 있습니다.

> [!NOTE]
> CMake는 지난 몇 번의 릴리스에서 Visual Studio와 점점 더 통합되었습니다. 선호하는 버전의 Visual Studio에 대한 설명서를 보려면 **버전** 선택기 컨트롤을 사용합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker range="vs-2019"

Windows 구성 요소에 **대한 C ++ CMake 도구는** IntelliSense 및 브라우징의 목적을 위해 CMake 프로젝트 파일 (예 : *CMakeLists.txt)을*직접 사용하기 위해 [폴더 열기](open-folder-projects-cpp.md) 기능을 사용합니다. Ninja 및 Visual Studio 생성기 모두 지원됩니다. Visual Studio 생성기를 사용하는 경우 임시 프로젝트 파일을 생성하여 msbuild.exe에 전달합니다. 그러나 IntelliSense 또는 브라우징 목적으로 프로젝트가 로드되지 않습니다. 기존 CMake 캐시를 가져올 수도 있습니다.

## <a name="installation"></a>설치

**Windows용 C++ CMake 도구는** C++ 워크로드가 **있는 C++** 및 **Linux 개발과** 함께 데스크톱 개발의 일부로 설치됩니다. 자세한 내용은 [플랫폼 간 CMake 프로젝트를](../linux/cmake-linux-project.md)참조하십시오.

![C++ 데스크톱 워크로드의 CMake 구성 요소](media/cmake-install-2019.png)

자세한 내용은 [Visual Studio에서 C++ Linux 워크로드 설치](../linux/download-install-and-setup-the-linux-development-workload.md)를 참조하세요.

## <a name="ide-integration"></a>IDE 통합

**파일 > 열기 > 폴더를** 선택하여 *CMakeLists.txt* 파일이 포함된 폴더를 열면 다음과 같은 상황이 발생합니다.

- Visual Studio는 **CMake** 스크립트를 보고 편집하는 명령과 함께 **프로젝트** 메뉴에 CMake 항목을 추가합니다.

- **솔루션 탐색기**에서 폴더 구조와 파일이 표시됩니다.

- Visual Studio는 cmake.exe를 실행하고 기본(x64 디버그) 구성에 대해 CMake 캐시*파일(CMakeCache.txt)을*생성합니다. CMake 명령줄이 CMake의 추가 출력과 함께 **출력 창**에 표시됩니다.

- IntelliSense, 검색 정보, 리팩터링 등을 사용할 수 있도록 하기 위해 Visual Studio에서 백그라운드로 소스 파일을 인덱싱합니다. 작업하는 동안 Visual Studio에서 편집기와 디스크의 변경 내용을 모니터링하여 인덱스가 소스와 동기화되도록 유지합니다.

여러 CMake 프로젝트가 포함된 폴더를 열 수 있습니다. Visual Studio는 작업 공간의 모든 "루트" *CMakeLists.txt* 파일을 검색하고 구성합니다. CMake 작업(구성, 빌드, 디버그), C++ IntelliSense 및 브라우징은 작업 영역의 모든 CMake 프로젝트에서 사용할 수 있습니다.

![여러 루트가 있는 CMake 프로젝트](media/cmake-multiple-roots.png)

대상별로 논리적으로 구성된 프로젝트를 볼 수도 있습니다. **솔루션 탐색기** 도구 모음의 드롭다운 목록에서 **대상 보기**를 선택합니다.

![CMake 대상 보기 단추](media/cmake-targets-view.png)

**솔루션 탐색기** 상단의 **모든 파일 표시** 단추를 클릭하여 *아웃/빌드/구성\<>* 폴더의 모든 CMake 생성 출력을 확인합니다.

비주얼 스튜디오는 **CMakeSettings.json이라는**구성 파일을 사용합니다. 이 파일을 사용하면 여러 빌드 구성을 정의및 저장하고 IDE에서 편리하게 전환할 수 있습니다. *구성은* 지정된 빌드 유형과 관련된 설정을 캡슐화하는 Visual Studio 구문입니다. 이 설정은 Visual Studio에서 cmake.exe에 전달하는 기본 명령줄 옵션을 구성하는 데 사용됩니다. 여기에서 추가 CMake 옵션을 지정하고 원하는 추가 변수를 정의할 수도 있습니다. 모든 옵션은 CMake 캐시에 내부 또는 외부 변수로 기록됩니다. Visual Studio 2019에서 **CMake 설정 편집기는** 설정을 편집하는 편리한 방법을 제공합니다. 자세한 내용은 [CMake 설정 사용자 지정을](customize-cmake-settings.md)참조하십시오.

하나의 `intelliSenseMode` 설정은 CMake에 전달되지 않지만 Visual Studio에서만 사용됩니다.

CMake 프로젝트에서와 마찬가지로 각 프로젝트 폴더에서 **CMakeLists.txt** 파일을 사용합니다. 원본 파일을 지정하고, 라이브러리를 찾고, 컴파일러 및 링커 옵션을 설정하고, 다른 빌드 시스템 관련 정보를 지정할 수 있습니다.

디버그 시간에 실행 파일에 인수를 전달하려면 **launch.vs.json**이라는 다른 파일을 사용할 수 있습니다. 일부 시나리오에서는 Visual Studio에서 이러한 파일을 자동으로 생성합니다. 수동으로 편집하거나 직접 파일을 만들 수도 있습니다.

> [!NOTE]
> 다른 종류의 오픈 폴더 프로젝트의 경우 **CppProperties.json** 및 **tasks.vs.json**의 두 개의 추가 JSON 파일이 사용됩니다. 이 두 가지 모두 CMake 프로젝트와 관련이 없습니다.

## <a name="open-an-existing-cache"></a>기존 캐시 열기

기존 CMake 캐시*파일(CMakeCache.txt)을*열면 Visual Studio에서 캐시를 관리하고 트리를 빌드하지 않습니다. 사용자 지정 또는 기본 설정 도구는 CMake가 프로젝트를 구성하는 방법을 완벽하게 제어할 수 있습니다. Visual Studio에서 기존 캐시를 열려면 **파일 > 열기 > CMake를**선택합니다. 그런 다음 기존 *CMakeCache.txt* 파일로 이동합니다.

열려 있는 프로젝트에 기존 CMake 캐시를 추가할 수 있습니다. 새 구성을 추가하는 것과 동일한 방식으로 수행됩니다. 자세한 내용은 [Visual Studio에서 기존 캐시를 여는](https://devblogs.microsoft.com/cppblog/open-existing-cmake-caches-in-visual-studio/)블로그 게시물을 참조하십시오.

## <a name="building-cmake-projects"></a>CMake 프로젝트 빌드

CMake 프로젝트를 빌드하려면 다음과 같이 선택할 수 있습니다.

1. 일반 도구 모음에서 **구성 드롭다운을 찾습니다.** 기본적으로 "x64-디버그"가 표시될 수 있습니다. 기본 구성을 선택하고 **F5를**누르거나 도구 모음에서 **실행(녹색** 삼각형) 단추를 클릭합니다. Visual Studio 솔루션과 마찬가지로 프로젝트가 자동으로 먼저 빌드됩니다.

1. *CMakeLists.txt를* 마우스 오른쪽 버튼으로 클릭하고 컨텍스트 메뉴에서 **빌드를** 선택합니다. 폴더 구조에 여러 대상이 있는 경우 모든 대상 또는 특정 대상만 빌드하도록 선택할 수 있습니다.

1. 메인 메뉴에서 **빌드 > 모두** 빌드(F7 또는 **Ctrl+Shift+B)를**선택합니다.**F7** **일반** 도구 모음의 **시작 항목** 드롭다운에서 CMake 대상이 이미 선택되어 있는지 확인합니다.

![C만들기 빌드 메뉴 명령](media/cmake-build-menu.png "C만들기 빌드 명령 메뉴")

빌드 결과가 예상한 대로 **출력 창** 및 **오류 목록**에 표시됩니다.

![C만들기 빌드 오류](media/cmake-build-errors.png "C만들기 빌드 오류")

빌드 대상이 여러 개인 폴더에서 빌드할 CMake 대상을 **Build** 지정할 수 **CMake** 있습니다. *CMakeLists.txt* CMake 프로젝트에서 **Ctrl+Shift+B를** 입력하면 현재 활성 문서를 작성합니다.

## <a name="debugging-cmake-projects"></a>CMake 프로젝트 디버깅

CMake 프로젝트를 디버깅하려면 기본 구성을 선택하고 **F5를**누르거나 도구 모음에서 **실행** 버튼을 누릅니다. **실행** 버튼에 "시작 항목 선택"이라고 적혀 있는 경우 드롭다운 화살표를 선택합니다. 실행할 대상을 선택합니다. (CMake 프로젝트에서 "현재 문서" 옵션은 .cpp 파일에만 유효합니다.)

![C메이크 실행 버튼](media/cmake-run-button.png "C메이크 실행 버튼")

**실행** 또는 **F5** 명령은 이전 빌드 이후 변경된 경우 프로젝트를 먼저 빌드합니다. *CMakeSettings.json을* 변경하면 CMake 캐시가 다시 생성됩니다.

**launch.vs.json** 파일에서 속성을 설정하여 CMake 디버깅 세션을 사용자 지정할 수 있습니다. 자세한 내용은 [CMake 디버깅 세션 구성](configure-cmake-debugging-sessions.md)을 참조하세요.

## <a name="just-my-code-for-cmake-projects"></a>CMake 프로젝트에 대한 내 코드만

MSVC 컴파일러를 사용하여 Windows용으로 빌드할 때 CMake 프로젝트에는 내 코드 디버깅을 지원합니다. 내 코드 설정을 변경하려면 **도구** > **옵션** > **디버깅** > **일반으로**이동합니다.

## <a name="vcpkg-integration"></a>Vcpkg 통합

[vcpkg을](vcpkg.md)설치 한 경우 Visual Studio에서 열린 CMake 프로젝트는 vcpkg 도구 체인 파일을 자동으로 통합합니다. 즉, CMake 프로젝트에서 vcpkg을 사용하기 위해 추가 구성이 필요하지 않습니다. 이 지원은 타겟팅하는 원격 시스템의 로컬 vcpkg 설치 및 vcpkg 설치모두에 적용됩니다. CMake 설정 구성에서 다른 도구 체인을 지정하면 이 동작이 자동으로 비활성화됩니다.

## <a name="customize-configuration-feedback"></a>구성 피드백 사용자 지정

기본적으로 오류가 없는 한 대부분의 구성 메시지는 억제됩니다. **도구** > **옵션** > **CMake에서**이 기능을 사용하도록 설정하여 모든 메시지를 볼 수 있습니다.

   ![CMake 진단 옵션 구성](media/vs2019-cmake-configure-options.png "CMake 진단 옵션")

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt 파일 편집

*CMakeLists.txt* 파일을 편집하려면 **솔루션 탐색기에서** 파일을 마우스 오른쪽 단추로 클릭하고 **열기를**선택합니다. 파일을 변경하면 노란색 상태 표시줄이 나타나고 IntelliSense가 업데이트될 것임을 알려줍니다. 업데이트 작업을 취소할 수 있습니다. *CMakeLists.txt에*대한 자세한 내용은 [CMake 설명서를](https://cmake.org/documentation/)참조하십시오.

   ![CMakeLists.txt 파일 편집](media/cmake-cmakelists.png "CMakeLists.txt 파일 편집")

파일을 저장하는 즉시 구성 단계가 자동으로 다시 실행되고 **출력** 창에 정보가 표시됩니다. 오류와 경고가 **오류 목록** 또는 **출력** 창에 표시됩니다. **오류 목록에서** 오류를 두 번 클릭하여 *CMakeLists.txt의*잘못된 줄로 이동합니다.

   ![CMakeLists.txt 파일 오류](media/cmake-cmakelists-error.png "CMakeLists.txt 파일 오류")

## <a name="cmake-configure-step"></a>CMake 구성 단계

*CMakeSettings.json* 또는 *CMakeLists.txt* 파일을 크게 변경하면 Visual Studio에서 CMake 구성 단계를 자동으로 다시 실행합니다. 구성 단계가 오류 없이 완료되면 수집된 정보는 C++ IntelliSense 및 언어 서비스에서 사용할 수 있습니다. 빌드 및 디버그 작업에도 사용됩니다.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake 캐시 오류 문제 해결

문제를 진단하기 위해 CMake 캐시의 상태에 대한 자세한 정보가 필요한 경우 **프로젝트** 주 메뉴 또는 **솔루션 탐색기의** *CMakeLists.txt* 컨텍스트 메뉴를 열어 다음 명령 중 하나를 실행합니다.

- **뷰 캐시는** 편집기의 빌드 루트 폴더에서 *CMakeCache.txt* 파일을 엽니다. *(CMakeCache.txt에* 여기에서 편집한 모든 편집은 캐시를 청소하면 지워지게 됩니다. 캐시를 정리한 후 지속되는 변경 내용을 만들려면 [CMake 설정 사용자 지정을](customize-cmake-settings.md)참조하십시오.)

- **캐시 폴더 열기**는 빌드 루트 폴더에 대한 탐색기 창을 엽니다.

- **캐시 정리**는 다음 CMake 구성 단계를 정리된 캐시에서 시작하도록 빌드 루트 폴더를 삭제합니다.

- **캐시 생성은** Visual Studio에서 환경을 최신 상태로 간주하는 경우에도 생성 단계를 실행하도록 강제합니다.

CMake 일반 대화 상자에서 도구 > 옵션 > 자동 캐시 생성을 **비활성화할 수 >** 있습니다.

## <a name="run-cmake-from-the-command-line"></a>명령줄에서 CMake 실행

Visual Studio 설치 관리자에서 CMake를 설치한 경우 다음 단계에 따라 명령줄에서 이를 실행할 수 있습니다.

1. 해당하는 vsdevcmd.bat(x86/x64)를 실행합니다. 자세한 내용은 [명령줄에서 건물 을](building-on-the-command-line.md)참조하십시오.

1. 출력 폴더로 전환합니다.

1. CMake를 실행하여 앱을 빌드/구성합니다.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017은 크로스 플랫폼 [CMake 프로젝트를 포함하여 CMake에](../linux/cmake-linux-project.md)대한 풍부한 지원을 제공합니다. CMake 구성 요소에 **대한 Visual C++ 도구는** **열기 폴더** 기능을 사용하여 IDE가 IntelliSense 및 브라우징을 위해 CMake 프로젝트 파일(예: *CMakeLists.txt)을*직접 사용할 수 있도록 합니다. Ninja 및 Visual Studio 생성기 모두 지원됩니다. Visual Studio 생성기를 사용하는 경우 임시 프로젝트 파일을 생성하여 msbuild.exe에 전달합니다. 그러나 IntelliSense 또는 브라우징 목적으로 프로젝트가 로드되지 않습니다. 기존 CMake 캐시를 가져올 수도 있습니다.

## <a name="installation"></a>설치

**CMake용 Visual C++ 도구는** C++ 워크로드가 **있는 C++** 및 **Linux 개발과** 함께 데스크톱 개발의 일부로 설치됩니다.

![C++ 데스크톱 워크로드의 CMake 구성 요소](media/cmake-install.png)

자세한 내용은 [Visual Studio에서 C++ Linux 워크로드 설치](../linux/download-install-and-setup-the-linux-development-workload.md)를 참조하세요.

## <a name="ide-integration"></a>IDE 통합

**파일 > 열기 > 폴더를** 선택하여 *CMakeLists.txt* 파일이 포함된 폴더를 열면 다음과 같은 상황이 발생합니다.

- Visual Studio에서 CMake 스크립트를 보고 편집하는 명령이 있는 **CMake** 메뉴 항목이 주 메뉴에 추가됩니다.

- **솔루션 탐색기**에서 폴더 구조와 파일이 표시됩니다.

- Visual Studio에서 CMake.exe를 실행하고 선택적으로 x86 디버그인 기본 *구성*에 대한 CMake 캐시를 생성합니다. CMake 명령줄이 CMake의 추가 출력과 함께 **출력 창**에 표시됩니다.

- IntelliSense, 검색 정보, 리팩터링 등을 사용할 수 있도록 하기 위해 Visual Studio에서 백그라운드로 소스 파일을 인덱싱합니다. 작업하는 동안 Visual Studio에서 편집기와 디스크의 변경 내용을 모니터링하여 인덱스가 소스와 동기화되도록 유지합니다.

여러 CMake 프로젝트가 포함된 폴더를 열 수 있습니다. Visual Studio는 작업 공간의 모든 "루트" *CMakeLists.txt* 파일을 검색하고 구성합니다. CMake 작업(구성, 빌드, 디버그), C++ IntelliSense 및 브라우징은 작업 영역의 모든 CMake 프로젝트에서 사용할 수 있습니다.

![여러 루트가 있는 CMake 프로젝트](media/cmake-multiple-roots.png)

대상별로 논리적으로 구성된 프로젝트를 볼 수도 있습니다. **솔루션 탐색기** 도구 모음의 드롭다운 목록에서 **대상 보기**를 선택합니다.

![CMake 대상 보기 단추](media/cmake-targets-view.png)

Visual Studio는 *CMakeSettings.json이라는* 파일을 사용하여 Cmake.exe에 대한 환경 변수 또는 명령줄 옵션을 저장합니다. *또한 CMakeSettings.json을* 사용하면 여러 CMake 빌드 구성을 정의하고 저장할 수 있습니다. IDE에서 편리하게 전환할 수 있습니다.

그렇지 않으면 CMake 프로젝트에서와 마찬가지로 *CMakeLists.txt를* 사용하여 원본 파일을 지정하고, 라이브러리를 찾고, 컴파일러 및 링커 옵션을 설정하고, 다른 빌드 시스템 관련 정보를 지정합니다.

디버그 시간에 실행 파일에 인수를 전달해야 하는 경우 **launch.vs.json**이라는 다른 파일을 사용할 수 있습니다. 일부 시나리오에서는 Visual Studio에서 이러한 파일을 자동으로 생성합니다. 수동으로 편집하거나 직접 파일을 만들 수도 있습니다.

> [!NOTE]
> 다른 종류의 오픈 폴더 프로젝트의 경우 **CppProperties.json** 및 **tasks.vs.json**의 두 개의 추가 JSON 파일이 사용됩니다. 이 두 가지 모두 CMake 프로젝트와 관련이 없습니다.

## <a name="import-an-existing-cache"></a>기존 캐시 가져오기

기존 *CMakeCache.txt* 파일을 가져올 때 Visual Studio는 사용자 지정된 변수를 자동으로 추출하고 이를 기반으로 미리 채워진 *CMakeSettings.json* 파일을 만듭니다. 원래 캐시는 어떤 방식으로도 수정되지 않습니다. 명령줄에서 또는 이를 생성하는 데 사용되는 도구 나 IDE와 함께 계속 사용할 수 있습니다. 새로운 *CMakeSettings.json* 파일은 프로젝트의 루트 *CMakeLists.txt와*함께 배치됩니다. Visual Studio에서는 설정 파일을 기반으로 하여 새 캐시를 생성합니다. **CMake 일반** 대화 상자에서 도구 > 옵션 > 자동 캐시 생성을 재정의할 수 > 있습니다.

캐시의 모든 항목을 가져오지는 않습니다.  생성기 및 컴파일러 위치와 같은 속성은 IDE에서 제대로 작동하는 것으로 알려진 기본값으로 대체됩니다.

### <a name="to-import-an-existing-cache"></a>기존 캐시를 가져오려면

1. 메인 메뉴에서 **파일 > 열기 > CMake를**선택합니다.

   ![오픈 CMake](media/cmake-file-open.png "파일, 열기, CMake")

   이 명령은 **캐시에서 CMake 가져오기 마법사를** 가져옵니다.

2. 가져올 *CMakeCache.txt* 파일로 이동한 다음 **확인을**클릭합니다. **캐시에서 CMake 프로젝트 가져오기** 마법사가 표시됩니다.

   ![CMake 캐시 가져오기](media/cmake-import-wizard.png "CMake 가져오기 캐시 마법사 열기")

   마법사가 완료되면 프로젝트의 루트 CMakeLists.txt 파일 옆에 **있는 솔루션 탐색기에서** 새 *CMakeCache.txt* 파일을 볼 수 있습니다. *CMakeLists.txt*

## <a name="building-cmake-projects"></a>CMake 프로젝트 빌드

CMake 프로젝트를 빌드하려면 다음과 같이 선택할 수 있습니다.

1. 일반 도구 모음에서 **구성 드롭다운을 찾습니다.** 그것은 아마 기본적으로 "리눅스 디버그" 또는 "x64-디버그"를 보여주는. 기본 구성을 선택하고 **F5를**누르거나 도구 모음에서 **실행(녹색** 삼각형) 단추를 클릭합니다. Visual Studio 솔루션과 마찬가지로 프로젝트가 자동으로 먼저 빌드됩니다.

1. *CMakeLists.txt를* 마우스 오른쪽 버튼으로 클릭하고 컨텍스트 메뉴에서 **빌드를** 선택합니다. 폴더 구조에 여러 대상이 있는 경우 모든 대상 또는 특정 대상만 빌드하도록 선택할 수 있습니다.

1. 주 메뉴에서 빌드 솔루션**빌드(F7** 또는 **Ctrl+Shift+B)>** 선택합니다. **Build > Build Solution** **일반** 도구 모음의 **시작 항목** 드롭다운에서 CMake 대상이 이미 선택되어 있는지 확인합니다.

![C만들기 빌드 메뉴 명령](media/cmake-build-menu.png "C만들기 빌드 명령 메뉴")

*CMakeSettings.json* 파일에서 빌드 구성, 환경 변수, 명령줄 인수 및 기타 설정을 사용자 지정할 수 있습니다. *CMakeLists.txt* 파일을 수정하지 않고도 변경할 수 있습니다. 자세한 내용은 [CMake 설정 사용자 지정을](customize-cmake-settings.md)참조하십시오.

빌드 결과가 예상한 대로 **출력 창** 및 **오류 목록**에 표시됩니다.

![C만들기 빌드 오류](media/cmake-build-errors.png "C만들기 빌드 오류")

빌드 대상이 여러 개인 폴더에서 빌드할 CMake 대상을 **Build** 지정할 수 **CMake** 있습니다. *CMakeLists.txt* CMake 프로젝트에서 **Ctrl+Shift+B를** 입력하면 현재 활성 문서를 작성합니다.

## <a name="debugging-cmake-projects"></a>CMake 프로젝트 디버깅

CMake 프로젝트를 디버깅하려면 기본 구성을 선택하고 **F5를**누릅니다. 또는 도구 모음에서 **실행** 버튼을 누릅니다. **실행** 단추에서 "시작 항목 선택"이라고 표시되면 드롭다운 화살표를 선택하고 실행할 대상을 선택합니다. (CMake 프로젝트에서 "현재 문서" 옵션은 .cpp 파일에만 유효합니다.)

![C메이크 실행 버튼](media/cmake-run-button.png "C메이크 실행 버튼")

**실행** 또는 **F5** 명령은 이전 빌드 이후 변경된 경우 프로젝트를 먼저 빌드합니다.

**launch.vs.json** 파일에서 속성을 설정하여 CMake 디버깅 세션을 사용자 지정할 수 있습니다. 자세한 내용은 [CMake 디버깅 세션 구성](configure-cmake-debugging-sessions.md)을 참조하세요.

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt 파일 편집

*CMakeLists.txt* 파일을 편집하려면 **솔루션 탐색기에서** 파일을 마우스 오른쪽 단추로 클릭하고 **열기를**선택합니다. 파일을 변경하면 노란색 상태 표시줄이 나타나고 IntelliSense가 업데이트될 것임을 알려줍니다. 업데이트 작업을 취소할 수 있습니다. *CMakeLists.txt에*대한 자세한 내용은 [CMake 설명서를](https://cmake.org/documentation/)참조하십시오.

   ![CMakeLists.txt 파일 편집](media/cmake-cmakelists.png "CMakeLists.txt 파일 편집")

파일을 저장하는 즉시 구성 단계가 자동으로 다시 실행되고 **출력** 창에 정보가 표시됩니다. 오류와 경고가 **오류 목록** 또는 **출력** 창에 표시됩니다. **오류 목록에서** 오류를 두 번 클릭하여 *CMakeLists.txt의*잘못된 줄로 이동합니다.

   ![CMakeLists.txt 파일 오류](media/cmake-cmakelists-error.png "CMakeLists.txt 파일 오류")

## <a name="cmake-configure-step"></a>CMake 구성 단계

*CMakeSettings.json* 또는 *CMakeLists.txt* 파일에 중요한 변경 사항이 있으면 Visual Studio에서 CMake 구성 단계를 자동으로 다시 실행합니다. 구성 단계가 오류 없이 완료되면 수집된 정보는 C++ IntelliSense 및 언어 서비스에서 사용할 수 있습니다. 빌드 및 디버그 작업에도 사용됩니다.

여러 CMake 프로젝트는 동일한 CMake 구성 이름(예: x86-디버그)을 사용할 수 있습니다. 구성을 선택하면 모두 구성되고 빌드됩니다(자체 빌드 루트 폴더). 해당 CMake 구성에 참여하는 모든 CMake 프로젝트에서 대상을 디버그할 수 있습니다.

   ![C만들기 빌드 전용 메뉴 항목](media/cmake-build-only.png "C만들기 빌드 전용 메뉴 항목")

빌드 및 디버그 세션을 작업 영역의 프로젝트 하위 집합으로 제한할 수 있습니다. *CMakeSettings.json* 파일에 고유한 이름으로 새 구성을 만듭니다. 그런 다음 해당 프로젝트에만 구성을 적용합니다. 해당 구성을 선택하면 IntelliSense 및 빌드 및 디버그 명령은 지정된 프로젝트에만 적용됩니다.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake 캐시 오류 문제 해결

문제를 진단하는 데 CMake 캐시의 상태에 대한 추가 정보가 필요하면, **CMake** 주 메뉴 또는 **솔루션 탐색기**의 상황에 맞는 *CMakeLists.txt* 메뉴를 열어 다음 명령 중 하나를 실행합니다.

- **뷰 캐시는** 편집기의 빌드 루트 폴더에서 *CMakeCache.txt* 파일을 엽니다. *(CMakeCache.txt에* 여기에서 편집한 모든 편집은 캐시를 청소하면 지워지게 됩니다. 캐시를 정리한 후 지속되는 변경 내용을 만들려면 [CMake 설정 사용자 지정을](customize-cmake-settings.md)참조하십시오.)

- **캐시 폴더 열기**는 빌드 루트 폴더에 대한 탐색기 창을 엽니다.

- **캐시 정리**는 다음 CMake 구성 단계를 정리된 캐시에서 시작하도록 빌드 루트 폴더를 삭제합니다.

- **캐시 생성은** Visual Studio에서 환경을 최신 상태로 간주하는 경우에도 생성 단계를 실행하도록 강제합니다.

CMake 일반 대화 상자에서 도구 > 옵션 > 자동 캐시 생성을 **비활성화할 수 >** 있습니다.

## <a name="single-file-compilation"></a>단일 파일 컴파일

CMake 프로젝트에서 단일 파일을 작성하려면 **솔루션 탐색기**에서 파일을 마우스 오른쪽 단추로 클릭합니다. 팝업 메뉴에서 **컴파일을** 선택합니다. 기본 **CMake** 메뉴를 사용하여 편집기에서 현재 열려 있는 파일을 빌드할 수도 있습니다.

![CMake 단일 파일 컴파일](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>명령줄에서 CMake 실행

Visual Studio 설치 관리자에서 CMake를 설치한 경우 다음 단계에 따라 명령줄에서 이를 실행할 수 있습니다.

1. 해당하는 vsdevcmd.bat(x86/x64)를 실행합니다. 자세한 내용은 [명령줄에서 건물 을](building-on-the-command-line.md) 참조하십시오.

1. 출력 폴더로 전환합니다.

1. CMake를 실행하여 앱을 빌드/구성합니다.

::: moniker-end

::: moniker range="vs-2015"

Visual Studio 2015에서 Visual Studio 사용자는 [CMake 생성기](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html)를 사용하여 MSBuild 프로젝트 파일을 생성합니다. 그러면 IDE에서는 IntelliSense, 검색 및 컴파일에 사용합니다.

::: moniker-end

## <a name="see-also"></a>참고 항목

[자습서: Visual Studio에서 C++ 크로스 플랫폼 프로젝트 만들기](get-started-linux-cmake.md)\
[Linux CMake 프로젝트 구성](../linux/cmake-linux-project.md)\
[원격 리눅스 컴퓨터에 연결](../linux/connect-to-your-remote-linux-computer.md)\
[CMake 빌드 설정 사용자 지정](customize-cmake-settings.md)\
[CMakeSettings.json 스키마 참조](cmakesettings-reference.md)\
[CMake 디버깅 세션 구성](configure-cmake-debugging-sessions.md)\
[Linux 프로젝트를 배포, 실행 및 디버깅](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake 미리 정의된 구성 참조](cmake-predefined-configuration-reference.md)
