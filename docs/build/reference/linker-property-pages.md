---
title: 링커 속성 페이지
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
ms.openlocfilehash: 2f2068c6c51fc6bf4e4104213e946e243fc6df2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336583"
---
# <a name="linker-property-pages"></a>링커 속성 페이지

다음 속성은 **프로젝트** > **속성** > **구성 속성** > **링커**에서 찾을 수 있습니다. 링커에 대한 자세한 내용은 [CL이 링커](cl-invokes-the-linker.md) 및 [링커 옵션을](linker-options.md)호출합니다.

## <a name="general-property-page"></a>일반 속성 페이지

### <a name="output-file"></a>출력 파일

[/OUT](out-output-file-name.md) 옵션은 링커가 만드는 프로그램의 기본 이름과 위치를 재정의합니다.

### <a name="show-progress"></a>진행률 표시

링커 진행률 메시지 인쇄

**Choices**

- **설정되지 않음** - 자세한 내용은 없습니다.
- **모든 진행률 메시지 표시** - 모든 진행률 메시지를 표시합니다.
- **검색된 라이브러리의 경우** - 검색된 라이브러리만 나타내는 진행률 메시지를 표시합니다.
- **최적화된 연결 중 COMDAT 폴딩 정보** - 최적화된 연결 중에 COMDAT 폴딩에 대한 정보를 표시합니다.
- **최적화된 연결 중에 제거된 데이터에 대해** - 최적화된 연결 중에 제거된 함수 및 데이터에 대한 정보를 표시합니다.
- **SEH와 호환되지 않는 모듈 정보** - 안전 예외 처리와 호환되지 않는 모듈에 대한 정보를 표시합니다.
- **관리 코드와 관련된 링커 활동 정보** - 관리 코드와 관련된 링커 활동에 대한 정보를 표시합니다.

### <a name="version"></a>버전

[/VERSION](version-version-information.md) 옵션은 링커에게 .exe 또는 .dll 파일의 헤더에 버전 번호를 넣도록 지시합니다. DUMPBIN /HEADERS를 사용하여 선택적 헤더 값의 이미지 버전 필드를 확인하여 **/VERSION**의 효과를 확인합니다.

### <a name="enable-incremental-linking"></a>증분 링크 사용

증분 연결을 활성화합니다. [(/증분,](incremental-link-incrementally.md)/증분:아니오)

### <a name="suppress-startup-banner"></a>시작 배너 표시 안 함

[/NOLOGO](nologo-suppress-startup-banner-linker.md) 옵션은 저작권 메시지와 버전 번호를 표시하지 않습니다.

### <a name="ignore-import-library"></a>가져오기 라이브러리 무시

이 속성은 이 빌드에서 생성된 .lib 출력을 종속 프로젝트에 연결하지 않도록 링커에 지시합니다. 이를 통해 프로젝트 시스템에서 빌드할 때 .lib 파일을 생성하지 않는 .dll 파일을 처리할 수 있습니다. 프로젝트가 DLL을 생성하는 다른 프로젝트에 종속되는 경우 프로젝트 시스템은 해당 하위 프로젝트에서 생성한 .lib 파일을 자동으로 연결합니다. 이러한 DLL에는 의미 있는 내보내기가 없기 때문에 COM DLL 또는 리소스 전용 DLL을 생성하는 프로젝트에서 이 속성이 필요하지 않을 수 있습니다. DLL에 내보내기가 없는 경우 링커는 .lib 파일을 생성하지 않습니다. 내보내기 .lib 파일이 없고 프로젝트 시스템에서 링커에게 누락된 DLL과 연결하도록 알려주면 링크가 실패합니다. 이 문제를 해결하려면 **가져오기 라이브러리 무시** 속성을 사용하세요. **예로**설정하면 프로젝트 시스템은 .lib 파일의 유무를 무시하고 이 프로젝트에 의존하는 모든 프로젝트가 존재하지 않는 .lib 파일과 연결되지 않도록 합니다.

프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>을 참조하세요.

### <a name="register-output"></a>출력 등록

.dll 프로젝트에서만 유효한 빌드 출력에서 `regsvr32.exe /s $(TargetPath)`를 실행합니다. .exe 프로젝트의 경우 이 속성은 무시됩니다. .exe 출력을 등록하려면 구성에 postbuild 이벤트를 설정하여, 등록된 .exe 파일에 항상 필요한 사용자 지정 등록을 수행합니다.

프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>을 참조하세요.

### <a name="per-user-redirection"></a>사용자별 리디렉션

