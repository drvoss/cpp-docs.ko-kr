---
title: C문서 클래스
ms.date: 11/04/2016
f1_keywords:
- CDocument
- AFXWIN/CDocument
- AFXWIN/CDocument::CDocument
- AFXWIN/CDocument::AddView
- AFXWIN/CDocument::BeginReadChunks
- AFXWIN/CDocument::CanCloseFrame
- AFXWIN/CDocument::ClearChunkList
- AFXWIN/CDocument::ClearPathName
- AFXWIN/CDocument::DeleteContents
- AFXWIN/CDocument::FindChunk
- AFXWIN/CDocument::GetAdapter
- AFXWIN/CDocument::GetDocTemplate
- AFXWIN/CDocument::GetFile
- AFXWIN/CDocument::GetFirstViewPosition
- AFXWIN/CDocument::GetNextView
- AFXWIN/CDocument::GetPathName
- AFXWIN/CDocument::GetThumbnail
- AFXWIN/CDocument::GetTitle
- AFXWIN/CDocument::InitializeSearchContent
- AFXWIN/CDocument::IsModified
- AFXWIN/CDocument::IsSearchAndOrganizeHandler
- AFXWIN/CDocument::LoadDocumentFromStream
- AFXWIN/CDocument::OnBeforeRichPreviewFontChanged
- AFXWIN/CDocument::OnChangedViewList
- AFXWIN/CDocument::OnCloseDocument
- AFXWIN/CDocument::OnCreatePreviewFrame
- AFXWIN/CDocument::OnDocumentEvent
- AFXWIN/CDocument::OnDrawThumbnail
- AFXWIN/CDocument::OnLoadDocumentFromStream
- AFXWIN/CDocument::OnNewDocument
- AFXWIN/CDocument::OnOpenDocument
- AFXWIN/CDocument::OnPreviewHandlerQueryFocus
- AFXWIN/CDocument::OnPreviewHandlerTranslateAccelerator
- AFXWIN/CDocument::OnRichPreviewBackColorChanged
- AFXWIN/CDocument::OnRichPreviewFontChanged
- AFXWIN/CDocument::OnRichPreviewSiteChanged
- AFXWIN/CDocument::OnRichPreviewTextColorChanged
- AFXWIN/CDocument::OnSaveDocument
- AFXWIN/CDocument::OnUnloadHandler
- AFXWIN/CDocument::PreCloseFrame
- AFXWIN/CDocument::ReadNextChunkValue
- AFXWIN/CDocument::ReleaseFile
- AFXWIN/CDocument::RemoveChunk
- AFXWIN/CDocument::RemoveView
- AFXWIN/CDocument::ReportSaveLoadException
- AFXWIN/CDocument::SaveModified
- AFXWIN/CDocument::SetChunkValue
- AFXWIN/CDocument::SetModifiedFlag
- AFXWIN/CDocument::SetPathName
- AFXWIN/CDocument::SetTitle
- AFXWIN/CDocument::UpdateAllViews
- AFXWIN/CDocument::OnFileSendMail
- AFXWIN/CDocument::OnUpdateFileSendMail
- AFXWIN/CDocument::m_bGetThumbnailMode
- AFXWIN/CDocument::m_bPreviewHandlerMode
- AFXWIN/CDocument::m_bSearchMode
- AFXWIN/CDocument::m_clrRichPreviewBackColor
- AFXWIN/CDocument::m_clrRichPreviewTextColor
- AFXWIN/CDocument::m_lfRichPreviewFont
helpviewer_keywords:
- CDocument [MFC], CDocument
- CDocument [MFC], AddView
- CDocument [MFC], BeginReadChunks
- CDocument [MFC], CanCloseFrame
- CDocument [MFC], ClearChunkList
- CDocument [MFC], ClearPathName
- CDocument [MFC], DeleteContents
- CDocument [MFC], FindChunk
- CDocument [MFC], GetAdapter
- CDocument [MFC], GetDocTemplate
- CDocument [MFC], GetFile
- CDocument [MFC], GetFirstViewPosition
- CDocument [MFC], GetNextView
- CDocument [MFC], GetPathName
- CDocument [MFC], GetThumbnail
- CDocument [MFC], GetTitle
- CDocument [MFC], InitializeSearchContent
- CDocument [MFC], IsModified
- CDocument [MFC], IsSearchAndOrganizeHandler
- CDocument [MFC], LoadDocumentFromStream
- CDocument [MFC], OnBeforeRichPreviewFontChanged
- CDocument [MFC], OnChangedViewList
- CDocument [MFC], OnCloseDocument
- CDocument [MFC], OnCreatePreviewFrame
- CDocument [MFC], OnDocumentEvent
- CDocument [MFC], OnDrawThumbnail
- CDocument [MFC], OnLoadDocumentFromStream
- CDocument [MFC], OnNewDocument
- CDocument [MFC], OnOpenDocument
- CDocument [MFC], OnPreviewHandlerQueryFocus
- CDocument [MFC], OnPreviewHandlerTranslateAccelerator
- CDocument [MFC], OnRichPreviewBackColorChanged
- CDocument [MFC], OnRichPreviewFontChanged
- CDocument [MFC], OnRichPreviewSiteChanged
- CDocument [MFC], OnRichPreviewTextColorChanged
- CDocument [MFC], OnSaveDocument
- CDocument [MFC], OnUnloadHandler
- CDocument [MFC], PreCloseFrame
- CDocument [MFC], ReadNextChunkValue
- CDocument [MFC], ReleaseFile
- CDocument [MFC], RemoveChunk
- CDocument [MFC], RemoveView
- CDocument [MFC], ReportSaveLoadException
- CDocument [MFC], SaveModified
- CDocument [MFC], SetChunkValue
- CDocument [MFC], SetModifiedFlag
- CDocument [MFC], SetPathName
- CDocument [MFC], SetTitle
- CDocument [MFC], UpdateAllViews
- CDocument [MFC], OnFileSendMail
- CDocument [MFC], OnUpdateFileSendMail
- CDocument [MFC], m_bGetThumbnailMode
- CDocument [MFC], m_bPreviewHandlerMode
- CDocument [MFC], m_bSearchMode
- CDocument [MFC], m_clrRichPreviewBackColor
- CDocument [MFC], m_clrRichPreviewTextColor
- CDocument [MFC], m_lfRichPreviewFont
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
ms.openlocfilehash: d356ba6b6134221c2fc9595fc6d78f91961c5b7f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753250"
---
# <a name="cdocument-class"></a>C문서 클래스

