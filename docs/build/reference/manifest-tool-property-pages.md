---
title: 매니페스트 도구 속성 페이지
ms.date: 07/24/2019
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.ResourceOutputFileName
- VC.Project.VCManifestTool.GenerateCatalogFiles
- VC.Project.VCManifestTool.ManifestFromManagedAssembly
- VC.Project.VCManifestTool.SuppressDependencyElement
- VC.Project.VCManifestTool.GenerateCategoryTags
- VC.Project.VCManifestTool.EnableDPIAwareness
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.ReplacementsFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- vc.project.AdditionalOptionsPage
ms.assetid: f33499c4-7733-42d9-80e3-8a5018786965
ms.openlocfilehash: e1d0f1ac889cb915216ceb70d48e36efe4ad21bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336304"
---
# <a name="manifest-tool-property-pages"></a>매니페스트 도구 속성 페이지

이 페이지를 사용하여 [Mt.exe](/windows/win32/sbscs/mt-exe)에 대한 일반 옵션을 지정합니다. 이러한 페이지는 **프로젝트** > **속성** > **구성 속성** > **매니페스트 도구**에서 찾을 수 있습니다.

## <a name="general-property-page"></a>일반 속성 페이지

### <a name="suppress-startup-banner"></a>시작 배너 표시 안 함

   **예(/nologo)** 는 매니페스트 도구가 시작될 때 표준 Microsoft 저작권 데이터가 숨겨지도록 지정합니다. 빌드 프로세스의 일부 또는 빌드 환경에서 mt.exe를 실행할 때 로그 파일에서 원치 않는 출력이 표시되지 않도록 하려면 이 옵션을 사용합니다.

### <a name="verbose-output"></a>자세한 출력

   **예(/verbose)** 는 매니페스트 생성 중에 추가 빌드 정보가 표시되도록 지정합니다.

### <a name="assembly-identity"></a>어셈블리 ID

/identity 옵션을 사용하여 [ \<어셈블리Id> Element에](/visualstudio/deployment/assemblyidentity-element-clickonce-application)대한 특성으로 구성된 ID 문자열을 지정합니다. ID `name` 문자열은 특성의 값으로 시작하고 *특성* = *값* 쌍다음에 있습니다. ID 문자열의 특성은 쉼표로 구분됩니다.

다음은 예제 ID 문자열입니다.`Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`

## <a name="input-and-output-property-page"></a>입력 및 출력 속성 페이지

### <a name="additional-manifest-files"></a>추가 매니페스트 파일

**/manifest** 옵션을 사용하여 매니페스트 도구가 처리하거나 병합할 추가 매니페스트 파일의 전체 경로를 지정합니다. 전체 경로는 세미콜론으로 구분됩니다. (매니페스트 [매니페스트1] [매니페스트2] ...)

### <a name="input-resource-manifests"></a>입력 리소스 매니페스트

**/inputresource** 옵션을 사용하여 매니페스트 도구에 입력할 RT_MANIFEST 형식의 리소스 전체 경로를 지정합니다. 경로 다음에 지정된 리소스 ID가 올 수 있습니다. 다음은 그 예입니다.

`dll_with_manifest.dll;#1`

### <a name="embed-manifest"></a>매니페스트 포함

- **예**는 프로젝트 시스템이 애플리케이션 매니페스트 파일을 어셈블리에 포함하도록 지정합니다.

- **아니요**는 프로젝트 시스템이 애플리케이션 매니페스트 파일을 독립형 파일로 생성하도록 지정합니다.

### <a name="output-manifest-file"></a>출력 매니페스트 파일

출력 매니페스트 파일의 이름을 지정합니다. 이 속성은 매니페스트 도구에서 하나의 매니페스트 파일만 작동하는 경우 선택 사항입니다. (-out:[파일];#[리소스 ID])

### <a name="manifest-resource-file"></a>매니페스트 리소스 파일

매니페스트를 프로젝트 출력에 포함시키는 데 사용하는 출력 리소스 파일을 지정합니다.

### <a name="generate-catalog-files"></a>카탈로그 파일 생성

**/makecdfs** 옵션을 사용하여 매니페스트 도구가 카탈로그를 만드는 데 사용되는 카탈로그 정의 파일(.cdf 파일)을 생성하도록 지정합니다. (/마크dfs)

### <a name="generate-manifest-from-managedassembly"></a>ManagedAssembly에서 매니페스트 생성

관리되는 어셈블리에서 매니페스트를 생성합니다. (관리되는 어셈블리 이름:\[파일])

### <a name="suppress-dependency-element"></a>종속성 요소 억제

-managedassembly와 함께 사용됩니다. 은 최종 매니페스트에서 종속성 요소의 생성을 억제합니다. (-독립없음)

### <a name="generate-category-tags"></a>범주 태그 생성

-managedassembly와 함께 사용됩니다. -범주로 인해 범주 태그가 생성됩니다. (카테고리)

### <a name="dpi-awareness"></a>DPI 인식

애플리케이션이 DPI를 인식하는지 여부를 지정합니다. 기본적으로 MFC 프로젝트는 **예**로 설정되고, 다른 프로젝트는 **아니요**로 설정됩니다. MFC 프로젝트에만 DPI 인식 기능이 내장되어 있기 때문입니다. 다른 DPI 설정을 처리하는 코드를 추가하는 경우, 이 설정을 **예**로 재정의할 수 있습니다. 애플리케이션이 DPI를 인식하지 않는데 인식하는 것으로 설정할 경우 애플리케이션이 흐릿하게 또는 작게 표시될 수 있습니다.

**Choices**

- **없음**
- **높은 DPI 인식**
- **모니터당 높은 DPI 인식**

## <a name="isolated-com-property-page"></a>격리된 COM 속성 페이지

격리된 COM에 대한 자세한 내용은 [격리된 응용 프로그램](/windows/win32/SbsCs/isolated-applications) 및 [방법: 격리된 응용 프로그램을 빌드하여 COM 구성 요소를 사용합니다.](../how-to-build-isolated-applications-to-consume-com-components.md)

### <a name="type-library-file"></a>형식 라이브러리 파일

regfree COM 매니페스트 지원에 사용할 형식 라이브러리를 지정합니다. (-tlb:[파일])

### <a name="registrar-script-file"></a>등록자 스크립트 파일

regfree COM 매니페스트 지원에 사용할 레지스트라 스크립트 파일을 지정합니다. (-rgs:[파일])

### <a name="component-file-name"></a>구성 요소 파일 이름

지정된 .tlb 또는 .rgs에서 빌드된 구성 요소의 파일 이름을 지정합니다. (-dll:[파일])

### <a name="replacements-file"></a>대체 파일

RGS 파일에서 교체 가능한 문자열에 대한 값이 포함된 파일을 지정합니다. (교체:[파일])

## <a name="advanced-property-page"></a>고급 속성 페이지

### <a name="update-file-hashes"></a>파일 해시 업데이트

파일 요소에 지정된 파일의 해시를 계산하고 이 값으로 해시 특성을 업데이트합니다. (해시 업데이트:[경로])

### <a name="update-file-hashes-search-path"></a>파일 해시 업데이트 검색 경로

파일 해시를 업데이트할 때 사용할 검색 경로를 지정합니다.

### <a name="additional-options"></a>추가 옵션

추가 옵션

## <a name="see-also"></a>참고 항목

[C++ 프로젝트 속성 페이지 참조](property-pages-visual-cpp.md)
