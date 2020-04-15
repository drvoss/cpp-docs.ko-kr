---
title: Visual Studio 프로젝트의 속성 상속 - C++
description: 기본(MSBuild) Visual Studio C++ 프로젝트에서 속성 상속이 작동하는 방식입니다.
ms.date: 02/21/2020
helpviewer_keywords:
- C++ projects, property inheritance
ms.openlocfilehash: 4740c479c6cc7c877fd72b7828a8e4811826de6c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328470"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Visual Studio 프로젝트의 속성 상속

비주얼 스튜디오 네이티브 프로젝트 시스템은 MSBuild를 기반으로 합니다. MSBuild는 모든 종류의 프로젝트를 빌드하기 위한 파일 형식과 규칙을 정의합니다. 여러 구성 및 플랫폼에 대한 건물의 복잡성대부분을 관리합니다. 어떻게 작동하는지 이해하는 것이 유용할 것입니다. 사용자 지정 구성을 정의하려는 경우 특히 중요합니다. 또는 여러 프로젝트로 공유하고 가져올 수 있는 재사용 가능한 속성 집합을 만듭니다.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>.Vcxproj 파일,.props 파일 및.targets 파일

프로젝트 속성은 프로젝트 파일()*`.vcxproj`* 또는 프로젝트 *`.targets`* 파일이 가져오고 기본값을 제공하는 다른 파일 또는 *`.props`* 파일에 직접 저장됩니다. Visual Studio 2015의 경우 이러한 *`\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140`* 파일은 에 있습니다. Visual Studio 2017의 경우 이러한 *`\Program Files (x86)\Microsoft Visual Studio\2017\<edition>\Common7\IDE\VC\VCTargets`* *`<edition>`* 파일은 Visual Studio 버전이 설치된 위치에 있습니다. Visual Studio 2019에서 이러한 파일은 에 있습니다. *`\Program Files (x86)\Microsoft Visual Studio\2019\<edition>\MSBuild\Microsoft\VC\v160`* 속성은 사용자 지정 *`.props`* 파일에 추가할 수 있는 사용자 지정 파일에도 저장됩니다. 해당 파일을 수동으로 편집하지 않는 것이 좋습니다. 대신 MSBuild에 대한 깊은 이해가 없는 한 IDE의 속성 페이지를 사용하여 상속에 참여하는 모든 속성, 특히 속성을 수정합니다.

앞에 설명한 것처럼 다른 파일에서 다른 값이 동일한 구성에 대한 동일한 속성에 할당될 수 있습니다. 프로젝트를 빌드하면 MSBuild 엔진은 올바로 정의된 순서대로(아래 설명 참조) 프로젝트 파일 및 가져온 모든 파일을 평가합니다. 각 파일을 평가하기 때문에 해당 파일에서 정의된 모든 속성 값이 기존 값을 재정의합니다. 지정되지 않은 모든 값은 이전에 평가된 파일에서 상속됩니다. 속성 페이지가 있는 속성을 설정할 때는 속성을 설정한 위치에 주의를 기울이는 것도 중요합니다. *`.props`* 파일에서 속성을 "X"로 설정하지만 속성이 프로젝트 파일에서 "Y"로 설정된 경우 프로젝트는 속성이 "Y"로 설정된 것으로 빌드됩니다. *`.cpp`* 파일과 같은 프로젝트 항목에서 동일한 속성이 "Z"로 설정된 경우 MSBuild 엔진은 "Z" 값을 사용합니다.

다음은 기본 상속 트리입니다.

1. MSBuild CPP 도구 집합의 기본 설정(.) \프로그램 파일\MSBuild\Microsoft.Cpp\v4.0\Microsoft.Cpp.Default.props, *`.vcxproj`* 파일에서 가져온.)

1. 속성 시트

1. *`.vcxproj`* 파일. 기본 및 속성 시트 설정을 재정의할 수 있습니다.

1. 항목 메타데이터

> [!TIP]
> 속성 페이지에서 **굵은 속성은** 현재 컨텍스트에서 정의됩니다. 일반 글꼴의 속성이 상속됩니다.

