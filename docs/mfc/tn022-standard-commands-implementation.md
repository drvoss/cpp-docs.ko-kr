---
title: 'TN022: 표준 명령 구현'
ms.date: 11/04/2016
f1_keywords:
- vc.commands
helpviewer_keywords:
- ID_PREV_PANE command [MFC]
- ID_APP_EXIT command [MFC]
- ID_NEXT_PANE command [MFC]
- ID_INDICATOR_REC command [MFC]
- ID_WINDOW_SPLIT command [MFC]
- ID_FILE_PRINT_PREVIEW command [MFC]
- ID_WINDOW_CASCADE command [MFC]
- ID_FILE_CLOSE command [MFC]
- ID_FILE_SAVE_COPY_AS command [MFC]
- ID_WINDOW_ARRANGE command [MFC]
- ID_EDIT_FIND command [MFC]
- ID_FILE_OPEN command [MFC]
- ID_FILE_PAGE_SETUP command [MFC]
- ID_OLE_VERB_FIRST command [MFC]
- ID_EDIT_UNDO command [MFC]
- ID_EDIT_CLEAR command [MFC]
- ID_INDICATOR_CAPS command [MFC]
- ID_HELP_INDEX command [MFC]
- commands [MFC], standard
- ID_FILE_PRINT_SETUP command [MFC]
- ID_DEFAULT_HELP command [MFC]
- ID_INDICATOR_SCRL command [MFC]
- ID_FILE_PRINT command [MFC]
- ID_INDICATOR_OVR command [MFC]
- ID_INDICATOR_KANA command [MFC]
- ID_EDIT_COPY command [MFC]
- ID_EDIT_REDO command [MFC]
- ID_EDIT_PASTE command [MFC]
- ID_OLE_INSERT_NEW command [MFC]
- ID_OLE_EDIT_LINKS command [MFC]
- ID_EDIT_PASTE_SPECIAL command [MFC]
- ID_INDICATOR_EXT command [MFC]
- ID_HELP_USING command [MFC]
- standard commands
- ID_VIEW_STATUS_BAR command [MFC]
- ID_FILE_SAVE_AS command [MFC]
- ID_EDIT_CLEAR_ALL command [MFC]
- ID_WINDOW_NEW command [MFC]
- ID_CONTEXT_HELP command [MFC]
- ID_EDIT_REPLACE command [MFC]
- ID_WINDOW_TILE_HORZ command [MFC]
- ID_APP_ABOUT command [MFC]
- TN022
- ID_VIEW_TOOLBAR command [MFC]
- ID_HELP command [MFC]
- ID_WINDOW_TILE_VERT command [MFC]
- ID_EDIT_CUT command [MFC]
- ID_FILE_UPDATE command [MFC]
- ID_EDIT_REPEAT command [MFC]
- ID_FILE_SAVE command [MFC]
- ID_EDIT_PASTE_LINK command [MFC]
- ID_EDIT_SELECT_ALL command [MFC]
- ID_FILE_NEW command [MFC]
- ID_INDICATOR_NUM command
ms.assetid: a7883b46-23f7-4870-ac3a-804aed9258b5
ms.openlocfilehash: 5c7041f40c7e30592f642d29d9d02812a9596864
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370392"
---
# <a name="tn022-standard-commands-implementation"></a>TN022: 표준 명령 구현

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 참고 는 MFC 2.0에서 제공하는 표준 명령 구현에 대해 설명합니다. [기술 참고 21을](../mfc/tn021-command-and-message-routing.md) 먼저 읽으려면 많은 표준 명령을 구현하는 데 사용되는 메커니즘을 설명합니다.

이 설명에서는 MFC 아키텍처, API 및 일반적인 프로그래밍 연습에 대한 지식을 가정합니다. 문서화되지 않은 "구현 전용" API에 대해설명합니다. 이것은 MFC에서 프로그래밍하는 방법이나 기능에 대해 배우기 시작하는 장소가 아닙니다. 자세한 내용 및 문서화된 API에 대한 자세한 내용은 Visual C++를 참조하십시오.

## <a name="the-problem"></a>문제

MFC는 헤더 파일 AFXRES에서 많은 표준 명령 암호를 정의합니다. H. 이러한 명령에 대한 프레임워크 지원은 다양합니다. 프레임워크 클래스가 이러한 명령을 처리하는 위치와 방법을 이해하면 프레임워크가 내부적으로 작동하는 방식을 보여 줄 뿐만 아니라 표준 구현을 사용자 지정하는 방법에 대한 유용한 정보를 제공하고 사용자 고유의 명령 처리기를 구현하기 위한 몇 가지 기술을 설명합니다.

## <a name="contents-of-this-technical-note"></a>이 기술 노트의 내용

각 명령 ID는 두 섹션에서 설명합니다.

- 제목: 명령 ID의 기호 이름(예: ID_FILE_SAVE)과 콜론으로 구분되는 명령의 목적(예: "현재 문서 저장")이 뒤따릅니다.

- 명령을 구현하는 클래스와 기본 구현이 수행하는 작업을 설명하는 하나 이상의 단락

