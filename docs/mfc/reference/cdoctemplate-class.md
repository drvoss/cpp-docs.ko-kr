---
title: CDoc템플릿 클래스
ms.date: 11/04/2016
f1_keywords:
- CDocTemplate
- AFXWIN/CDocTemplate
- AFXWIN/CDocTemplate::CDocTemplate
- AFXWIN/CDocTemplate::AddDocument
- AFXWIN/CDocTemplate::CloseAllDocuments
- AFXWIN/CDocTemplate::CreateNewDocument
- AFXWIN/CDocTemplate::CreateNewFrame
- AFXWIN/CDocTemplate::CreateOleFrame
- AFXWIN/CDocTemplate::CreatePreviewFrame
- AFXWIN/CDocTemplate::GetDocString
- AFXWIN/CDocTemplate::GetFirstDocPosition
- AFXWIN/CDocTemplate::GetNextDoc
- AFXWIN/CDocTemplate::InitialUpdateFrame
- AFXWIN/CDocTemplate::LoadTemplate
- AFXWIN/CDocTemplate::MatchDocType
- AFXWIN/CDocTemplate::OpenDocumentFile
- AFXWIN/CDocTemplate::RemoveDocument
- AFXWIN/CDocTemplate::SaveAllModified
- AFXWIN/CDocTemplate::SetContainerInfo
- AFXWIN/CDocTemplate::SetDefaultTitle
- AFXWIN/CDocTemplate::SetPreviewInfo
- AFXWIN/CDocTemplate::SetServerInfo
helpviewer_keywords:
- CDocTemplate [MFC], CDocTemplate
- CDocTemplate [MFC], AddDocument
- CDocTemplate [MFC], CloseAllDocuments
- CDocTemplate [MFC], CreateNewDocument
- CDocTemplate [MFC], CreateNewFrame
- CDocTemplate [MFC], CreateOleFrame
- CDocTemplate [MFC], CreatePreviewFrame
- CDocTemplate [MFC], GetDocString
- CDocTemplate [MFC], GetFirstDocPosition
- CDocTemplate [MFC], GetNextDoc
- CDocTemplate [MFC], InitialUpdateFrame
- CDocTemplate [MFC], LoadTemplate
- CDocTemplate [MFC], MatchDocType
- CDocTemplate [MFC], OpenDocumentFile
- CDocTemplate [MFC], RemoveDocument
- CDocTemplate [MFC], SaveAllModified
- CDocTemplate [MFC], SetContainerInfo
- CDocTemplate [MFC], SetDefaultTitle
- CDocTemplate [MFC], SetPreviewInfo
- CDocTemplate [MFC], SetServerInfo
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
ms.openlocfilehash: 69b94a4188804f47c950ca31fb5cba80d85176e9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753305"
---
# <a name="cdoctemplate-class"></a>CDoc템플릿 클래스

