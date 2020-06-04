---
title: 콜레데이터오브젝트 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDataObject
- AFXOLE/COleDataObject
- AFXOLE/COleDataObject::COleDataObject
- AFXOLE/COleDataObject::Attach
- AFXOLE/COleDataObject::AttachClipboard
- AFXOLE/COleDataObject::BeginEnumFormats
- AFXOLE/COleDataObject::Detach
- AFXOLE/COleDataObject::GetData
- AFXOLE/COleDataObject::GetFileData
- AFXOLE/COleDataObject::GetGlobalData
- AFXOLE/COleDataObject::GetNextFormat
- AFXOLE/COleDataObject::IsDataAvailable
- AFXOLE/COleDataObject::Release
helpviewer_keywords:
- COleDataObject [MFC], COleDataObject
- COleDataObject [MFC], Attach
- COleDataObject [MFC], AttachClipboard
- COleDataObject [MFC], BeginEnumFormats
- COleDataObject [MFC], Detach
- COleDataObject [MFC], GetData
- COleDataObject [MFC], GetFileData
- COleDataObject [MFC], GetGlobalData
- COleDataObject [MFC], GetNextFormat
- COleDataObject [MFC], IsDataAvailable
- COleDataObject [MFC], Release
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
ms.openlocfilehash: 8b9565382de8ae731c166f60a0d1994c1b948a7b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753916"
---
# <a name="coledataobject-class"></a>콜레데이터오브젝트 클래스

끌어 놓기를 통해 클립보드에서 또는 포함된 OLE 항목에서 다양한 형식의 데이터를 검색하기 위해 데이터를 전송하는 데 사용됩니다.

## <a name="syntax"></a>구문

```
class COleDataObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레데이터오브젝트::콜레데이터오브젝트](#coledataobject)|`COleDataObject` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COle데이터 오브젝트::첨부](#attach)|지정된 OLE 데이터 개체를 `COleDataObject`에 연결합니다.|
|[COleDataObject::연결 클립보드](#attachclipboard)|클립보드에 있는 데이터 개체를 연결합니다.|
|[COleDataObject::시작에이넘 형식](#beginenumformats)|하나 이상의 후속 `GetNextFormat` 호출을 준비합니다.|
|[콜레데이터오브젝트::D에타치](#detach)|연결된 개체를 `IDataObject` 분리합니다.|
|[COle데이터 오브젝트::데이터 수집](#getdata)|연결된 OLE 데이터 개체의 데이터를 지정된 형식으로 복사합니다.|
|[COle데이터 오브젝트::겟파일데이터](#getfiledata)|연결된 OLE 데이터 개체의 데이터를 `CFile` 지정된 형식의 포인터로 복사합니다.|
|[콜레데이터오브젝트::겟글로벌데이터](#getglobaldata)|연결된 OLE 데이터 개체의 `HGLOBAL` 데이터를 지정된 형식으로 복사합니다.|
|[COle데이터 오브젝트::GetNextFormat](#getnextformat)|사용 가능한 다음 데이터 형식을 반환합니다.|
|[콜레데이터오브젝트::데이터 사용 가능](#isdataavailable)|지정된 형식으로 데이터를 사용할 수 있는지 여부를 확인합니다.|
|[콜레데이터오브젝트::릴리즈](#release)|연관된 `IDataObject` 개체를 분리하고 해제합니다.|

## <a name="remarks"></a>설명

`COleDataObject`기본 클래스가 없습니다.

이러한 종류의 데이터 전송에는 원본과 대상이 포함됩니다. 데이터 원본은 [COleDataSource](../../mfc/reference/coledatasource-class.md) 클래스의 개체로 구현됩니다. 대상 응용 프로그램에 데이터가 삭제되거나 Clipboard에서 붙여넣기 작업을 수행하라는 메시지가 들 `COleDataObject` 때마다 클래스의 개체를 만들어야 합니다.

이 클래스를 사용하면 데이터가 지정된 형식으로 존재하는지 여부를 확인할 수 있습니다. 사용 가능한 데이터 형식을 열거하거나 지정된 형식을 사용할 수 있는지 확인한 다음 기본 설정 형식으로 데이터를 검색할 수도 있습니다. 개체 검색은 [CFile,](../../mfc/reference/cfile-class.md)HGLOBAL 또는 구조의 사용을 비롯한 여러 가지 `STGMEDIUM` 방법으로 수행할 수 있습니다.

자세한 내용은 Windows SDK의 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 구조를 참조하십시오.

응용 프로그램에서 데이터 개체를 사용하는 방법에 대한 자세한 내용은 [OLE(데이터 개체 및 데이터 원본)](../../mfc/data-objects-and-data-sources-ole.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`COleDataObject`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="coledataobjectattach"></a><a name="attach"></a>COle데이터 오브젝트::첨부

이 함수를 호출하여 개체를 `COleDataObject` OLE 데이터 개체와 연결합니다.

```cpp
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpDataObject*<br/>
OLE 데이터 개체를 가리킵니다.

