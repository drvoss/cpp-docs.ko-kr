---
title: 콜레데이터소스 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDataSource
- AFXOLE/COleDataSource
- AFXOLE/COleDataSource::COleDataSource
- AFXOLE/COleDataSource::CacheData
- AFXOLE/COleDataSource::CacheGlobalData
- AFXOLE/COleDataSource::DelayRenderData
- AFXOLE/COleDataSource::DelayRenderFileData
- AFXOLE/COleDataSource::DelaySetData
- AFXOLE/COleDataSource::DoDragDrop
- AFXOLE/COleDataSource::Empty
- AFXOLE/COleDataSource::FlushClipboard
- AFXOLE/COleDataSource::GetClipboardOwner
- AFXOLE/COleDataSource::OnRenderData
- AFXOLE/COleDataSource::OnRenderFileData
- AFXOLE/COleDataSource::OnRenderGlobalData
- AFXOLE/COleDataSource::OnSetData
- AFXOLE/COleDataSource::SetClipboard
helpviewer_keywords:
- COleDataSource [MFC], COleDataSource
- COleDataSource [MFC], CacheData
- COleDataSource [MFC], CacheGlobalData
- COleDataSource [MFC], DelayRenderData
- COleDataSource [MFC], DelayRenderFileData
- COleDataSource [MFC], DelaySetData
- COleDataSource [MFC], DoDragDrop
- COleDataSource [MFC], Empty
- COleDataSource [MFC], FlushClipboard
- COleDataSource [MFC], GetClipboardOwner
- COleDataSource [MFC], OnRenderData
- COleDataSource [MFC], OnRenderFileData
- COleDataSource [MFC], OnRenderGlobalData
- COleDataSource [MFC], OnSetData
- COleDataSource [MFC], SetClipboard
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
ms.openlocfilehash: 8746be43e3f2a31558904323392983b183d4f198
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753902"
---
# <a name="coledatasource-class"></a>콜레데이터소스 클래스

애플리케이션이 데이터를 넣어 두었다 클립보드 또는 끌어 놓기 작업과 같은 데이터 전송 작업에서 해당 데이터를 제공하는 캐시의 역할을 합니다.

## <a name="syntax"></a>구문

