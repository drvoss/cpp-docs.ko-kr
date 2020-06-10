---
title: 헤더 컨트롤에서 항목 순서 지정
ms.date: 11/04/2016
f1_keywords:
- DS_DRAGDROP
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
ms.openlocfilehash: c4b4711729c6c3a4b63d4ad05252a5c49df98a0c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622129"
---
# <a name="ordering-items-in-the-header-control"></a>헤더 컨트롤에서 항목 순서 지정

[헤더 컨트롤에 항목을 추가한](adding-items-to-the-header-control.md)후에는 다음 함수를 사용 하 여 해당 주문에 대 한 정보를 조작 하거나 가져올 수 있습니다.

- [CHeaderCtrl:: getorderarray](reference/cheaderctrl-class.md#getorderarray) 및 [CHeaderCtrl:: setorderarray](reference/cheaderctrl-class.md#setorderarray)

   머리글 항목의 왼쪽에서 오른쪽 순서를 검색 하 고 설정 합니다.

- [CHeaderCtrl:: OrderToIndex](reference/cheaderctrl-class.md#ordertoindex)입니다.

   특정 헤더 항목에 대 한 인덱스 값을 검색 합니다.

이전 멤버 함수 외에도 HDS_DRAGDROP 스타일을 통해 사용자는 헤더 컨트롤 내에서 머리글 항목을 끌어서 놓을 수 있습니다. 자세한 내용은 [헤더 항목에 대 한 끌어서 놓기 지원 제공](providing-drag-and-drop-support-for-header-items.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[CHeaderCtrl 사용](using-cheaderctrl.md)
