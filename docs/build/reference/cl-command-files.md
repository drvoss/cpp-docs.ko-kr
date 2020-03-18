---
title: CL 명령 파일
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, command files
- command files
- command files, CL compiler
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
ms.openlocfilehash: 1dc2d6bffe4d0681a04b875383215a0bbfc1a720
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440257"
---
# <a name="cl-command-files"></a>CL 명령 파일

명령 파일은 [명령줄](compiler-command-line-syntax.md) 에 입력 하거나 [CL 환경 변수](cl-environment-variables.md)를 사용 하 여 지정 하는 옵션과 파일 이름이 포함 된 텍스트 파일입니다. CL은 컴파일러 명령 파일을 CL 환경 변수 또는 명령줄에서 인수로 받아들입니다. 명령줄이나 CL 환경 변수와는 달리 명령 파일을 사용하면 여러 줄로 구성된 옵션과 파일 이름을 사용할 수 있습니다.

명령 파일의 옵션 및 파일 이름은 CL 환경 변수 또는 명령줄에서 명령 파일 이름의 위치에 따라 처리 됩니다. 그러나/link 옵션이 명령 파일에 표시 되는 경우 줄의 나머지 부분에 있는 모든 옵션이 링커에 전달 됩니다. 명령 파일의 다음 줄에 있는 옵션과 명령 파일 호출 후 명령줄의 옵션은 여전히 컴파일러 옵션으로 수락 됩니다. 옵션 순서가 해석에 주는 영향에 대 한 자세한 내용은 [CL 옵션 순서](order-of-cl-options.md)를 참조 하세요.

명령 파일에는 CL 명령이 포함 되지 않아야 합니다. 각 옵션은 같은 줄에서 시작 하 고 끝나야 합니다. 백슬래시 ( **\\** )를 사용 하 여 옵션을 두 줄로 결합할 수 없습니다.

명령 파일은 at 기호 ( **\@** ) 뒤에 파일 이름으로 지정 됩니다. 파일 이름에는 절대 경로 또는 상대 경로를 지정할 수 있습니다.

예를 들어 다음 명령은 응답 라는 파일에 있습니다.

```
/Og /link LIBC.LIB
```

다음 CL 명령을 지정 합니다.

```
CL /Ob2 @RESP MYAPP.C
```

CL 명령은 다음과 같습니다.

```
CL /Ob2 /Og MYAPP.C /link LIBC.LIB
```

명령줄과 명령 파일 명령은 효과적으로 결합 되어 있습니다.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)
