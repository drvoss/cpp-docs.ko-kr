---
title: 설명 블록
description: NMAKE는 설명 블록을 사용하여 메이크파일에서 대상, 종속성 및 명령을 연결합니다.
ms.date: 10/29/2019
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
ms.openlocfilehash: e4e80b59d3d30b3b34c55b40d337ef5c078e6404
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322254"
---
# <a name="description-blocks"></a>설명 블록

설명 블록은 메이크파일의 핵심을 형성합니다. 만들 *대상*또는 파일을 만들고 대상을 만드는 데 필요한 파일의 *종속성에*대해 설명합니다. 설명 블록에는 종속성에서 대상을 만드는 방법을 설명하는 *명령이*포함될 수 있습니다. 설명 블록은 종속성 줄이며, 선택적으로 명령 블록 다음에 있습니다.

```makefile
targets... : dependents...
    commands...
```

## <a name="dependency-lines"></a>종속성 선

*종속성 선은* 하나 이상의 대상과 0 개 이상의 종속 대상을 지정합니다. 대상이 존재하지 않거나 종속 보다 이전 타임스탬프가 있는 경우 NMAKE는 명령 블록에서 명령을 실행합니다. 또한 NMAKE는 대상이 [의사 대상인](pseudotargets.md)경우 명령 블록을 실행합니다. 다음은 종속성 의 예입니다.

```makefile
hi_bye.exe : hello.obj goodbye.obj helper.lib
```

이 종속성 줄에서 `hi_bye.exe` 대상입니다. 해당 종속성은 `hello.obj`" `goodbye.obj`및 `helper.lib` 종속성 줄은 NMAKE가 에 보다 `hello.obj` `hi_bye.exe` `goodbye.obj`최근에 `helper.lib` 변경되었거나 할 때마다 대상을 빌드하도록 지시합니다.

대상은 줄의 시작 부분에 있어야 합니다. 공백이나 탭으로 들여쓰기할 수 없습니다. 콜론 ()`:`을 사용하여 대상을 종속 대상과 분리합니다. 공백 또는 탭은 대상, 콜론 구분 기호()`:`및 종속자 간에 허용됩니다. 종속성 선을 분할하려면 대상 또는 종속`\`후 백슬래시() 를 사용합니다.

명령 블록을 실행하기 전에 NMAKE는 모든 종속성 및 적용 가능한 추론 규칙을 검사하여 *종속성 트리를*작성합니다. 종속성 트리는 대상을 완전히 업데이트하는 데 필요한 단계를 지정합니다. NMAKE는 종속이 다른 종속성 목록의 대상인지 여부를 재귀적으로 확인합니다. 종속성 트리를 빌드한 후 NMAKE는 타임스탬프를 확인합니다. 트리의 종속자가 대상보다 최신 종속인 경우 NMAKE는 대상을 빌드합니다.

## <a name="targets"></a><a name="targets"></a>대상

종속성 선의 대상 섹션은 하나 이상의 대상을 지정합니다. 대상은 유효한 파일 이름, 디렉터리 이름 또는 [의사 대상일](pseudotargets.md)수 있습니다. 하나 이상의 공백 이나 탭을 사용 하 여 여러 대상을 분리 합니다. 대상은 대/소문자를 구분하지 않습니다. 경로는 파일 이름으로 허용됩니다. 대상과 경로는 256자를 초과할 수 없습니다. 콜론 앞에 있는 대상이 단일 문자인 경우 분리 공간을 사용합니다. 그렇지 않으면 NMAKE는 문자 콜론 조합을 드라이브 지정자로 해석합니다.

### <a name="multiple-targets"></a><a name="multiple-targets"></a>여러 대상

NMAKE는 단일 종속성에서 여러 대상을 별도의 설명 블록에 각각 지정된 것처럼 평가합니다.

예를 들어 이 규칙은 다음과 같은 것입니다.

```makefile
bounce.exe leap.exe : jump.obj
   echo Building...
```

다음과 같이 평가됩니다.

```makefile
bounce.exe : jump.obj
   echo Building...

leap.exe : jump.obj
   echo Building...