Visual Studio의 등록은 일반적으로 HKEY_CLASSES_ROOT(HKCR)에서 수행되었습니다. Windows Vista 이상의 운영 체제에서 HKCR에 액세스하려면 Visual Studio를 승격된 모드로 실행해야 합니다. 개발자는 항상 상승 된 모드에서 실행 하려는 되지 않습니다 하지만 여전히 등록 작업 해야 합니다. 사용자별 리디렉션을 사용하면 상승 된 모드에서 실행하지 않고도 등록 할 수 있습니다.

사용자별 리디렉션은 HKCR에 대한 모든 쓰기가 HKEY\_CURRENT\_USER(HKCU)로 리디렉션되도록 합니다. 사용자별 리디렉션이 해제되어 있는 경우 프로그램이 HKCR에 쓰려고 할 때 [프로젝트 빌드 오류 PRJ0050](../../error-messages/tool-errors/project-build-error-prj0050.md)이 발생할 수 있습니다.

### <a name="additional-library-directories"></a>추가 라이브러리 디렉터리

사용자가 환경의 라이브러리 경로를 재정의할 수 있습니다. [(/LIBPATH](libpath-additional-libpath.md):폴더)

### <a name="link-library-dependencies"></a>라이브러리 종속성 링크

종속 프로젝트에서 생성한 .lib 파일을 연결할지 여부를 지정합니다. 일반적으로 .lib 파일에 연결하려고 하지만 특정 DLL의 경우는 그렇지 않을 수 있습니다.

파일 이름과 상대 경로를 제공하여 .obj 파일을 지정할 수도 있습니다(예: "..\\..\MyLibProject\MyObjFile.obj"). .obj 파일의 소스 코드가 미리 컴파일된 헤더(예: pch.h)#includes 경우 pch.obj 파일이 MyObjFile.obj와 동일한 폴더에 있습니다. 또한 pch.obj를 추가 종속성으로 추가해야 합니다.

### <a name="use-library-dependency-inputs"></a>라이브러리 종속성 입력 사용

프로젝트 종속성의 라이브러리 출력에 연결할 때 라이브러리 파일 자체가 아닌 라이브러리 도구에 입력을 사용할지 여부를 지정합니다. 대규모 프로젝트에서 종속 프로젝트가 .lib 파일을 생성하면 증분 연결은 사용할 수 없습니다. .lib 파일을 생성하는 많은 종속 프로젝트가 있는 경우 애플리케이션을 빌드하는 데 오랜 시간이 걸릴 수 있습니다. 이 속성이 **예로**설정되면 종속 프로젝트에서 생성된 .obj 파일에 대한 프로젝트 시스템이 연결되므로 증분 연결이 가능합니다.

**일반** 링커 속성 페이지에 액세스하는 방법에 대한 자세한 내용은 [Visual Studio에서 C++ 컴파일러 설정 및 빌드 속성을](../working-with-project-properties.md)참조하십시오.

### <a name="link-status"></a>연결 상태

링커에 링크의 완료 된 비율을 표시 하는 진행률 표시기를 표시 해야 하는지 여부를 지정 합니다. 기본값은 이 상태 정보를 표시하지 않는 것입니다. [(/LTCG](ltcg-link-time-code-generation.md):STATUS| LTCG:상태 없음)

### <a name="prevent-dll-binding"></a>DLL 바인딩 방지

[/ALLOWBIND](allowbind-prevent-dll-binding.md):NO는 이미지 바인딩이 허용되지 않음을 Bind.exe에 나타내는 DLL 헤더에 비트를 설정합니다. 바인딩이 서명을 무효화하므로 디지털 서명된 경우 DLL을 바인딩하지 않으려고 할 수 있습니다.

### <a name="treat-linker-warning-as-errors"></a>링커 경고를 오류로 처리

[/WX는](wx-treat-linker-warnings-as-errors.md) 링커가 경고를 생성하는 경우 출력 파일이 생성되지 않습니다.

### <a name="force-file-output"></a>강제 파일 출력

[/FORCE](force-force-file-output.md) 옵션은 심볼이 참조되었지만 정의되지 않았거나 곱하기 정의된 경우에도 링커에 .exe 파일 또는 DLL을 만들도록 지시합니다. 잘못된 .exe 파일을 만들 수 있습니다.

**Choices**

