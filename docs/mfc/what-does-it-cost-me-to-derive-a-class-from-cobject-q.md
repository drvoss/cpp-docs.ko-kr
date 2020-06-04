---
title: CObject에서 클래스를 파생시키는 비용
ms.date: 11/04/2016
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
ms.openlocfilehash: 8f83bf9ee522487761aaa865a8315a174a47302d
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446046"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>CObject에서 클래스를 파생시키는 비용

[CObject](../mfc/reference/cobject-class.md) 클래스에서 파생 되는 오버 헤드는 최소화 됩니다. 파생 클래스는 네 개의 가상 함수와 단일 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 개체를 상속 합니다.

## <a name="see-also"></a>참고 항목

[CObject 클래스: 질문과 대답](../mfc/cobject-class-frequently-asked-questions.md)
