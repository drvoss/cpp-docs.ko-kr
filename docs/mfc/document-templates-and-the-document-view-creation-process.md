---
title: 문서 템플릿 및 문서-뷰 만들기 프로세스
ms.date: 11/19/2018
helpviewer_keywords:
- icons, for multiple document templates
- document templates [MFC], and views
- document/view architecture [MFC], creating document/view
- single document template
- MFC, document templates
- multiple document template
- CDocTemplate class [MFC]
- templates [MFC], document templates
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
ms.openlocfilehash: 79d24ef4b6687bce61295a92cdb90f4ce4a0d619
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389611"
---
# <a name="document-templates-and-the-documentview-creation-process"></a>문서 템플릿 및 문서/뷰 만들기 프로세스

연관된 뷰, 프레임워크 창이 있는 문서를 만드는 복잡한 프로세스를 관리하기 위해 프레임워크는 SDI 응용 프로그램을 위한 [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md)과 MDI 응용 프로그램을 위한 [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)이라는 두 가지 문서 템플릿 클래스를 사용합니다. `CSingleDocTemplate`는 한 번에 한 가지 형식의 한 문서를 만들고 저장할 수 있습니다. `CMultiDocTemplate`은 한가지 형식의 열려 있는 많은 문서 목록을 유지합니다.

일부 응용 프로그램은 여러 문서 형식을 지원합니다. 예를 들어, 응용 프로그램은 텍스트 문서 및 그래픽 문서를 지원할 수 있습니다. 이러한 응용 프로그램에서 사용자가 파일 메뉴에서 새로 만들기 명령을 선택하면 대화 상자에는 열 수 있는 새 문서 형식 목록이 표시됩니다. 지원되는 각 문서 형식에 대해 응용 프로그램은 고유한 문서 템플릿 개체를 사용합니다. 다음 그림은 두 가지 문서 형식을 지원하고 여러 열린 문서를 보여주는 MDI 응용 프로그램의 구성을 보여줍니다.

![두 가지 문서 형식이 포함 된 MDI 응용 프로그램](../mfc/media/vc387h1.gif "2 가지 문서 형식이 있는 MDI 응용 프로그램") <br/>
두 문서 형식을 사용하는 MDI 애플리케이션

문서 템플릿은 응용 프로그램 개체에서 생성 및 관리됩니다. 응용 프로그램의 `InitInstance` 함수가 수행하는 주요 작업 중 하나는 적절한 종류의 문서 템플릿을 하나 이상 생성하는 것 입니다. 이 기능은 [문서 템플릿 만들기](../mfc/document-template-creation.md)에 설명되어 있습니다. 응용 프로그램 개체는 템플릿 목록에 각 문서 템플릿에 대한 포인터를 저장하고 문서 템플릿을 추가하는 인터페이스를 제공합니다.

두 개 이상의 문서 형식을 지원해야 하는 경우 각 문서 형식마다 [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate)에 대한 추가 호출 작업이 더 필요합니다.

응용 프로그램의 문서 템플릿의 목록에서의 위치에 따라 각 문서 템플릿에 아이콘이 등록됩니다. 문서 템플릿의 순서는 `AddDocTemplate`을 호출하여 추가된 순서에 따라 결정됩니다. MFC는 응용 프로그램의 첫 번째 아이콘 리소스가 응용 프로그램 아이콘이고, 다음 아이콘 리소스는 첫 번째 문서 아이콘이라고 가정합니다.

예를 들어, 문서 템플릿은 응용 프로그램에 대한 세 가지 중 세 번째입니다. 인덱스 3에 응용 프로그램의 아이콘 리소스가 있는 경우 이 아이콘은 문서 템플릿에 대해 사용됩니다. 그렇지 않은 경우 인덱스 0에 있는 아이콘을 기본으로 사용합니다.

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)<br/>
[문서 템플릿 만들기](../mfc/document-template-creation.md)<br/>
[문서/뷰 만들기](../mfc/document-view-creation.md)<br/>
[MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)<br/>
[새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)
