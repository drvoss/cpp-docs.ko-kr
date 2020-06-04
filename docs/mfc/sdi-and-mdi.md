---
title: SDI 및 MDI
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
ms.openlocfilehash: 9730e7baf9589c4b05a60703c619aae2e941bdec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372765"
---
# <a name="sdi-and-mdi"></a>SDI 및 MDI

MFC를 사용하면 단일 문서 인터페이스(SDI) 및 MDI(다중 문서 인터페이스) 응용 프로그램에서 모두 쉽게 작업할 수 있습니다.

SDI 응용 프로그램은 한 번에 하나의 열린 문서 프레임 창만 허용합니다. MDI 응용 프로그램을 사용하면 응용 프로그램의 동일한 인스턴스에서 여러 문서 프레임 창을 열 수 있습니다. MDI 응용 프로그램에는 프레임 창 자체인 여러 MDI 자식 창을 열 수 있는 창이 있으며 각 응용 프로그램에는 별도의 문서가 들어 있습니다. 일부 응용 프로그램에서자식 창은 차트 창 및 스프레드시트 창과 같은 다른 유형일 수 있습니다. 이 경우 다른 유형의 MDI 자식 창이 활성화되면 메뉴 모음이 변경될 수 있습니다.

> [!NOTE]
> Windows 95 이상에서 운영 체제가 "문서 중심" 보기를 채택했기 때문에 응용 프로그램은 일반적으로 SDI입니다.

자세한 내용은 [문서, 보기 및 프레임워크 를](../mfc/documents-views-and-the-framework.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스를 사용하여 Windows 애플리케이션 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)
