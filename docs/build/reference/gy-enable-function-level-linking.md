---
title: /Gy(함수 수준 링크 사용)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
ms.openlocfilehash: 8724ae4d018948c0f6aa9456f229db96878d7bf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328276"
---
# <a name="gy-enable-function-level-linking"></a>/Gy(함수 수준 링크 사용)

컴파일러가 개별 함수를 패키지된 함수(COMDAT)의 형태로 패키지할 수 있게 합니다.

## <a name="syntax"></a>구문

```
/Gy[-]
```

## <a name="remarks"></a>설명

링커는 DLL 또는 .exe 파일에서 개별 함수를 제외하거나 주문하기 위해 COMDAT로 함수를 별도로 패키징해야 합니다.

링커 [옵션/OPT(최적화)를](opt-optimizations.md) 사용하여 .exe 파일에서 참조되지 않은 패키지 함수를 제외할 수 있습니다.

링커 옵션 [/ORDER(함수 순서대로 넣기)를](order-put-functions-in-order.md) 사용하여 .exe 파일에 지정된 순서로 패키지된 함수를 포함할 수 있습니다.

인라인 함수는 호출로 인스턴스화되는 경우 항상 패키징됩니다(예: 인라이닝이 꺼져 있거나 함수 주소를 가져가는 경우). 또한 클래스 선언에 정의된 C++ 멤버 함수는 자동으로 패키지됩니다. 다른 함수는 그렇지 않으며 패키지된 함수로 컴파일하려면 이 옵션을 선택하는 것이 필요합니다.

> [!NOTE]
> 편집 및 계속에 사용되는 [/ZI](z7-zi-zi-debug-information-format.md) 옵션은 자동으로 **/Gy** 옵션을 설정합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **C/C++** 폴더를 클릭합니다.

1. 코드 생성 속성 페이지를 **클릭합니다.**

1. 함수 수준 연결 활성화 속성을 **수정합니다.**

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
