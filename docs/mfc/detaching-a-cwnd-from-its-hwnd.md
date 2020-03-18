---
title: CWnd를 해당 HWND에서 분리
ms.date: 11/04/2016
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
ms.openlocfilehash: f7a6f97ba9f1dd3a928a5450c1a899ce09a4ac5f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446963"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>CWnd를 해당 HWND에서 분리

개체`HWND` 관계를 피하는 경우 MFC는 다른 `CWnd` 멤버 함수인 [Detach](../mfc/reference/cwnd-class.md#detach)를 제공 합니다 .이 함수는 Windows 창 C++ 에서 창 개체의 연결을 끊습니다. 이렇게 하면 개체가 소멸 될 때 소멸자가 Windows 창을 소멸 시킬 수 없습니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [창 만들기](../mfc/creating-windows.md)

- [창 소멸 시퀀스](../mfc/window-destruction-sequence.md)

- [창 메모리 할당 및 할당 취소](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>참고 항목

[창 개체](../mfc/window-objects.md)