```
class COleDataSource : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레데이터소스::콜레데이터소스](#coledatasource)|`COleDataSource` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleDataSource::캐시데이터](#cachedata)|`STGMEDIUM` 구조를 사용하여 지정된 형식으로 데이터를 제공합니다.|
|[COleDataSource::캐시글로벌데이터](#cacheglobaldata)|HGLOBAL을 사용하여 지정된 형식으로 데이터를 제공합니다.|
|[콜레데이터소스::D헬레이렌더데이터](#delayrenderdata)|지연된 렌더링을 사용하여 지정된 형식으로 데이터를 제공합니다.|
|[COleDataSource::Delay렌더파일데이터](#delayrenderfiledata)|`CFile` 포인터에서 지정된 형식으로 데이터를 제공합니다.|
|[콜레데이터소스::DelaySetData](#delaysetdata)|에서 지원되는 모든 형식에 대해 호출됩니다. `OnSetData`|
|[콜레데이터소스::D오드래그드롭](#dodragdrop)|데이터 원본을 사용하여 끌어서 놓기 작업을 수행합니다.|
|[콜레데이터소스::비어 있음](#empty)|데이터의 개체를 `COleDataSource` 비우면 됩니다.|
|[콜레데이터소스::플러시 클립보드](#flushclipboard)|모든 데이터를 클립보드에 렌더링합니다.|
|[COleDataSource::GetClipboard 소유자](#getclipboardowner)|클립보드에 배치된 데이터가 여전히 있는지 확인합니다.|
|[콜레데이터소스::온렌더데이터](#onrenderdata)|지연된 렌더링의 일부로 데이터를 검색합니다.|
|[콜레데이터소스::온렌더파일데이터](#onrenderfiledata)|지연된 렌더링의 `CFile` 일부로 데이터를 검색합니다.|
|[콜레데이터소스:온렌더글로벌데이터](#onrenderglobaldata)|지연된 렌더링의 일부로 HGLOBAL에 데이터를 검색합니다.|
|[콜레데이터소스::온셋데이터](#onsetdata)|개체의 데이터를 바꾸기 `COleDataSource` 위해 호출됩니다.|
|[콜레데이터소스::셋클립보드](#setclipboard)|`COleDataSource` 클립보드에 오브젝트를 배치합니다.|

## <a name="remarks"></a>설명

OLE 데이터 원본을 직접 만들 수 있습니다. 또는 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 및 [COleServerItem](../../mfc/reference/coleserveritem-class.md) 클래스는 해당 `CopyToClipboard` 함수 및 `DoDragDrop` 멤버 함수에 대한 응답으로 OLE 데이터 원본을 만듭니다. 간단한 설명은 [COleServerItem::CopyTo클립보드를](../../mfc/reference/coleserveritem-class.md#copytoclipboard) 참조하십시오. 클라이언트 항목 `OnGetClipboardData` 또는 서버 항목 클래스의 멤버 함수를 재정의하여 `CopyToClipboard` 또는 `DoDragDrop` 멤버 함수에 대해 만든 OLE 데이터 원본의 데이터에 클립보드 형식을 추가합니다.

전송을 위해 데이터를 준비하려면 이 클래스의 개체를 만들고 데이터에 가장 적합한 방법을 사용하여 데이터로 채워야 합니다. 데이터 원본에 삽입되는 방식은 데이터가 즉시(즉시 렌더링) 제공되는지 또는 요청 시(지연된 렌더링)에 의해 직접적인 영향을 받습니다. 사용할 클립보드 형식(및 옵션 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조)을 전달하여 데이터를 제공하는 모든 클립보드 형식에 대해 [DelayRenderData](#delayrenderdata)를 호출합니다.

데이터 원본 및 데이터 전송에 대한 자세한 내용은 [OLE(데이터 개체 및 데이터 원본)](../../mfc/data-objects-and-data-sources-ole.md)문서를 참조하십시오. 또한 [문서 클립보드 항목에서는](../../mfc/clipboard.md) OLE 클립보드 메커니즘에 대해 설명합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDataSource`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

## <a name="coledatasourcecachedata"></a><a name="cachedata"></a>COleDataSource::캐시데이터

이 함수를 호출하여 데이터 전송 작업 중에 데이터가 제공되는 형식을 지정합니다.

