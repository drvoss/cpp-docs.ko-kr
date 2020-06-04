---
title: CTreeCtrl vs. CTreeView
ms.date: 11/04/2016
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
ms.openlocfilehash: 7c78dfa9920c913fdbedb009c5a6f275a3e3e273
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445224"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl vs. CTreeView

MFC는 트리 컨트롤 [CTreeCtrl](../mfc/reference/ctreectrl-class.md) 및 [ctreeview](../mfc/reference/ctreeview-class.md)를 캡슐화 하는 두 개의 클래스를 제공 합니다. 각 클래스는 여러 상황에서 유용 합니다.

일반 자식 창 컨트롤이 필요한 경우 `CTreeCtrl`를 사용 합니다. 예를 들어 대화 상자에서 특히 일반적인 대화 상자와 같이 창에 다른 자식 컨트롤이 있는 경우 `CTreeCtrl`를 사용 하는 것이 좋습니다.

트리 컨트롤이 문서/뷰 아키텍처의 뷰 창과 트리 컨트롤 처럼 동작 하도록 하려면 `CTreeView`를 사용 합니다. `CTreeView`은 프레임 창 또는 분할자 창의 전체 클라이언트 영역을 차지 합니다. 부모 창의 크기를 조정 하면 자동으로 크기가 조정 되 고 메뉴, 액셀러레이터 키 및 도구 모음에서 명령 메시지를 처리할 수 있습니다. 트리 컨트롤에는 트리를 표시 하는 데 필요한 데이터가 포함 되어 있기 때문에 해당 문서 개체는 복잡할 필요는 없습니다. 문서 템플릿에서 [CDocument](../mfc/reference/cdocument-class.md) 를 문서 형식으로 사용할 수도 있습니다.

## <a name="see-also"></a>참고 항목

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