대부분의 기본 명령 구현은 프레임워크의 기본 클래스 메시지 맵에 미리 배선됩니다. 파생 클래스에서 명시적 배선이 필요한 몇 가지 명령 구현이 있습니다. 이러한 설명은 "참고"에 설명되어 있습니다. AppWizard에서 올바른 옵션을 선택한 경우 이러한 기본 처리기가 생성된 스켈레톤 응용 프로그램에서 연결됩니다.

## <a name="naming-convention"></a>명명 규칙

표준 명령은 가능한 경우 사용하는 것이 좋습니다 간단한 명명 규칙을 따릅니다. 대부분의 표준 명령은 응용 프로그램의 메뉴 모음의 표준 위치에 있습니다. 명령의 기호 이름은 "ID_"로 시작하고 표준 팝업 메뉴 이름 다음에 메뉴 항목 이름이 표시됩니다. 기호 이름은 대문자 단어 나누기와 대문자입니다. 표준 메뉴 항목 이름이 없는 명령의 경우 논리 명령 이름은 "ID_"(예: ID_NEXT_PANE)으로 정의됩니다.

접두사 "ID_"을 사용하여 메뉴 항목, 도구 모음 단추 또는 기타 명령 사용자 인터페이스 개체에 바인딩되도록 설계된 명령을 나타냅니다. "ID_" 명령을 처리하는 명령 처리기는 MFC 명령 아키텍처의 ON_COMMAND 및 ON_UPDATE_COMMAND_UI 메커니즘을 사용해야 합니다.

명령 아키텍처를 따르지 않고 메뉴별 코드를 사용하거나 사용하지 않도록 설정해야 하는 메뉴 항목에 표준 "IDM_" 접두사를 사용하는 것이 좋습니다. 물론 MFC 명령 아키텍처를 따르는 것은 명령 처리기를 도구 모음에서 작동하므로 명령 처리기를 더 강력하게 만들 뿐만 아니라 명령 처리기 코드를 재사용할 수 있게 하기 때문에 메뉴 별 명령 의 수는 작아야 합니다.

## <a name="id-ranges"></a>ID 범위

MFC의 ID 범위 사용에 대한 자세한 내용은 [기술 참고 20을](../mfc/tn020-id-naming-and-numbering-conventions.md) 참조하십시오.

MFC 표준 명령은 0xE000 ~ 0xEFFF 범위에 속합니다. 이러한 아이디의 특정 값은 라이브러리의 이후 버전에서 변경될 수 있으므로 사용하지 마십시오.

응용 프로그램은 0x8000 ~ 0xDFFF 범위의 명령을 정의해야 합니다.

## <a name="standard-command-ids"></a>표준 명령 아이디

각 명령 ID에 대해 프롬프트 파일에서 찾을 수 있는 표준 메시지 줄 프롬프트 문자열이 있습니다. Rc. 해당 메뉴 프롬프트의 문자열 ID는 명령 ID와 동일해야 합니다.

- ID_FILE_NEW 새/빈 문서를 만듭니다.

    > [!NOTE]
    >  이 기능을 사용하려면 `CWinApp`파생 클래스의 메시지 맵에 연결해야 합니다.

   `CWinApp::OnFileNew`이 명령을 응용 프로그램의 문서 템플릿 수에 따라 다르게 구현합니다. 하나만 `CDocTemplate` `CWinApp::OnFileNew` 있는 경우 해당 형식의 새 문서와 적절한 프레임 및 뷰 클래스를 만듭니다.

   둘 `CDocTemplate`이상의 문서가 `CWinApp::OnFileNew` 있는 경우 사용할 문서 유형을 선택할 수 있도록 대화 상자(AFX_IDD_NEWTYPEDLG)를 사용자에게 표시합니다. 선택한 `CDocTemplate` 문서를 만드는 데 사용됩니다.

   ID_FILE_NEW 일반적인 사용자 지정 중 하나는 문서 유형의 다른 그래픽 선택을 제공하는 것입니다. 이 경우 직접 `CMyApp::OnFileNew` 구현하고 대신 메시지 맵에 배치할 수 `CWinApp::OnFileNew`있습니다. 기본 클래스 구현을 호출할 필요가 없습니다.

   ID_FILE_NEW 또 다른 일반적인 사용자 지정은 각 유형의 문서를 만들기 위한 별도의 명령을 제공하는 것입니다. 이 경우 ID_FILE_NEW_CHART 및 ID_FILE_NEW_SHEET 같은 새 명령 암호를 정의해야 합니다.

- ID_FILE_OPEN 기존 문서를 엽니다.

    > [!NOTE]
    >  이 기능을 사용하려면 `CWinApp`파생 클래스의 메시지 맵에 연결해야 합니다.

   `CWinApp::OnFileOpen`호출을 매우 간단하게 `CWinApp::DoPromptFileName` 구현한 `CWinApp::OpenDocumentFile` 다음 열 파일의 파일 또는 경로 이름을 따릅니다. 구현 `CWinApp` 루틴은 `DoPromptFileName` 표준 FileOpen 대화 상자를 가져오고 현재 문서 템플릿에서 가져온 파일 확장명으로 채웁니다.

   ID_FILE_OPEN 일반적인 사용자 지정 중 하나는 FileOpen 대화 상자를 사용자 지정하거나 파일 필터를 추가하는 것입니다. 이를 사용자 지정하는 데 권장되는 방법은 기본 구현을 고유한 FileOpen `CWinApp::OpenDocumentFile` 대화 상자로 바꾸고 문서의 파일 또는 경로 이름으로 호출하는 것입니다. 기본 클래스를 호출할 필요가 없습니다.

