---
title: MIDL 컴파일러 속성 페이지
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 57498a01-fccc-4a0e-a036-6ff702f83126
f1_keywords:
- VC.Project.VCMidlTool.PreprocessorDefinitions
- VC.Project.VCMidlTool.AdditionalIncludeDirectories
- VC.Project.VCMidlTool.AdditionalMetadataDirectories
- VC.Project.VCMidlTool.IgnoreStandardIncludePath
- VC.Project.VCMidlTool.IgnoreStandardIncludePath
- VC.Project.VCMidlTool.MkTypLibCompatible
- VC.Project.VCMidlTool.WarningLevel
- VC.Project.VCMidlTool.WarnAsError
- VC.Project.VCMidlTool.SuppressStartupBanner
- VC.Project.VCMidlTool.DefaultCharType
- VC.Project.VCMidlTool.TargetEnvironment
- VC.Project.VCMidlTool.GenerateStublessProxies
- VC.Project.VCMidlTool.SuppressCompilerWarnings
- VC.Project.VCMidlTool.ApplicationConfigurationMode
- VC.Project.VCMidlTool.LocaleID
- VC.Project.VCMidlTool.MultiProcMIDL
- VC.Project.VCMidlTool.OutputDirectory
- VC.Project.VCMidlTool.WinmdFileName
- VC.Project.VCMidlTool.HeaderFileName
- VC.Project.VCMidlTool.DLLDataFileName
- VC.Project.VCMidlTool.InterfaceIdentifierFileName
- VC.Project.VCMidlTool.ProxyFileName
- VC.Project.VCMidlTool.GenerateTypeLibrary
- VC.Project.VCMidlTool.TypeLibraryName
- VC.Project.VCMidlTool.GenerateClientFiles
- VC.Project.VCMidlTool.GenerateServerFiles
- VC.Project.VCMidlTool.ClientStubFile
- VC.Project.VCMidlTool.ServerStubFile
- VC.Project.VCMidlTool.TypeLibFormat
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.PreendWithABINamepsace
- VC.Project.VCMidlTool.ValidateParameters
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.MinimumTargetSystem
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: d6833230baca892836c187799df7f0658aa16772
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336248"
---
# <a name="midl-property-pages"></a>MIDL 속성 페이지

MIDL 속성 페이지는 에서 항목 속성으로 사용할 수 있습니다. COM을 사용하는 C++ 프로젝트의 IDL 파일입니다. 이를 사용하여 [MIDL 컴파일러를](/windows/win32/midl/using-the-midl-compiler-2)구성합니다. C++ 프로젝트의 MIDL 옵션에 프로그래밍 방식으로 액세스하는 방법에 대한 자세한 내용은 <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool> 개체를 참조하세요. 일반 [MIDL 명령줄 구문도](/windows/win32/midl/general-midl-command-line-syntax)참조하십시오.

## <a name="general-property-page"></a>일반 속성 페이지

### <a name="preprocessor-definitions"></a>전처리기 정의

MIDL\[매크로(/D) 매크로를 포함하여 하나 이상의 정의를\]지정합니다.[/D](/windows/win32/midl/-d)

### <a name="additional-include-directories"></a>추가 포함 디렉터리

포함 경로(/I[/I](/windows/win32/midl/-i)\[경로)에\]추가할 하나 이상의 디렉터리를 지정합니다.

### <a name="additional-metadata-directories"></a>추가 메타데이터 디렉토리

Windows.Foundation.WinMD 파일(/metadata_dir[/metadata_dir](/windows/win32/midl/-metadata-dir) \[경로)를\]포함하는 디렉토리를 지정합니다.

### <a name="enable-windows-runtime"></a>Windows 런타임 사용

Windows 런타임 시맨틱을 사용하여 Windows 메타데이터[파일(/winrt)을](/windows/win32/midl/-winrt)만들 수 있습니다.

### <a name="ignore-standard-include-path"></a>표준 포함 경로 무시

현재 및 INCLUDE[디렉터리(/no_def_idir)를](/windows/win32/midl/-no-def-idir)무시합니다.

### <a name="mktyplib-compatible"></a>MkTypLib 호환

