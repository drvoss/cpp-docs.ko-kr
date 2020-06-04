---
title: 인쇄
ms.date: 11/04/2016
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
ms.openlocfilehash: a46096592c9983d04d2122bfabb56ece9346c4bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371201"
---
# <a name="printing"></a>인쇄

Microsoft Windows는 장치 독립적인 디스플레이를 구현합니다. MFC에서 이는 뷰 클래스의 `OnDraw` 멤버 함수에서 동일한 그리기 호출이 디스플레이 및 프린터와 같은 다른 장치에 그리는 작업을 담당한다는 것을 의미합니다. 인쇄 미리 보기의 경우 대상 장치는 디스플레이에 대한 시뮬레이션된 프린터 출력입니다.

## <a name="your-role-in-printing-vs-the-frameworks-role"></a><a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a>인쇄에서 프레임워크의 역할과 관련하여의 역할

뷰 클래스에는 다음과 같은 책임이 있습니다.

- 문서에 있는 페이지 수를 프레임워크에 알립니다.

- 지정된 페이지를 인쇄하라는 메시지가 지정되면 문서의 해당 부분을 그립니다.

- 인쇄에 필요한 글꼴 또는 기타 GDI(그래픽 장치 인터페이스) 리소스를 할당하고 할당할 수 있습니다.

- 필요한 경우 지정된 페이지를 인쇄하기 전에 프린터 모드를 변경하는 데 필요한 이스케이프 코드를 보내면 페이지별로 인쇄 방향을 변경합니다.

프레임워크의 책임은 다음과 같습니다.

- **인쇄** 대화 상자를 표시합니다.

- 프린터에 대한 [CDC](../mfc/reference/cdc-class.md) 개체를 만듭니다.

- 개체의 [StartDoc](../mfc/reference/cdc-class.md#startdoc) 및 [EndDoc](../mfc/reference/cdc-class.md#enddoc) 멤버 `CDC` 함수를 호출합니다.

- 개체의 [StartPage](../mfc/reference/cdc-class.md#startpage) 멤버 함수를 `CDC` 반복적으로 호출하고, 인쇄할 페이지를 View 클래스에 알리고, 개체의 [EndPage](../mfc/reference/cdc-class.md#endpage) 멤버 함수를 `CDC` 호출합니다.

- 적절한 시간에 뷰에서 재정의 가능한 함수를 호출합니다.

다음 문서에서는 프레임워크가 인쇄 및 인쇄 미리 보기를 지원하는 방법에 대해 설명합니다.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [기본 인쇄 수행 방법](../mfc/how-default-printing-is-done.md)

- [다중 페이지 문서](../mfc/multipage-documents.md)

- [헤더 및 바닥글](../mfc/headers-and-footers.md)

- [인쇄를 위한 GDI 리소스 할당](../mfc/allocating-gdi-resources.md)

- [인쇄 미리 보기](../mfc/print-preview-architecture.md)

## <a name="see-also"></a>참고 항목

[인쇄 및 인쇄 미리 보기](../mfc/printing-and-print-preview.md)