## <a name="view-an-expanded-project-file-with-all-imported-values"></a>가져온 모든 값으로 확장된 프로젝트 파일 보기

확장된 파일을 보고 지정된 속성 값의 상속 방법을 결정하는 것이 유용한 경우도 있습니다. 확장 버전을 보려면 Visual Studio 명령 프롬프트에서 다음 명령을 입력합니다. 자리 표시자 파일 이름을 사용할 이름으로 변경합니다.

> **msbuild /pp:**_temp_**.txt** _myapp_**.vcxproj**

MSBuild에 익숙하지 않으면 확장된 프로젝트 파일이 크고 이해하기 어려울 수 있습니다. 프로젝트 파일의 기본 구조는 다음과 같음:

1. IDE에 노출되지 않는 기본 프로젝트 속성입니다.

1. 도구 *`Microsoft.cpp.default.props`* 집합독립적 속성을 정의하는 의 가져오기입니다.

1. 전역 구성 **속성(구성 일반** 페이지에서 **PlatformToolset** 및 **프로젝트** 기본 속성으로 노출됨) 이러한 속성은 다음 단계에서 가져올 *`Microsoft.cpp.props`* 도구 집합 및 내장 속성 시트를 결정합니다.

1. 프로젝트 *`Microsoft.cpp.props`* 기본값의 대부분을 설정하는 을 가져옵니다.

1. 파일을 포함한 *`.user`* 모든 속성 시트가져오기. 이러한 속성 시트는 **PlatformToolset** 및 **Project** 기본 속성을 제외한 모든 것을 재정의할 수 있습니다.

1. 나머지 프로젝트 구성 속성입니다. 이러한 값은 속성 시트에서 설정된 것을 재정의할 수 있습니다.

1. 메타데이터와 함께 있는 항목(파일)입니다. 이러한 항목은 다른 속성 및 가져오기 전에 발생 하는 경우에 항상 MSBuild 평가 규칙에서 마지막 단어입니다.

자세한 내용은 [MSBuild 속성을](/visualstudio/msbuild/msbuild-properties)참조하십시오.

## <a name="build-configurations"></a>빌드 구성

구성은 이름이 지정된 속성의 임의의 그룹입니다. Visual Studio는 디버그 및 릴리스 구성을 제공합니다. 각 속성은 디버그 빌드 또는 릴리스 빌드에 맞게 다양한 속성을 설정합니다. **구성 관리자를** 사용하여 사용자 지정 구성을 정의할 수 있습니다. 빌드의 특정 맛에 대 한 속성을 그룹화 하는 편리한 방법입니다.

빌드 구성에 대한 더 나은 아이디어를 얻으려면 **속성 관리자를**엽니다. 설정에 따라 **보기 > 속성 관리자** 또는 보기 > 다른 Windows > 속성 **관리자를**선택 하여 열 수 있습니다. **속성 관리자는** 프로젝트의 각 구성 및 플랫폼 쌍에 대한 노드를 가있습니다. 이러한 각 노드 아래에는 해당 구성에*`.props`* 대한 특정 속성을 설정하는 속성 시트(파일)에 대한 노드가 있습니다.

![속성 관리자](media/property-manager.png "속성 관리자")

예를 들어 속성 페이지의 일반 창으로 이동할 수 있습니다. 문자 집합 속성을 "유니코드 사용" 대신 "설정 안 않음"으로 변경한 다음 **확인을**클릭합니다. 이제 속성 관리자에 **유니코드 지원** 속성 시트가 표시되지 않습니다. 현재 구성에 대해 제거되었지만 다른 구성에 대해여전히 존재합니다.

속성 관리자 및 속성 시트에 대한 자세한 정보는 [Visual Studio C++ 프로젝트 설정 공유 또는 다시 사용](create-reusable-property-configurations.md)을 참조하세요.

> [!TIP]
> 이 *`.user`* 파일은 레거시 기능입니다. 구성 및 플랫폼에 따라 속성을 올바르게 그룹화하려면 속성을 삭제하는 것이 좋습니다.