- ID_FILE_CLOSE 현재 열려 있는 문서를 닫습니다.

   `CDocument::OnFileClose`문서를 `CDocument::SaveModified` 수정한 다음 호출하는 경우 사용자에게 문서를 저장하라는 메시지를 표시하라는 호출이 표시됩니다. `OnCloseDocument` 문서 파기를 포함한 모든 닫는 논리는 `OnCloseDocument` 루틴에서 수행됩니다.

    > [!NOTE]
    >  ID_FILE_CLOSE 문서 프레임 창에 전송된 WM_CLOSE 메시지 또는 SC_CLOSE 시스템 명령과 다르게 작동합니다. 창을 닫으면 문서가 표시되는 마지막 프레임 창인 경우에만 문서가 닫힙습니다. ID_FILE_CLOSE 함께 문서를 닫으면 문서가 닫히지만 문서를 보여주는 모든 프레임 창이 닫힙집니다.

- ID_FILE_SAVE 현재 문서를 저장합니다.

   구현은 둘 다에 `CDocument::DoSave` `OnFileSave` 사용되는 도우미 루틴과 `OnFileSaveAs`. 이전에 저장되지 않은 문서(즉, FileNew의 경우와 같이 경로 이름이 없는) 또는 읽기 전용 문서에서 읽은 문서를 저장하는 경우 `OnFileSave` 논리는 ID_FILE_SAVE_AS 명령처럼 작동하여 사용자에게 새 파일 이름을 제공하도록 요청합니다. 파일을 열고 저장하는 실제 프로세스는 가상 함수를 `OnSaveDocument`통해 수행됩니다.

   ID_FILE_SAVE 사용자 지정하는 데는 두 가지 일반적인 이유가 있습니다. 저장하지 않는 문서의 경우 사용자 인터페이스에서 ID_FILE_SAVE 메뉴 항목 및 도구 모음 단추를 제거하기만 하면 됩니다. 또한 문서를 더럽히지 않도록 해야 합니다(즉, 호출안 `CDocument::SetModifiedFlag`됨) 프레임워크로 인해 문서가 저장되지 않습니다. 디스크 파일이 아닌 다른 위치에 저장하는 문서의 경우 해당 작업에 대한 새 명령을 정의합니다.

   의 경우 `COleServerDoc`ID_FILE_SAVE 파일 저장(일반 문서의 경우) 및 파일 업데이트(포함된 문서의 경우)에 모두 사용됩니다.

   문서 데이터가 개별 디스크 파일에 저장되지만 기본 `CDocument` 직렬화 구현을 사용하지 않으려는 경우 `CDocument::OnSaveDocument` `OnFileSave`을 대신 재정의해야 합니다.

- ID_FILE_SAVE_AS 현재 문서를 다른 파일 이름으로 저장합니다.

   구현은 `CDocument::OnFileSaveAs` 와 `CDocument::DoSave` 동일한 도우미 `OnFileSave`루틴을 사용합니다. `OnFileSaveAs` 저장 하기 전에 문서에 파일 이름이 없는 경우 명령은 ID_FILE_SAVE 처리 됩니다. `COleServerDoc::OnFileSaveAs`에서는 일반 문서 데이터 파일을 저장하거나 다른 응용 프로그램에 포함된 OLE 개체를 별도의 파일로 나타내는 서버 문서를 저장하는 논리를 구현합니다.

   ID_FILE_SAVE 논리를 사용자 지정하는 경우 유사한 방식으로 ID_FILE_SAVE_AS 사용자 지정하거나 문서에 "Save As" 작업이 적용되지 않을 수 있습니다. 필요하지 않은 경우 메뉴 모음에서 메뉴 항목을 제거할 수 있습니다.

- ID_FILE_SAVE_COPY_AS 현재 문서를 새 이름으로 저장합니다.

   구현은 `COleServerDoc::OnFileSaveCopyAs` 저장 후 `CDocument::OnFileSaveAs`문서 개체가 기본 파일에 "첨부"되지 않는다는 점을 제외하면 은 과 매우 유사합니다. 즉, 저장하기 전에 메모리 내 문서가 "수정"된 경우 여전히 "수정"됩니다. 또한 이 명령은 문서에 저장된 경로 이름이나 제목에는 영향을 주지 않습니다.

- ID_FILE_UPDATE 포함된 문서를 저장하기 위해 컨테이너에 대한 통보를 합니다.

   구현은 `COleServerDoc::OnUpdateDocument` 단순히 포함을 저장해야 하는 컨테이너를 알리기만 하면 됩니다. 그런 다음 컨테이너는 포함된 개체를 저장하기 위해 적절한 OLE API를 호출합니다.

