---
title: COleDocument 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDocument
- AFXOLE/COleDocument
- AFXOLE/COleDocument::COleDocument
- AFXOLE/COleDocument::AddItem
- AFXOLE/COleDocument::ApplyPrintDevice
- AFXOLE/COleDocument::EnableCompoundFile
- AFXOLE/COleDocument::GetInPlaceActiveItem
- AFXOLE/COleDocument::GetNextClientItem
- AFXOLE/COleDocument::GetNextItem
- AFXOLE/COleDocument::GetNextServerItem
- AFXOLE/COleDocument::GetPrimarySelectedItem
- AFXOLE/COleDocument::GetStartPosition
- AFXOLE/COleDocument::HasBlankItems
- AFXOLE/COleDocument::OnShowViews
- AFXOLE/COleDocument::RemoveItem
- AFXOLE/COleDocument::UpdateModifiedFlag
- AFXOLE/COleDocument::OnEditChangeIcon
- AFXOLE/COleDocument::OnEditConvert
- AFXOLE/COleDocument::OnEditLinks
- AFXOLE/COleDocument::OnFileSendMail
- AFXOLE/COleDocument::OnUpdateEditChangeIcon
- AFXOLE/COleDocument::OnUpdateEditLinksMenu
- AFXOLE/COleDocument::OnUpdateObjectVerbMenu
- AFXOLE/COleDocument::OnUpdatePasteLinkMenu
- AFXOLE/COleDocument::OnUpdatePasteMenu
helpviewer_keywords:
- COleDocument [MFC], COleDocument
- COleDocument [MFC], AddItem
- COleDocument [MFC], ApplyPrintDevice
- COleDocument [MFC], EnableCompoundFile
- COleDocument [MFC], GetInPlaceActiveItem
- COleDocument [MFC], GetNextClientItem
- COleDocument [MFC], GetNextItem
- COleDocument [MFC], GetNextServerItem
- COleDocument [MFC], GetPrimarySelectedItem
- COleDocument [MFC], GetStartPosition
- COleDocument [MFC], HasBlankItems
- COleDocument [MFC], OnShowViews
- COleDocument [MFC], RemoveItem
- COleDocument [MFC], UpdateModifiedFlag
- COleDocument [MFC], OnEditChangeIcon
- COleDocument [MFC], OnEditConvert
- COleDocument [MFC], OnEditLinks
- COleDocument [MFC], OnFileSendMail
- COleDocument [MFC], OnUpdateEditChangeIcon
- COleDocument [MFC], OnUpdateEditLinksMenu
- COleDocument [MFC], OnUpdateObjectVerbMenu
- COleDocument [MFC], OnUpdatePasteLinkMenu
- COleDocument [MFC], OnUpdatePasteMenu
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
ms.openlocfilehash: b92c796fdaa972966dcbfa85b1e34f267b6c629c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78867016"
---
# <a name="coledocument-class"></a>COleDocument 클래스

