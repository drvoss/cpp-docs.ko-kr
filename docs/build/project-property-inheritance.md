---
title: Visual Studio 프로젝트의 속성 상속 - C++
description: 네이티브 (MSBuild) Visual Studio C++ 프로젝트에서 속성 상속이 작동 하는 방식입니다.
ms.date: 02/21/2020
helpviewer_keywords:
- C++ projects, property inheritance
ms.openlocfilehash: 2032ab63c7d278a080742dba8d8d0c6c3ed7a094
ms.sourcegitcommit: 9a63e9b36d5e7fb13eab15c2c35bedad4fb03ade
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77600026"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Visual Studio 프로젝트의 속성 상속

Visual Studio 네이티브 프로젝트 시스템은 MSBuild를 기반으로 합니다. MSBuild는 모든 종류의 프로젝트를 빌드하기 위한 파일 형식 및 규칙을 정의 합니다. 여러 구성 및 플랫폼에 대 한 빌드의 복잡성을 대부분 관리 합니다. 작동 방식을 이해 하는 것이 유용 합니다. 사용자 지정 구성을 정의 하려는 경우에 특히 중요 합니다. 또는 여러 프로젝트로 공유 하 고 가져올 수 있는 재사용 가능한 속성 집합을 만들 수 있습니다.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>.Vcxproj 파일,.props 파일 및.targets 파일

프로젝트 속성은 프로젝트 파일 ( *`.vcxproj`* )에 직접 저장 되거나 프로젝트 파일이 가져오고 기본값을 제공 하는 다른 *`.targets`* 또는 *`.props`* 파일에 저장 됩니다. Visual Studio 2015의 경우 이러한 파일은 *`\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140`* 에 있습니다. Visual Studio 2017의 경우 이러한 파일은 *`\Program Files (x86)\Microsoft Visual Studio\2017\<edition>\Common7\IDE\VC\VCTargets`* 에 있으며, 여기서 *`<edition>`* 는 visual studio 버전을 설치 합니다. Visual Studio 2019에서 이러한 파일은 *`\Program Files (x86)\Microsoft Visual Studio\2019\<edition>\MSBuild\Microsoft\VC\v160`* 에 있습니다. 속성은 사용자 지정 프로젝트에 추가할 수 있는 사용자 지정 *`.props`* 파일에도 저장 됩니다. 이러한 파일은 직접 편집 하지 않는 것이 좋습니다. 대신, MSBuild를 깊이 이해 하는 경우를 제외 하 고는 IDE의 속성 페이지를 사용 하 여 모든 속성, 특히 상속에 참여 하는 속성을 수정 합니다.

앞에 설명한 것처럼 다른 파일에서 다른 값이 동일한 구성에 대한 동일한 속성에 할당될 수 있습니다. 프로젝트를 빌드하면 MSBuild 엔진은 올바로 정의된 순서대로(아래 설명 참조) 프로젝트 파일 및 가져온 모든 파일을 평가합니다. 각 파일을 평가하기 때문에 해당 파일에서 정의된 모든 속성 값이 기존 값을 재정의합니다. 지정 되지 않은 모든 값은 앞에서 평가한 파일에서 상속 됩니다. 속성 페이지를 사용 하 여 속성을 설정 하는 경우 설정 하는 위치에 주의 해야 합니다. *`.props`* 파일에서 속성을 "X"로 설정 했지만 프로젝트 파일에서 속성이 "y"로 설정 된 경우 프로젝트는 속성을 "y"로 설정 하 여 빌드합니다. 프로젝트 항목에서 동일한 속성이 "Z"로 설정 된 경우 (예: *`.cpp`* 파일) MSBuild 엔진은 "z" 값을 사용 합니다.

다음은 기본 상속 트리입니다.

