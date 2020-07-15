---
title: '방법: 사용자 지정 도구를 프로젝트 속성에 통합'
ms.date: 05/16/2019
helpviewer_keywords:
- 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
ms.openlocfilehash: 5a96ffd15bb28022b3000252307c75b3383ac59c
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373751"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>방법: 사용자 지정 도구를 프로젝트 속성에 통합

기본 XML 스키마 파일을 만들어 Visual Studio **속성 페이지** 창에 사용자 지정 도구 옵션을 추가할 수 있습니다.

**속성 페이지** 창의 **구성 속성** 섹션은 *규칙*이라고 하는 설정 그룹을 표시합니다. 모든 규칙에는 도구 또는 기능 그룹에 대한 설정이 포함됩니다. 예를 들어 **링커** 규칙은 링커 도구에 대한 설정을 포함합니다. 규칙의 설정은 *범주*로 세분화할 수 있습니다.

이 문서에서는 Visual Studio를 시작할 때 속성이 로드되도록 사용자 지정 도구에 대한 속성을 포함하는 설정 디렉터리에 파일을 만드는 방법을 설명합니다. 파일을 수정하는 방법에 대한 자세한 내용은 Visual Studio Project Team 블로그에서 [플랫폼 확장성 2부](https://docs.microsoft.com/archive/blogs/vsproject/platform-extensibility-part-2)를 참조하십시오.

### <a name="to-add-or-change-project-properties"></a>프로젝트 속성을 추가하거나 변경하려면

1. XML 편집기에서 XML 파일을 만듭니다.

1. Visual Studio `VCTargets\1033` 폴더에 파일을 저장합니다. 설치된 각 Visual Studio의 버전과 각각의 언어에 대해 경로가 다릅니다. 예를 들어, Visual Studio 2019 Community 영어 버전의 기본 폴더 경로는 `C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\VC\VCTargets`입니다. 언어와 Visual Studio 버전에 맞게 경로를 조정합니다. **속성 페이지** 창의 모든 규칙은 이 폴더에서 XML 파일로 표시됩니다. 파일의 이름은 폴더 내에서 고유해야 합니다.

1. `%ProgramFiles%\Microsoft Visual Studio\2019\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`(또는 해당 경로)의 콘텐츠를 복사하고, 변경 내용을 저장하지 않고 닫은 다음, 새 XML 파일에 콘텐츠를 붙여넣습니다. 단순히 템플릿을 사용하여 시작하기 위한 용도이므로 아무 XML 스키마 파일이나 사용할 수 있습니다.

1. 새 XML 파일에서 요구 사항에 따라 콘텐츠를 수정합니다. 파일 맨 위의 **규칙 이름**과 **Rule.DisplayName**을 변경해야 합니다.

1. 변경 내용을 저장하고 파일을 닫습니다.

1. Visual Studio를 시작하면 `%ProgramFiles%\Microsoft Visual Studio\2019\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>`(또는 저장한 위치)의 XML 파일이 로드됩니다. 따라서 새 파일을 테스트하려면 Visual Studio를 다시 시작합니다.

1. **솔루션 탐색기**에서 프로젝트를 오른쪽 마우스 단추로 클릭하고 **속성**을 클릭합니다. **속성 페이지** 창의 왼쪽 창에 해당 규칙 이름이 있는 새 노드가 있는지 확인합니다.

## <a name="see-also"></a>참조

[명령줄의 MSBuild - C++](msbuild-visual-cpp.md)
