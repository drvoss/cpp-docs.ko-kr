---
title: 전처리기
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: 7188d7a6803c9eec109a59906cf0c016a460819d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337491"
---
# <a name="preprocessor"></a>전처리기

전처리기는 첫 번째 변환 단계의 일부로 소스 파일의 텍스트를 조작하는 텍스트 처리기입니다. 전처리기는 원본 텍스트를 구문 분석하지 않지만 매크로 호출을 찾기 위해 토큰으로 분리합니다. 컴파일러는 일반적으로 첫 번째 단계에서 전처리기를 호출하지만, 컴파일 없이 텍스트를 처리하기 위해 전처리기를 별도로 호출할 수도 있습니다.

전처리기에 대한 참조 자료에는 다음 단원이 포함되어 있습니다.

- [전처리기 지시문](../preprocessor/preprocessor-directives.md)

- [전처리 연산자](../preprocessor/preprocessor-operators.md)

- [미리 정의된 매크로](../preprocessor/predefined-macros.md)

- [pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**마이크로소프트 특정**

[/E](../build/reference/e-preprocess-to-stdout.md) 또는 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 컴파일러 옵션을 사용하여 사전 처리 후 소스 코드 목록을 가져올 수 있습니다. 두 옵션 모두 전처리기를 호출하고 결과 텍스트를 표준 출력 장치로 보냅니다. 두 옵션의 차이점은 `/E` 지시문을 `#line` 포함하고 이러한 `/EP` 지시문을 제거하는 것입니다.

**Microsoft 전용 종료**

## <a name="special-terminology"></a><a name="_predir_special_terminology"></a>특수 용어

전처리기 설명서에서 "인수"라는 용어는 함수에 전달되는 엔터티를 나타냅니다. 경우에 따라 함수 호출에 지정된 인수 식과 함수 정의에 지정된 인수 선언을 각각 설명하는 "실제" 또는 "formal"으로 수정됩니다.

"변수"라는 용어는 간단한 C 형식 데이터 개체를 나타냅니다. "object"라는 용어는 C++ 개체와 변수를 모두 나타냅니다. 그것은 포괄적 인 용어입니다.

## <a name="see-also"></a>참고 항목

[C/C++ 전처리기 참조](../preprocessor/c-cpp-preprocessor-reference.md)\
[번역 단계](../preprocessor/phases-of-translation.md)