*bAutoRelease*<br/>
TRUE 개체가 소멸될 때 OLE `COleDataObject` 데이터 개체를 해제해야 하는 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [IDataObject를](/windows/win32/api/objidl/nn-objidl-idataobject) 참조하십시오.

## <a name="coledataobjectattachclipboard"></a><a name="attachclipboard"></a>COleDataObject::연결 클립보드

이 함수를 호출하여 현재 클립보드에 있는 데이터 `COleDataObject` 개체를 개체에 연결합니다.

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

> [!NOTE]
> 이 함수를 호출하면 이 데이터 개체가 해제될 때까지 클립보드가 잠잠됩니다. 데이터 개체는 `COleDataObject`에 대한 소멸자에서 해제됩니다. 자세한 내용은 Win32 문서의 [OpenClipboard](/windows/win32/api/winuser/nf-winuser-openclipboard) 및 [닫기 클립보드를](/windows/win32/api/winuser/nf-winuser-closeclipboard) 참조하십시오.

## <a name="coledataobjectbeginenumformats"></a><a name="beginenumformats"></a>COleDataObject::시작에이넘 형식

이 함수를 호출하여 항목에서 데이터 형식 목록을 검색하기 `GetNextFormat` 위한 후속 호출을 준비합니다.

```cpp
void BeginEnumFormats();
```

### <a name="remarks"></a>설명

호출 후 `BeginEnumFormats`이 데이터 개체에서 지원하는 첫 번째 형식의 위치가 저장됩니다. 에 대한 `GetNextFormat` 연속 호출은 데이터 개체에서 사용 가능한 형식 목록을 나열합니다.