- **Enabled** - 인수가 없는 /FORCE는 다중 및 미해결을 모두 의미합니다.
- **정의된 기호만 곱하기** - /FORCE:MULTIPLE을 사용하여 LINK가 기호에 대해 두 개 이상의 정의를 찾더라도 출력 파일을 만듭니다.
- **정의되지 않은 기호만** - /FORCE:UNRESOLVED를 사용하여 LINK가 정의되지 않은 기호를 찾는지 여부에 관계없이 출력 파일을 만듭니다. 입력점 기호가 확인되지 않으면 /FORCE:해결되지 않은 경우 무시됩니다.

### <a name="create-hot-patchable-image"></a>핫 패치 가능한 이미지 만들기

핫패칭을 위한 이미지를 준비합니다.

**Choices**

- **사용** - 핫패칭을 위해 이미지를 준비합니다.
- **X86 이미지 만** - 핫패싱을 위해 X86 이미지를 준비합니다.
- **X64 이미지만** - 핫패싱을 위해 X64 이미지를 준비합니다.
- **이타늄 이미지만** - 핫패칭을 위해 이타늄 이미지를 준비합니다.

### <a name="specify-section-attributes"></a>단면 특성 지정

[/SECTION](section-specify-section-attributes.md) 옵션은 섹션의 .obj 파일이 컴파일될 때 설정된 특성을 재정의하여 섹션의 특성을 변경합니다.

## <a name="input-property-page"></a>입력 속성 페이지

### <a name="additional-dependencies"></a>추가 종속성

링크 명령줄에 추가할 추가 항목(예: *kernel32.lib)을*지정합니다.

### <a name="ignore-all-default-libraries"></a>모든 기본 라이브러리 무시

[/NODEFAULTLIB](nodefaultlib-ignore-libraries.md) 옵션은 외부 참조를 확인할 때 검색하는 라이브러리 목록에서 하나 이상의 기본 라이브러리를 제거하도록 링커에게 지시합니다.

### <a name="ignore-specific-default-libraries"></a>특정 기본 라이브러리 무시

무시할 하나 이상의 기본 라이브러리 이름을 지정합니다. 세미콜론으로 여러 라이브러리를 분리합니다. (/NODEFAULTLIB:[이름, 이름, ...])

### <a name="module-definition-file"></a>모듈 정의 파일

[/DEF](def-specify-module-definition-file.md) 옵션은 모듈 정의 파일(.def)을 링커에 전달합니다. LINK에 하나의 .def 파일만 지정할 수 있습니다.

### <a name="add-module-to-assembly"></a>어셈블리에 모듈 추가

[/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md) 옵션을 사용하면 어셈블리에 모듈 참조를 추가할 수 있습니다. 모듈 참조를 추가한 어셈블리 프로그램에서는 모듈의 형식 정보를 사용할 수 없습니다. 그러나 모듈의 형식 정보는 어셈블리를 참조하는 모든 프로그램에서 사용할 수 있습니다.

### <a name="embed-managed-resource-file"></a>관리되는 리소스 파일 포함

[/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) 출력 파일에 리소스 파일을 포함 합니다.

### <a name="force-symbol-references"></a>강제 기호 참조

[/INCLUDE](include-force-symbol-references.md) 옵션은 링커에게 기호 테이블에 지정된 기호를 추가하도록 지시합니다.

### <a name="delay-loaded-dlls"></a>로드된 DLL 지연

[/DELAYLOAD](delayload-delay-load-import.md) 옵션으로 인해 DLL로드가 지연됩니다. dLL 이름은 로드를 지연시키기 위해 DLL을 지정합니다.

### <a name="assembly-link-resource"></a>어셈블리 링크 리소스

[/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md) 옵션은 출력 파일의 .NET Framework 리소스에 대한 링크를 만듭니다. 리소스 파일이 출력 파일에 배치되지 않습니다.

## <a name="manifest-file-property-page"></a>매니페스트 파일 속성 페이지

### <a name="generate-manifest"></a>매니페스트 생성

[/MANIFEST는](manifest-create-side-by-side-assembly-manifest.md) 링커가 나란히 매니페스트 파일을 만들어야 한다고 지정합니다.

### <a name="manifest-file"></a>매니페스트 파일

[/MANIFESTFILE을](manifestfile-name-manifest-file.md) 사용하면 매니페스트 파일의 기본 이름을 변경할 수 있습니다. 매니페스트 파일의 기본 이름은 .manifest가 추가된 파일 이름입니다.

### <a name="additional-manifest-dependencies"></a>추가 매니페스트 종속성

[/MANIFESTDEPENDENCY를](manifestdependency-specify-manifest-dependencies.md) 사용하면 매니페스트 파일의 종속성 섹션에 배치할 특성을 지정할 수 있습니다.