```

### <a name="cumulative-dependencies"></a><a name="cumulative-dependencies"></a>누적 종속성

대상이 반복되는 경우 종속성은 설명 블록에서 누적됩니다.

예를 들어, 이 규칙 집합은

```makefile
bounce.exe : jump.obj
bounce.exe : up.obj
   echo Building bounce.exe...
```

다음과 같이 평가됩니다.

```makefile
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

단일 설명 블록에 여러 종속성 줄에 여러 대상이 있는 경우 NMAKE는 각각 별도의 설명 블록에 지정된 것처럼 평가합니다. 그러나 마지막 종속성 줄의 대상만 명령 블록을 사용합니다. NMAKE는 다른 대상에 대한 추론 규칙을 사용하려고 시도합니다.

예를 들어, 이 규칙 집합은

```makefile
leap.exe bounce.exe : jump.obj
bounce.exe climb.exe : up.obj
   echo Building bounce.exe...
```

다음과 같이 평가됩니다.

```makefile
leap.exe : jump.obj
# invokes an inference rule

bounce.exe : jump.obj up.obj
   echo Building bounce.exe...

climb.exe : up.obj
   echo Building bounce.exe...
```

### <a name="targets-in-multiple-description-blocks"></a><a name="targets-in-multiple-description-blocks"></a>여러 설명 블록의 대상

서로 다른 명령을 사용하여 둘 이상의 설명 블록에서 대상을 업데이트하려면 두 개의 연속된 콜론(::)을 지정합니다. 대상과 부양 가족 사이.

```makefile
target.lib :: one.asm two.asm three.asm
    ml one.asm two.asm three.asm
    lib target one.obj two.obj three.obj
target.lib :: four.c five.c
    cl /c four.c five.c
    lib target four.obj five.obj
```

### <a name="dependency-side-effects"></a><a name="dependency-side-effects"></a>종속성 부작용

콜론(:)있는 대상을 지정할 수 있습니다. 서로 다른 위치에 있는 두 개의 종속성 줄에 있습니다. 명령이 줄 중 하나 후에만 나타나는 경우 NMAKE는 종속성을 줄이 인접하거나 결합된 것처럼 해석합니다. 명령이 없는 종속성에 대한 추론 규칙을 호출하지 않습니다. 대신 NMAKE는 종속성이 한 설명 블록에 속한다고 가정하고 다른 종속성으로 지정된 명령을 실행합니다. 다음 규칙 집합을 고려하십시오.

```makefile
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
```

다음과 같이 평가됩니다.

```makefile
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

이 효과는 이중 콜론()을`::`사용하는 경우에는 발생하지 않습니다. 예를 들어, 이 규칙 집합은 다음과 같은 것입니다.

```makefile
bounce.exe :: jump.obj
   echo Building bounce.exe...

bounce.exe :: up.obj
```

다음과 같이 평가됩니다.

```makefile
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
# invokes an inference rule
```

### <a name="pseudotargets"></a><a name="pseudotargets"></a>의사 대상

*의사 대상은* 종속성 줄의 파일 이름 대신 사용되는 레이블입니다. 존재하지 않는 파일로 해석되며 오래된 파일입니다. NMAKE는 의사 대상의 타임스탬프가 모든 부양 가족의 가장 최근과 동일하다고 가정합니다. 종속 가족이 없는 경우 현재 시간이 가정됩니다. 의사 대상을 대상으로 사용하는 경우 해당 명령은 항상 실행됩니다. 종속으로 사용되는 의사 대상도 다른 종속성의 대상으로 나타나야 합니다. 그러나 해당 종속성에는 명령 블록이 필요하지 않습니다.

의사 대상 이름은 대상에 대한 파일 이름 구문 규칙을 따릅니다. 그러나 이름에 확장명이 없는 경우 파일 이름에 대한 8자 제한을 초과할 수 있으며 최대 256자까지 길 수 있습니다.

의사 대상은 NMAKE가 둘 이상의 대상을 자동으로 빌드하려는 경우에 유용합니다. NMAKE는 명령줄에 지정된 대상만 빌드합니다. 또는 명령줄 대상이 지정되지 않은 경우 makefile의 첫 번째 종속성의 첫 번째 대상만 빌드합니다. NMAKE는 명령줄에 개별적으로 나열하지 않고 여러 대상을 빌드하도록 지시할 수 있습니다. 의사 대상을 포함하는 종속성으로 설명 블록을 작성하고 빌드할 대상을 종속 대상으로 나열합니다. 그런 다음 이 설명 블록을 makefile에 먼저 배치하거나 NMAKE 명령줄에 의사 대상을 지정합니다.

이 예제에서 UPDATE는 의사 대상입니다.

```makefile
UPDATE : *.*
!COPY $** c:\product\release
```

UPDATE를 평가하면 NMAKE는 현재 디렉터리에 있는 모든 파일을 지정된 드라이브 및 디렉터리로 복사합니다.

다음 makefile에서 의사 `all` 대상은 명령줄에 `project1.exe` `project2.exe` 둘 `all` 다 또는 대상이 지정되지 않은 경우 빌드합니다. 의사 대상은 `setenv` 파일이 업데이트되기 전에 `.exe` LIB 환경 변수를 변경합니다.

```makefile
all : setenv project1.exe project2.exe