- ID_FILE_PAGE_SETUP 응용 프로그램별 페이지 설정/레이아웃 대화 상자를 호출합니다.

   현재 이 대화 상자에는 표준이 없으며 프레임워크에는 이 명령의 기본 구현이 없습니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_FILE_PRINT_SETUP 표준 인쇄 설치 대화 상자를 호출합니다.

    > [!NOTE]
    >  이 기능을 사용하려면 `CWinApp`파생 클래스의 메시지 맵에 연결해야 합니다.

   이 명령은 사용자가 프린터를 사용자 지정하고 최소한 이 문서 또는 이 응용 프로그램의 모든 문서에 대한 설정을 인쇄할 수 있는 표준 인쇄 설정 대화 상자를 호출합니다. 제어판을 사용하여 전체 시스템의 기본 프린터 설정을 변경해야 합니다.

   `CWinApp::OnFilePrintSetup`개체를 만들고 `CPrintDialog` 구현 함수를 호출하는 매우 간단한 구현이 `CWinApp::DoPrintDialog` 있습니다. 이렇게 하면 응용 프로그램 기본 프린터 설정이 설정됩니다.

   이 명령을 사용자 지정하는 일반적인 필요성은 문서당 프린터 설정을 허용하는 것이며, 이 설정은 저장할 때 문서와 함께 저장해야 합니다. 이렇게 `CDocument` 하려면 `CPrintDialog` 개체를 만드는 클래스에 메시지 맵 처리기를 추가하고 적절한 프린터 특성(일반적으로 *hDevMode* 및 *hDevNames)으로* `CPrintDialog::DoModal`초기화하고 를 호출하고 변경된 프린터 설정을 저장해야 합니다. 강력한 구현을 위해 오류를 감지하고 `CWinApp::DoPrintDialog` `CWinApp::UpdatePrinterSelection` 합리적인 기본값을 처리하고 시스템 전체 프린터 변경 사항을 추적하는 구현을 살펴봐야 합니다.

- 현재 문서의 ID_FILE_PRINT 표준 인쇄

    > [!NOTE]
    >  이 기능을 사용하려면 `CView`파생 클래스의 메시지 맵에 연결해야 합니다.

   이 명령은 현재 문서를 인쇄하거나 보다 정확하게 인쇄 프로세스를 시작합니다.

   `CView::OnFilePrint`이 명령과 기본 인쇄 루프를 구현합니다. 인쇄 `CView::OnPreparePrinting` 대화 상자를 사용하여 사용자의 프롬프트를 가상으로 호출합니다. 그런 다음 출력 DC가 프린터로 이동하도록 준비하고 인쇄 진행 률 대화 상자(AFX_IDD_PRINTDLG)를 가져오고 이스케이프를 `StartDoc` 프린터로 보냅니다. `CView::OnFilePrint`또한 기본 페이지 지향 인쇄 루프가 포함되어 있습니다. 각 페이지에 대해 가상 `CView::OnPrepareDC` 을 호출한 다음 `StartPage` 이스케이프를 호출하고 해당 페이지에 대해 가상을 `CView::OnPrint` 호출합니다. 완료되면 가상이 `CView::OnEndPrinting` 호출되고 인쇄 진행률 대화 상자가 닫힙됩니다.

   MFC 인쇄 아키텍처는 인쇄 및 인쇄 미리 보기를 위해 다양한 방법으로 연결되도록 설계되었습니다. 일반적으로 모든 페이지 `CView` 지향 인쇄 작업에 적합한 다양한 재정의 가능한 함수를 찾을 수 있습니다. 페이지 지향이 아닌 출력을 위해 프린터를 사용하는 응용 프로그램의 경우에만 ID_FILE_PRINT 구현을 대체해야 합니다.

- ID_FILE_PRINT_PREVIEW 현재 문서에 대한 인쇄 미리 보기 모드를 입력합니다.

    > [!NOTE]
    >  이 기능을 사용하려면 `CView`파생 클래스의 메시지 맵에 연결해야 합니다.

   `CView::OnFilePrintPreview`문서화된 도우미 함수를 `CView::DoPrintPreview`호출하여 인쇄 미리 보기 모드를 시작합니다. `CView::DoPrintPreview`인쇄 미리 보기 루프의 주요 엔진은 인쇄 루프의 주요 엔진과 마찬가지로 `OnFilePrint` 입니다.

   인쇄 미리 보기 작업은 다른 매개 변수를 에 전달하여 다양한 방법으로 사용자 지정할 `DoPrintPreview`수 있습니다. 인쇄 미리 보기의 세부 사항 및 사용자 지정 방법에 대해 설명하는 [기술 참고 30을](../mfc/tn030-customizing-printing-and-print-preview.md)참조하십시오.

