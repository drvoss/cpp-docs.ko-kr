---
title: 국가별 사용
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
ms.openlocfilehash: b6c645bafef87ed0b2d43903f4752ef659d79f89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375798"
---
# <a name="international-enabling"></a>국가별 사용

대부분의 기존 C 및 C++ 코드는 국제 응용 프로그램에서는 잘 작동하지 않는 문자 및 문자열 조작에 대해 가정합니다. MFC와 런타임 라이브러리모두 유니코드 또는 MBCS를 지원하지만 여전히 수행할 작업이 있습니다. 안내하기 위해 이 섹션에서는 Visual C++에서 "국제 사용"의 의미를 설명합니다.

- 유니코드와 MBCS는 MFC 함수 매개 변수 목록 및 반환 형식의 휴대용 데이터 형식을 통해 활성화됩니다. 이러한 형식은 빌드에서 기호 `_UNICODE` 또는 기호를 `_MBCS` 정의하는지(DBCS를 의미)에 따라 적절한 방식으로 조건부로 정의됩니다. MFC 라이브러리의 다른 변형은 빌드가 정의하는 두 기호 중 어느 기호에 따라 응용 프로그램과 자동으로 연결됩니다.

- 클래스 라이브러리 코드는 올바른 유니코드 또는 MBCS 동작을 보장하기 위해 이식 가능한 런타임 함수 및 기타 방법을 사용합니다.

- 코드에서 특정 종류의 국제화 작업을 처리해야 합니다.

  - 두 환경에서 MFC를 이식할 수 있도록 하는 동일한 휴대용 런타임 함수를 사용합니다.

  - 매크로를 사용하여 두 환경 중 하나에서 리터럴 문자열과 문자를 이식할 수 있도록 합니다. `_T` 자세한 내용은 [tchar.h의 일반 텍스트 매핑을](../text/generic-text-mappings-in-tchar-h.md)참조하십시오.

  - MBCS에서 문자열을 구문 분석할 때는 주의해야 합니다. 이러한 예방 조치는 유니코드에서 필요하지 않습니다. 자세한 내용은 [MBCS 프로그래밍 팁을](../text/mbcs-programming-tips.md)참조하십시오.

  - 응용 프로그램에서 ANSI(8비트) 및 유니코드(16비트) 문자를 혼합하는 경우 주의해야 합니다. 프로그램의 일부 부분에서 ANSI 문자를 사용할 수 있고 다른 부분에서는 유니코드 문자를 사용할 수 있지만 동일한 문자열로 혼합할 수는 없습니다.

  - 응용 프로그램에서 문자열을 하드 코딩하지 마십시오. 대신 응용 프로그램의 .rc 파일에 추가하여 STRINGTABLE 리소스를 만듭니다. 그런 다음 소스 코드를 변경하거나 다시 컴파일할 필요 없이 응용 프로그램을 지역화할 수 있습니다. STRINGTABLE 리소스에 대한 자세한 내용은 [문자열 편집기](../windows/string-editor.md)를 참조하십시오.

> [!NOTE]
> 유럽 및 MBCS 문자 세트에는 악센트 문자와 같은 문자가 있으며 문자 코드가 0x80보다 큽니다. 대부분의 코드는 서명된 문자를 사용하기 때문에 0x80보다 큰 이러한 문자는 **int로**변환할 때 부호 확장됩니다. 이는 부호 확장 문자가 음수인 배열 외부의 인덱스이기 때문에 배열 인덱싱에 문제가 됩니다. 일본어와 같이 MBCS를 사용하는 언어도 독특합니다. 문자는 1바이트 또는 2바이트로 구성될 수 있으므로 항상 두 바이트를 동시에 조작해야 합니다.

## <a name="see-also"></a>참고 항목

[유니코드 및 멀티바이트 문자 집합(MBCS)](../text/unicode-and-mbcs.md)<br/>
[국제화 전략](../text/internationalization-strategies.md)