비주얼 편집을 지원하는 OLE 문서에 대한 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class COleDocument : public CDocument
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|name|설명|
|----------|-----------------|
|[COleDocument::COleDocument](#coledocument)|`COleDocument` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|name|설명|
|----------|-----------------|
|[COleDocument::AddItem](#additem)|문서에서 유지 관리 하는 항목 목록에 항목을 추가 합니다.|
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|문서의 모든 클라이언트 항목에 대 한 인쇄 대상 장치를 설정 합니다.|
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|OLE 구조적 저장소 파일 형식을 사용 하 여 문서를 저장 합니다.|
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|현재 내부 활성 상태인 OLE 항목을 반환 합니다.|
|[COleDocument::GetNextClientItem](#getnextclientitem)|반복을 위한 다음 클라이언트 항목을 가져옵니다.|
|[COleDocument::GetNextItem](#getnextitem)|반복을 위한 다음 문서 항목을 가져옵니다.|
|[COleDocument::GetNextServerItem](#getnextserveritem)|반복을 위한 다음 서버 항목을 가져옵니다.|
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|문서에서 선택한 기본 OLE 항목을 반환 합니다.|
|[COleDocument::GetStartPosition](#getstartposition)|반복을 시작할 초기 위치를 가져옵니다.|
|[COleDocument::HasBlankItems](#hasblankitems)|문서의 빈 항목을 확인 합니다.|
|[COleDocument::OnShowViews](#onshowviews)|문서를 표시 하거나 숨길 때 호출 됩니다.|
|[COleDocument::RemoveItem](#removeitem)|문서에 의해 유지 관리 되는 항목 목록에서 항목을 제거 합니다.|
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|포함 된 OLE 항목이 수정 된 경우 문서를 수정 된 것으로 표시 합니다.|

### <a name="protected-methods"></a>보호된 메서드

|name|설명|
|----------|-----------------|
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|아이콘 변경 메뉴 명령에서 이벤트를 처리 합니다.|
|[COleDocument::OnEditConvert](#oneditconvert)|포함 된 개체 또는 연결 된 개체를 한 형식에서 다른 형식으로 변환 하는 과정을 처리 합니다.|
|[COleDocument::OnEditLinks](#oneditlinks)|편집 메뉴의 링크 명령에서 이벤트를 처리 합니다.|
|[COleDocument::OnFileSendMail](#onfilesendmail)|첨부 된 문서가 있는 메일 메시지를 보냅니다.|
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|편집/변경 아이콘 메뉴 옵션에 대 한 명령 UI를 업데이트 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|편집/링크 메뉴 옵션에 대 한 명령 UI를 업데이트 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|편집/ *objectname* 메뉴 옵션 및 편집/ *objectname*에서 액세스 하는 동사 하위 메뉴에 대 한 명령 UI를 업데이트 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|특수 메뉴 붙여넣기 옵션에 대 한 명령 UI를 업데이트 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|붙여넣기 메뉴 옵션에 대 한 명령 UI를 업데이트 하기 위해 프레임 워크에서 호출 됩니다.|

## <a name="remarks"></a>설명

`COleDocument`는 OLE 응용 프로그램이 MFC 라이브러리에서 제공 하는 문서/뷰 아키텍처를 사용할 수 있도록 하는 `CDocument`에서 파생 됩니다.

`COleDocument`은 문서를 [Cdocitem](../../mfc/reference/cdocitem-class.md) 개체의 컬렉션으로 처리 하 여 OLE 항목을 처리 합니다. 컨테이너와 서버 응용 프로그램 모두에는 해당 문서에 OLE 항목이 포함 될 수 있어야 하므로 이러한 아키텍처가 필요 합니다. [에서 파생된 ](../../mfc/reference/coleserveritem-class.md)COleServerItem[ 및 ](../../mfc/reference/coleclientitem-class.md)COleClientItem`CDocItem` 클래스는 응용 프로그램과 OLE 항목 간의 상호 작용을 관리합니다.

간단한 컨테이너 응용 프로그램을 작성 하는 경우 `COleDocument`에서 문서 클래스를 파생 시킵니다. 문서에 포함 된 포함 된 항목에 대 한 링크를 지 원하는 컨테이너 응용 프로그램을 작성 하는 경우 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)에서 문서 클래스를 파생 시킵니다. 서버 응용 프로그램을 작성 하거나 컨테이너/서버를 조합 하는 경우 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)에서 문서 클래스를 파생 시킵니다. `COleLinkingDoc` 및 `COleServerDoc`는 `COleDocument`에서 파생 되므로 이러한 클래스는 `COleDocument` 및 `CDocument`에서 사용할 수 있는 모든 서비스를 상속 합니다.

`COleDocument`를 사용 하려면 클래스에서 클래스를 파생 시키고 응용 프로그램의 비 OLE 데이터 및 포함 되거나 연결 된 항목을 관리 하는 기능을 추가 합니다. 응용 프로그램의 네이티브 데이터를 저장 하는 `CDocItem`파생 클래스를 정의 하는 경우 `COleDocument`에서 정의한 기본 구현을 사용 하 여 OLE 및 비 OLE 데이터를 모두 저장할 수 있습니다. Ole 항목과는 별도로 비 OLE 데이터를 저장 하는 데이터 구조를 직접 디자인할 수도 있습니다. 자세한 내용은 [컨테이너: 복합 파일](../../mfc/containers-compound-files.md)(영문) 문서를 참조 하세요.

`CDocument`는 MAPI (메일 지원)가 있는 경우 전자 메일을 통해 문서를 보내는 것을 지원 합니다. `COleDocument`에서 복합 문서를 올바르게 처리 하도록 [Onfilesendmail](#onfilesendmail) 을 업데이트 했습니다. 자세한 내용은 MFC의 [mapi](../../mfc/mapi.md) 및 [mapi 지원](../../mfc/mapi-support-in-mfc.md)문서를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>요구 사항

**헤더:** afxole

##  <a name="additem"></a>  COleDocument::AddItem

문서에 항목을 추가 하려면이 함수를 호출 합니다.

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
추가 되는 문서 항목에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`COleClientItem` 또는 문서에 대 한 포인터를 수락 하는 `COleServerItem` 생성자에 의해 호출 될 때이 함수를 명시적으로 호출할 필요가 없습니다.

##  <a name="applyprintdevice"></a>  COleDocument::ApplyPrintDevice

응용 프로그램 컨테이너 문서의 포함 된 모든 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 항목에 대 한 인쇄 대상 장치를 변경 하려면이 함수를 호출 합니다.

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>매개 변수

*ptd*<br/>
새 인쇄 대상 장치에 대 한 정보를 포함 하는 `DVTARGETDEVICE` 데이터 구조에 대 한 포인터입니다. NULL일 수 있습니다.

*ppd*<br/>
새 인쇄 대상 장치에 대 한 정보를 포함 하는 `PRINTDLG` 데이터 구조에 대 한 포인터입니다. NULL일 수 있습니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 0이 아닌 값입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 모든 항목에 대 한 인쇄 대상 장치를 업데이트 하지만 해당 항목에 대해 프레젠테이션 캐시를 새로 고치지 않습니다. 항목에 대 한 프레젠테이션 캐시를 업데이트 하려면 [COleClientItem:: UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)를 호출 합니다.

이 함수에 대 한 인수는 OLE에서 대상 장치를 식별 하는 데 사용 하는 정보를 포함 합니다. [Printdlg](/windows/win32/api/commdlg/ns-commdlg-printdlga) 구조체는 Windows에서 일반 인쇄 대화 상자를 초기화 하는 데 사용 하는 정보를 포함 합니다. 사용자가 대화 상자를 닫은 후에는이 구조에서 사용자의 선택 항목에 대 한 정보를 반환 합니다. [CPrintDialog](../../mfc/reference/cprintdialog-class.md) 개체의 `m_pd` 멤버는 `PRINTDLG` 구조체입니다.

자세한 내용은 Windows SDK에서 [Printdlg](/windows/win32/api/commdlg/ns-commdlg-printdlga) 구조체를 참조 하세요.

자세한 내용은 Windows SDK [DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) 구조체를 참조 하세요.

##  <a name="coledocument"></a>  COleDocument::COleDocument

`COleDocument` 개체를 생성합니다.

```
COleDocument();
```

##  <a name="enablecompoundfile"></a>  COleDocument::EnableCompoundFile

복합 파일 형식을 사용 하 여 문서를 저장 하려는 경우이 함수를 호출 합니다.

```
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
복합 파일 지원을 사용할 수 있는지 여부를 지정 합니다.

### <a name="remarks"></a>설명

이를 구조적 저장소 라고도 합니다. 일반적으로 `COleDocument`파생 클래스의 생성자에서이 함수를 호출 합니다. 복합 문서에 대 한 자세한 내용은 [컨테이너: 복합 파일](../../mfc/containers-compound-files.md)(영문) 문서를 참조 하세요.

이 멤버 함수를 호출 하지 않으면 문서가 nonstructured ("플랫") 파일 형식으로 저장 됩니다.

문서에 대해 복합 파일 지원을 사용 하거나 사용 하지 않도록 설정한 후에는 문서 수명 동안 설정을 변경 하면 안 됩니다.

##  <a name="getinplaceactiveitem"></a>  COleDocument::GetInPlaceActiveItem

*PWnd*로 식별 된 뷰가 포함 된 프레임 창에서 현재 활성화 된 OLE 항목을 가져오려면이 함수를 호출 합니다.

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
컨테이너 문서를 표시 하는 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

단일 내부 활성 OLE 항목에 대 한 포인터입니다. 현재 "내부 활성" 상태인 OLE 항목이 없으면 NULL입니다.

##  <a name="getnextclientitem"></a>  COleDocument::GetNextClientItem

문서의 각 클라이언트 항목에 액세스 하려면이 함수를 반복적으로 호출 합니다.

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
`GetNextClientItem`에 대 한 이전 호출로 설정 된 위치 값에 대 한 참조입니다. 초기 값은 `GetStartPosition` 멤버 함수에 의해 반환 됩니다.

### <a name="return-value"></a>반환 값

문서의 다음 클라이언트 항목에 대 한 포인터 이거나, 더 이상 클라이언트 항목이 없으면 NULL입니다.

### <a name="remarks"></a>설명

각 호출 후 *pos* 의 값은 문서에서 다음 항목에 대해 설정 됩니다 .이 항목은 클라이언트 항목이 될 수도 있고 그렇지 않을 수도 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

##  <a name="getnextitem"></a>  COleDocument::GetNextItem

문서의 각 항목에 액세스 하려면이 함수를 반복적으로 호출 합니다.

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
`GetNextItem`에 대 한 이전 호출로 설정 된 위치 값에 대 한 참조입니다. 초기 값은 `GetStartPosition` 멤버 함수에 의해 반환 됩니다.

### <a name="return-value"></a>반환 값

지정 된 위치에 있는 문서 항목에 대 한 포인터입니다.

### <a name="remarks"></a>설명

각 호출 후 *pos* 의 값은 문서에서 다음 항목의 위치 값으로 설정 됩니다. 검색 된 요소가 문서의 마지막 요소 이면 *pos* 의 새 값은 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

##  <a name="getnextserveritem"></a>  COleDocument::GetNextServerItem

문서의 각 서버 항목에 액세스 하려면이 함수를 반복적으로 호출 합니다.

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
`GetNextServerItem`에 대 한 이전 호출로 설정 된 위치 값에 대 한 참조입니다. 초기 값은 `GetStartPosition` 멤버 함수에 의해 반환 됩니다.

### <a name="return-value"></a>반환 값

문서의 다음 서버 항목에 대 한 포인터 이거나, 더 이상 서버 항목이 없으면 NULL입니다.

### <a name="remarks"></a>설명

각 호출 후 *pos* 의 값은 문서에서 다음 항목에 대해 설정 됩니다 .이 항목은 서버 항목이 될 수도 있고 그렇지 않을 수도 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

##  <a name="getprimaryselecteditem"></a>  COleDocument::GetPrimarySelectedItem

지정 된 뷰에서 현재 선택 된 OLE 항목을 검색 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>매개 변수

*pView*<br/>
문서를 표시 하는 활성 뷰 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

선택한 단일 OLE 항목에 대 한 포인터입니다. 선택 된 OLE 항목이 없거나 둘 이상의를 선택한 경우 NULL입니다.

### <a name="remarks"></a>설명

기본 구현에서는 포함 된 OLE 항목 목록을 검색 하 여 선택한 단일 항목을 검색 하 고이에 대 한 포인터를 반환 합니다. 선택 된 항목이 없거나 둘 이상의 항목을 선택 하는 경우이 함수는 NULL을 반환 합니다. 이 함수가 작동 하려면 view 클래스에서 `CView::IsSelected` 멤버 함수를 재정의 해야 합니다. 포함 된 OLE 항목을 저장 하는 고유한 메서드가 있는 경우이 함수를 재정의 합니다.

##  <a name="getstartposition"></a>  COleDocument::GetStartPosition

문서에서 첫 번째 항목의 위치를 가져오려면이 함수를 호출 합니다.

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>반환 값

문서 항목의 반복을 시작 하는 데 사용할 수 있는 위치 값입니다. 문서에 항목이 없으면 NULL입니다.

### <a name="remarks"></a>설명

`GetNextItem`, `GetNextClientItem`또는 `GetNextServerItem`에 반환 된 값을 전달 합니다.

##  <a name="hasblankitems"></a>  COleDocument::HasBlankItems

문서에 빈 항목이 포함 되어 있는지 여부를 확인 하려면이 함수를 호출 합니다.

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>반환 값

문서에 빈 항목이 포함 되어 있으면 0이 아닌 값입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

빈 항목은 사각형이 비어 있는 항목입니다.

##  <a name="oneditchangeicon"></a>  COleDocument::OnEditChangeIcon

OLE 아이콘 변경 대화 상자를 표시 하 고 현재 선택한 OLE 항목을 나타내는 아이콘을 사용자가 대화 상자에서 선택 하는 아이콘으로 변경 합니다.

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>설명

`OnEditChangeIcon` `COleChangeIconDialog` 아이콘 변경 대화 상자를 만들고 시작 합니다.

##  <a name="oneditconvert"></a>  COleDocument::OnEditConvert

OLE 변환 대화 상자를 표시 하 고 대화 상자에서 사용자가 선택한 항목에 따라 현재 선택한 OLE 항목을 변환 하거나 활성화 합니다.

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>설명

`OnEditConvert` `COleConvertDialog` 변환 대화 상자를 만들고 시작 합니다.

변환의 예는 Microsoft Word 문서를 워드 패드 문서로 변환 하는 것입니다.

##  <a name="oneditlinks"></a>  COleDocument::OnEditLinks

OLE 편집/링크 대화 상자를 표시 합니다.

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>설명

`OnEditLinks` 사용자가 연결 된 개체를 변경할 수 있는 `COleLinksDialog` 링크 대화 상자를 만들고 시작 합니다.

##  <a name="onfilesendmail"></a>  COleDocument::OnFileSendMail

문서를 첨부 파일로 사용 하 여 상주 메일 호스트 (있는 경우)를 통해 메시지를 보냅니다.

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>설명

`OnFileSendMail`은 `OnSaveDocument` 호출 하 여 제목이 없는 문서와 수정 된 문서를 임시 파일로 serialize (저장) 한 다음 전자 메일을 통해 보냅니다. 문서가 수정 되지 않은 경우에는 임시 파일이 필요 하지 않습니다. 원본이 전송 됩니다. `OnFileSendMail` MAPI32.DLL를 로드 합니다. DLL이 아직 로드 되지 않은 경우 DLL입니다.

`CDocument`에 대 한 `OnFileSendMail` 구현과 달리이 함수는 복합 파일을 올바르게 처리 합니다.

자세한 내용은 [Mapi 토픽](../../mfc/mapi.md) 및 [MFC의 mapi 지원](../../mfc/mapi-support-in-mfc.md) 문서를 참조 하세요.

##  <a name="onshowviews"></a>  COleDocument::OnShowViews

프레임 워크는 문서 표시 상태가 변경 된 후이 함수를 호출 합니다.

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>매개 변수

*bVisible*<br/>
문서를 표시 하거나 숨길 수 있는지 여부를 나타냅니다.

### <a name="remarks"></a>설명

이 함수의 기본 버전은 아무 작업도 수행 하지 않습니다. 문서 표시 유형이 변경 될 때 응용 프로그램에서 특별 한 처리를 수행 해야 하는 경우이를 재정의 합니다.

##  <a name="onupdateeditchangeicon"></a>  COleDocument::OnUpdateEditChangeIcon

편집 메뉴의 아이콘 변경 명령을 업데이트 하기 위해 프레임 워크에서 호출 됩니다.

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
업데이트 명령을 생성 한 메뉴를 나타내는 `CCmdUI` 구조체에 대 한 포인터입니다. 업데이트 처리기는 *pCmdUI* 를 통해 `CCmdUI` 구조의 `Enable` 멤버 함수를 호출 하 여 사용자 인터페이스를 업데이트 합니다.

### <a name="remarks"></a>설명

`OnUpdateEditChangeIcon`는 유효한 아이콘이 문서에 있는지 여부에 따라 명령의 사용자 인터페이스를 업데이트 합니다. 이 함수를 재정의 하 여 동작을 변경 합니다.

##  <a name="onupdateeditlinksmenu"></a>  COleDocument::OnUpdateEditLinksMenu

편집 메뉴에서 링크 명령을 업데이트 하기 위해 프레임 워크에서 호출 됩니다.

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
업데이트 명령을 생성 한 메뉴를 나타내는 `CCmdUI` 구조체에 대 한 포인터입니다. 업데이트 처리기는 *pCmdUI* 를 통해 `CCmdUI` 구조의 `Enable` 멤버 함수를 호출 하 여 사용자 인터페이스를 업데이트 합니다.

### <a name="remarks"></a>설명

`OnUpdateEditLinksMenu` 문서의 첫 번째 OLE 항목부터 시작 하 여 각 항목에 액세스 하 고, 항목이 링크 인지 여부를 테스트 하 고, 링크 인 경우 링크 명령을 사용 하도록 설정 합니다. 이 함수를 재정의 하 여 동작을 변경 합니다.

##  <a name="onupdateobjectverbmenu"></a>  COleDocument::OnUpdateObjectVerbMenu

편집 메뉴에서 *objectname* 명령을 업데이트 하기 위해 프레임 워크에서 호출 하 고 *objectname* 명령에서 액세스 하는 동사 하위 메뉴를 업데이트 합니다. 여기서 *objectname* 은 문서에 포함 된 OLE 개체의 이름입니다.

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
업데이트 명령을 생성 한 메뉴를 나타내는 `CCmdUI` 구조체에 대 한 포인터입니다. 업데이트 처리기는 *pCmdUI* 를 통해 `CCmdUI` 구조의 `Enable` 멤버 함수를 호출 하 여 사용자 인터페이스를 업데이트 합니다.

### <a name="remarks"></a>설명

`OnUpdateObjectVerbMenu`는 유효한 개체가 문서에 있는지 여부에 따라 *ObjectName* 명령의 사용자 인터페이스를 업데이트 합니다. 개체가 있으면 편집 메뉴의 *ObjectName* 명령이 사용 됩니다. 이 메뉴 명령을 선택 하면 동사 하위 메뉴가 표시 됩니다. 동사 하위 메뉴에는 편집, 속성 등의 개체에 사용할 수 있는 모든 동사 명령이 들어 있습니다. 이 함수를 재정의 하 여 동작을 변경 합니다.

##  <a name="onupdatepastelinkmenu"></a>  COleDocument::OnUpdatePasteLinkMenu

연결 된 OLE 항목을 클립보드에서 붙여 넣을 수 있는지 여부를 확인 하기 위해 프레임 워크에서 호출 됩니다.

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
업데이트 명령을 생성 한 메뉴를 나타내는 `CCmdUI` 구조체에 대 한 포인터입니다. 업데이트 처리기는 *pCmdUI* 를 통해 `CCmdUI` 구조의 `Enable` 멤버 함수를 호출 하 여 사용자 인터페이스를 업데이트 합니다.

### <a name="remarks"></a>설명

항목을 문서에 붙여 넣을 수 있는지 여부에 따라 특수 메뉴 붙여넣기 명령을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

##  <a name="onupdatepastemenu"></a>  COleDocument::OnUpdatePasteMenu

포함 된 OLE 항목을 클립보드에서 붙여 넣을 수 있는지 여부를 확인 하기 위해 프레임 워크에서 호출 됩니다.

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
업데이트 명령을 생성 한 메뉴를 나타내는 `CCmdUI` 구조체에 대 한 포인터입니다. 업데이트 처리기는 *pCmdUI* 를 통해 `CCmdUI` 구조의 `Enable` 멤버 함수를 호출 하 여 사용자 인터페이스를 업데이트 합니다.

### <a name="remarks"></a>설명

항목을 문서에 붙여 넣을 수 있는지 여부에 따라 붙여넣기 메뉴 명령 및 단추를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

##  <a name="removeitem"></a>  COleDocument::RemoveItem

문서에서 항목을 제거 하려면이 함수를 호출 합니다.

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
제거할 문서 항목에 대 한 포인터입니다.

### <a name="remarks"></a>설명

일반적으로이 함수는 명시적으로 호출할 필요가 없습니다. `COleClientItem` 및 `COleServerItem`에 대 한 소멸자에서 호출 됩니다.

##  <a name="updatemodifiedflag"></a>  COleDocument::UpdateModifiedFlag

포함 된 OLE 항목이 수정 된 경우 문서를 수정 된 것으로 표시 하려면이 함수를 호출 합니다.

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>설명

이를 통해 프레임 워크는 문서의 네이티브 데이터가 수정 되지 않았더라도 문서를 닫기 전에 저장할 것인지를 사용자에 게 표시할 수 있습니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 컨테이너](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[CDocument 클래스](../../mfc/reference/cdocument-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
