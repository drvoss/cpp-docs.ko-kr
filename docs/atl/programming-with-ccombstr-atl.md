---
title: CComBSTR을 사용한 프로그래밍(ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
ms.openlocfilehash: 020c2d18c721e658d15bb1451039154ae50b99f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321790"
---
# <a name="programming-with-ccombstr-atl"></a>CComBSTR을 사용한 프로그래밍(ATL)

ATL 클래스 [CComBSTR은](../atl/reference/ccombstr-class.md) BSTR 데이터 형식 주위에 래퍼를 제공합니다. 유용한 `CComBSTR` 도구이지만 주의가 필요한 몇 가지 상황이 있습니다.

- [전환 문제](#programmingwithccombstr_conversionissues)

- [범위 문제](#programmingwithccombstr_scopeissues)

- [CComBSTR 개체를 명시적으로 해제](#programmingwithccombstr_explicitlyfreeing)

- [루프에서 CComBSTR 객체 사용](#programmingwithccombstr_usingloops)

- [메모리 누수 문제](#programmingwithccombstr_memoryleaks)

## <a name="conversion-issues"></a><a name="programmingwithccombstr_conversionissues"></a>전환 문제

여러 `CComBSTR` 메서드가 ANSI 문자열 인수를 유니코드로 자동으로 변환하지만 메서드는 항상 유니코드 형식 문자열을 반환합니다. 출력 문자열을 ANSI로 다시 변환하려면 ATL 변환 클래스를 사용합니다. ATL 변환 클래스에 대한 자세한 내용은 [ATL 및 MFC 문자열 변환 매크로를](reference/string-conversion-macros.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]

문자열 리터럴을 사용하여 `CComBSTR` 개체를 수정하는 경우 와이드 문자열을 사용합니다. 이렇게 하면 불필요한 변환이 줄어듭니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]

## <a name="scope-issues"></a><a name="programmingwithccombstr_scopeissues"></a>범위 문제

잘 행동한 클래스와 마찬가지로 `CComBSTR` 범위를 벗어날 때 리소스를 해제합니다. 함수가 `CComBSTR` 문자열에 대한 포인터를 반환하면 포인터가 이미 해제된 메모리를 참조하므로 문제가 발생할 수 있습니다. 이러한 경우 아래와 `Copy` 같이 메서드를 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]

## <a name="explicitly-freeing-the-ccombstr-object"></a><a name="programmingwithccombstr_explicitlyfreeing"></a>CComBSTR 개체를 명시적으로 해제

개체가 범위를 벗어나기 전에 `CComBSTR` 개체에 포함된 문자열을 명시적으로 해제할 수 있습니다. 문자열이 해제되면 개체가 `CComBSTR` 유효하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]

## <a name="using-ccombstr-objects-in-loops"></a><a name="programmingwithccombstr_usingloops"></a>루프에서 CComBSTR 객체 사용

클래스는 `CComBSTR` 연산자 나 메서드와 `+=` `Append` 같은 특정 작업을 수행하기 위해 버퍼를 할당하므로 꽉 루프 내에서 문자열 조작을 수행하는 것은 권장되지 않습니다. 이러한 상황에서는 `CStringT` 더 나은 성능을 제공합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]

## <a name="memory-leak-issues"></a><a name="programmingwithccombstr_memoryleaks"></a>메모리 누수 문제

초기화된 `CComBSTR` 주소를 **[out]** 매개 변수로 함수에 전달하면 메모리 누수가 발생합니다.

아래 예제에서는 함수가 `"Initialized"` `MyGoodFunction` 문자열을 대체할 때 문자열을 유지하도록 할당된 문자열이 유출됩니다.

[!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]

누출을 방지하려면 주소를 `Empty` `CComBSTR` **[out]** 매개 변수로 전달하기 전에 기존 개체의 메서드를 호출합니다.

함수의 매개 변수가 **[in, out]인**경우 동일한 코드로 인해 누출이 발생하지 않습니다.

## <a name="see-also"></a>참고 항목

[개념](../atl/active-template-library-atl-concepts.md)<br/>
[CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[스트링](../standard-library/basic-string-class.md)<br/>
[문자열 변환 매크로](../atl/reference/string-conversion-macros.md)
