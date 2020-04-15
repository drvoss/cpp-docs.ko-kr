---
title: 재배포 가능 패키지(C++)를 사용하여 앱 배포
ms.date: 04/23/2019
helpviewer_keywords:
- walkthrough, deploying a Visual C++ application by using the redistributable package
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
ms.openlocfilehash: d2bd0794a67cf70b9da0499e3d2cafa553531fe1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370250"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-the-visual-c-redistributable-package"></a>연습: Visual C++ 재배포 가능 패키지를 사용하여 Visual C++ 애플리케이션 배포

이 단계별 문서에서는 Visual C++ 재배포 가능 패키지를 사용하여 Visual C++ 애플리케이션을 배포하는 방법을 설명합니다.

## <a name="prerequisites"></a>사전 요구 사항

이 연습을 완료하려면 다음 구성 요소가 필요합니다.

- Visual Studio가 설치가 설치된 컴퓨터.

- Visual C++ 라이브러리가 없는 추가 컴퓨터

### <a name="to-use-the-visual-c-redistributable-package-to-deploy-an-application"></a>Visual C++ 재배포 가능 패키지를 사용하여 애플리케이션을 배포하려면

1. [연습: 설치 프로젝트를 사용하여 Visual C++ 애플리케이션 배포](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)의 단계를 수행하여 MFC 애플리케이션을 생성하고 구축합니다.

1. 파일을 만들고 이름을 setup.bat로 지정한 후, 다음 명령을 추가합니다. `MyMFCApplication`을 프로젝트의 이름으로 변경합니다.

    ```cmd
    @echo off
    vcredist_x86.exe
    mkdir "C:\Program Files\MyMFCApplication"
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"
    ```

1. 자동 압축 풀기 설치 파일을 만듭니다.

   1. 명령 프롬프트 또는 **실행** 창에서 iexpress.exe를 실행합니다.

   1. **새 자동 압축 풀기 지시문 파일 만들기**를 선택한 후, **다음** 단추를 선택합니다.

   1. **파일 압축을 풀고 설치 명령 실행**을 선택한 후, **다음**을 선택합니다.

   1. 텍스트 상자에 MFC 애플리케이션 이름을 입력한 후, **다음**을 선택합니다.

   1. **확인 프롬프트** 페이지에서 **프롬프트 없음**을 선택한 후, **다음**을 선택합니다.

   1. **사용권 계약** 페이지에서 **라이선스를 표시하지 않음**을 선택한 후, **다음**을 선택합니다.

   1. **파일 패키지** 페이지에서 다음 파일을 추가한 후, **다음**을 선택합니다.

      - MFC 애플리케이션(.exe 파일).

      - vcredist_x86.exe. 비주얼 스튜디오 2015에서,이 파일은 *%VCINSTALLDIR %\\재배포 1033에\\*있습니다 . 비주얼 스튜디오 2017 및 비주얼 스튜디오 2019에서,이 파일은 *%VCToolsRedistDir %에*있습니다 . Microsoft에서 [지원되는 최신 중복 파일도 다운로드할](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)수 있습니다.

      - 이전 단계에서 만든 setup.bat 파일.

   1. **시작할 설치 프로그램** 페이지의 **설치 프로그램** 텍스트 상자에 다음 명령줄을 입력한 후, **다음**을 선택합니다.

      **cmd.exe /c "setup.bat"**

   1. **창 표시** 페이지에서 **기본값**을 선택한 후, **다음**을 선택합니다.

   1. **완료 메시지** 페이지에서 **메시지 없음**을 선택한 후, **다음**을 선택합니다.

   1. **패키지 이름 및 옵션** 페이지에서 자동 압축 풀기 설치 파일의 이름을 입력하고 **패키지 내 긴 파일 이름을 사용하여 파일 저장** 옵션을 선택한 후, **다음**을 선택합니다. 파일 이름의 끝은 Setup.exe여야 합니다(예: *MyMFCApplicationSetup.exe*).

   1. **다시 시작 구성** 페이지에서 **다시 시작 없음**을 선택한 후, **다음**을 선택합니다.

   1. **자동 압축 풀기 지시문 저장** 페이지에서 **SED(자동 압축 풀기 지시문) 파일 저장**을 선택한 후, **다음**을 선택합니다.

   1. **패키지 만들기** 페이지에서 **다음**을 선택합니다. **마침**을 선택합니다.

1. Visual C++ 라이브러리가 없는 다른 컴퓨터에서 자동 압축 풀기 설치 파일을 테스트합니다.

   1. 다른 컴퓨터에 설치 파일의 복사본을 다운로드한 다음, 해당 파일을 실행하고 제공되는 단계에 따라 설치합니다. 선택한 옵션에 따라 설치 시 **관리자 권한으로 실행** 명령이 필요할 수 있습니다.

   1. MFC 애플리케이션을 실행합니다.

      자동 압축 풀기 설치 파일은 2단계에서 지정한 폴더에 있는 MFC 애플리케이션을 설치합니다. Visual C++ 재배포 가능 패키지 설치 관리자가 자동 압축 풀기 설치 파일에 포함되어 있기 때문에 애플리케이션이 성공적으로 실행됩니다.

      > [!IMPORTANT]
      > 설치된 런타임 \\버전을 확인하기 위해 설치 관리자는 레지스트리 키 HKLM\\\\소프트웨어\\Microsoft\\VisualStudio\\_버전_\\VC\\런타임_플랫폼_\\버전을 확인합니다. 현재 설치된 버전이 설치 관리자가 설치하려고 하는 버전보다 최신 버전인 경우, 설치 관리자는 이전 버전을 설치하지 않고 성공을 반환하고 제어판의 설치된 프로그램 페이지에 추가 항목을 남겨둡니다.

## <a name="see-also"></a>참고 항목

[배포 예](deployment-examples.md)<br/>
