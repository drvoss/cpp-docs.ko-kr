---
title: 미리 컴파일된 헤더 파일
ms.date: 10/24/2019
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
ms.openlocfilehash: 158301ec3caacced1663892071b17ef2b8f8e741
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328666"
---
# <a name="precompiled-header-files"></a>미리 컴파일된 헤더 파일

Visual Studio에서 새 프로젝트를 만들면 *pch.h라는* *미리 컴파일된 헤더 파일이* 프로젝트에 추가됩니다. (비주얼 스튜디오 2017 이전, 파일은 *stdafx.h라고했다.)* 파일의 목적은 빌드 프로세스를 가속화하는 것입니다. `<vector>`"와 같은 표준 라이브러리 헤더와 같은 모든 안정적인 헤더 파일은 여기에 포함되어야 합니다. 미리 컴파일된 헤더는 컴파일된 헤더 또는 해당 헤더에 포함된 모든 파일이 수정될 때만 컴파일됩니다. 프로젝트 소스 코드만 변경하면 빌드에서 미리 컴파일된 헤더에 대한 컴파일을 건너뜁니다.

미리 컴파일된 헤더의 컴파일러 옵션은 [/Y입니다.](reference/y-precompiled-headers.md) 프로젝트 속성 페이지에서 옵션은 **C/C++ > 미리 컴파일된 헤더에 > 구성 속성**아래에 있습니다. 미리 컴파일된 헤더를 사용하지 않도록 선택할 수 있으며 헤더 파일 이름과 출력 파일의 이름 및 경로를 지정할 수 있습니다.

## <a name="custom-precompiled-code"></a>사용자 지정 사전 컴파일된 코드

빌드하는 데 상당한 시간이 걸리는 대규모 프로젝트의 경우 미리 컴파일된 사용자 지정 파일을 만드는 것이 좋습니다. Microsoft C 및 C++ 컴파일러는 인라인 코드를 포함하여 모든 C 또는 C++ 코드를 미리 컴파일하는 옵션을 제공합니다. 이 성능 기능을 사용하여 안정적인 코드 본문을 컴파일하고, 코드의 컴파일된 상태를 파일에 저장하고, 후속 컴파일 중 미리 컴파일된 코드와 아직 개발 중인 코드를 결합할 수 있습니다. 안정적인 코드는 다시 컴파일할 필요가 없기 때문에 각 후속 컴파일 속도가 향상됩니다.

## <a name="when-to-precompile-source-code"></a>소스 코드를 미리 컴파일하는 시기

사전 컴파일된 코드는 개발 주기 동안 컴파일 시간을 줄이는 데 유용합니다.

- 항상 자주 변경되지 않는 큰 코드 본문을 사용합니다.

- 프로그램은 여러 모듈로 구성되며, 모두 포함 파일과 동일한 컴파일 옵션의 표준 집합을 사용합니다. 이 경우 포함 된 모든 파일을 미리 컴파일된 하나의 헤더로 미리 컴파일할 수 있습니다.

미리 컴파일된 헤더(PCH) 파일을 만드는 첫 번째 컴파일은 후속 컴파일보다 약간 더 오래 걸립니다. 후속 컴파일은 미리 컴파일된 코드를 포함하여 더 빠르게 진행할 수 있습니다.

C 및 C++ 프로그램을 모두 미리 컴파일할 수 있습니다. C++ 프로그래밍에서는 클래스 인터페이스 정보를 헤더 파일로 분리하는 것이 일반적입니다. 이러한 헤더 파일은 나중에 클래스를 사용하는 프로그램에 포함될 수 있습니다. 이러한 헤더를 미리 컴파일하면 프로그램이 컴파일하는 데 걸리는 시간을 줄일 수 있습니다.

> [!NOTE]
> 소스 파일당 미리 컴파일된 헤더(.pch) 파일은 하나만 사용할 수 있지만 프로젝트에서 여러 .pch 파일을 사용할 수 있습니다.

## <a name="two-choices-for-precompiling-code"></a>코드를 미리 컴파일하기 위한 두 가지 선택 사항

