---
title: '&lt;set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <set>
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
ms.openlocfilehash: 4ac5c0bbf94c4d17389efb424d2e12b84717c4a9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846227"
---
# <a name="ltsetgt"></a>&lt;set&gt;

컨테이너 클래스 템플릿 집합과 multiset 및 해당 지원 템플릿을 정의 합니다.

## <a name="requirements"></a>요구 사항

**헤더:**\<set>

**네임스페이스:** std

> [!NOTE]
> \<set>또한 라이브러리는 문을 사용 `#include <initializer_list>` 합니다.

## <a name="members"></a>멤버

### <a name="operators"></a>연산자

|set 버전|multiset 버전|설명|
|-|-|-|
|[operator! = (set)](../standard-library/set-operators.md#op_neq)|[operator! = (multiset)](../standard-library/set-operators.md#op_neq)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체와 같지 않은지 테스트합니다.|
|[연산자< (set)](../standard-library/set-operators.md#op_lt)|[연산자< (multiset)](../standard-library/set-operators.md#op_lt_multiset)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 작은지 테스트합니다.|
|[연산자<= (set)](../standard-library/set-operators.md#op_lt_eq)|[operator\<= (multiset)](../standard-library/set-operators.md#op_lt_eq_multiset)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 작거나 같은지 테스트합니다.|
|[operator = = (set)](../standard-library/set-operators.md#op_eq_eq)|[operator = = (multiset)](../standard-library/set-operators.md#op_eq_eq_multiset)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체와 같은지 테스트합니다.|
|[연산자> (set)](../standard-library/set-operators.md#op_gt)|[연산자> (multiset)](../standard-library/set-operators.md#op_gt_multiset)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 큰지 테스트합니다.|
|[연산자>= (set)](../standard-library/set-operators.md#op_gt_eq)|[연산자>= (multiset)](../standard-library/set-operators.md#op_gt_eq_multiset)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 크거나 같은지 테스트합니다.|

### <a name="specialized-template-functions"></a>특별 템플릿 함수

|set 버전|multiset 버전|설명|
|-|-|-|
|[스왑을](../standard-library/set-functions.md#swap)|[swap (multiset)](../standard-library/set-functions.md#swap_multiset)|두 set 또는 multiset의 요소를 교환합니다.|

### <a name="classes"></a>클래스

|이름|설명|
|-|-|
|[set 클래스](../standard-library/set-class.md)|포함된 요소의 값이 고유하고 데이터가 자동 정렬되는 기준인 키 값으로 사용된 컬렉션의 데이터를 스토리지 및 검색하는 데 사용됩니다.|
|[multiset 클래스](../standard-library/multiset-class.md)|포함된 요소의 값이 고유할 필요가 없고 데이터가 자동 정렬되는 기준인 키 값으로 사용된 컬렉션의 데이터를 스토리지 및 검색하는 데 사용됩니다.|

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C + + 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)