mktyplib.exe 버전 2.03[(/mktyplib203)과의](/windows/win32/midl/-mktyplib203)호환성을 강제합니다.

### <a name="warning-level"></a>경고 수준

MIDL 코드[오류(/W)의](/windows/win32/midl/-w)엄격성을 선택합니다.

**Choices**

- **1**
- **1**
- **2**
- **3**
- **4**

### <a name="treat-warnings-as-errors"></a>경고를 오류로 처리

MIDL이 모든 경고를[오류(/WX)로](/windows/win32/midl/-wx)처리하도록 합니다.

### <a name="suppress-startup-banner"></a>시작 배너 표시 안 함

시작 배너 및 정보[메시지(/nologo)의](/windows/win32/midl/-nologo)표시를 억제합니다.

### <a name="c-compiler-char-type"></a>C 컴파일러 차 유형

생성된 코드를 컴파일하는 데 사용할 C 컴파일러의 기본 문자 형식을 지정합니다. [(/char](/windows/win32/midl/-char) 서명됨|서명되지 않음|ascii7).

**Choices**

- **서명됨** - 서명됨
- **서명되지 않음** - 서명되지 않음
- **아시이** - 아시이

### <a name="target-environment"></a>대상 환경

대상[환경(/env](/windows/win32/midl/-env) arm32|win32|32|ia64|x64)을 지정합니다.

**Choices**

- **설정되지 않음** - Win32
- **마이크로소프트 윈도우 32 비트** - Win32
- **이타늄에 마이크로 소프트 윈도우 64 비트** - IA64
- **마이크로 소프트 윈도우 팔** - 팔
- **마이크로 소프트 윈도우 ARM64** - ARM64
- **마이크로 소프트 윈도우 64 비트 에 x64** - X64

### <a name="generate-stubless-proxies"></a>스텁리스 프록시 생성

개체[인터페이스(/Oicf,](/windows/win32/midl/-oi) [/Oif)에](/windows/win32/midl/-oi) 대한 확장 및 스텁없는 프록시를 사용하여 완전히 해석된 스텁을 생성합니다.

### <a name="suppress-compiler-warnings"></a>컴파일러 경고 표시 안 함

컴파일러 경고[메시지(/no_warn)를](/windows/win32/midl/-no-warn)표시하지 않습니다.

### <a name="application-configuration-mode"></a>응용 프로그램 구성 모드

IDL[파일(/app_config)에서](/windows/win32/midl/-app-config)선택한 ACF 특성을 허용합니다.

### <a name="locale-id"></a>로케일 ID

입력 파일, 파일 이름 및 디렉토리[경로(/lcid](/windows/win32/midl/-lcid) DECIMAL)에 대해 LCID를 지정합니다.

### <a name="multi-processor-compilation"></a>다중 프로세서 컴파일

동시에 여러 인스턴스를 실행합니다.

## <a name="output-property-page"></a>출력 속성 페이지

### <a name="output-directory"></a>출력 디렉터리

출력 디렉토리[(/out](/windows/win32/midl/-out) [디렉토리])를 지정합니다.

### <a name="metadata-file"></a>메타데이터 파일

생성된 메타데이터[파일(/winmd](/windows/win32/midl/-winmd) 파일 이름)의 이름을 지정합니다.

### <a name="header-file"></a>헤더 파일

생성된 헤더[파일(/h](/windows/win32/midl/-h) 파일 이름)의 이름을 지정합니다.

### <a name="dlldata-file"></a>DllData 파일

DLLDATA[파일(/dlldata](/windows/win32/midl/-dlldata) 파일 이름)의 이름을 지정합니다.

### <a name="iid-file"></a>IID 파일

인터페이스 식별자[파일(/iid](/windows/win32/midl/-iid) 파일 이름)의 이름을 지정합니다.

### <a name="proxy-file"></a>프록시 파일

프록시[파일(/proxy](/windows/win32/midl/-proxy) filename)의 이름을 지정합니다.

### <a name="generate-type-library"></a>유형 라이브러리 생성

형식 라이브러리를 생성하지 않도록 지정합니다(아니요의 경우[/notlb]).

### <a name="type-library"></a>형식 라이브러리

