---
title: 유니코드 지원
ms.date: 01/09/2018
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
ms.openlocfilehash: 0b61407920a0ce35a1c6a8466458736e983e271e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168566"
---
# <a name="support-for-unicode"></a>유니코드 지원

유니코드는 단일 바이트로 표현할 수 없는 문자 집합을 포함 하 여 모든 문자 집합을 지 원하는 사양입니다.  국제 시장을 대상으로 프로그래밍 하는 경우 유니코드 또는 MBCS ( [멀티 바이트 문자 집합](../text/support-for-multibyte-character-sets-mbcss.md) )를 사용 하는 것이 좋습니다. 또는 스위치를 변경 하 여 프로그램을 빌드할 수 있도록 프로그램을 코딩 합니다.

와이드 문자는 2바이트 다국어 문자 코드입니다. 기술 기호 및 특별한 게시 문자를 포함하여 전 세계의 현대적인 컴퓨팅 환경에서 사용되는 거의 모든 문자열을 구성하는 수만 개의 문자는 UTF-16을 사용하여 인코딩된 하나의 와이드 문자로 유니코드 사양에 따라 표현될 수 있습니다. 하나의 와이드 문자로 표현할 수 없는 문자는 유니코드 서로게이트 쌍(Unicode surrogate pair)을 이용하여 하나의 유니코드 쌍으로 표현할 수 있습니다. 일반적으로 사용 되는 거의 모든 문자는 단일 16 비트 와이드 문자에서 u t f-16으로 표시 되므로 와이드 문자를 사용 하면 국제 문자 집합을 사용한 프로그래밍이 단순해 집니다. 리틀엔디안(Little endian)용인 UTF-16LE를 사용하여 인코딩된 와이드 문자는 Windows용 기본 문자 형식입니다.

와이드 문자열은 `wchar_t[]` 배열로 표현되며 `wchar_t*` 포인터가 가리킵니다. 모든 ASCII 문자는 문자 앞에 접두사로 문자 L을 붙여 와이드 문자로 표현할 수 있습니다. 예를 들어 L'\0'은 종료 와이드(16비트) NULL 문자입니다. 마찬가지로, ASCII 문자열 리터럴은 ASCII 리터럴에 접두사로 문자 L을 붙여(예: L"Hello") 와이드 문자열 리터럴로 표현할 수 있습니다.

일반적으로 와이드 문자는 멀티바이트 문자보다 더 많은 메모리 공간을 차지하지만 프로세스 속도는 더 빠릅니다. 뿐만 아니라, 멀티바이트 인코딩에서는 한 번에 하나의 로캘만 표현할 수 있는 반면, 유니코드는 세계의 모든 문자 집합을 동시에 표현할 수 있습니다.

MFC 프레임워크 전체에서는 유니코드를 사용할 수 있으며 MFC에서는 다음 테이블에 표시된 것처럼 이식 가능한 매크로를 사용하여 유니코드를 사용할 수 있습니다.

## <a name="portable-data-types-in-mfc"></a>MFC의 이식 가능한 데이터 형식

|이식 불가능한 데이터 형식|다음 매크로로 바뀜|
|-----------------------------|----------------------------|
|`char`, `wchar_t`|`_TCHAR`|
|`char*`, `LPSTR` (Win32 데이터 형식), `LPWSTR`|`LPTSTR`|
|`const char*`, `LPCSTR` (Win32 데이터 형식), `LPCWSTR`|`LPCTSTR`|

클래스 `CString`는 `_TCHAR`를 기반으로 사용 하며 쉽게 변환할 수 있도록 생성자와 연산자를 제공 합니다. 유니코드에 대한 대부분의 문자열 작업은 Windows ANSI 문자 집합을 처리하는 데 사용되는 것과 동일한 논리를 사용하여 작성할 수 있습니다. 이러한 논리는 작업의 기본 단위가 8비트 바이트 대신 16비트 문자라는 점이 다릅니다. 멀티바이트 문자 집합을 사용하는 것과 달리 유니코드 문자를 별도의 2바이트인 것처럼 처리할 필요가 없습니다. 와이드 문자의 서로게이트 쌍으로 단일 문자처럼 사용할 때는 고려해야 할 수도 있습니다. 일반적으로, 좁은 문자나 와이드 문자로 이루어진 문자열의 길이가 문자의 갯수와 같다고 가정하는 코드 작성은 바람직하지 않습니다.

## <a name="what-do-you-want-to-do"></a>수행 작업

- [MFC 유니코드 및 MBCS (멀티 바이트 문자 집합) 지원 사용](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)

- [내 프로그램에서 유니코드 사용](../text/international-enabling.md)

- [프로그램에서 유니코드 및 MBCS 모두 사용](../text/internationalization-strategies.md)

- [유니코드를 사용 하 여 국제화 된 프로그램 만들기](../text/unicode-programming-summary.md)

- [유니코드의 이점 알아보기](../text/benefits-of-character-set-portability.md)

- [프로그램에 와이드 문자 인수를 전달할 수 있도록 wmain 사용](../text/support-for-using-wmain.md)

- [유니코드 프로그래밍 요약 보기](../text/unicode-programming-summary.md)

- [바이트 너비 이식성에 대 한 일반 텍스트 매핑에 대해 알아보기](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>참고 항목

[텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)<br/>
[wmain 사용 지원](../text/support-for-using-wmain.md)
