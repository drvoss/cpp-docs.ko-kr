---
title: CString 인수 전달
ms.date: 11/04/2016
helpviewer_keywords:
- strings [C++], as function input/output
- argument passing [C++]
- arguments [C++], passing
- functions [C++], strings as input/output
- argument passing [C++], C strings
- passing arguments, C strings
- CString objects, passing arguments
- string arguments
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
ms.openlocfilehash: 53977eb47520a20571a2d5ba8aa105c567ff40d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317927"
---
# <a name="cstring-argument-passing"></a>CString 인수 전달

이 문서에서는 [CString](../atl-mfc-shared/reference/cstringt-class.md) 개체를 함수에 전달하는 `CString` 방법과 함수에서 개체를 반환하는 방법에 대해 설명합니다.

## <a name="cstring-argument-passing-conventions"></a><a name="_core_cstring_argument.2d.passing_conventions"></a>CString 인수 전달 규칙

클래스 인터페이스를 정의할 때 멤버 함수에 대한 인수 전달 규칙을 결정해야 합니다. 개체를 전달하고 반환하는 `CString` 몇 가지 표준 규칙이 있습니다. [함수 입력으로 문자열에](#_core_strings_as_function_inputs) 설명된 규칙을 따르고 함수 [출력으로 문자열을](#_core_strings_as_function_outputs)따르는 경우 효율적이고 올바른 코드를 갖게 됩니다.

## <a name="strings-as-function-inputs"></a><a name="_core_strings_as_function_inputs"></a>함수 입력으로 문자열

호출된 함수에서 `CString` 개체를 사용하는 가장 효율적이고 안전한 `CString` 방법은 함수에 개체를 전달하는 것입니다. 이름에도 불구하고 `CString` 개체는 null 종결자가 있는 C 스타일 문자열로 내부적으로 문자열을 저장하지 않습니다. 대신 개체는 `CString` 개체의 문자 수를 주의 깊게 추적합니다. null `CString` 종료 된 문자열에 LPCTSTR 포인터를 제공 하는 것은 코드에서 지속적으로 수행 해야 하는 경우 중요 한 될 수 있는 작업의 작은 금액입니다. `CString` 내용을 변경하면 LPCTSTR 포인터의 이전 복사본이 무효화되므로 결과가 일시적입니다.

경우에 따라 C 스타일 문자열을 제공하는 것이 합리적입니다. 예를 들어 호출된 함수가 C로 작성되고 개체를 지원하지 않는 상황이 있을 수 있습니다. 이 경우 매개 변수를 `CString` LPCTSTR로 강제 변환하면 함수에 C 스타일 null 종료 문자열이 표시됩니다. C 스타일 문자열 매개 변수를 `CString` 허용하는 `CString` 생성자사용을 사용하여 다른 방향으로 이동하여 개체를 만들 수도 있습니다.

함수에 의해 문자열 내용을 변경하려면 매개 변수를 비상 `CString` 참조()로`CString&`선언합니다.

## <a name="strings-as-function-outputs"></a><a name="_core_strings_as_function_outputs"></a>함수 출력과 같은 문자열

일반적으로 개체는 `CString` 기본 형식과 `CString` 같은 값 의미 체계를 따르기 때문에 함수에서 개체를 반환할 수 있습니다. 읽기 전용 문자열을 반환하려면 상수 `CString` `const CString&`참조()를 사용합니다. 다음 예제에서는 매개 변수 `CString` 및 반환 형식의 사용을 보여 줍니다.

[!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]

## <a name="see-also"></a>참고 항목

[문자열(ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
