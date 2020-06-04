---
title: 이미지 목록 사용
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
ms.openlocfilehash: 0d9566739a15e5d216eb052a7265313850515648
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366569"
---
# <a name="using-an-image-list"></a>이미지 목록 사용

이미지 목록의 일반적인 사용은 아래 패턴을 따릅니다.

- [CImageList](../mfc/reference/cimagelist-class.md) 개체를 구성 하고 [이미지](../mfc/reference/cimagelist-class.md#create) 목록을 만들고 `CImageList` 개체에 연결 하는 만들기 함수의 오버 로드 중 하나를 호출 합니다.

- 이미지 목록을 만들 때 이미지를 추가하지 않은 경우 멤버 [추가](../mfc/reference/cimagelist-class.md#add) 또는 [읽기](../mfc/reference/cimagelist-class.md#read) 함수를 호출하여 이미지 목록에 이미지를 추가합니다.

- 해당 컨트롤의 적절한 멤버 함수를 호출하여 이미지 목록을 컨트롤과 연결하거나 이미지 목록의 [멤버 그리기](../mfc/reference/cimagelist-class.md#draw) 기능을 사용하여 이미지 목록에서 직접 이미지를 그립니다.

- 아마도 사용자가 드래그에 대한 이미지 목록의 기본 제공 지원을 사용하여 이미지를 드래그 할 수 있습니다.

> [!NOTE]
> **새** 연산자로 이미지 목록을 만든 경우 개체를 완료할 때 개체를 삭제해야 `CImageList` 합니다.

## <a name="see-also"></a>참고 항목

[CImageList 사용](../mfc/using-cimagelist.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
