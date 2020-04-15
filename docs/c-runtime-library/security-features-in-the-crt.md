---
title: CRT의 보안 기능
ms.date: 11/04/2016
f1_keywords:
- _CRT_SECURE_NO_DEPRECATE
- _CRT_NONSTDC_NO_WARNINGS
- _CRT_SECURE_NO_WARNINGS
helpviewer_keywords:
- security deprecation warnings [C++]
- CRT_NONSTDC_NO_DEPRECATE
- buffers [C++], buffer overruns
- deprecation warnings (security-related), disabling
- _CRT_NONSTDC_NO_WARNINGS
- security [CRT]
- _CRT_SECURE_NO_WARNINGS
- _CRT_NONSTDC_NO_DEPRECATE
- _CRT_SECURE_NO_DEPRECATE
- security-enhanced CRT
- CRT_SECURE_NO_WARNINGS
- CRT_SECURE_NO_DEPRECATE
- deprecation warnings (security-related)
- buffer overruns
- CRT_NONSTDC_NO_WARNINGS
- CRT, security enhancements
- parameters [C++], validation
ms.assetid: d9568b08-9514-49cd-b3dc-2454ded195a3
ms.openlocfilehash: 1b42c766a7b75cb3f4d5c20d715968905d529d04
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361003"
---
# <a name="security-features-in-the-crt"></a>CRT의 보안 기능

이전 CRT 함수 중 상당수에 더 안전한 최신 버전이 있습니다. 안전한 함수가 있을 경우 보안 수준이 떨어지는 이전 버전이 사용되지 않는 것으로 표시되고 새 버전에 `_s`("안전함") 접미사가 붙습니다.

이 컨텍스트에서 "사용되지 않는다"는 것은 해당 함수를 사용하는 것이 권장되지 않는다는 의미이지 해당 함수가 CRT에서 제거될 예정이라는 의미가 아닙니다.

안전한 함수를 사용하면 보안 오류가 방지되거나 해결되는 것이 아니라 오류 발생 시 이를 포착할 수 있게 됩니다. 이러한 함수는 오류 조건이 있는지 확인하기 위해 추가적인 검사를 수행하며, 오류 발생 시 오류 처리기를 호출합니다([매개 변수 유효성 검사](../c-runtime-library/parameter-validation.md) 참조).

예를 들어 `strcpy` 함수는 복사하는 문자열이 대상 버퍼에 비해 너무 큰지 확인할 수 없습니다. 그러나 이 함수의 안전한 버전인 `strcpy_s`는 버퍼 오버런이 발생할 것인지 확인하기 위해 버퍼의 크기를 매개 변수로 사용합니다. `strcpy_s`를 사용하여 11자를 10자 버퍼로 복사할 경우 이는 사용자의 잘못입니다. `strcpy_s`는 사용자의 실수를 바로잡을 수 없지만 잘못된 매개 변수 처리기를 호출하여 오류를 발견하고 사용자에게 이 사실을 알려 줄 수 있습니다.

## <a name="eliminating-deprecation-warnings"></a>사용되지 않음 경고 제거

보안 수준이 떨어지는 이전 함수에 대한 사용되지 않음 경고는 여러 가지 방법으로 제거할 수 있습니다. 가장 간단한 방법은 단순히 `_CRT_SECURE_NO_WARNINGS`를 정의하거나 [warning](../preprocessor/warning.md) pragma를 사용하는 것입니다. 두 방법 모두 사용되지 않음 경고가 표시되지 않게 만들지만 해당 경고를 발생시킨 보안 문제는 물론 여전히 존재합니다. 따라서 사용되지 않음 경고가 계속 표시되게 두고 새로운 CRT 보안 기능을 활용하는 것이 훨씬 더 낫습니다.

C++에서 이렇게 하는 가장 쉬운 방법은 [안전한 템플릿 오버로드](../c-runtime-library/secure-template-overloads.md)를 사용하는 것입니다. 많은 경우 이렇게 하면 사용되지 않는 함수에 대한 호출이 해당 함수의 안전한 새 버전에 대한 호출로 대체되어 사용되지 않음 경고가 제거됩니다. 예를 들어 `strcpy`에 대한 사용되지 않는 다음 호출을 살펴보십시오.

