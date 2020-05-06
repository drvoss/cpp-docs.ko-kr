---
title: C 명령줄 처리 사용자 지정
ms.date: 11/04/2016
helpviewer_keywords:
- _spawn functions
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _exec function
ms.assetid: c20fa11d-b35b-4f3e-93b6-2cd5a1c3c993
ms.openlocfilehash: 1abdb0c104755efc86543ac4773359078e855999
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62290692"
---
# <a name="customizing-c-command-line-processing"></a>C 명령줄 처리 사용자 지정

프로그램에서 명령줄 인수를 사용하지 않는 경우 명령줄 처리를 수행하는 라이브러리 루틴의 사용을 억제하여 약간의 공간을 절약할 수 있습니다. 이 루틴을 **_setargv**(또는 와이드 문자 환경에서는 **_wsetargv**)라고 합니다([와일드카드 인수 확장명](../c-language/expanding-wildcard-arguments.md) 참조). 이 루틴의 사용을 억제하려면 **main** 함수를 포함하는 파일에서 아무 작업도 수행하지 않는 루틴을 정의하고 **_setargv**(또는 와이드 문자 환경에서는 **_wsetargv**)라는 이름을 지정합니다. **_setargv** 또는 **_wsetargv**를 호출하면 정의한 **_setargv** 또는 **_wsetargv**가 실행되며 라이브러리 버전이 로드되지 않습니다.

마찬가지로 `envp` 인수를 통해 환경 테이블에 액세스하지 않을 경우 환경 처리 루틴인 **_setenvp**(또는 **_wsetenvp**) 대신 사용할 사용자 고유의 빈 루틴을 제공할 수 있습니다.

프로그램에서 C 런타임 라이브러리의 **_spawn** 또는 **_exec** 계열 루틴을 호출하는 경우 생성하는 프로세스에서 새 프로세스로 환경을 전달하는 데 환경 처리 루틴이 사용되므로 환경 처리 루틴을 억제하면 안 됩니다.

## <a name="see-also"></a>참조

[main 함수 및 프로그램 실행](../c-language/main-function-and-program-execution.md)
