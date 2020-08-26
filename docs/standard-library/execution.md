---
title: '&lt;문제점&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: f37458fdc0b58968e095a7c59de797eac295bde7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835938"
---
# <a name="ltexecutiongt"></a>&lt;문제점&gt;

병렬 알고리즘에 대 한 실행 정책에 대해 설명 합니다.

## <a name="syntax"></a>구문

```
namespace std {
    template<class T> inline constexpr bool is_execution_policy_v = is_execution_policy<T>::value;
}
namespace std::execution {
    inline constexpr sequenced_policy seq { unspecified };
    inline constexpr parallel_policy par { unspecified };
    inline constexpr parallel_unsequenced_policy par_unseq { unspecified };
}
```

### <a name="classes-and-structs"></a>클래스 및 구조체

|Name|설명|
|-|-|
|[is_execution_policy 구조체](is-execution-policy-struct.md)|모호한 오버 로드 확인 참여의 함수 시그니처를 제외 하기 위해 실행 정책을 검색 합니다.|
|[parallel_policy 클래스](parallel-policy-class.md)|병렬 알고리즘 오버 로드를 명확 하 게 구분 하는 고유 형식으로 사용 되며 병렬 알고리즘의 실행이 병렬화 될 수 있음을 표시 합니다.|
|[parallel_unsequenced_policy 클래스](parallel-unsequenced-policy-class.md)|병렬 알고리즘 오버 로드를 명확 하 게 구분 하는 고유한 형식으로 사용 되며 병렬 알고리즘의 실행이 병렬화 되 고 벡터화 수 있음을 표시 합니다.|
|[sequenced_policy 클래스](sequenced-policy-class.md)|병렬 알고리즘 오버 로드를 명확 하 게 구분 하기 위해 고유한 형식으로 사용 되며 병렬 알고리즘의 실행이 병렬화 될 수 있어야 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:**\<execution>

**네임스페이스:** stdext

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](cpp-standard-library-header-files.md)\
[C + + 표준 라이브러리의 스레드 보안](thread-safety-in-the-cpp-standard-library.md)\
[C + + 표준 라이브러리 참조](cpp-standard-library-reference.md)