사용자 정의 문서 클래스에 대한 기본 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CDocument : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C문서::C문서](#cdocument)|`CDocument` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C문서::추가 보기](#addview)|문서에 뷰를 연결합니다.|
|[C문서::시작읽기청크](#beginreadchunks)|청크 판독을 초기화합니다.|
|[C문서::캔클로즈프레임](#cancloseframe)|고급 재정의 가능; 이 문서를 보는 프레임 창을 닫기 전에 호출됩니다.|
|[C문서::지우기목록](#clearchunklist)|청크 목록을 지웁습니다.|
|[C문서::클리어 패스 이름](#clearpathname)|문서 개체의 경로를 지웁습니다.|
|[C문서::Delete콘텐츠](#deletecontents)|문서 정리를 수행하도록 호출됩니다.|
|[C문서::찾기청크](#findchunk)|지정된 GUID가 있는 청크를 찾습니다.|
|[C문서::GetAdapter](#getadapter)|인터페이스를 구현하는 `IDocument` 개체에 대한 포인터를 반환합니다.|
|[C문서::GetDocTemplate](#getdoctemplate)|문서 형식을 설명하는 문서 템플릿에 대한 포인터를 반환합니다.|
|[C문서::GetFile](#getfile)|원하는 `CFile` 개체에 대한 포인터를 반환합니다.|
|[C문서::GetFirstView포지션](#getfirstviewposition)|뷰 목록에서 첫 번째 위치의 위치를 반환합니다. 반복을 시작하는 데 사용됩니다.|
|[C문서::겟넥스트뷰](#getnextview)|문서와 연관된 뷰 목록을 통해 이터레이션합니다.|
|[C문서::GetPathName](#getpathname)|문서의 데이터 파일 의 경로를 반환합니다.|
|[C문서::GetThumbnail](#getthumbnail)|썸네일 공급자가 축소판 그림을 표시하는 데 사용할 비트맵을 만들도록 호출됩니다.|
|[C문서::GetTitle](#gettitle)|문서 제목을 반환합니다.|
|[C문서::검색 콘텐츠 초기화](#initializesearchcontent)|검색 처리기에 대한 검색 콘텐츠를 초기화하기 위해 호출됩니다.|
|[C문서::수정됨](#ismodified)|문서가 마지막으로 저장된 이후 수정되었는지 여부를 나타냅니다.|
|[C문서::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|이 개체 인스턴스가 `CDocument` 검색 & 구성 처리기에 대해 만들어졌는지 여부를 알려줍니다.|
|[C문서::로드문서FromStream](#loaddocumentfromstream)|스트림에서 문서 데이터를 로드하도록 호출됩니다.|
|[C문서::에전에리치 프리뷰폰트 변경](#onbeforerichpreviewfontchanged)|리치 미리 보기 글꼴이 변경되기 전에 호출됩니다.|
|[C문서::변경된 뷰리스트](#onchangedviewlist)|뷰가 문서에 추가되거나 문서에서 제거된 후 호출됩니다.|
|[C문서::온클로즈문서](#onclosedocument)|문서를 닫기 위해 호출되었습니다.|
|[C문서::온미프리뷰프레임](#oncreatepreviewframe)|리치 미리 보기에 대한 미리 보기 프레임을 만들어야 할 때 프레임워크에서 호출합니다.|
|[C문서::온문서 이벤트](#ondocumentevent)|문서 이벤트에 대한 응답으로 프레임워크에서 호출됩니다.|
|[C문서::온드로우엄지네일](#ondrawthumbnail)|파생 클래스에서 이 메서드를 재정의하여 축소판 그림의 내용을 그립니다.|
|[C문서::온로드문서FromStream](#onloaddocumentfromstream)|스트림에서 문서 데이터를 로드해야 하는 경우 프레임워크에서 호출합니다.|
|[C문서::온뉴문서](#onnewdocument)|새 문서를 만들기 위해 호출되었습니다.|
|[C문서::온오픈문서](#onopendocument)|기존 문서를 여는 호출됩니다.|
|[C문서::온프리뷰핸들러쿼리포커스](#onpreviewhandlerqueryfocus)|미리 보기 처리기를 지시하여 HWND가 GetFocus 함수를 호출하지 못하도록 합니다.|
|[C문서::미리보기처리기번역가속기](#onpreviewhandlertranslateaccelerator)|미리 보기 처리기가 실행 중인 프로세스의 메시지 펌프에서 전달된 키 입력을 처리하도록 미리 보기 처리기를 지시합니다.|
|[C문서::온리치프리뷰백색상 변경](#onrichpreviewbackcolorchanged)|리치 미리 보기 배경 색이 변경된 경우 호출됩니다.|
|[C문서::온리치프리뷰폰트 변경](#onrichpreviewfontchanged)|리치 미리 보기 글꼴이 변경된 경우 호출됩니다.|
|[C문서::온리치프리뷰사이트변경](#onrichpreviewsitechanged)|리치 미리 보기 사이트가 변경된 경우 호출됩니다.|
|[C문서::온리치프리뷰텍스트색상 변경](#onrichpreviewtextcolorchanged)|리치 미리 보기 텍스트 색상이 변경된 경우 호출됩니다.|
|[C문서::온세이브 문서](#onsavedocument)|문서를 디스크에 저장하기 위해 호출됩니다.|
|[C문서::온로드핸들러](#onunloadhandler)|미리 보기 처리기가 언로드될 때 프레임워크에서 호출됩니다.|
|[C문서::P레클로즈프레임](#precloseframe)|프레임 창이 닫히기 전에 호출됩니다.|
|[C문서::읽기다음청크값](#readnextchunkvalue)|다음 청크 값을 읽습니다.|
|[C문서::릴리스 파일](#releasefile)|다른 응용 프로그램에서 사용할 수 있도록 파일을 해제합니다.|
|[C문서::제거청크](#removechunk)|지정된 GUID로 청크를 제거합니다.|
|[C문서::제거보기](#removeview)|문서에서 보기를 분리합니다.|
|[C문서::보고서저장로드예외](#reportsaveloadexception)|고급 재정의 가능; 는 예외로 인해 열려 있거나 저장 작업을 완료할 수 없는 경우에 호출됩니다.|
|[C문서:::수정된 저장](#savemodified)|고급 재정의 가능; 문서를 저장해야 하는지 여부를 사용자에게 묻습니다.|
|[C문서::SetChunk값](#setchunkvalue)|청크 값을 설정합니다.|
|[C문서::세트수정플래그](#setmodifiedflag)|문서가 마지막으로 저장된 이후 수정했음을 나타내는 플래그를 설정합니다.|
|[C문서::SetPathName](#setpathname)|문서에서 사용하는 데이터 파일의 경로를 설정합니다.|
|[C문서::세트타이틀](#settitle)|문서의 제목을 설정합니다.|
|[C문서::업데이트AllViews](#updateallviews)|문서가 수정되었음을 모든 보기에 알게 합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C문서::온파일센드메일](#onfilesendmail)|문서가 첨부된 메일 메시지를 보냅니다.|
|[C문서::온업데이트파일센드메일](#onupdatefilesendmail)|메일 지원이 있는 경우 메일 보내기 명령을 활성화합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C문서::m_bGetThumbnailMode](#m_bgetthumbnailmode)|dllhost가 `CDocument` 썸네일을 위해 만든 개체를 지정합니다. 을 체크 `CView::OnDraw`인해야 합니다.|
|[C문서::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|에 대한 `Rich Preview` `CDocument` 이전 호스트에서 만든 개체를 지정합니다. 을 체크 `CView::OnDraw`인해야 합니다.|
|[C문서::m_bSearchMode](#m_bsearchmode)|인덱서 `CDocument` 또는 다른 검색 응용 프로그램에서 만든 개체를 지정합니다.|
|[C문서:m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|[[보기] 창의 배경색을 지정합니다. 이 색상은 호스트에 의해 설정됩니다.|
|[C문서:m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|[보기] 창의 전경 색상을 지정합니다. 이 색상은 호스트에 의해 설정됩니다.|
|[C문서::m_lfRichPreviewFont](#m_lfrichpreviewfont)|[[00100]은 [[보기] 창에 텍스트 글꼴을 지정합니다. 이 글꼴 정보는 호스트에 의해 설정됩니다.|

## <a name="remarks"></a>설명

문서는 사용자가 일반적으로 파일 열기 명령으로 열고 파일 저장 명령으로 저장하는 데이터 단위를 나타냅니다.

`CDocument`는 문서 작성, 로드 및 저장과 같은 표준 작업을 지원합니다. 프레임워크는 에 의해 `CDocument`정의된 인터페이스를 사용하여 문서를 조작합니다.

응용 프로그램은 두 개 이상의 문서 유형을 지원할 수 있습니다. 예를 들어 응용 프로그램은 스프레드시트와 텍스트 문서를 모두 지원할 수 있습니다. 각 문서 유형에는 연결된 문서 템플릿이 있습니다. 문서 템플릿은 해당 문서 유형에 사용되는 리소스(예: 메뉴, 아이콘 또는 액셀러레이터 테이블)를 지정합니다. 각 문서에는 연결된 `CDocTemplate` 개체에 대한 포인터가 포함되어 있습니다.

사용자는 연결된 [CView](../../mfc/reference/cview-class.md) 개체를 통해 문서와 상호 작용합니다. 뷰는 프레임 창에서 문서 의 이미지를 렌더링하고 사용자 입력을 문서의 작업으로 해석합니다. 문서에 연결된 여러 뷰가 있을 수 있습니다. 사용자가 문서에서 창을 열면 프레임워크는 뷰를 만들고 문서에 연결합니다. 문서 템플릿은 각 문서 유형을 표시하는 데 사용되는 보기 및 프레임 창 유형을 지정합니다.

문서는 프레임워크의 표준 명령 라우팅의 일부이므로 결과적으로 파일 저장 메뉴 항목과 같은 표준 사용자 인터페이스 구성 요소에서 명령을 받습니다. 문서는 활성 보기에 의해 전달된 명령을 수신합니다. 문서가 지정된 명령을 처리하지 않으면 명령을 관리하는 문서 템플릿으로 전달합니다.

문서의 데이터가 수정되면 각 보기에는 이러한 수정 사항이 반영되어야 합니다. `CDocument`은 [UpdateAllViews](#updateallviews) 멤버 함수를 제공하여 이러한 변경 사항에 대한 뷰를 알리므로 필요에 따라 뷰를 다시 그릴 수 있습니다. 또한 프레임워크는 수정된 파일을 닫기 전에 저장하라는 메시지를 사용자에게 표시합니다.

일반적인 응용 프로그램에서 문서를 구현하려면 다음을 수행해야 합니다.

- 각 문서 `CDocument` 유형에 대해 클래스를 파생합니다.

- 멤버 변수를 추가하여 각 문서의 데이터를 저장합니다.

- 문서의 데이터를 읽고 수정하기 위한 멤버 함수를 구현합니다. 문서의 보기는 이러한 멤버 함수의 가장 중요한 사용자입니다.

- [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) 멤버 함수를 문서 클래스에서 재정의하여 문서의 데이터를 디스크로 및 읽습니다.

`CDocument`메일 지원(MAPI)이 있는 경우 우편으로 문서를 전송할 수 있습니다. [MFC의](../../mfc/mapi-support-in-mfc.md) [MAPI](../../mfc/mapi.md) 및 MAPI 지원 문서를 참조하십시오.

자세한 내용은 [직렬화,](../../mfc/serialization-in-mfc.md) [문서/아키텍처 보기 항목](../../mfc/document-view-architecture.md)및 [문서/보기 만들기](../../mfc/document-view-creation.md)를 참조하십시오. `CDocument`

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cdocumentaddview"></a><a name="addview"></a>C문서::추가 보기

이 함수를 호출하여 문서에 뷰를 연결합니다.

```cpp
void AddView(CView* pView);
```

### <a name="parameters"></a>매개 변수

*pView*<br/>
추가되는 뷰를 가리킵니다.

### <a name="remarks"></a>설명

이 함수는 문서와 연결된 뷰 목록에 지정된 뷰를 추가합니다. 또한 이 함수는 뷰의 문서 포인터를 이 문서에 설정합니다. 프레임워크는 새로 만든 뷰 개체를 문서에 첨부할 때 이 함수를 호출합니다. 이 문제는 파일 새로 열기, 파일 열기 또는 새 창 명령에 대한 응답 또는 스플리터 창이 분할될 때 발생합니다.

뷰를 수동으로 만들고 연결하는 경우에만 이 함수를 호출합니다. 일반적으로 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체를 정의하여 문서 클래스, 뷰 클래스 및 프레임 창 클래스를 연결하도록 프레임워크에서 문서와 뷰를 연결할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

## <a name="cdocumentbeginreadchunks"></a><a name="beginreadchunks"></a>C문서::시작읽기청크

청크 판독을 초기화합니다.

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>설명

## <a name="cdocumentcancloseframe"></a><a name="cancloseframe"></a>C문서::캔클로즈프레임

문서를 표시하는 프레임 창이 닫히기 전에 프레임워크에서 호출됩니다.

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>매개 변수

*pFrame*<br/>
문서에 첨부된 뷰의 프레임 창을 가리킵니다.

### <a name="return-value"></a>Return Value

프레임 창을 닫는 것이 안전하다면 0이 아닌 경우; 그렇지 않으면 0.

### <a name="remarks"></a>설명

기본 구현은 문서를 표시하는 다른 프레임 창이 있는지 확인합니다. 지정된 프레임 창이 문서를 표시하는 마지막 프레임 창인 경우 수정된 경우 문서를 저장하라는 메시지가 표시됩니다. 프레임 창이 닫혀 있을 때 특수 처리를 수행하려는 경우 이 함수를 재정의합니다. 이 고급 재정의 할 수 있습니다.

## <a name="cdocumentcdocument"></a><a name="cdocument"></a>C문서::C문서

`CDocument` 개체를 생성합니다.

```
CDocument();
```

### <a name="remarks"></a>설명

프레임워크는 문서 작성을 처리합니다. 문서별로 초기화를 수행하려면 [OnNewDocument](#onnewdocument) 멤버 함수를 재정의합니다. 이는 단일 문서 인터페이스(SDI) 응용 프로그램에서 특히 중요합니다.

## <a name="cdocumentclearchunklist"></a><a name="clearchunklist"></a>C문서::지우기목록

청크 목록을 지웁습니다.

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>설명

## <a name="cdocumentclearpathname"></a><a name="clearpathname"></a>C문서::클리어 패스 이름

문서 개체의 경로를 지웁습니다.

```
virtual void ClearPathName();
```

### <a name="remarks"></a>설명

`CDocument` 개체에서 경로를 지우면 문서가 다음에 저장될 때 응용 프로그램이 사용자에게 메시지를 표시합니다. 이렇게 하면 **저장** 명령이 **As로 저장** 명령처럼 행동합니다.

## <a name="cdocumentdeletecontents"></a><a name="deletecontents"></a>C문서::Delete콘텐츠

개체 자체를 삭제하지 않고 문서의 데이터를 `CDocument` 삭제하는 프레임워크에서 호출합니다.

```
virtual void DeleteContents();
```

### <a name="remarks"></a>설명

문서가 삭제되기 직전에 호출됩니다. 또한 문서를 다시 사용 하기 전에 비어 있는지 확인 하기 위해 호출 됩니다. 이는 하나의 문서만 사용하는 SDI 응용 프로그램에 특히 중요합니다. 사용자가 다른 문서를 만들거나 열 때마다 문서가 다시 사용됩니다. 이 함수를 호출하여 문서의 모든 데이터를 삭제하는 "모두 지우기 편집" 또는 이와 유사한 명령을 구현합니다. 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 이 함수를 재정의하여 문서의 데이터를 삭제합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

## <a name="cdocumentfindchunk"></a><a name="findchunk"></a>C문서::찾기청크

지정된 GUID가 있는 청크를 찾습니다.

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>매개 변수

*guid*<br/>
찾을 청크의 GUID를 지정합니다.

*Pid*<br/>
찾을 청크의 PID를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 내부 청크 목록에 배치됩니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

## <a name="cdocumentgetadapter"></a><a name="getadapter"></a>C문서::GetAdapter

인터페이스를 구현하는 개체에 `IDocument` 대한 포인터를 반환합니다.

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>Return Value

인터페이스를 구현하는 개체에 `IDocument` 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cdocumentgetdoctemplate"></a><a name="getdoctemplate"></a>C문서::GetDocTemplate

이 함수를 호출하여 이 문서 형식의 문서 템플릿에 대한 포인터를 가져옵니다.

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>Return Value

이 문서 형식에 대한 문서 템플릿에 대한 포인터 또는 문서 템플릿에서 문서를 관리하지 않는 경우 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

## <a name="cdocumentgetfile"></a><a name="getfile"></a>C문서::GetFile

이 멤버 함수를 호출하여 `CFile` 개체에 대한 포인터를 가져옵니다.

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>매개 변수

*lpsz파일이름*<br/>
원하는 파일의 경로인 문자열입니다. 경로는 상대적이거나 절대적일 수 있습니다.

*pError*<br/>
작업의 완료 상태를 나타내는 기존 파일 예외 개체에 대한 포인터입니다.

*n오픈 플래그*<br/>
공유 및 액세스 모드. 파일을 열 때 수행할 작업을 지정합니다. 비트별 OR(&#124;) 연산자를 사용하여 CFile 생성자 [CFile::CFile에](../../mfc/reference/cfile-class.md#cfile) 나열된 옵션을 결합할 수 있습니다. 액세스 권한 1개와 공유 옵션 1개가 필요합니다. `modeCreate` 및 `modeNoInherit` 모드는 선택 사항입니다.

### <a name="return-value"></a>Return Value

`CFile` 개체에 대한 포인터입니다.

## <a name="cdocumentgetfirstviewposition"></a><a name="getfirstviewposition"></a>C문서::GetFirstView포지션

이 함수를 호출하여 문서와 연결된 뷰 목록에서 첫 번째 뷰의 위치를 가져옵니다.

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>Return Value

[GetNextView](#getnextview) 멤버 함수를 사용하여 반복에 사용할 수 있는 위치 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

## <a name="cdocumentgetnextview"></a><a name="getnextview"></a>C문서::겟넥스트뷰

이 함수를 호출하여 문서의 모든 보기를 반복합니다.

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*rPosition*<br/>
`GetNextView` 또는 [GetFirstViewPosition](#getfirstviewposition) 멤버 함수에 대한 이전 호출에서 반환된 위치 값에 대한 참조입니다. 이 값은 NULL이 아니어야 합니다.

### <a name="return-value"></a>Return Value

*rPosition로*식별된 뷰에 대한 포인터입니다.

### <a name="remarks"></a>설명

함수는 *rPosition로* 식별된 뷰를 반환한 다음 *rPosition를* 목록에서 다음 뷰의 위치 값으로 설정합니다. 검색된 뷰가 목록의 마지막 뷰인 경우 *rPosition가* NULL로 설정됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

## <a name="cdocumentgetpathname"></a><a name="getpathname"></a>C문서::GetPathName

이 함수를 호출하여 문서 디스크 파일의 정규화된 경로를 가져옵니다.

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>Return Value

문서의 정규화된 경로입니다. 문서가 저장되지 않았거나 연결된 디스크 파일이 없는 경우 이 문자열은 비어 있습니다.

## <a name="cdocumentgetthumbnail"></a><a name="getthumbnail"></a>C문서::GetThumbnail

썸네일 공급자가 사용할 비트맵을 만들어 썸네일을 표시합니다.

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>매개 변수

*Cx*<br/>
비트맵의 너비와 높이를 지정합니다.

*phbmp*<br/>
함수가 성공적으로 반환될 때 비트맵에 대한 핸들을 포함합니다.

*pdw알파*<br/>
함수가 성공적으로 반환될 때 알파 채널 값을 지정하는 DWORD가 포함되어 있습니다.

### <a name="return-value"></a>Return Value

썸네일의 비트맵이 성공적으로 생성된 경우 TRUE를 반환합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cdocumentgettitle"></a><a name="gettitle"></a>C문서::GetTitle

이 함수를 호출하여 일반적으로 문서의 파일 이름에서 파생되는 문서 제목을 가져옵니다.

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>Return Value

문서의 제목입니다.

## <a name="cdocumentinitializesearchcontent"></a><a name="initializesearchcontent"></a>C문서::검색 콘텐츠 초기화

검색 처리기에 대한 검색 콘텐츠를 초기화하기 위해 호출됩니다.

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 검색 콘텐츠를 초기화합니다. 내용은 ";"로 구분된 부품이 있는 문자열이어야 합니다. 예를 들어, "포인트; 사각형; 올레 항목".

## <a name="cdocumentismodified"></a><a name="ismodified"></a>C문서::수정됨

이 함수를 호출하여 문서가 마지막으로 저장된 이후 수정되었는지 확인합니다.

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>Return Value

문서가 마지막으로 저장된 이후 수정된 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="cdocumentissearchandorganizehandler"></a><a name="issearchandorganizehandler"></a>C문서::IsSearchAndOrganizeHandler

이 인스턴스가 `CDocument` 검색 & 구성 처리기에 대해 만들어졌는지 여부를 알려줍니다.

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>Return Value

검색 & 구성 `CDocument` 처리기에 대해 이 인스턴스가 만들어진 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

현재 이 함수는 프로세스 외 서버에서 구현된 리치 미리 보기 처리기에 대해서만 TRUE를 반환합니다. 응용 프로그램 수준에서 적절한 플래그(m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode)를 설정하여 이 함수가 TRUE를 반환하도록 할 수 있습니다.

## <a name="cdocumentloaddocumentfromstream"></a><a name="loaddocumentfromstream"></a>C문서::로드문서FromStream

스트림에서 문서 데이터를 로드하도록 호출됩니다.

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
스트림에 대한 포인터입니다. 이 스트림은 셸에서 제공됩니다.

*dwGrfMode*<br/>
스트림에 대한 액세스 모드입니다.

### <a name="return-value"></a>Return Value

S_OK 로드 작업이 성공하면 오류 코드가 있는 HRESULT가 있습니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 스트림에서 데이터를 로드하는 방법을 사용자 지정할 수 있습니다.

## <a name="cdocumentm_bgetthumbnailmode"></a><a name="m_bgetthumbnailmode"></a>C문서::m_bGetThumbnailMode

개체가 축소판 `CDocument` 그림에 대 한 dllhost에 의해 만들어진 지정 합니다. 을 체크 `CView::OnDraw`인해야 합니다.

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>설명

`TRUE`은 문서가 축소판용 dllhost에 의해 작성되었다는 것을 나타냅니다.

## <a name="cdocumentm_bpreviewhandlermode"></a><a name="m_bpreviewhandlermode"></a>C문서::m_bPreviewHandlerMode

`CDocument` 리치 미리 보기에 대한 사전 호스트에서 개체를 만들었는지 지정합니다. 을 체크 `CView::OnDraw`인해야 합니다.

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>설명

TRUE는 리치 미리 보기를 위해 사전 호스트에서 문서를 작성했음을 나타냅니다.

## <a name="cdocumentm_bsearchmode"></a><a name="m_bsearchmode"></a>C문서::m_bSearchMode

인덱서 또는 `CDocument` 다른 검색 응용 프로그램에서 개체를 만들었는지 지정합니다.

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>설명

`TRUE`은 문서가 인덱서 또는 다른 검색 응용 프로그램에 의해 생성됨을 나타냅니다.

## <a name="cdocumentm_clrrichpreviewbackcolor"></a><a name="m_clrrichpreviewbackcolor"></a>C문서:m_clrRichPreviewBackColor

[[미리 보기] 창의 배경색을 지정합니다. 이 색상은 호스트에 의해 설정됩니다.

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>설명

## <a name="cdocumentm_clrrichpreviewtextcolor"></a><a name="m_clrrichpreviewtextcolor"></a>C문서:m_clrRichPreviewTextColor

[[보기] 창의 전경 색상을 지정합니다. 이 색상은 호스트에 의해 설정됩니다.

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>설명

## <a name="cdocumentm_lfrichpreviewfont"></a><a name="m_lfrichpreviewfont"></a>C문서::m_lfRichPreviewFont

[[미리 보기] 창의 텍스트 글꼴을 지정합니다. 이 글꼴 정보는 호스트에 의해 설정됩니다.

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>설명

## <a name="cdocumentonbeforerichpreviewfontchanged"></a><a name="onbeforerichpreviewfontchanged"></a>C문서::에전에리치 프리뷰폰트 변경

리치 미리 보기 글꼴이 변경되기 전에 호출됩니다.

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>설명

## <a name="cdocumentonchangedviewlist"></a><a name="onchangedviewlist"></a>C문서::변경된 뷰리스트

뷰가 문서에 추가되거나 문서에서 제거된 후 프레임워크에서 호출됩니다.

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>설명

이 함수의 기본 구현은 마지막 뷰가 제거되고 있는지 여부를 검사하고, 이 경우 문서를 삭제합니다. 프레임워크에서 뷰를 추가하거나 제거할 때 특수 처리를 수행하려는 경우 이 함수를 재정의합니다. 예를 들어 문서가 연결된 뷰가 없는 경우에도 문서를 열어 두려면 이 함수를 재정의합니다.

## <a name="cdocumentonclosedocument"></a><a name="onclosedocument"></a>C문서::온클로즈문서

일반적으로 파일 닫기 명령의 일부로 문서가 닫힐 때 프레임워크에서 호출됩니다.

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>설명

이 함수의 기본 구현은 문서를 보는 데 사용되는 모든 프레임을 삭제하고, 뷰를 닫고, 문서 내용을 정리한 다음 [DeleteContents](#deletecontents) 멤버 함수를 호출하여 문서의 데이터를 삭제합니다.

프레임워크가 문서를 닫을 때 특수 정리 처리를 수행하려는 경우 이 함수를 재정의합니다. 예를 들어 문서가 데이터베이스의 레코드를 나타내는 경우 이 함수를 재정의하여 데이터베이스를 닫을 수 있습니다. 재정의에서 이 함수의 기본 클래스 버전을 호출해야 합니다.

## <a name="cdocumentoncreatepreviewframe"></a><a name="oncreatepreviewframe"></a>C문서::온미프리뷰프레임

리치 미리 보기에 대한 미리 보기 프레임을 만들어야 할 때 프레임워크에서 호출합니다.

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>Return Value

프레임이 성공적으로 생성되면 TRUE를 반환합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cdocumentondocumentevent"></a><a name="ondocumentevent"></a>C문서::온문서 이벤트

문서 이벤트에 대한 응답으로 프레임워크에서 호출됩니다.

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>매개 변수

*디 이벤트*<br/>
【인】 이벤트 유형을 설명하는 예인된 데이터 형식입니다.

### <a name="remarks"></a>설명

문서 이벤트는 여러 클래스에 영향을 줄 수 있습니다. 이 메서드는 [CDocument 클래스](../../mfc/reference/cdocument-class.md)가 아닌 클래스에 영향을 주는 문서 이벤트를 처리 합니다. 현재 문서 이벤트에 응답해야 하는 유일한 클래스는 [CDataRecoveryHandler 클래스입니다.](../../mfc/reference/cdatarecoveryhandler-class.md) 클래스에는 `CDocument` `CDocument`에 대한 영향을 처리하는 다른 재사용 가능한 메서드가 있습니다.

다음 표에는 *deEvent에* 대한 가능한 값과 해당 이벤트가 해당되는 이벤트가 나열되어 있습니다.

|값|해당 이벤트|
|-----------|-------------------------|
|`onAfterNewDocument`|새 문서가 만들어졌습니다.|
|`onAfterOpenDocument`|새 문서가 열렸습니다.|
|`onAfterSaveDocument`|문서가 저장되었습니다.|
|`onAfterCloseDocument`|문서가 닫혔습니다.|

## <a name="cdocumentondrawthumbnail"></a><a name="ondrawthumbnail"></a>C문서::온드로우엄지네일

파생 클래스에서 이 메서드를 재정의하여 축소판 그림을 그립니다.

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>매개 변수

*Dc*<br/>
장치 컨텍스트에 대한 참조입니다.

*lprcBounds*<br/>
축소판 그림을 그려야 하는 영역의 경계 사각형을 지정합니다.

### <a name="remarks"></a>설명

## <a name="cdocumentonfilesendmail"></a><a name="onfilesendmail"></a>C문서::온파일센드메일

첨부 파일로 첨부 된 상주 메일 호스트 (있는 경우)를 통해 메시지를 보냅니다.

```cpp
void OnFileSendMail();
```

### <a name="remarks"></a>설명

`OnFileSendMail`[OnSaveDocument를](#onsavedocument) 호출하여 제목이 없는 수정된 문서를 임시 파일로 직렬화(저장)한 다음 전자 메일을 통해 전송합니다. 문서를 수정하지 않은 경우 임시 파일이 필요하지 않습니다. 원본이 전송됩니다. `OnFileSendMail`MAPI32를 로드합니다. DLL이 아직 로드되지 않은 경우.

`OnFileSendMail` [COleDocument에](../../mfc/reference/coledocument-class.md) 대한 특수 구현은 복합 파일을 올바르게 처리합니다.

`CDocument`메일 지원(MAPI)이 있는 경우 우편으로 문서를 전송할 수 있습니다. [MFC의](../../mfc/mapi-support-in-mfc.md) [MAPI 토픽](../../mfc/mapi.md) 및 MAPI 지원 문서를 참조하십시오.

## <a name="cdocumentonloaddocumentfromstream"></a><a name="onloaddocumentfromstream"></a>C문서::온로드문서FromStream

스트림에서 문서 데이터를 로드해야 하는 경우 프레임워크에서 호출합니다.

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
들어오는 스트림에 대한 포인터입니다.

*그레프 모드*<br/>
스트림에 대한 액세스 모드입니다.

### <a name="return-value"></a>Return Value

S_OK 로드가 성공했는지 를 S_OK. 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="cdocumentonnewdocument"></a><a name="onnewdocument"></a>C문서::온뉴문서

파일 새 명령의 일부로 프레임 워크에 의해 호출 됩니다.

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>Return Value

문서가 성공적으로 초기화된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 DeleteContents 멤버 함수를 호출하여 문서가 비어 있는지 확인하고 새 문서를 정리됨으로 [표시합니다.](#deletecontents) 이 함수를 재정의하여 새 문서의 데이터 구조를 초기화합니다. 재정의에서 이 함수의 기본 클래스 버전을 호출해야 합니다.

사용자가 SDI 응용 프로그램에서 새 파일 새 명령을 선택하면 프레임워크는 이 함수를 사용하여 새 문서를 만드는 대신 기존 문서를 다시 초기화합니다. 사용자가 여러 문서 인터페이스(MDI) 응용 프로그램에서 새 파일 지정을 선택하면 프레임워크는 매번 새 문서를 작성한 다음 이 함수를 호출하여 초기화합니다. SDI 응용 프로그램에서 효과적이기 위해 파일 New 명령을 생성자 대신 이 함수에 초기화 코드를 배치해야 합니다.

두 번 `OnNewDocument` 호출되는 경우가 있습니다. 이 문제는 문서가 ActiveX 문서 서버로 포함될 때 발생합니다. 함수는 `CreateInstance` 먼저 `COleObjectFactory`메서드(-파생 클래스에 의해 노출됨)에 의해 호출되고 메서드에 의해 `InitNew` 두 번째로 호출됩니다(-derived 클래스에 `COleServerDoc`의해 노출됨).

### <a name="example"></a>예제

다음 예제에서는 문서 개체를 초기화하는 대체 방법을 보여 줍니다.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

## <a name="cdocumentonopendocument"></a><a name="onopendocument"></a>C문서::온오픈문서

파일 열기 명령의 일부로 프레임워크에서 호출됩니다.

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
열 문서의 경로를 가리킵니다.

### <a name="return-value"></a>Return Value

문서가 성공적으로 로드된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 지정된 파일을 열고 [DeleteContents](#deletecontents) 멤버 함수를 호출하여 문서가 비어 있는지 확인하고 [CObject::Serialize를](../../mfc/reference/cobject-class.md#serialize) 호출하여 파일내용을 읽은 다음 문서를 정리됨으로 표시합니다. 아카이브 메커니즘 또는 파일 메커니즘 이외의 것을 사용하려는 경우 이 함수를 재정의합니다. 예를 들어 문서가 별도의 파일이 아닌 데이터베이스의 레코드를 나타내는 응용 프로그램을 작성할 수 있습니다.

사용자가 SDI 응용 프로그램에서 파일 열기 명령을 선택하면 프레임워크는 이 함수를 사용하여 `CDocument` 새 개체를 만드는 대신 기존 개체를 다시 초기화합니다. 사용자가 MDI 응용 프로그램에서 파일 열기를 선택하면 프레임워크는 `CDocument` 매번 새 개체를 생성한 다음 이 함수를 호출하여 초기화합니다. SDI 응용 프로그램에서 효과적이기 위해 파일 열기 명령이 유효하려면 생성자 대신 이 함수에 초기화 코드를 배치해야 합니다.

### <a name="example"></a>예제

다음 예제에서는 문서 개체를 초기화하는 대체 방법을 보여 줍니다.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

## <a name="cdocumentonpreviewhandlerqueryfocus"></a><a name="onpreviewhandlerqueryfocus"></a>C문서::온프리뷰핸들러쿼리포커스

미리 보기 처리기를 지시하여 함수를 호출할 `GetFocus` 때 검색된 HWND를 반환합니다.

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>매개 변수

*phwnd*<br/>
【아웃】 이 메서드가 반환될 때 미리 보기 처리기의 `GetFocus` 전경 스레드에서 함수를 호출한 후 반환된 HWND에 대한 포인터가 포함됩니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK 반환합니다. 또는 오류 값 그렇지 않으면.

### <a name="remarks"></a>설명

## <a name="cdocumentonpreviewhandlertranslateaccelerator"></a><a name="onpreviewhandlertranslateaccelerator"></a>C문서::미리보기처리기번역가속기

미리 보기 처리기가 실행 중인 프로세스의 메시지 펌프에서 전달된 키 입력을 처리하도록 미리 보기 처리기를 지시합니다.

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>매개 변수

*pmsg*<br/>
【인】 창 메시지에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

미리 보기 처리기에서 키 입력 메시지를 처리할 수 있는 경우 처리기는 이를 처리하고 S_OK 반환합니다. 미리 보기 처리기가 키 입력 메시지를 처리할 수 없는 `IPreviewHandlerFrame::TranslateAccelerator`경우 을 통해 호스트에 메시지를 제공합니다. 호스트가 메시지를 처리하는 경우 이 메서드는 S_OK 반환합니다. 호스트가 메시지를 처리하지 않으면 이 메서드는 S_FALSE 반환합니다.

### <a name="remarks"></a>설명

## <a name="cdocumentonrichpreviewbackcolorchanged"></a><a name="onrichpreviewbackcolorchanged"></a>C문서::온리치프리뷰백색상 변경

리치 미리 보기 배경 색이 변경된 경우 호출됩니다.

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>설명

## <a name="cdocumentonrichpreviewfontchanged"></a><a name="onrichpreviewfontchanged"></a>C문서::온리치프리뷰폰트 변경

리치 미리 보기 글꼴이 변경된 경우 호출됩니다.

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>설명

## <a name="cdocumentonrichpreviewsitechanged"></a><a name="onrichpreviewsitechanged"></a>C문서::온리치프리뷰사이트변경

리치 미리 보기 사이트가 변경된 경우 호출됩니다.

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>설명

## <a name="cdocumentonrichpreviewtextcolorchanged"></a><a name="onrichpreviewtextcolorchanged"></a>C문서::온리치프리뷰텍스트색상 변경

[미리 보기] 텍스트 색상이 변경된 경우 호출됩니다.

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>설명

## <a name="cdocumentonsavedocument"></a><a name="onsavedocument"></a>C문서::온세이브 문서

파일 저장 또는 파일 저장 명령의 일부로 프레임워크에서 호출됩니다.

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
파일을 저장해야 하는 정규화된 경로를 가리킵니다.

### <a name="return-value"></a>Return Value

문서가 성공적으로 저장된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 지정된 파일을 열고 [CObject::Serialize를](../../mfc/reference/cobject-class.md#serialize) 호출하여 문서의 데이터를 파일에 작성한 다음 문서를 정리됨으로 표시합니다. 프레임워크에서 문서를 저장할 때 특수 처리를 수행하려는 경우 이 함수를 재정의합니다. 예를 들어 문서가 별도의 파일이 아닌 데이터베이스의 레코드를 나타내는 응용 프로그램을 작성할 수 있습니다.

## <a name="cdocumentonunloadhandler"></a><a name="onunloadhandler"></a>C문서::온로드핸들러

미리 보기 처리기가 언로드될 때 프레임워크에서 호출됩니다.

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>설명

## <a name="cdocumentonupdatefilesendmail"></a><a name="onupdatefilesendmail"></a>C문서::온업데이트파일센드메일

메일 지원(MAPI)이 있는 경우 ID_FILE_SEND_MAIL 명령을 활성화합니다.

```cpp
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
ID_FILE_SEND_MAIL 명령과 연결된 [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

그렇지 않으면 함수는 메뉴 항목 위 또는 아래에 있는 구분 기호를 포함하여 메뉴에서 ID_FILE_SEND_MAIL 명령을 제거합니다. MAPI32인 경우 MAPI가 활성화됩니다. DLL은 경로에 있고 WIN의 [메일] 섹션에 있습니다. INI 파일, MAPI=1. 대부분의 응용 프로그램은 이 명령을 파일 메뉴에 배치합니다.

`CDocument`메일 지원(MAPI)이 있는 경우 우편으로 문서를 전송할 수 있습니다. [MFC의](../../mfc/mapi-support-in-mfc.md) [MAPI 토픽](../../mfc/mapi.md) 및 MAPI 지원 문서를 참조하십시오.

## <a name="cdocumentprecloseframe"></a><a name="precloseframe"></a>C문서::P레클로즈프레임

이 멤버 함수는 프레임 창이 소멸되기 전에 프레임워크에서 호출됩니다.

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>매개 변수

*pFrame*<br/>
연결된 개체를 포함하는 [CFrameWnd에](../../mfc/reference/cframewnd-class.md) 대한 포인터입니다. `CDocument`

### <a name="remarks"></a>설명

사용자 지정 정리를 제공하기 위해 재정의할 수 있지만 기본 클래스도 호출해야 합니다.

기본값은 `PreCloseFrame` 에서 `CDocument`아무 것도 수행하지 않습니다. `CDocument`-derive된 클래스 [COleDocument](../../mfc/reference/coledocument-class.md) 및 [CRichEditDoc이](../../mfc/reference/cricheditdoc-class.md) 멤버 함수를 사용 합니다.

## <a name="cdocumentreadnextchunkvalue"></a><a name="readnextchunkvalue"></a>C문서::읽기다음청크값

다음 청크 값을 읽습니다.

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>매개 변수

*pp값*<br/>
【아웃】 함수가 반환되면 *ppValue에는* 읽은 값이 포함됩니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

## <a name="cdocumentreleasefile"></a><a name="releasefile"></a>C문서::릴리스 파일

이 멤버 함수는 프레임워크에서 파일을 해제하도록 호출되므로 다른 응용 프로그램에서 사용할 수 있습니다.

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>매개 변수

*pFile*<br/>
해제할 CFile 개체에 대한 포인터입니다.

*바보트 (주)*<br/>
파일을 사용하여 `CFile::Close` 해제할지 여부를 `CFile::Abort`지정합니다. False 파일을 [CFile::Close를](../../mfc/reference/cfile-class.md#close)사용하여 릴리스할 경우 TRUE 파일을 [CFile::Abort를](../../mfc/reference/cfile-class.md#abort)사용하여 릴리스할 경우.

### <a name="remarks"></a>설명

*bAbort가* `ReleaseFile` TRUE이면 `CFile::Abort`호출하고 파일이 해제됩니다. `CFile::Abort`예외를 throw 하지 않습니다.

*bAbort가* `ReleaseFile` FALSE이면 `CFile::Close` 호출되고 파일이 해제됩니다.

파일이 해제되기 전에 사용자가 작업을 요구하도록 이 멤버 함수를 재정의합니다.

## <a name="cdocumentremovechunk"></a><a name="removechunk"></a>C문서::제거청크

지정된 GUID로 청크를 제거합니다.

```
virtual void RemoveChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>매개 변수

*Guid*<br/>
제거할 청크의 GUID를 지정합니다.

*Pid*<br/>
제거할 청크의 PID를 지정합니다.

### <a name="remarks"></a>설명

## <a name="cdocumentremoveview"></a><a name="removeview"></a>C문서::제거보기

이 함수를 호출하여 문서에서 뷰를 분리합니다.

```cpp
void RemoveView(CView* pView);
```

### <a name="parameters"></a>매개 변수

*pView*<br/>
제거되는 뷰를 가리킵니다.

### <a name="remarks"></a>설명

이 함수는 문서와 연결된 뷰 목록에서 지정된 뷰를 제거합니다. 또한 뷰의 문서 포인터를 NULL로 설정합니다. 프레임 창이 닫히거나 스플리터 창의 창이 닫혀 있을 때 이 함수는 프레임워크에서 호출됩니다.

뷰를 수동으로 분리하는 경우에만 이 함수를 호출합니다. 일반적으로 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체를 정의하여 문서 클래스, 뷰 클래스 및 프레임 창 클래스를 연결하도록 프레임워크에서 문서및 뷰를 분리할 수 있습니다.

샘플 구현에 대한 [AddView의](#addview) 예제를 참조하십시오.

## <a name="cdocumentreportsaveloadexception"></a><a name="reportsaveloadexception"></a>C문서::보고서저장로드예외

문서를 저장하거나 로드하는 동안 예외가 throw된 경우(일반적으로 [CFileException](../../mfc/reference/cfileexception-class.md) 또는 [CArchiveException)가](../../mfc/reference/carchiveexception-class.md)호출됩니다.

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
저장되거나 로드된 문서의 이름을 가리킵니다.

*전자*<br/>
throw된 예외를 가리킵니다. NULL일 수 있습니다.

*b저장*<br/>
진행 중인 작업을 나타내는 플래그; 문서를 저장하는 경우 0이 아닌 경우 문서를 로드하는 경우 0입니다.

*니드P디폴티*<br/>
함수가 더 구체적인 메시지를 지정하지 않으면 표시할 오류 메시지의 식별자입니다.

### <a name="remarks"></a>설명

기본 구현은 예외 개체를 검사하고 원인을 구체적으로 설명하는 오류 메시지를 찾습니다. 특정 메시지를 찾을 수 없거나 *e가* NULL인 경우 *nIDPDefault* 매개 변수에서 지정한 일반 메시지가 사용됩니다. 그러면 함수에 오류 메시지가 포함된 메시지 상자가 표시됩니다. 사용자 지정된 추가 오류 메시지를 제공하려는 경우 이 함수를 재정의합니다. 이 고급 재정의 할 수 있습니다.

## <a name="cdocumentsavemodified"></a><a name="savemodified"></a>C문서:::수정된 저장

수정된 문서를 닫기 전에 프레임워크에서 호출합니다.

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>Return Value

문서를 계속 닫는 것이 안전한 경우 비영; 문서를 닫지 않아야 하는 경우 0입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현에는 변경 내용을 문서에 저장할지 여부를 묻는 메시지 상자가 표시됩니다. 프로그램에 다른 프롬프트 프로시저가 필요한 경우 이 함수를 재정의합니다. 이 고급 재정의 할 수 있습니다.

## <a name="cdocumentsetchunkvalue"></a><a name="setchunkvalue"></a>C문서::SetChunk값

청크 값을 설정합니다.

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
설정할 청크 값을 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

## <a name="cdocumentsetmodifiedflag"></a><a name="setmodifiedflag"></a>C문서::세트수정플래그

문서를 수정한 후 이 함수를 호출합니다.

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>매개 변수

*bModified*<br/>
문서가 수정되었는지 여부를 나타내는 플래그입니다.

### <a name="remarks"></a>설명

이 함수를 일관되게 호출하면 프레임워크에서 문서를 닫기 전에 변경 내용을 저장하라는 메시지가 표시됩니다. 일반적으로 *bModified* 매개 변수에 대해 TRUE의 기본값을 사용해야 합니다. 문서를 수정되지 않은 정리(수정되지 않은)로 표시하려면 FALSE 값을 사용하여 이 함수를 호출합니다.

## <a name="cdocumentsetpathname"></a><a name="setpathname"></a>C문서::SetPathName

이 함수를 호출하여 문서 디스크 파일의 정규화된 경로를 지정합니다.

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
문서의 경로로 사용할 문자열을 가리킵니다.

*bAddToMRU*<br/>
파일 이름이 가장 최근에 사용된(MRU) 파일 목록에 추가되는지 여부를 결정합니다. TRUE이면 파일 이름이 추가됩니다. FALSE인 경우 추가되지 않습니다.

### <a name="remarks"></a>설명

*bAddToMRU의* 값에 따라 경로가 응용 프로그램에서 유지 관리하는 MRU 목록에 추가되거나 추가되지 않습니다. 일부 문서는 디스크 파일과 연결되지 않습니다. 프레임워크에서 사용하는 파일을 열고 저장하기 위한 기본 구현을 재정의하는 경우에만 이 함수를 호출합니다.

## <a name="cdocumentsettitle"></a><a name="settitle"></a>C문서::세트타이틀

이 함수를 호출하여 문서의 제목(프레임 창의 제목 표시줄에 표시된 문자열)을 지정합니다.

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>매개 변수

*lpszTitle*<br/>
문서 제목으로 사용할 문자열을 가리킵니다.

### <a name="remarks"></a>설명

이 함수를 호출하면 문서를 표시하는 모든 프레임 창의 제목이 업데이트됩니다.

## <a name="cdocumentupdateallviews"></a><a name="updateallviews"></a>C문서::업데이트AllViews

문서가 수정된 후 이 함수를 호출합니다.

```cpp
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>매개 변수

*pSender*<br/>
모든 뷰를 업데이트할 경우 문서를 수정한 뷰 또는 NULL을 가리킵니다.

*lHint*<br/>
수정에 대한 정보가 들어 있습니다.

*pHint*<br/>
수정에 대한 정보를 저장하는 객체를 가리킵니다.

### <a name="remarks"></a>설명

[SetModifiedFlag](#setmodifiedflag) 멤버 함수를 호출한 후 이 함수를 호출해야 합니다. 이 함수는 *pSender에서*지정한 뷰를 제외하고 문서에 첨부된 각 뷰에 문서가 수정되었음을 알립니다. 일반적으로 사용자가 뷰를 통해 문서를 변경한 후 뷰 클래스에서 이 함수를 호출합니다.

이 함수는 [cView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) 멤버 함수를 호출합니다.pHint 및 *lHint*를 전달 하는 송신 뷰를 제외 한 문서의 각 보기. *pHint* 이러한 매개 변수를 사용하여 문서에 대한 수정 사항에 대한 정보를 뷰에 전달합니다. *lHint를* 사용하여 정보를 인코딩하거나 [CObject](../../mfc/reference/cobject-class.md)-derived 클래스를 정의하여 수정 사항에 대한 정보를 저장하고 *pHint를*사용하여 해당 클래스의 개체를 전달할 수 있습니다. [CView](../../mfc/reference/cview-class.md) `CView::OnUpdate` -derived 클래스의 멤버 함수를 재정의하여 전달된 정보를 기반으로 뷰 표시의 업데이트를 최적화합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 스냅폭스](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 NPP](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CDoc템플릿 클래스](../../mfc/reference/cdoctemplate-class.md)
