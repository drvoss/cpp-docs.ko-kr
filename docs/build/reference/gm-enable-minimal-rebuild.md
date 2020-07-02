---
title: /Gm(최소 다시 빌드 사용)
ms.date: 11/12/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
ms.openlocfilehash: 9b928f3add0a2ec10257bf63fe61a824336c19b8
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439637"
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm(최소 다시 빌드 사용)

사용되지 않습니다. 변경된 C++ 클래스 정의(헤더 파일(.h)에 저장됨)가 포함된 C++ 소스 파일을 다시 컴파일해야 할지 여부를 결정하는 최소 다시 빌드가 가능하도록 설정합니다.

## <a name="syntax"></a>구문

```
/Gm
```

## <a name="remarks"></a>설명

**/Gm** 은 사용 되지 않습니다. 특정 유형의 헤더 파일 변경에 대해 빌드를 트리거하지 않을 수도 있습니다. 프로젝트에서 이 옵션을 안전하게 제거할 수 있습니다. 빌드 시간을 개선하기 위해서는 미리 컴파일된 헤더와 증분 및 병렬 빌드 옵션을 사용하는 것이 좋습니다. 사용 되지 않는 컴파일러 옵션의 목록은 [컴파일러 옵션 범주별 목록](compiler-options-listed-by-category.md)에서 **사용 되지 않는 컴파일러 옵션** 섹션을 참조 하세요.

컴파일러는 처음 컴파일 중 소스 파일과 .idb 파일의 클래스 정의 간의 종속성 정보를 저장합니다. 종속성 정보는 어떤 소스 파일이 어떤 클래스 정의에 종속되어 있는지 그리고 어떤 .h 파일에 정의가 위치해 있는지 알려줍니다. 소스 파일에 수정된 .h 파일이 포함되어 있는 경우라도 후속 컴파일에서는 .idb 파일에 저장된 정보를 사용하여 소스 파일을 컴파일해야 할지를 결정합니다.

> [!NOTE]
> 최소 다시 빌드는 포함 파일 간에 변경되지 않는 클래스 정의를 사용합니다. .idb 파일의 종속성 정보가 전체 프로젝트에 대해 생성되기 때문에 클래스 정의는 프로젝트에 대해 전역적이어야 합니다(한 클래스의 정의는 하나만 있어야 합니다). 프로젝트에 클래스 정의가 둘 이상 있는 경우 최소 다시 빌드를 비활성화하세요.

증분 링커는 [/ZW (Windows 런타임 컴파일)](zw-windows-runtime-compilation.md) 옵션을 사용하여 .obj 파일에 포함된 Windows 메타 데이터를 지원하지 않으므로 **/Gm** 옵션은 **/ZW**와 호환되지 않습니다.

증분 링커는 [/zw (Windows 런타임 컴파일)](zw-windows-runtime-compilation.md) 옵션을 사용 하 여 .obj 파일에 포함 된 Windows 메타 데이터를 지원 하지 않으므로 **/Gm** 옵션은 **/zw**와 호환 되지 않습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **CC++ /**  > **코드 생성** 속성 페이지를 선택 합니다.

1. **최소 다시 빌드 사용** 속성을 수정 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
