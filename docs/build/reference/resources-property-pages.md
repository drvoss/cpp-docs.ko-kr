---
title: 리소스
ms.date: 08/28/2019
ms.topic: article
ms.assetid: dade2f6b-c51f-4c33-9023-41956ae4b5f6
f1_keywords:
- VC.Project.VCResourceCompilerTool.PreprocessorDefinitions
- VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions
- VC.Project.VCResourceCompilerTool.Culture
- VC.Project.VCResourceCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCResourceCompilerTool.IgnoreStandardIncludePath
- VC.Project.VCResourceCompilerTool.ShowProgress
- VC.Project.VCResourceCompilerTool.SuppressStartupBanner
- VC.Project.VCResourceCompilerTool.ResourceOutputFileName
- VC.Project.VCResourceCompilerTool.NullTerminateStrings
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: c4a3048bfa07e9635662534b510fa57caa091f00
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336083"
---
# <a name="resources-property-page"></a>리소스 속성 페이지

네이티브 Windows 데스크톱 프로그램의 경우 빌드는 [리소스 컴파일러(rc.exe)를](/windows/win32/menurc/resource-compiler) 호출하여 이미지, 문자열 테이블 및 *.res* 파일을 바이너리로 추가합니다. 이 속성 페이지에 노출된 속성은 C++ 컴파일러 또는 링커가 아니라 리소스 컴파일러로 전달됩니다. 여기에 나열된 속성및 RC 명령줄 옵션에 매핑하는 방법에 대한 자세한 내용은 [RC(RC 명령줄 사용)를](/windows/win32/menurc/using-rc-the-rc-command-line-)참조하십시오. **Resources** 속성 페이지에 액세스하는 방법에 대한 자세한 내용은 [Visual Studio의 C++ 컴파일러 설정 및 빌드 속성을](../working-with-project-properties.md)참조하십시오. 프로그래밍 방식으로 이러한 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCResourceCompilerTool>을 참조하세요.

C++/CLI 응용 프로그램의 .NET 리소스에 대한 속성은 [관리되는 리소스 속성 페이지에](managed-resources-property-page.md)노출됩니다.

## <a name="preprocessor-definitions"></a>전처리기 정의

리소스 컴파일러에 대해 하나 이상의 정의를 지정합니다. (/d[매크로])

## <a name="undefine-preprocessor-definitions"></a>전처리기 정의 해제

기호를 정의 해제합니다. (/u)

## <a name="culture"></a>culture

리소스에 사용되는 문화(예: 미국 영어 또는 이탈리아어)를 나열합니다. (/l[num])

## <a name="additional-include-directories"></a>추가 포함 디렉터리

포함 경로에 추가할 하나 이상의 디렉터리를 지정합니다. 세미 콜론 구분 기호를 사용 하 여 하나 이상 인 경우. (/I[경로])

## <a name="ignore-standard-include-paths"></a>표준 포함 패스 무시

리소스 컴파일러가 INCLUDE 환경 변수에 지정된 디렉터리에 포함 파일을 검색하지 못하도록 합니다. (/X)

## <a name="show-progress"></a>진행률 표시

진행률 메시지를 출력 창으로 보냅니다. (/v)

## <a name="suppress-startup-banner"></a>시작 배너 표시 안 함

시작 배너 및 정보 메시지 의 표시를 억제 (/nologo)

## <a name="resource-file-name"></a>리소스 파일 이름

리소스 파일의 이름을 지정합니다(/fo[파일])

## <a name="null-terminate-strings"></a>Null 문자열 종료

문자열 테이블의 모든 문자열에 null을 부합니다. (/n)

## <a name="see-also"></a>참고 항목

[C++ 프로젝트 속성 페이지 참조](property-pages-visual-cpp.md)
