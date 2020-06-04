---
title: MFC의 MAPI 지원
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
ms.openlocfilehash: 3024f744407cf33c8dfad8a6f7af736e0f8061ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356996"
---
# <a name="mapi-support-in-mfc"></a>MFC의 MAPI 지원

MFC는 클래스에서 `CDocument`Microsoft 메시징 응용 프로그램 인터페이스(MAPI)의 하위 집합에 대한 지원을 제공합니다. `CDocument` 특히 최종 사용자의 컴퓨터에 메일 지원이 있는지 여부를 결정하는 멤버 함수가 있으며, 이 경우 표준 명령 ID가 ID_FILE_SEND_MAIL Mail 보내기 명령을 사용하도록 설정합니다. 이 명령에 대한 MFC 처리기 기능을 사용하면 전자 메일을 통해 문서를 보낼 수 있습니다.

> [!TIP]
> MFC는 전체 MAPI 함수 집합을 캡슐화하지는 않지만 MFC 프로그램에서 직접 Win32 API 함수를 호출할 수 있는 것처럼 MAPI 함수를 직접 호출할 수 있습니다.

응용 프로그램에서 메일 보내기 명령을 제공하는 것은 매우 쉽습니다. MFC는 문서(즉, 파생된 개체)를 `CDocument`첨부 파일로 패키징하고 메일로 보내는 구현을 제공합니다. 이 첨부 파일은 문서의 내용을 메일 메시지에 저장(직렬화)하는 파일 저장 명령과 동일합니다. 이 구현은 사용자의 컴퓨터에 있는 메일 클라이언트를 호출하여 사용자에게 메일을 처리하고 메일 메시지에 제목 및 메시지 텍스트를 추가할 수 있는 기회를 제공합니다. 사용자는 익숙한 메일 응용 프로그램의 사용자 인터페이스를 볼 수 있습니다. 이 기능은 두 `CDocument` 멤버 `OnFileSendMail` 함수및. `OnUpdateFileSendMail`

MAPI는 첨부 파일을 보내려면 파일을 읽어야합니다. 응용 프로그램이 `OnFileSendMail` 함수 호출 중에 데이터 파일을 열어 두면 여러 프로세스가 파일에 액세스할 수 있는 공유 모드로 파일을 열어야 합니다.

> [!NOTE]
> 클래스에 `OnFileSendMail` `COleDocument` 대한 재정의 버전은 복합 문서를 올바르게 처리합니다.

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>MFC를 사용하여 메일 보내기 명령을 구현하려면

1. Visual C++ 메뉴 편집기를 사용하여 명령 ID가 ID_FILE_SEND_MAIL 메뉴 항목을 추가합니다.

   이 명령 ID는 AFXRES의 프레임워크에서 제공합니다. H. 명령은 모든 메뉴에 추가할 수 있지만 일반적으로 **파일** 메뉴에 추가됩니다.

1. 문서의 메시지 맵에 다음을 수동으로 추가합니다.

   [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  이 메시지 맵은 메시지 맵이 `CDocument` `COleDocument` 파생 문서 클래스에 있더라도 두 경우 모두 올바른 기본 클래스를 선택하거나 파생된 문서에서 파생된 문서에 대해 작동합니다.

1. 응용 프로그램을 빌드합니다.

메일 지원을 사용할 수 있는 경우 MFC는 메뉴 항목을 에서 `OnUpdateFileSendMail` 활성화하고 이후에 을 사용하여 `OnFileSendMail`명령을 처리합니다. 메일 지원을 사용할 수 없는 경우 MFC는 메뉴 항목을 자동으로 제거하여 사용자가 볼 수 없도록 합니다.

> [!TIP]
> 앞서 설명한 대로 메시지 맵 항목을 수동으로 추가하는 대신 [클래스 클래스 마법사를](reference/mfc-class-wizard.md) 사용하여 메시지를 함수에 매핑할 수 있습니다. 자세한 내용은 [메시지 메시지를 함수에 매핑을](../mfc/reference/mapping-messages-to-functions.md)참조하십시오.

관련 정보는 [MAPI](../mfc/mapi.md) 개요를 참조하십시오.

MAPI를 `CDocument` 사용하도록 설정하는 멤버 함수에 대한 자세한 내용은 다음을 참조하십시오.

- [C문서::온파일센드메일](../mfc/reference/cdocument-class.md#onfilesendmail)

- [C문서::온업데이트파일센드메일](../mfc/reference/cdocument-class.md#onupdatefilesendmail)

- [콜레문서::온파일센드메일](../mfc/reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>참고 항목

[MAPI](../mfc/mapi.md)
