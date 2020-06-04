---
title: '&lt;list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <list>
helpviewer_keywords:
- list header
ms.assetid: 2345823b-5612-44d8-95d3-aa96ed076d17
ms.openlocfilehash: 6b67434d36146de87a124fc02f49971425943dc5
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447288"
---
# <a name="ltlistgt"></a>&lt;list&gt;

컨테이너 클래스 템플릿 목록과 여러 지원 템플릿을 정의 합니다.

## <a name="syntax"></a>구문

```cpp
#include <list>
```

> [!NOTE]
> \<목록 > 라이브러리에도 `#include <initializer_list>` 문이 사용 됩니다.

## <a name="members"></a>구성원

### <a name="operators"></a>연산자

|||
|-|-|
|[operator!=](../standard-library/list-operators.md#op_neq)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체와 같지 않은지 테스트합니다.|
|[operator<](../standard-library/list-operators.md#op_lt)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체보다 작은지 테스트합니다.|
|[operator\<=](../standard-library/list-operators.md#op_gt_eq)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체보다 작거나 같은지 테스트합니다.|
|[연산자==](../standard-library/list-operators.md#op_eq_eq)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체와 같은지 테스트합니다.|
|[operator>](../standard-library/list-operators.md#op_gt)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체보다 큰지 테스트합니다.|
|[operator>=](../standard-library/list-operators.md#op_gt_eq)|연산자의 좌변에 있는 목록 개체가 우변에 있는 목록 개체보다 크거나 같은지 테스트합니다.|

### <a name="functions"></a>Functions

|||
|-|-|
|[swap](../standard-library/list-functions.md#swap)|두 목록의 요소를 교환합니다.|

### <a name="classes"></a>클래스

|||
|-|-|
|[list 클래스](../standard-library/list-class.md)|선형 배열에서 해당 요소를 유지 관리 하 고 시퀀스 내의 모든 위치에서 효율적인 삽입 및 삭제를 허용 하는 시퀀스 컨테이너의 클래스 템플릿입니다.|

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)
