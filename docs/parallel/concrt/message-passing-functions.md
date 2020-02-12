---
title: 메시지 전달 함수
ms.date: 11/04/2016
helpviewer_keywords:
- message passing functions
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
ms.openlocfilehash: 4e1052a59f355c4ad5a7c6b57724268c24a209b4
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143293"
---
# <a name="message-passing-functions"></a>메시지 전달 함수

비동기 에이전트 라이브러리는 구성 요소 간에 메시지를 전달 하는 데 사용할 수 있는 여러 함수를 제공 합니다.

이러한 메시지 전달 함수는 다양 한 메시지 블록 형식과 함께 사용 됩니다. 동시성 런타임에서 정의한 메시지 블록 형식에 대 한 자세한 내용은 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)을 참조 하세요.

## <a name="top"></a> 섹션

이 항목에서는 다음 메시지 전달 함수에 대해 설명 합니다.

- [send 및 asend](#send)

- [수신 및 try_receive](#receive)

- [예](#examples)

## <a name="send"></a>send 및 asend

[Concurrency:: send](reference/concurrency-namespace-functions.md#send) 함수는 지정 된 대상에 동기적으로 메시지를 보내고 [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) 함수는 지정 된 대상에 비동기적으로 메시지를 보냅니다. `send` 및 `asend` 함수는 모두 메시지가 메시지를 수락 하거나 거부 한다는 것을 나타내는 것으로 표시 될 때까지 기다립니다.

`send` 함수는 대상에서 반환 하기 전에 메시지를 수락 하거나 거절할 때까지 대기 합니다. `send` 함수는 메시지가 배달 되었으면 **true** 를 반환 하 고 그렇지 않으면 **false** 를 반환 합니다. `send` 함수는 동기적으로 작동 하므로 `send` 함수는 반환 되기 전에 대상이 메시지를 받을 때까지 대기 합니다.

반대로 `asend` 함수는 대상에서 메시지를 반환 하기 전에 메시지를 수락 하거나 거부할 때까지 기다리지 않습니다. 대신, 대상이 메시지를 수락 하 고 최종적으로 사용 하는 경우 `asend` 함수는 **true** 를 반환 합니다. 그렇지 `asend` 않으면 **false** 를 반환 하 여 대상이 메시지를 거부 하거나 메시지의 사용 여부에 대 한 결정을 연기 했음을 나타냅니다.

[[맨 위로 이동](#top)]

## <a name="receive"></a>수신 및 try_receive

[Concurrency:: receive](reference/concurrency-namespace-functions.md#receive) 및 [concurrency:: try_receive](reference/concurrency-namespace-functions.md#try_receive) 함수는 지정 된 소스에서 데이터를 읽습니다. `receive` 함수는 데이터를 사용할 수 있을 때까지 대기 하는 반면 `try_receive` 함수는 즉시 반환 됩니다.

데이터를 계속 사용 해야 하는 경우 `receive` 함수를 사용 합니다. 현재 컨텍스트를 차단 하지 않거나 계속할 데이터를 갖지 않아도 되는 경우 `try_receive` 함수를 사용 합니다.

[[맨 위로 이동](#top)]

## <a name="examples"></a> 예제

`send` 및 `asend`및 `receive` 함수를 사용 하는 예제는 다음 항목을 참조 하세요.

- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)

- [방법: 다양한 공급자-소비자 패턴 구현](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)

- [방법: call 및 transformer 클래스에 작업 함수 제공](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)

- [방법: 데이터 파이프라인에서 transformer 사용](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)

- [방법: 완료된 작업 간 선택](../../parallel/concrt/how-to-select-among-completed-tasks.md)

- [방법: 정기적으로 메시지 보내기](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)

- [방법: 메시지 블록 필터 사용](../../parallel/concrt/how-to-use-a-message-block-filter.md)

[[맨 위로 이동](#top)]

## <a name="see-also"></a>참고 항목

[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[send 함수](reference/concurrency-namespace-functions.md#send)<br/>
[asend 함수](reference/concurrency-namespace-functions.md#asend)<br/>
[receive 함수](reference/concurrency-namespace-functions.md#receive)<br/>
[try_receive 함수](reference/concurrency-namespace-functions.md#try_receive)
