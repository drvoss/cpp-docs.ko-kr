---
title: C 런타임 오류 R6035
ms.date: 11/04/2016
f1_keywords:
- R6035
helpviewer_keywords:
- R6035
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
ms.openlocfilehash: 7c497347689bcfc5528280bd22aa5183d5fafd61
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197006"
---
# <a name="c-runtime-error-r6035"></a>C 런타임 오류 R6035

Microsoft Visual C++ Runtime Library, Error R6035-이 응용 프로그램의 모듈은 해당 보안 쿠키를 신뢰 하는 함수가 활성화 되어 있는 동안 모듈의 전역 보안 쿠키를 초기화 합니다.  이전에 __security_init_cookie를 호출 합니다.

[__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md) 는 전역 보안 쿠키를 처음 사용 하기 전에 호출 해야 합니다.

전역 보안 쿠키는 [/gs (버퍼 보안 검사)](../../build/reference/gs-buffer-security-check.md) 를 사용 하 여 컴파일된 코드에서 구조적 예외 처리를 사용 하는 코드에서 버퍼 오버런 보호에 사용 됩니다. 기본적으로, 오버런이 보호 된 함수에 대 한 항목에서 쿠키가 스택에 배치 되며 종료 시 스택의 값을 전역 쿠키와 비교 합니다. 이러한 차이점은 버퍼 오버런이 발생 하 여 프로그램을 즉시 종료 함을 나타냅니다.

오류 R6035는 보호 된 함수를 입력 한 후 `__security_init_cookie`를 호출 했음을 나타냅니다. 실행이 계속 되 면 스택의 쿠키가 전역 쿠키와 더 이상 일치 하지 않기 때문에 의사 버퍼 오버런이 검색 됩니다.

다음 DLL 예제를 참조 하십시오. DLL 진입점은 링커 [/entry (진입점 기호)](../../build/reference/entry-entry-point-symbol.md) 옵션을 통해 즉 dllentrypoint로 설정 됩니다. 이렇게 하면 일반적으로 전역 보안 쿠키를 초기화 하는 CRT의 초기화가 무시 되므로 DLL 자체가 `__security_init_cookie`를 호출 해야 합니다.

```
// Wrong way to call __security_init_cookie
DllEntryPoint(...) {
   DllInitialize();
   ...
   __try {
      ...
   } __except()... {
      ...
   }
}

void DllInitialize() {
   __security_init_cookie();
}
```

이 예제에서는 즉 dllentrypoint에서 구조적 예외 처리를 사용 하므로 보안 쿠키를 사용 하 여 버퍼 오버런을 검색 하기 때문에 오류 R6035 생성 됩니다. DllInitialize가 호출 되 면 전역 보안 쿠키는 이미 스택에 배치 된 것입니다.

이 예제에서는 올바른 방법을 보여 줍니다.

```
// Correct way to call __security_init_cookie
DllEntryPoint(...) {
   __security_init_cookie();
   DllEntryHelper();
}

void DllEntryHelper() {
   ...
   __try {
      ...
   } __except()... {
      ...
   }
}
```

이 경우 즉 dllentrypoint는 버퍼 오버런 으로부터 보호 되지 않습니다 (로컬 문자열 버퍼가 없고 구조적 예외 처리를 사용 하지 않음). 따라서 `__security_init_cookie`를 안전 하 게 호출할 수 있습니다. 그런 다음 보호 되는 도우미 함수를 호출 합니다.

> [!NOTE]
>  오류 메시지 R6035는 x86 디버그 CRT 에서만 생성 되며 구조적 예외 처리의 경우에만 발생 하지만 모든 플랫폼에서 발생 하는 오류 및 EH와 C++ 같은 모든 형태의 예외 처리에 대 한 조건입니다.

## <a name="see-also"></a>참고 항목

[MSVC의 보안 기능](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)