C 또는 C++ 코드를 미리 컴파일할 수 있습니다. 헤더 파일만 미리 컴파일하는 것으로 제한되지 않습니다.

사전 컴파일에는 계획이 필요하지만 간단한 헤더 파일 이외의 소스 코드를 미리 컴파일하는 경우 훨씬 빠른 컴파일이 제공됩니다.

소스 파일이 일반적인 헤더 파일 집합을 사용하지만 동일한 순서로 포함하지 않거나 사전 컴파일에 소스 코드를 포함하려는 경우 코드를 미리 컴파일합니다.

미리 컴파일된 헤더 옵션은 [/Yc(미리 컴파일된 헤더 파일 만들기)](reference/yc-create-precompiled-header-file.md) 및 [/Yu(미리 컴파일된 헤더 파일 사용)입니다.](reference/yu-use-precompiled-header-file.md) **/Yc를** 사용하여 미리 컴파일된 헤더를 만듭니다. 선택적 [hdrstop](../preprocessor/hdrstop.md) pragma와 함께 사용 하는 **경우/Yc** 헤더 파일 및 소스 코드를 미리 컴파일할 수 있습니다. 기존 컴파일에서 기존 미리 컴파일된 헤더를 사용하려면 **/Yu를** 선택합니다. **/Yc** 및 **/Yu** 옵션과 함께 **/Fp를** 사용하여 미리 컴파일된 헤더에 대한 대체 이름을 제공할 수도 있습니다.

**/Yu** 및 **/Yc에** 대한 컴파일러 옵션 참조 항목에서는 개발 환경에서 이 기능에 액세스하는 방법에 대해 설명합니다.

## <a name="precompiled-header-consistency-rules"></a>미리 컴파일된 헤더의 일관성 규칙

PCH 파일에는 시스템에 대한 정보뿐만 아니라 프로그램에 대한 메모리 주소 정보가 포함되어 있으므로 PCH 파일이 생성된 컴퓨터에서만 PCH 파일을 사용해야 합니다.

## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>미리 컴파일된 헤더의 파일별 사용에 대한 일관성 규칙

[/Yu](reference/yu-use-precompiled-header-file.md) 컴파일러 옵션을 사용하면 사용할 PCH 파일을 지정할 수 있습니다.

PCH 파일을 사용하는 경우 컴파일러는 일관성 있는 컴파일러 옵션, pragmas 등을 사용하는 컴파일 환경과 동일하게 가정하며, 이는 PCH 파일을 만들 때 달리 지정하지 않는 한 적용되었습니다. 컴파일러가 불일치를 감지하면 경고를 발행하고 가능한 경우 불일치를 식별합니다. 이러한 경고가 반드시 PCH 파일에 문제가 있음을 나타내는 것은 아닙니다. 그들은 단순히 가능한 충돌의 당신을 경고. PCH 파일에 대한 일관성 요구 사항은 다음 섹션에 설명되어 있습니다.

### <a name="compiler-option-consistency"></a>컴파일러 옵션 일관성

다음 컴파일러 옵션은 PCH 파일을 사용할 때 불일치 경고를 트리거할 수 있습니다.

- 사전 처리기(/D) 옵션을 사용하여 만든 매크로는 PCH 파일을 만든 컴파일과 현재 컴파일 간에 동일해야 합니다. 정의된 상수의 상태는 확인되지 않지만 이러한 변경이 발생할 경우 예기치 않은 결과가 발생할 수 있습니다.

- PCH 파일은 /E 및 /EP 옵션으로 작동하지 않습니다.

- PCH 파일을 사용하는 후속 컴파일이 이러한 옵션을 사용하기 전에 찾아보기 정보 생성(/FR) 옵션 또는 로컬 변수 제외(/Fr) 옵션을 사용하여 PCH 파일을 만들어야 합니다.

### <a name="c-70-compatible-z7"></a>C 7.0 호환(/Z7)

PCH 파일을 만들 때 이 옵션이 적용되는 경우 PCH 파일을 사용하는 후속 컴파일에서 디버깅 정보를 사용할 수 있습니다.

