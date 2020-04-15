---
title: 기본 CString 작업
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
ms.openlocfilehash: 68947dc37e5398ac7caa4754e9af40223cec7bf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317954"
---
# <a name="basic-cstring-operations"></a>기본 CString 작업

이 항목에서는 다음과 같은 기본 [CString](../atl-mfc-shared/reference/cstringt-class.md) 작업에 대해 설명합니다.

- [표준 C 리터럴 문자열에서 CString 개체 만들기](#_core_creating_cstring_objects_from_standard_c_literal_strings)

- [CString에서 개별 문자 에 액세스](#_core_accessing_individual_characters_in_a_cstring)

- [두 개의 CString 개체 통합](#_core_concatenating_two_cstring_objects)

- [CString 개체 비교](#_core_comparing_cstring_objects)

- [CString 개체 변환](#_core_converting_cstring_objects)

`Class CString`클래스 템플릿 [CStringT 클래스를](../atl-mfc-shared/reference/cstringt-class.md)기반으로 합니다. `CString`의 **형식** `CStringT`def입니다. 더 정확히 `CString` 말하자면, `CStringT`클래스 *템플릿을* 사용하여 클래스를 정의하는 일반적인 방법입니다. **typedef** 마찬가지로 정의된 `CStringA` 클래스는 및 `CStringW`.

`CString`을 `CStringA`참조하십시오. `CStringW` `CStringT`는 cstringt.h에 정의됩니다.

`CString`과 `CStringA` `CStringW` 는 각각 그들이 지원하는 문자열 데이터와 함께 `CStringT` 사용하기 위해 정의 된 메서드 및 연산자의 집합을 가져옵니다. 일부 메서드는 복제되며 경우에 따라 C 런타임 라이브러리의 문자열 서비스를 능가합니다.

참고: `CString` 네이티브 클래스입니다. C++/CLI 관리 프로젝트에서 사용할 문자열 클래스의 경우 `System.String`을 사용합니다.

## <a name="creating-cstring-objects-from-standard-c-literal-strings"></a><a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a>표준 C 리터럴 문자열에서 CString 개체 만들기

한 `CString` 개체를 다른 개체에 할당할 `CString` 수 있는 것처럼 C 스타일 리터럴 문자열을 할당할 수 있습니다.

- 개체에 C 리터럴 문자열의 값을 `CString` 할당합니다.

   [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]

- 하나의 `CString` 값을 다른 `CString` 개체에 할당합니다.

   [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]

   한 `CString` 개체가 `CString` 다른 개체에 할당될 때 개체의 내용이 복사됩니다. 따라서 두 문자열은 문자열을 구성하는 실제 문자에 대한 참조를 공유하지 않습니다. 개체를 값으로 사용하는 `CString` 방법에 대한 자세한 내용은 [CString 시맨틱을](../atl-mfc-shared/cstring-semantics.md)참조하십시오.

   > [!NOTE]
   > 유니코드 또는 ANSI에 대해 컴파일할 수 있도록 응용 프로그램을 작성하려면 _T 매크로를 사용하여 리터럴 문자열을 코딩합니다. 자세한 내용은 [유니코드 및 다중바이트 문자 집합(MBCS) 지원을](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)참조하십시오.

## <a name="accessing-individual-characters-in-a-cstring"></a><a name="_core_accessing_individual_characters_in_a_cstring"></a>CString에서 개별 문자 에 액세스

및 메서드를 사용하여 `CString` `SetAt` 개체의 개별 문자에 액세스할 수 `GetAt` 있습니다. 개별 문자를 얻는 대신 `GetAt` 배열 요소 또는 하위 스크립트 연산자 (] ] )를 사용할 수도 있습니다. (이것은 표준 C 스타일 문자열에서와 같이 인덱스별로 배열 요소에 액세스하는 것과 유사합니다.) 문자의 `CString` 인덱스 값은 0을 기준으로 합니다.

## <a name="concatenating-two-cstring-objects"></a><a name="_core_concatenating_two_cstring_objects"></a>두 개의 CString 개체 통합

두 `CString` 객체를 연결하려면 다음과 같이 연결 연산자(+ 또는 +=)를 사용합니다.

[!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]

연결 연산자(+ 또는 +=)에 대한 인수가 `CString` 하나 이상 이어야 하지만 다른 인수에 대해 `"big"`상수 문자 문자열(예: 'x')이나 **char(예:** 'x')를 사용할 수 있습니다.

## <a name="comparing-cstring-objects"></a><a name="_core_comparing_cstring_objects"></a>CString 개체 비교

`Compare` 메서드와 == `CString` 연산자는 동일합니다. `Compare`. **연산자 = =**= 및 `CompareNoCase` MBCS 및 유니코드 인식; `CompareNoCase` 또한 대/소문자를 구분하지 않습니다. 방법은 `Collate` `CString` 로캘에 민감하며 종종 보다 `Compare`느립니다. 현재 `Collate` 로캘에서 지정한 정렬 규칙을 준수해야 하는 경우에만 사용합니다.

다음 표에서는 C 런타임 라이브러리에서 사용 가능한 [CString](../atl-mfc-shared/reference/cstringt-class.md) 비교 함수와 해당 유니코드/MBCS 이식 가능한 함수를 보여 주었습니다.

|CString 함수|MBCS 기능|유니코드 함수|
|----------------------|-------------------|----------------------|
|`Compare`|`_mbscmp`|`wcscmp`|
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|
|`Collate`|`_mbscoll`|`wcscoll`|

클래스 `CStringT` 템플릿은 `CString`에서 사용할 수 있는 \<관계형 연산자(<, =, >=, >, ==및 !=)를 정의합니다. 다음 예제와 `CStrings` 같이 이러한 연산자를 사용하여 두 연산을 비교할 수 있습니다.

[!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]

## <a name="converting-cstring-objects"></a><a name="_core_converting_cstring_objects"></a>CString 개체 변환

CString 개체를 다른 문자열 유형으로 변환하는 방법에 대한 자세한 내용은 [다양한 문자열 형식 간에 변환하는 방법을](../text/how-to-convert-between-various-string-types.md)참조하십시오.

## <a name="using-cstring-with-wcout"></a>wcout을 사용하여 CString 사용

CString을 `wcout` 사용하려면 다음 예제와 같이 `const wchar_t*` 개체를 a에 명시적으로 캐스팅해야 합니다.

```cpp
CString cs("meow");

wcout << (const wchar_t*) cs << endl;
```

캐스트가 없으면 `cs` a로 `void*` 처리되고 `wcout` 개체의 주소를 인쇄합니다. 이 동작은 템플릿 인수 추론과 과부하 확인 간의 미묘한 상호 작용으로 인해 발생하며 그 자체로 C++ 표준을 준수합니다.

## <a name="see-also"></a>참고 항목

[문자열(ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[템플릿 특수화](../cpp/template-specialization-cpp.md)<br/>
[방법: 다양한 문자열 형식 간 변환](../text/how-to-convert-between-various-string-types.md)
