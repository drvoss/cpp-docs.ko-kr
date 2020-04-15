---
title: 유니코드 및 멀티바이트 문자 집합(MBCS) 지원
ms.date: 01/09/2017
helpviewer_keywords:
- MFC [C++], character set support
- MBCS [C++], strings and MFC support
- strings [C++], MBCS support in MFC
- character sets [C++], multibyte
- Unicode [C++], MFC strings
- Unicode [C++], string objects
- strings [C++], Unicode
- strings [C++], character set support
ms.openlocfilehash: e1b93a3540cba553afd8f133c18496bddbd561b8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317433"
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>유니코드 및 멀티바이트 문자 집합(MBCS) 지원

예를 들어 일본어와 중국어와 같은 일부 언어에는 큰 문자 집합이 있습니다. 이러한 시장에 대한 프로그래밍을 지원하기 위해 Microsoft 재단 클래스 라이브러리(MFC)를 사용하면 큰 문자 집합을 처리하는 두 가지 방법을 사용할 수 있습니다.

- [유니코드](#mfc-support-for-unicode-strings) `wchar_t` , UTF-16으로 인코딩 된 와이드 문자 및 문자열을 기반으로합니다.

- [멀티바이트 문자 집합(MBCS)](#mfc-support-for-mbcs-strings)- **로캘별** 문자 집합에 인코딩된 char 기반 단일 또는 이중 바이트 문자 및 문자열입니다.

Microsoft는 모든 새로운 개발을 위해 MFC 유니코드 라이브러리를 권장했으며, MBCS 라이브러리는 Visual Studio 2013 및 Visual Studio 2015에서 더 이상 사용되지 않았습니다. 더 이상 그렇지 않습니다. MBCS 사용 중단 경고는 Visual Studio 2017에서 제거되었습니다.

## <a name="mfc-support-for-unicode-strings"></a>유니코드 문자열에 대한 MFC 지원

전체 MFC 클래스 라이브러리는 유니코드 문자및 UTF-16으로 넓은 문자로 저장된 문자열에 대해 조건부로 활성화됩니다. 특히 클래스 [CString은](../atl-mfc-shared/reference/cstringt-class.md) 유니코드 가 사용됩니다.

이러한 라이브러리, 디버거 및 DLL 파일은 MFC에서 유니코드를 지원하는 데 사용됩니다.

|||||
|-|-|-|-|
|UAFXCW. Lib|UAFXCW. Pdb|UAFXCWD. Lib|UAFXCWD. Pdb|
|MFC*버전*U.LIB|MFC*버전*U.PDB|MFC*버전*U.DLL|MFC*버전*UD. Lib|
|MFC*버전*UD. Pdb|MFC*버전*UD. Dll|MFCS*버전*U.LIB|MFCS*버전*U.PDB|
|MFCS*버전*UD. Lib|MFCS*버전*UD. Pdb|MFCM*버전*U.LIB|MFCM*버전*U.PDB|
|MFCM*버전*U.DLL|MFCM*버전*UD. Lib|MFCM*버전*UD. Pdb|MFCM*버전*UD. Dll|

*(버전은* 파일의 버전 번호를 나타내며, 예를 들어 '140'은 버전 14.0을 의미합니다.)

`CString`은 TCHAR 데이터 형식을 기반으로 합니다. 프로그램의 빌드에 대해 _UNICODE 기호가 정의된 경우 TCHAR는 `wchar_t`16비트 문자 인코딩 유형인 type으로 정의됩니다. 그렇지 않으면 TCHAR는 **char,** 일반 8비트 문자 인코딩으로 정의됩니다. 따라서 유니코드 에서 `CString` a는 16비트 문자로 구성됩니다. 유니코드가 없으면 **문자**문자로 구성됩니다.

응용 프로그램의 유니코드 프로그래밍을 완료하려면 다음을 수행해야 합니다.

- _T 매크로를 사용하여 유니코드로 이식할 수 있도록 리터럴 문자열을 조건부로 코딩합니다.

- 문자열을 전달할 때 함수 인수에 문자 길이또는 바이트 길이가 필요한지 여부에 주의하십시오. 유니코드 문자열을 사용하는 경우 차이점이 중요합니다.

- C 런타임 문자열 처리 함수의 이식 가능한 버전을 사용합니다.

- 문자 및 문자 포인터에 다음 데이터 형식을 사용합니다.

  - **char를**사용할 TCHAR를 사용합니다.

  - **char를**<strong>\*</strong>사용할 LPTSTR을 사용합니다.

  - **Const char를**<strong>\*</strong>사용하는 LPCTSTR을 사용합니다. `CString`LPCTSTR `CString` 사이를 변환하는 운영자 LPCTSTR을 제공합니다.

`CString`또한 유니코드 인식 생성자, 할당 연산자 및 비교 연산자를 제공합니다.

[런타임 라이브러리 참조는](../c-runtime-library/c-run-time-library-reference.md) 모든 문자열 처리 함수의 이식 가능한 버전을 정의합니다. 자세한 내용은 [국제화](../c-runtime-library/internationalization.md)범주를 참조하십시오.

## <a name="mfc-support-for-mbcs-strings"></a>MBCS 문자열에 대한 MFC 지원

클래스 라이브러리는 다중 바이트 문자 집합에 대해서도 사용할 수 있지만 DBCS(이중 바이트 문자 집합)에만 사용할 수 있습니다.

멀티바이트 문자 집합에서 문자는 1바이트 또는 2바이트 너비일 수 있습니다. 너비가 2바이트인 경우 첫 번째 바이트는 사용 중인 코드 페이지에 따라 특정 범위에서 선택되는 특수 "리드 바이트"입니다. 함께 가져온 경우 잠재 고객 및 "추적 바이트"는 고유한 문자 인코딩을 지정합니다.

기호 _MBCS 프로그램의 빌드에 대해 정의된 경우 기반이 되는 `CString` TCHAR를 입력하여 **char에**매핑합니다. 리드 바이트의 `CString` 바이트와 트레일 바이트를 결정하는 것은 사용자에 달려 있습니다. C 런타임 라이브러리는 이를 확인하는 데 도움이 되는 기능을 제공합니다.

DBCS에서 지정된 문자열에는 모든 단일 바이트 ANSI 문자, 모든 이중 바이트 문자 또는 이 둘의 조합이 포함될 수 있습니다. 이러한 가능성은 구문 분석 문자열에 특별한주의가 필요합니다. 여기에는 `CString` 개체가 포함됩니다.

> [!NOTE]
> MFC의 유니코드 문자열 직렬화는 실행 중인 응용 프로그램의 버전에 관계없이 유니코드 및 MBCS 문자열을 모두 읽을 수 있습니다. 데이터 파일은 유니코드와 MBCS 버전의 프로그램 간에 이식가능합니다.

`CString`멤버 함수는 호출하는 C 런타임 함수의 특수 "일반 텍스트" 버전을 사용하거나 유니코드 인식 함수를 사용합니다. 따라서 예를 들어 함수가 `CString` 일반적으로 `strcmp`호출하는 경우 해당 제네릭 텍스트 함수를 `_tcscmp` 호출합니다. 기호_MBCS 및 _UNICODE 정의되는 방식에 `_tcscmp` 따라 다음과 같이 매핑됩니다.

|||
|-|-|
|_MBCS 정의됨|`_mbscmp`|
|_UNICODE 정의됨|`wcscmp`|
|두 심볼 모두 정의되지 않음|`strcmp`|

> [!NOTE]
> _MBCS _UNICODE 기호는 상호 배타적입니다.

모든 런타임 문자열 처리 루틴에 대한 일반 텍스트 함수 매핑은 [C 런타임 라이브러리 참조에서](../c-runtime-library/c-run-time-library-reference.md)설명합니다. 목록은 [국제화를](../c-runtime-library/internationalization.md)참조하십시오.

마찬가지로 `CString` 메서드는 일반 데이터 형식 매핑을 사용하여 구현됩니다. MBCS와 유니코드를 모두 활성화하기 위해 MFC는 `wchar_t`문자 또는 **문자에** **대한** <strong>\*</strong> LPTSTR, `wchar_t*` **const char** <strong>\*</strong> 또는 `const wchar_t*`에 대한 LPCTSTR에 대한 TCHAR를 사용합니다. 이렇게 하면 MBCS 또는 유니코드에 대한 올바른 매핑이 보장됩니다.

## <a name="see-also"></a>참고 항목

[문자열(ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[문자열 조작](../c-runtime-library/string-manipulation-crt.md)