PCH 파일을 만들 때 C 7.0 호환(/Z7) 옵션이 적용되지 않으면 PCH 파일 및 /Z7을 사용하는 후속 컴파일에 경고가 트리거됩니다. 디버깅 정보는 현재 .obj 파일에 배치되며 PCH 파일에 정의된 로컬 기호는 디버거에서 사용할 수 없습니다.

### <a name="include-path-consistency"></a>경로 일관성 포함

PCH 파일에는 포함 경로가 만들 때 적용되었던 포함 경로에 대한 정보가 포함되어 있지 않습니다. PCH 파일을 사용하는 경우 컴파일러는 항상 현재 컴파일에 지정된 포함 경로를 사용합니다.

### <a name="source-file-consistency"></a>소스 파일 일관성

미리 컴파일된 헤더 파일(/Yu) 사용 옵션을 지정하면 컴파일러는 미리 컴파일될 소스 코드에 나타나는 모든 사전 처리자 지시문(pragmas 포함)을 무시합니다. 이러한 사전 처리기 지시문에 의해 지정된 컴파일은 미리 컴파일된 헤더 파일(/Yc) 만들기 옵션에 사용되는 컴파일과 같아야 합니다.

### <a name="pragma-consistency"></a>실용주의 일관성

PCH 파일을 만드는 동안 처리된 Pragmas는 일반적으로 PCH 파일이 나중에 사용되는 파일에 영향을 미칩니다. `comment` 및 `message` 실용골은 컴파일의 나머지 부분에 영향을 미치지 않습니다.

이러한 pragmas는 PCH 파일 내의 코드에만 영향을 미칩니다. 이후 PCH 파일을 사용하는 코드에는 영향을 주지 않습니다.

||||
|-|-|-|
|`comment`|`page`|`subtitle`|
|`linesize`|`pagesize`|`title`|
|`message`|`skip`||

이러한 pragma는 미리 컴파일된 헤더의 일부로 유지되며 미리 컴파일된 헤더를 사용하는 컴파일의 나머지 부분에 영향을 미칩니다.

||||
|-|-|-|
|`alloc_text`|`include_alias`|`pack`|
|`auto_inline`|`init_seg`|`pointers_to_members`|
|`check_stack`|`inline_depth`|`setlocale`|
|`code_seg`|`inline_recursion`|`vtordisp`|
|`data_seg`|`intrinsic`|`warning`|
|`function`|`optimize`||

## <a name="consistency-rules-for-yc-and-yu"></a>/Yc 및 /Yu에 대한 일관성 규칙

/Yc 또는 /Yu를 사용하여 만든 미리 컴파일된 헤더를 사용하는 경우 컴파일러는 현재 컴파일 환경을 PCH 파일을 만들 때 존재했던 컴파일 환경과 비교합니다. 현재 컴파일에 대해 이전 환경과 일치하는 환경(일관된 컴파일러 옵션, pragmas 등 사용)을 지정해야 합니다. 컴파일러가 불일치를 감지하면 경고를 발행하고 가능한 경우 불일치를 식별합니다. 이러한 경고가 반드시 PCH 파일에 문제가 있음을 나타내는 것은 아닙니다. 그들은 단순히 가능한 충돌의 당신을 경고. 다음 섹션에서는 미리 컴파일된 헤더에 대한 일관성 요구 사항을 설명합니다.

### <a name="compiler-option-consistency"></a>컴파일러 옵션 일관성

이 테이블에는 미리 컴파일된 헤더를 사용할 때 불일치 경고를 트리거할 수 있는 컴파일러 옵션이 나열됩니다.

