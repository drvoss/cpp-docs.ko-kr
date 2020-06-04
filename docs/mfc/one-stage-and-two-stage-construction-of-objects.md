---
title: 1단계 및 2단계 개체 생성
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: 8f221ac6b63a06c65f932a695dfbf7b93ae7ac96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375975"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>1단계 및 2단계 개체 생성

펜및 브러시와 같은 그래픽 개체를 만드는 두 가지 기술 중에서 선택할 수 있습니다.

- *1단계 구성*: 생성자와 함께 한 단계에서 개체를 생성하고 초기화합니다.

- *2단계 구성*: 두 단계로 객체를 구성하고 초기화합니다. 생성자는 개체를 만들고 초기화 함수는 이를 초기화합니다.

2단계 구조는 항상 안전합니다. 1단계 구성에서 생성자는 잘못된 인수를 제공하거나 메모리 할당이 실패하는 경우 예외를 throw할 수 있습니다. 이 문제는 2단계 시공으로 피할 수 있지만 실패여부를 확인해야 합니다. 두 경우 모두 개체를 파괴하는 것은 동일한 프로세스입니다.

> [!NOTE]
> 이러한 기술은 그래픽 개체뿐만 아니라 모든 개체를 만드는 데 적용됩니다.

## <a name="example-of-both-construction-techniques"></a>두 건설 기술의 예

다음 간단한 예제에서는 펜 개체를 구성하는 두 가지 방법을 모두 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주실 수 있습니다.

[!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [그래픽 객체](../mfc/graphic-objects.md)

- [장치 컨텍스트로 그래픽 개체 선택](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [장치 컨텍스트](../mfc/device-contexts.md)

- [뷰에 그리기](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>참고 항목

[그래픽 개체](../mfc/graphic-objects.md)
