---
title: CL 환경 변수
ms.date: 06/06/2019
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 4d6b1982b1e544459a025d6cb7bee75666e7130e
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440250"
---
# <a name="cl-environment-variables"></a>CL 환경 변수

CL 도구는 다음과 같은 환경 변수를 사용합니다.

- CL 및 \_CL_ (정의 된 경우). CL 도구는 CL 환경 변수에 정의 된 옵션 및 인수를 명령줄 인수 앞에 추가 하 고, 처리 하기 전에 \_CL_에 정의 된 옵션 및 인수를 추가 합니다.

- Visual Studio 설치의 \include 하위 디렉터리를 가리켜야 하는를 포함 합니다.

- LIBPATH- [#using](../../preprocessor/hash-using-directive-cpp.md)에서 참조 되는 메타 데이터 파일을 검색할 디렉터리를 지정 합니다. LIBPATH에 대 한 자세한 내용은 [#using](../../preprocessor/hash-using-directive-cpp.md)를 참조 하세요.

다음 구문을 사용 하 여 CL 또는 \_CL_ 환경 변수를 설정할 수 있습니다.

> SET CL = [[*옵션*] ... [*file*] ...] [/link *링크-opt* ...] \
> \_CL\_= [[*옵션*]을 설정 합니다. [*file*] ...] [/link *링크-opt* ...]

CL 및 \_CL_ 환경 변수에 대 한 인수에 대 한 자세한 내용은 [MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)을 참조 하세요.

이러한 환경 변수를 사용 하 여 자주 사용 하는 파일 및 옵션을 정의할 수 있습니다. 그런 다음 명령줄을 사용 하 여 특정 용도에 대 한 추가 파일 및 옵션을 CL에 제공 합니다. CL 및 \_CL_ 환경 변수는 1024 자로 제한 됩니다 (명령줄 입력 제한).

[/D](d-preprocessor-definitions.md) 옵션을 사용 하 여 등호 ( **=** )를 사용 하는 기호를 정의할 수 없습니다. 대신 등호 기호에 숫자 기호 ( **#** )를 사용할 수 있습니다. 이러한 방식으로 CL 또는 \_CL_ 환경 변수를 사용 하 여 명시적 값으로 전처리기 상수를 정의할 수 있습니다 (예: `/DDEBUG#1` `DEBUG=1`정의).

관련 정보는 [환경 변수 설정](../setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조 하세요.

## <a name="examples"></a>예

다음 명령은 CL 환경 변수를 설정 하는 예입니다.

> SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ

CL 환경 변수를 설정 하는 경우 명령줄에 `CL INPUT.C`를 입력 하면 유효 명령이 다음과 같이 됩니다.

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C

다음 예제에서는 일반 CL 명령을 사용하여 소스 파일 FILE1.c 및 FILE2.c를 컴파일한 다음 개체 파일 FILE1.obj, FILE2.obj 및 FILE3.obj를 연결합니다.

> SET CL=FILE1.C FILE2.C \
> \_CL_ = FILE3을 설정 합니다. 인스턴스인
> CL

이러한 환경 변수를 사용 하면 CL 호출은 다음 명령줄과 동일한 효과를 가집니다.

> CL FILE1.C FILE2.C FILE3.OBJ

## <a name="see-also"></a>참고 항목

[컴파일러 옵션 설정](compiler-command-line-syntax.md) \
[MSVC 컴파일러 옵션](compiler-options.md)
