---
title: C 스타일 문자열 관련 CString 작업
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- MFC [C++], string handling class
- string conversion [C++], C-style strings
- strings [C++], string operations
- standard run-time library string functions
- null values, Null-terminated string conversion
- string functions
- strings [C++], in C
- string arguments
- C-style strings
- strings [C++], class CString
- casting CString objects
ms.assetid: 5048de8a-5298-4891-b8a0-c554b5a3ac1b
ms.openlocfilehash: 406a934d3691c7787085cc319770074ac2ee5926
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317943"
---
# <a name="cstring-operations-relating-to-c-style-strings"></a>C 스타일 문자열 관련 CString 작업

[CString](../atl-mfc-shared/using-cstring.md) 개체에는 문자열 데이터가 포함되어 있습니다. `CString`문자열 데이터로 작업할 클래스 템플릿 [CStringT에](../atl-mfc-shared/reference/cstringt-class.md) 정의된 [메서드 및 연산자의](../atl-mfc-shared/reference/cstringt-class.md) 집합을 상속합니다. (지원하는`CString` 문자 데이터의 `CStringT` 종류로 작업하는 전문 유형 `CString` **def입니다.)**

`CString`은 문자 데이터를 C 스타일의 null로 종료되는 문자열로 저장하지 않습니다. 대신 `CString`은 필요한 데이터와 공간을 보다 안전하게 감시하기 위해 문자 데이터 길이를 추적합니다.

`CString`은 C 스타일 문자열을 허용하며 C 스타일 문자열로 문자 데이터에 액세스하는 방법을 제공합니다. 이 항목의 다음 섹션에서는 C 스타일의 null로 종료되는 문자열처럼 `CString` 개체를 사용하는 방법을 설명합니다.

