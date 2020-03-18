---
title: LIB 실행
description: Lib.exe에서 사용할 수 있는 명령줄 옵션에 대해 설명 합니다.
ms.date: 02/09/2020
f1_keywords:
- VC.Project.VCLibrarianTool.TargetMachine
- VC.Project.VCLibrarianTool.PrintProgress
- VC.Project.VCLibrarianTool.SuppressStartupBanner
helpviewer_keywords:
- -MACHINE target platform option
- command files, LIB
- MACHINE target platform option
- colon command files
- VERBOSE library manager option
- /NOLOGO library manager option
- dash option specifier
- /MACHINE target platform option
- forward slash option specifier
- -NOLOGO library manager option
- LIB [C++], running LIB
- -VERBOSE library manager option
- /VERBOSE library manager option
- command files
- NOLOGO library manager option
- slash (/)
- semicolon, command files
- / command files
ms.assetid: d54f5c81-7147-4b2c-a8db-68ce6eb1eabd
ms.openlocfilehash: 871b92809f38b4dcbf84de802b1ac9940ea6f1e9
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438945"
---
# <a name="running-lib"></a>LIB 실행

다양 한 명령줄 옵션을 사용 하 여 LIB를 제어할 수 있습니다.

## <a name="lib-command-line"></a>LIB 명령줄

LIB를 실행 하려면 `lib`명령을 입력 한 다음 LIB를 사용 하 고 있는 작업에 대 한 옵션 및 파일 이름을 입력 합니다. 또한 LIB는 명령 파일의 명령줄 입력을 허용 합니다 .이에 대해서는 다음 섹션에서 설명 합니다. LIB는 환경 변수를 사용 하지 않습니다.

## <a name="lib-command-files"></a>LIB 명령 파일

다음 구문을 사용 하 여 명령 파일의 LIB에 명령줄 인수를 전달할 수 있습니다.

> **LIB \@** <em>명령 파일</em>

파일 *명령 파일* 은 텍스트 파일입니다. At 기호 ( **\@** )와 파일 이름 사이에는 공백 또는 탭을 사용할 수 없습니다. *명령 파일* 이름에 기본 확장명이 없습니다. 모든 확장명을 포함 하 여 전체 파일 이름을 지정 합니다. 와일드 카드는 사용할 수 없습니다. 파일 이름으로 절대 경로 또는 상대 경로를 지정할 수 있습니다.

명령 파일에서 인수는 명령줄에서 사용할 수 있는 것 처럼 공백이 나 탭으로 구분할 수 있습니다. 또한 인수는 줄 바꿈 문자로 구분할 수 있습니다. 세미콜론 ( **;** )을 사용 하 여 주석을 표시 합니다. LIB는 세미콜론부터 줄 끝 까지의 모든 텍스트를 무시 합니다.

명령 파일에서 명령줄의 전체 또는 일부를 지정할 수 있으며 LIB 명령에 둘 이상의 명령 파일을 사용할 수 있습니다. LIB는 명령줄의 해당 위치에 지정 된 것 처럼 명령 파일 입력을 허용 합니다. 명령 파일은 중첩할 수 없습니다. LIB는 **/nologo** 옵션을 사용 하지 않는 한 명령 파일의 콘텐츠를 에코 합니다.

## <a name="using-lib-options"></a>LIB 옵션 사용

