---
title: 미리 컴파일된 헤더 파일
ms.date: 10/24/2019
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- cl.exe compiler, precompiling code
- .pch files, creating
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
ms.openlocfilehash: 071839df431071a7d8921d1b445094f886ad38e2
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422849"
---
# <a name="precompiled-header-files"></a>미리 컴파일된 헤더 파일

Visual Studio에서 새 프로젝트를 만들 때 *.pch. h* 라는 *미리 컴파일된 헤더 파일이* 프로젝트에 추가 됩니다. Visual Studio 2017이 하 버전에서는 파일을 *stdafx.h*라고 합니다. 이 파일의 목적은 빌드 프로세스의 속도를 높이는 것입니다. `<vector>`와 같은 표준 라이브러리 헤더와 같은 안정적인 헤더 파일은 여기에 포함 되어야 합니다. 미리 컴파일된 헤더는이 헤더 또는 포함 된 모든 파일이 수정 된 경우에만 컴파일됩니다. 프로젝트 소스 코드를 변경 하는 경우에만 빌드에서 미리 컴파일된 헤더에 대 한 컴파일이 생략 됩니다. 

미리 컴파일된 헤더에 대 한 컴파일러 옵션은 [/y](reference/y-precompiled-headers.md)입니다. 프로젝트 속성 페이지에서 옵션은 **구성 속성 > C/C++ > 미리 컴파일된 헤더**에 있습니다. 미리 컴파일된 헤더를 사용 하지 않도록 선택 하 고 출력 파일의 이름 및 경로와 헤더 파일 이름을 지정할 수 있습니다. 

## <a name="custom-precompiled-code"></a>사용자 지정 미리 컴파일된 코드

빌드하는 데 시간이 오래 걸리는 큰 프로젝트의 경우 사용자 지정 미리 컴파일된 파일을 만드는 것이 좋습니다. Microsoft C 및 C++ 컴파일러는 인라인 코드를 포함하여 모든 C 또는 C++ 코드를 미리 컴파일하는 옵션을 제공합니다. 이 성능 기능을 사용하여 안정적인 코드 본문을 컴파일하고, 코드의 컴파일된 상태를 파일에 저장하고, 후속 컴파일 중 미리 컴파일된 코드와 아직 개발 중인 코드를 결합할 수 있습니다. 안정적인 코드는 다시 컴파일할 필요가 없기 때문에 각 후속 컴파일 속도가 향상됩니다.

## <a name="when-to-precompile-source-code"></a>소스 코드를 미리 컴파일하는 시기

미리 컴파일된 코드는 컴파일 시간을 단축 하기 위해 개발 주기 동안 유용 합니다. 특히 다음과 같은 경우에 유용 합니다.

- 항상 자주 변경 되지 않는 코드의 많은 본문을 사용 합니다.

- 프로그램은 여러 모듈로 구성 되며, 모든 모듈은 표준 포함 파일 집합과 동일한 컴파일 옵션을 사용 합니다. 이 경우 모든 포함 파일을 미리 컴파일된 하나의 헤더로 미리 볼 수 있습니다.

미리 컴파일된 헤더 (PCH) 파일을 만드는 첫 번째 컴파일에서는 다음 컴파일 보다 약간 더 오래 걸립니다. 이후 컴파일은 미리 컴파일된 코드를 포함 하 여 더 빠르게 진행할 수 있습니다.

C와 C++ 프로그램을 모두 미리 컴파일할 수 있습니다. C++ 프로그래밍에서는 클래스 인터페이스 정보를 헤더 파일로 분리 하는 것이 일반적입니다. 이러한 헤더 파일은 나중에 클래스를 사용 하는 프로그램에 포함 될 수 있습니다. 이러한 헤더를 미리 컴파일하면 프로그램을 컴파일하는 데 걸리는 시간을 줄일 수 있습니다.

> [!NOTE]
> 원본 파일당 미리 컴파일된 헤더 (.pch) 파일을 하나만 사용할 수 있지만 프로젝트에서 여러 .pch 파일을 사용할 수 있습니다.

## <a name="two-choices-for-precompiling-code"></a>코드를 미리 컴파일하기 위한 두 가지 선택 사항

모든 C 또는 C++ 코드를 미리 컴파일할 수 있습니다. 헤더 파일만 미리 컴파일하는 것으로 제한 되지 않습니다.

