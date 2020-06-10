---
title: 트리 컨트롤과 통신
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: f480cdad2fce53f830b8067083a8a4be4b4e4848
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619656"
---
# <a name="communicating-with-a-tree-control"></a>트리 컨트롤과 통신

개체 생성 방법에 따라 [CTreeCtrl](reference/ctreectrl-class.md) 개체에서 멤버 함수를 호출 하는 데 다른 메서드를 사용 합니다.

- 트리 컨트롤이 대화 상자에 있는 경우 `CTreeCtrl` 대화 상자 클래스에서 만든 형식의 멤버 변수를 사용 합니다.

- 트리 컨트롤이 자식 창인 경우 `CTreeCtrl` 개체를 생성 하는 데 사용한 개체 (또는 포인터)를 사용 합니다.

- 개체를 사용 하는 경우 `CTreeView` [ctreeview:: GetTreeCtrl](reference/ctreeview-class.md#gettreectrl) 함수를 사용 하 여 트리 컨트롤에 대 한 참조를 가져옵니다. 이 값을 사용 하 여 다른 참조를 초기화 하거나 참조 주소를 포인터에 할당할 수 있습니다 `CTreeCtrl` .

## <a name="see-also"></a>참고 항목

[CTreeCtrl 사용](using-ctreectrl.md)<br/>
[컨트롤](controls-mfc.md)