옵션은 대시 ( **-** ) 또는 슬래시 ( **/** ), 옵션 이름을 차례로 나타내는 옵션 지정자로 구성 됩니다. 옵션 이름은 약식 일 수 없습니다. 일부 옵션은 콜론 ( **:** ) 뒤에 지정 된 인수를 사용 합니다. 옵션 사양에는 공백이나 탭을 사용할 수 없습니다. 한 개 이상의 공백 또는 탭을 사용하여 명령줄에서 옵션 사양을 구분합니다. 옵션 이름과 해당 키워드 또는 파일 이름 인수는 대/소문자를 구분 하지 않지만 인수로 사용 되는 식별자는 대/소문자를 구분 합니다. LIB는 명령줄 및 명령 파일에 지정 된 순서로 옵션을 처리 합니다. 다른 인수를 사용 하 여 옵션을 반복 하면 처리할 마지막 항목을 우선적으로 사용 합니다.

다음 옵션은 LIB의 모든 모드에 적용 됩니다.

> **/ERRORREPORT** \[**없음** &#124; **메시지** &#124; **QUEUE** 큐 &#124; **송신**]

/ERRORREPORT 옵션은 사용 되지 않습니다. Windows Vista부터 오류 보고는 [WER (Windows 오류 보고)](/windows/win32/wer/windows-error-reporting) 설정에 의해 제어 됩니다.

> **/LINKREPRO:** _directory-경로_ \
> **/LINKREPROTARGET:** _파일 이름_

Microsoft에서 lib.exe 충돌 및 내부 오류를 진단 하는 데 도움이 되도록 [/LINKREPRO](linkrepro.md) 옵션을 사용할 수 있습니다. 이 옵션은 Microsoft에서 라이브러리 작업 중 발생 하는 문제를 재현할 수 있도록 하는 빌드 아티팩트 집합인 *링크 재현*을 생성 합니다. [/LINKREPROTARGET](linkreprotarget.md) 옵션은 **/LINKREPRO** 옵션과 함께 사용할 수 있습니다. Lib에서 지정 된 파일을 생성 하는 경우에만 링크 재현 아티팩트를 생성 합니다. 자세한 내용은 [Microsoft C++ 도구 집합의 문제를 보고 하는 방법](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)을 참조 하세요.

> **/LTCG**

"LTCG"는 *링크 타임 코드 생성*을 의미 합니다. 이 기능을 사용 하려면 컴파일러 ([cl.exe](compiler-options.md)), LIB 및 링커 ([링크](linker-options.md)) 간의 협력이 필요 합니다. 구성 요소가 자체적으로 수행할 수 있는 작업 외에도 코드를 최적화할 수 있습니다.

LIB에 대 한 **/ltcg** 옵션은 cl.exe의 입력에 [/gl](gl-whole-program-optimization.md) 컴파일러 옵션을 사용 하 여 생성 된 개체 파일이 포함 되도록 지정 합니다. LIB가 이러한 입력을 발견 하 고 **/ltcg** 가 지정 되지 않은 경우 정보 메시지를 표시 한 후/ltcg를 사용 하도록 설정 하 고 다시 시작 합니다. 즉,이 옵션을 명시적으로 설정할 필요는 없지만 빌드 성능을 향상 시킬 수 있습니다. 이는 LIB를 다시 시작할 필요가 없기 때문입니다.

빌드 프로세스에서 LIB의 출력을 링크로 보냅니다. 링크에는 별도의 **/ltcg** 옵션이 있습니다. 전체 프로그램 최적화 및 PGO (프로필 기반 최적화) 계측을 포함 하 여 다양 한 최적화를 수행 하는 데 사용 됩니다. 링크 옵션에 대 한 자세한 내용은 [/ltcg](ltcg-link-time-code-generation.md)를 참조 하십시오.

> **/MACHINE**

프로그램의 대상 플랫폼을 지정 합니다. 일반적으로 **/MACHINE**를 지정할 필요가 없습니다. LIB는 .obj 파일에서 컴퓨터 유형을 유추 합니다. 그러나 경우에 따라 LIB에서는 컴퓨터 유형을 확인 하 고 오류 메시지를 표시할 수 없습니다. 이러한 오류가 발생 하면 **/MACHINE**를 지정 합니다. **/Extract** 모드에서이 옵션은 확인을 위해서만 사용할 수 있습니다. 명령줄에서 `lib /?` 사용 하 여 사용 가능한 컴퓨터 종류를 확인 합니다.

> **/NOLOGO**

LIB 저작권 메시지 및 버전 번호의 표시를 억제 하 고 명령 파일의 에코를 방지 합니다.

> **/VERBOSE**

추가 되는 .obj 파일의 이름을 포함 하 여 세션 진행률에 대 한 세부 정보를 표시 합니다. 이 정보는 표준 출력으로 보내지며 파일로 리디렉션될 수 있습니다.

> **/WX**[ **: NO**]

경고를 오류로 처리 합니다. 자세한 내용은 [/WX(링커 경고를 오류로 처리)](wx-treat-linker-warnings-as-errors.md)를 참조하세요.

다른 옵션은 LIB의 특정 모드에만 적용 됩니다. 이러한 옵션은 각 모드에 대해 설명 하는 섹션에서 설명 합니다.

## <a name="see-also"></a>참고 항목

[LIB 참조](lib-reference.md)