### <a name="allow-isolation"></a>격리 허용

매니페스트 조회 동작을 지정합니다. [(/허용 격리](allowisolation-manifest-lookup.md):NO)

### <a name="enable-user-account-control-uac"></a>사용자 계정 제어(UAC) 사용

사용자 계정 제어가 활성화되어 있는지 여부를 지정합니다.  [(/MANIFESTUAC,](manifestuac-embeds-uac-information-in-manifest.md)/매니페스트:NO)

### <a name="uac-execution-level"></a>UAC 실행 수준

사용자 계정 컨트롤로 실행할 때 응용 프로그램에 대해 요청된 실행 수준을 지정합니다.  (/MANIFESTUAC:레벨=[값])

**Choices**

- **asInvoker** - UAC 실행 수준: 호출자로.
- **가장 높은 사용 가능** - UAC 실행 수준: 사용 가능한 최고 수준입니다.
- **요구관리자** - UAC 실행 수준: 관리자가 필요합니다.

### <a name="uac-bypass-ui-protection"></a>UAC 바이패스 UI 보호

바탕 화면의 다른 창에 대한 사용자 인터페이스 보호 수준을 우회할지 여부를 지정합니다.  접근성 응용 프로그램에 대해서만 이 속성을 '예'로 설정합니다.  [(/MANIFESTUAC](manifestuac-embeds-uac-information-in-manifest.md):uiAccess=[true | 거짓])

## <a name="debugging-property-page"></a>디버깅 속성 페이지

### <a name="generate-debug-info"></a>디버그 정보 생성

이 옵션을 사용하면 .exe 파일 또는 DLL에 대한 디버깅 정보를 만들 수 있습니다.

**Choices**

- **아니오** - 디버깅 정보가 생성되지 않습니다.
- **디버그 정보 생성** - Microsoft 심볼 서버에 배포하는 데 이상적인 전체 프로그램 데이터베이스(PDB)를 만듭니다.
- **더 빠른 링크에 최적화된 디버그 정보 생성** - 편집 링크 디버그 주기에 이상적인 프로그램 데이터베이스(PDB)를 생성합니다.
- **공유 및 게시에 최적화된 디버그 정보 생성** - 편집 링크 디버그 주기에 이상적인 프로그램 데이터베이스(PDB)를 생성합니다.

### <a name="generate-program-database-file"></a>프로그램 데이터베이스 파일 생성

기본적으로 [/DEBUG를](debug-generate-debug-info.md) 지정하면 링커는 디버깅 정보를 포함하는 프로그램 데이터베이스(PDB)를 만듭니다. PDB의 기본 파일 이름에는 프로그램의 기본 이름과 확장명 .pdb가 있습니다.

### <a name="strip-private-symbols"></a>스트립 개인 기호

[/PDBSTRIPPED](pdbstripped-strip-private-symbols.md) 옵션은 PDB 파일(/DEBUG, /Z7, /Zd 또는 /Zi)을 생성하는 컴파일러 또는 링커 옵션으로 프로그램 이미지를 빌드할 때 두 번째 프로그램 데이터베이스(PDB) 파일을 만듭니다.

### <a name="generate-map-file"></a>맵 파일 생성

[/MAP](map-generate-mapfile.md) 옵션은 링커에게 맵 파일을 만들라고 알려줍니다.

### <a name="map-file-name"></a>맵 파일 이름

맵 파일의 사용자 지정 이름입니다. 기본 이름을 바꿉니다.

### <a name="map-exports"></a>지도 내보내기

[/MAPINFO](mapinfo-include-information-in-mapfile.md) 옵션은 링커에게 /MAP 옵션을 지정하면 생성되는 맵 파일에 지정된 정보를 포함하도록 지시합니다. 내보내기는 내보낸 함수를 포함하도록 링커에 지시합니다.

### <a name="debuggable-assembly"></a>디버깅 어셈블리

[/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md) 디버그 정보 추적을 사용 하 여 디버깅 속성 특성을 내보전 하 고 JIT 최적화를 사용 하지 않도록 설정 합니다.

## <a name="system-property-page"></a>시스템 속성 페이지

### <a name="subsystem"></a>하위

[/SUBSYSTEM](subsystem-specify-subsystem.md) 옵션은 운영 체제에 .exe 파일을 실행하는 방법을 알려줍니다. 하위 시스템을 선택하면 링커가 선택할 진입점 기호(또는 진입점 함수)에 영향을 줍니다.