문서 템플릿의 기본 기능을 정의하는 추상 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CDocTemplate : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CDoc템플릿::CDoc템플릿](#cdoctemplate)|`CDocTemplate` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDoc 템플릿::추가 문서](#adddocument)|템플릿에 문서를 추가합니다.|
|[CDoc 템플릿::닫기모든 문서](#closealldocuments)|이 템플릿과 연결된 모든 문서를 닫습니다.|
|[CDoc 템플릿::새 문서 만들기](#createnewdocument)|새 문서를 만듭니다.|
|[CDoc 템플릿::만들기뉴프레임](#createnewframe)|문서 및 뷰를 포함하는 새 프레임 창을 만듭니다.|
|[CDoc템플릿::크리에이션올레프레임](#createoleframe)|OLE 지원 프레임 창을 만듭니다.|
|[CDoc 템플릿::미리 보기 만들기프레임 만들기](#createpreviewframe)|[리치 미리 보기]에 사용되는 하위 프레임을 만듭니다.|
|[CDoc 템플릿 ::GetDocString](#getdocstring)|문서 유형과 연결된 문자열을 검색합니다.|
|[CDoc 템플릿::GetFirstDocPosition](#getfirstdocposition)|이 템플릿과 연결된 첫 번째 문서의 위치를 검색합니다.|
|[CDoc 템플릿::GetNextDoc](#getnextdoc)|문서와 다음 문서의 위치를 검색합니다.|
|[CDoc 템플릿::초기 업데이트 프레임](#initialupdateframe)|프레임 창을 초기화하고 선택적으로 표시합니다.|
|[CDoc 템플릿:로드 템플릿](#loadtemplate)|지정된 `CDocTemplate` 또는 파생 클래스에 대한 리소스를 로드합니다.|
|[CDoc 템플릿::매치닥타입](#matchdoctype)|문서 형식과 이 템플릿 간의 일치에 대한 신뢰도를 결정합니다.|
|[CDoc 템플릿::오픈 문서 파일](#opendocumentfile)|경로 이름으로 지정된 파일을 엽니다.|
|[CDoc 템플릿::제거문서](#removedocument)|템플릿에서 문서를 제거합니다.|
|[CDoc 템플릿::SaveAll수정](#saveallmodified)|수정된 이 템플릿과 연결된 모든 문서를 저장합니다.|
|[CDoc 템플릿::세트 컨테이너정보](#setcontainerinfo)|내부 OLE 항목을 편집할 때 OLE 컨테이너에 대한 리소스를 결정합니다.|
|[CDoc 템플릿:설정기본 제목](#setdefaulttitle)|문서 창의 제목 표시줄에 기본 제목을 표시합니다.|
|[CDoc 템플릿::세트 미리보기정보](#setpreviewinfo)|프로세스 미리 보기 처리기에서 설정합니다.|
|[CDoc 템플릿::세트 서버정보](#setserverinfo)|서버 문서가 포함되거나 편집될 때 리소스 및 클래스를 결정합니다.|

## <a name="remarks"></a>설명

일반적으로 응용 프로그램 `InitInstance` 기능을 구현할 때 하나 이상의 문서 템플릿을 만듭니다. 문서 템플릿은 세 가지 유형의 클래스 간의 관계를 정의합니다.

- 에서 파생되는 문서 클래스입니다. `CDocument`

- 위에 나열된 문서 클래스의 데이터를 표시하는 뷰 클래스입니다. 에서 이 클래스를 `CView` `CScrollView` `CFormView` `CEditView`파생할 수 있습니다. (직접 사용할 `CEditView` 수도 있습니다.)

- 뷰를 포함하는 프레임 창 클래스입니다. 단일 문서 인터페이스(SDI) 응용 프로그램의 경우 `CFrameWnd`에서 이 클래스를 파생합니다. 여러 문서 인터페이스(MDI) 응용 프로그램의 경우 `CMDIChildWnd`에서 이 클래스를 파생합니다. 프레임 창의 동작을 사용자 지정할 필요가 없는 경우 `CFrameWnd` 고유한 `CMDIChildWnd` 클래스를 파생하지 않고 직접 사용하거나 직접 사용할 수 있습니다.

응용 프로그램에는 지원하는 각 문서 유형에 대해 하나의 문서 템플릿이 있습니다. 예를 들어 응용 프로그램에서 스프레드시트와 텍스트 문서를 모두 지원하는 경우 응용 프로그램에는 두 개의 문서 템플릿 개체가 있습니다. 각 문서 템플릿은 해당 형식의 모든 문서를 만들고 관리합니다.

문서 템플릿은 문서, `CRuntimeClass` 보기 및 프레임 창 클래스에 대한 개체에 대한 포인터를 저장합니다. 이러한 `CRuntimeClass` 개체는 문서 템플릿을 생성할 때 지정됩니다.

문서 템플릿에는 문서 유형(예: 메뉴, 아이콘 또는 액셀러레이터 테이블 리소스)과 함께 사용되는 리소스의 ID가 포함되어 있습니다. 문서 템플릿에는 문서 유형에 대한 추가 정보가 포함된 문자열도 있습니다. 여기에는 문서 유형(예: "워크시트")과 파일 확장명(예: ".xls")의 이름이 포함됩니다. 선택적으로 응용 프로그램의 사용자 인터페이스, Windows 파일 관리자 및 개체 연결 및 포함(OLE) 지원에서 사용하는 다른 문자열이 포함될 수 있습니다.

응용 프로그램이 OLE 컨테이너 및/또는 서버인 경우 문서 템플릿은 내부 활성화 중에 사용되는 메뉴의 ID도 정의합니다. 응용 프로그램이 OLE 서버인 경우 문서 템플릿은 내부 활성화 중에 사용되는 도구 모음 및 메뉴의 ID를 정의합니다. 호출 `SetContainerInfo` 및 `SetServerInfo`을 통해 이러한 추가 OLE 리소스를 지정합니다.

추상 클래스이기 때문에 `CDocTemplate` 클래스를 직접 사용할 수 없습니다. 일반적인 응용 프로그램은 Microsoft `CDocTemplate`Foundation 클래스 라이브러리에서 `CSingleDocTemplate` `CMultiDocTemplate`제공하는 두 가지 파생 클래스 중 하나를 사용합니다. 문서 템플릿 사용에 대한 자세한 내용은 해당 클래스를 참조하십시오.

응용 프로그램에 SDI 또는 MDI와 근본적으로 다른 사용자 인터페이스 패러다임이 필요한 경우 `CDocTemplate`에서 고유한 클래스를 파생시킬 수 있습니다.

자세한 `CDocTemplate`내용은 문서 [템플릿 및 문서/보기 작성 프로세스를](../../mfc/document-templates-and-the-document-view-creation-process.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocTemplate`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cdoctemplateadddocument"></a><a name="adddocument"></a>CDoc 템플릿::추가 문서

이 함수를 사용하여 템플릿에 문서를 추가합니다.

```
virtual void AddDocument(CDocument* pDoc);
```

### <a name="parameters"></a>매개 변수

*pDoc*<br/>
추가할 문서에 대한 포인터입니다.

### <a name="remarks"></a>설명

파생 된 클래스 [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) 및 [CSingleDocTemplate이](../../mfc/reference/csingledoctemplate-class.md) 함수를 재정의 합니다. 에서 `CDocTemplate`고유한 문서 템플릿 클래스를 파생하는 경우 파생 클래스는 이 함수를 재정의해야 합니다.

## <a name="cdoctemplatecdoctemplate"></a><a name="cdoctemplate"></a>CDoc템플릿::CDoc템플릿

`CDocTemplate` 개체를 생성합니다.

```
CDocTemplate (
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>매개 변수

*nIDResource*<br/>
문서 유형에 사용된 리소스의 ID를 지정합니다. 여기에는 메뉴, 아이콘, 액셀러레이터 테이블 및 문자열 리소스가 포함될 수 있습니다.

문자열 리소스는 '\n' 문자로 구분된 최대 7개의 하위 문자열로 구성됩니다(하위 문자열이 포함되지 않은 경우 '\n' 문자는 자리 표시자로 필요하지만 후행 '\n' 문자는 필요하지 않습니다.) 이러한 하위 문자열은 문서 형식을 설명합니다. 하위 문자열에 대한 자세한 내용은 [GetDocString](#getdocstring)을 참조하십시오. 이 문자열 리소스는 응용 프로그램의 리소스 파일에서 찾을 수 있습니다. 다음은 그 예입니다.

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

문자열은 '\n' 문자로 시작합니다. 이는 첫 번째 하위 문자열이 MDI 응용 프로그램에 사용되지 않으므로 포함되지 않기 때문입니다. 문자열 편집기에서 이 문자열을 편집할 수 있습니다. 전체 문자열은 7개의 개별 항목이 아니라 문자열 편집기의 단일 항목으로 나타납니다.

*pDoc클래스*<br/>
문서 클래스의 `CRuntimeClass` 개체를 가리킵니다. 이 클래스는 `CDocument`문서를 나타내기 위해 정의한 -파생 클래스입니다.

*pFrame클래스*<br/>
프레임 창 `CRuntimeClass` 클래스의 개체를 가리킵니다. 이 클래스는 `CFrameWnd`-derived 클래스일 수도 `CFrameWnd` 있고 주 프레임 창에 대한 기본 동작을 원하는 경우 그 자체일 수도 있습니다.

*pView클래스*<br/>
뷰 클래스의 `CRuntimeClass` 개체를 가리킵니다. 이 클래스는 `CView`문서를 표시하도록 정의하는 -derive 클래스입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 `CDocTemplate` 사용하여 개체를 생성합니다. 개체를 `CDocTemplate` 동적으로 할당하고 응용 프로그램 클래스의 멤버 함수에서 `InitInstance` [CWinApp::AddDocTemplate에](../../mfc/reference/cwinapp-class.md#adddoctemplate) 전달합니다.

## <a name="cdoctemplateclosealldocuments"></a><a name="closealldocuments"></a>CDoc 템플릿::닫기모든 문서

열려 있는 모든 문서를 닫을 려면 이 멤버 함수를 호출합니다.

```
virtual void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>매개 변수

*bEndSession*<br/>
사용되지 않습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 일반적으로 파일 종료 명령의 일부로 사용됩니다. 이 함수의 기본 구현은 [CDocument::DeleteContents](../../mfc/reference/cdocument-class.md#deletecontents) 멤버 함수를 호출하여 문서의 데이터를 삭제한 다음 문서에 연결된 모든 뷰의 프레임 창을 닫습니다.

문서를 닫기 전에 사용자가 특별한 정리 처리를 수행하도록 하려면 이 함수를 재정의합니다. 예를 들어 문서가 데이터베이스의 레코드를 나타내는 경우 이 함수를 재정의하여 데이터베이스를 닫을 수 있습니다.

## <a name="cdoctemplatecreatenewdocument"></a><a name="createnewdocument"></a>CDoc 템플릿::새 문서 만들기

이 멤버 함수를 호출하여 이 문서 템플릿과 연결된 형식의 새 문서를 만듭니다.

```
virtual CDocument* CreateNewDocument();
```

### <a name="return-value"></a>Return Value

새로 만든 문서에 대한 포인터 또는 오류가 발생하면 NULL입니다.

## <a name="cdoctemplatecreatenewframe"></a><a name="createnewframe"></a>CDoc 템플릿::만들기뉴프레임

문서 및 뷰를 포함하는 새 프레임 창을 만듭니다.

```
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,
    CFrameWnd* pOther);
```

### <a name="parameters"></a>매개 변수

*pDoc*<br/>
새 프레임 창이 참조해야 하는 문서입니다. NULL일 수 있습니다.

*p기타*<br/>
새 프레임 창을 기반으로 하는 프레임 창입니다. NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

새로 생성된 프레임 창또는 오류가 발생하면 NULL에 대한 포인터입니다.

### <a name="remarks"></a>설명

`CreateNewFrame`생성자로 전달된 `CRuntimeClass` 객체를 사용하여 뷰및 문서가 첨부된 새 프레임 창을 만듭니다. *pDoc* 매개 변수가 NULL이면 프레임워크는 TRACE 메시지를 출력합니다.

*pOther* 매개 변수는 창 새 명령을 구현하는 데 사용됩니다. 새 프레임 창을 모델링할 프레임 창을 제공합니다. 새 프레임 창은 일반적으로 보이지 않게 만들어집니다. 이 함수를 호출하여 파일 새로 만들기 및 파일 열기의 표준 프레임워크 구현 외부에 프레임 창을 만듭니다.

## <a name="cdoctemplatecreateoleframe"></a><a name="createoleframe"></a>CDoc템플릿::크리에이션올레프레임

OLE 프레임 창을 만듭니다.

```
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,
    CDocument* pDoc,
    BOOL bCreateView);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
프레임의 상위 창에 대한 포인터입니다.

*pDoc*<br/>
새 OLE 프레임 창이 참조해야 하는 문서에 대한 포인터입니다.

*b만들기보기*<br/>
프레임과 함께 뷰가 작성되는지 여부를 결정합니다.

### <a name="return-value"></a>Return Value

성공하면 프레임 창에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

*bCreateView가* 0이면 빈 프레임이 만들어집니다.

## <a name="cdoctemplategetdocstring"></a><a name="getdocstring"></a>CDoc 템플릿 ::GetDocString

문서 유형과 연결된 문자열을 검색합니다.

```
virtual BOOL GetDocString(
    CString& rString,
    enum DocStringIndex index) const;
```

### <a name="parameters"></a>매개 변수

*rString*<br/>
함수가 `CString` 반환될 때 문자열을 포함하는 개체에 대한 참조입니다.

*index*<br/>
문서 형식을 설명하는 문자열에서 검색되는 하위 문자열의 인덱스입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.

- `CDocTemplate::windowTitle`응용 프로그램 창의 제목 표시줄에 나타나는 이름(예: "Microsoft Excel"). SDI 응용 프로그램에 대한 문서 템플릿에만 표시됩니다.

- `CDocTemplate::docName`기본 문서 이름(예: "시트")에 대한 루트입니다. 이 루트와 숫자는 사용자가 파일 메뉴에서 새 명령을 선택할 때마다 이 유형의 새 문서의 기본 이름에 사용됩니다(예: "Sheet1" 또는 "Sheet2"). 지정하지 않으면 "제목 없음"이 기본값으로 사용됩니다.

- `CDocTemplate::fileNewName`이 문서 유형의 이름입니다. 응용 프로그램이 두 개 이상의 문서 유형을 지원하는 경우 이 문자열은 새 파일 대화 상자(예: "워크시트")에 표시됩니다. 지정하지 않으면 새 파일 명령을 사용하여 문서 형식에 액세스할 수 없습니다.

- `CDocTemplate::filterName`이 유형의 문서와 와일드카드 필터일치 문서에 대한 설명입니다. 이 문자열은 파일 열기 대화 상자의 형식 파일 목록 드롭다운 목록에 표시됩니다(예: "워크시트(*.xls)"). 지정하지 않으면 파일 열기 명령을 사용하여 문서 형식에 액세스할 수 없습니다.

- `CDocTemplate::filterExt`이 유형의 문서에 대한 확장(예: ".xls"). 지정하지 않으면 파일 열기 명령을 사용하여 문서 형식에 액세스할 수 없습니다.

- `CDocTemplate::regFileTypeId`Windows에서 유지 관리하는 등록 데이터베이스에 저장할 문서 형식의 식별자입니다. 이 문자열은 내부 용도로만 사용됩니다(예: "ExcelWorksheet"). 지정하지 않으면 문서 유형을 Windows 파일 관리자에 등록할 수 없습니다.

- `CDocTemplate::regFileTypeName`등록 데이터베이스에 저장할 문서 유형의 이름입니다. 이 문자열은 등록 데이터베이스에 액세스하는 응용 프로그램의 대화 상자(예: "Microsoft Excel 워크시트")에 표시될 수 있습니다.

### <a name="return-value"></a>Return Value

지정된 하위 문자열이 발견된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수를 호출하여 문서 형식을 설명하는 특정 하위 문자열을 검색합니다. 이러한 하위 문자열을 포함하는 문자열은 문서 템플릿에 저장되며 응용 프로그램의 리소스 파일의 문자열에서 파생됩니다. 프레임워크는 이 함수를 호출하여 응용 프로그램의 사용자 인터페이스에 필요한 문자열을 가져옵니다. 응용 프로그램의 문서에 대한 파일 이름 확장명을 지정한 경우 Windows 등록 데이터베이스에 항목을 추가할 때 프레임워크도 이 함수를 호출합니다. 이렇게 하면 Windows 파일 관리자에서 문서를 열 수 있습니다.

에서 사용자 고유의 클래스를 파생하는 경우에만 `CDocTemplate`이 함수를 호출합니다.

## <a name="cdoctemplategetfirstdocposition"></a><a name="getfirstdocposition"></a>CDoc 템플릿::GetFirstDocPosition

이 템플릿과 연결된 첫 번째 문서의 위치를 검색합니다.

```
virtual POSITION GetFirstDocPosition() const = 0;
```

### <a name="return-value"></a>Return Value

이 문서 템플릿과 연관된 문서 목록을 반복하는 데 사용할 수 있는 위치 값입니다. 또는 목록이 비어 있는 경우 NULL을 선택합니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 이 템플릿과 연결된 문서 목록에서 첫 번째 문서의 위치를 가져옵니다. 위치 값을 [CDocTemplate::GetNextDoc에](#getnextdoc) 대한 인수로 사용하여 템플릿과 연결된 문서 목록을 반복합니다.

[CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) 및 [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) 모두 이 순수 가상 함수를 재정의합니다. 파생된 `CDocTemplate` 모든 클래스도 이 함수를 재정의해야 합니다.

## <a name="cdoctemplategetnextdoc"></a><a name="getnextdoc"></a>CDoc 템플릿::GetNextDoc

*rPos에서*식별된 목록 요소를 검색한 다음 *rPos를* 목록의 다음 항목의 위치 값으로 설정합니다.

```
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;
```

### <a name="return-value"></a>Return Value

이 템플릿과 연결된 문서 목록의 다음 문서에 대한 포인터입니다.

### <a name="parameters"></a>매개 변수

*rPos*<br/>
[GetFirstDocPosition](#getfirstdocposition) 또는 `GetNextDoc`에 대한 이전 호출에서 반환된 위치 값에 대한 참조입니다.

### <a name="remarks"></a>설명

검색된 요소가 목록의 마지막 요소인 경우 *rPos의* 새 값이 NULL로 설정됩니다.

`GetNextDoc` [GetFirstDocPosition에](#getfirstdocposition)대한 호출을 사용하여 초기 위치를 설정하는 경우 정방향 반복 루프에서 사용할 수 있습니다.

POSITION 값이 목록에서 유효한 위치를 나타내는지 확인해야 합니다. 유효하지 않은 경우 Microsoft 파운데이션 클래스 라이브러리의 디버그 버전이 어설션됩니다.

## <a name="cdoctemplateinitialupdateframe"></a><a name="initialupdateframe"></a>CDoc 템플릿::초기 업데이트 프레임

프레임 창을 초기화하고 선택적으로 표시합니다.

```
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,
    CDocument* pDoc,
    BOOL bMakeVisible = TRUE);
```

### <a name="parameters"></a>매개 변수

*pFrame*<br/>
초기 업데이트가 필요한 프레임 창입니다.

*pDoc*<br/>
프레임이 연결된 문서입니다. NULL일 수 있습니다.

*bMakeVisible*<br/>
프레임이 표시되고 활성화되어야 하는지 여부를 나타냅니다.

### <a name="remarks"></a>설명

을 `IntitialUpdateFrame` 통해 새 프레임을 `CreateNewFrame`만든 후 호출합니다. 이 함수를 호출하면 해당 프레임 창의 뷰가 호출을 수신합니다. `OnInitialUpdate` 또한 이전에 활성 뷰가 없는 경우 프레임 창의 기본 뷰가 활성화됩니다. 기본 보기는 AFX_IDW_PANE_FIRST 자식 ID가 있는 보기입니다. 마지막으로 *bMakeVisible가* 0이 아닌 경우 프레임 창이 표시됩니다. *bMakeVisible가* 0이면 프레임 창의 현재 초점과 표시되는 상태는 변경되지 않습니다.

프레임워크의 파일 새 및 파일 열기 구현을 사용할 때 이 함수를 호출할 필요는 없습니다.

## <a name="cdoctemplateloadtemplate"></a><a name="loadtemplate"></a>CDoc 템플릿:로드 템플릿

지정된 `CDocTemplate` 또는 파생 클래스에 대한 리소스를 로드합니다.

```
virtual void LoadTemplate();
```

### <a name="remarks"></a>설명

이 멤버 함수는 지정된 `CDocTemplate` 클래스 또는 파생 클래스에 대 한 리소스를 로드 하는 프레임 워크에 의해 호출 됩니다. 일반적으로 템플릿이 전역으로 생성되는 경우를 제외하고 는 구성 중에 호출됩니다. 이 경우 `LoadTemplate` [CWinApp::AddDocTemplate가](../../mfc/reference/cwinapp-class.md#adddoctemplate) 호출될 때까지 호출이 지연됩니다.

## <a name="cdoctemplatematchdoctype"></a><a name="matchdoctype"></a>CDoc 템플릿::매치닥타입

문서 형식과 이 템플릿 간의 일치에 대한 신뢰도를 결정합니다.

```
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,
    CDocument*& rpDocMatch);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
형식을 결정할 파일의 경로 이름입니다.

*rpDocMatch*<br/>
*lpszPathName에* 의해 지정된 파일이 이미 열려 있는 경우 일치하는 문서가 할당된 문서에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

**신뢰 열거형의** 값으로, 다음과 같이 정의됩니다.

```
enum Confidence
    {
    noAttempt,
    maybeAttemptForeign,
    maybeAttemptNative,
    yesAttemptForeign,
    yesAttemptNative,
    yesAlreadyOpen
    };
```

### <a name="remarks"></a>설명

이 함수를 사용하여 파일을 여는 데 사용할 문서 템플릿의 유형을 결정합니다. 예를 들어 응용 프로그램에서 여러 파일 형식을 지원하는 경우 이 함수를 사용하여 각 템플릿을 차례로 호출하고 `MatchDocType` 반환된 신뢰도 값에 따라 템플릿을 선택하여 지정된 파일에 적합한 문서 템플릿을 결정할 수 있습니다.

*lpszPathName에* 의해 지정된 파일이 이미 열려 `CDocTemplate::yesAlreadyOpen` 있는 경우 이 `CDocument` 함수는 *rpDocMatch*에서 파일의 개체를 반환하고 개체에 복사합니다.

파일이 열려 있지 않지만 *lpszPathName의* 확장명이 에 `CDocTemplate::filterExt`의해 지정된 `CDocTemplate::yesAttemptNative` 확장명과 일치하는 경우 이 함수는 *rpDocMatch를* NULL로 반환하고 설정합니다. 자세한 `CDocTemplate::filterExt`내용은 [CDocTemplate::GetDocString](#getdocstring)을 참조하십시오.

두 경우 모두 true이면 `CDocTemplate::yesAttemptForeign`함수가 반환됩니다.

기본 구현이 `CDocTemplate::maybeAttemptForeign` 반환되지 `CDocTemplate::maybeAttemptNative`않거나 . 이 함수를 재정의하여 **신뢰** 열거에서 이러한 두 값을 사용하여 응용 프로그램에 적합한 형식 일치 논리를 구현합니다.

## <a name="cdoctemplateopendocumentfile"></a><a name="opendocumentfile"></a>CDoc 템플릿::오픈 문서 파일

경로에 의해 지정된 파일을 엽니다.

```
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;

virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU) = 0;
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
【인】 열 문서를 포함하는 파일의 경로에 대한 포인터입니다.

*bAddToMRU*<br/>
【인】 TRUE는 문서가 가장 최근 파일 중 하나임을 나타냅니다. FALSE는 문서가 최신 파일 중 하나가 아님을 나타냅니다.

### <a name="return-value"></a>Return Value

*파일이 lpszPathName에*의해 명명된 문서에 대한 포인터입니다. 실패하면 NULL.

### <a name="remarks"></a>설명

*경로가 lpszPathName에*의해 지정된 파일을 엽니다. *lpszPathName이* NULL이면 이 템플릿과 연결된 형식의 문서가 포함된 새 파일이 만들어집니다.

## <a name="cdoctemplateremovedocument"></a><a name="removedocument"></a>CDoc 템플릿::제거문서

이 템플릿과 연결된 문서 목록에서 *pDoc이* 가리키는 문서를 제거합니다.

```
virtual void RemoveDocument(CDocument* pDoc);
```

### <a name="parameters"></a>매개 변수

*pDoc*<br/>
제거할 문서에 대한 포인터입니다.

### <a name="remarks"></a>설명

파생된 `CMultiDocTemplate` 클래스와 `CSingleDocTemplate` 이 함수를 재정의합니다. 에서 `CDocTemplate`고유한 문서 템플릿 클래스를 파생하는 경우 파생 클래스는 이 함수를 재정의해야 합니다.

## <a name="cdoctemplatesaveallmodified"></a><a name="saveallmodified"></a>CDoc 템플릿::SaveAll수정

수정된 모든 문서를 저장합니다.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아닌 경우; 그렇지 않으면 0.

## <a name="cdoctemplatesetcontainerinfo"></a><a name="setcontainerinfo"></a>CDoc 템플릿::세트 컨테이너정보

내부 OLE 항목을 편집할 때 OLE 컨테이너에 대한 리소스를 결정합니다.

```cpp
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```

### <a name="parameters"></a>매개 변수

*니돌인플레이스컨테이너*<br/>
포함된 개체가 활성화될 때 사용되는 리소스의 ID입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 OLE 개체가 활성화되어 있을 때 사용할 리소스를 설정합니다. 이러한 리소스에는 메뉴 및 가속기 테이블이 포함될 수 있습니다. 이 함수는 일반적으로 응용 프로그램의 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 함수에서 호출됩니다.

*nIDOleInPlaceContainer와* 연관된 메뉴에는 활성화된 내/ 항목의 메뉴가 컨테이너 응용 프로그램의 메뉴와 병합될 수 있는 구분 기호가 포함되어 있습니다. 서버 및 컨테이너 메뉴 병합에 대한 자세한 내용은 [OLE(메뉴 및 리소스)](../../mfc/menus-and-resources-ole.md)문서를 참조하십시오.

## <a name="cdoctemplatesetdefaulttitle"></a><a name="setdefaulttitle"></a>CDoc 템플릿:설정기본 제목

이 함수를 호출하여 문서의 기본 제목을 로드하고 문서의 제목 표시줄에 표시합니다.

```
virtual void SetDefaultTitle(CDocument* pDocument) = 0;
```

### <a name="parameters"></a>매개 변수

*p문서*<br/>
제목을 설정할 문서에 대한 포인터입니다.

### <a name="remarks"></a>설명

기본 제목에 대한 자세한 내용은 `CDocTemplate::docName` [CDocTemplate::GetDocString](#getdocstring)의 설명을 참조하십시오.

## <a name="cdoctemplatesetserverinfo"></a><a name="setserverinfo"></a>CDoc 템플릿::세트 서버정보

서버 문서가 포함되거나 편집될 때 리소스 및 클래스를 결정합니다.

```cpp
void SetServerInfo(
    UINT nIDOleEmbedding,
    UINT nIDOleInPlaceServer = 0,
    CRuntimeClass* pOleFrameClass = NULL,
    CRuntimeClass* pOleViewClass = NULL);
```

### <a name="parameters"></a>매개 변수

*니돌엠베딩*<br/>
포함된 개체가 별도의 창에서 열릴 때 사용되는 리소스의 ID입니다.

*니돌인플레이스서버*<br/>
포함된 개체가 제자리에서 활성화될 때 사용되는 리소스의 ID입니다.

*폴프레임 클래스*<br/>
내부 활성화가 발생할 때 생성된 프레임 창 개체에 대한 클래스 정보를 포함하는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조에 대한 포인터입니다.

*폴뷰클래스*<br/>
내부 활성화가 `CRuntimeClass` 발생할 때 생성된 뷰 개체에 대한 클래스 정보가 포함된 구조체에 대한 포인터입니다.

### <a name="remarks"></a>설명

사용자가 포함된 개체의 활성화를 요청할 때 서버 응용 프로그램에서 사용할 리소스를 식별하려면 이 멤버 함수를 호출합니다. 이러한 리소스는 메뉴 와 가속기 테이블로 구성됩니다. 이 함수는 일반적으로 `InitInstance` 응용 프로그램에서 호출됩니다.

*nIDOleInPlaceServer와* 연관된 메뉴에는 서버 메뉴가 컨테이너 메뉴와 병합될 수 있는 구분 기호가 포함되어 있습니다. 서버 및 컨테이너 메뉴 병합에 대한 자세한 내용은 [OLE(메뉴 및 리소스)](../../mfc/menus-and-resources-ole.md)문서를 참조하십시오.

## <a name="cdoctemplatecreatepreviewframe"></a><a name="createpreviewframe"></a>CDoc 템플릿::미리 보기 만들기프레임 만들기

[리치 미리 보기]에 사용되는 하위 프레임을 만듭니다.

```
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,
    CDocument* pDoc);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
부모 창에 대한 포인터(일반적으로 Shell에서 제공).

*pDoc*<br/>
내용을 미리 볼 문서 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

개체에 대한 `CFrameWnd` 유효한 포인터 또는 생성이 실패할 경우 NULL입니다.

### <a name="remarks"></a>설명

## <a name="cdoctemplatesetpreviewinfo"></a><a name="setpreviewinfo"></a>CDoc 템플릿::세트 미리보기정보

프로세스 에서 미리 보기 처리기를 설정합니다.

```cpp
void SetPreviewInfo(
    UINT nIDPreviewFrame,
    CRuntimeClass* pPreviewFrameClass = NULL,
    CRuntimeClass* pPreviewViewClass = NULL);
```

### <a name="parameters"></a>매개 변수

*nID 프리뷰프레임*<br/>
미리 보기 프레임의 리소스 ID를 지정합니다.

*p미리보기프레임클래스*<br/>
미리 보기 프레임의 런타임 클래스 정보 구조에 대한 포인터를 지정합니다.

*p미리보기뷰클래스*<br/>
미리 보기보기의 런타임 클래스 정보 구조에 대한 포인터를 지정합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CSingleDocTemplate 클래스](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CMultiDocTemplate 클래스](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[C문서 클래스](../../mfc/reference/cdocument-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[C스크롤뷰 클래스](../../mfc/reference/cscrollview-class.md)<br/>
[CEditView 클래스](../../mfc/reference/ceditview-class.md)<br/>
[CFormView 클래스](../../mfc/reference/cformview-class.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[CMDI차일드 클래스](../../mfc/reference/cmdichildwnd-class.md)