- ID_FILE_MRU_FILE1... FILE16 파일 MRU **목록에**대한 명령 아이디 범위 .

   `CWinApp::OnUpdateRecentFileMenu`는 ON_UPDATE_COMMAND_UI 메커니즘의 고급 용도 중 하나인 업데이트 명령 UI 처리기입니다. 메뉴 리소스에서 ID ID_FILE_MRU_FILE1 있는 단일 메뉴 항목만 정의하면 됩니다. 해당 메뉴 항목은 처음에 비활성화된 상태로 유지됩니다.

   MRU 목록이 커지면 목록에 더 많은 메뉴 항목이 추가됩니다. 표준 `CWinApp` 구현은 가장 최근에 사용한 4개의 파일의 표준 제한을 기본값으로 설정합니다. 더 크거나 작은 `CWinApp::LoadStdProfileSettings` 값으로 호출하여 기본값을 변경할 수 있습니다. MRU 목록은 응용 프로그램의 에 저장됩니다. INI 파일입니다. 를 호출하면 `LoadStdProfileSettings`목록이 응용 `InitInstance` 프로그램의 함수에 로드되고 응용 프로그램이 종료될 때 저장됩니다. MRU 업데이트 명령 UI 처리기도 절대 경로를 파일 메뉴에 표시할 상대 경로로 변환합니다.

   `CWinApp::OnOpenRecentFile`는 실제 명령을 수행하는 ON_COMMAND 처리기입니다. 단순히 MRU 목록및 호출에서 `CWinApp::OpenDocumentFile`파일 이름을 가져옵니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- ID_EDIT_CLEAR 현재 선택 영역을 지웁습니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   `CEditView`을 사용하여 `CEdit::Clear`이 명령의 구현을 제공합니다. 현재 선택 영역이 없는 경우 명령을 사용할 수 없습니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_EDIT_CLEAR_ALL 전체 문서를 지웁습니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다. 예제 구현은 MFC 자습서 샘플 [SCRIBBLE를](../overview/visual-cpp-samples.md) 참조하십시오.

- ID_EDIT_COPY 현재 선택 영역을 클립보드에 복사합니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   `CEditView`CF_TEXT 사용하여 `CEdit::Copy`현재 선택된 텍스트를 클립보드에 복사하는 이 명령의 구현을 제공합니다. 현재 선택 영역이 없는 경우 명령을 사용할 수 없습니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_EDIT_CUT 현재 선택 영역을 클립보드로 잘라냅니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   `CEditView`이 명령의 구현을 제공하며, 이 명령은 현재 선택된 `CEdit::Cut`텍스트를 을 사용하여 CF_TEXT 클립보드로 잘라냅니다. 현재 선택 영역이 없는 경우 명령을 사용할 수 없습니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_EDIT_FIND 찾기 작업을 시작하고 모덜리스 찾기 대화 상자를 가져옵니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   `CEditView`이 명령의 구현을 제공하며, 구현 `OnEditFindReplace` 도우미 함수를 호출하여 이전 찾기/바꾸기 설정을 개인 구현 변수에 사용하고 저장합니다. 클래스는 `CFindReplaceDialog` 사용자에게 프롬프트를 표시하기 위한 모덜리스 대화 상자를 관리하는 데 사용됩니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_EDIT_PASTE 현재 클립보드 내용을 삽입합니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   `CEditView`을 사용하여 `CEdit::Paste`선택한 텍스트를 대체하는 현재 클립보드 데이터를 복사하는 이 명령의 구현을 제공합니다. 클립보드에 **CF_TEXT** 없는 경우 명령이 비활성화됩니다.

   `COleClientDoc`이 명령에 대한 업데이트 명령 UI 처리기를 제공합니다. 클립보드에 포함 가능한 OLE 항목/개체가 없는 경우 명령이 비활성화됩니다. 실제 붙여넣기를 수행 하도록 실제 명령에 대 한 처리기를 작성 하는 책임은 있습니다. OLE 응용 프로그램이 다른 형식을 붙여넣기할 수 있는 경우 뷰 또는 문서에 고유한 업데이트 명령 `COleClientDoc` UI 처리기를 제공해야 합니다(즉, 명령 대상 라우팅의 이전 어딘가).

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

   표준 OLE 구현을 대체할 `COleClientItem::CanPaste`때 는 을 사용합니다.

- ID_EDIT_PASTE_LINK 현재 클립보드 내용의 링크를 삽입합니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   `COleDocument`이 명령에 대한 업데이트 명령 UI 처리기를 제공합니다. 클립보드에 연결 가능한 OLE 항목/개체가 포함되어 있지 않으면 명령이 비활성화됩니다. 실제 붙여넣기를 수행 하도록 실제 명령에 대 한 처리기를 작성 하는 책임은 있습니다. OLE 응용 프로그램이 다른 형식을 붙여넣기할 수 있는 경우 뷰 또는 문서에 고유한 업데이트 명령 `COleDocument` UI 처리기를 제공해야 합니다(즉, 명령 대상 라우팅의 이전 어딘가).

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

   표준 OLE 구현을 대체할 `COleClientItem::CanPasteLink`때 는 을 사용합니다.

