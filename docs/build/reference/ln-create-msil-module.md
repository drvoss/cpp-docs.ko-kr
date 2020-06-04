---
title: /LN(MSIL 모듈 만들기)
ms.date: 11/04/2016
f1_keywords:
- /LN
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
ms.openlocfilehash: 2dbd5ae5ddf802185912c49caf37aa61c6a7d4c3
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446268"
---
# <a name="ln-create-msil-module"></a>/LN(MSIL 모듈 만들기)

어셈블리 매니페스트가 출력 파일에 삽입되지 않도록 지정합니다.

## <a name="syntax"></a>구문

```
/LN
```

## <a name="remarks"></a>설명

기본적으로 **/LN**은 적용되지 않습니다(어셈블리 매니페스트가 출력 파일에 삽입됩니다).

**/LN**을 사용하면 [/clr(공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md) 옵션 중 하나를 사용해야 합니다.

매니페스트에 어셈블리 메타데이터가 없는 관리되는 프로그램을 모듈이라고 합니다. [/c(링크 없이 컴파일)](c-compile-without-linking.md) 및 **/LN**을 지정하여 컴파일하는 경우 링커 단계에서 [/NOASSEMBLY(MSIL 모듈 만들기)](noassembly-create-a-msil-module.md)를 지정하여 출력 파일을 만듭니다.

어셈블리를 작성할 때 구성요소 기반 접근 방식을 사용하려는 경우 모듈을 만들 수 있습니다. 즉, 형식을 작성하고 모듈로 컴파일할 수 있습니다. 그런 다음 하나 이상의 모듈에서 어셈블리를 생성할 수 있습니다. 모듈에서 어셈블리를 만드는 방법에 대한 자세한 내용은 [링커 입력의 .netmodule 파일](netmodule-files-as-linker-input.md)이나 [Al.exe(어셈블리 링커)](/dotnet/framework/tools/al-exe-assembly-linker)를 참조합니다.

모듈의 기본 파일 확장명은 .netmodule입니다.

Visual Studio 2005 이전 버전에서는 **/clr:noAssembly**를 사용하여 모듈을 만듭니다.

MSVC 링커는 .netmodule 파일을 입력으로 받고 링커에서 만들어진 출력 파일은 링커에 입력된 .netmodule로 런타임 종속성이 없는 어셈블리나 .ntmodules가 됩니다. 자세한 내용은 [링커 입력 파일로 사용하는 .netmodule 파일](netmodule-files-as-linker-input.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

- 지정할 [/NOASSEMBLY (MSIL 모듈 만들기)](noassembly-create-a-msil-module.md) 링커 단계 출력 파일을 만듭니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- 이 컴파일러 옵션을 프로그래밍 방식으로 변경할 수 없습니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
