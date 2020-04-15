---
title: 문서 및 뷰 정리
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 06ff60a2cf6245f64e80d899c13a8444558fcf0b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374616"
---
# <a name="cleaning-up-documents-and-views"></a>문서 및 뷰 정리

문서가 닫히면 프레임워크는 먼저 [DeleteContents 멤버 함수를 호출합니다.](../mfc/reference/cdocument-class.md#deletecontents) 문서 작업 중 힙에서 메모리를 할당한 경우 메모리를 할당 해제하기에 가장 좋은 위치는 `DeleteContents`입니다.

> [!NOTE]
> 문서의 소멸자에서는 문서 데이터를 할당 해제하지 않아야 합니다. SDI 애플리케이션의 경우 문서 개체를 다시 사용할 수 있습니다.

힙에 할당한 메모리를 할당 해제하도록 뷰의 소멸자를 재정의할 수 있습니다.

## <a name="see-also"></a>참고 항목

[문서 및 뷰 초기화 및 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)
