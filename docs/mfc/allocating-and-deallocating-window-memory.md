---
title: 창 메모리 할당 및 할당 취소
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
ms.openlocfilehash: 02546559183d0e14973bc2e5ccb26a4570a39b1e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623259"
---
# <a name="allocating-and-deallocating-window-memory"></a>창 메모리 할당 및 할당 취소

C + + **delete** 연산자를 사용 하 여 프레임 창이 나 뷰를 제거 하지 마세요. 대신 `CWnd` 멤버 함수를 호출 `DestroyWindow` 합니다. 따라서 프레임 창은 **new**연산자를 사용 하 여 힙에 할당 되어야 합니다. 스택 프레임 또는 전역적으로 프레임 창을 할당할 때는 주의 해야 합니다. 가능한 경우 다른 창이 스택 프레임에 할당 되어야 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아야 할 내용

- [창 만들기](creating-windows.md)

- [창 소멸 시퀀스](window-destruction-sequence.md)

- [CWnd를 해당 HWND에서 분리](detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>참고 항목

[창 개체 소멸시키기](destroying-window-objects.md)