- ID_EDIT_PASTE_SPECIAL 옵션으로 현재 클립보드 내용을 삽입합니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다. MFC는 이 대화 상자를 제공하지 않습니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_EDIT_REPEAT 마지막 작업을 반복합니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   `CEditView`에서는 마지막 찾기 작업을 반복하는 이 명령의 구현을 제공합니다. 마지막 찾기에 대한 개인 구현 변수가 사용됩니다. 찾기를 시도할 수 없는 경우 명령이 비활성화됩니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_EDIT_REPLACE 바꾸기 작업을 시작하고 모덜리스 바꾸기 대화 상자를 가져옵니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   `CEditView`이 명령의 구현을 제공하며, 구현 `OnEditFindReplace` 도우미 함수를 호출하여 이전 찾기/바꾸기 설정을 개인 구현 변수에 사용하고 저장합니다. 클래스는 `CFindReplaceDialog` 사용자에게 메시지를 표시하는 모데리스 대화 상자를 관리하는 데 사용됩니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_EDIT_SELECT_ALL 전체 문서를 선택합니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   `CEditView`에서는 문서의 모든 텍스트를 선택하는 이 명령의 구현을 제공합니다. 선택할 텍스트가 없는 경우 명령을 사용할 수 없습니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_EDIT_UNDO 마지막 작업을 취소합니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   `CEditView`을 사용하여 `CEdit::Undo`이 명령의 구현을 제공합니다. FALSE를 반환하면 `CEdit::CanUndo` 명령이 비활성화됩니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_EDIT_REDO 마지막 작업을 다시 수행합니다.

   현재 이 명령에 대한 표준 구현은 없습니다. 각 `CView`파생 클래스에 대해 이 것을 구현해야 합니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_WINDOW_NEW 활성 문서의 다른 창을 엽니다.

   `CMDIFrameWnd::OnWindowNew`현재 문서의 문서 템플릿을 사용하여 현재 문서의 다른 뷰를 포함하는 다른 프레임을 만들어 이 강력한 기능을 구현합니다.

   대부분의 MDI(여러 문서 인터페이스) 창 메뉴 명령과 마찬가지로 활성 MDI 자식 창이 없는 경우 명령이 비활성화됩니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다. 추가 뷰 또는 프레임 창을 만드는 명령을 제공하려는 경우 사용자 고유의 명령을 발명하는 것이 더 나을 수 있습니다. 코드를 `CMDIFrameWnd::OnWindowNew` 복제하여 특정 프레임으로 수정하고 원하는 클래스를 볼 수 있습니다.

- ID_WINDOW_ARRANGE MDI 창 의 하단에 아이콘을 정렬합니다.

   `CMDIFrameWnd`구현 도우미 함수에서 `OnMDIWindowCmd`이 표준 MDI 명령을 구현합니다. 이 도우미는 명령 암호를 MDI Windows 메시지에 매핑하므로 많은 코드를 공유할 수 있습니다.

   대부분의 MDI 창 메뉴 명령과 마찬가지로 활성 MDI 자식 창이 없는 경우 명령이 비활성화됩니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- ID_WINDOW_CASCADE 캐스케이드 창이 겹치게 됩니다.

   `CMDIFrameWnd`구현 도우미 함수에서 `OnMDIWindowCmd`이 표준 MDI 명령을 구현합니다. 이 도우미는 명령 암호를 MDI Windows 메시지에 매핑하므로 많은 코드를 공유할 수 있습니다.

   대부분의 MDI 창 메뉴 명령과 마찬가지로 활성 MDI 자식 창이 없는 경우 명령이 비활성화됩니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- ID_WINDOW_TILE_HORZ 타일 창을 수평으로 합니다.

   이 명령은 작업에 `CMDIFrameWnd` 다른 MDI Windows 메시지가 사용되는 것을 제외하고는 ID_WINDOW_CASCADE 마찬가지로 구현됩니다.

   응용 프로그램의 기본 타일 방향을 선택해야 합니다. 이 작업을 수행할 수 있습니다.창 "타일" 메뉴 항목의 ID를 ID_WINDOW_TILE_HORZ 또는 ID_WINDOW_TILE_VERT.

- ID_WINDOW_TILE_VERT 타일 창을 수직으로 합니다.

   이 명령은 작업에 `CMDIFrameWnd` 다른 MDI Windows 메시지가 사용되는 것을 제외하고는 ID_WINDOW_CASCADE 마찬가지로 구현됩니다.

   응용 프로그램의 기본 타일 방향을 선택해야 합니다. 이 작업을 수행할 수 있습니다.창 "타일" 메뉴 항목의 ID를 ID_WINDOW_TILE_HORZ 또는 ID_WINDOW_TILE_VERT.

- 스플리터에 키보드 인터페이스를 ID_WINDOW_SPLIT.

   `CView`구현에 대해 이 `CSplitterWnd` 명령을 처리합니다. 뷰가 스플리터 창의 일부인 경우 이 명령은 구현 `CSplitterWnd::DoKeyboardSplit`함수에 위임합니다. 이렇게 하면 키보드 사용자가 스플리터 창을 분할하거나 분할해제할 수 있는 모드로 스플리터가 배치됩니다.

   뷰가 스플리터에 없는 경우 이 명령은 비활성화됩니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- ID_APP_ABOUT 소개 대화 상자입니다.

   응용 프로그램의 About 상자에 대한 표준 구현은 없습니다. 기본 AppWizard 만든 응용 프로그램은 응용 프로그램에 대한 사용자 지정 대화 상자 클래스를 만들고 About 상자로 사용합니다. 또한 AppWizard는 이 명령을 처리하고 대화 상자를 호출하는 사소한 명령 처리기를 작성합니다.

   거의 항상 이 명령을 구현합니다.

