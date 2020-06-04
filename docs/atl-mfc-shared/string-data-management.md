---
title: 문자열 데이터 관리
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
ms.openlocfilehash: 7f92b38ac659faef2dd9319b2f204ba837f0d473
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317458"
---
# <a name="string-data-management"></a>문자열 데이터 관리

Visual C++는 문자열 데이터를 관리하는 여러 가지 방법을 제공합니다.

- C 스타일 null 종료 문자열로 작업하기 위한 [문자열 조작](../c-runtime-library/string-manipulation-crt.md)

- 문자열 관리를 위한 Win32 API 함수

- 유연하고 큰 규모의 문자열 개체를 제공하는 MFC의 클래스 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)

- 클래스 [CStringT 클래스는](../atl-mfc-shared/reference/cstringt-class.md)동일한 기능을 가진 MFC 독립적인 문자열 개체를 제공합니다.`CString`

거의 모든 프로그램은 문자열 데이터로 작동합니다. MFC의 `CString` 클래스는 유연한 문자열 처리를 위한 최상의 솔루션인 경우가 많습니다. 버전 7.0부터MFC 또는 MFC 독립 프로그램에서 사용할 `CString` 수 있습니다. 유니코드 또는 MBCS `CString` 프로그래밍에서와 같이 런타임 라이브러리와 다중 바이트(와이드) 문자를 포함하는 지원 문자열입니다.

이 문서에서는 클래스 라이브러리에서 문자열 조작과 관련된 범용 서비스에 대해 설명합니다. 이 문서에서 다루는 주제는 다음과 같습니다.

