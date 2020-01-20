---
title: Visual Studio에 C++ 지원 설치
description: Visual Studio에 대한 visual Studio 지원 설치C++
ms.custom: mvc
ms.date: 04/02/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: a20a2432cbf8c4dc5f211f6f483c0084888f1199
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857166"
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio에 C++ 지원 설치

Visual Studio 및 시각적 C++ 도구를 아직 다운로드하여 설치 하지 않은 경우 시작 하는 방법은 다음과 같습니다.

::: moniker range="vs-2019"

## <a name="visual-studio-2019-installation"></a>Visual Studio 2019 설치

Visual Studio 2019를 시작합니다. 이 버전에서는 필요한 기능만 선택하여 쉽게 설치할 수 있습니다. 또한 최소 설치 공간이 줄어들기 때문에 시스템에 미치는 영향을 최소화하면서 빠르게 설치됩니다.

> [!NOTE]
> 이 항목은 Windows에서 Visual Studio를 설치 하는 경우에 적용 됩니다. [Visual Studio Code](https://code.visualstudio.com/) 는 Windows, Mac 및 Linux 시스템에서 실행 되는 경량 플랫폼 간 개발 환경입니다. Microsoft [C/C++ for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) 확장 프로그램은 IntelliSense, 디버깅, 코드 서식 지정, 자동 완성 기능을 지원 합니다. Mac용 Visual Studio는 Microsoft C++를 지원 하지 않지만 .NET 언어 및 플랫폼 간 개발을 지원 합니다. 설치 지침은 [Mac용 Visual Studio 설치](/visualstudio/mac/installation/)를 참조 하세요.

이 버전의 다른 새로운 기능에 대해 자세히 알고 싶으세요? Visual Studio [릴리스 정보](/visualstudio/releases/2019/release-notes/)를 참조 하세요.

설치할 준비가 되었나요? 설치 과정을 단계별로 안내합니다.

### <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>1단계 - Visual Studio에 대해 컴퓨터가 준비되었는지 확인

Visual Studio 설치를 시작하기 전에

1. [시스템 요구 사항](/visualstudio/releases/2019/system-requirements)을 확인합니다. 이러한 요구 사항은 컴퓨터에서 Visual Studio 2019를 지원하는지 여부를 확인하는 데 도움이 됩니다.

1. 최신 Windows 업데이트를 적용합니다. 이러한 업데이트는 컴퓨터에 최신 보안 업데이트와 Visual Studio에 필요한 시스템 구성 요소가 모두 설치되어 있는지 확인합니다.

1. 다시 부팅합니다. 다시 부팅하면 보류 중인 설치 또는 업데이트가 Visual Studio 설치를 방해하지 않습니다.

1. 공간을 확보합니다. 예를 들어 디스크 정리 앱을 실행하여 %SystemDrive%에서 불필요한 파일 및 애플리케이션을 제거합니다.

Visual Studio 2019와 함께 이전 버전의 Visual Studio를 실행하는 방법에 대한 의문 사항은 [Visual Studio 2019 플랫폼 대상 지정 및 호환성](/visualstudio/releases/2019/compatibility/) 페이지를 참조하세요.

### <a name="step-2---download-visual-studio"></a>2단계 - Visual Studio 다운로드

다음으로 Visual Studio 부트스트래퍼 파일을 다운로드합니다. 이렇게 하려면 다음 단추를 선택하고, 원하는 Visual Studio 버전을 선택하고, **저장**을 선택한 다음, **폴더 열기**를 선택합니다.

 > [!div class="button"]
 > [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+rc)

### <a name="step-3---install-the-visual-studio-installer"></a>3단계 - Visual Studio 설치 관리자 설치

Visual Studio 설치 관리자를 설치하려면 부트스트래퍼 파일을 실행합니다. 이 새 경량 설치 관리자는 Visual Studio를 설치하고 사용자 지정하는 데 필요한 모든 항목을 포함합니다.

1. **다운로드** 폴더에서 다음 파일 중 하나와 일치하거나 비슷한 부트스트래퍼 파일을 두 번 클릭합니다.

   * Visual Studio Community용 **vs_community.exe**
   * Visual Studio Professional용 **vs_professional.exe**
   * Visual Studio Enterprise용 **vs_enterprise.exe**

   사용자 계정 컨트롤 알림을 받으면 **예**를 선택합니다.

1. Microsoft [사용 약관](https://visualstudio.microsoft.com/license-terms/) 및 Microsoft [개인정보처리방침](https://privacy.microsoft.com/privacystatement)에 동의하도록 요청하는 메시지가 표시됩니다. **계속**을 선택합니다.

### <a name="step-4---choose-workloads"></a>4단계 - 워크로드 선택

설치 관리자를 설치한 후에는 이를 사용하여 원하는 *작업* 또는 기능 집합을 선택하여 설치를 사용자 지정할 수 있습니다. 방법은 다음과 같습니다.

1. **Visual Studio 설치** 화면에서 원하는 작업을 찾습니다.

   ![Visual Studio 2019: 워크 로드 설치](../get-started/media/vs-installer-workloads.png)

   핵심 C++ 지원을 위해 "워크 로드를 사용한 C++데스크톱 개발"을 선택 합니다. 20개가 넘는 언어에 대한 기본 코드 편집 기능, 프로젝트 없이도 폴더에서 코드를 열어 편집할 수 있는 기능 및 통합 소스 코드 제어 기능이 포함된 기본 핵심 편집기가 제공됩니다.

   추가 작업은 다른 종류의 C++ 개발을 지원 합니다. 예를 들어 "유니버설 Windows 플랫폼 개발" 워크 로드를 선택하여 Microsoft Store에 Windows 런타임를 사용 하는 앱을 만듭니다. DirectX, Unreal 및 C++Cocos2d를 사용 하는 게임을 만들려면 "게임 개발"을 선택 합니다. IoT 개발을 포함 하 C++여 linux 플랫폼을 대상으로 하는 "linux 개발"을 선택 합니다.

   **설치 세부 정보** 창에는 각 워크 로드에 의해 설치 된 포함 된 선택적 구성 요소가 나열 됩니다. 이 목록에서 선택적 구성 요소를 선택 하거나 선택 취소할 수 있습니다. 예를 들어 Visual Studio 2017 또는 2015 컴파일러 도구 집합을 사용하여 개발을 지원 하려면 MSVC v141 또는 MSVC v140 선택적 구성 요소를 선택 합니다. MFC, 실험적 모듈 언어 확장, IncrediBuild 등에 대한 지원을 추가할 수 있습니다.

1. 원하는 작업 및 선택적 구성 요소를 선택한 후 **설치**를 선택 합니다.

    다음으로 Visual Studio 설치 진행률을 보여 주는 상태 화면이 나타납니다.

> [!TIP]
> 설치 후에 언제든지 초기에 설치하지 않은 워크로드 또는 구성 요소를 설치할 수 있습니다. Visual Studio가 열려 있으면 **도구** > **도구 및 기능 가져오기...** 로 이동하여 Visual Studio 설치 관리자를 엽니다. 또는 [시작] 메뉴에서 **Visual Studio 설치 관리자**를 엽니다. 여기에서 설치할 워크로드 또는 구성 요소를 선택합니다. 그런 다음, **수정**을 선택합니다.

### <a name="step-5---choose-individual-components-optional"></a>5단계 - 개별 구성 요소 선택(선택 사항)

워크 로드 기능을 사용하여 Visual Studio 설치를 사용자 지정 하지 않으려는 경우 또는 작업을 설치 하는 것 보다 더 많은 구성 요소를 추가 하려는 경우 **개별 구성** 요소 탭에서 개별 구성 요소를 설치 하거나 추가하여 수행할 수 있습니다. 원하는 항목을 선택하고 프롬프트를 따릅니다.

  ![Visual Studio 2019-개별 구성 요소 설치](../get-started/media/vs-installer-individual-components.png "Visual Studio 개별 구성 요소 설치")

### <a name="step-6---install-language-packs-optional"></a>6단계 - 언어 팩 설치(선택 사항)

기본적으로 설치 관리자 프로그램은 처음 실행될 때 운영 체제의 언어와 일치시키려고 합니다. 선택한 언어로 Visual Studio를 설치하려면 Visual Studio 설치 관리자에서 **언어 팩** 탭을 선택한 다음, 지시에 따릅니다.

  ![Visual Studio 2019-언어 팩 설치](../get-started/media/vs-installer-language-packs.png "Visual Studio 언어 팩 설치")

#### <a name="change-the-installer-language-from-the-command-line"></a>명령줄에서 설치 관리자 언어 변경

기본 언어를 변경할 수 있는 다른 방법은 명령줄에서 설치 관리자를 실행하는 것입니다. 예를 들어 `vs_installer.exe --locale en-US` 명령을 사용하여 설치 관리자를 영어로 강제 실행할 수 있습니다. 설치 관리자는 다음에 실행 될 때 이 설정을 기억할 것입니다. 설치 관리자는 zh-cn, zh-tw, cs-cz, en-us, es-es, fr-fr, de-de, it-it, ja-jp, ko-kr, pl-pl, pt-br, ru-ru, and tr-tr과 같은 언어 토큰을 지원합니다.

### <a name="step-7---change-the-installation-location-optional"></a>7단계 - 설치 위치 변경(선택 사항)

시스템 드라이브에서 Visual Studio의 설치 공간을 줄일 수 있습니다. 다운로드 캐시, 공유 구성 요소, SDK 및 도구를 다른 드라이브로 이동하고 Visual Studio를 가장 빠르게 실행되는 드라이브에 유지하도록 선택할 수 있습니다.

  ![Visual Studio 2019-설치 위치 변경](../get-started/media/vs-installer-installation-locations.png "설치 위치 변경")

> [!IMPORTANT]
> Visual Studio를 처음 설치할 때만 다른 드라이브를 선택할 수 있습니다. 이미 설치하고 드라이브를 변경하려면 Visual Studio를 제거한 다음, 다시 설치해야 합니다.

### <a name="step-8---start-developing"></a>8단계 - 개발 시작

1. Visual Studio 설치가 완료되면 **시작** 단추를 선택하여 Visual Studio에서 개발을 시작합니다.

1. 시작 창에서 **새 프로젝트 만들기**를 선택합니다.

1. 검색 상자에 생성할 앱 유형을 입력하여 사용 가능한 템플릿 목록을 확인합니다. 템플릿 목록은 설치 중에 선택한 워크로드에 따라 달라집니다. 다른 템플릿을 보려면 다른 워크로드를 선택합니다.

   **언어** 드롭다운 목록을 사용하여 특정 프로그래밍 언어 검색을 필터링할 수도 있습니다. **플랫폼** 목록 및 **프로젝트 형식** 목록을 사용하여 필터링할 수도 있습니다.

1. Visual Studio에서 새 프로젝트를 열면 코딩할 준비가 완료됩니다.

::: moniker-end

::: moniker range="<=vs-2017"

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 설치

Visual Studio 2017에서는 필요한 기능만 쉽게 선택하여 설치할 수 있습니다. 또한 최소 설치 공간이 줄어들기 때문에 시스템에 미치는 영향을 최소화하면서 빠르게 설치됩니다.

### <a name="prerequisites"></a>Prerequisites

- 광대역 인터넷 연결입니다. Visual Studio 설치 관리자는 몇 기가바이트의 데이터를 다운로드할 수 있습니다.

- Microsoft Windows 7 이상 버전을 실행하는 컴퓨터. 최상의 개발 환경을 위해서는 Windows 10이 권장됩니다. Visual Studio를 설치 하기 전에 최신 업데이트가 시스템에 적용 되었는지 확인 합니다.

- 사용 가능한 디스크 공간이 충분 합니다. Visual Studio에는 최소 7GB 이상의 디스크 공간이 필요 하며, 많은 일반 옵션을 설치한 경우 50 g b 이상이 걸릴 수 있습니다. C: 드라이브에 설치 하는 것이 좋습니다.

디스크 공간 및 운영 체제 요구 사항에 대한 자세한 내용은 [Visual Studio 제품군 시스템 요구 사항](/visualstudio/productinfo/vs2017-system-requirements-vs)을 참조 하세요. 설치 관리자는 선택한 옵션에 필요한 디스크 공간을 보고 합니다.

### <a name="download-and-install"></a>를 다운로드하여 설치합니다

1. 최신 Windows 용 Visual Studio 2017 설치 관리자를 다운로드 합니다.

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 Community 설치](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > 커뮤니티 에디션은 개인 개발자, 교실 학습, 학술 연구 및 오픈 소스 개발용입니다. 다른 용도의 경우 [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 또는 [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)를 설치합니다.

1. 다운로드 한 설치 관리자 파일을 찾아서 실행 합니다. 브라우저에 표시 되거나 다운로드 폴더에서 찾을 수 있습니다. 설치 관리자를 실행 하려면 관리자 권한이 필요 합니다. 설치 관리자가 시스템을 변경할 수 있는 권한을 부여 하도록 요청 하는 **사용자 계정 컨트롤** 대화 상자가 표시 될 수 있습니다. **예**를 선택 합니다. 문제가 발생 하는 경우 파일 탐색기에서 다운로드 한 파일을 찾고 설치 관리자 아이콘을 마우스 오른쪽 단추로 클릭 한 다음 상황에 맞는 메뉴에서 **관리자 권한으로 실행** 을 선택 합니다.

   ![Visual Studio 설치 관리자 다운로드 및 설치](media/vscpp-concierge-run-installer.gif "Visual Studio 설치 관리자 다운로드 및 설치")

1. 설치 관리자는 특정 개발 영역에 대한 관련 옵션의 그룹인 워크로드 목록을 제공합니다. 에 대 C++ 한 지원은 이제 기본적으로 설치 되지 않는 선택적 워크 로드의 일부입니다.

   ![워크 로드를 C++ 사용한 데스크톱 개발](media/desktop-development-with-cpp.png "C++를 사용한 데스크톱 개발")

   에서 워크 로드를 **사용하여 C++ 데스크톱 개발** 을 선택한 다음 설치를 선택 합니다. C++

   ![워크 로드를 사용 하 C++ 여 데스크톱 개발 설치](media/vscpp-concierge-choose-workload.gif "워크 로드를 사용 하 C++ 여 데스크톱 개발 설치")

1. 설치가 완료 되 면 **시작** 단추를 선택하여 Visual Studio를 시작 합니다.

   Visual Studio를 처음 실행할 때 Microsoft 계정으로 로그인 하 라는 메시지가 표시 됩니다. 가지고 있지 않으면 무료로 만들 수 있습니다. 테마도 선택 해야 합니다. 걱정 하지 마세요. 원하는 경우 나중에 변경할 수 있습니다.

   Visual Studio를 처음 실행할 때 사용할 수 있도록 준비 하는 데 몇 분 정도 걸릴 수 있습니다. 빠른 시간 경과 시의 모양은 다음과 같습니다.

   ![Visual Studio 2017 로그인](media/vscpp-quickstart-first-run.gif "Visual Studio 2017 로그인")

   다시 실행 하면 Visual Studio가 훨씬 빠르게 시작 됩니다.

1. Visual Studio가 열리면 제목 표시줄의 플래그 아이콘이 강조 표시 되는지 확인 합니다.

   ![Visual Studio 2017 알림 플래그](media/vscpp-first-start-page-flag.png "Visual Studio 2017 알림 플래그")

   강조 표시 된 경우 선택하여 **알림** 창을 엽니다. Visual Studio에 사용할 수 있는 업데이트가 있는 경우 지금 설치 하는 것이 좋습니다. 설치가 완료 되 면 Visual Studio를 다시 시작 합니다.

::: moniker-end

::: moniker range="<vs-2017"

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 설치

Visual Studio 2015를 설치하려면 [이전 버전의 Visual Studio 다운로드](https://www.visualstudio.com/vs/older-downloads/)로 이동합니다. 설치 프로그램을 실행하고 **사용자 지정 설치**를 선택한 다음, C++ 구성 요소를 선택합니다. 기존 Visual C++ Studio 2015 설치에 대한 지원을 추가 하려면 Windows 시작 단추를 클릭 하 고 **프로그램 추가/제거**를 입력 합니다. 결과 목록에서 프로그램을 열고 설치 된 프로그램 목록에서 Visual Studio 2015 설치를 찾습니다. 두 번 클릭 한 다음 **수정** 을 선택하고 설치할 시각적 C++ 구성 요소를 선택 합니다.

일반적으로 Visual Studio 2015 컴파일러를 사용하여 코드를 컴파일해야 하는 경우에도 Visual Studio 2017을 사용하는 것이 좋습니다. 자세한 내용은 [Visual Studio의 네이티브 멀티 타기팅을 사용하여 이전 프로젝트 빌드](../porting/use-native-multi-targeting.md)를 참조하세요.

::: moniker-end

Visual Studio가 실행 중일 때 다음 단계로 진행할 준비가 되었습니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [C++ 프로젝트 만들기](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
