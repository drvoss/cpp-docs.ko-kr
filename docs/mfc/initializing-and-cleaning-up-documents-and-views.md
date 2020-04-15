---
title: 문서 및 뷰 초기화 및 정리
ms.date: 11/04/2016
helpviewer_keywords:
- initializing documents [MFC]
- views [MFC], cleaning up
- documents [MFC], initializing
- documents [MFC], cleaning up
- views [MFC], initializing
- initializing objects [MFC], document objects
- document objects [MFC], life cycle of
- initializing views [MFC]
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
ms.openlocfilehash: 3c92d60941cd6542bd0d6c27e8a879dc85e3a3d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377212"
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>문서 및 뷰 초기화 및 정리

문서 및 뷰 를 초기화하고 정리하려면 다음 지침을 사용합니다.

- MFC 프레임워크는 문서및 뷰를 초기화합니다. 추가한 모든 데이터를 초기화할 수 있습니다.

- 프레임워크는 문서및 뷰가 닫히면 정리됩니다. 해당 문서 및 뷰의 멤버 함수 내에서 힙에 할당된 메모리를 할당 할당 해야 합니다.

> [!NOTE]
> 전체 응용 프로그램에 대한 초기화는 클래스의 `CWinApp` [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 멤버 함수의 재정의에서 수행하는 것이 가장 우수하며 전체 응용 `CWinApp` 프로그램에 대한 정리는 멤버 함수 [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance).

MDI 응용 프로그램에서 문서(및 해당 프레임 창 및 보기 또는 보기)의 수명 주기는 다음과 같습니다.

1. 동적 생성 중에 문서 생성자가 호출됩니다.

1. 각 새 문서에 대해 문서의 [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) 또는 [OnOpenDocument가](../mfc/reference/cdocument-class.md#onopendocument) 호출됩니다.

1. 사용자는 수명 동안 문서와 상호 작용합니다. 일반적으로 이 문제는 사용자가 뷰를 통해 문서 데이터에서 작업하고 데이터를 선택하고 편집할 때 발생합니다. 뷰는 다른 뷰를 저장하고 업데이트하기 위해 문서에 변경 내용을 전달합니다. 이 시간 동안 문서와 뷰 모두 명령을 처리할 수 있습니다.

1. 프레임워크는 [DeleteContents를](../mfc/reference/cdocument-class.md#deletecontents) 호출하여 문서와 관련된 데이터를 삭제합니다.

1. 문서의 소멸자가 호출됩니다.

SDI 응용 프로그램에서 1단계는 문서를 처음 만들 때 한 번 수행됩니다. 그런 다음 새 문서를 열 때마다 2~4단계가 반복적으로 수행됩니다. 새 문서는 기존 문서 개체를 다시 사용합니다. 마지막으로 응용 프로그램이 종료되면 5단계가 수행됩니다.

## <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [문서 및 뷰 초기화](../mfc/initializing-documents-and-views.md)

- [문서 및 뷰 정리](../mfc/cleaning-up-documents-and-views.md)

## <a name="see-also"></a>참고 항목

[문서/아키텍처 보기](../mfc/document-view-architecture.md)
