---
title: MFC DLL 마법사
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.dll.overview
helpviewer_keywords:
- MFC DLLs [MFC], creating
- MFC DLL Wizard
- DLLs [MFC], MFC
- DLL wizard [MFC]
- MFC DLLs [MFC]
- DLLs [MFC], creating
ms.assetid: 4e936031-7e39-4f40-a295-42a09c5ff264
ms.openlocfilehash: e607a27cbb06efd86d3a50aae5e62edf5ba3d400
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65217584"
---
# <a name="mfc-dll-wizard"></a>MFC DLL 마법사

MFC DLL 마법사를 사용하여 MFC DLL 프로젝트를 만들면 컴파일시 [DLL](../../build/dlls-in-visual-cpp.md)의 기본 기능을 구현하는 기본 제공 기능이 포함된 작업용 스타터 응용 프로그램이 제공됩니다.  MFC 스타터 프로그램에는 C++ 소스 파일 (.cpp), 리소스 (.rc) 파일 및 프로젝트 (.vcxproj) 파일이 포함됩니다. 이 스타터 파일에서 생성된 코드는 MFC를 기반으로 합니다. 자세한 내용은 Visual Studio에서 프로젝트에 생성된 Readme.txt 파일 세부 정보 및 [MFC DLL 마법사에서 생성된 클래스와 함수](../../mfc/reference/classes-and-functions-generated-by-the-mfc-dll-wizard.md)를 참조합니다.

## <a name="overview"></a>개요

이 마법사 페이지에서는 개발자가 생성한 현재 [MFC DLL 프로젝트에 대한 응용 프로그램 설정](../../mfc/reference/application-settings-mfc-dll-wizard.md)에 대해 설명합니다. 기본적으로 추가설정이 없다면 MFC DLL(MFC 공유 DLL)로 프로젝트가 만들어집니다.

이러한 기본값을 변경 하려면 마법사의 왼쪽 열에서 **응용 프로그램 설정**을 클릭하고 MFC DLL 마법사의 해당 페이지에서 변경하세요.

MFC DLL 프로젝트를 만든 후 Visual C++ [코드 마법사](../../ide/adding-functionality-with-code-wizards-cpp.md)를 사용하여 프로젝트에 개체 또는 컨트롤을 추가할 수 있습니다.

기본 MFC DLL 프로젝트에 대하여 다음 작업 및 성능 향상을 위한 유형을 수행할 수 있습니다.

- [DLL에서 내보내기](../../build/exporting-from-a-dll.md)

- [DLL에 실행 파일 링크](../../build/linking-an-executable-to-a-dll.md)

- [DLL 초기화](../../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="see-also"></a>참고자료

[Visual Studio 프로젝트 - C++](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[속성 페이지(Visual C++)](../../build/reference/property-pages-visual-cpp.md)<br/>
[컴파일러 설정 및 빌드 속성](../../build/working-with-project-properties.md)<br/>
[MFC 클래스](../../mfc/reference/adding-an-mfc-class.md)<br/>
[멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[인터페이스 구현](../../ide/implementing-an-interface-visual-cpp.md)<br/>