- [C 스타일의 null로 종료되는 문자열로 변환](#_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string)

- [표준 런타임 라이브러리 문자열 함수 사용](#_core_working_with_standard_run.2d.time_library_string_functions)

- [CString 콘텐츠 직접 수정](#_core_modifying_cstring_contents_directly)

- [가변 인수 함수가 있는 CString 개체 사용](#_core_using_cstring_objects_with_variable_argument_functions)

- [CString 형식 매개 변수 지정](#_core_specifying_cstring_formal_parameters)

## <a name="using-cstring-as-a-c-style-null-terminated-string"></a><a name="_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string"></a>C-스타일 Null 종료 문자열로 CString 사용

개체를 `CString` C 스타일 문자열로 사용하려면 개체를 LPCTSTR에 캐스팅합니다. 다음 예에서 `CString`은 C 스타일의 null로 종료되는 읽기 전용 문자열에 대한 포인터를 반환합니다. `strcpy` 함수는 C 스타일 문자열 복사본을 `myString` 변수에 포함합니다.

```cpp
CString aCString = "A string";
char myString[256];
strcpy(myString, (LPCTSTR)aCString);
```

`CString` 등의 `SetAt` 메서드를 사용하여 문자열 개체에서 개별 문자를 수정할 수 있습니다. 그러나 LPCTSTR 포인터는 일시적이며 `CString`에 대한 변경사항이 있을 때 유효하지 않게 됩니다. `CString`이 범위를 벗어나 자동으로 삭제될 수도 있습니다. 개체를 사용할 때마다 새 LPCTSTR `CString` 포인터를 사용하는 것이 좋습니다.

`CString` 데이터의 복사본을 직접 수정해야 할 수도 있습니다. `strcpy_s` 개체를 별도의 버퍼에 복사하려면 보다 안전한 `_tcscpy_s` 함수 또는 유니코드/MBCS 이식 가능 `CString`를 사용합니다. 이렇게 하면 다음 예에 나와 있는 것처럼 문자를 안전하게 수정할 수 있습니다.

[!code-cpp[NVC_ATLMFC_Utilities#189](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_1.cpp)]

> [!NOTE]
> 세 번째 `strcpy_s` 인수(또는 유니코드/MBCS `_tcscpy_s`이식)는 `const wchar_t*` (유니코드) 또는 `const char*` ANSI입니다. 위의 예에서는 이 인수에 대해 `CString`을 전달합니다. C++ 컴파일러는 `CString`을 `CString`로 변환하는 `LPCTSTR` 클래스에 대해 정의된 변환 함수를 자동으로 적용합니다. C++의 가장 유용한 기능 중 하나는 형식 간의 캐스팅 작업을 정의하는 기능입니다.

## <a name="working-with-standard-run-time-library-string-functions"></a><a name="_core_working_with_standard_run.2d.time_library_string_functions"></a>표준 런타임 라이브러리 문자열 함수 작업

`CString` 또는 유니코드/MBCS 이식 가능 `strcmp`와 같은 표준 C 런타임 라이브러리 문자열 함수를 사용할 수 있는 모든 문자열 작업을 수행하는 `_tcscmp` 메서드를 찾을 수 있습니다.

C 런타임 문자열 함수를 사용해야 하는 경우 _core_using_cstring_as_a_c.2d.style_null.terminated_string 설명된 기술을 사용할 수 있습니다. `CString` 개체를 해당하는 C 스타일 문자열 버퍼에 복사하고 버퍼에 대해 작업을 수행한 다음 결과로 생성된 C 스타일 문자열을 `CString` 개체에 다시 할당할 수 있습니다.

## <a name="modifying-cstring-contents-directly"></a><a name="_core_modifying_cstring_contents_directly"></a>CString 내용 직접 수정

대부분의 경우에는 `CString` 멤버 함수를 사용하여 `CString` 개체의 콘텐츠를 수정하거나 `CString`을 C 스타일 문자열로 변환해야 합니다.

그러나 문자 버퍼가 필요한 운영 체제 함수를 사용하는 등의 경우에는 `CString` 콘텐츠를 직접 수정할 수 있습니다.

`GetBuffer` 및 `ReleaseBuffer` 메서드를 통해 `CString` 개체의 내부 문자 버퍼에 액세스하여 해당 버퍼를 직접 수정할 수 있습니다. 다음 단계에서는 이러한 작업을 위해 해당 함수를 사용하는 방법을 보여줍니다.

### <a name="to-use-getbuffer-and-releasebuffer-to-access-the-internal-character-buffer-of-a-cstring-object"></a>GetBuffer 및 ReleaseBuffer를 사용하여 CString 개체의 내부 문자 버퍼에 액세스하려면

1. `GetBuffer` 개체에 대해 `CString`를 호출하고 필요한 버퍼 길이를 지정합니다.

1. `GetBuffer`에서 반환하는 포인터를 사용하여 `CString` 개체에 문자를 직접 씁니다.

1. `ReleaseBuffer` 개체에 대해 `CString`를 호출하여 문자열 길이 등의 모든 내부 `CString` 상태 정보를 업데이트합니다. `CString` 개체의 콘텐츠를 직접 수정한 후에는 `ReleaseBuffer`를 호출한 후에 다른 `CString` 멤버 함수를 호출해야 합니다.

## <a name="using-cstring-objects-with-variable-argument-functions"></a><a name="_core_using_cstring_objects_with_variable_argument_functions"></a>가변 인수 함수가 있는 CString 개체 사용

일부 C 함수는 가변 인수 수를 사용합니다. 이러한 함수의 대표적인 예로 `printf_s`가 있습니다. 이러한 종류의 함수가 선언되는 방식으로 인해 컴파일러는 인수의 형식을 명확하게 파악할 수 없으며 각 인수에 대해 수행할 변환 작업을 결정할 수 없습니다. 따라서 가변 인수 수를 사용하는 함수로 `CString` 개체를 전달할 때는 명시적 형식 캐스팅을 사용해야 합니다.

변수 인수 `CString` 함수에서 개체를 사용 하려면 `CString` 다음 예제와 같이 LPCTSTR 문자열에 명시적으로 캐스팅 합니다.

[!code-cpp[NVC_ATLMFC_Utilities#190](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_2.cpp)]

## <a name="specifying-cstring-formal-parameters"></a><a name="_core_specifying_cstring_formal_parameters"></a>CString 형식 매개 변수 지정

문자열 인수가 필요한 대부분의 함수에서는 함수 프로토타입의 정식 매개 변수를 `const` 대신 문자에 대한 `LPCTSTR` 포인터(`CString`)로 지정하는 것이 가장 좋습니다. 형식 매개 변수가 문자에 대한 `const` 포인터로 지정되면 TCHAR 배열, 리터럴 문자열 []또는`"hi there"`개체에 대한 포인터를 전달할 수 있습니다. `CString` 개체는 `CString` 자동으로 LPCTSTR로 변환됩니다. LPCTSTR을 사용할 수 있는 모든 장소에서 `CString` 개체를 사용할 수도 있습니다.

인수가 수정되지 않는 경우 형식 매개 변수를 `const CString&`상수 문자열 참조(즉,)로 지정할 수도 있습니다. 함수에 의해 문자열이 수정될 경우 **구성 컨스트** 수정자를 놓습니다. 기본 null 값을 사용하려면 아래에 나와 있는 것처럼 정식 매개 변수를 null 문자열 [`""`]로 초기화합니다.

[!code-cpp[NVC_ATLMFC_Utilities#191](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_3.cpp)]

대부분의 함수 결과에 대해 값을 기준으로 `CString` 개체를 반환할 수 있습니다.

## <a name="see-also"></a>참고 항목

[문자열(ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CString 인수 전달](../atl-mfc-shared/cstring-argument-passing.md)