|옵션|속성|규칙|
|------------|----------|----------|
|/D|상수 및 매크로 정의|미리 컴파일된 헤더를 만든 컴파일과 현재 컴파일 간에 동일해야 합니다. 정의된 상수의 상태는 확인되지 않지만 파일이 변경된 상수의 값에 종속되는 경우 예기치 않은 결과가 발생할 수 있습니다.|
|/E 또는 /EP|전프로세서 출력을 표준 출력으로 복사|미리 컴파일된 헤더는 /E 또는 /EP 옵션으로 작동하지 않습니다.|
|/Fr 또는 /FR|마이크로소프트 소스 브라우저 정보 생성|/Fr 및 /FR 옵션이 /Yu 옵션과 함께 유효하려면 미리 컴파일된 헤더가 만들어질 때도 적용되었어야 합니다. 미리 컴파일된 헤더를 사용하는 후속 컴파일도 소스 브라우저 정보를 생성합니다. 브라우저 정보는 단일 .sbr 파일에 배치되며 CodeView 정보와 동일한 방식으로 다른 파일에 의해 참조됩니다. 소스 브라우저 정보의 배치를 재정의할 수 없습니다.|
|/GA, /GD, /GE, /Gw 또는 /GW|윈도우 프로토콜 옵션|미리 컴파일된 헤더를 만든 컴파일과 현재 컴파일 간에 동일해야 합니다. 이러한 옵션이 다른 경우 경고 메시지가 나타납니다.|
|/Zi|전체 디버깅 정보 생성|미리 컴파일된 헤더를 만들 때 이 옵션이 적용되는 경우 사전 컴파일을 사용하는 후속 컴파일에서 해당 디버깅 정보를 사용할 수 있습니다. 미리 컴파일된 헤더를 만들 때 /Zi가 적용되지 않으면 사전 컴파일및 /Zi 옵션을 사용하는 후속 컴파일은 경고를 트리거합니다. 디버깅 정보는 현재 개체 파일에 배치되며 미리 컴파일된 헤더에 정의된 로컬 기호는 디버거에서 사용할 수 없습니다.|

> [!NOTE]
> 미리 컴파일된 헤더 기능은 C 및 C++ 소스 파일에서만 사용하기 위한 것입니다.

## <a name="using-precompiled-headers-in-a-project"></a>프로젝트에 미리 컴파일된 헤더 사용

이전 섹션에서는 미리 컴파일된 헤더의 개요를 제공합니다: /Yc 및 /Yu, /Fp 옵션 및 [hdrstop](../preprocessor/hdrstop.md) pragma. 이 섹션에서는 프로젝트에서 미리 컴파일된 수동 헤더 옵션을 사용하는 방법에 대해 설명합니다. 예제 makefile 및 관리하는 코드로 끝납니다.

프로젝트에서 수동 사전 컴파일 헤더 옵션을 사용하는 또 다른 방법은 Visual Studio의 기본 설정 중에 생성되는 MFC\SRC 디렉터리에 있는 makefiles 중 하나를 연구합니다. 이러한 makefiles는 이 섹션에 제시된 것과 유사한 접근 방식을 취하지만 NMAKE(Microsoft 프로그램 유지 관리 유틸리티) 매크로를 더 많이 사용하고 빌드 프로세스를 보다 잘 제어할 수 있습니다.

## <a name="pch-files-in-the-build-process"></a>빌드 프로세스의 PCH 파일