```cpp
void CacheData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 제공 해야 하는 클립보드 형식입니다. 이 매개 변수는 미리 정의된 클립보드 형식 중 하나이거나 기본 Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 함수에서 반환되는 값일 수 있습니다.

*lpStgMedium*<br/>
지정된 형식으로 데이터를 포함하는 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 구조를 가리킵니다.

*lpFormatEtc*<br/>
데이터가 제공될 형식을 설명하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다. *cfFormat에*의해 지정된 클립보드 형식 이외의 추가 형식 정보를 지정하려는 경우 이 매개 변수에 대한 값을 제공합니다. NULL인 경우 기본값은 `FORMATETC` 구조의 다른 필드에 사용됩니다.

### <a name="remarks"></a>설명

이 함수는 즉시 렌더링을 사용하여 데이터를 제공하기 때문에 데이터를 제공해야 합니다. 필요할 때까지 데이터가 캐시됩니다.

[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 구조를 사용하여 데이터를 공급합니다. 또한 제공하는 데이터의 `CacheGlobalData` 양이 HGLOBAL을 사용하여 효율적으로 전송될 수 있을 만큼 작은 경우 멤버 함수를 사용할 수도 있습니다.

`CacheData` 의 `ptd` `lpFormatEtc` 멤버와 *lpStgMedium의* 내용에 대한 호출 후 호출자하지 데이터 개체에 의해 소유됩니다.

지연된 렌더링을 사용하려면 [DelayRenderData](#delayrenderdata) 또는 [DelayRenderFileData](#delayrenderfiledata) 멤버 함수를 호출합니다. MFC에서 처리하는 지연 렌더링에 대한 자세한 내용은 [문서 데이터 개체 및 데이터 원본: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)을 참조하십시오.

자세한 내용은 Windows SDK의 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 및 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 참조하십시오.

자세한 내용은 Windows SDK의 [RegisterClipboardFormat을](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 참조하십시오.

## <a name="coledatasourcecacheglobaldata"></a><a name="cacheglobaldata"></a>COleDataSource::캐시글로벌데이터

이 함수를 호출하여 데이터 전송 작업 중에 데이터가 제공되는 형식을 지정합니다.

```cpp
void CacheGlobalData(
    CLIPFORMAT cfFormat,
    HGLOBAL hGlobal,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 제공 해야 하는 클립보드 형식입니다. 이 매개 변수는 미리 정의된 클립보드 형식 중 하나이거나 기본 Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 함수에서 반환되는 값일 수 있습니다.

*Hglobal*<br/>
지정된 형식으로 데이터를 포함하는 전역 메모리 블록을 처리합니다.

*lpFormatEtc*<br/>
데이터가 제공될 형식을 설명하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다. *cfFormat에*의해 지정된 클립보드 형식 이외의 추가 형식 정보를 지정하려는 경우 이 매개 변수에 대한 값을 제공합니다. NULL인 경우 기본값은 `FORMATETC` 구조의 다른 필드에 사용됩니다.

### <a name="remarks"></a>설명

이 함수는 즉각적인 렌더링을 사용하여 데이터를 제공하므로 함수를 호출할 때 데이터를 제공해야 합니다. 필요할 때까지 데이터가 캐시됩니다. 많은 `CacheData` 양의 데이터를 제공하거나 구조화 된 저장소 매체가 필요한 경우 멤버 함수를 사용합니다.

지연된 렌더링을 사용하려면 [DelayRenderData](#delayrenderdata) 또는 [DelayRenderFileData](#delayrenderfiledata) 멤버 함수를 호출합니다. MFC에서 처리하는 지연 렌더링에 대한 자세한 내용은 [문서 데이터 개체 및 데이터 원본: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)을 참조하십시오.

자세한 내용은 Windows SDK의 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 참조하십시오.

자세한 내용은 Windows SDK의 [RegisterClipboardFormat을](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 참조하십시오.

## <a name="coledatasourcecoledatasource"></a><a name="coledatasource"></a>콜레데이터소스::콜레데이터소스

`COleDataSource` 개체를 생성합니다.

```
COleDataSource();
```

## <a name="coledatasourcedelayrenderdata"></a><a name="delayrenderdata"></a>콜레데이터소스::D헬레이렌더데이터

이 함수를 호출하여 데이터 전송 작업 중에 데이터가 제공되는 형식을 지정합니다.

```cpp
void DelayRenderData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 제공 해야 하는 클립보드 형식입니다. 이 매개 변수는 미리 정의된 클립보드 형식 중 하나이거나 기본 Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 함수에서 반환되는 값일 수 있습니다.

*lpFormatEtc*<br/>
데이터가 제공될 형식을 설명하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다. *cfFormat에*의해 지정된 클립보드 형식 이외의 추가 형식 정보를 지정하려는 경우 이 매개 변수에 대한 값을 제공합니다. NULL인 경우 기본값은 `FORMATETC` 구조의 다른 필드에 사용됩니다.

### <a name="remarks"></a>설명

이 함수는 지연된 렌더링을 사용하여 데이터를 제공하므로 데이터가 즉시 제공되지 않습니다. [OnRenderData](#onrenderdata) 또는 [OnRenderGlobalData](#onrenderglobaldata) 멤버 함수는 데이터를 요청하기 위해 호출됩니다.

개체를 통해 데이터를 제공하지 않을 경우 이 `CFile` 함수를 사용합니다. `CFile` 개체를 통해 데이터를 제공하려는 경우 [DelayRenderFileData](#delayrenderfiledata) 멤버 함수를 호출합니다. MFC에서 처리하는 지연 렌더링에 대한 자세한 내용은 [문서 데이터 개체 및 데이터 원본: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)을 참조하십시오.

즉각적인 렌더링을 사용하려면 [CacheData](#cachedata) 또는 [CacheGlobalData](#cacheglobaldata) 멤버 함수를 호출합니다.

자세한 내용은 Windows SDK의 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 참조하십시오.

자세한 내용은 Windows SDK의 [RegisterClipboardFormat을](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 참조하십시오.

## <a name="coledatasourcedelayrenderfiledata"></a><a name="delayrenderfiledata"></a>COleDataSource::Delay렌더파일데이터

이 함수를 호출하여 데이터 전송 작업 중에 데이터가 제공되는 형식을 지정합니다.

```cpp
void DelayRenderFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 제공 해야 하는 클립보드 형식입니다. 이 매개 변수는 미리 정의된 클립보드 형식 중 하나이거나 기본 Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 함수에서 반환되는 값일 수 있습니다.

*lpFormatEtc*<br/>
데이터가 제공될 형식을 설명하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다. *cfFormat에*의해 지정된 클립보드 형식 이외의 추가 형식 정보를 지정하려는 경우 이 매개 변수에 대한 값을 제공합니다. NULL인 경우 기본값은 `FORMATETC` 구조의 다른 필드에 사용됩니다.

### <a name="remarks"></a>설명

이 함수는 지연된 렌더링을 사용하여 데이터를 제공하므로 데이터가 즉시 제공되지 않습니다. [OnRenderFileData](#onrenderfiledata) 멤버 함수는 데이터를 요청하기 위해 호출됩니다.

개체를 `CFile` 사용하여 데이터를 제공하려는 경우 이 함수를 사용합니다. 개체를 `CFile` 사용하지 않을 경우 [DelayRenderData](#delayrenderdata) 멤버 함수를 호출합니다. MFC에서 처리하는 지연 렌더링에 대한 자세한 내용은 [문서 데이터 개체 및 데이터 원본: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)을 참조하십시오.

즉각적인 렌더링을 사용하려면 [CacheData](#cachedata) 또는 [CacheGlobalData](#cacheglobaldata) 멤버 함수를 호출합니다.

자세한 내용은 Windows SDK의 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 참조하십시오.

자세한 내용은 Windows SDK의 [RegisterClipboardFormat을](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 참조하십시오.

## <a name="coledatasourcedelaysetdata"></a><a name="delaysetdata"></a>콜레데이터소스::DelaySetData

이 함수를 호출하여 데이터 원본의 내용 변경을 지원합니다.

```cpp
void DelaySetData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*cfFormat*<br/>
데이터를 배치할 클립보드 형식입니다. 이 매개 변수는 미리 정의된 클립보드 형식 중 하나이거나 기본 Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 함수에서 반환되는 값일 수 있습니다.

*lpFormatEtc*<br/>
데이터를 대체할 형식을 설명하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다. *cfFormat에*의해 지정된 클립보드 형식 이외의 추가 형식 정보를 지정하려는 경우 이 매개 변수에 대한 값을 제공합니다. NULL인 경우 기본값은 `FORMATETC` 구조의 다른 필드에 사용됩니다.

### <a name="remarks"></a>설명

[OnSetData이](#onsetdata) 발생 하는 경우 프레임 워크에 의해 호출 됩니다. 프레임워크가 [COleServerItem::GetDataSource](../../mfc/reference/coleserveritem-class.md#getdatasource)에서 데이터 원본을 반환하는 경우에만 사용됩니다. 호출되지 않으면 `DelaySetData` `OnSetData` 함수가 호출되지 않습니다. `DelaySetData`지원하려는 각 클립보드 `FORMATETC` 또는 형식에 대해 호출해야 합니다.

자세한 내용은 Windows SDK의 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 참조하십시오.

자세한 내용은 Windows SDK의 [RegisterClipboardFormat을](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 참조하십시오.

## <a name="coledatasourcedodragdrop"></a><a name="dodragdrop"></a>콜레데이터소스::D오드래그드롭

멤버 `DoDragDrop` 함수를 호출하여 일반적으로 [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) 처리기에서 이 데이터 원본에 대한 끌어서 놓기 작업을 수행합니다.

```
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,
    LPCRECT lpRectStartDrag = NULL,
    COleDropSource* pDropSource = NULL);
```

### <a name="parameters"></a>매개 변수

*dwEffects*<br/>
이 데이터 원본에서 허용되는 끌어서 놓기 작업입니다. 다음 중 하나 이상이 될 수 있습니다.

- DROPEFFECT_COPY 복사 작업을 수행할 수 있습니다.

- DROPEFFECT_MOVE 이동 작업을 수행할 수 있습니다.

- DROPEFFECT_LINK 삭제된 데이터에서 원본 데이터에 대한 링크를 설정할 수 있습니다.

- DROPEFFECT_SCROLL 끌기 스크롤 작업이 발생할 수 있음을 나타냅니다.

*lpRectStartDrag*<br/>
드래그가 실제로 시작되는 위치를 정의하는 사각형에 대한 포인터입니다. 자세한 내용은 아래 설명 부분을 참조하십시오.

*pDrop소스*<br/>
드롭 소스를 가리킵니다. NULL이면 [COleDropSource의](../../mfc/reference/coledropsource-class.md) 기본 구현이 사용됩니다.

### <a name="return-value"></a>Return Value

끌어서 놓기 동작에 의해 생성된 낙하 효과; 그렇지 않으면 사용자가 제공된 사각형을 떠나기 전에 마우스 단추를 해제했기 때문에 작업이 시작되지 않는 경우 DROPEFFECT_NONE.

### <a name="remarks"></a>설명

끌어서 놓기 작업이 즉시 시작되지 는 않습니다. 마우스 커서가 *lpRectStartDrag에서* 지정한 사각형을 떠날 때까지 또는 지정된 밀리초가 경과할 때까지 기다립니다. *lpRectStartDrag가* NULL이면 사각형의 크기는 1픽셀입니다.

지연 시간은 레지스트리 키 설정에 의해 지정됩니다. [CWinApp:::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) 또는 [CWinApp::WriteProfileInt를](../../mfc/reference/cwinapp-class.md#writeprofileint)호출하여 지연 시간을 변경할 수 있습니다. 지연 시간을 지정하지 않으면 기본값 200밀리초가 사용됩니다. 드래그 지연 시간은 다음과 같이 저장됩니다.

- 윈도우 NT 드래그 지연 시간은 HKEY_LOCAL_MACHINE 저장됩니다 \SOFTWARE\마이크로 소프트 \윈도우 \NT \현재버전\IniFileMapping\win.ini\Windows\DragDelay.

- 윈도우 3.x 드래그 지연 시간은 WIN에 저장됩니다. [Windows} 섹션 아래의 INI 파일입니다.

- 윈도우 95/98 드래그 지연 시간은 WIN의 캐시 된 버전에 저장됩니다. Ini.

드래그 지연 정보가 레지스트리 또는 에 저장되는 방법에 대한 자세한 내용은 INI 파일은 Windows SDK의 [WriteProfileString을](/windows/win32/api/winbase/nf-winbase-writeprofilestringw) 참조하십시오.

자세한 내용은 [OLE 끌어놓기](../../mfc/drag-and-drop-ole.md)문서를 참조하십시오.

## <a name="coledatasourceempty"></a><a name="empty"></a>콜레데이터소스::비어 있음

이 함수를 호출하여 데이터 개체를 비웁습니다. `COleDataSource`

```cpp
void Empty();
```

### <a name="remarks"></a>설명

캐시된 렌더 형식과 지연 렌더링 형식은 모두 비워서 다시 사용할 수 있습니다.

자세한 내용은 Windows SDK의 [ReleaseStgMedium를](/windows/win32/api/ole2/nf-ole2-releasestgmedium) 참조하십시오.

## <a name="coledatasourceflushclipboard"></a><a name="flushclipboard"></a>콜레데이터소스::플러시 클립보드

클립보드에 있는 데이터를 렌더링한 다음 응용 프로그램이 종료된 후 클립보드에서 데이터를 붙여넣을 수 있습니다.

```
static void PASCAL FlushClipboard();
```

### <a name="remarks"></a>설명

[SetClipboard를](#setclipboard) 사용하여 클립보드에 데이터를 배치합니다.

## <a name="coledatasourcegetclipboardowner"></a><a name="getclipboardowner"></a>COleDataSource::GetClipboard 소유자

[SetClipboard가](#setclipboard) 마지막으로 호출된 이후 클립보드의 데이터가 변경되었는지 여부를 결정하고, 이 경우 현재 소유자를 식별합니다.

```
static COleDataSource* PASCAL GetClipboardOwner();
```

### <a name="return-value"></a>Return Value

현재 클립보드에 있는 데이터 원본 또는 클립보드에 아무 것도 없거나 클립보드가 호출 응용 프로그램에서 소유하지 않은 경우 NULL입니다.

## <a name="coledatasourceonrenderdata"></a><a name="onrenderdata"></a>콜레데이터소스::온렌더데이터

지정된 형식으로 데이터를 검색하는 프레임워크에서 호출됩니다.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
정보가 요청되는 형식을 지정하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다.

*lpStgMedium*<br/>
데이터를 반환할 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 구조를 가리킵니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정된 형식은 지연 렌더링을 `COleDataSource` 위해 [DelayRenderData](#delayrenderdata) 또는 [DelayRenderFileData](#delayrenderfiledata) 멤버 함수를 사용하여 이전에 개체에 배치된 형식입니다. 이 함수의 기본 구현은 제공된 저장소 매체가 각각 파일 또는 메모리인 경우 [OnRenderFileData](#onrenderfiledata) 또는 [OnRenderGlobalData를](#onrenderglobaldata) 호출합니다. 이러한 형식이 제공되지 않으면 기본 구현이 0을 반환하고 아무 것도 수행하지 않습니다. MFC에서 처리하는 지연 렌더링에 대한 자세한 내용은 [문서 데이터 개체 및 데이터 원본: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)을 참조하십시오.

*lpStgMedium*-> *타이메드가* TYMED_NULL `STGMEDIUM` 경우, TYMED_NULL 할당하고 *lpFormatEtc->의해*지정된 대로 채워야 한다. TYMED_NULL 않으면 데이터가 `STGMEDIUM` 채워져야 합니다.

이 고급 재정의 할 수 있습니다. 이 함수를 재정의하여 요청된 형식과 매체로 데이터를 제공합니다. 데이터에 따라 이 함수의 다른 버전 중 하나를 대신 재정의할 수 있습니다. 데이터가 작고 크기가 고정된 경우 `OnRenderGlobalData`재정의합니다. 데이터가 파일에 있거나 크기가 가변인 경우 재정의합니다. `OnRenderFileData`

자세한 내용은 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 및 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조, [TYMED](/windows/win32/api/objidl/ne-objidl-tymed) 열거 형 및 Windows SDK의 [IDataObject:GetData를](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) 참조하십시오.

## <a name="coledatasourceonrenderfiledata"></a><a name="onrenderfiledata"></a>콜레데이터소스::온렌더파일데이터

지정된 저장소 매체가 파일인 경우 지정된 형식으로 데이터를 검색하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
정보가 요청되는 형식을 지정하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다.

*pFile*<br/>
데이터를 렌더링할 [CFile](../../mfc/reference/cfile-class.md) 개체를 가리킵니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정된 형식은 지연된 렌더링을 `COleDataSource` 위해 [DelayRenderData](#delayrenderdata) 멤버 함수를 사용하여 개체에 이전에 배치된 형식입니다. 이 함수의 기본 구현은 단순히 FALSE를 반환합니다.

이 고급 재정의 할 수 있습니다. 이 함수를 재정의하여 요청된 형식과 매체로 데이터를 제공합니다. 데이터에 따라 이 함수의 다른 버전 중 하나를 대신 재정의할 수 있습니다. 여러 저장소 미디어를 처리하려면 [OnRenderData](#onrenderdata)를 재정의합니다. 데이터가 파일에 있거나 크기가 가변인 경우 재정의합니다. `OnRenderFileData` MFC에서 처리하는 지연 렌더링에 대한 자세한 내용은 [문서 데이터 개체 및 데이터 원본: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)을 참조하십시오.

자세한 내용은 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조 및 [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) Windows SDK를 참조하십시오.

## <a name="coledatasourceonrenderglobaldata"></a><a name="onrenderglobaldata"></a>콜레데이터소스:온렌더글로벌데이터

지정된 저장소 매체가 전역 메모리인 경우 지정된 형식으로 데이터를 검색하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
정보가 요청되는 형식을 지정하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다.

*phGlobal*<br/>
데이터를 반환할 전역 메모리에 대한 핸들을 가리킵니다. 아직 할당되지 않은 매개 변수는 NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정된 형식은 지연된 렌더링을 `COleDataSource` 위해 [DelayRenderData](#delayrenderdata) 멤버 함수를 사용하여 개체에 이전에 배치된 형식입니다. 이 함수의 기본 구현은 단순히 FALSE를 반환합니다.

*phGlobal이* NULL이면 새 HGLOBAL을 할당하고 *phGlobal로*반환해야 합니다. 그렇지 않으면 phGlobal에서 지정한 *HGLOBAL은* 데이터로 채워야 합니다. HGLOBAL에 배치된 데이터 양은 메모리 블록의 현재 크기를 초과해서는 안 됩니다. 또한 블록을 더 큰 크기로 다시 할당할 수 없습니다.

이 고급 재정의 할 수 있습니다. 이 함수를 재정의하여 요청된 형식과 매체로 데이터를 제공합니다. 데이터에 따라 이 함수의 다른 버전 중 하나를 대신 재정의할 수 있습니다. 여러 저장소 미디어를 처리하려면 [OnRenderData](#onrenderdata)를 재정의합니다. 데이터가 파일에 있거나 가변 크기인 경우 [OnRenderFileData](#onrenderfiledata)를 재정의합니다. MFC에서 처리하는 지연 렌더링에 대한 자세한 내용은 [문서 데이터 개체 및 데이터 원본: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)을 참조하십시오.

자세한 내용은 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조 및 [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) Windows SDK를 참조하십시오.

## <a name="coledatasourceonsetdata"></a><a name="onsetdata"></a>콜레데이터소스::온셋데이터

지정된 형식으로 `COleDataSource` 개체의 데이터를 설정하거나 바꾸기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>매개 변수

*lpFormatEtc*<br/>
데이터가 대체되는 형식을 지정하는 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조를 가리킵니다.

*lpStgMedium*<br/>
`COleDataSource` 개체의 현재 내용을 대체할 데이터를 포함하는 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 구조를 가리킵니다.

*bRelease*<br/>
함수 호출을 완료한 후 저장소 매체의 소유권이 있는 사람을 나타냅니다. 호출자는 저장소 매체를 대신하여 할당된 리소스를 해제할 책임이 있는 사람을 결정합니다. 호출자는 *bRelease*를 설정하여 이 작업을 수행합니다. *bRelease가* 0이 아닌 경우 데이터 원본은 소유권을 가지므로 미디어사용이 완료되면 미디어를 해제합니다. *bRelease가* 0이면 호출자는 소유권을 유지하고 데이터 원본은 호출 기간 동안에만 저장소 매체를 사용할 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

데이터 원본은 데이터 원본을 성공적으로 획득할 때까지 데이터의 소유권을 가지지 않습니다. 즉, 0을 반환하는 `OnSetData` 경우 소유권을 받지 않습니다. 데이터 원본이 소유권을 가지면 [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) 함수를 호출하여 저장소 매체를 해제합니다.

기본 구현은 아무 작업도 수행하지 않습니다. 이 함수를 재정의하여 지정된 형식으로 데이터를 바꿉니다. 이 고급 재정의 할 수 있습니다.

자세한 내용은 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) 및 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 구조및 Windows SDK의 [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) 및 [IDataObject:GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) 함수를 참조하십시오.

## <a name="coledatasourcesetclipboard"></a><a name="setclipboard"></a>콜레데이터소스::셋클립보드

다음 함수 중 `COleDataSource` 하나를 호출한 후 클립보드의 개체에 포함된 데이터를 [캐시데이터,](#cachedata) [캐시글로벌데이터,](#cacheglobaldata) [DelayRenderData](#delayrenderdata)또는 [DelayRenderFileData](#delayrenderfiledata).

```cpp
void SetClipboard();
```

## <a name="see-also"></a>참조

[MFC 샘플 HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 클라이언트](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[콜레데이터오브젝트 클래스](../../mfc/reference/coledataobject-class.md)
