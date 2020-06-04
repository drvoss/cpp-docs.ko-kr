---
title: Windows 데스크톱 마법사
ms.date: 03/29/2019
f1_keywords:
- vc.appwiz.win32.overview
- vc.appwiz.win32.appset
helpviewer_keywords:
- Windows Desktop Wizard
- Win32 Project Wizard
ms.assetid: 5d7b3a5e-8461-479a-969a-67b7883725b9
ms.openlocfilehash: 3ba53be8e412a39d938198cbd7f2587496ea38eb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165953"
---
# <a name="windows-desktop-wizard"></a>Windows 데스크톱 마법사

Windows 데스크톱 마법사는 Visual Studio 2017 이상의 Win32 응용 프로그램 마법사를 대체합니다. 마법사를 사용하면 아래 표의 제목에 나열된 네 가지 유형 중 하나의 C++ 프로젝트를 만들 수 있습니다. 각각의 경우 연 프로젝트 형식에 적합한 추가 옵션을 지정할 수 있습니다.

   ![Windows 데스크톱 마법사](media/windows-desktop-wizard.png)

다음 표에서는 각 애플리케이션 유형에 사용할 수 있는 옵션을 나타냅니다.

|지원 유형|콘솔 애플리케이션|실행 파일(Windows) 애플리케이션|동적 연결 라이브러리|정적 라이브러리|
|---------------------|-------------------------|----------------------------------------|---------------------------|--------------------|
|**빈 프로젝트**|yes|yes|yes|예|
|**내보내기 기호**|예|예|yes|예|
|**미리 컴파일된 헤더**|예|예|예|yes|
|**ATL 지원**|yes|예|예|예|
|**MFC 지원**|yes|예|예|yes|

## <a name="overview"></a>개요

이 마법사 페이지에서는 만들려는 Win32 애플리케이션에 대한 현재 프로젝트 설정을 설명합니다. 기본적으로 설정된 옵션은 다음과 같습니다.

- 프로젝트는 Windows 애플리케이션입니다.

- 프로젝트가 비어 있지 않습니다.

- 프로젝트에 내보내기 기호가 없습니다.

- 프로젝트에서 미리 컴파일된 헤더 파일을 사용하지 않습니다. 이 옵션은 정적 라이브러리 프로젝트에만 사용할 수 있습니다.

- 프로젝트에 MFC 또는 ATL에 대한 지원이 없습니다.

## <a name="application-type"></a>애플리케이션 종류

지정 된 응용 프로그램 유형을 만듭니다.

|옵션|Description|
|------------|-----------------|
|**콘솔 응용 프로그램**|콘솔 애플리케이션을 만듭니다. 또한 시각적 C++ [런타임 라이브러리](../c-runtime-library/c-run-time-library-reference.md) 는 `printf_s()` 및 `scanf_s()`와 같은 표준 i/o 함수를 사용 하 여 콘솔 창에서 출력 및 입력을 제공 합니다. 콘솔 응용 프로그램에 그래픽 사용자 인터페이스가 없습니다. .exe로 컴파일되고 명령줄에서 독립 실행형 응용 프로그램으로 실행할 수 있습니다.<br /><br /> Windows 응용 프로그램에 MFC 또는 ATL 지원을 추가 할 수 없습니다.|
|**Windows 응용 프로그램**|Win32 프로그램을 만듭니다. Win32 프로그램은 실행 가능한 응용 프로그램(EXE)으로 C 또는 C++로 작성되고, Win32 API를 호출하여 그래픽 사용자 인터페이스를 만들 수 있습니다.<br /><br /> MFC를 추가할 수 없습니다. 또는 Windows 응용 프로그램에 ATL을 지원합니다.|
|**동적 연결 라이브러리**|Win32 동적 연결 라이브러리 (DLL)를 만듭니다. Win32 DLL은 C 또는 C++로 작성된 바이너리 파일로, MFC 클래스 대신 Win32 API를 호출하며 동시에 여러 응용 프로그램에서 사용할 수 있는 함수의 공유 라이브러리 역할을 합니다.<br /><br /> 이 마법사를 사용 하 여 만든 DLL 응용 프로그램에 MFC 또는 ATL 지원을 추가할 수는 없지만 **새 > 프로젝트 > MFC dll**을 선택 하 여 mfc dll을 만들 수 있습니다.|
|**정적 라이브러리**|정적 라이브러리를 만듭니다. 정적 라이브러리는 개체와 개체 함수 그리고 실행 파일을 빌드할 때 프로그램에 연결되는 데이터를 포함하는 파일입니다. 이 항목에서는 정적 라이브러리에 대 한 시작 파일 및 [프로젝트 속성](../build/reference/property-pages-visual-cpp.md) 을 만드는 방법에 대해 설명 합니다. 정적 라이브러리 파일은 다음과 같은 이점을 제공합니다.<br /><br />-Win32 정적 라이브러리는 작업 중인 응용 프로그램에서 MFC 클래스 대신 Win32 API를 호출하는 경우에 유용합니다.<br />-Windows 응용 프로그램의 나머지 부분이 C 또는 C++로 작성되었는지 여부와 관계없이 연결된 프로세스는 동일합니다.<br />-비 MFC 프로그램과 MFC 기반 프로그램 모두 정적 라이브러리를 연결할 수 있습니다.|

