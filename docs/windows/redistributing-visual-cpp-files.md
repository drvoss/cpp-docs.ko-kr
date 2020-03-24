---
title: Visual C++ 파일 재배포
ms.date: 11/04/2016
helpviewer_keywords:
- application deployment [C++], file redistributing
- redistributing applications [C++]
- deploying applications [C++], file redistributing
- file redistribution [C++]
- redistributing applications [C++], about redistributing applications
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
ms.openlocfilehash: 46192fe7ff5b29c22a5001cc460c74f5ddf6d1bb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167929"
---
# <a name="redistributing-visual-c-files"></a>Visual C++ 파일 재배포

> [!NOTE]
> Visual C++ 런타임 파일 중 하나의 다운로드를 찾고 있습니까? [Microsoft 웹 사이트로](https://www.microsoft.com/) 이동 하 고 검색 상자에  **C++ 비주얼 재배포 가능** 을 입력 합니다. 컴퓨터 아키텍처(예: 64비트 Windows를 실행하는 경우 x64) 및 필요한 Visual C++ 버전(예: 2015)의 재배포 가능 패키지를 다운로드하여 설치합니다.

애플리케이션을 배포할 때 이 애플리케이션을 지원하는 데 필요한 파일도 배포해야 합니다. Microsoft에서 이러한 파일을 제공하는 경우 파일을 다시 배포할 수 있는지 여부를 확인합니다. Visual Studio 사용 조건을 검토하려면 IDE의 Microsoft Visual Studio 정보 대화 상자에서 사용 조건 연결을 참조하거나, [Microsoft 소프트웨어 사용 조건](https://visualstudio.microsoft.com/license-terms/mlt687465/) 파일을 다운로드합니다. 특정 버전의 Visual Studio에 대한 Microsoft 소프트웨어 사용 조건의 "배포 가능 코드" 섹션에서 언급된 "REDIST 목록"을 보려면 [Microsoft Visual Studio 2017 및 Microsoft Visual Studio 2017 SDK용 배포 가능 코드(유틸리티 및 BuildServer 파일 포함)](/visualstudio/productinfo/2017-redistribution-vs)를 참조하세요. Visual Studio 2015의 경우 [Microsoft Visual Studio 2015 및 Microsoft Visual Studio 2015 SDK용 배포 가능 코드](/visualstudio/productinfo/2015-redistribution-vs)를 참조하세요. 재배포 가능 파일에 대한 자세한 내용은 [재배포할 DLL 확인](determining-which-dlls-to-redistribute.md) 및 [배포 예제](deployment-examples.md)를 참조하세요.

재배포 가능한 Visual C++ 파일을 배포하려면 Visual Studio에 포함된 Visual C++ 재배포 가능 패키지(VCRedist\_x86.exe, VCRedist\_x64.exe 또는 VCRedist\_arm.exe)를 사용할 수 있습니다. Visual Studio 2017에서 이러한 파일은 Program Files[(x86)]\\Microsoft Visual Studio\\2017\\_edition_\\VC\\Redist\\MSVC\\_lib-version_ 폴더에 있습니다. 여기서 _edition_은 설치된 Visual Studio 버전이고, _lib-version_은 재배포할 라이브러리 버전입니다. Visual Studio 2015에서 이러한 파일은 Program Files[(x86)]\Microsoft Visual Studio *version*\VC\redist\\*locale*\\의 Visual Studio 설치 디렉터리 아래에 있습니다. 다른 옵션은 Visual Studio 2017의 Program Files[(x86)]\\Microsoft Visual Studio\\2017\\_edition_\\ VC\\Redist\\MSVC\\_lib-version_\\MergeModules\\ 폴더에 있는 재배포 가능 병합 모듈(.msm 파일)을 사용하는 것입니다. Visual Studio 2015에서 이러한 파일은 Program Files[(x86)]\common Files\Merge Modules\\에 있습니다. 애플리케이션 실행 파일이 들어 있는 폴더인 *애플리케이션 로컬 폴더*에 재배포 가능한 Visual C++ DLL을 직접 설치할 수도 있습니다. 서비스 편의를 위해 이 설치 위치를 사용하지 않는 것이 좋습니다.

Visual C++ 재배포 가능 패키지는 모든 Visual C++ 라이브러리를 설치하고 등록합니다. 재배포 가능 패키지를 사용하는 경우 애플리케이션 설치의 필수 구성 요소로 대상 시스템에서 실행되도록 설정해야 합니다. Visual C++ 라이브러리의 자동 업데이트를 사용하기 때문에 이러한 배포 패키지를 사용하는 것이 좋습니다. 이러한 패키지를 사용하는 방법에 대한 예제는 [연습: Visual C++ 재배포 가능 패키지를 사용하여 Visual C++ 애플리케이션 배포](deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md)를 참조하세요.

각 Visual C++ 재배포 가능 패키지는 컴퓨터에 최신 버전이 있는지 여부를 확인합니다. 최신 버전이 있는 경우 패키지가 설치되지 않습니다. Visual Studio 2015부터 재배포 가능 패키지에 설치 실패를 알리는 오류 메시지가 표시됩니다. **/quiet** 플래그를 사용하여 패키지를 실행하는 경우 오류 메시지가 표시되지 않습니다. 어떤 경우든 오류가 Microsoft Installer에 기록되며, 오류 결과가 호출자에게 반환됩니다. Visual Studio 2015 패키지부터 레지스트리를 검사하여 최신 버전이 설치되어 있는지 확인함으로써 이 오류를 방지할 수 있습니다. 현재 설치된 버전은 HKEY_LOCAL_MACHINE\SOFTWARE[\Wow6432Node]\Microsoft\VisualStudio\\_vs-version_\VC\Runtimes\\{x86|x64|ARM} 키에 저장됩니다. 여기서 _vs-version_은 Visual Studio의 버전 번호입니다(업데이트된 2017 재배포 가능 파일은 2015 버전과 이진 호환되므로 Visual Studio 2015와 Visual Studio 2017의 경우 모두 14.0). 여기서 키는 플랫폼에 설치된 vcredist 버전에 따라 ARM, x86 또는 x64입니다. (X64 플랫폼에서 설치 된 x86 패키지의 버전을 확인 하는 데 RegEdit를 사용 하지 않는 한 Wow6432Node 하위 키에서 확인할 필요가 없습니다.) 버전 번호는 REG_SZ 문자열 값 **버전** 에 저장 되며 **Major**, **Minor**, **Bld**및 **Rbld** REG_DWORD 값 집합에도 저장 됩니다. 설치 시 오류를 방지하려면 현재 설치된 버전이 최신 버전인 경우 재배포 가능 패키지 설치를 건너뛰어야 합니다.

Visual C++ DLL이 들어 있는 병합 모듈을 사용하는 경우 애플리케이션을 배포하는 데 사용할 Windows Installer 패키지(또는 유사한 설치 패키지)에 해당 모듈을 포함해야 합니다. 자세한 내용은 [병합 모듈을 사용하여 재배포](redistributing-components-by-using-merge-modules.md)를 참조하세요. 예제는 [연습: 설치 프로젝트를 사용하여 Visual C++ 애플리케이션 배포](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)를 참조하세요. 여기에서는 InstallShield Limited Edition을 사용하여 설치 패키지를 만드는 방법도 보여 줍니다.

## <a name="potential-run-time-errors"></a>발생 가능한 런타임 오류

Windows에서 애플리케이션에 필요한 재배포 가능 라이브러리 DLL 중 하나를 찾을 수 없는 경우, "*library*.dll을 찾을 수 없어 이 애플리케이션을 시작하지 못했습니다. 애플리케이션을 다시 설치하면 이 문제가 해결될 수 있습니다."와 유사한 메시지가 표시될 수 있습니다.

이러한 종류의 오류를 해결하려면 애플리케이션 설치 관리자가 올바르게 빌드되고, 재배포 가능 라이브러리가 대상 시스템에 올바르게 배포되었는지 확인합니다. 자세한 내용은 [Visual C++ 애플리케이션의 종속성 이해](understanding-the-dependencies-of-a-visual-cpp-application.md)를 참조하세요.

## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----------|-----------------|
|[병합 모듈을 사용하여 재배포](redistributing-components-by-using-merge-modules.md)|Visual C++ 재배포 가능 병합 모듈을 사용하여 Visual C++ 런타임 라이브러리를 공유 DLL로 %windir%\system32\ 폴더에 설치하는 방법에 대해 설명합니다.|
|[Visual C++ ActiveX 컨트롤 재배포](redistributing-visual-cpp-activex-controls.md)|ActiveX 컨트롤을 사용하는 애플리케이션을 재배포하는 방법에 대해 설명합니다.|
|[MFC 라이브러리 재배포](redistributing-the-mfc-library.md)|MFC를 사용하는 애플리케이션을 재배포하는 방법에 대해 설명합니다.|
|[ATL 애플리케이션 재배포](redistributing-an-atl-application.md)|ATL을 사용하는 애플리케이션을 재배포하는 방법에 대해 설명합니다. Visual Studio 2012부터 ATL에 대한 재배포 가능 라이브러리가 필요하지 않습니다.|
|[배포 예제](deployment-examples.md)|Visual C++ 애플리케이션을 배포하는 방법을 보여 주는 예제에 대한 링크입니다.|
|[데스크톱 애플리케이션 배포](deploying-native-desktop-applications-visual-cpp.md)|Visual C++ 배포 개념과 기술을 소개합니다.|
