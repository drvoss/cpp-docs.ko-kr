---
title: 시스템 함수
ms.date: 11/04/2016
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
ms.openlocfilehash: e37de4e084de6727cf2858117945fd162f6b0d63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345125"
---
# <a name="system-function"></a>시스템 함수

**ANSI 4.10.4.5** **시스템** 함수에 의한 문자열의 실행 모드 및 내용

**시스템** 함수는 명령줄이 아닌 C 프로그램 내에서 내부 운영 체제 명령 또는 .EXE, .COM(Windows NT에서는 .CMD) 또는 .BAT 파일을 실행합니다.

시스템 함수는 명령 해석기를 찾습니다. 일반적으로 명령 해석기는 Windows NT 운영 체제에서 CMD.EXE, Windows에서는 COMMAND.COM을 찾습니다.  그런 다음 시스템 함수는 인수 문자열을 명령 해석기에 전달합니다.

자세한 내용은 [system, _wsystem](../c-runtime-library/reference/system-wsystem.md)을 참조하세요.

## <a name="see-also"></a>참조

[라이브러리 함수](../c-language/library-functions.md)