지정된 형식의 데이터의 가용성을 확인하려면 [COleDataObject::IsDataAvailable](#isdataavailable).

자세한 내용은 [IDataObject::EnumFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) Windows SDK를 참조하십시오.

## <a name="coledataobjectcoledataobject"></a><a name="coledataobject"></a>콜레데이터오브젝트::콜레데이터오브젝트

`COleDataObject` 개체를 생성합니다.

```
COleDataObject();
```

### <a name="remarks"></a>설명

[COleDataObject::연결](#attach) 또는 [COleDataObject::AttachClipboard를](#attachclipboard) 호출하려면 다른 `COleDataObject` 함수를 호출하기 전에 수행해야 합니다.

> [!NOTE]
> 끌어서 놓기 처리기에 대한 매개 변수 중 하나가 에 `COleDataObject`대한 포인터이므로 끌어서 놓기를 지원하기 위해 이 생성기를 호출할 필요가 없습니다.

## <a name="coledataobjectdetach"></a><a name="detach"></a>콜레데이터오브젝트::D에타치

이 함수를 호출하여 `COleDataObject` 데이터 개체를 해제하지 않고 연결된 OLE 데이터 개체에서 개체를 분리합니다.

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>Return Value

분리된 OLE 데이터 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="coledataobjectgetdata"></a><a name="getdata"></a>COle데이터 오브젝트::데이터 수집

이 함수를 호출하여 지정된 형식으로 항목에서 데이터를 검색합니다.

```
BOOL GetData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 반환할 형식입니다. 이 매개 변수는 미리 정의된 클립보드 형식 중 하나이거나 기본 Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 함수에서 반환되는 값일 수 있습니다.

*lpStgMedium*<br/>
데이터를 수신할 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 구조를 가리킵니다.

*lpFormatEtc*<br/>
데이터를 반환할 형식을 설명하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다. *cfFormat에*의해 지정된 클립보드 형식 이외의 추가 형식 정보를 지정하려는 경우 이 매개 변수에 대한 값을 제공합니다. NULL인 경우 기본값은 `FORMATETC` 구조의 다른 필드에 사용됩니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [IDataObject::GetData,](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)및 [FORMATETC를](/windows/win32/api/objidl/ns-objidl-formatetc) 참조하십시오.

자세한 내용은 Windows SDK의 [RegisterClipboardFormat을](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 참조하십시오.

## <a name="coledataobjectgetfiledata"></a><a name="getfiledata"></a>COle데이터 오브젝트::겟파일데이터

이 함수를 호출하여 `CFile`또는 파생된 개체를 `CFile` `CFile` 만들고 지정된 형식의 데이터를 포인터로 검색합니다.

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 반환할 형식입니다. 이 매개 변수는 미리 정의된 클립보드 형식 중 하나이거나 기본 Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 함수에서 반환되는 값일 수 있습니다.

*lpFormatEtc*<br/>
데이터를 반환할 형식을 설명하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다. *cfFormat에*의해 지정된 클립보드 형식 이외의 추가 형식 정보를 지정하려는 경우 이 매개 변수에 대한 값을 제공합니다. NULL인 경우 기본값은 `FORMATETC` 구조의 다른 필드에 사용됩니다.

### <a name="return-value"></a>Return Value

성공하면 데이터를 `CFile` `CFile`포함하는 새 개체 또는 파생 된 개체에 대한 포인터; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

데이터가 저장되는 매체에 따라 반환 값으로 가리키는 실제 형식은 `CFile` `CSharedFile`. `COleStreamFile`

> [!NOTE]
> 이 `CFile` 함수의 반환 값으로 액세스하는 개체는 호출자에서 소유합니다. 개체를 삭제하여 파일을 닫는 것은 호출자의 책임입니다. **delete** `CFile`

자세한 내용은 Windows SDK의 [FORMATETC를](/windows/win32/api/objidl/ns-objidl-formatetc) 참조하십시오.

자세한 내용은 Windows SDK의 [RegisterClipboardFormat을](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 참조하십시오.

## <a name="coledataobjectgetglobaldata"></a><a name="getglobaldata"></a>콜레데이터오브젝트::겟글로벌데이터

이 함수를 호출하여 전역 메모리 블록을 할당하고 지정된 형식의 데이터를 HGLOBAL에 검색합니다.

```
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 반환할 형식입니다. 이 매개 변수는 미리 정의된 클립보드 형식 중 하나이거나 기본 Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 함수에서 반환되는 값일 수 있습니다.

*lpFormatEtc*<br/>
데이터를 반환할 형식을 설명하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다. *cfFormat에*의해 지정된 클립보드 형식 이외의 추가 형식 정보를 지정하려는 경우 이 매개 변수에 대한 값을 제공합니다. NULL인 경우 기본값은 `FORMATETC` 구조의 다른 필드에 사용됩니다.

### <a name="return-value"></a>Return Value

성공하면 데이터를 포함하는 전역 메모리 블록의 핸들입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [FORMATETC를](/windows/win32/api/objidl/ns-objidl-formatetc) 참조하십시오.

자세한 내용은 Windows SDK의 [RegisterClipboardFormat을](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 참조하십시오.

## <a name="coledataobjectgetnextformat"></a><a name="getnextformat"></a>COle데이터 오브젝트::GetNextFormat

항목에서 데이터를 검색하는 데 사용할 수 있는 모든 형식을 가져오려면 이 함수를 반복적으로 호출합니다.

```
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
함수 호출이 반환될 때 형식 정보를 수신하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

다른 형식을 사용할 수 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

[COleDataObject::BeginEnumFormats를](#beginenumformats)호출한 후 이 데이터 개체에서 지원하는 첫 번째 형식의 위치가 저장됩니다. 에 대한 `GetNextFormat` 연속 호출은 데이터 개체에서 사용 가능한 형식 목록을 나열합니다. 이러한 함수를 사용하여 사용 가능한 형식을 나열합니다.

지정된 형식의 가용성을 확인하려면 [COleDataObject::IsDataAvailable](#isdataavailable).

자세한 내용은 [IEnumXXXX::다음](/previous-versions/ms695273\(v=vs.85\)) Windows SDK를 참조하십시오.

## <a name="coledataobjectisdataavailable"></a><a name="isdataavailable"></a>콜레데이터오브젝트::데이터 사용 가능

이 함수를 호출하여 OLE 항목에서 데이터를 검색하는 데 특정 형식을 사용할 수 있는지 확인합니다.

```
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
클립 보드 데이터 형식은 *lpFormatEtc에*의해 가리키는 구조에 사용할 수 있습니다. 이 매개 변수는 미리 정의된 클립보드 형식 중 하나이거나 기본 Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 함수에서 반환되는 값일 수 있습니다.

*lpFormatEtc*<br/>
원하는 형식을 설명하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다. *cfFormat에*의해 지정된 클립보드 형식 이외의 추가 형식 정보를 지정하려는 경우에만 이 매개 변수에 대한 값을 제공합니다. NULL인 경우 기본값은 `FORMATETC` 구조의 다른 필드에 사용됩니다.

### <a name="return-value"></a>Return Value

지정된 형식으로 데이터를 사용할 수 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 을 `GetData` `GetFileData` `GetGlobalData`호출하기 전에 유용합니다.

자세한 내용은 Windows SDK의 [IDataObject::QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) 및 [FORMATETC를](/windows/win32/api/objidl/ns-objidl-formatetc) 참조하십시오.

자세한 내용은 Windows SDK의 [RegisterClipboardFormat을](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 참조하십시오.

### <a name="example"></a>예제

  [CRichEditView::쿼리AcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata)에 대한 예제를 참조하십시오.

## <a name="coledataobjectrelease"></a><a name="release"></a>콜레데이터오브젝트::릴리즈

이 함수를 호출하여 이전에 개체와 연결되었던 [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) 개체의 소유권을 해제합니다. `COleDataObject`

```cpp
void Release();
```

### <a name="remarks"></a>설명

을 `IDataObject` 호출하거나 `COleDataObject` `Attach` 명시적으로 또는 `AttachClipboard` 프레임워크에 의해 연결되었습니다. 의 *bAutoRelease* 매개 `Attach` 변수가 `IDataObject` FALSE이면 개체가 해제되지 않습니다. 이 경우 호출자는 `IDataObject` [IUnknown::Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)를 호출하여 해제할 책임이 있습니다.

## <a name="see-also"></a>참조

[MFC 샘플 HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 클라이언트](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[콜레데이터소스 클래스](../../mfc/reference/coledatasource-class.md)<br/>
[COle클라이언트항목 클래스](../../mfc/reference/coleclientitem-class.md)<br/>
[콜레서버아이템 클래스](../../mfc/reference/coleserveritem-class.md)
