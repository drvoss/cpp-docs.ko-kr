---
title: 스택 및 큐 컬렉션 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- MFC collection classes [MFC], stack collections
- collections, stack
- stack
- collection classes [MFC], creating
- queue collections
- MFC collection classes [MFC], queue collections
- stack collections
- collections, queue
ms.assetid: 3c7bc198-35f0-4fc3-aaed-6005a0f22638
ms.openlocfilehash: 5b3427f7bb2e46435ddf2768bcbb816f9d7e5c1a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371597"
---
# <a name="creating-stack-and-queue-collections"></a>스택 및 큐 컬렉션 만들기

이 문서에서는 MFC 목록 클래스에서 [스택](#_core_stacks) 및 큐와 같은 다른 데이터 구조를 만드는 방법에 대해 [설명합니다.](#_core_queues) 예제에서는 에서 `CList`파생된 클래스를 사용 `CList` 하지만 기능을 추가 해야 하는 경우가 아니면 직접 사용할 수 있습니다.

## <a name="stacks"></a><a name="_core_stacks"></a>스택

표준 목록 컬렉션에는 머리와 꼬리가 모두 있으므로 마지막 첫 번째 스택의 동작을 모방하는 파생 목록 컬렉션을 쉽게 만들 수 있습니다. 스택은 카페테리아에 있는 트레이 더미와 같습니다. 트레이가 스택에 추가되면 스택 의 맨 위로 이동합니다. 마지막으로 추가된 트레이는 제거할 첫 번째 용지함입니다. 목록 컬렉션 멤버는 `AddHead` `RemoveHead` 기능하며 목록의 헤드에서 특별히 요소를 추가하고 제거하는 데 사용할 수 있습니다. 따라서 가장 최근에 추가된 요소가 제거되는 첫 번째 요소입니다.

#### <a name="to-create-a-stack-collection"></a>스택 컬렉션을 만들려면

1. 기존 MFC 목록 클래스 중 하나에서 새 목록 클래스를 파생 하 고 스택 작업의 기능을 지원 하기 위해 더 많은 멤버 함수를 추가 합니다.

   다음 예제에서는 멤버 함수를 추가하여 요소를 스택에 푸시하고, 스택의 맨 위 요소를 엿보고, 스택에서 맨 위 요소를 팝하는 방법을 보여 주어집니다.

   [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_1.h)]

이 방법은 기본 `CObList` 클래스를 노출합니다. 사용자는 스택에 `CObList` 적합한지 여부에 관계없이 모든 멤버 함수를 호출할 수 있습니다.

## <a name="queues"></a><a name="_core_queues"></a> 큐

표준 목록 컬렉션에는 헤드와 테일이 모두 있으므로 첫 번째-첫 번째 대기열의 동작을 모방하는 파생 목록 컬렉션을 쉽게 만들 수도 있습니다. 대기열은 카페테리아에 있는 사람들의 줄과 같습니다. 첫 번째 줄이 제공되는 첫 번째 사람입니다. 더 많은 사람들이 와서, 그들은 자신의 차례를 기다리는 줄의 끝으로 이동합니다. 리스트 컬렉션 멤버는 `AddTail` `RemoveHead` 기능하며, 리스트의 머리 또는 꼬리에서 특별히 요소를 추가하고 제거하는 데 사용할 수 있습니다. 따라서 가장 최근에 추가된 요소는 항상 제거할 마지막 요소입니다.

#### <a name="to-create-a-queue-collection"></a>큐 컬렉션을 만들려면

1. Microsoft Foundation 클래스 라이브러리와 함께 제공되는 미리 정의된 목록 클래스 중 하나에서 새 목록 클래스를 파생하고 큐 작업의 의미 체계를 지원하기 위해 더 많은 멤버 함수를 추가합니다.

   다음 예제에서는 멤버 함수를 추가하여 큐 끝에 요소를 추가하고 큐 앞에서 요소를 가져옵니다.

   [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_2.h)]

## <a name="see-also"></a>참고 항목

[컬렉션](../mfc/collections.md)
