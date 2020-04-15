---
title: 동적 개체 만들기
ms.date: 03/27/2020
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: 40a17d3ed458d0634fd5bf27b54d0a36a65e35b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364804"
---
# <a name="dynamic-object-creation"></a>동적 개체 만들기

이 문서에서는 런타임에 동적으로 개체를 만드는 방법을 설명합니다. 이 프로시저는 런타임 클래스 정보 액세스 문서에서 설명하는 대로 [런타임 클래스 정보를](../mfc/accessing-run-time-class-information.md)사용합니다.

#### <a name="dynamically-create-an-object-given-its-run-time-class"></a>런타임 클래스가 지정된 개체를 동적으로 만듭니다.

1. 다음 코드를 사용하여 `CreateObject` `CRuntimeClass`의 함수를 사용하여 개체를 동적으로 만듭니다. 오류가 발생할 `CreateObject` 경우 예외를 발생시키는 대신 **NULL을** 반환합니다.

   [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>참고 항목

[Destroying Window Objects](tn017-destroying-window-objects.md)
[CObject를 사용하여](using-cobject.md) 창 개체 파괴