미리 컴파일하면 계획이 필요 하지만 단순한 헤더 파일 이외의 소스 코드를 미리 컴파일하는 경우 훨씬 더 빠른 컴파일을 제공 합니다.

소스 파일에 헤더 파일의 공통 집합을 사용 하지만 동일한 순서로 포함 하지 않거나 미리 컴파일에 소스 코드를 포함 하려는 경우 코드를 미리 컴파일합니다.

미리 컴파일된 헤더 옵션은 [/yc (미리 컴파일된 헤더 파일 만들기)](reference/yc-create-precompiled-header-file.md) 및 [/Yu (미리 컴파일된 헤더 파일 사용)](reference/yu-use-precompiled-header-file.md)입니다. **/Yc** 를 사용 하 여 미리 컴파일된 헤더를 만듭니다. 선택적 [hdrstop](../preprocessor/hdrstop.md) pragma와 함께 사용 하는 경우에는 **/yc** 를 사용 하 여 헤더 파일과 소스 코드를 모두 미리 컴파일할 수 있습니다. 기존 컴파일에서 미리 컴파일된 기존 헤더를 사용 하려면 **/yu** 를 선택 합니다. 또한 **/fp** 를 **/yc** 및 **/yu** 옵션과 함께 사용 하 여 미리 컴파일된 헤더에 대 한 대체 이름을 제공할 수도 있습니다.

**/Yu** 및 **/yc** 에 대 한 컴파일러 옵션 참조 항목에서는 개발 환경에서이 기능에 액세스 하는 방법에 대해 설명 합니다.

## <a name="precompiled-header-consistency-rules"></a>미리 컴파일된 헤더의 일관성 규칙

PCH 파일은 컴퓨터 환경 및 프로그램에 대 한 메모리 주소 정보에 대 한 정보를 포함 하기 때문에 생성 된 컴퓨터 에서만 PCH 파일을 사용 해야 합니다.

## <a name="consistency-rules-for-per-file-use-of-precompiled-headers"></a>미리 컴파일된 헤더의 파일별 사용에 대한 일관성 규칙

[/Yu](reference/yu-use-precompiled-header-file.md) 컴파일러 옵션을 사용 하면 사용할 PCH 파일을 지정할 수 있습니다.

PCH 파일을 사용 하는 경우 컴파일러는 동일한 컴파일 환경을 가정 합니다. 즉, 일치 하는 컴파일러 옵션, pragma 등을 사용 하는 것과 달리 지정 하지 않는 한 PCH 파일을 만들 때 적용 된 것입니다. 컴파일러가 불일치를 감지 하면 경고를 발생 하 고 가능한 경우 불일치를 식별 합니다. 이러한 경고는 PCH 파일에 문제가 있음을 나타내는 것은 아닙니다. 가능한 충돌을 경고 합니다. PCH 파일의 일관성 요구 사항은 다음 섹션에 설명 되어 있습니다.

### <a name="compiler-option-consistency"></a>컴파일러 옵션 일관성

다음 컴파일러 옵션은 PCH 파일을 사용할 때 불일치 경고를 트리거할 수 있습니다.

- 전처리기 (/D) 옵션을 사용 하 여 만든 매크로는 PCH 파일을 만든 컴파일과 현재 컴파일 사이에서 동일 해야 합니다. 정의 된 상수의 상태를 확인 하지는 않지만 이러한 변경이 발생 하면 예측할 수 없는 결과가 발생할 수 있습니다.

- PCH 파일은/E 및/EP 옵션과 함께 사용할 수 없습니다.

- Pch 파일을 사용 하는 후속 컴파일에서 이러한 옵션을 사용할 수 있으려면 찾아보기 정보 생성 (/FR) 옵션을 사용 하거나 로컬 변수 제외 (/Fr) 옵션을 사용 하 여 PCH 파일을 만들어야 합니다.

### <a name="c-70-compatible-z7"></a>C 7.0 호환 (/Z7)

PCH 파일을 만들 때이 옵션이 적용 되는 경우 PCH 파일을 사용 하는 후속 컴파일에서 디버깅 정보를 사용할 수 있습니다.

