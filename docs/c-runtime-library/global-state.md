---
title: CRT의 글로벌 상태
ms.date: 04/02/2020
helpviewer_keywords:
- CRT global state
ms.openlocfilehash: 1b32e8d4f23d2361a52a9b81150ef7c5c7422761
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745355"
---
# <a name="global-state-in-the-crt"></a>CRT의 글로벌 상태

UCRT(유니버설 C 런타임)의 일부 함수는 전역 상태를 사용합니다. 예를 들어 `setlocale()` 숫자 구분 기호, 텍스트 코드 페이지 등에게 영향을 미치는 전체 프로그램의 로캘을 설정합니다.

UCRT의 전역 상태는 응용 프로그램과 OS 간에 공유되지 않습니다. 예를 들어 응용 프로그램이 `setlocale()`호출하는 경우 C 런타임을 사용하는 OS 구성 요소에 대한 로캘에 영향을 주지 않거나 그 반대의 경우도 마찬가지입니다.

## <a name="os-specific-versions-of-crt-functions"></a>CRT 함수의 OS별 버전

UCRT에서 전역 상태와 상호 작용하는 함수에는 에 접두사된 `_o_`"트윈" 함수가 있습니다. 다음은 그 예입니다.

- `setlocale()`앱과 관련된 전역 상태에 영향을 줍니다.
- `_o_setlocale()`앱이 아닌 모든 OS 구성 요소가 공유하는 전역 상태에 영향을 줍니다.

이러한 "트윈" 함수간의 유일한 차이점은 전역 CRT 상태를 읽음/쓸 때 OS 관련 버전(즉, 시작하는 `_o_`버전)이 앱의 전역 상태 복사본 대신 전역 상태의 OS 복사본을 사용한다는 것입니다.

이러한 함수의 OS 별 버전은 에 `ucrt.osmode.lib`있습니다. 예를 들어, OS 별 `setlocale()` 버전은`_o_setlocale()`

구성 요소의 CRT 상태를 앱의 CRT 상태에서 격리하는 방법에는 두 가지가 있습니다.

- 컴파일러 옵션 /MT (릴리스) 또는 MTd (디버그)를 사용하여 구성 요소를 정적으로 연결합니다. 자세한 내용은 [/MD, /MT, /LD를](https://docs.microsoft.com/cpp/build/reference/md-mt-ld-use-run-time-library?view=vs-2019)참조하십시오. 정적 연결은 이진 크기를 크게 늘릴 수 있습니다.
- Windows 10 20H2부터는 CRT에 동적으로 연결하여 CRT 상태 격리를 얻을 수 있지만 OS 모드 _내보내기(o로_시작하는 함수)를 호출합니다. OS 모드 내보내기를 호출하려면 이전과 같이 정적 링크하지만 링커 옵션 `/NODEFAULTLIB:libucrt.lib` (릴리스) `/NODEFAULTLIB:libucrtd.lib` 또는 (디버그) 참조 [/NODEFAULTLIB (라이브러리 무시)를](https://docs.microsoft.com/cpp/build/reference/nodefaultlib-ignore-libraries?view=vs-2019) 사용하여 정적 UCRT를 무시하십시오. 그리고 `ucrt.osmode.lib` 링커 입력에 추가합니다.

> [!Note]
> 소스 코드에서는 `setlocale()`을 `_o_setlocale()`작성하지 않습니다. 에 대해 `ucrt.osmode.lib`링크하면 링커는 자동으로 OS 관련 버전의 함수를 대체합니다. 즉, `setlocale()` `_o_setlocale()`로 대체됩니다.

에 `ucrt.osmode.lib` 대해 연결하면 앱 모드에서만 사용할 수 있는 일부 UCRT 호출이 비활성화됩니다. 이 호출을 시도하면 링크 오류가 발생합니다.

## <a name="global-state-affected-by-appos-separation"></a>앱/OS 분리의 영향을 받는 전역 상태

앱 및 OS 상태의 분리에 의해 영향을 받는 전역 상태는 다음과 같습니다.

- [로캘 데이터](locale.md)
- [신호에](reference/signal.md) 의해 설정된 신호 처리기
- [종료에](reference/set-terminate-crt.md) 의해 설정된 종료 루틴
- [에르노와 _doserrno](errno-doserrno-sys-errlist-and-sys-nerr.md)
- [랜드와](reference/rand.md) [스랜드가](reference/srand.md) 사용하는 난수 생성 상태
- [스트톡, wcstok, _mbstok](reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) [Tmpnam, _wtmpnam](reference/tempnam-wtempnam-tmpnam-wtmpnam.md) [asctime, _wasctime](reference/asctime-wasctime.md) [gmtime, _gmtime32, _gmtime64](reference/gmtime-gmtime32-gmtime64.md) _fcvt [_ecvt](reference/fcvt.md) [strerror, _strerror, _wcserror, __wcserror](reference/strerror-strerror-wcserror-wcserror.md) [_ecvt](reference/ecvt.md)
- _putch 사용하는 [버퍼, _putwch](reference/putch-putwch.md)
- [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)
- [_set_new_handler](reference/set-new-handler.md) [및 _set_new_mode](reference/set-new-mode.md)
- [fmode] (text-and-binary-mode-file-i-o.md)
- [표준 시간대 정보](time-management.md)

## <a name="see-also"></a>참조

[C 런타임 라이브러리 참조](c-run-time-library-reference.md)