1. MSBuild CPP 도구 집합의 기본 설정 (.. *`.vcxproj`* 파일에서 가져온 파일 \ Files\MSBuild\Microsoft.Cpp\v4.0\Microsoft.Cpp.Default.props

1. 속성 시트

1. *`.vcxproj`* 파일입니다. 기본 및 속성 시트 설정을 재정의할 수 있습니다.

1. 항목 메타데이터

> [!TIP]
> 속성 페이지에서 **굵게 표시** 된 속성은 현재 컨텍스트에서 정의 됩니다. 일반 글꼴의 속성이 상속됩니다.

## <a name="view-an-expanded-project-file-with-all-imported-values"></a>가져온 모든 값으로 확장된 프로젝트 파일 보기

확장된 파일을 보고 지정된 속성 값의 상속 방법을 결정하는 것이 유용한 경우도 있습니다. 확장 버전을 보려면 Visual Studio 명령 프롬프트에서 다음 명령을 입력합니다. 자리 표시자 파일 이름을 사용할 이름으로 변경합니다.

> **msbuild/spp:** _\temp_

확장 된 프로젝트 파일은 클 수 있으며 MSBuild를 잘 알고 있지 않은 한 이해 하기 어렵습니다. 프로젝트 파일의 기본 구조는 다음과 같음:

1. IDE에 노출 되지 않는 기본 프로젝트 속성입니다.

1. 몇 가지 기본 도구 집합 독립적 속성을 정의 하는 *`Microsoft.cpp.default.props`* 가져오기

1. **구성 일반** 페이지에서 **PlatformToolset** 및 **프로젝트** 기본 속성으로 노출된 전역 구성 속성입니다. 이러한 속성은 다음 단계에서 *`Microsoft.cpp.props`* 에서 가져올 도구 집합과 내장 속성 시트를 결정 합니다.

1. 대부분의 프로젝트 기본값을 설정 하는 *`Microsoft.cpp.props`* 가져오기

1. *`.user`* 파일을 포함 하 여 모든 속성 시트를 가져옵니다. 등록 정보 시트는 **PlatformToolset** 및 **프로젝트** 기본 속성을 제외한 모든 항목을 재정의할 수 있습니다.

1. 프로젝트 구성 속성의 나머지입니다. 이러한 값은 속성 시트에서 설정된 것을 재정의할 수 있습니다.

1. 메타데이터와 함께 있는 항목(파일)입니다. 이러한 항목은 다른 속성 및 가져오기 전에 발생 하더라도 항상 MSBuild 평가 규칙의 마지막 단어입니다.

자세한 내용은 [MSBuild 속성](/visualstudio/msbuild/msbuild-properties)을 참조하세요.

## <a name="build-configurations"></a>빌드 구성

구성은 이름이 지정된 속성의 임의의 그룹입니다. Visual Studio는 디버그 및 릴리스 구성을 제공 합니다. 각각은 디버그 빌드 또는 릴리스 빌드에 대 한 다양 한 속성을 적절 하 게 설정 합니다. **Configuration Manager** 를 사용 하 여 사용자 지정 구성을 정의할 수 있습니다. 이는 빌드의 특정 버전에 대 한 속성을 그룹화 하는 편리한 방법입니다.

빌드 구성에 대해 더 잘 이해 하려면 **속성 관리자**를 엽니다. 설정에 따라 **> 속성 관리자 보기** 를 선택 하거나 **다른 Windows > 속성 관리자 > 확인**하 여 열 수 있습니다. **속성 관리자** 에는 프로젝트의 각 구성 및 플랫폼 쌍에 대 한 노드가 있습니다. 이러한 각 노드는 구성에 대 한 특정 속성을 설정 하는 속성 시트 ( *`.props`* 파일)에 대 한 노드입니다.

![속성 관리자](media/property-manager.png "속성 관리자")

예를 들어 속성 페이지에서 일반 창으로 이동할 수 있습니다. 문자 집합 속성을 "유니코드 사용" 대신 "Not Set"으로 변경한 다음 **확인**을 클릭 합니다. 이제 속성 관리자는 **유니코드 지원** 속성 시트를 표시 하지 않습니다. 현재 구성에 대해서는 제거 되지만 다른 구성에 대해서는 여전히 남아 있습니다.

속성 관리자 및 속성 시트에 대한 자세한 정보는 [Visual Studio C++ 프로젝트 설정 공유 또는 다시 사용](create-reusable-property-configurations.md)을 참조하세요.

> [!TIP]
> *`.user`* 파일은 레거시 기능입니다. 구성 및 플랫폼에 따라 속성을 정확 하 게 그룹화 하려면 삭제 하는 것이 좋습니다.