PCH 파일을 만들 때 C 7.0 호환 (/Z7) 옵션이 적용 되지 않는 경우 PCH 파일 및/Z7을 사용 하는 후속 컴파일에서 경고를 트리거합니다. 디버깅 정보는 현재 .obj 파일에 저장 되 고 PCH 파일에 정의 된 로컬 기호는 디버거에 사용할 수 없습니다.

### <a name="include-path-consistency"></a>경로 일관성 포함

PCH 파일은 만들어질 때 적용 된 포함 경로에 대 한 정보를 포함 하지 않습니다. PCH 파일을 사용 하는 경우 컴파일러는 항상 현재 컴파일에 지정 된 포함 경로를 사용 합니다.

### <a name="source-file-consistency"></a>소스 파일 일관성

/Yu (미리 컴파일된 헤더 파일) 사용 옵션을 지정 하면 컴파일러가 미리 컴파일하는 소스 코드에 표시 되는 모든 전처리기 지시문 (pragma 포함)을 무시 합니다. 이러한 전처리기 지시문에 의해 지정 된 컴파일은 미리 컴파일된 헤더 파일 (/Yc) 만들기 옵션에 사용 되는 컴파일과 동일 해야 합니다.

### <a name="pragma-consistency"></a>Pragma 일관성

PCH 파일을 만드는 동안 처리 된 pragma는 일반적으로 PCH 파일이 사용 되는 파일에 영향을 줍니다. `comment` 및 `message` pragma는 컴파일의 나머지 부분에 영향을 주지 않습니다.

이러한 pragma는 PCH 파일 내에 있는 코드에만 영향을 줍니다. 이후에 PCH 파일을 사용 하는 코드에는 영향을 주지 않습니다.

||||
|-|-|-|
|`comment`|`page`|`subtitle`|
|`linesize`|`pagesize`|`title`|
|`message`|`skip`||

이러한 pragma는 미리 컴파일된 헤더의 일부로 유지 되며 미리 컴파일된 헤더를 사용 하는 컴파일의 나머지 부분에 영향을 줍니다.

||||
|-|-|-|
|`alloc_text`|`include_alias`|`pack`|
|`auto_inline`|`init_seg`|`pointers_to_members`|
|`check_stack`|`inline_depth`|`setlocale`|
|`code_seg`|`inline_recursion`|`vtordisp`|
|`data_seg`|`intrinsic`|`warning`|
|`function`|`optimize`||

## <a name="consistency-rules-for-yc-and-yu"></a>/Yc 및 /Yu에 대한 일관성 규칙

/Yc 또는/Yu를 사용 하 여 만든 미리 컴파일된 헤더를 사용 하는 경우 컴파일러는 현재 컴파일 환경을 PCH 파일을 만들 때 있었던 것과 비교 합니다. 현재 컴파일에 대해 일치 하는 컴파일러 옵션, pragma 등을 사용 하 여 이전 이름과 일관 된 환경을 지정 해야 합니다. 컴파일러가 불일치를 감지 하면 경고를 발생 하 고 가능한 경우 불일치를 식별 합니다. 이러한 경고가 반드시 PCH 파일에 문제가 있음을 나타내는 것은 아닙니다. 가능한 충돌을 경고 합니다. 다음 섹션에서는 미리 컴파일된 헤더의 일관성 요구 사항에 대해 설명 합니다.

### <a name="compiler-option-consistency"></a>컴파일러 옵션 일관성

다음 표에서는 미리 컴파일된 헤더를 사용할 때 불일치 경고를 트리거할 수 있는 컴파일러 옵션을 보여 줍니다.

