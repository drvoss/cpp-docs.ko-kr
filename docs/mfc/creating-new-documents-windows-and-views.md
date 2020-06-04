---
title: 새 문서, 창 및 뷰 만들기
ms.date: 11/19/2018
helpviewer_keywords:
- MDI [MFC], creating windows
- window objects [MFC], creating
- objects [MFC], creating document objects
- MFC default objects
- frame windows [MFC], creating
- windows [MFC], MDI
- MFC, documents
- view objects [MFC], creating
- windows [MFC], creating
- overriding, default view behavior
- views [MFC], initializing
- customizing MFC default objects
- MFC, frame windows
- MFC, views
- MDI [MFC], frame windows
- child windows [MFC], creating MDI
- view objects [MFC]
- document objects [MFC], creating
- MFC default objects [MFC], customizing
- views [MFC], overriding default behavior
- initializing views [MFC]
ms.assetid: 88aa1f5f-2078-4603-b16b-a2b4c7b4a2a3
ms.openlocfilehash: aa1c58b02df92d79ca9915032b97fb5c0e2eaffc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371672"
---
# <a name="creating-new-documents-windows-and-views"></a>새 문서, 창 및 뷰 만들기

다음 그림에서는 문서, 뷰 및 프레임 창에 대한 작성 프로세스에 대한 개요를 제공합니다. 참여 개체에 중점을 둔 다른 문서에서는 자세한 내용을 제공합니다.

이 프로세스가 완료되면 협력 개체가 존재하고 서로 포인터를 저장합니다. 다음 그림은 객체가 생성되는 순서를 보여 준다. 그림에서 그림으로 순서를 따를 수 있습니다.

![문서 만들기 시퀀스](../mfc/media/vc387l1.gif "문서 만들기 시퀀스") <br/>
문서를 만드는 순서

![프레임 창 만들기 시퀀스](../mfc/media/vc387l2.png "프레임 창 만들기 시퀀스") <br/>
프레임 창을 만드는 순서

![뷰 만들기 시퀀스](../mfc/media/vc387l3.gif "뷰 만들기 시퀀스") <br/>
뷰를 만드는 순서

프레임워크가 새 문서, 보기 및 프레임 창 개체를 초기화하는 방법에 대한 자세한 내용은 MFC 라이브러리 참조에서 [CDocument,](../mfc/reference/cdocument-class.md) [CView,](../mfc/reference/cview-class.md) [CFrameWnd,](../mfc/reference/cframewnd-class.md) [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)및 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) 클래스를 참조하십시오. 또한 **파일** 메뉴에서 **새** 항목 및 **열기** 항목에 대한 프레임워크의 표준 명령에 대한 설명에서 작성 및 초기화 프로세스를 자세히 설명하는 [기술 참고 22를](../mfc/tn022-standard-commands-implementation.md)참조하십시오.

## <a name="initializing-your-own-additions-to-these-classes"></a><a name="_core_initializing_your_own_additions_to_these_classes"></a>이러한 클래스에 대한 사용자 고유의 추가 초기화

앞의 그림에서는 멤버 함수를 재정의하여 응용 프로그램의 개체를 초기화할 수 있는 점을 제안합니다. 뷰 클래스에서 `OnInitialUpdate` 재정의하면 뷰를 초기화하는 가장 좋은 위치에 있습니다. `OnInitialUpdate` 프레임 창을 만들고 프레임 창 내의 뷰가 문서에 첨부된 직후에 호출이 발생합니다. 예를 들어 뷰가 스크롤 뷰인 경우(대신 `CScrollView` `CView`파생됨) `OnInitialUpdate` 재정의의 문서 크기에 따라 뷰 크기를 설정해야 합니다. (이 프로세스는 [클래스 CScrollView에](../mfc/reference/cscrollview-class.md)대한 설명에 설명되어 있습니다.) 멤버 함수를 `CDocument` `OnNewDocument` 재정의하고 `OnOpenDocument` 문서의 응용 프로그램별 초기화를 제공할 수 있습니다. 일반적으로 두 가지 방법으로 문서를 만들 수 있으므로 둘 다 재정의해야 합니다.

대부분의 경우 재정의는 기본 클래스 버전을 호출해야 합니다. 자세한 내용은 MFC 라이브러리 참조에서 [클래스 CDocument,](../mfc/reference/cdocument-class.md) [CView,](../mfc/reference/cview-class.md) [CFrameWnd](../mfc/reference/cframewnd-class.md)및 [CWinApp의](../mfc/reference/cwinapp-class.md) 명명된 멤버 함수를 참조하십시오.

## <a name="see-also"></a>참고 항목

[문서 템플릿 및 문서/뷰 작성 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[문서 템플릿 만들기](../mfc/document-template-creation.md)<br/>
[문서/뷰 만들기](../mfc/document-view-creation.md)<br/>
[MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)
