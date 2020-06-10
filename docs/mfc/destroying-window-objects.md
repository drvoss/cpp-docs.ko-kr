---
title: 창 개체 소멸시키기
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
ms.openlocfilehash: 22b483c1005931b229453ae229935c0e716ab726
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621858"
---
# <a name="destroying-window-objects"></a>창 개체 소멸시키기

사용자가 창에서 완료 되 면 c + + 창 개체를 삭제 하려면 자신의 자식 창에서 주의를 기울여야 합니다. 이러한 개체가 제거 되지 않으면 응용 프로그램에서 메모리를 복구 하지 않습니다. 다행히 프레임 워크는 프레임 창, 뷰 및 대화 상자에 대 한 생성 뿐만 아니라 창 소멸도 관리 합니다. 추가 창을 만드는 경우 제거 해야 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아야 할 내용

- [창 소멸 시퀀스](window-destruction-sequence.md)

- [창 메모리 할당 및 할당 취소](allocating-and-deallocating-window-memory.md)

- [CWnd를 해당 HWND에서 분리](detaching-a-cwnd-from-its-hwnd.md)

- [일반 창 만들기 시퀀스](general-window-creation-sequence.md)

- [프레임 창 제거](destroying-frame-windows.md)

## <a name="see-also"></a>참고 항목

[창 개체](window-objects.md)