|옵션|속성|규칙|
|------------|----------|----------|
|/D|상수 및 매크로 정의|는 미리 컴파일된 헤더를 만든 컴파일과 현재 컴파일 사이에서 동일 해야 합니다. 정의 된 상수의 상태는 선택 되지 않지만 파일이 변경 된 상수의 값에 종속 되는 경우 예측할 수 없는 결과가 발생할 수 있습니다.|
|/E 또는/EP|전처리기 출력을 표준 출력에 복사 합니다.|미리 컴파일된 헤더는/E 또는/EP 옵션과 함께 사용할 수 없습니다.|
|/Fr 또는/FR|Microsoft 원본 브라우저 정보 생성|/Fr 및/FR 옵션이/Yu 옵션에 유효 하려면 미리 컴파일된 헤더를 만들 때에도 적용 되어야 합니다. 미리 컴파일된 헤더를 사용 하는 후속 컴파일에서도 소스 브라우저 정보를 생성 합니다. 브라우저 정보는 단일 .sbr 파일에 저장 되며 다른 파일에서 CodeView 정보와 동일한 방식으로 참조 됩니다. 소스 브라우저 정보의 배치를 재정의할 수 없습니다.|
|/GA,/GD,/GE,/Gw 또는/GW|Windows 프로토콜 옵션|는 미리 컴파일된 헤더를 만든 컴파일과 현재 컴파일 사이에서 동일 해야 합니다. 이러한 옵션이 다른 경우 경고 메시지를 생성 합니다.|
|/ZI|전체 디버깅 정보 생성|미리 컴파일된 헤더를 만들 때이 옵션이 적용 되 면 미리 컴파일을 사용 하는 후속 컴파일에서 해당 디버깅 정보를 사용할 수 있습니다. 미리 컴파일된 헤더를 만들 때/Zi를 적용 하지 않으면 미리 컴파일 및/Zi 옵션을 사용 하는 후속 컴파일에서 경고를 트리거합니다. 디버깅 정보는 현재 개체 파일에 배치 되 고 미리 컴파일된 헤더에 정의 된 로컬 기호는 디버거에 사용할 수 없습니다.|

> [!NOTE]
>  미리 컴파일된 헤더 기능은 C 및 C++ 소스 파일에만 사용할 수 있습니다.

## <a name="using-precompiled-headers-in-a-project"></a>프로젝트에 미리 컴파일된 헤더 사용

이전 섹션에서는 미리 컴파일된 헤더의 개요 인/Yc와/Yu,/Fp 옵션 및 [hdrstop](../preprocessor/hdrstop.md) pragma를 제공 합니다. 이 단원에서는 프로젝트에서 수동 미리 컴파일된 헤더 옵션을 사용 하는 방법에 대해 설명 합니다. 예제 메이크파일 및 관리 되는 코드로 끝납니다.

프로젝트에서 수동 미리 컴파일된 헤더 옵션을 사용 하는 다른 방법에 대해서는 Visual Studio의 기본 설정 중에 생성 된 MFC\SRC 디렉터리에 있는 메이크파일 중 하나를 검토 합니다. 이러한 메이크파일은이 단원에 나와 있는 것과 유사한 접근 방식을 사용 하지만, NMAKE (Microsoft Program Maintenance Utility) 매크로를 더 효율적으로 사용 하 고 빌드 프로세스를 더 효율적으로 제어할 수 있습니다.

## <a name="pch-files-in-the-build-process"></a>빌드 프로세스의 PCH 파일