소프트웨어 프로젝트의 코드 베이스는 일반적으로 여러 C 또는 C++ 소스 파일, 개체 파일, 라이브러리 및 헤더 파일에 포함됩니다. 일반적으로 makefile은 이러한 요소의 조합을 실행 파일로 조정합니다. 다음 그림은 미리 컴파일된 헤더 파일을 사용하는 makefile의 구조를 보여 주며, 이 다이어그램의 NMAKE 매크로 이름과 파일 이름은 [PCH에 대한 샘플 확인 파일](#sample-makefile-for-pch) 및 [PCH에 대한 예제 코드에](#example-code-for-pch)있는 예제 코드의 이름과 일치합니다.

이 그림은 세 개의 다이어그램 장치를 사용하여 빌드 프로세스의 흐름을 보여 준다. 명명된 사각형은 각 파일 또는 매크로를 나타냅니다. 세 개의 매크로는 하나 이상의 파일을 나타냅니다. 그늘진 영역은 각 컴파일 또는 링크 작업을 나타냅니다. 화살표는 컴파일 또는 연결 프로세스 중에 결합되는 파일과 매크로를 표시합니다.

![미리 컴파일된 헤더 파일을 사용하는 메이크 파일의 구조](media/vc30ow1.gif "미리 컴파일된 헤더 파일을 사용하는 메이크 파일의 구조") <br/>
미리 컴파일된 헤더 파일을 사용하는 메이크파일의 구조

다이어그램의 맨 위에서 시작하여 STABLEHDRS와 BOUNDRY는 다시 컴파일할 필요가 없는 파일을 나열하는 NMAKE 매크로입니다. 이러한 파일은 명령 문자열에 의해 컴파일됩니다.

`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`

미리 컴파일된 헤더 파일(STABLE.pch)이 없거나 두 매크로에 나열된 파일을 변경하는 경우에만 가능합니다. 두 경우 모두 미리 컴파일된 헤더 파일에는 STABLEHDRS 매크로에 나열된 파일의 코드만 포함됩니다. BOUNDRY 매크로에서 미리 컴파일할 마지막 파일을 나열합니다.

이러한 매크로에 나열된 파일은 헤더 파일 또는 C 또는 C++ 소스 파일일 수 있습니다. (단일 PCH 파일은 C 및 C++ 모듈 모두에서 사용할 수 없습니다.) **hdrstop** 매크로를 사용하여 BOUNDRY 파일 내의 어느 지점에서 사전 컴파일을 중지할 수 있습니다. 자세한 내용은 [hdrstop을](../preprocessor/hdrstop.md) 참조하십시오.

다이어그램을 계속 아래로 계속, APPLIB.obj는 최종 응용 프로그램에 사용되는 지원 코드를 나타냅니다. UNSTABLEHDRS 매크로에 나열된 파일인 APPLIB.cpp에서 생성되며 미리 컴파일된 헤더에서 미리 컴파일된 코드입니다.

MYAPP.obj는 최종 응용 프로그램을 나타냅니다. MYAPP.cpp, UNSTABLEHDRS 매크로에 나열된 파일 및 미리 컴파일된 헤더에서 미리 컴파일된 코드에서 만들어집니다.

마지막으로 실행 파일(MYAPP) EXE)는 OBJS 매크로 (APPLIB.obj 및 MYAPP.obj)에 나열된 파일을 연결하여 생성됩니다.

## <a name="sample-makefile-for-pch"></a>PCH용 샘플 메이크파일

다음 메이크 파일은 매크로와 ! 경우! 다른! ENDIF 제어 흐름 명령 구조는 프로젝트에 대한 적응을 단순화합니다.

```NMAKE
# Makefile : Illustrates the effective use of precompiled
#            headers in a project
# Usage:     NMAKE option
# option:    DEBUG=[0|1]
#            (DEBUG not defined is equivalent to DEBUG=0)
#
OBJS = myapp.obj applib.obj
# List all stable header files in the STABLEHDRS macro.
STABLEHDRS = stable.h another.h
# List the final header file to be precompiled here:
BOUNDRY = stable.h
# List header files under development here:
UNSTABLEHDRS = unstable.h
# List all compiler options common to both debug and final
# versions of your code here:
CLFLAGS = /c /W3
# List all linker options common to both debug and final
# versions of your code here:
LINKFLAGS = /nologo
!IF "$(DEBUG)" == "1"
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi
LINKFLAGS = $(LINKFLAGS) /COD
LIBS      = slibce
!ELSE
CLFLAGS   = $(CLFLAGS) /Oselg /Gs
LINKFLAGS = $(LINKFLAGS)
LIBS      = slibce
!ENDIF
myapp.exe: $(OBJS)
    link $(LINKFLAGS) @<<
$(OBJS), myapp, NUL, $(LIBS), NUL;
<<
# Compile myapp
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp
# Compile applib
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp
# Compile headers
stable.pch : $(STABLEHDRS)
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp
```

