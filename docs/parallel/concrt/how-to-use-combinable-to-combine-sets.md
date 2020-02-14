---
title: '방법: combinable을 사용하여 집합 결합'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
ms.openlocfilehash: 7ccbb3e8bad5c4d3b6f4177afbfdba3e200681a5
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142124"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>방법: combinable을 사용하여 집합 결합

이 항목에서는 [concurrency:: 결합할](../../parallel/concrt/reference/combinable-class.md) 수 있는 클래스를 사용 하 여 소수 집합을 계산 하는 방법을 보여 줍니다.

## <a name="example"></a>예제

다음 예제에서는 소수 집합을 두 번 계산합니다. 각 계산은 [std:: bitset](../../standard-library/bitset-class.md) 개체에 결과를 저장 합니다. 이 예제에서는 먼저 직렬로 집합을 계산한 후 병렬로 집합을 계산합니다. 또한 이 예제에서는 두 계산을 모두 수행하는 데 필요한 시간을 콘솔에 출력합니다.

이 예제에서는 [concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘과 `combinable` 개체를 사용 하 여 스레드 로컬 집합을 생성 합니다. 그런 다음 [concurrency:: 결합할 수:: combine_each](reference/combinable-class.md#combine_each) 메서드를 사용 하 여 스레드 로컬 집합을 최종 집합으로 결합 합니다.

[!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]

프로세서가 4개인 컴퓨터의 샘플 출력은 다음과 같습니다.

```Output
serial time: 312 ms

parallel time: 78 ms
```

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사 하 여 Visual Studio 프로젝트에 붙여넣거나, `parallel-combine-primes.cpp` 이름이 지정 된 파일에 붙여 넣은 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.

> **cl.exe/EHsc parallel-combine-primes**

## <a name="see-also"></a>참고 항목

[병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable 클래스](../../parallel/concrt/reference/combinable-class.md)<br/>
[결합할 때:: combine_each 메서드](reference/combinable-class.md#combine_each)
