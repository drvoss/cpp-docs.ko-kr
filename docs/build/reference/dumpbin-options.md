---
title: DUMPBIN 옵션
description: Microsoft DUMPBIN 유틸리티 명령줄 옵션에 대 한 참조 가이드입니다.
ms.date: 02/09/2020
helpviewer_keywords:
- DUMPBIN program, options
ms.assetid: 563b696e-7599-4480-94b9-014776289ec8
ms.openlocfilehash: 54f5a22808026f4442f85d5e53a0805702e05868
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440046"
---
# <a name="dumpbin-options"></a>DUMPBIN 옵션

옵션은 대시 (`-`) 또는 슬래시 (`/`), 옵션 이름을 차례로 나타내는 *옵션 지정자*로 구성 됩니다. 옵션 이름은 약식 일 수 없습니다. 일부 옵션은 콜론 (`:`) 뒤에 지정 되는 인수를 사용 합니다. 옵션 사양에는 공백이나 탭을 사용할 수 없습니다. 한 개 이상의 공백 또는 탭을 사용하여 명령줄에서 옵션 사양을 구분합니다. 옵션 이름과 해당 키워드 또는 파일 이름 인수는 대/소문자를 구분 하지 않습니다. 대부분의 옵션은 모든 이진 파일에 적용 되지만 몇 가지 옵션은 특정 파일 형식에만 적용 됩니다. 기본적으로 DUMPBIN은 표준 출력으로 정보를 보냅니다. [/Out](out-dumpbin.md) 옵션을 사용 하 여 출력을 파일로 보냅니다.

## <a name="options-list"></a>옵션 목록

DUMPBIN에는 다음과 같은 옵션이 있습니다.

- [/ALL](all.md)

- [/ARCHIVEMEMBERS](archivemembers.md)

- [/CLRHEADER](clrheader.md)

- [/DEPENDENTS](dependents.md)

- [/DIRECTIVES](directives.md)

- [/DISASM\[: {BYTES\|NOBYTES}\]](disasm.md)

- [/ERRORREPORT: {NONE | 프롬프트 | 큐 | SEND}](errorreport-dumpbin-exe.md) (사용 되지 않음)

- [/EXPORTS](dash-exports.md)

- [/FPO](fpo.md)

- [/HEADERS](headers.md)

- [/IMPORTS\[: 파일 이름\]](imports-dumpbin.md)

- [/LINENUMBERS](linenumbers.md)

- [/LINKERMEMBER\[: {1 | 2}\]](linkermember.md)

- [/LOADCONFIG](loadconfig.md)

- [/NOPDB](nopdb.md)

- [/OUT: filename](out-dumpbin.md)

- [/PDATA](pdata.md)

- [/PDBPATH\[: VERBOSE\]](pdbpath.md)

- [/RANGEE: vaMin\[, Vamin\]](range.md)

- [/RAWDATA\[: {NONE\|1\|2\|4\|8}\[, #\]\]](rawdata.md)

- [/RELOCATIONS](relocations.md)

- [/SECTION: 이름](section-dumpbin.md)

- [/SUMMARY](summary.md)

- [/SYMBOLS](symbols.md)

- [/TLS](tls.md)

명령줄에서 DUMPBIN에서 지 원하는 옵션을 나열 하려면 **/?** 를 사용 합니다. 이동합니다.

## <a name="see-also"></a>참고 항목

[추가 MSVC 빌드 도구](c-cpp-build-tools.md)\
[DUMPBIN 명령줄](dumpbin-command-line.md)\
[DUMPBIN 참조](dumpbin-reference.md)
