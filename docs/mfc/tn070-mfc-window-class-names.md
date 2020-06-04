---
title: 'TN070: MFC 창 클래스 이름'
ms.date: 11/04/2016
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: ad43f5af5d2e90cb5fc2bc90f0909c2b495b4a4c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373492"
---
# <a name="tn070-mfc-window-class-names"></a>TN070: MFC 창 클래스 이름

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

MFC 창은 창의 기능을 반영하는 동적으로 생성된 클래스 이름을 사용합니다. MFC는 응용 프로그램에서 생성한 프레임 창, 보기 및 팝업 창에 대해 동적으로 클래스 이름을 생성합니다. MFC 응용 프로그램에서 생성되는 대화 상자 및 컨트롤에는 해당 창 클래스에 대한 Windows 제공 이름이 있습니다.

사용자 고유의 창 클래스를 등록하고 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)의 재정의에서 사용하여 동적으로 제공된 클래스 이름을 바꿀 수 있습니다. MFC에서 제공한 클래스 이름은 다음 두 가지 양식 중 하나에 맞습니다.

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

`%x` 문자를 대체하는 육하는 숫자는 [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) 구조의 데이터에서 채워져 있습니다. MFC는 이 기술을 사용하여 동일한 **WNDCLASS** 구조를 요구하는 여러 C++ 클래스가 등록된 동일한 창 클래스를 공유할 수 있도록 합니다. 대부분의 간단한 Win32 응용 프로그램과 달리 MFC 응용 프로그램에는 **WNDPROC가**하나뿐이므로 **WNDCLASS** 구조를 쉽게 공유하여 시간과 메모리를 절약할 수 있습니다. 위에 표시된 문자의 `%x` 대체 가능한 값은 다음과 같습니다.

- **WNDCLASS.h인스턴스**

- **WNDCLASS.스타일**

- **WNDCLASS.h커서**

- **WNDCLASS.hbr배경**

- **WNDCLASS.hicon**

첫 번째`Afx:%x:%x`양식 () 은 **hCursor,** **hbrBackground**및 **hIcon이** 모두 **NULL인**경우에 사용됩니다.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)<br/>
[TN020: ID 명명 및 번호 매기기 규칙](../mfc/tn020-id-naming-and-numbering-conventions.md)
