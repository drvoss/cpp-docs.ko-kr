---
title: CPictureHolder 클래스
ms.date: 11/04/2016
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
helpviewer_keywords:
- CPictureHolder [MFC], CPictureHolder
- CPictureHolder [MFC], CreateEmpty
- CPictureHolder [MFC], CreateFromBitmap
- CPictureHolder [MFC], CreateFromIcon
- CPictureHolder [MFC], CreateFromMetafile
- CPictureHolder [MFC], GetDisplayString
- CPictureHolder [MFC], GetPictureDispatch
- CPictureHolder [MFC], GetType
- CPictureHolder [MFC], Render
- CPictureHolder [MFC], SetPictureDispatch
- CPictureHolder [MFC], m_pPict
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
ms.openlocfilehash: edb93b05c1187d2c78f4c1120ee76282167c9b49
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753605"
---
# <a name="cpictureholder-class"></a>CPictureHolder 클래스

사용자가 컨트롤에 그림을 표시할 수 있는 Picture 속성을 구현합니다.

## <a name="syntax"></a>구문

```
class CPictureHolder
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C픽처 홀더::C픽처홀더](#cpictureholder)|`CPictureHolder` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C그림 표시자:빈 만들기](#createempty)|빈 `CPictureHolder` 개체를 만듭니다.|
|[C픽처 홀더::만들기From비트맵](#createfrombitmap)|비트맵에서 `CPictureHolder` 개체를 만듭니다.|
|[C픽처 홀더::만들기From아이콘](#createfromicon)|아이콘에서 `CPictureHolder` 개체를 만듭니다.|
|[C픽처 홀더::생성FromMetafile](#createfrommetafile)|메타파일에서 `CPictureHolder` 개체를 만듭니다.|
|[C픽처 홀더::GetDisplayString](#getdisplaystring)|컨트롤 컨테이너의 속성 브라우저에 표시되는 문자열을 검색합니다.|
|[C픽처 홀더::GetPicture디스패치](#getpicturedispatch)|개체의 `CPictureHolder` 인터페이스를 `IDispatch` 반환합니다.|
|[C픽처 홀더::겟타입](#gettype)|개체가 `CPictureHolder` 비트맵인지 메타파일인지 아이콘인지 를 알려줍니다.|
|[C픽처 홀더::렌더링](#render)|그림을 렌더링합니다.|
|[C픽처 홀더::세트그림 디스패치](#setpicturedispatch)|개체의 `CPictureHolder` 인터페이스를 `IDispatch` 설정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C픽처 홀더:m_pPict](#m_ppict)|그림 개체에 대한 포인터입니다.|

## <a name="remarks"></a>설명

`CPictureHolder`기본 클래스가 없습니다.

스톡 사진 속성을 사용하여 개발자는 표시할 비트맵, 아이콘 또는 메타파일을 지정할 수 있습니다.

사용자 지정 그림 속성 만들기에 대한 자세한 내용은 [MFC ActiveX 컨트롤: ActiveX 컨트롤에서 그림 사용](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CPictureHolder`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="cpictureholdercpictureholder"></a><a name="cpictureholder"></a>C픽처 홀더::C픽처홀더

`CPictureHolder` 개체를 생성합니다.

```
CPictureHolder();
```

## <a name="cpictureholdercreateempty"></a><a name="createempty"></a>C그림 표시자:빈 만들기

빈 `CPictureHolder` 개체를 만들고 인터페이스에 `IPicture` 연결합니다.

```
BOOL CreateEmpty();
```

### <a name="return-value"></a>Return Value

개체가 성공적으로 생성되면 0이 아닙니다. 그렇지 않으면 0.

## <a name="cpictureholdercreatefrombitmap"></a><a name="createfrombitmap"></a>C픽처 홀더::만들기From비트맵

비트맵을 사용하여 `CPictureHolder`에서 그림 개체를 초기화합니다.

```
BOOL CreateFromBitmap(
    UINT idResource);

BOOL CreateFromBitmap(
    CBitmap* pBitmap,
    CPalette* pPal = NULL,
    BOOL bTransferOwnership = TRUE);

BOOL CreateFromBitmap(
    HBITMAP hbm,
    HPALETTE hpal = NULL,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>매개 변수

*idResource*<br/>
비트맵 리소스의 리소스 ID입니다.

*pBitmap*<br/>
[CBitmap](../../mfc/reference/cbitmap-class.md) 개체에 대한 포인터입니다.

*pPal*<br/>
[CPalette](../../mfc/reference/cpalette-class.md) 개체에 대한 포인터입니다.

*b전송소유권*<br/>
그림 개체가 비트맵 및 팔레트 개체의 소유권을 차지할지 여부를 나타냅니다.

*Hbm*<br/>
개체가 생성되는 비트맵을 처리합니다. `CPictureHolder`

*hpal*<br/>
비트맵을 렌더링하는 데 사용되는 팔레트를 처리합니다.

### <a name="return-value"></a>Return Value

개체가 성공적으로 생성되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

*bTransferOwnershipTRUE인* 경우 호출자는 이 호출이 반환된 후 어떤 방식으로든 비트맵 또는 팔레트 개체를 사용해서는 안 됩니다. *bTransferOwnership이* FALSE이면 호출자는 비트맵 및 팔레트 개체가 그림 개체의 수명 동안 유효한 상태로 유지되도록 할 책임이 있습니다.

## <a name="cpictureholdercreatefromicon"></a><a name="createfromicon"></a>C픽처 홀더::만들기From아이콘

아이콘을 사용하여 `CPictureHolder`에서 그림 개체를 초기화합니다.

```
BOOL CreateFromIcon(
    UINT idResource);