project1.exe : project1.obj
    LINK project1;

project2.exe : project2.obj
    LINK project2;

setenv :
    set LIB=\project\lib
```

## <a name="dependents"></a><a name="dependents"></a>부양 가족

종속성 줄에서 유효한 파일 이름 또는 [의사 대상을](pseudotargets.md)사용하여 콜론 ()`:`또는 이중 콜론 (double colon) 다음으로`::`0 개 이상의 종속 파일을 지정합니다. 하나 이상의 공백 이나 탭을 사용 하 여 여러 부양 가족을 분리 합니다. 부양 가족은 대/소문자를 구분하지 않습니다. 경로는 파일 이름으로 허용됩니다.

### <a name="inferred-dependents"></a><a name="inferred-dependents"></a>유추된 부양가족

종속성 줄에 명시적으로 나열하는 종속 부양가족과 함께 NMAKE는 *추론된 종속*을 가정할 수 있습니다. 추론된 종속성은 추론 규칙에서 파생되며 명시적 종속 종자 전에 평가됩니다. 추론된 종속성이 대상과 비교하여 오래된 경우 NMAKE는 종속성에 대한 명령 블록을 호출합니다. 추론된 종속 종속자가 존재하지 않거나 자체 종속 종과 비교하여 오래된 경우 NMAKE는 먼저 유추된 종속 을 업데이트합니다. 추론된 종속 가족에 대한 자세한 내용은 [추론 규칙을](inference-rules.md)참조하십시오.

### <a name="search-paths-for-dependents"></a><a name="search-paths-for-dependents"></a>부양 가족 검색 경로

각 종속 종속에 대한 선택적 검색 경로를 지정할 수 있습니다. 검색할 디렉터리 집합을 지정하는 구문은 다음과 같습니다.

> **{**_디렉토리;_\[**;** _디렉토리_...] **}**_종속_

중괄호 ()에`{ }`디렉터리 이름을 동봉합니다. 세미콜론()으로`;`여러 디렉터리분리 공백이나 탭은 허용되지 않습니다. NMAKE는 현재 디렉터리에서 먼저 종속 을 찾은 다음 지정된 순서대로 디렉터리 목록에서 찾습니다. 매크로를 사용하여 검색 경로의 일부 또는 전부를 지정할 수 있습니다. 지정된 종속 종자만 이 검색 경로를 사용합니다.

#### <a name="directory-search-path-example"></a>디렉터리 검색 경로 예제

이 종속성 줄은 검색에 대한 디렉터리 사양을 만드는 방법을 보여 주며 다음과 같은 방법을 보여 주며 있습니다.

```makefile
reverse.exe : {\src\omega;e:\repo\backwards}retro.obj
```

대상에는 `reverse.exe` 종속 대상이 `retro.obj`하나 있습니다. 중괄호로 둘러싸인 목록은 두 개의 디렉터리를 지정합니다. NMAKE는 먼저 `retro.obj` 현재 디렉토리에서 검색합니다. 거기에 없는 경우 NMAKE는 `\src\omega` 디렉토리, 다음 `e:\repo\backwards` 디렉토리를 검색합니다.

## <a name="see-also"></a>참고 항목

[NMAKE 참조](nmake-reference.md)