- ID_APP_EXIT 응용 프로그램을 종료합니다.

   `CWinApp::OnAppExit`은 응용 프로그램의 기본 창에 WM_CLOSE 메시지를 전송하여 이 명령을 처리합니다. 응용 프로그램의 표준 종료(더티 파일 등의 프롬프트)는 `CFrameWnd` 구현에서 처리됩니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다. 재정의 `CWinApp::SaveAllModified` 또는 `CFrameWnd` 닫는 논리를 권장합니다.

   이 명령을 구현하도록 선택한 경우 이 명령 ID를 사용하는 것이 좋습니다.

- ID_HELP_INDEX 에서 도움말 항목 목록 입니다. HLP 파일.

    > [!NOTE]
    >  이 기능을 사용하려면 `CWinApp`파생 클래스의 메시지 맵에 연결해야 합니다.

   `CWinApp::OnHelpIndex`을 호출하여 이 명령을 `CWinApp::WinHelp`처리합니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- ID_HELP_USING 도움말을 사용하는 방법에 대한 도움말을 표시합니다.

    > [!NOTE]
    >  이 기능을 사용하려면 `CWinApp`파생 클래스의 메시지 맵에 연결해야 합니다.

   `CWinApp::OnHelpUsing`을 호출하여 이 명령을 `CWinApp::WinHelp`처리합니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- ID_CONTEXT_HELP SHIFT-F1 도움말 모드로 들어갑니다.

    > [!NOTE]
    >  이 기능을 사용하려면 `CWinApp`파생 클래스의 메시지 맵에 연결해야 합니다.

   `CWinApp::OnContextHelp`는 도움말 모드 커서를 설정하고 모달 루프를 입력하고 사용자가 도움을 받을 창을 선택할 때까지 기다리면서 이 명령을 처리합니다. MFC 도움말 구현에 대한 자세한 내용은 [기술 참고 28을](../mfc/tn028-context-sensitive-help-support.md) 참조하십시오.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- ID_HELP 현재 컨텍스트에 대한 도움말 제공

    > [!NOTE]
    >  이 기능을 사용하려면 `CWinApp`파생 클래스의 메시지 맵에 연결해야 합니다.

   `CWinApp::OnHelp`은 현재 응용 프로그램 컨텍스트에 적합한 도움말 컨텍스트를 제공하여 이 명령을 처리합니다. 이것은 간단한 F1 도움말, 메시지 상자 에 대한 도움말 등을 처리합니다. MFC 도움말 구현에 대한 자세한 내용은 [기술 참고 28을](../mfc/tn028-context-sensitive-help-support.md) 참조하십시오.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- ID_DEFAULT_HELP 컨텍스트에 대한 기본 도움말을 표시합니다.

    > [!NOTE]
    >  이 기능을 사용하려면 `CWinApp`파생 클래스의 메시지 맵에 연결해야 합니다.

   이 명령은 일반적으로 에 `CWinApp::OnHelpIndex`매핑됩니다.

   기본 도움말과 도움말 인덱스의 구분이 필요한 경우 다른 명령 처리기를 제공할 수 있습니다.

- ID_NEXT_PANE 다음 창으로 이동

   `CView`구현에 대해 이 `CSplitterWnd` 명령을 처리합니다. 뷰가 스플리터 창의 일부인 경우 이 명령은 구현 `CSplitterWnd::OnNextPaneCmd`함수에 위임합니다. 그러면 활성 뷰가 스플리터의 다음 창으로 이동합니다.

   뷰가 스플리터에 없거나 다음 창으로 이동하지 않는 경우 이 명령은 비활성화됩니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- 이전 창으로 이동ID_PREV_PANE

   `CView`구현에 대해 이 `CSplitterWnd` 명령을 처리합니다. 뷰가 스플리터 창의 일부인 경우 이 명령은 구현 `CSplitterWnd::OnNextPaneCmd`함수에 위임합니다. 그러면 활성 뷰가 스플리터의 이전 창으로 이동합니다.

   뷰가 스플리터에 없거나 이전 창이 없는 경우 이 명령은 비활성화됩니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- ID_OLE_INSERT_NEW 새 OLE 개체 삽입

   현재 이 명령에 대한 표준 구현은 없습니다. 현재 선택 에서 `CView`새 OLE 항목/개체를 삽입 하려면 -derived 클래스에 대 한이 구현 해야 합니다.

   모든 OLE 클라이언트 응용 프로그램은 이 명령을 구현해야 합니다. Ole 옵션을 사용하여 AppWizard는 완료해야 하는 `OnInsertObject` 뷰 클래스의 스켈레톤 구현을 만듭니다.

   이 명령의 전체 구현은 MFC OLE 샘플 [OCLIENT](../overview/visual-cpp-samples.md) 예제를 참조하십시오.