- [유니코드 및 MBCS로 이식성 제공](#_core_unicode_and_mbcs_provide_portability)

- [CStrings 및 const char 포인터](#_core_cstrings_and_const_char_pointers)

- [CString 참조 계수](#_core_cstring_reference_counting)

[CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md) 클래스는 문자열 조작을 지원합니다. C 런타임 라이브러리 문자열 패키지에서 일반적으로 제공하는 기능을 대체하고 확장하기 위한 것입니다. 클래스는 `CString` Basic에 있는 것과 유사한 단순화된 문자열 처리를 위해 멤버 함수와 연산자를 제공합니다. 또한 클래스는 s 및 표준 C++ 문자열 데이터 `CString`형식을 생성, 할당 및 비교하기 위한 생성자 및 연산자도 제공합니다. `CString` 에서 파생되지 `CObject`않으므로 대부분의 MFC(Microsoft Foundation 클래스 라이브러리)와 독립적으로 개체를 사용할 `CString` 수 있습니다.

`CString`개체는 "값 의미 체계"를 따릅니다. 개체는 `CString` 고유한 값을 나타냅니다. 문자열에 `CString` 대한 포인터가 아니라 실제 문자열로 생각하십시오.

개체는 `CString` 가변 문자 수의 시퀀스를 나타냅니다. `CString`개체는 문자 배열로 생각할 수 있습니다.

## <a name="unicode-and-mbcs-provide-portability"></a><a name="_core_unicode_and_mbcs_provide_portability"></a>유니코드 및 MBCS는 이식성을 제공합니다.

MFC 버전 3.0 이상에서는 을 `CString`포함한 MFC가 유니코드 및 다바이트 문자 집합(MBCS)에 모두 사용할 수 있습니다. 이 지원을 사용하면 유니코드 또는 ANSI 문자에 대해 빌드할 수 있는 이식 가능한 응용 프로그램을 쉽게 작성할 수 있습니다. 이 이식성을 활성화하기 위해 `CString` 개체의 각 문자는 응용 프로그램을 `wchar_t` `char` 빌드할 때 _UNICODE 기호를 정의하는 것처럼 정의되는 TCHAR 형식입니다. 문자너비는 `wchar_t` 16비트입니다. 정의된 기호로 빌드하는 경우 MBCS가 활성화_MBCS MFC 자체는 naFX 라이브러리의 _MBCS 기호 또는 정의된 _UNICODE 기호(UAFX 라이브러리용)로 빌드됩니다.

> [!NOTE]
> 이 `CString` 예제와 문자열의 함께 제공되는 문서에서는 리터럴 문자열을 폼으로 변환하는 _T 매크로를 사용하여 유니코드 이식성을 위해 올바르게 서식이 지정된 리터럴 문자열을 보여 준다.

`L"literal string"`

> [!NOTE]
> 컴파일러가 유니코드 문자열로 처리합니다. 예를 들어, 다음 코드는

[!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]

> [!NOTE]
> _UNICODE 정의된 경우 유니코드 문자열로 변환하거나 그렇지 않은 경우 ANSI 문자열로 변환됩니다. 자세한 내용은 [유니코드 및 다중바이트 문자 집합(MBCS) 지원](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)문서를 참조하십시오.

개체는 `CString` 최대 INT_MAX(2,147,483,647) 문자를 저장할 수 있습니다. TCHAR 데이터 형식은 `CString` 개체 내에서 개별 문자를 얻거나 설정하는 데 사용됩니다. 문자 배열과 달리 `CString` 클래스에는 기본 제공 메모리 할당 기능이 있습니다. 이렇게 `CString` 하면 개체가 필요에 따라 자동으로 증가할 수 있습니다(즉, `CString` 더 긴 문자열에 맞게 개체를 늘리는 것에 대해 걱정할 필요가 없습니다).

## <a name="cstrings-and-const-char-pointers"></a><a name="_core_cstrings_and_const_char_pointers"></a>CStrings 및 const char 포인터

개체는 `CString` 리터럴 C 스타일 문자열(유니코드가 `PCXSTR`아닌 경우 **const char와** <strong>\*</strong> 동일)처럼 작동할 수도 있습니다. [CSimpleStringT::연산자 PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr) `CString` 변환 연산자는 함수 호출에서 문자 포인터를 자유롭게 대체할 수 있습니다. **CString(LPCWSTR)** `pszSrc` **)** 생성자는 문자 포인터를 개체로 `CString` 대체할 수 있도록 합니다.

개체를 접으려고 `CString` 시도하지 않습니다. 예를 들어 `CString` 를 포함하는 `Chicago`두 개의 객체를 `Chicago` 만드는 경우 의 문자는 두 위치에 저장됩니다. (이 MFC의 이후 버전에서는 그렇지 않을 수 있으므로 이 버전에 의존해서는 안 됩니다.)

> [!NOTE]
> [CSimpleStringT::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 및 [CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) 멤버 함수를 문자에 `CString` 대한 비상성 포인터로 직접 액세스해야 하는 경우 사용합니다.

> [!NOTE]
> [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) 및 [CStringT::SetSysString](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) 멤버 함수를 사용하여 자동화에 사용되는 BSTR 개체를 할당하고 설정합니다(이전의 OLE 자동화).

> [!NOTE]
> 가능한 경우 힙이 아닌 프레임에 개체를 할당합니다. `CString` 이렇게 하면 메모리가 절약되고 매개 변수 전달이 간소화됩니다.

개체는 `CString` 컬렉션의 요소로 저장할 수 있지만 `CString` 클래스는 Microsoft Foundation 클래스 라이브러리 컬렉션 클래스로 구현되지 않습니다.

## <a name="cstring-reference-counting"></a><a name="_core_cstring_reference_counting"></a>CString 참조 계수

MFC 버전 4.0에서 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md) 개체가 복사될 때 MFC는 데이터를 복사하는 대신 참조 수를 증가시입니다. 이렇게 하면 값별로 매개 `CString` 변수를 전달하고 값별로 개체를 반환하는 것이 더 효율적입니다. 이러한 작업을 통해 복사 생성자가 호출되고 때로는 두 번 이상 호출됩니다. 참조 수를 증가하면 이러한 공통 작업에 대한 오버헤드가 줄어들고 더 매력적인 옵션을 사용할 `CString` 수 있습니다.

각 복사본이 소멸되면 원래 개체의 참조 수가 감소됩니다. 원래 `CString` 개체는 참조 수가 0으로 줄어들 때까지 소멸되지 않습니다.

`CString` 멤버 함수 [CSimpleStringT::LockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) 및 [CSimpleStringT::UnlockBuffer를](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) 사용하여 참조 계수를 비활성화하거나 활성화할 수 있습니다.

## <a name="see-also"></a>참고 항목

[일반 MFC 항목](../mfc/general-mfc-topics.md)