**Choices**

- **설정되지 않음** - 하위 시스템 집합이 없습니다.
- **콘솔** - Win32 문자 모드 응용 프로그램입니다. 콘솔 응용 프로그램에는 운영 체제에 의해 콘솔이 제공됩니다. main 또는 wmain이 정의된 경우 콘솔이 기본값입니다.
- **Windows** - 응용 프로그램은 사용자와의 상호 작용을 위해 자체 창을 생성하기 때문에 콘솔이 필요하지 않습니다. WinMain 또는 wWinMain이 정의된 경우 WINDOWS가 기본값입니다.
- **네이티브** - Windows NT용 장치 드라이버입니다. /DRIVER:WDM을 지정하면 네이티브가 기본값입니다.
- **EFI 응용 프로그램** - EFI 응용 프로그램.
- **EFI 부팅 서비스 드라이버** - EFI 부팅 서비스 드라이버.
- **EFI ROM** - EFI ROM.
- **EFI 런타임** - EFI 런타임.
- **POSIX** - Windows NT의 POSIX 하위 시스템과 함께 실행되는 응용 프로그램입니다.

### <a name="minimum-required-version"></a>최소 필수 버전

하위 시스템의 최소 필수 버전을 지정합니다. 인수는 범위 0에서 65,535까지의 소수자릿수입니다.

### <a name="heap-reserve-size"></a>힙 예비 크기

가상 메모리의 총 힙 할당 크기를 지정합니다. 기본값은 1MB입니다.    [(/HEAP:예약)](heap-set-heap-size.md)

### <a name="heap-commit-size"></a>힙 커밋 크기

실제 메모리의 총 힙 할당 크기를 지정합니다. 기본값은 4KB입니다.    [(/HEAP:예약,](heap-set-heap-size.md)커밋)

### <a name="stack-reserve-size"></a>스택 리저브 크기

가상 메모리의 총 스택 할당 크기를 지정합니다. 기본값은 1MB입니다.     [(/STACK:예약)](stack-stack-allocations.md)

### <a name="stack-commit-size"></a>스택 커밋 크기

실제 메모리의 총 스택 할당 크기를 지정합니다. 기본값은 4KB입니다.     [(/STACK](stack-stack-allocations.md):예약, 커밋)

### <a name="enable-large-addresses"></a>큰 주소 사용

[/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md) 옵션은 응용 프로그램이 2기가바이트보다 큰 주소를 처리할 수 있음을 링커에 알려줍니다. 기본적으로 /LARGEADDRESSAWARE:NO는 링커 줄에 /LARGEADDRESSAWARE가 달리 지정되지 않은 경우 활성화됩니다.

### <a name="terminal-server"></a>터미널 서버

[/TSAWARE](tsaware-create-terminal-server-aware-application.md) 옵션은 프로그램 이미지의 선택적 헤더에서 IMAGE_OPTIONAL_HEADER Dll특성 필드에 플래그를 설정합니다. 이 플래그를 설정하면 터미널 서버가 애플리케이션에서 특정 변경 작업을 수행할 수 없습니다.

### <a name="swap-run-from-cd"></a>CD에서 스왑 실행

[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md) 옵션은 운영 체제에 링커 출력을 먼저 스왑 파일에 복사한 다음 거기에서 이미지를 실행하도록 지시합니다. 이 옵션은 Windows NT 4.0(및 이후) 기능입니다. **CD를** 지정하면 운영 체제는 이동식 디스크의 이미지를 페이지 파일에 복사한 다음 로드합니다.

### <a name="swap-run-from-network"></a>네트워크에서 실행 스왑

[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md) 옵션은 운영 체제에 링커 출력을 먼저 스왑 파일에 복사한 다음 거기에서 이미지를 실행하도록 지시합니다. 이 옵션은 Windows NT 4.0(및 이후) 기능입니다. **NET을** 지정하면 운영 체제가 먼저 네트워크에서 바이너리 이미지를 스왑 파일로 복사하여 로드합니다. 이 옵션은 네트워크를 통해 응용 프로그램을 실행하는 데 유용합니다.

### <a name="driver"></a>드라이버

[/DRIVER](driver-windows-nt-kernel-mode-driver.md) 링커 옵션을 사용하여 Windows NT 커널 모드 드라이버를 빌드합니다.

**Choices**

