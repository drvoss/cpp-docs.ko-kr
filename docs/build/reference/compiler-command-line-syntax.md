---
title: MSVC 컴파일러 명령줄 구문
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
ms.openlocfilehash: 6a56474b537d78a3d0bea8a74d9082007cd2e295
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320539"
---
# <a name="compiler-command-line-syntax"></a>컴파일러 명령줄 구문

CL 명령줄은 다음 구문을 사용합니다.

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

다음 표는 CL 명령에 대한 입력에 대해 설명합니다.

|항목|의미|
|-----------|-------------|
|*옵션*|하나 이상의 [CL 옵션](compiler-options.md). 모든 옵션은 지정된 모든 원본 파일에 적용됩니다. 옵션은 정방향 슬래시(/) 또는 대시(-)로 지정됩니다. 옵션이 인수를 취하는 경우 옵션의 설명은 옵션과 인수 사이에 공백이 허용되는지 여부를 문서화합니다. 옵션 이름(/HELP 옵션 제외)은 대/소문자를 구분합니다. 자세한 내용은 [CL 옵션 순서를](order-of-cl-options.md) 참조하십시오.|
|`file`|하나 이상의 소스 파일, .obj 파일 또는 라이브러리의 이름입니다. CL은 소스 파일을 컴파일하고 .obj 파일 및 라이브러리의 이름을 링커에 전달합니다. 자세한 내용은 [CL 파일 이름 구문을](cl-filename-syntax.md) 참조하십시오.|
|*Lib*|하나 이상의 라이브러리 이름입니다. CL은 이러한 이름을 링커에 전달합니다.|
|*명령 파일*|여러 옵션과 파일 이름이 포함된 파일입니다. 자세한 내용은 [CL 명령 파일을](cl-command-files.md) 참조하십시오.|
|*링크 옵트*|하나 이상의 [MSVC 링커 옵션](linker-options.md). CL은 이러한 옵션을 링커에 전달합니다.|

명령줄의 문자 수가 1024를 초과하지 않는 한 운영 체제에서 지정한 제한만큼 옵션, 파일 이름 및 라이브러리 이름을 지정할 수 있습니다.

cl.exe의 반환 값에 대한 자세한 내용은 [cl.exe의 반환 값을](return-value-of-cl-exe.md) 참조하십시오.

> [!NOTE]
> 1024자의 명령줄 입력 제한은 Windows의 향후 릴리스에서 동일하게 유지될 수 없습니다.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)