- ID_OLE_EDIT_LINKS 올레 링크 편집

   `COleDocument`은 MFC에서 제공한 표준 OLE 링크 대화 상자의 구현을 사용하여 이 명령을 처리합니다. 이 대화 상자의 구현은 클래스를 `COleLinksDialog` 통해 액세스됩니다. 현재 문서에 링크가 없는 경우 명령을 사용하지 않도록 설정합니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- ID_OLE_VERB_FIRST... OLE 동사에 대한 마지막 ID 범위

   `COleDocument`은 현재 선택된 OLE 항목/개체에서 지원하는 동사에 대해 이 명령 ID 범위를 사용합니다. 지정된 OLE 항목/개체 형식이 0개 이상의 사용자 지정 동사를 지원할 수 있기 때문에 이 범위여야 합니다. 응용 프로그램의 메뉴에는 ID가 있는 메뉴 항목이 하나 있어야 ID_OLE_VERB_FIRST. 프로그램이 실행되면 메뉴가 적절한 메뉴 동사 설명(또는 많은 동사가 있는 팝업 메뉴)으로 업데이트됩니다. OLE 메뉴의 관리는 이 `AfxOleSetEditMenu`명령에 대한 업데이트 명령 UI 처리기에서 수행된 에 의해 처리됩니다.

   이 범위에는 각 명령 ID를 처리하기 위한 명시적 명령 처리기가 없습니다. `COleDocument::OnCmdMsg`이 범위의 모든 명령 IP를 트랩하고, 0기반 동사 번호로 변환하고, 해당 동사에 `COleClientItem::DoVerb`대한 서버를 실행하기 위해 재정의됩니다(사용).

   이 명령 ID 범위의 사용자 지정 또는 기타 사용은 권장되지 않습니다.

- ID_VIEW_TOOLBAR 도구 모음을 켜고 끄는 것입니다.

   `CFrameWnd`이 명령과 업데이트 명령 UI 처리기를 처리하여 도구 모음의 표시되는 상태를 토글합니다. 도구 모음은 AFX_IDW_TOOLBAR 자식 창 ID가 있는 프레임의 자식 창이어야 합니다. 명령 처리기는 실제로 도구 모음 창의 가시성을 전환합니다. `CFrameWnd::RecalcLayout`을 사용하며 도구 모음을 사용하여 프레임 창을 새 상태로 다시 그립니다. 업데이트 명령 UI 처리기는 도구 모음이 표시되면 메뉴 항목을 확인합니다.

   이 명령 처리기의 사용자 지정은 권장되지 않습니다. 도구 모음을 추가하려면 이 명령에 대한 명령 처리기와 업데이트 명령 UI 처리기를 복제하고 수정해야 합니다.

- ID_VIEW_STATUS_BAR 상태 표시줄을 켜고 끌 수 있습니다.

   이 명령은 다른 `CFrameWnd` 자식 창 ID(AFX_IDW_STATUS_BAR)가 사용되는 것을 제외하고 ID_VIEW_TOOLBAR 마찬가지로 구현됩니다.

## <a name="update-only-command-handlers"></a>업데이트 전용 명령 처리기

여러 표준 명령 ID는 상태 표시줄의 표시로 사용됩니다. 동일한 업데이트 명령 UI 처리 메커니즘을 사용하여 응용 프로그램 유휴 시간 동안 현재 시각적 상태를 표시합니다. 사용자가 선택할 수 없으므로(즉, 상태 표시줄 창을 푸시할 수 없음) 이러한 명령 IP에 대한 ON_COMMAND 처리기를 사용하는 것은 의미가 없습니다.

- ID_INDICATOR_CAPS : 캡 잠금 표시기.

- ID_INDICATOR_NUM : NUM 잠금 표시기.

- ID_INDICATOR_SCRL : SCRL 잠금 표시기.

- ID_INDICATOR_KANA : KANA 잠금 표시기 (일본 시스템에만 적용 가능).

이 세 가지 모두 `CFrameWnd::OnUpdateKeyIndicator`명령 ID를 사용하여 적절한 가상 키에 매핑하는 구현 도우미에서 구현됩니다. 일반적인 구현은 적절한 가상 키가 현재 잠겨 있는지 여부에 `CCmdUI` 따라 개체를 활성화하거나 사용하지 않도록 설정합니다(상태 창 사용 안 함 = 텍스트 없음).

이 명령 처리기의 사용자 지정은 권장되지 않습니다.

- ID_INDICATOR_EXT : 선택 표시기를 EXTended.

- ID_INDICATOR_OVR : OVeRstrike 표시기.

- ID_INDICATOR_REC : 리코드 표시기.

현재 이러한 지표에 대한 표준 구현은 없습니다.

이러한 지표를 구현하도록 선택하는 경우 이러한 표시기 를 사용하고 상태 표시 줄에서 표시기의 순서를 유지하는 것이 좋습니다 (즉, 이 순서: EXT, CAP, NUM, SCRL, OVR, REC).

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