이 메이크 파일은 [빌드 프로세스의 PCH 파일에서](#pch-files-in-the-build-process)"미리 컴파일된 헤더 파일을 사용하는 메이크 파일의 구조"그림에 표시된 STABLEHDRS, BOUNDRY 및 UNSTABLEHDRS 매크로외에도 이 메이크 파일은 CLFLAGS 매크로및 LINKFLAGS 매크로를 제공합니다. 이러한 매크로를 사용하여 디버그를 빌드하든 응용 프로그램의 실행 파일의 최종 버전을 작성하든 관계없이 적용되는 컴파일러 및 링커 옵션을 나열해야 합니다. 프로젝트에 필요한 라이브러리를 나열하는 LIBS 매크로도 있습니다.

메이크 파일도 사용! 경우! 다른! ENDIF는 NMAKE 명령줄에서 디버그 기호를 정의하는지 여부를 감지합니다.

```NMAKE
NMAKE DEBUG=[1|0]
```

이 기능을 사용하면 개발 중에 동일한 makefile을 사용할 수 있으며 프로그램의 최종 버전에는 최종 버전에 DEBUG=0을 사용할 수 있습니다. 다음 명령줄은 동일합니다.

```NMAKE
NMAKE
NMAKE DEBUG=0
```

메이크 파일에 대한 자세한 내용은 [NMAKE 참조](reference/nmake-reference.md)를 참조하십시오. 또한 [MSVC 컴파일러 옵션](reference/compiler-options.md) 및 [MSVC 링커 옵션을](reference/linker-options.md)참조하십시오.

## <a name="example-code-for-pch"></a>PCH에 대한 예제 코드

다음 소스 파일은 [빌드 프로세스의 PCH 파일에](#pch-files-in-the-build-process) 설명된 makefile 및 [PCH에 대한 샘플 메이크파일에](#sample-makefile-for-pch)사용됩니다. 주석에는 중요한 정보가 포함되어 있습니다.

```cpp
// ANOTHER.H : Contains the interface to code that is not
//             likely to change.
//
#ifndef __ANOTHER_H
#define __ANOTHER_H
#include<iostream>
void savemoretime( void );
#endif // __ANOTHER_H
```

```cpp
// STABLE.H : Contains the interface to code that is not likely
//            to change. List code that is likely to change
//            in the makefile's STABLEHDRS macro.
//
#ifndef __STABLE_H
#define __STABLE_H
#include<iostream>
void savetime( void );
#endif // __STABLE_H
```

```cpp
// UNSTABLE.H : Contains the interface to code that is
//              likely to change. As the code in a header
//              file becomes stable, remove the header file
//              from the makefile's UNSTABLEHDR macro and list
//              it in the STABLEHDRS macro.
//
#ifndef __UNSTABLE_H
#define __UNSTABLE_H
#include<iostream>
void notstable( void );
#endif // __UNSTABLE_H
```

```cpp
// APPLIB.CPP : This file contains the code that implements
//              the interface code declared in the header
//              files STABLE.H, ANOTHER.H, and UNSTABLE.H.
//
#include"another.h"
#include"stable.h"
#include"unstable.h"
using namespace std;
// The following code represents code that is deemed stable and
// not likely to change. The associated interface code is
// precompiled. In this example, the header files STABLE.H and
// ANOTHER.H are precompiled.
void savetime( void )
    { cout << "Why recompile stable code?\n"; }
void savemoretime( void )
    { cout << "Why, indeed?\n\n"; }
// The following code represents code that is still under
// development. The associated header file is not precompiled.
void notstable( void )
    { cout << "Unstable code requires"
            << " frequent recompilation.\n";
    }
```

```cpp
// MYAPP.CPP : Sample application
//             All precompiled code other than the file listed
//             in the makefile's BOUNDRY macro (stable.h in
//             this example) must be included before the file
//             listed in the BOUNDRY macro. Unstable code must
//             be included after the precompiled code.
//
#include"another.h"
#include"stable.h"
#include"unstable.h"
int main( void )
{
    savetime();
    savemoretime();
    notstable();
}
```

## <a name="see-also"></a>참고 항목

[C/C++ 빌드 참조](reference/c-cpp-building-reference.md)<br/>
[MSVC 컴파일러 옵션](reference/compiler-options.md)
