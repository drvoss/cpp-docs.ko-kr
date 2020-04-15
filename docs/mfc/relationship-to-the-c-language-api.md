---
title: C 언어 API와의 관계
ms.date: 11/04/2016
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
ms.openlocfilehash: 1fbd4d332f5ade1cb9415448b138ac5bc838307d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372821"
---
# <a name="relationship-to-the-c-language-api"></a>C 언어 API와의 관계

Windows용 다른 클래스 라이브러리와 는 별도로 Microsoft Foundation 클래스(MFC) 라이브러리를 설정하는 단일 특성은 C 언어로 작성된 Windows API에 매우 근접한 매핑입니다. 또한 일반적으로 클래스 라이브러리에 대한 호출을 Windows API에 대한 직접 호출과 자유롭게 혼합할 수 있습니다. 그러나 이 직접 액세스는 클래스가 해당 API를 완전히 대체한다는 의미는 아닙니다. 개발자는 [SetCursor](/windows/win32/api/winuser/nf-winuser-setcursor) 및 [GetSystemMetrics와](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)같은 일부 Windows 함수를 직접 호출해야 합니다. Windows 함수는 클래스 멤버 함수에 의해 래핑됩니다.

네이티브 Windows 함수 호출을 수행해야 하는 경우가 있으므로 C 언어 Windows API 설명서에 액세스할 수 있어야 합니다. 이 설명서는 Microsoft 시각적 C++에 포함되어 있습니다.

> [!NOTE]
> MFC 라이브러리 프레임워크의 작동 방식에 대한 개요는 [클래스 를 사용하여 Windows용 응용 프로그램을 작성합니다.](../mfc/using-the-classes-to-write-applications-for-windows.md)

## <a name="see-also"></a>참고 항목

[일반 클래스 디자인 철학](../mfc/general-class-design-philosophy.md)
