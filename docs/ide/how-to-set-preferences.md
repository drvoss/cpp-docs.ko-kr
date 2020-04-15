---
title: 비주얼 스튜디오에서 C++ 코딩 환경 설정
ms.description: Customize C++ formatting, colors, layout, line numbers, and menus in the Visual Studio IDE.
ms.topic: overview
ms.date: 09/27/2019
ms.openlocfilehash: e3a665ead7a314b343ec3320e95b189f83a38a47
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365384"
---
# <a name="set-your-c-coding-preferences-in-visual-studio"></a>비주얼 스튜디오에서 C++ 코딩 환경 설정

Visual Studio를 개인화하여 C++ 코딩 환경을 보다 편리하고 생산적이며 즐겁게 만들 수 있습니다. 다음을 수행할 수 있습니다.

- 메뉴 및 도구 모음을 사용자 지정합니다.
- 창 레이아웃을 정렬합니다.
- 색상 테마를 설정합니다.
- ClangFormat의 여러 스타일을 포함하여 C++ 서식 규칙을 지정합니다.
- 사용자 지정 키보드 단축키를 만듭니다.

여러 컴퓨터에서 기본 설정을 동기화하고 여러 환경 설정 집합을 만들고 저장하고 팀원과 공유할 수 있습니다. Visual Studio 마켓플레이스에서 확장을 설치하여 동작을 사용자 지정할 수 있는 추가 옵션을 제공할 수 있습니다. 자세한 내용은 [시각적 스튜디오 IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하십시오.

## <a name="arrange-window-layout"></a>창 레이아웃 정렬

Visual Studio 창 내에서 공간은 주 메뉴, 도구 모음, 코드 편집기(또는 문서 창) 및 도구 창(예: 솔루션 탐색기 및 오류 목록)으로 나뉩니다. 일부 창은 동일한 위치에서 서로 겹칩니다. 예를 들어 솔루션 탐색기, 클래스 뷰, 리소스 보기 및 소스 제어 탐색기는 모두 동일한 기본 위치를 공유합니다. 프레임 하단의 탭을 선택하여 전환합니다. 이러한 두 개 이상의 창을 동시에 표시하려면 제목 표시줄에서 해당 창 중 하나를 새 위치로 드래그하면 됩니다. Visual Studio 기본 창 테두리 중 하나에 도킹하거나 부동 할 수 있습니다.

다음 스크린샷은 **팀 탐색기** 창이 기본 위치에서 코드 편집기 왼쪽에 있는 새 도킹 위치로 드래그되는 것을 보여 주며, 파란색 그늘진 영역은 마우스 단추를 놓을 때 창이 배치될 위치를 표시합니다.

![레이아웃 변경이 강조 표시된 Visual Studio 팀 탐색기 창의 스크린샷](media/window-layout-move-team-explorer.png)

문서 창에서 열려 있는 각 파일은 탭된 프레임에 포함됩니다. 도구 창처럼 이러한 탭을 띄거나 잠글 수 있습니다. 자세한 내용은 [Visual Studio에서 창 레이아웃 사용자 지정을](/visualstudio/ide/customizing-window-layouts-in-visual-studio)참조하세요.

모든 도구 창을 숨기고 코드 편집기 창을 최대화하려면 **Alt** + **Shift** + **Enter를** 눌러 *전체 화면 모드를*전환합니다.

## <a name="set-c-coding-styles-and-formatting"></a>C++ 코딩 스타일 및 서식 설정

들여쓰기 및 중괄호 위치와 같은 많은 개별 코드 서식 지정 옵션을 지정할 수 있습니다. 이렇게 하려면 **도구** > **옵션** > **텍스트 편집기** > **C/C++** > **서식(또는** **Ctrl + Q를** 입력하고 "서식 지정"을 검색)으로 이동합니다. 또는 [ClangFormat](https://clang.llvm.org/docs/ClangFormat.html) 스타일(또는 사용자 지정 ClangFormat 스타일) 중 하나를 지정할 수 있습니다.

![ClangFormat 옵션의 스크린샷](media/clang-format-ide.png)

모든 서식 옵션에 대한 자세한 내용은 [옵션, 텍스트 편집기, C/C++, 서식 지정](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting)을 참조하십시오.

## <a name="set-the-color-theme"></a>색 테마 설정

밝거나 어두운 배경을 설정하려면 **Ctrl + Q를** 입력하고 "색상 테마"를 검색합니다. 도구**옵션** > **환경으로** **이동하여** > 색상 테마를 선택하여 이러한 옵션을 찾을 수도 **있습니다.**

![색상 테마의 스크린 샷](media/tools-options-color-theme.png)

예를 들어 어두운 테마는 다음과 같습니다.

![어두운 색상 테마와 비주얼 스튜디오의 스크린 샷](media/tools-options-dark-theme.png)

## <a name="customize-code-colorization"></a>코드 색상 지정

Visual Studio 2019에서는 미리 정의된 세 *가지 색 구성표*중에서 선택할 수 있습니다. 이러한 코드 요소는 편집기에서 색상지정을 지정합니다. 테마를 선택하려면 **도구** > **옵션** > **텍스트 편집기** > **C/C++** > **보기로**이동하여 **색 구성표를**선택합니다.

![향상된 강조 표시된 C++ 색 구성표 옵션의 스크린샷](media/color-schemes.png)

**Visual Studio 2017이라는**색 구성표에서 대부분의 코드 요소는 단순히 검은색입니다. **고급** 색 구성표에서 함수, 지역 변수, 매크로 및 기타 요소는 색상이 표시됩니다. **고급(전역 대 멤버)** 체계에서 전역 함수 및 변수는 클래스 멤버와 대조하도록 색상이 표시됩니다. 기본 모드는 **향상된**으로 표시됩니다.

![향상된 색 구성표의 스크린샷](media/color-scheme-enhanced.png)

어떤 테마 나 색 구성표가 활성화되어 있든 관계없이 개별 코드 요소에 대한 글꼴및 색상을 사용자 정의 할 수 있습니다. 이렇게 하려면 **도구** > **옵션** > **환경** > **글꼴 및 색상으로** 이동하거나 **Ctrl + Q를** 입력하고 "글꼴"을 검색합니다. C++ 옵션이 표시될 때까지 표시 항목 목록을 아래로 스크롤합니다.

![C ++ 글꼴 및 색상 옵션의 스크린 샷](media/tools-options-cpp-colors.png)

여기에 설정한 색상은 색 구성표에 정의된 값을 재정의합니다. 색 구성표의 기본 색상으로 돌아가려면 색상을 **기본값으로**다시 설정합니다.

## <a name="customize-the-toolbars"></a>도구 모음 사용자 지정

도구 모음은 메뉴 나 키보드 단축키를 사용하는 대신 한 번의 클릭으로 명령을 내리는 편리한 방법을 제공합니다. Visual Studio에는 표준 도구 모음 세트가 포함되어 있습니다. 표준 C++ 개발의 경우 가장 유용한 도구 모음은 표준, 텍스트 편집기, 빌드, 디버그, 소스 제어 및 파일 비교일 수 있습니다. Windows 개발의 경우 대화 상자 와 이미지 편집기는 대화 상자를 배치하고 아이콘을 편집하는 데 유용합니다.

도구 모음의 아이콘 위로 마우스를 가져가면 다음을 나타내는 명령을 확인할 수 있습니다.

![도구 모음 아이콘의 스크린샷, 마우스를 가져가기에서 사용할 수 있는 명령 정보의 예](media/toolbar-mouse-hover.png)

아래쪽 화살표를 선택하여 명령을 추가하거나 제거하거나 사용자 지정 도구 모음을 만들 수 있습니다. 도구 모음을 새 위치로 이동하려면 왼쪽의 점선 막대로 드래그합니다.

![아래쪽 화살표와 점선 막대가 강조 표시된 도구 모음의 스크린샷](media/toolbar-move-edit.png).

자세한 내용은 [Visual Studio의 메뉴 및 도구 모음 사용자 지정 방법을 참조하세요.](/visualstudio/ide/how-to-customize-menus-and-toolbars-in-visual-studio)

## <a name="show-or-hide-line-numbers"></a>선 번호 표시 또는 숨기기

편집기 창 왼쪽에 줄 번호가 표시되는지 여부를 지정할 수 있습니다. **옵션에서** **C/C++에서** **일반**을 선택합니다. **설정** 섹션에서 기본 설정에 따라 **줄 번호를**선택하거나 지웁니다.

![줄 번호가 강조 표시된 일반 옵션의 스크린샷](media/tools-options-line-numbers.png)

## <a name="create-keyboard-shortcuts"></a>바로 가기 키 만들기

Visual Studio의 많은 명령에는 *키보드 단축키,* Ctrl, Alt 및 Shift 키와 키 조합이 있습니다. 이러한 키보드 단축키를 수정하거나 Visual Studio에서 직접 새 키보드 단축키를 만들 수 있습니다. **도구** > **옵션** > **환경** > **키보드로** 이동(또는 **Ctrl + Q를** 입력하고 "바로 가기"를 검색). 자세한 내용은 [Visual Studio에서 키보드 단축키 식별 및 사용자 지정을](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)참조하세요.
