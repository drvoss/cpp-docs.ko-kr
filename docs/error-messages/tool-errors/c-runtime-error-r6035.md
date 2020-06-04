---
title: C 런타임 오류 R6035
ms.date: 11/04/2016
f1_keywords:
- R6035
helpviewer_keywords:
- R6035
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
ms.openlocfilehash: ff3cd0259df92aa5cdade3f78a240e69f8f6f7de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377474"
---
# <a name="c-runtime-error-r6035"></a>C 런타임 오류 R6035

Microsoft Visual C++ 런타임 라이브러리, 오류 R6035 - 이 응용 프로그램의 모듈은 해당 보안 쿠키에 의존하는 기능이 활성화되어 있는 동안 모듈의 전역 보안 쿠키를 초기화합니다.  __security_init_cookie 일찍 전화하십시오.

[__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md) 글로벌 보안 쿠키를 처음 사용하기 전에 호출해야 합니다.

전역 보안 쿠키는 [/GS(버퍼 보안 검사)로](../../build/reference/gs-buffer-security-check.md) 컴파일된 코드및 구조화된 예외 처리를 사용하는 코드에서 버퍼 오버런 보호에 사용됩니다. 기본적으로 오버런 보호 함수에 입력하면 쿠키가 스택에 배치되고 종료시 스택의 값은 전역 쿠키와 비교됩니다. 버퍼 오버런이 발생하여 프로그램이 즉시 종료되었음을 나타냅니다.

오류 R6035는 보호된 `__security_init_cookie` 함수를 입력한 후 호출이 이루어졌음을 나타냅니다. 실행을 계속하는 경우 스택의 쿠키가 더 이상 전역 쿠키와 일치하지 않으므로 스퓨리어스 버퍼 오버런이 검색됩니다.

다음 DLL 예제를 고려하십시오. DLL 진입점은 [링커/ENTRY(진입점 기호)](../../build/reference/entry-entry-point-symbol.md) 옵션을 통해 DllEntryPoint로 설정됩니다. 이렇게 하면 일반적으로 전역 보안 쿠키를 초기화하는 CRT의 초기화를 무시하므로 DLL `__security_init_cookie`자체는 을 호출해야 합니다.

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

이 예제에서는 DllEntryPoint가 구조화된 예외 처리를 사용하므로 보안 쿠키를 사용하여 버퍼 오버런을 검색하기 때문에 R6035 오류가 생성됩니다. DllInitialize가 호출될 때까지 전역 보안 쿠키가 이미 스택에 배치되었습니다.

올바른 방법은 이 예제에서 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을

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

이 경우 DllEntryPoint는 버퍼 오버런으로부터 보호되지 않습니다(로컬 문자열 버퍼가 없고 구조화된 예외 처리를 사용하지 않음). 따라서 안전하게 호출 `__security_init_cookie`할 수 있습니다. 그런 다음 보호되는 도우미 함수를 호출합니다.

> [!NOTE]
> 오류 메시지 R6035는 x86 디버그 CRT에 의해서만 생성되며 구조화된 예외 처리에 대해서만 생성되지만 조건은 모든 플랫폼및 C++ EH와 같은 모든 형태의 예외 처리에 대한 오류입니다.

## <a name="see-also"></a>참고 항목

[MSVC의 보안 기능](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)
