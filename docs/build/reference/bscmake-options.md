---
title: BSCMAKE 옵션
description: Microsoft BSCMAKE 유틸리티 명령줄 옵션에 대 한 참조입니다.
ms.date: 02/09/2020
f1_keywords:
- VC.Project.VCBscMakeTool.OutputFile
- VC.Project.VCBscMakeTool.SuppressStartupBanner
- VC.Project.VCBscMakeTool.PreserveSBR
helpviewer_keywords:
- /v BSCMAKE option
- Iu BSCMAKE option
- browse information files (.bsc), content
- /Er BSCMAKE option
- NOLOGO BSCMAKE option
- /s BSCMAKE option
- /Ei BSCMAKE option
- /o BSCMAKE option
- /NOLOGO BSCMAKE option
- /Iu BSCMAKE option
- s BSCMAKE option (/s)
- /Em BSCMAKE option
- Em BSCMAKE option
- Es BSCMAKE option
- files [C++], BSCMAKE
- Er BSCMAKE option
- BSCMAKE, options for controlling files
- controlling BSCMAKE options
- El BSCMAKE option
- /El BSCMAKE option
- /Es BSCMAKE option
- Ei BSCMAKE option
ms.assetid: fa2f1e06-c684-41cf-80dd-6a554835ebd2
ms.openlocfilehash: f0fd0e01d3325267ac175435aab65b5d0a9d47ea
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257795"
---
# <a name="bscmake-options"></a>BSCMAKE 옵션

> [!WARNING]
> BSCMAKE는 Visual Studio와 함께 설치되지만 더 이상 IDE에서 사용되지 않습니다. Visual Studio 2008 이후 찾아보기 및 기호 정보는 솔루션 폴더의 SQL Server *`.sdf`* 파일에 자동으로 저장 됩니다.

이 섹션에서는 BSCMAKE를 제어 하는 데 사용할 수 있는 옵션에 대해 설명 합니다. 몇 가지 옵션은 특정 정보를 제외 하거나 포함 하 여 찾아보기 정보 파일의 내용을 제어 합니다. 제외 옵션을 사용 하 여 BSCMAKE를 더 빠르게 실행 하 고 *`.bsc`* 파일 크기를 줄일 수 있습니다. 옵션 이름은 대/소문자를 구분 합니다 ( **/help** 및 **/nologo**제외).

**/Nologo** 와 **/O** 만 Visual Studio 개발 환경에서 사용할 수 있습니다.  프로젝트의 속성 페이지에 액세스 하는 방법에 대 한 자세한 내용은 [Visual Studio에서 컴파일러 및 빌드 속성 설정 C++ ](../working-with-project-properties.md) 을 참조 하세요.

**/Ei (** _파일 이름_... **)** \
찾아보기 정보 파일에서 지정 된 포함 파일의 콘텐츠를 제외 합니다. 여러 파일을 지정 하려면 이름을 공백으로 구분 하 고 목록을 괄호로 묶습니다. *파일 이름을*하나만 지정 하는 경우에는 괄호가 필요 하지 않습니다. **/Es 옵션과 함께** **/Ei** 를 사용 하 여 **/es**로 제외 되지 않은 파일을 제외 합니다.

**/El**\
로컬 기호를 제외 합니다. 기본값은 로컬 기호를 포함 하는 것입니다. 로컬 기호에 대 한 자세한 내용은 [.Sbr 파일 만들기](creating-an-dot-sbr-file.md)를 참조 하세요.

**/Em**\
매크로 본문에서 기호를 제외 합니다. 찾아보기 정보 파일에 매크로 이름만 포함 하려면 **/Em** 를 사용 합니다. 기본값은 매크로 이름과 매크로 확장 결과를 모두 포함 하는 것입니다.

**/Er (** _기호_... **)** \
찾아보기 정보 파일에서 지정 된 기호를 제외 합니다. 여러 기호 이름을 지정 하려면 이름을 공백으로 구분 하 고 목록을 괄호로 묶습니다. *기호*를 하나만 지정 하는 경우에는 괄호가 필요 하지 않습니다.

