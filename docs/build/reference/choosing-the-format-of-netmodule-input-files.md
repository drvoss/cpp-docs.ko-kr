---
title: .netmodule 입력 파일 형식 선택
ms.date: 11/04/2016
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
ms.openlocfilehash: b4d4b80e4b9195d184b9d97cea67bbaaa3d7d843
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320570"
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>.netmodule 입력 파일 형식 선택

MSIL .obj [파일(/clr로](clr-common-language-runtime-compilation.md)컴파일)도 .netmodule 파일로 사용할 수 있습니다.  .obj 파일에는 메타데이터 및 네이티브 기호가 포함되어 있습니다.  .netmodules에는 메타데이터만 포함됩니다.

MSIL .obj 파일을 /addmodule 컴파일러 옵션을 통해 다른 Visual Studio 컴파일러에 전달할 수 있습니다(하지만 .obj 파일은 결과 어셈블리의 일부가 되고 어셈블리와 함께 제공되어야 합니다).  예를 들어 Visual C# 및 Visual Basic에는 /addmodule 컴파일러 옵션이 있습니다.

> [!NOTE]
> 대부분의 경우 .net 모듈을 생성한 컴파일로부터 가져온 .obj 파일을 링커에 전달해야 합니다.  .dll 또는 .netmodule MSIL 모듈 파일을 링커에 전달하면 LNK1107이 발생할 수 있습니다.

소스에서 #include를 통해 참조하는 연결된 .h 파일과 함께 .obj 파일은 C++ 애플리케이션이 모듈에서 고유 형식을 사용할 수 있도록 허용하며, 반면에 .netmodule 파일에서는 C++ 애플리케이션이 관리되는 형식만 사용할 수 있습니다.  #using .obj 파일을 전달하려고 하면 네이티브 형식에 대한 정보를 사용할 수 없습니다. 대신 .obj 파일의 .h 파일을 #include.

다른 Visual Studio 컴파일러는 모듈에서 관리되는 형식만 사용할 수 있습니다.

다음을 사용하여 .netmodule 또는 .obj 파일을 MSVC 링커에 대한 모듈 입력으로 사용해야 하는지 여부를 결정합니다.

- Visual C++ 이외의 Visual Studio 컴파일러로 빌드하는 경우 .netmodule을 생성하고 .netmodule을 링커에 대한 입력으로 사용합니다.

- MSVC 컴파일러를 사용하여 모듈을 생성하는 경우 모듈이 라이브러리 이외의 것을 빌드하는 데 사용되는 경우 컴파일러에서 생성한 .obj 파일을 링커에 대한 모듈 입력으로 사용합니다. .netmodule 파일을 입력으로 사용하지 마십시오.

- 모듈을 사용하여 관리되지 않는 네이티브 라이브러리를 작성하는 경우 .obj 파일을 링커에 대한 모듈 입력으로 사용하고 .lib 라이브러리 파일을 생성합니다.

- 모듈이 관리되는 라이브러리를 빌드하는 데 사용되고 링커에 대한 모든 모듈 입력을 확인할 수 있는 경우(/clr:safe로 생성), .obj 파일을 링커에 대한 모듈 입력으로 사용하고 .dll(어셈블리) 또는 .netmodule(모듈) 라이브러리 파일을 생성합니다.

- 모듈이 관리되는 라이브러리를 구축하는 데 사용되고 링커에 입력된 모듈이 /clr로 생성되는 경우 .obj 파일을 링커에 대한 모듈 입력으로 사용하고 .dll(어셈블리)을 생성합니다.  라이브러리에서 관리되는 형식을 노출하려는 경우 C++ 응용 프로그램이 라이브러리의 기본 형식을 사용하려는 경우 라이브러리는 라이브러리 구성 요소 모듈에 대한 .obj 파일로 구성됩니다(각 모듈에 대해 .h 파일을 제공하여 소스 코드에서 #include 참조할 수도 있습니다).

## <a name="see-also"></a>참고 항목

[링커 입력 파일로 사용하는 .netmodule 파일](netmodule-files-as-linker-input.md)
