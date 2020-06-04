---
title: 표준 명령 및 창 ID
ms.date: 11/04/2016
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
ms.openlocfilehash: a7f9e37702c686e13379d4034be94949f92e5e79
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372952"
---
# <a name="standard-command-and-window-ids"></a>표준 명령 및 창 ID

Microsoft Foundation Class 라이브러리는 Afxres.h의 여러 표준 명령 및 창 ID를 정의합니다. 이러한 아이디는 리소스 편집기 및 [클래스 마법사](mfc-class-wizard.md) 내에서 메시지를 처리기 함수에 매핑하는 데 가장 일반적으로 사용됩니다. 모든 표준 명령에는 **ID_** 접두사가 있습니다. 예를 들어 메뉴 편집기를 사용하는 경우 일반적으로 파일 열기 메뉴 항목을 표준 ID_FILE_OPEN 명령 ID에 바인딩합니다.

대부분의 표준 명령의 경우 프레임워크 자체가 기본`CWinThread`프레임워크 클래스(, " `CWinApp` `CView` `CDocument`등)의 메시지 맵을 통해 명령을 처리하기 때문에 응용 프로그램 코드는 명령 ID를 참조할 필요가 없습니다.

표준 명령 번호 외에도 **AFX_ID**접두사가 있는 여러 다른 표준 ID가 정의됩니다. 이러한 아이디에는 표준 창 AFX_IDW_(접두사 **AFX_IDW_),** 문자열 AFX_IDW_(접두사 **AFX_IDS_)** 및 기타 여러 유형이 포함됩니다.

**AFX_ID** 접두사로 시작하는 아이디는 프로그래머가 거의 사용하지 않지만 **AFX_ID**s를 참조하는 프레임워크 함수를 재정의할 때 이러한 아이디를 참조해야 할 수 있습니다.

ID는 이 참조 설명서에서 개별적으로 설명하지 않습니다. 자세한 내용은 기술 노트 [20,](../../mfc/tn020-id-naming-and-numbering-conventions.md) [21](../../mfc/tn021-command-and-message-routing.md)및 [22에서](../../mfc/tn022-standard-commands-implementation.md)확인할 수 있습니다.

> [!NOTE]
> 헤더 파일 Afxres.h는 Afxwin.h에 간접적으로 포함됩니다. 애플리케이션의 리소스 스크립트(.rc) 파일에 다음 문을 명시적으로 포함해야 합니다.

[!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