**/Es**\
절대 경로로 지정 된 모든 포함 파일을 제외 하거나 INCLUDE 환경 변수에 지정 된 절대 경로에서 찾을 수 있습니다. 일반적으로 이러한 파일은 찾아보기 정보 파일에 필요 하지 않을 수 있는 많은 정보를 포함 하는 시스템 포함 파일입니다. 이 옵션은 경로 없이 지정 된 파일이 나 상대 경로 또는 포함의 상대 경로에 있는 파일을 제외 하지 않습니다. **/Ei** 옵션을 **/es** 와 함께 사용 하 여 **/es** 로 제외 되지 않는 파일을 제외할 수 있습니다. 일부 파일만 제외 하려면 **/es**대신 **/Ei** 를 사용 하 고 제외할 파일을 나열 합니다.

**/errorreport:** [**없음** &#124; **프롬프트** &#124; **큐** &#124; **보내기**] \
이 옵션은 사용되지 않습니다. Windows Vista부터 오류 보고는 [WER (Windows 오류 보고)](/windows/win32/wer/windows-error-reporting) 설정에 의해 제어 됩니다.

**/Help**\
BSCMAKE 명령줄 구문에 대 한 요약 정보를 표시 합니다.

**/Iu**\
참조 되지 않은 기호를 포함 합니다. 기본적으로 BSCMAKE는 정의 되었지만 참조 되지 않은 기호를 기록 하지 않습니다. *`.sbr`* 파일이 압축 된 경우 컴파일러에서 참조 되지 않은 기호를 이미 제거 했으므로이 옵션은 해당 입력 파일에 영향을 주지 않습니다.

**/n**\
비증분 빌드를 강제로 실행 합니다. *`.bsc`* 파일이 있는지 여부와 관계 없이 찾아보기 정보 파일의 전체 빌드를 강제로 수행 하 고 *`.sbr`* 파일이 잘리지 않도록 하려면 **/n** 을 사용 합니다. [BSCMAKE에서 .Bsc 파일을 빌드하는 방법](how-bscmake-builds-a-dot-bsc-file.md)을 참조 하세요.

**/Nologo**\
BSCMAKE 저작권 메시지를 표시 하지 않습니다.

**/o** *파일 이름*\
찾아보기 정보 파일의 이름을 지정 합니다. 기본적으로 BSCMAKE는 찾아보기 정보 파일에 첫 번째 *`.sbr`* 파일의 기본 이름과 *`.bsc`* 확장명을 제공 합니다.

**/S (** _파일 이름_... **)** \
지정 된 포함 파일을 처음으로 발견할 때이 파일을 처리 하 고 그렇지 않은 경우 해당 파일을 제외 하도록 BSCMAKE에 지시 합니다. 이 옵션을 사용 하 여 파일 (예: *`.c`* 또는 *`.cpp`* 소스 파일에 대 한 헤더 또는 *`.h`* 파일)이 여러 소스 파일에 포함 되어 있지만 매번 전처리 지시문에 의해 변경 되지 않은 경우 처리 시간을 절약할 수 있습니다. 사용자가 만드는 찾아보기 정보 파일에 대 한 중요 하지 않은 방식으로 파일을 변경 하는 경우이 옵션을 사용 합니다. 여러 파일을 지정 하려면 이름을 공백으로 구분 하 고 목록을 괄호로 묶습니다. *파일 이름을*하나만 지정 하는 경우에는 괄호가 필요 하지 않습니다. 파일이 포함 될 때마다 제외 하려면 **/Ei** 또는 **/es** 옵션을 사용 합니다.

**/v**\
처리 되는 각 *`.sbr`* 파일의 이름과 전체 BSCMAKE 실행에 대 한 정보를 포함 하는 자세한 정보를 출력 합니다.

**/?** \
BSCMAKE 명령줄 구문에 대 한 간략 한 요약을 표시 합니다.

다음 명령줄은 3 개의 *`.sbr`* 파일에서 기본 .bsc의 전체 빌드를 수행 하도록 BSCMAKE에 지시 합니다. 또한 도구 상자의 중복 인스턴스를 제외 하도록 BSCMAKE에 지시 합니다. h:

```cmd
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr
```

## <a name="see-also"></a>참고 항목

[BSCMAKE 참조](bscmake-reference.md)
