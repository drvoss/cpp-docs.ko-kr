---
title: '연습: 사용자 지정 메시지 블록 만들기'
ms.date: 04/25/2019
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
ms.openlocfilehash: 3386994dce68812cf3ed0852a24d8910cb903acf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368567"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>연습: 사용자 지정 메시지 블록 만들기

이 문서에서는 들어오는 메시지를 우선 순위별로 정렬하는 사용자 지정 메시지 블록 유형을 만드는 방법을 설명합니다.

기본 제공 메시지 블록 형식은 광범위한 기능을 제공하지만 사용자 고유의 메시지 블록 유형을 만들고 응용 프로그램의 요구 사항에 맞게 사용자 지정할 수 있습니다. 비동기 에이전트 라이브러리에서 제공하는 기본 제공 메시지 블록 유형에 대한 설명은 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.

## <a name="prerequisites"></a>사전 요구 사항

이 연습을 시작하기 전에 다음 문서를 읽으십시오.

- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)

- [메시지 전달 기능](../../parallel/concrt/message-passing-functions.md)

## <a name="sections"></a><a name="top"></a>섹션

이 연습에는 다음과 같은 섹션이 있습니다.

- [사용자 지정 메시지 블록 디자인](#design)

- [priority_buffer 클래스 정의](#class)

- [전체 예제](#complete)

## <a name="designing-a-custom-message-block"></a><a name="design"></a>사용자 지정 메시지 블록 디자인

메시지 블록은 메시지를 보내고 받는 행위에 참여합니다. 메시지를 보내는 메시지 블록을 소스 *블록이라고*합니다. 메시지를 수신하는 메시지 블록을 *대상 블록이라고*합니다. 메시지를 보내고 받는 메시지 블록을 *전파자 블록이라고*합니다. 에이전트 라이브러리는 추상 클래스 [동시성을 사용합니다::ISource는](../../parallel/concrt/reference/isource-class.md) 소스 블록과 추상 클래스 [동시성을 나타내며 대상](../../parallel/concrt/reference/itarget-class.md) 블록을 나타냅니다. 에서 파생되는 소스 역할을 `ISource`하는 메시지 블록 형식; 에서 파생되는 대상으로 작용하는 `ITarget`메시지 블록 형식입니다.

메시지 블록 형식을 직접 `ISource` 파생시킬 `ITarget`수 있지만 에이전트 라이브러리는 모든 메시지 블록 유형에 공통적인 많은 기능을 수행하는 세 가지 기본 클래스(예: 오류 처리 및 메시지 블록 연결)를 동시성으로 안전하게 연결합니다. [동시성::source_block](../../parallel/concrt/reference/source-block-class.md) 클래스는 다른 `ISource` 블록에서 파생되고 메시지를 보냅니다. [동시성::target_block](../../parallel/concrt/reference/target-block-class.md) 클래스는 다른 `ITarget` 블록에서 파생되고 메시지를 수신합니다. [동시성::propagator_block](../../parallel/concrt/reference/propagator-block-class.md) 클래스는 다른 `ISource` `ITarget` 블록에서 파생및 메시지를 보내고 다른 블록에서 메시지를 수신합니다. 메시지 블록의 동작에 집중할 수 있도록 이 세 가지 기본 클래스를 사용하여 인프라 세부 정보를 처리하는 것이 좋습니다.

`source_block`및 `target_block` `propagator_block` 클래스는 원본과 대상 블록 사이의 연결 또는 링크를 관리하는 형식과 메시지가 처리되는 방법을 관리하는 형식에서 매개 변수화된 템플릿입니다. 에이전트 라이브러리는 링크 관리를 수행하는 두 가지 유형인 [동시성::single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) 및 [동시성:multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md)을 정의합니다. 클래스를 `single_link_registry` 사용하면 메시지 블록을 하나의 소스 또는 한 대상에 연결할 수 있습니다. 클래스를 `multi_link_registry` 사용하면 메시지 블록을 여러 소스 또는 여러 대상에 연결할 수 있습니다. 에이전트 라이브러리는 메시지 관리를 수행하는 하나의 클래스인 [동시성::ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md)을 정의합니다. 클래스를 `ordered_message_processor` 사용하면 메시지 블록이 메시지를 받는 순서대로 처리할 수 있습니다.

메시지 블록이 소스 및 대상과 어떻게 관련되는지 더 잘 이해하려면 다음 예제를 고려하십시오. 이 예제에서는 [동시성::transformer](../../parallel/concrt/reference/transformer-class.md) 클래스의 선언을 보여 주며 있습니다.

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

클래스는 `transformer` 에서 `propagator_block`파생되므로 소스 블록과 대상 블록으로 모두 작동합니다. 형식의 `_Input` 메시지를 수락하고 형식의 `_Output`메시지를 보냅니다. 클래스는 `transformer` 모든 `single_link_registry` 대상 블록에 대한 링크 `multi_link_registry` 관리자와 모든 소스 블록의 링크 관리자로 지정합니다. 따라서 개체에는 `transformer` 최대 하나의 대상과 무제한의 소스를 가질 수 있습니다.

`source_block` 파생되는 클래스는 [propagate_to_any_targets, accept_message,](reference/source-block-class.md#propagate_to_any_targets) [reserve_message,](reference/source-block-class.md#reserve_message) [consume_message,](reference/source-block-class.md#consume_message) [release_message](reference/source-block-class.md#release_message)및 [resume_propagation](reference/source-block-class.md#resume_propagation)의 여섯 가지 메서드를 구현해야 합니다. [accept_message](reference/source-block-class.md#accept_message) 에서 `target_block` 파생 되는 [클래스는 propagate_message](reference/propagator-block-class.md#propagate_message) 메서드를 구현 해야 하 고 선택적으로 [send_message](reference/propagator-block-class.md#send_message) 메서드를 구현할 수 있습니다. 에서 `propagator_block` 파생되는 것은 기능적으로 둘 다에서 `source_block` `target_block`파생되는 것과 동일합니다.

메서드는 `propagate_to_any_targets` 런타임에 의해 호출되어 들어오는 메시지를 비동기적으로 또는 동기적으로 처리하고 나가는 메시지를 전파합니다. 메서드는 `accept_message` 메시지를 수락하기 위해 대상 블록에서 호출됩니다. 과 같은 `unbounded_buffer`많은 메시지 블록 유형은 메시지를 수신할 첫 번째 대상에게만 메시지를 보냅니다. 따라서 메시지의 소유권을 대상에 전송합니다. [동시성::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md)같은 다른 메시지 블록 유형은 각 대상 블록에 메시지를 제공합니다. 따라서 `overwrite_buffer` 각 대상에 대 한 메시지의 복사본을 만듭니다.

의 `reserve_message` `consume_message`에서 `release_message`및 `resume_propagation` 메서드는 메시지 블록이 메시지 예약에 참여할 수 있도록 합니다. 대상 블록은 `reserve_message` 메시지가 제공될 때 메서드를 호출하고 나중에 사용할 수 있도록 메시지를 예약해야 합니다. 대상 블록이 메시지를 예약한 후 해당 `consume_message` 메시지 또는 예약을 `release_message` 취소하는 메서드를 사용하도록 메서드를 호출할 수 있습니다. 메서드와 `accept_message` 마찬가지로 `consume_message` 구현은 메시지의 소유권을 이전하거나 메시지 복사본을 반환할 수 있습니다. 대상 블록이 예약된 메시지를 사용하거나 해제하면 런타임에서 메서드를 호출합니다. `resume_propagation` 일반적으로 이 메서드는 큐의 다음 메시지부터 시작하여 메시지 전파를 계속합니다.

런타임은 메서드를 `propagate_message` 호출하여 다른 블록에서 현재 블록으로 메시지를 비동기적으로 전송합니다. 메서드는 `send_message` `propagate_message`비동기가 아닌 동기식으로 메시지를 대상 블록으로 보낸다는 점을 제외하면 유사합니다. 기본 구현은 `send_message` 들어오는 모든 메시지를 거부합니다. 메시지가 대상 블록과 연결된 선택적 필터 함수를 전달하지 않는 경우 런타임은 이러한 메서드 중 하나를 호출하지 않습니다. 메시지 필터에 대한 자세한 내용은 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.

【[맨 위](#top)】

## <a name="defining-the-priority_buffer-class"></a><a name="class"></a>priority_buffer 클래스 정의

클래스는 `priority_buffer` 들어오는 메시지를 우선 순위별로 먼저 정렬한 다음 메시지가 수신되는 순서로 정렬하는 사용자 지정 메시지 블록 유형입니다. 클래스는 `priority_buffer` 메시지 큐를 보유하기 때문에 [클래스::unbounded_buffer](reference/unbounded-buffer-class.md) 클래스와 유사하며 소스 및 대상 메시지 블록역할을 하며 여러 원본과 여러 대상을 모두 가질 수 있기 때문입니다. 그러나 `unbounded_buffer` 메시지 전파는 소스에서 메시지를 받는 순서에만 기반합니다.

클래스는 `priority_buffer` std:: 포함 요소와 `Type` 요소를 `PriorityType` 포함하는[튜플의](../../standard-library/tuple-class.md) 메시지를 수신합니다. `PriorityType`는 각 메시지의 우선 순위를 보유하는 형식을 나타냅니다. `Type` 은 메시지의 데이터 부분을 나타냅니다. 클래스는 `priority_buffer` 형식의 `Type`메시지를 보냅니다. 클래스는 `priority_buffer` 또한 들어오는 메시지에 대한 [std::priority_queue](../../standard-library/priority-queue-class.md) 개체와 나가는 메시지에 대한 큐 개체:: std:: 나가는 메시지에 대한[큐](../../standard-library/queue-class.md) 개체의 두 개의 메시지 큐를 관리합니다. 우선 순위로 메시지 정렬은 `priority_buffer` 개체가 동시에 여러 메시지를 수신하거나 소비자가 메시지를 읽기 전에 여러 메시지를 수신할 때 유용합니다.

클래스에서 파생 되는 7 메서드 구현 `propagator_block` 해야 하는 `priority_buffer` 메서드 외에도 `link_target_notification` 클래스는 `send_message` 및 메서드를 재정의 합니다. `priority_buffer` 클래스는 또한 두 개의 공용 `enqueue` 도우미 `dequeue`메서드 및 및 개인 `propagate_priority_order`도우미 메서드를 정의합니다.

다음 절차에서 클래스를 구현하는 `priority_buffer` 방법을 설명합니다.

#### <a name="to-define-the-priority_buffer-class"></a>priority_buffer 클래스를 정의하려면

1. C ++ 헤더 파일을 만들고 `priority_buffer.h`이름을 지정합니다. 또는 프로젝트의 일부인 기존 헤더 파일을 사용할 수 있습니다.

1. 에서 `priority_buffer.h`다음 코드를 추가합니다.

    [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. 네임스페이스에서 [std::less](../../standard-library/less-struct.md) 및 [std:::greater](../../standard-library/greater-struct.md) 동시성에 따라 작동합니다:: 메시지 개체의 특수화를 정의합니다.[message](../../parallel/concrt/reference/message-class.md) `std`

    [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

   클래스는 `priority_buffer` `message` 개체에 `priority_queue` 개체를 저장합니다. 이러한 유형 전문화 는 우선 순위 큐가 우선 순위에 따라 메시지를 정렬 할 수 있도록합니다. 우선 순위는 `tuple` 개체의 첫 번째 요소입니다.

1. `concurrencyex` 네임스페이스에서 클래스를 `priority_buffer` 선언합니다.

    [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

   `priority_buffer` 클래스는 `propagator_block`에서 파생됩니다. 따라서 메시지를 보내고 받을 수 있습니다. 클래스에는 `priority_buffer` 형식의 `Type`메시지를 수신하는 여러 대상이 있을 수 있습니다. 또한 형식의 `tuple<PriorityType, Type>`메시지를 보내는 여러 소스를 가질 수도 있습니다.

1. `priority_buffer` 클래스의 `private` 섹션에서 다음 멤버 변수를 추가합니다.

    [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

   개체는 `priority_queue` 들어오는 메시지를 보유합니다. 개체는 `queue` 나가는 메시지를 보유합니다. 개체는 `priority_buffer` 여러 메시지를 동시에 수신할 수 있습니다. 개체는 `critical_section` 입력 메시지 큐에 대한 액세스를 동기화합니다.

1. `private` 섹션에서 복사 생성자와 할당 연산자를 정의합니다. 이렇게 하면 `priority_queue` 개체에 할당할 수 없습니다.

    [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. `public` 섹션에서 많은 메시지 블록 형식에 공통적인 생성자 정의합니다. 또한 소멸자 정의합니다.

    [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. 섹션에서 `public` 메서드 `enqueue` 및 `dequeue`을 정의합니다. 이러한 도우미 메서드는 `priority_buffer` 개체에서 메시지를 보내고 받는 다른 방법을 제공합니다.

    [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

1. `protected` 섹션에서 메서드를 정의합니다. `propagate_to_any_targets`

    [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

   메서드는 `propagate_to_any_targets` 입력 큐의 맨 앞에 있는 메시지를 출력 큐로 전송하고 출력 큐의 모든 메시지를 전파합니다.

1. `protected` 섹션에서 메서드를 정의합니다. `accept_message`

    [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

   대상 블록이 메서드를 `accept_message` 호출하면 클래스는 `priority_buffer` 메시지의 소유권을 허용하는 첫 번째 대상 블록으로 전송합니다. (이것은 `unbounded_buffer`.)

1. `protected` 섹션에서 메서드를 정의합니다. `reserve_message`

    [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

   클래스는 `priority_buffer` 제공된 메시지 식별자가 큐 앞에 있는 메시지의 식별자와 일치할 때 대상 블록이 메시지를 예약하도록 허용합니다. 즉, `priority_buffer` 개체가 아직 추가 메시지를 받지 못했고 현재 메시지를 전파하지 않은 경우 대상이 메시지를 예약할 수 있습니다.

1. `protected` 섹션에서 메서드를 정의합니다. `consume_message`

    [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

   대상 블록은 `consume_message` 예약한 메시지의 소유권을 전송하기 위해 호출됩니다.

1. `protected` 섹션에서 메서드를 정의합니다. `release_message`

    [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

   대상 블록은 `release_message` 메시지에 대한 예약을 취소하기 위해 호출합니다.

1. `protected` 섹션에서 메서드를 정의합니다. `resume_propagation`

    [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

   런타임은 `resume_propagation` 대상 블록이 예약된 메시지를 사용하거나 해제한 후에 호출됩니다. 이 메서드는 출력 큐에 있는 모든 메시지를 전파 합니다.

1. `protected` 섹션에서 메서드를 정의합니다. `link_target_notification`

    [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

   `_M_pReservedFor` 멤버 변수는 기본 클래스에 `source_block`의해 정의됩니다. 이 멤버 변수는 출력 큐 앞에 있는 메시지에 대한 예약을 보류하는 대상 블록(있는 경우)을 가리킵니다. 런타임은 `link_target_notification` 새 대상이 개체에 연결될 때 호출됩니다. `priority_buffer` 이 메서드는 예약을 보유 하는 대상이 없는 경우 출력 큐에 있는 모든 메시지를 전파 합니다.

1. `private` 섹션에서 메서드를 정의합니다. `propagate_priority_order`

    [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

   이 메서드는 출력 큐에서 모든 메시지를 전파 합니다. 큐의 모든 메시지는 대상 블록 중 하나가 메시지를 수락할 때까지 모든 대상 블록에 제공됩니다. 클래스는 `priority_buffer` 나가는 메시지의 순서를 유지합니다. 따라서 이 메서드가 대상 블록에 다른 메시지를 제공 하기 전에 출력 큐의 첫 번째 메시지를 대상 블록에 의해 허용 되어야 합니다.

1. `protected` 섹션에서 메서드를 정의합니다. `propagate_message`

    [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

   이 `propagate_message` 메서드를 `priority_buffer` 사용하면 클래스가 메시지 수신자 또는 대상 역할을 할 수 있습니다. 이 메서드는 제공된 소스 블록에서 제공하는 메시지를 수신하고 해당 메시지를 우선 순위 큐에 삽입합니다. 그런 `propagate_message` 다음 메서드는 비동기적으로 모든 출력 메시지를 대상 블록에 보냅니다.

   런타임은 [동시성::asend](reference/concurrency-namespace-functions.md#asend) 함수를 호출하거나 메시지 블록이 다른 메시지 블록에 연결된 경우 이 메서드를 호출합니다.

1. `protected` 섹션에서 메서드를 정의합니다. `send_message`

    [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

   메서드는 `send_message` 와 `propagate_message`유사합니다. 그러나 비동기 대신 출력 메시지를 동기로 보냅니다.

   런타임은 [동시성 ::send](reference/concurrency-namespace-functions.md#send) 함수를 호출할 때와 같이 동기 송신 작업 중에 이 메서드를 호출합니다.

클래스에는 `priority_buffer` 많은 메시지 블록 유형에서 일반적인 생성자 오버로드가 포함되어 있습니다. 일부 생성자 오버로드는 [동시성을 취합니다::스케줄러](../../parallel/concrt/reference/scheduler-class.md) 또는 [동시성::Schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체를 사용하면 특정 작업 스케줄러에서 메시지 블록을 관리할 수 있습니다. 다른 생성자 오버로드는 필터 함수를 수행합니다. 필터 기능을 사용하면 메시지 블록이 페이로드를 기준으로 메시지를 수락하거나 거부할 수 있습니다. 메시지 필터에 대한 자세한 내용은 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오. 작업 스케줄러에 대한 자세한 내용은 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)를 참조하십시오.

클래스는 `priority_buffer` 메시지를 우선 순위별로 정렬한 다음 메시지를 수신하는 순서로 정렬하기 때문에 이 클래스는 [동시성:::asend](reference/concurrency-namespace-functions.md#asend) 함수를 호출하거나 메시지 블록이 다른 메시지 블록에 연결된 경우와 같이 비동기적으로 메시지를 수신할 때 가장 유용합니다.

【[맨 위](#top)】

## <a name="the-complete-example"></a><a name="complete"></a>전체 예제

다음 예제에서는 클래스의 전체 `priority_buffer` 정의를 보여 주며 있습니다.

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

다음 예제는 개체에 대한 `asend` 여러 및 [동시성::receive](reference/concurrency-namespace-functions.md#receive) 작업을 동시에 수행합니다. `priority_buffer`

[!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]

이 예제에서는 다음 샘플 출력을 생성합니다.

```Output
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
```

클래스는 `priority_buffer` 우선 순위별로 메시지를 정렬한 다음 메시지를 받는 순서로 메시지를 정렬합니다. 이 예제에서는 숫자 우선 순위가 더 높은 메시지가 큐 의 앞쪽으로 삽입됩니다.

【[맨 위](#top)】

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트에 붙여넣거나 이름이 지정된 `priority_buffer` `priority_buffer.h` 파일과 명명된 파일에 클래스의 정의를 `priority_buffer.cpp` 붙여넣은 다음 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe/EHsc priority_buffer.cpp**

## <a name="see-also"></a>참고 항목

[동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 기능](../../parallel/concrt/message-passing-functions.md)