- **설정되지 않음** - 기본 드라이버 설정입니다.
- **드라이버** - 드라이버
- **UP 전용** - /DRIVER:UPONLY를 사용하면 링커가 출력 헤더의 특성에 IMAGE_FILE_UP_SYSTEM_ONLY 비트를 추가하여 단일 프로세서(UP) 드라이버임을 지정합니다. 운영 체제는 다중 프로세서(MP) 시스템에서 UP 드라이버를 로드하지 않습니다.
- **WDM** - /DRIVER:WDM을 사용하면 링커가 선택적 헤더의 Dll특성 필드에 IMAGE_DLLCHARACTERISTICS_WDM_DRIVER 비트를 설정합니다.

## <a name="optimization-property-page"></a>최적화 속성 페이지

### <a name="references"></a>참조 항목

[/OPT](opt-optimizations.md):REF는 /OPT:NOREF가 참조되지 않은 함수 및/또는 데이터를 유지하면서 참조되지 않는 함수 및/또는 데이터를 제거합니다.

### <a name="enable-comdat-folding"></a>COMDAT 정리 사용

[/OPT](opt-optimizations.md):ICF\[=반복]을 사용하여 동일한 COMDAT 폴딩을 수행합니다.

### <a name="function-order"></a>함수 순서

[/ORDER](order-put-functions-in-order.md)옵션은 특정 COMDAT를 미리 정해진 순서로 이미지에 배치하여 프로그램을 최적화하도록 LINK에 알려줍니다. LINK는 이미지의 각 섹션 내에서 지정된 순서로 함수를 배치합니다.

### <a name="profile-guided-database"></a>프로필 안내 데이터베이스

프로파일 안내 최적화를 위해 .pgd 파일을 지정합니다. [(/PGD)](pgd-specify-database-for-profile-guided-optimizations.md)

### <a name="link-time-code-generation"></a>링크 시간 코드 생성

링크 타임 코드 생성을 지정합니다. [(/LTCG)](ltcg-link-time-code-generation.md)

**Choices**

- **기본값** - 기본 LTCG 설정입니다.
- **빠른 링크 시간 코드 생성 사용** - [/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)를 사용하여 링크 시간 코드 생성을 사용합니다.
- **링크 시간 코드 생성** 사용 - [링크 시간 코드 생성](ltcg-link-time-code-generation.md)을 사용합니다.
- **프로파일 가이드 최적화 - 계측기** - :PGINSTRUMENT를 사용하여 [프로파일 가이드 최적화를](../profile-guided-optimizations.md) 사용합니다.
- **프로파일 안내 최적화 - 최적화** - 링커는 계측된 바이너리를 실행한 후 생성된 프로파일 데이터를 사용하여 최적화된 이미지를 생성하도록 지정합니다.
- **프로필 안내 최적화 - 업데이트** - :PGINSTRUMENT 단계에서 지정된 내용에서 추가하거나 수정할 입력 파일 목록을 허용하고 추적합니다.

## <a name="embedded-idl-property-page"></a>포함된 IDL 속성 페이지

### <a name="midl-commands"></a>MIDL 명령

MIDL 명령줄 옵션을 지정합니다. [(/MIDL)](midl-specify-midl-command-line-options.md):@responsefile

### <a name="ignore-embedded-idl"></a>임베디드 IDL 무시

[/IGNOREIDL](ignoreidl-don-t-process-attributes-into-midl.md) 옵션은 소스 코드의 모든 IDL 특성을 .idl 파일로 처리해서는 안 되도록 지정합니다.

### <a name="merged-idl-base-file-name"></a>병합된 IDL 기본 파일 이름

[/IDLOUT](idlout-name-midl-output-files.md) 옵션은 .idl 파일의 이름과 확장을 지정합니다.

### <a name="type-library"></a>형식 라이브러리

[/TLBOUT](tlbout-name-dot-tlb-file.md) 옵션은 .tlb 파일의 이름과 확장을 지정합니다.

### <a name="typelib-resource-id"></a>TypeLib 리소스 ID

링커에서 생성된 형식 라이브러리의 리소스 ID를 지정할 수 있습니다. [(/TLBID](tlbid-specify-resource-id-for-typelib.md):id)

## <a name="windows-metadata-property-page"></a>Windows 메타데이터 속성 페이지

### <a name="generate-windows-metadata"></a>Windows 메타데이터 생성

Windows 메타데이터 생성을 사용하거나 사용하지 않도록 설정합니다.

**Choices**

- **예** - Windows 메타데이터 파일 생성을 활성화합니다.
- **아니오** - Windows 메타데이터 파일 생성을 사용하지 않도록 설정합니다.