형식 라이브러리[파일(/tlb](/windows/win32/midl/-tlb) 파일 이름)의 이름을 지정합니다.

### <a name="generate-client-stub-files"></a>클라이언트 스텁 파일 생성

클라이언트 스텁 파일만[/client](/windows/win32/midl/-client) 생성합니다(/클라이언트[스텁|없음]).

**Choices**

- **스텁** - 스텁
- **없음** - 없음

### <a name="generate-server-stub-files"></a>서버 스텁 파일 생성

서버 스텁 파일만[생성합니다(/server](/windows/win32/midl/-server) [스텁|없음]).

**Choices**

- **스텁** - 스텁
- **없음** - 없음

### <a name="client-stub-file"></a>클라이언트 스텁 파일

클라이언트 스텁[파일(/cstub](/windows/win32/midl/-cstub) [파일])을 지정합니다.

### <a name="server-stub-file"></a>서버 스텁 파일

서버 스텁[파일(/sstub](/windows/win32/midl/-sstub) [파일])을 지정합니다.

### <a name="type-library-format"></a>형식 라이브러리 형식

형식 라이브러리 파일 형식([/oldtlb|/newtlb])을 지정합니다.

**Choices**

- **New 포맷** - 새 형식
- **이전 형식** - 이전 형식

## <a name="advanced-property-page"></a>고급 속성 페이지

### <a name="c-preprocess-options"></a>C 전처리 옵션

C 컴파일러[전처리기(/cpp_opt](/windows/win32/midl/-cpp-opt) 스위치)에 전달할 스위치를 지정합니다.

### <a name="undefine-preprocessor-definitions"></a>전처리기 정의 해제

MIDL[매크로(/U](/windows/win32/midl/-U) [매크로])를 포함하여 하나 이상의 정의미정을 지정합니다.

### <a name="enable-error-checking"></a>오류 검사 사용

오류 검사 옵션([/error all|none])을 선택합니다.

**Choices**

- **사용 하기 사용자 지정** - 모두
- **모두** - 모두
- **없음** - 없음

### <a name="check-allocations"></a>할당 확인

메모리 부족[오류(/오류 할당)를](/windows/win32/midl/-error) 확인합니다.

### <a name="check-bounds"></a>경계 확인

크기 대 전송 길이 사양[(/오류](/windows/win32/midl/-error) bounds_check)을 확인합니다.

### <a name="check-enum-range"></a>체크 열거형 범위

열거형 값이 허용[범위(/error](/windows/win32/midl/-error) 열거형)에 있는지 확인합니다.

### <a name="check-reference-pointers"></a>참조 포인터 확인

ref 포인터를[null(/error](/windows/win32/midl/-error) ref)이 아닌 지 확인합니다.

### <a name="check-stub-data"></a>스텁 데이터 확인

서버 측 스텁 데이터[유효성(/error](/windows/win32/midl/-error) stub_data)에 대한 추가 검사를 내보전합니다.

### <a name="prepend-with-abi-namespace"></a>'ABI' 네임스페이스로 준비

모든 형식에 'ABI' 네임스페이스를 준비합니다.  [(/ns_prefix)을](/windows/win32/midl/-ns-prefix)

### <a name="validate-parameters"></a>매개 변수 유효성 검사

매개 변수의 유효성을 검사하기 위해 추가 정보를 생성합니다(/강력한/no_robust).[/robust](/windows/win32/midl/-robust) | [/no_robust](/windows/win32/midl/-no-robust)

### <a name="struct-member-alignment"></a>구조체 부재 정렬

대상 시스템(/ZpN)에서 구조물의 보압 수준을 지정합니다.

**Choices**

- **설정되지 않음** - 설정되지 않음
- **1 바이트** - Zp1
- **2바이트** - Zp2
- **4 바이트** - Zp4
- **8 바이트** - Zp8

### <a name="redirect-output"></a>출력 리디렉션

화면에서[파일(/o](/windows/win32/midl/-o) 파일)으로 출력을 리디렉션합니다.

### <a name="minimum-target-system"></a>최소 대상 시스템

최소 대상[시스템(/대상 STRING)을](/windows/win32/midl/-target) 설정합니다.