```
char szBuf[10];
strcpy(szBuf, "test"); // warning: deprecated
```

`_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES`를 1로 정의하면 `strcpy` 호출이 버퍼 오버런을 방지하는 `strcpy_s`로 변경되어 경고가 제거됩니다. 자세한 내용은 [안전한 템플릿 오버로드](../c-runtime-library/secure-template-overloads.md)를 참조하세요.

사용되지 않는 함수 중 안전한 템플릿 오버로드가 없는 함수의 경우 안전한 버전을 사용하도록 수동으로 코드를 업데이트해야 합니다.

보안과 관련되지는 않았지만 사용되지 않음 경고의 원인이 되는 또 다른 항목은 POSIX 함수입니다. POSIX 함수 이름을 표준 상응 항목으로 대체하거나(예: [access](../c-runtime-library/reference/access-crt.md)를 [_access](../c-runtime-library/reference/access-waccess.md)로 변경) `_CRT_NONSTDC_NO_WARNINGS`를 정의하여 POSIX 관련 사용되지 않음 경고가 표시되지 않게 만듭니다. 자세한 내용은 [호환성](compatibility.md)을 참조하세요.

## <a name="additional-security-features"></a>추가 보안 기능

다음은 보안 기능 중 일부입니다.

- `Parameter Validation`. 안전한 함수와 많은 기존 버전의 함수에서 모두 CRT 함수에 전달되는 매개 변수의 유효성이 검사됩니다. 이러한 유효성 검사는 다음과 같습니다.

  - 함수에 전달된 **NULL** 값

  - 열거형 값의 유효성

  - 정수 계열 값이 유효 범위 내에 있는지 여부

- 자세한 내용은 [매개 변수 유효성 검사](../c-runtime-library/parameter-validation.md)를 참조하세요.

- 개발자가 잘못된 매개 변수에 대한 처리기에도 액세스할 수 있습니다. 잘못된 매개 변수가 발견되면 CRT는 애플리케이션을 어설션 및 종료하는 대신 [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) 함수를 사용하여 이러한 문제를 확인하는 방법을 제공합니다.

- `Sized Buffers`. 안전한 함수를 사용하려면 버퍼에 쓰는 모든 함수에 버퍼 크기를 전달해야 합니다. 안전한 버전은 버퍼에 쓰기 전에 버퍼가 충분히 큰지 검증하여 악의적인 코드가 실행되게 만들 수 있는 위험한 버퍼 오버런 오류를 방지하는 데 도움을 줍니다. 이러한 함수는 일반적으로 `errno` 형식의 오류 코드를 반환하고 버퍼 크기가 너무 작을 경우 잘못된 매개 변수 처리기를 호출합니다. `gets`와 같이 입력 버퍼에서 읽는 함수에는 최대 크기를 지정해야 하는 안전한 버전이 있습니다.

- `Null termination`. 종료되지 않았을 수 있는 문자열을 남긴 일부 함수에는 문자열이 적절하게 null로 종료되게 만드는 안전한 버전이 있습니다.

- `Enhanced error reporting`. 안전한 함수는 기존 함수에서 사용할 수 있었던 것보다 더 많은 오류 정보와 함께 오류 코드를 반환합니다. 안전한 함수 및 기존 함수 중 상당수가 이제 `errno`를 설정하며, 더 나은 오류 보고를 제공하기 위해 `errno` 코드 형식도 반환하는 경우가 많습니다.

- `Filesystem security`. 안전한 파일 I/O API는 default case에서 안전한 파일 액세스를 지원합니다.

- `Windows security`. 안전한 프로세스 API는 보안 정책을 적용하고 ACL을 지정할 수 있게 허용합니다.

- `Format string syntax checking`. 잘못된 문자열이 검색됩니다(예:`printf` 형식 문자열에 잘못된 형식 필드 문자 사용).

## <a name="see-also"></a>참고 항목

[매개 변수 유효성 검사](../c-runtime-library/parameter-validation.md)<br/>
[안전한 템플릿 오버로드](../c-runtime-library/secure-template-overloads.md)<br/>
[CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)
