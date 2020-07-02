---
title: MFC 개체 간 관계
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
ms.openlocfilehash: d7e40e25b405d3f8ec50a518889cc2b89bc8c725
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372816"
---
# <a name="relationships-among-mfc-objects"></a>MFC 개체 간 관계

문서/뷰 작성 프로세스를 큐브 뷰에 배치하려면 실행 중인 프로그램( 문서, 뷰포함에 사용된 프레임 창 및 문서와 연관된 보기)을 고려합니다.

- 문서는 해당 문서의 뷰 목록과 문서를 만든 문서 템플릿에 대한 포인터를 유지합니다.

- 뷰는 해당 문서에 대한 포인터를 유지하고 상위 프레임 창의 자식입니다.

- 문서 프레임 창은 현재 활성 보기에 대한 포인터를 유지합니다.

- 문서 템플릿은 열려 있는 문서 목록을 유지합니다.

- 응용 프로그램은 문서 템플릿 목록을 유지합니다.

- Windows는 열려 있는 모든 창을 추적하여 메시지를 보낼 수 있도록 합니다.

이러한 관계는 문서/뷰를 만드는 동안 설정됩니다. 다음 표에서는 실행 중인 프로그램의 개체가 다른 개체에 액세스하는 방법을 보여 주며 있습니다. 모든 개체는 전역 함수 [AfxGetApp를](../mfc/reference/application-information-and-management.md#afxgetapp)호출하여 응용 프로그램 개체에 대한 포인터를 가져올 수 있습니다.

### <a name="gaining-access-to-other-objects-in-your-application"></a>응용 프로그램의 다른 개체에 대한 액세스 권한 확보

|개체에서|다른 개체에 액세스하는 방법|
|-----------------|---------------------------------|
|문서|[GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) 및 [GetNextView를](../mfc/reference/cdocument-class.md#getnextview) 사용하여 문서의 보기 목록에 액세스합니다.<br /><br /> [GetDocTemplate를](../mfc/reference/cdocument-class.md#getdoctemplate) 호출하여 문서 템플릿을 가져옵니다.|
|보기|[GetDocument에](../mfc/reference/cview-class.md#getdocument) 전화하여 문서를 가져옵니다.<br /><br /> [GetParentFrame을](../mfc/reference/cwnd-class.md#getparentframe) 호출하여 프레임 창을 가져옵니다.|
|문서 프레임 창|현재 보기를 얻으려면 [GetActiveView에](../mfc/reference/cframewnd-class.md#getactiveview) 전화합니다.<br /><br /> [GetActiveDocument를](../mfc/reference/cframewnd-class.md#getactivedocument) 호출하여 문서를 현재 보기에 연결합니다.|
|MDI 프레임 창|[MDIGetActive에](../mfc/reference/cmdiframewnd-class.md#mdigetactive) 전화하여 현재 활성 [CMDIChildWnd를](../mfc/reference/cmdichildwnd-class.md)가져옵니다.|


일반적으로 프레임 창에는 하나의 뷰가 있지만 스플리터 창과 마찬가지로 동일한 프레임 창에는 여러 뷰가 포함되는 경우가 있습니다. 프레임 창은 현재 활성 뷰에 대한 포인터를 유지합니다. 포인터는 다른 뷰가 활성화될 때마다 업데이트됩니다.

> [!NOTE]
> 주 프레임 창에 대한 포인터는 응용 프로그램 개체의 [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) 멤버 변수에 저장됩니다. 집합의 `OnFileNew` `InitInstance` 멤버 함수를 재정의하는 호출은 *m_pMainWnd.* `CWinApp` 호출하지 `OnFileNew`않으면 변수값을 `InitInstance` 직접 설정해야 합니다. (SDI COM 구성 요소(서버) 응용 프로그램은 /Embedding이 명령줄에 있는 경우 변수를 설정하지 않을 수 있습니다. 이제 *m_pMainWnd* 클래스가 아닌 `CWinApp` `CWinThread` 클래스의 멤버가 됩니다.

## <a name="see-also"></a>참고 항목

[문서 템플릿 및 문서/뷰 작성 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[문서 템플릿 만들기](../mfc/document-template-creation.md)<br/>
[문서/뷰 만들기](../mfc/document-view-creation.md)<br/>
[새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)