소프트웨어 프로젝트의 코드 베이스는 일반적으로 여러 C 또는 C++ 소스 파일, 개체 파일, 라이브러리 및 헤더 파일에 포함 되어 있습니다. 일반적으로 메이크파일은 이러한 요소의 조합을 실행 파일로 조정 합니다. 다음 그림에는 미리 컴파일된 헤더 파일을 사용 하는 메이크파일의 구조가 나와 있습니다. 이 다이어그램의 NMAKE 매크로 이름과 파일 이름은 pch 용 [샘플 메이크파일](#sample-makefile-for-pch) 및 [Pch의 예제 코드](#example-code-for-pch)에 있는 예제 코드와 일치 합니다.

이 그림에서는 세 개의 다이어그램 장치를 사용 하 여 빌드 프로세스의 흐름을 보여 줍니다. 명명 된 사각형은 각 파일이 나 매크로를 나타냅니다. 세 매크로는 하나 이상의 파일을 나타냅니다. 음영 처리 된 영역은 각 컴파일 또는 링크 동작을 나타냅니다. 화살표는 컴파일 또는 연결 프로세스 중에 결합 된 파일 및 매크로를 보여 줍니다.

![미리 컴파일된 헤더 파일을 사용 하는 메이크파일의 구조](media/vc30ow1.gif "미리 컴파일된 헤더 파일을 사용 하는 메이크파일의 구조") <br/>
미리 컴파일된 헤더 파일을 사용하는 메이크파일의 구조

다이어그램의 위쪽에서 시작 하 여 STABLEHDRS와 BOUNDRY는 모두 재컴파일을 필요로 할 가능성이 없는 파일을 나열 하는 NMAKE 매크로입니다. 이러한 파일은 명령 문자열에 의해 컴파일됩니다.

`CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp`

미리 컴파일된 헤더 파일 (안정적인 .pch)이 없거나 두 매크로에 나열 된 파일을 변경 하는 경우에만 가능 합니다. 두 경우 모두 미리 컴파일된 헤더 파일에는 STABLEHDRS 매크로에 나열 된 파일의 코드만 포함 됩니다. BOUNDRY 매크로에서 미리 컴파일된 마지막 파일을 나열 합니다.

이러한 매크로에 나열 되는 파일은 헤더 파일 또는 C 또는 C++ 소스 파일 일 수 있습니다. 단일 PCH 파일은 C 및 C++ 모듈과 함께 사용할 수 없습니다. **Hdrstop** 매크로를 사용 하 여 BOUNDRY 파일 내의 특정 지점에서 미리 컴파일을 중지할 수 있습니다. 자세한 내용은 [hdrstop](../preprocessor/hdrstop.md) 을 참조 하세요.

다이어그램을 계속 진행 하면 APPLIB은 최종 응용 프로그램에서 사용 되는 지원 코드를 나타냅니다. 이 파일은 APPLIB에서 생성 되며, UNSTABLEHDRS 매크로에 나열 된 파일 및 미리 컴파일된 헤더의 미리 컴파일된 코드입니다.

MYAPP .obj는 최종 응용 프로그램을 나타냅니다. 이 파일은 MYAPP .cpp, UNSTABLEHDRS 매크로에 나열 된 파일 및 미리 컴파일된 헤더의 미리 컴파일된 코드에서 생성 됩니다.

마지막으로 실행 파일 (MYAPP. EXE)는 OBJ 매크로에 나열 된 파일 (APPLIB 및 MYAPP.EXE)을 연결 하 여 만듭니다.

## <a name="sample-makefile-for-pch"></a>PCH용 샘플 메이크파일

다음 메이크파일에서는 매크로와을 사용 합니다. 이면이 고, 그렇지 않으면입니다. 그렇지 않으면! ENDIF는 프로젝트에 대 한 적응을 간소화 하기 위한 제어 흐름 제어 명령 구조입니다.

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

[빌드 프로세스의 PCH 파일](#pch-files-in-the-build-process)에서 그림 "미리 컴파일된 헤더 파일을 사용 하는 메이크파일의 구조"에 표시 된 STABLEHDRS, BOUNDRY 및 unstablehdrs 매크로 외에이 메이크파일의는 clflags 매크로와 linkflags 매크로를 제공 합니다. 이러한 매크로를 사용 하 여 응용 프로그램 실행 파일의 디버그 또는 최종 버전을 빌드 하는지 여부에 적용 되는 컴파일러 및 링커 옵션을 나열 해야 합니다. 프로젝트에 필요한 라이브러리를 나열 하는 라이브러리 매크로도 있습니다.

메이크파일에도!를 사용 합니다. 이면이 고, 그렇지 않으면입니다. 그렇지 않으면! ENDIF는 NMAKE 명령줄에서 디버그 기호를 정의 하는지 여부를 검색 합니다.

```NMAKE
NMAKE DEBUG=[1|0]
```

이 기능을 사용 하면 개발 중에 동일한 메이크파일을 사용 하 고, 프로그램의 최종 버전을 사용할 수 있습니다. 최종 버전에는 DEBUG = 0을 사용 합니다. 다음 명령줄은 동일 합니다.

```NMAKE
NMAKE
NMAKE DEBUG=0
```

메이크파일에 대 한 자세한 내용은 [NMAKE 참조](reference/nmake-reference.md)를 참조 하세요. 또한 [MSVC 컴파일러 옵션](reference/compiler-options.md) 및 [MSVC 링커 옵션](reference/linker-options.md)을 참조 하세요.

## <a name="example-code-for-pch"></a>PCH에 대한 예제 코드

다음 소스 파일은 [빌드 프로세스의 Pch 파일](#pch-files-in-the-build-process) 에 설명 된 메이크파일에 사용 되며 [Pch 용 샘플 메이크파일](#sample-makefile-for-pch)에 사용 됩니다. 주석에는 중요 한 정보가 포함 되어 있습니다.

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
