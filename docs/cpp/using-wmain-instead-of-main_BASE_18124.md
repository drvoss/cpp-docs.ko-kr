---
title: main 대신 wmain 사용
ms.date: 11/04/2016
f1_keywords:
- wmain
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
ms.openlocfilehash: f47d7219a54b197ec59f109cf08879774b48e6f7
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857218"
---
# <a name="using-wmain-instead-of-main"></a>main 대신 wmain 사용

**Microsoft 전용**

유니코드 프로그래밍 모델에서 와이드 문자 버전의 `main` 함수를 정의할 수 있습니다. 유니코드 사양을 준수하는 이식성 있는 코드를 작성하려면 `main` 대신 **wmain**을 사용하세요.

`main`과 비슷한 형태로 형식 매개변수를 **wmain**으로 선언합니다. 와이드 문자 인수 또는 와이드 문자 환경 포인터를 프로그램에 전달할 수 있습니다. **wmain**에 대한 *argv*와 *envp* 매개 변수는 `wchar_t*` 형식입니다.

프로그램이 `main` 함수를 사용하는 경우 프로그램 시작 시 운영체제에 의해 멀티 바이트 문자 환경이 만들어집니다. 와이드 문자 사본 환경은 필요한 경우에만 만들어집니다(예 : [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)나 [_wputenv](../c-runtime-library/reference/putenv-wputenv.md) 함수 호출 시). `_wputenv` 또는 `_wgetenv`의 첫 번째 호출에서 MBCS 환경이 이미 있는 경우 해당 와이드 문자 문자열 환경이 만들어지고 `_wenviron` 전역 변수의 와이드 문자 버전인 `_environ` 전역 변수에 의해 가리킵니다. 이 시점에서 환경 복사본 두 개(MBCS와 유니코드)가 동시에 존재하며 프로그램의 수명 내내 운영 체제에 의해 유지 관리됩니다.

마찬가지로 프로그램이 **wmain** 함수를 사용하는 경우 `_putenv`나 `getenv`의 첫 번째 호출에서 MBCS(ASCII) 환경이 생성되고 `_environ` 전역 변수가 가리킵니다.

MBCS 환경에 대한 자세한 내용은 *런타임 라이브러리 참조*에서 [싱글바이트 및 멀티바이트 문자 집합](../c-runtime-library/single-byte-and-multibyte-character-sets.md)을 참조합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[main: 프로그램 시작](../cpp/main-program-startup.md)