### <a name="windows-metadata-file"></a>윈도우 메타데이터 파일

[/WINMDFILE](winmdfile-specify-winmd-file.md) 옵션 스위치.

### <a name="windows-metadata-key-file"></a>윈도우 메타데이터 키 파일

Windows 메타데이터에 서명할 키 또는 키 쌍을 지정합니다. [(/WINMDKEYFILE](winmdkeyfile-specify-winmd-key-file.md):파일 이름)

### <a name="windows-metadata-key-container"></a>윈도우 메타데이터 키 컨테이너

Windows 메타데이터에 서명할 키 컨테이너를 지정합니다. [(/WINMDKEYCONTAINER](winmdkeycontainer-specify-key-container.md):name)

### <a name="windows-metadata-delay-sign"></a>윈도우 메타데이터 지연 기호

Windows 메타데이터에 부분적으로 서명합니다. Windows 메타데이터에 공개 키만 배치하려는 경우 [/WINMDDELAYSIGN을](winmddelaysign-partially-sign-a-winmd.md) 사용합니다. 기본값은 /WINMDDELAYSIGN:NO입니다.

## <a name="advanced-property-page"></a>고급 속성 페이지

### <a name="entry-point"></a>진입점

[/ENTRY](entry-entry-point-symbol.md) 옵션은 .exe 파일 또는 DLL의 시작 주소로 진입점 함수를 지정합니다.

### <a name="no-entry-point"></a>진입점 없음

리소스 전용 DLL을 만들 [때는 /NOENTRY](noentry-no-entry-point.md)옵션이 필요합니다. 이 옵션을 사용하면 LINK가 참조를 `_main` DLL에 연결하지 못하도록 합니다.

### <a name="set-checksum"></a>체크섬 설정

[/RELEASE](release-set-the-checksum.md) 옵션은 .exe 파일의 헤더에 체크섬을 설정합니다.

### <a name="base-address"></a>기준 주소

프로그램의 기준 주소를 설정합니다. [(/BASE](base-base-address.md):{주소,\[크기] | @filename,키})

### <a name="randomized-base-address"></a>무작위 기본 주소

무작위 기본 주소입니다. [(/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)\[:NO])

### <a name="fixed-base-address"></a>고정 기본 주소

