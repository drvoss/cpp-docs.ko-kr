---
title: '방법: Windows 데스크톱 응용 프로그램에서 Windows 10 SDK 사용'
description: Windows 10 SDK를 사용 하도록 Windows 데스크톱 응용 프로그램 프로젝트에서 대상 SDK 버전을 설정 하는 방법입니다.
ms.custom: get-started-article
ms.date: 01/22/2020
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
ms.openlocfilehash: c1d71b591398453f7cee02aa22cd2e377991588f
ms.sourcegitcommit: b67b08472b6f1ee8f1c5684bba7056d3e0fc745f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76725736"
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>방법: Windows 데스크톱 응용 프로그램에서 Windows 10 SDK 사용

Visual Studio에서 새 클래식 Windows 데스크톱 프로젝트를 만들면 기본적으로 Windows 10 SDK를 대상으로 합니다. 데스크톱 워크 로드를 C++ 설치 하면 Visual Studio에서이 SDK의 버전을 설치 합니다. Windows 10 SDK는 Windows 7 SP1 이상에 대 한 코드 작성을 지원 합니다. 특정 버전의 Windows를 대상으로 지정 하는 방법에 대 한 자세한 내용은 [Windows 헤더 사용](/windows/win32/WinProg/using-the-windows-headers) 및 [업데이트 WINVER 및 _WIN32_WINNT](../porting/modifying-winver-and-win32-winnt.md)를 참조 하세요.

기존 프로젝트를 업그레이드할 때 선택할 수 있습니다. 프로젝트에 지정 된 대상 Windows SDK를 계속 사용할 수 있습니다. 또는 Windows 10 SDK를 사용 하도록 프로젝트 대상을 변경할 수 있습니다. Windows 10 SDK를 사용 하 여 최신 운영 체제 및 언어 표준에 대 한 지원의 이점을 얻을 수 있습니다.

## <a name="use-the-right-windows-sdk-for-your-project"></a>프로젝트에 적합 한 Windows SDK 사용

Visual Studio 2015부터 CRT (C 런타임) 라이브러리는 두 부분으로 구분 됩니다. 즉, C 런타임 (C 런타임) 라이브러리는 유니버설 Windows 앱에서 사용할 수 있는 표준 C 및 Microsoft 전용 CRT 함수를 포함 합니다. 이 라이브러리는 이제 유니버설 CRT 또는가 중 RT로 알려져 있고 Windows 10 SDK로 이동 했습니다. C99 함수는 최신 C++ 언어 표준을 지 원하는 데 필요한 여러 가지 새로운 함수를 포함 합니다. 원본 CRT의 다른 부분은 vcruntime입니다. 여기에는 C 런타임 지원, 시작 및 종료 코드와 기타 모든 항목이 포함 됩니다. Vcruntime 라이브러리는 Visual Studio에서 C++ 컴파일러 및 도구 집합과 함께 설치 됩니다. 자세한 내용은 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)을 참조 하세요.

이제는 모든 버전의 Windows 10에 설치 된 시스템 구성 요소가 있습니다. 또한 이전에 지원 되는 모든 버전의 Windows에 대 한 설치 가능 구성 요소로 사용할 수 있습니다. Windows 10 SDK를 사용 하 여 지원 되는 모든 버전의 Windows를 대상으로 지정할 수 있습니다. 지원 되는 운영 체제의 전체 목록은 [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk)를 참조 하세요.

Visual Studio 2015 이전 버전의 프로젝트에서 업그레이드 하는 경우 Windows 10 SDK를 사용 하도록 프로젝트 대상을 변경 하려면 다음 단계를 수행 합니다.

### <a name="to-target-the-windows-10-sdk"></a>Windows 10 SDK를 대상으로 하려면

1. Windows 10 SDK가 설치되었는지 확인합니다. Windows 10 SDK는 워크 로드 **를 사용 하 C++ 여 데스크톱 개발** 의 일부로 설치 됩니다. 독립 실행형 버전은 [Windows 10 용 다운로드 및 도구](https://developer.microsoft.com/windows/downloads)에서 사용할 수 있습니다.

1. 프로젝트 노드에 대 한 바로 가기 메뉴를 열고 **프로젝트**대상 변경을 선택 합니다. (이전 버전의 Visual Studio에서는 대상 변경 **SDK 버전**을 선택 합니다.) **솔루션 작업 검토** 대화 상자가 나타납니다.

   ![솔루션 작업 검토](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")

1. 에 **대상 플랫폼 버전** 드롭다운 목록에서 대상으로 하려는 Windows 10 SDK의 버전을 선택합니다. 일반적으로 설치 된 최신 버전을 선택 하는 것이 좋습니다. **확인** 단추를 선택 하 여 변경 내용을 적용 합니다.

   이 컨텍스트의 8.1는 Windows 8.1 SDK를 참조 합니다.

   이 단계에 성공한 경우 출력 창에 다음 텍스트가 나타납니다.

   `Retargeting End: 1 completed, 0 failed, 0 skipped`

1. 프로젝트 속성 대화 상자를 엽니다. **구성 속성** > **일반** 섹션에서 **Windows 대상 플랫폼 버전**의 값을 확인 합니다. 여기서 이 값을 변경하면 이 절차를 따르는 것과 효과가 같습니다. 자세한 내용은 [일반 속성 페이지(프로젝트)](../build/reference/general-property-page-project.md)를 참조하세요.

   ![대상 플랫폼 버전](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")

   이 작업은 헤더 파일 및 라이브러리 파일에 대한 경로가 포함된 프로젝트 매크로의 값을 변경합니다. 변경 된 내용을 확인 하려면 **프로젝트 속성** 대화 상자의 **시각적 C++ 디렉터리** 섹션을 엽니다. **포함 디렉터리**와 같은 속성 중 하나를 선택 합니다. 그런 다음 속성 값의 드롭다운 목록을 열고 **\<편집 >** 를 선택 합니다. **포함 디렉터리** 대화 상자가 나타납니다.

   ![포함 디렉터리 대화 상자](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")

   **매크로 > >** 단추를 선택 하 고 매크로 목록에서 Windows SDK 매크로로 스크롤하여 모든 새 값을 확인 합니다.

   ![Windows SDK 매크로](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")

1. 필요에 따라 다른 솔루션 프로젝트에 대 한 대상 변경 절차를 반복 하 고 솔루션을 다시 빌드합니다.

### <a name="to-target-the-windows-81-sdk"></a>Windows 8.1 SDK를 대상으로 하려면

1. 솔루션 탐색기에서 프로젝트 노드에 대 한 바로 가기 메뉴를 열고 **프로젝트**대상 변경을 선택 합니다. (이전 버전의 Visual Studio에서는 대상 변경 **SDK 버전**을 선택 합니다.)

2. **대상 플랫폼 버전** 드롭다운 목록에서 **8.1**를 선택 합니다.

## <a name="see-also"></a>참조

[연습: 기존 Windows 데스크톱 응용 프로그램 만들기 (C++)](../windows/walkthrough-creating-windows-desktop-applications-cpp.md)
