---
title: CLR을 대상으로 하는 C++/CLI 프로그램 컴파일
description: Microsoft C++를 사용하여 기본 C++ 코드 및 .NET 프로그램을 연결할 수 있는 프로그램 및 라이브러리를 만듭니다.
ms.date: 04/23/2019
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
ms.openlocfilehash: 0d661d9e77211a0e49f8695ad713b607377a236a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371807"
---
# <a name="walkthrough-compile-a-ccli-program-that-targets-the-clr-in-visual-studio"></a>연습: 비주얼 스튜디오에서 CLR을 대상으로 하는 C++/CLI 프로그램 컴파일

C++/CLI를 사용하면 기본 C++ 형식뿐만 아니라 .NET 클래스를 사용하는 C++ 프로그램을 만들 수 있습니다. C++/CLI는 기본 C++ 코드를 래핑하고 .NET 프로그램에서 액세스할 수 있도록 하는 콘솔 응용 프로그램 및 DLL에서 사용하기 위한 것입니다. .NET을 기반으로 하는 Windows 사용자 인터페이스를 만들려면 C# 또는 Visual Basic을 사용합니다.

이 절차에서는 고유한 C++ 프로그램을 입력하거나 샘플 프로그램 중 하나를 사용할 수 있습니다. 이 프로시저에서 사용하는 샘플 프로그램은 textfile.txt라는 텍스트 파일을 만들고 프로젝트 디렉터리에 저장합니다.

## <a name="prerequisites"></a>사전 요구 사항

- C++ 언어의 기본적인 사항을 알고 있어야 합니다.
- Visual Studio 2017 이상에서 C++/CLI 지원은 선택적 구성 요소입니다. 설치하려면 Windows 시작 메뉴에서 **Visual Studio 설치 관리자를** 엽니다. **C++** 타일이 있는 데스크톱 개발이 선택되어 있는지 확인하고 **옵션** 구성 요소 섹션에서 **C++/CLI 지원도**확인합니다.

## <a name="create-a-new-project"></a>새 프로젝트 만들기

다음 단계는 사용 중인 Visual Studio 버전에 따라 다릅니다. 선호하는 버전의 Visual Studio에 대한 설명서를 보려면 **버전** 선택기 컨트롤을 사용합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker range="vs-2019"

### <a name="to-create-a-ccli-project-in-visual-studio-2019"></a>비주얼 스튜디오 2019에서 C++/CLI 프로젝트를 만들려면

1. **솔루션 탐색기에서**맨 오른쪽 단추를 클릭하여 **새 프로젝트 만들기** 대화 상자를 엽니다.

1. 대화 상자 맨 위에 있는 검색 상자에 **CLR을** 입력한 다음 결과 목록에서 **CLR 빈 프로젝트를** 선택합니다.

1. **만들기** 단추를 선택하여 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-ccli-project-in-visual-studio-2017"></a>비주얼 스튜디오 2017에서 C++/CLI 프로젝트를 만들려면

1. 새 프로젝트를 만듭니다. **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.

1. Visual C++ 프로젝트 형식에서 **CLR**을 클릭한 다음, **CLR 빈 프로젝트**를 클릭합니다.

1. 프로젝트 이름을 입력합니다. 기본적으로 프로젝트를 포함하는 솔루션에는 새 프로젝트와 동일한 이름이 있지만 다른 이름을 입력할 수 있습니다. 원하는 경우 프로젝트에 다른 위치를 입력할 수 있습니다.

1. **확인**을 클릭하여 새 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-ccli-project-in-visual-studio-2015"></a>비주얼 스튜디오 2015에서 C++/CLI 프로젝트를 만들려면

1. 새 프로젝트를 만듭니다. **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.

1. Visual C++ 프로젝트 형식에서 **CLR**을 클릭한 다음, **CLR 빈 프로젝트**를 클릭합니다.

1. 프로젝트 이름을 입력합니다. 기본적으로 프로젝트를 포함하는 솔루션에는 새 프로젝트와 동일한 이름이 있지만 다른 이름을 입력할 수 있습니다. 원하는 경우 프로젝트에 다른 위치를 입력할 수 있습니다.

1. **확인**을 클릭하여 새 프로젝트를 만듭니다.

::: moniker-end

## <a name="add-a-source-file"></a>소스 파일 추가

1. **솔루션 탐색기**가 보이지 않으면 **보기** 메뉴에서 **솔루션 탐색기**를 클릭합니다.

1. 프로젝트에 새 원본 파일을 추가합니다.

   - **솔루션 탐색기**에서 **소스 파일** 폴더를 마우스 오른쪽 단추로 클릭하고, **추가**를 가리키고, **새 항목**을 클릭합니다.

   - **C++ 파일(.cpp)** 을 클릭하고, 파일 이름을 입력한 다음, **추가**를 클릭합니다.

   **.cpp** 파일은 **솔루션 탐색기**의 **소스 파일** 폴더에 나타나고, 탭으로 구분된 창은 해당 파일에 원하는 코드를 입력한 위치에 나타납니다.

1. Visual Studio에서 새로 만든 탭을 클릭하고, 유효한 Visual C++ 프로그램을 입력하거나 샘플 프로그램 중 하나를 복사하고 붙여넣습니다.

   예를 들어 프로그래밍 가이드의 **파일 처리 및 I/O** 노드에서 [방법: 텍스트 파일 쓰기(C++/CLI)](how-to-write-a-text-file-cpp-cli.md) 샘플 프로그램을 사용할 수 있습니다.

   샘플 프로그램을 사용하는 경우 .NET 개체를 만들 때 `new` 대신 `gcnew` 키워드를 사용하고 `gcnew`는 포인터(`*`) 대신 핸들(`^`)을 반환합니다.

   `StreamWriter^ sw = gcnew StreamWriter(fileName);`

   C++/CLI 구문에 대한 자세한 내용은 [런타임 플랫폼에 대한 구성 요소 확장을](../extensions/component-extensions-for-runtime-platforms.md)참조하십시오.

1. **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

   **출력** 창은 빌드 로그의 위치 및 빌드 상태를 나타내는 메시지와 같은 컴파일 진행 상황에 대한 정보를 표시합니다.

   빌드 작업을 수행하지 않고 프로그램을 변경하고 실행하는 경우 대화 상자는 프로젝트가 만료되었다고 표시할 수 있습니다. Visual Studio가 항상 최신 버전의 파일을 사용하도록 하려면 애플리케이션을 빌드할 때마다 메시지를 표시하는 대신 **확인**을 클릭하기 전에 이 대화 상자에서 확인란을 선택합니다.

1. **디버그** 메뉴에서 **디버깅 하지 않고 시작을**클릭합니다.

1. 샘플 프로그램을 사용한 경우 프로그램을 실행할 때 텍스트 파일이 만들어졌는지 여부를 나타내는 명령 창이 표시됩니다.

   **textfile.txt** 텍스트 파일은 이제 프로젝트 디렉터리에 위치합니다. 메모장을 사용하여 이 파일을 열 수 있습니다.

   > [!NOTE]
   > 빈 CLR 프로젝트 템플릿을 선택하면 `/clr` 컴파일러 옵션이 자동으로 설정됩니다. 이를 확인하려면 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고, **속성**을 클릭한 다음, **구성 속성**의 **일반** 노드에서 **공용 언어 런타임 지원** 옵션을 선택합니다.

## <a name="see-also"></a>참고 항목

[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[프로젝트 및 빌드 시스템](../build/projects-and-build-systems-cpp.md)<br/>
