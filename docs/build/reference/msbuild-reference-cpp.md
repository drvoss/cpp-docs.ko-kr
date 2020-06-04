---
title: 비주얼 스튜디오에서 C++ 프로젝트에 대한 MSBuild 참조
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: 96987a252d12f718025dd55deecad5c6bac26872
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336203"
---
# <a name="msbuild-reference-for-c-projects"></a>C++ 프로젝트용 MSBuild 참조

MSBuild는 C++ 프로젝트를 포함하여 Visual Studio의 모든 프로젝트에 대한 기본 빌드 시스템입니다. Visual Studio 통합 개발 환경(IDE)에서 프로젝트를 빌드할 때 msbuild.exe 도구를 호출하여 .vcxproj 프로젝트 파일및 다양한 .targets 및 .props 파일을 사용합니다. 일반적으로 Visual Studio IDE를 사용하여 프로젝트 속성을 설정하고 MSBuild를 호출하는 것이 좋습니다. 프로젝트 파일을 수동으로 편집하면 제대로 수행되지 않으면 심각한 문제가 발생할 수 있습니다.

어떤 이유로 명령줄에서 직접 MSBuild를 사용하려는 경우 [명령줄에서 MSBuild 사용을](../msbuild-visual-cpp.md)참조하십시오. 일반적으로 MSBuild에 대한 자세한 내용은 시각적 스튜디오 설명서의 [MSBuild를](/visualstudio/msbuild/msbuild) 참조하십시오.

## <a name="in-this-section"></a>섹션 내용

[C++ 프로젝트용 MSBuild 내부](msbuild-visual-cpp-overview.md)<br/>
속성 및 대상이 저장되고 사용되는 방법에 대한 정보입니다.

[빌드 명령 및 속성에 대한 일반 매크로](common-macros-for-build-commands-and-properties.md)<br/>
경로 및 제품 버전과 같은 속성을 정의하는 데 사용할 수 있는 매크로(컴파일 시간 상수)에 대해 설명합니다.

[C++ 프로젝트에 대해 생성된 파일 형식](file-types-created-for-visual-cpp-projects.md)<br/>
Visual Studio에서 다양한 프로젝트 유형에 대해 만드는 다양한 종류의 파일에 대해 설명합니다.

[비주얼 스튜디오 C++ 프로젝트 템플릿](visual-cpp-project-types.md)<br>
C++에 사용할 수 있는 MSBuild 기반 프로젝트 형식에 대해 설명합니다.

[C++ 새 항목 템플릿](using-visual-cpp-add-new-item-templates.md)<br>
Visual Studio 프로젝트에 추가할 수 있는 소스 파일 및 기타 항목에 대해 설명합니다.

[미리 컴파일된 헤더 파일](../creating-precompiled-header-files.md) 미리 컴파일된 헤더 파일을 사용하는 방법과 빌드 시간을 단축하기 위해 사용자 지정 미리 컴파일된 코드를 만드는 방법.

[비주얼 스튜디오 프로젝트 속성 참조](property-pages-visual-cpp.md)<br/>
Visual Studio IDE에 설정된 프로젝트 속성에 대한 참조 설명서입니다.

## <a name="see-also"></a>참고 항목

[C/C++ 빌드 참조](c-cpp-building-reference.md)
