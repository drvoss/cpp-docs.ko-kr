---
title: 콜레문서 클래스
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
ms.openlocfilehash: 1500035cb8be3036678090918154829aace48d2f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753866"
---
# <a name="coledocument-class"></a>콜레문서 클래스

비주얼 편집을 지원하는 OLE 문서에 대한 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class COleDocument : public CDocument
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COleDocument::COleDocument](#coledocument)|`COleDocument` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[콜레문서::추가 항목](#additem)|문서에서 유지 관리하는 항목 목록에 항목을 추가합니다.|
|[콜레문서::인쇄적용장치](#applyprintdevice)|문서의 모든 클라이언트 항목에 대한 인쇄 대상 장치를 설정합니다.|
|[COle문서::인에이블컴파일](#enablecompoundfile)|OLE 구조화 저장소 파일 형식을 사용하여 문서를 저장하도록 합니다.|
|[콜레문서::겟인플레이스액티브아이템](#getinplaceactiveitem)|현재 활성 상태인 OLE 항목을 반환합니다.|
|[COle문서::GetNext클라이언트항목](#getnextclientitem)|반복을 위한 다음 클라이언트 항목을 가져옵니다.|
|[COleDocument::GetNextItem](#getnextitem)|반복을 위한 다음 문서 항목을 가져옵니다.|
|[COleDocument::GetNextServerItem](#getnextserveritem)|반복을 위한 다음 서버 항목을 가져옵니다.|
|[콜레문서::GetPrimary선택항목](#getprimaryselecteditem)|문서에서 선택한 기본 OLE 항목을 반환합니다.|
|[COleDocument::GetStartPosition](#getstartposition)|반복을 시작할 초기 위치를 가져옵니다.|
|[COleDocument::HasBlankItems](#hasblankitems)|문서의 빈 항목을 확인합니다.|
|[콜레문서::온쇼뷰](#onshowviews)|문서가 표시되거나 보이지 않게 될 때 호출됩니다.|
|[콜레문서::제거항목](#removeitem)|문서에서 유지 관리하는 항목 목록에서 항목을 제거합니다.|
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|포함된 OLE 항목중 어느 것이라도 수정된 경우 문서를 수정된 것으로 표시합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[COle문서::온편집 변경 아이콘](#oneditchangeicon)|아이콘 변경 메뉴 명령에서 이벤트를 처리합니다.|
|[COleDocument::OnEditConvert](#oneditconvert)|포함된 개체 또는 연결된 개체를 한 형식에서 다른 유형으로 변환하는 것을 처리합니다.|
|[콜레문서::온에더티링크](#oneditlinks)|편집 메뉴의 링크 명령에서 이벤트를 처리합니다.|
|[콜레문서::온파일센드메일](#onfilesendmail)|문서가 첨부된 메일 메시지를 보냅니다.|
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|편집/아이콘 변경 메뉴 옵션에 대 한 명령 UI를 업데이트 하는 프레임 워크에 의해 호출 됩니다.|
|[콜레 문서::업데이트 된편집 링크메뉴](#onupdateeditlinksmenu)|편집/링크 메뉴 옵션에 대 한 명령 UI를 업데이트 하는 프레임 워크에 의해 호출 됩니다.|
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|편집 / ObjectName 메뉴 옵션및 편집 / *ObjectName에서* 액세스 한 동사 하위 메뉴에 대한 명령 UI를 업데이트하기 위해 프레임 워크에 의해 호출됩니다 . *ObjectName*|
|[콜레 문서::온업데이트붙여넣기링크메뉴](#onupdatepastelinkmenu)|붙여 넣기 특수 메뉴 옵션에 대 한 명령 UI를 업데이트 하는 프레임 워크에 의해 호출 됩니다.|
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|붙여 넣기 메뉴 옵션에 대 한 명령 UI를 업데이트 하는 프레임 워크에 의해 호출 됩니다.|

## <a name="remarks"></a>설명

`COleDocument`OLE 응용 `CDocument`프로그램에서 Microsoft Foundation 클래스 라이브러리에서 제공하는 문서/보기 아키텍처를 사용할 수 있는 에서 파생됩니다.

`COleDocument`문서를 Ole 항목을 처리하는 [CDocItem](../../mfc/reference/cdocitem-class.md) 개체의 컬렉션으로 처리합니다. 컨테이너 응용 프로그램과 서버 응용 프로그램 모두 문서에 OLE 항목을 포함할 수 있어야 하기 때문에 이러한 아키텍처가 필요합니다. `CDocItem`에서 파생된 [COleServerItem](../../mfc/reference/coleserveritem-class.md) 및 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 클래스는 응용 프로그램과 OLE 항목 간의 상호 작용을 관리합니다.

간단한 컨테이너 응용 프로그램을 작성하는 경우 에서 `COleDocument`문서 클래스를 파생합니다. 해당 문서에 포함된 포함된 포함된 항목에 대한 연결을 지원하는 컨테이너 응용 프로그램을 작성하는 경우 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)에서 문서 클래스를 파생합니다. 서버 응용 프로그램 또는 조합 컨테이너/서버를 작성하는 경우 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)에서 문서 클래스를 파생합니다. `COleLinkingDoc`및 `COleServerDoc` `COleDocument`에서 파생되므로 이러한 클래스는 에서 `COleDocument` 사용할 `CDocument`수 있는 모든 서비스를 상속합니다.

을 `COleDocument`사용하려면 클래스를 파생시키고 응용 프로그램의 비 OLE 데이터뿐만 아니라 임베디드 또는 링크된 항목을 관리하는 기능을 추가합니다. 응용 프로그램의 `CDocItem`기본 데이터를 저장하기 위해 파생 클래스를 정의하는 경우 OLE `COleDocument` 및 비OLE 데이터를 모두 저장하기 위해 정의된 기본 구현을 사용할 수 있습니다. OLE 항목과 별도로 비 OLE 데이터를 저장하기 위한 고유한 데이터 구조를 디자인할 수도 있습니다. 자세한 내용은 문서 [컨테이너: 복합 파일을](../../mfc/containers-compound-files.md)참조하세요.

`CDocument`메일 지원(MAPI)이 있는 경우 우편으로 문서를 전송할 수 있습니다. `COleDocument`복합 문서를 올바르게 처리하기 위해 [OnFileSendMail을](#onfilesendmail) 업데이트했습니다. 자세한 내용은 [MFC의](../../mfc/mapi-support-in-mfc.md) [MAPI](../../mfc/mapi.md) 및 MAPI 지원 문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="coledocumentadditem"></a><a name="additem"></a>콜레문서::추가 항목

이 함수를 호출하여 문서에 항목을 추가합니다.

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
추가되는 문서 항목에 대한 포인터입니다.

### <a name="remarks"></a>설명

문서에 대한 포인터를 허용하는 `COleClientItem` 생성자 또는 `COleServerItem` 생성자가 호출할 때 이 함수를 명시적으로 호출할 필요가 없습니다.

## <a name="coledocumentapplyprintdevice"></a><a name="applyprintdevice"></a>콜레문서::인쇄적용장치

이 함수를 호출하여 응용 프로그램의 컨테이너 문서에 포함된 모든 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 항목에 대한 인쇄 대상 장치를 변경합니다.

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>매개 변수

*ptd*<br/>
새 인쇄 `DVTARGETDEVICE` 대상 장치에 대한 정보가 포함된 데이터 구조에 대한 포인터입니다. NULL일 수 있습니다.

*ppd*<br/>
새 인쇄 `PRINTDLG` 대상 장치에 대한 정보가 포함된 데이터 구조에 대한 포인터입니다. NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

함수가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 모든 항목에 대한 인쇄 대상 장치를 업데이트하지만 해당 항목에 대한 프레젠테이션 캐시를 새로 고치지는 않습니다. 항목에 대한 프레젠테이션 캐시를 업데이트하려면 [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)를 호출합니다.

이 함수에 대한 인수에는 OLE가 대상 장치를 식별하는 데 사용하는 정보가 포함되어 있습니다. [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) 구조에는 Windows에서 일반적인 인쇄 대화 상자를 초기화하는 데 사용하는 정보가 포함되어 있습니다. 사용자가 대화 상자를 닫은 후 Windows는 이 구조에서 사용자의 선택에 대한 정보를 반환합니다. [CPrintDialog](../../mfc/reference/cprintdialog-class.md) 개체의 `m_pd` 멤버는 `PRINTDLG` 구조체입니다.

자세한 내용은 Windows SDK의 [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) 구조를 참조하십시오.

자세한 내용은 Windows SDK의 [DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) 구조를 참조하십시오.

## <a name="coledocumentcoledocument"></a><a name="coledocument"></a>콜레 문서::콜레문서

`COleDocument` 개체를 생성합니다.

```
COleDocument();
```

## <a name="coledocumentenablecompoundfile"></a><a name="enablecompoundfile"></a>COle문서::인에이블컴파일

복합 파일 형식을 사용하여 문서를 저장하려면 이 함수를 호출합니다.

```cpp
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
복합 파일 지원이 활성화되어 있는지 또는 사용할 수 있는지 여부를 지정합니다.

### <a name="remarks"></a>설명

이를 구조화 된 저장소라고도 합니다. 일반적으로 -derived 클래스의 생성자에서이 함수를 호출 합니다. `COleDocument` 복합 문서에 대한 자세한 내용은 [컨테이너: 복합 파일](../../mfc/containers-compound-files.md)문서를 참조하십시오.

이 멤버 함수를 호출하지 않으면 문서는 구조화되지 않은("플랫") 파일 형식으로 저장됩니다.

문서에 대해 복합 파일 지원을 사용하도록 설정하거나 비활성화한 후에는 문서의 수명 동안 설정을 변경하지 않아야 합니다.

## <a name="coledocumentgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>콜레문서::겟인플레이스액티브아이템

*pWnd로*식별된 뷰를 포함하는 프레임 창에서 현재 활성화된 OLE 항목을 얻으려면 이 함수를 호출합니다.

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
컨테이너 문서를 표시하는 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

단일, 현재 활성 OLE 항목에 대한 포인터; 현재 "현재 활성 상태" 상태에 있는 OLE 항목이 없는 경우 NULL입니다.

## <a name="coledocumentgetnextclientitem"></a><a name="getnextclientitem"></a>COle문서::GetNext클라이언트항목

이 함수를 반복적으로 호출하여 문서의 각 클라이언트 항목에 액세스합니다.

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
에 대한 이전 호출에 의해 설정된 `GetNextClientItem`POSITION 값에 대한 참조입니다. 초기 값은 멤버 `GetStartPosition` 함수에서 반환됩니다.

### <a name="return-value"></a>Return Value

문서의 다음 클라이언트 항목에 대한 포인터 또는 더 이상 클라이언트 항목이 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

각 호출 후 *pos값은* 문서의 다음 항목에 대해 설정되며, 이 값은 클라이언트 항목일 수도 있으며 그렇지 않을 수도 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

## <a name="coledocumentgetnextitem"></a><a name="getnextitem"></a>콜레문서::겟넥스트아이템

이 함수를 반복적으로 호출하여 문서의 각 항목에 액세스합니다.

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
에 대한 이전 호출에 의해 설정된 `GetNextItem`POSITION 값에 대한 참조입니다. 초기 값은 멤버 `GetStartPosition` 함수에서 반환됩니다.

### <a name="return-value"></a>Return Value

지정된 위치에서 문서 항목에 대한 포인터입니다.

### <a name="remarks"></a>설명

각 호출 후 *pos* 값은 문서의 다음 항목의 POSITION 값으로 설정됩니다. 검색된 요소가 문서의 마지막 요소인 경우 *pos의* 새 값은 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

## <a name="coledocumentgetnextserveritem"></a><a name="getnextserveritem"></a>COle문서::GetNextServer항목

이 함수를 반복적으로 호출하여 문서의 각 서버 항목에 액세스합니다.

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>매개 변수

*Pos*<br/>
에 대한 이전 호출에 의해 설정된 `GetNextServerItem`POSITION 값에 대한 참조입니다. 초기 값은 멤버 `GetStartPosition` 함수에서 반환됩니다.

### <a name="return-value"></a>Return Value

문서의 다음 서버 항목에 대한 포인터 또는 서버 항목이 더 이상 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

호출할 때마다 *문서의* 다음 항목에 대해 pos 값이 설정되며, 이 값은 서버 항목일 수도 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

## <a name="coledocumentgetprimaryselecteditem"></a><a name="getprimaryselecteditem"></a>콜레문서::GetPrimary선택항목

지정된 보기에서 현재 선택된 OLE 항목을 검색하기 위해 프레임워크에서 호출합니다.

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>매개 변수

*pView*<br/>
문서를 표시하는 활성 뷰 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

선택한 단일 OLE 항목에 대한 포인터; OLE 항목이 선택되지 않았거나 둘 이상의 항목을 선택한 경우 NULL입니다.

### <a name="remarks"></a>설명

기본 구현은 포함된 OLE 항목 의 목록을 선택한 단일 항목에 대해 검색하고 포인터를 반환합니다. 선택한 항목이 없거나 선택한 항목이 두 개 이상인 경우 함수는 NULL을 반환합니다. 이 함수가 `CView::IsSelected` 작동하려면 뷰 클래스의 멤버 함수를 재정의해야 합니다. 포함된 OLE 항목을 저장하는 고유한 방법이 있는 경우 이 함수를 재정의합니다.

## <a name="coledocumentgetstartposition"></a><a name="getstartposition"></a>COle문서::GetStart포지션

이 함수를 호출하여 문서의 첫 번째 항목의 위치를 가져옵니다.

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Return Value

문서의 항목을 반복하는 데 사용할 수 있는 위치 값입니다. 문서에 항목이 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

에 반환된 `GetNextItem` `GetNextClientItem`값을 에 `GetNextServerItem`전달합니다.

## <a name="coledocumenthasblankitems"></a><a name="hasblankitems"></a>콜레문서::하스블랭크아이템

이 함수를 호출하여 문서에 빈 항목이 있는지 확인합니다.

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>Return Value

문서에 빈 항목이 포함되어 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

빈 항목은 사각형이 비어 있는 항목입니다.

## <a name="coledocumentoneditchangeicon"></a><a name="oneditchangeicon"></a>COle문서::온편집 변경 아이콘

OLE 변경 아이콘 대화 상자를 표시하고 현재 선택된 OLE 항목을 나타내는 아이콘을 대화 상자에서 사용자가 선택한 아이콘으로 변경합니다.

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>설명

`OnEditChangeIcon`아이콘 `COleChangeIconDialog` 변경 대화 상자를 만들고 실행합니다.

## <a name="coledocumentoneditconvert"></a><a name="oneditconvert"></a>콜레문서::온에티트변환

OLE 변환 대화 상자를 표시 하고 변환 또는 변환 또는 대화 상자에서 사용자 선택에 따라 현재 선택 된 OLE 항목을 활성화 합니다.

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>설명

`OnEditConvert`변환 대화 `COleConvertDialog` 상자를 만들고 실행합니다.

변환의 예는 Microsoft Word 문서를 워드패드 문서로 변환하는 것입니다.

## <a name="coledocumentoneditlinks"></a><a name="oneditlinks"></a>콜레문서::온에더티링크

OLE 편집/링크 대화 상자가 표시됩니다.

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>설명

`OnEditLinks`에서는 사용자가 `COleLinksDialog` 연결된 개체를 변경할 수 있는 링크 대화 상자를 만들고 시작합니다.

## <a name="coledocumentonfilesendmail"></a><a name="onfilesendmail"></a>콜레문서::온파일센드메일

첨부 파일로 첨부 된 상주 메일 호스트 (있는 경우)를 통해 메시지를 보냅니다.

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>설명

`OnFileSendMail``OnSaveDocument` 제목이 없는 수정된 문서를 임시 파일로 직렬화(저장)한 다음 전자 메일을 통해 전송됩니다. 문서를 수정하지 않은 경우 임시 파일이 필요하지 않습니다. 원본이 전송됩니다. `OnFileSendMail`MAPI32를 로드합니다. DLL이 아직 로드되지 않은 경우.

`OnFileSendMail` 에 `CDocument`대한 구현과 달리이 함수는 복합 파일을 올바르게 처리합니다.

자세한 내용은 MFC 문서의 [MAPI 토픽](../../mfc/mapi.md) 및 [MAPI 지원을](../../mfc/mapi-support-in-mfc.md) 참조하십시오.

## <a name="coledocumentonshowviews"></a><a name="onshowviews"></a>콜레문서::온쇼뷰

프레임워크는 문서의 가시성 상태가 변경된 후 이 함수를 호출합니다.

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>매개 변수

*bVisible*<br/>
문서가 표시되었는지 표시되지 않았는지 또는 보이지 않는지 나타냅니다.

### <a name="remarks"></a>설명

이 함수의 기본 버전은 아무 것도 수행하지 않습니다. 문서의 가시성이 변경될 때 응용 프로그램에서 특수 처리를 수행해야 하는 경우 이를 재정의합니다.

## <a name="coledocumentonupdateeditchangeicon"></a><a name="onupdateeditchangeicon"></a>COle문서::업데이트된업데이트변경아이콘

편집 메뉴에서 아이콘 변경 명령을 업데이트하려면 프레임워크에서 호출합니다.

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
업데이트 명령을 `CCmdUI` 생성한 메뉴를 나타내는 구조에 대한 포인터입니다. 업데이트 처리기는 `Enable` `CCmdUI` *pCmdUI를* 통해 구조의 멤버 함수를 호출하여 사용자 인터페이스를 업데이트합니다.

### <a name="remarks"></a>설명

`OnUpdateEditChangeIcon`문서에 유효한 아이콘이 있는지 여부에 따라 명령의 사용자 인터페이스를 업데이트합니다. 이 함수를 재정의하여 동작을 변경합니다.

## <a name="coledocumentonupdateeditlinksmenu"></a><a name="onupdateeditlinksmenu"></a>콜레 문서::업데이트 된편집 링크메뉴

편집 메뉴에서 링크 명령을 업데이트하려면 프레임워크에서 호출합니다.

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
업데이트 명령을 `CCmdUI` 생성한 메뉴를 나타내는 구조에 대한 포인터입니다. 업데이트 처리기는 `Enable` `CCmdUI` *pCmdUI를* 통해 구조의 멤버 함수를 호출하여 사용자 인터페이스를 업데이트합니다.

### <a name="remarks"></a>설명

문서의 첫 번째 OLE 항목부터 시작하여 각 항목에 `OnUpdateEditLinksMenu` 액세스하고 항목이 링크인지 여부를 테스트하고 링크인 경우 링크 명령을 활성화합니다. 이 함수를 재정의하여 동작을 변경합니다.

## <a name="coledocumentonupdateobjectverbmenu"></a><a name="onupdateobjectverbmenu"></a>콜레 문서::에 업데이트개체 버브 메뉴

개체 이름이 문서에 포함된 OLE 개체의 *이름인* ObjectName 명령에서 액세스한 *개체 이름* 및 동사 하위 메뉴에서 *ObjectName* 명령을 업데이트하기 위해 프레임워크에서 호출합니다.

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
업데이트 명령을 `CCmdUI` 생성한 메뉴를 나타내는 구조에 대한 포인터입니다. 업데이트 처리기는 `Enable` `CCmdUI` *pCmdUI를* 통해 구조의 멤버 함수를 호출하여 사용자 인터페이스를 업데이트합니다.

### <a name="remarks"></a>설명

`OnUpdateObjectVerbMenu`문서에 유효한 개체가 있는지 여부에 따라 *ObjectName* 명령의 사용자 인터페이스를 업데이트합니다. 개체가 있는 경우 편집 메뉴의 *ObjectName* 명령이 활성화됩니다. 이 메뉴 명령을 선택하면 동사 하위 메뉴가 표시됩니다. 동사 하위 메뉴에는 편집, 속성 등과 같은 개체에 사용할 수 있는 모든 동사 명령이 포함되어 있습니다. 이 함수를 재정의하여 동작을 변경합니다.

## <a name="coledocumentonupdatepastelinkmenu"></a><a name="onupdatepastelinkmenu"></a>콜레 문서::온업데이트붙여넣기링크메뉴

연결된 OLE 항목을 클립보드에서 붙여넣기할 수 있는지 여부를 결정하기 위해 프레임워크에서 호출합니다.

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
업데이트 명령을 `CCmdUI` 생성한 메뉴를 나타내는 구조에 대한 포인터입니다. 업데이트 처리기는 `Enable` `CCmdUI` *pCmdUI를* 통해 구조의 멤버 함수를 호출하여 사용자 인터페이스를 업데이트합니다.

### <a name="remarks"></a>설명

항목을 문서에 붙여넣을 수 있는지 여부에 따라 특수 메뉴 붙여넣기 명령이 활성화되거나 비활성화됩니다.

## <a name="coledocumentonupdatepastemenu"></a><a name="onupdatepastemenu"></a>콜레 문서::온업데이트페이스트 메뉴

프레임워크에서 호출하여 포함된 OLE 항목을 Clipboard에서 붙여넣기를 사용할 수 있는지 여부를 결정합니다.

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
업데이트 명령을 `CCmdUI` 생성한 메뉴를 나타내는 구조에 대한 포인터입니다. 업데이트 처리기는 `Enable` `CCmdUI` *pCmdUI를* 통해 구조의 멤버 함수를 호출하여 사용자 인터페이스를 업데이트합니다.

### <a name="remarks"></a>설명

항목을 문서에 붙여넣을 수 있는지 여부에 따라 붙여넣기 메뉴 명령 및 단추를 사용 하거나 사용할 수 없습니다.

## <a name="coledocumentremoveitem"></a><a name="removeitem"></a>콜레문서::제거항목

이 함수를 호출하여 문서에서 항목을 제거합니다.

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
제거할 문서 항목에 대한 포인터입니다.

### <a name="remarks"></a>설명

일반적으로 이 함수를 명시적으로 호출할 필요가 없습니다. 소멸자 및 `COleClientItem` `COleServerItem`에 대해 호출됩니다.

## <a name="coledocumentupdatemodifiedflag"></a><a name="updatemodifiedflag"></a>COle문서::업데이트수정플래그

포함된 OLE 항목중 어느 것이라도 수정된 경우 문서를 수정된 것으로 표시하려면 이 함수를 호출합니다.

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>설명

이렇게 하면 문서의 기본 데이터가 수정되지 않은 경우에도 프레임워크에서 닫기 전에 문서를 저장하라는 메시지를 표시할 수 있습니다.

## <a name="see-also"></a>참조

[MFC 샘플 컨테이너](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[C문서 클래스](../../mfc/reference/cdocument-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