## <a name="additional-options"></a>추가 옵션

해당 형식에 따라 응용 프로그램에 대한 지원 및 옵션을 정의합니다.

|옵션|Description|
|------------|-----------------|
|**빈 프로젝트**|프로젝트 파일이 비어 있는지를 확인합니다. 소스 코드 파일(예:.cpp 파일, 헤더 파일, 아이콘, 도구 모음, 대화 상자 등)의 집합이 있고 Visual C++ 개발 환경에서 프로젝트를 만들 경우 먼저 빈 프로젝트를 만든 다음 파일을 프로젝트에 추가해야 합니다.<br /><br /> 이 옵션은 정적 라이브러리 프로젝트를 선택할 수 없는 경우 사용합니다.|
|**내보내기 기호**|DLL 프로젝트에서 기호를 내보내도록 지정 합니다.|
|**미리 컴파일된 헤더**|정적 라이브러리 프로젝트에서는 미리 컴파일된 헤더를 사용하도록 지정합니다.|
|**SDL (보안 개발 수명 주기) 검사**|SDL에 대 한 자세한 내용은 [Microsoft SDL(Security Development Lifecycle) 프로세스 지침](../build/reference/sdl-enable-additional-security-checks.md) 을 참조 하세요.|

## <a name="add-common-headers-for"></a>공용 헤더 추가

Visual C++에서 제공되는 라이브러리에 대한 지원을 추가합니다.

|옵션|Description|
|------------|-----------------|
|**ALT**|액티브 템플릿 라이브러리 (ATL)의 클래스를 추가 지원하여 프로젝트를 빌드합니다. Win32 콘솔 응용 프로그램에만 해당됩니다.<br /><br /> **참고** 이 옵션은 ATL 코드 마법사를 사용 하 여 ATL 개체를 추가 하는 것을 지원 하지 않습니다. ATL 프로젝트나 MFC 프로젝트에서만 ATL 개체를 추가할 수 있습니다.|
|**MFC**|MFC 라이브러리에 대한 지원을 프로젝트에 빌드합니다. Win32 콘솔 응용 프로그램 및 정적 라이브러리만 해당됩니다.||

## <a name="remarks"></a>설명

Windows 데스크톱 애플리케이션을 만들었으면 [제네릭](../ide/generic-cpp-class-wizard.md) 코드 마법사를 사용하여 제네릭 C++ 클래스를 추가할 수 있습니다. HTML 파일, 헤더 파일, 리소스 또는 텍스트 파일 등의 다른 항목을 추가할 수 있습니다.

> [!NOTE]
> ATL 클래스는 추가할 수 없으며 MFC 클래스는 MFC를 지원하는 Windows 데스크톱 애플리케이션 형식(이전 표 참조)에만 추가할 수 있습니다.

마법사에서 프로젝트용으로 만든 파일은 **솔루션 탐색기**에서 볼 수 있습니다. 마법사에서 프로젝트용으로 만드는 파일에 대 한 자세한 내용은 프로젝트 생성 파일, `ReadMe.txt`를 참조 하세요. 파일 형식에 대 한 자세한 내용은 [Visual Studio C++ 프로젝트용으로 만들어지는 파일 형식](../build/reference/file-types-created-for-visual-cpp-projects.md)을.

## <a name="see-also"></a>참고 항목

[Visual Studio의 C++ 프로젝트 형식](../build/reference/visual-cpp-project-types.md)
