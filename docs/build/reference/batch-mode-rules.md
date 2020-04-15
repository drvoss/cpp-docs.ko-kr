---
title: 일괄 처리 모드 규칙
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
ms.openlocfilehash: 38402e7b8a937cebb823ce13fa1ac01fc1099878
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328407"
---
# <a name="batch-mode-rules"></a>일괄 처리 모드 규칙

```
{frompath}.fromext{topath}.toext::
   commands
```

일괄 처리 모드 추론 규칙은 N 명령이 이 추론 규칙을 통과할 때 추론 규칙을 하나만 호출합니다. 일괄 처리 모드 추론 규칙이 없으면 N 명령을 호출해야 합니다. N은 추론 규칙을 트리거하는 종속 인의 수입니다.

일괄 처리 모드 추론 규칙이 포함된 Makefiles는 NMAKE 버전 1.62 이상을 사용해야 합니다. NMAKE 버전을 확인하려면 NMAKE 버전 1.62 이상에서 사용할 수 있는 _NMAKE_VER 매크로를 실행합니다. 이 매크로는 Visual C++ 제품 버전을 나타내는 문자열을 반환합니다.

표준 추론 규칙의 유일한 구문적 차이점은 일괄 처리 모드 추론 규칙이 이중 콜론(::)으로 종료된다는 것입니다.

> [!NOTE]
> 호출되는 도구는 여러 파일을 처리할 수 있어야 합니다. 일괄 처리 모드 추론 규칙은 `$<` 종속 파일에 액세스하기 위해 매크로로 사용해야 합니다.

일괄 처리 모드 추론 규칙은 빌드 프로세스의 속도를 높일 수 있습니다. 컴파일러 드라이버가 한 번만 호출되므로 일괄 적으로 컴파일러에 파일을 제공하는 것이 더 빠릅니다. 예를 들어 C 및 C++ 컴파일러는 프로세스 중에 메모리상주체로 남을 수 있으므로 파일 집합을 처리할 때 더 나은 성능을 발휘합니다.

다음 예제에서는 일괄 처리 모드 추론 규칙을 사용하는 방법을 보여 주십입니다.

```
#
# sample makefile to illustrate batch-mode inference rules
#
O = .
S = .
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj
CFLAGS = -nologo

all : $(Objs)

!ifdef NOBatch
{$S}.cpp{$O}.obj:
!else
{$S}.cpp{$O}.obj::
!endif
   $(CC) $(CFLAGS) -Fd$O\ -c $<

$(Objs) :

#end of makefile
```

NMAKE는 일괄 처리 모드 추론 규칙 없이 다음과 같은 출력을 생성합니다.

```
E:\tmp> nmake -f test.mak -a NOBatch=1

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.
        cl -nologo -Fd.\ -c .\foo1.cpp
foo1.cpp
        cl -nologo -Fd.\ -c .\foo2.cpp
foo2.cpp
        cl -nologo -Fd.\ -c .\foo3.cpp
foo3.cpp
        cl -nologo -Fd.\ -c .\foo4.cpp
foo4.cpp
```

NMAKE는 일괄 처리 모드 추론 규칙을 사용하여 다음과 같은 결과를 생성합니다.

```
E:\tmp> nmake -f test.mak -a

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.

        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp
foo1.cpp
foo2.cpp
foo3.cpp
foo4.cpp
Generating Code...
```

## <a name="see-also"></a>참고 항목

[추론 규칙](inference-rules.md)