BOOL CreateFromIcon(
    HICON hIcon,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>매개 변수

*idResource*<br/>
비트맵 리소스의 리소스 ID입니다.

*hIcon*<br/>
개체가 생성되는 아이콘을 처리합니다. `CPictureHolder`

*b전송소유권*<br/>
그림 개체가 아이콘 개체의 소유권을 차지할지 여부를 나타냅니다.

### <a name="return-value"></a>Return Value

개체가 성공적으로 생성되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

*bTransferOwnershipTRUE인* 경우 호출자는 이 호출이 반환된 후 어떤 방식으로든 아이콘 개체를 사용해서는 안 됩니다. *bTransferOwnership이* FALSE이면 호출자는 아이콘 개체가 그림 개체의 수명 동안 유효한 상태로 유지되도록 할 책임이 있습니다.

## <a name="cpictureholdercreatefrommetafile"></a><a name="createfrommetafile"></a>C픽처 홀더::생성FromMetafile

메타파일을 사용하여 `CPictureHolder`에서 그림 개체를 초기화합니다.

```
BOOL CreateFromMetafile(
    HMETAFILE hmf,
    int xExt,
    int yExt,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>매개 변수

*흠 (것)흠*<br/>
개체를 만드는 데 사용되는 메타파일을 처리합니다. `CPictureHolder`

*엑스트 (것)에 스펙트 (것*<br/>
사진의 X 범위.

*이엑스트 (것)이*<br/>
사진의 Y 범위.

*b전송소유권*<br/>
그림 개체가 메타파일 개체의 소유권을 차지할지 여부를 나타냅니다.

### <a name="return-value"></a>Return Value

개체가 성공적으로 생성되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

*bTransferOwnershipTRUE인* 경우 호출자는 이 호출이 반환된 후 메타파일 개체를 어떤 식으로든 사용해서는 안 됩니다. *bTransferOwnership이* FALSE이면 호출자는 메타파일 개체가 그림 개체의 수명 동안 유효한 상태로 유지되도록 할 책임이 있습니다.

## <a name="cpictureholdergetdisplaystring"></a><a name="getdisplaystring"></a>C픽처 홀더::GetDisplayString

컨테이너의 속성 브라우저에 표시되는 문자열을 검색합니다.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>매개 변수

*strValue*<br/>
표시 문자열을 보유하는 [CString에](../../atl-mfc-shared/reference/cstringt-class.md) 대한 참조입니다.

### <a name="return-value"></a>Return Value

문자열이 성공적으로 검색되는 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="cpictureholdergetpicturedispatch"></a><a name="getpicturedispatch"></a>C픽처 홀더::GetPicture디스패치

이 함수는 개체의 `CPictureHolder` `IPictureDisp` 인터페이스에 대한 포인터를 반환합니다.

```
LPPICTUREDISP GetPictureDispatch();
```

### <a name="return-value"></a>Return Value

개체의 인터페이스에 `CPictureHolder` 대한 `IPictureDisp` 포인터입니다.

### <a name="remarks"></a>설명

호출자는 이 `Release` 포인터를 완료하면 이 포인터를 호출해야 합니다.

## <a name="cpictureholdergettype"></a><a name="gettype"></a>C픽처 홀더::겟타입

그림이 비트맵인지 메타파일인지 아이콘인지 를 나타냅니다.

```
short GetType();
```

### <a name="return-value"></a>Return Value

그림의 유형을 나타내는 값입니다. 가능한 값과 그 의미는 다음과 같습니다.

|값|의미|
|-----------|-------------|
|PICTYPE_UNINITIALIZED|`CPictureHolder`객체가 통일됩니다.|
|PICTYPE_NONE|`CPictureHolder`개체가 비어 있습니다.|
|PICTYPE_BITMAP|그림은 비트맵입니다.|
|PICTYPE_METAFILE|사진은 메타파일입니다.|
|PICTYPE_ICON|그림은 아이콘입니다.|

## <a name="cpictureholderm_ppict"></a><a name="m_ppict"></a>C픽처 홀더:m_pPict

개체의 인터페이스에 `CPictureHolder` 대한 `IPicture` 포인터입니다.

```
LPPICTURE m_pPict;
```

## <a name="cpictureholderrender"></a><a name="render"></a>C픽처 홀더::렌더링

*rcRender*에서 참조하는 사각형의 그림을 렌더링합니다.

```cpp
void Render(
    CDC* pDC,
    const CRect& rcRender,
    const CRect& rcWBounds);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
그림을 렌더링할 표시 컨텍스트에 대한 포인터입니다.

*rcRender*<br/>
그림을 렌더링할 사각형입니다.

*rcW바운드*<br/>
그림을 렌더링하는 개체의 경계 사각형을 나타내는 사각형입니다. 컨트롤의 경우 이 사각형은 [COleControl::OnDraw](../../mfc/reference/colecontrol-class.md#ondraw)의 재정의에 전달된 *rcBounds* 매개 변수입니다.

## <a name="cpictureholdersetpicturedispatch"></a><a name="setpicturedispatch"></a>C픽처 홀더::세트그림 디스패치

개체를 `CPictureHolder` 인터페이스에 `IPictureDisp` 연결합니다.

```cpp
void SetPictureDispatch(LPPICTUREDISP pDisp);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
새 `IPictureDisp` 인터페이스에 대한 포인터입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFontHolder 클래스](../../mfc/reference/cfontholder-class.md)
