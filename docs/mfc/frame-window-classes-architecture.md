---
title: 프레임 창 클래스(아키텍처)
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: e3ae432c1adc881a5c67d6a6c292dc1f6a583ab3
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441260"
---
# <a name="frame-window-classes-architecture"></a>프레임 창 클래스(아키텍처)

문서/뷰 아키텍처에서 프레임 창은 보기 창이 포함 된 창입니다. 컨트롤 막대를 연결 하는 것도 지원 합니다.

MDI (다중 문서 인터페이스) 응용 프로그램에서는 주 창이 `CMDIFrameWnd`에서 파생 됩니다. 개체 `CMDIChildWnd` 되는 문서 프레임을 간접적으로 포함 합니다. `CMDIChildWnd` 개체는 문서의 뷰를 포함 합니다.

SDI (단일 문서 인터페이스) 응용 프로그램에서 `CFrameWnd`파생 된 주 창에는 현재 문서 뷰가 포함 되어 있습니다.

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
SDI 응용 프로그램의 주 프레임 창에 대 한 기본 클래스입니다. 또한 다른 모든 프레임 창 클래스에 대 한 기본 클래스입니다.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
MDI 응용 프로그램의 주 프레임 창에 대 한 기본 클래스입니다.

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
MDI 응용 프로그램의 문서 프레임 창에 대 한 기본 클래스입니다.

[클래스에서 파생하는 대신](../mfc/reference/coleipframewnd-class.md)<br/>
서버 문서를 편집 하는 동안 보기에 대 한 프레임 창을 제공 합니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../mfc/class-library-overview.md)
