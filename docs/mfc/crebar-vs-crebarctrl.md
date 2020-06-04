---
title: CReBar와 CReBarCtrl 비교
ms.date: 11/04/2016
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
ms.openlocfilehash: 94f889be453a17a55357a260bd2a0c07037f6ded
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445277"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar와 CReBarCtrl 비교

MFC에서는 [CReBar](../mfc/reference/crebar-class.md) 및 [cre바 ctrl](../mfc/reference/crebarctrl-class.md) (Windows 공용 컨트롤 API를 래핑하는)를 만드는 두 가지 클래스를 제공 합니다. `CReBar`은 rebar 공용 컨트롤의 모든 기능을 제공 하 고 필요한 일반적인 컨트롤 설정 및 구조체의 대부분을 처리 합니다.

`CReBarCtrl`은 Win32 rebar 컨트롤에 대 한 래퍼 클래스 이므로, rebar를 MFC 아키텍처에 통합 하지 않으려는 경우 더 쉽게 구현할 수 있습니다. `CReBarCtrl`를 사용 하 고 rebar를 MFC 아키텍처에 통합 하려는 경우에는 크기 조정 막대 컨트롤 조작을 MFC에 전달 하기 위해 추가 주의가 필요 합니다. 이 통신은 어렵지 않습니다. 그러나 `CReBar`를 사용 하는 경우에는 불필요 한 추가 작업이 있습니다.

시각적 C++ 개체는 rebar 공용 컨트롤을 활용 하는 두 가지 방법을 제공 합니다.

- `CReBar`를 사용 하 여 rebar를 만든 다음 [CReBar:: GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) 을 호출 하 여 `CReBarCtrl` 멤버 함수에 대 한 액세스를 가져옵니다.

    > [!NOTE]
    >  `CReBar::GetReBarCtrl`는 rebar 개체의 **this** 포인터를 캐스팅 하는 인라인 멤버 함수입니다. 이는 런타임에 함수 호출에 오버 헤드가 없음을 의미 합니다.

- [Cre바 ctrl](../mfc/reference/crebarctrl-class.md)의 생성자를 사용 하 여 rebar를 만듭니다.

두 메서드 모두 rebar 컨트롤의 멤버 함수에 대 한 액세스를 제공 합니다. `CReBar::GetReBarCtrl`를 호출 하는 경우 멤버 함수 집합을 사용할 수 있도록 `CReBarCtrl` 개체에 대 한 참조를 반환 합니다. `CReBar`를 사용 하 여 rebar를 생성 하 고 만드는 방법에 대 한 자세한 내용은 [CReBar](../mfc/reference/crebar-class.md) 를 참조 하세요.

## <a name="see-also"></a>참고 항목

[CReBarCtrl 사용](../mfc/using-crebarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