기본 설정 기준 주소에서만 로드할 수 있는 프로그램을 만듭니다. (/고정:아니오])[/FIXED](fixed-fixed-base-address.md)\[

### <a name="data-execution-prevention-dep"></a>데이터 실행 방지(DEP)

실행 수는 Windows 데이터 실행 방지 기능과 호환되는 것으로 테스트된 것으로 표시합니다. [(/NXCOMPAT](nxcompat-compatible-with-data-execution-prevention.md)\[:NO])

### <a name="turn-off-assembly-generation"></a>어셈블리 생성 끄기

[/NOASSEMBLY](noassembly-create-a-msil-module.md) 옵션은 링커에게 .NET Framework 어셈블리 없이 현재 출력 파일에 대한 이미지를 만들도록 지시합니다.

### <a name="unload-delay-loaded-dll"></a>언로드 지연 로드 DLL

**언로드** 한정자는 지연 로드 도우미 함수에 DLL의 명시적 언로드를 지원하도록 지시합니다. [(/지연](delay-delay-load-import-settings.md):언로드)

### <a name="nobind-delay-loaded-dll"></a>노빈드 지연 로드 DLL

**NOBIND** 한정자는 링커에게 최종 이미지에 바인딩가능한 IAT를 포함하지 않도록 지시합니다. 기본값은 지연 로드된 DLL에 대해 바인딩할 수 있는 IAT를 만드는 것입니다. (/지연:노빈드)[/DELAY](delay-delay-load-import-settings.md)

### <a name="import-library"></a>가져오기 라이브러리

기존 가져오기 라이브러리 이름을 재정의합니다. [(/IMPLIB](implib-name-import-library.md):파일 이름)

### <a name="merge-sections"></a>단면 병합

[/MERGE](merge-combine-sections.md) 옵션은 첫 번째 단면(from)과 두 번째 단면(받는 것)을 결합하여 결과 섹션의 이름을 지정합니다. 예를 들어 /merge:.rdata=.text를 예로 들 수 있습니다.

### <a name="target-machine"></a>대상 기계

[/MACHINE](machine-specify-target-platform.md) 옵션은 프로그램의 대상 플랫폼을 지정합니다.

**Choices**

- **설정되지 않음**
- **기계 암**
- **기계암64**
- **기계에BC**
- **기계A64**
- **기계 MIPS**
- **기계MIPS16**
- **기계MIPSFPU**
- **기계MIPSFPU16**
- **머신시4**
- **기계 엄지 손가락**
- **기계X64**
- **기계X86**

### <a name="profile"></a>프로필

성능 도구 프로파일러와 함께 사용할 수 있는 출력 파일을 생성합니다. 생성디버그정보(//DEBUG)를 설정해야 합니다.[/DEBUG](debug-generate-debug-info.md) [(/PROFILE)](profile-performance-tools-profiler.md)

### <a name="clr-thread-attribute"></a>CLR 스레드 특성

CLR 프로그램의 진입점에 대한 스레딩 특성을 명시적으로 지정합니다.

**Choices**

- **MTA 스레딩 특성** - MTAThreadAttribute 특성을 프로그램의 진입점에 적용합니다.
- **STA 스레딩 특성** - 프로그램의 진입점에 STAThreadAttribute 특성을 적용합니다.
- **기본 스레딩 특성** - [/CLRTHREADATTRIBUTE를](clrthreadattribute-set-clr-thread-attribute.md)지정하지 않는 것과 동일합니다. 공통 언어 런타임(CLR)이 기본 스레딩 특성을 설정할 수 있습니다.

### <a name="clr-image-type"></a>CLR 이미지 유형

CLR 이미지의 형식(IJW, 순수 또는 안전)을 설정합니다.

**Choices**

- **포스 IJW 이미지**
- **순수 IL 이미지 강제**
- **강제 안전 IL 이미지**
- **기본 이미지 유형**

### <a name="key-file"></a>키 파일

어셈블리에 서명할 키 또는 키 쌍을 지정합니다. [(/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md):파일 이름)

### <a name="key-container"></a>키 컨테이너

어셈블리에 서명할 키 컨테이너를 지정합니다. [(/키컨테이너:이름)](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

### <a name="delay-sign"></a>지연 기호

어셈블리에 부분적으로 서명합니다. 어셈블리에 공개 키만 배치하려는 경우 [/DELAYSIGN을](delaysign-partially-sign-an-assembly.md) 사용합니다. 기본값은 /DELAYSIGN:NO입니다.

### <a name="clr-unmanaged-code-check"></a>CLR 관리되지 않는 코드 검사

[/CLRUNMANAGEDCODECHECK는](clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md) 링커가 관리되는 코드에서 네이티브 DLL로 링커에서 생성된 PInvoke 호출에 SuppressUnmanagedCodeSecurityAttribute를 적용할지 여부를 지정합니다.

### <a name="error-reporting"></a>오류 보고

ICE(내부 컴파일러 오류) 정보를 Visual C++ 팀에 직접 제공할 수 있습니다.

**Choices**

- **프롬프트즉시** - 즉시 프롬프트.
- **다음 로그인대기열** - 다음 로그인을 위한 큐입니다.
- **오류 보고서 보내기** - 오류 보고서를 보냅니다.
- **오류 보고서 없음** - 오류 보고서가 없습니다.

### <a name="sectionalignment"></a>SectionAlignment

[/ALIGN](align-section-alignment.md) 옵션은 프로그램의 선형 주소 공간 내에서 각 섹션의 정렬을 지정합니다. 숫자 인수는 바이트이며 2의 힘이어야 합니다.

### <a name="preserve-last-error-code-for-pinvoke-calls"></a>PInvoke 호출에 대한 마지막 오류 코드 보존

[/CLRSUPPORTLASTERROR는](clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)기본적으로 사용 중이며/clr로 컴파일된 코드에서 DLLS의 네이티브 함수를 호출할 수 있는 P/Invoke 메커니즘을 통해 호출된 함수의 마지막 오류 코드를 유지합니다.

**Choices**

- **사용 -** CLRSupportLastError를 사용하도록 설정합니다.
- **사용 안 함** - CLRSupportLastError를 사용하지 않도록 설정합니다.
- **시스템 Dlls 전용** - 시스템 dlls에 대해서만 CLRSupportLastError를 사용하도록 설정합니다.

### <a name="image-has-safe-exception-handlers"></a>이미지에 안전한 예외 처리기가 있습니다.

[/SAFESEH를](safeseh-image-has-safe-exception-handlers.md) 지정하면 링커는 이미지의 안전한 예외 처리기 테이블을 생성할 수 있는 경우에만 이미지를 생성합니다. 이 표는 이미지에 대해 유효한 예외 처리기를 운영 체제에 지정합니다.
