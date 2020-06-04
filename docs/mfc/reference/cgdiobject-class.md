---
title: CGdiObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
helpviewer_keywords:
- CGdiObject [MFC], CGdiObject
- CGdiObject [MFC], Attach
- CGdiObject [MFC], CreateStockObject
- CGdiObject [MFC], DeleteObject
- CGdiObject [MFC], DeleteTempMap
- CGdiObject [MFC], Detach
- CGdiObject [MFC], FromHandle
- CGdiObject [MFC], GetObject
- CGdiObject [MFC], GetObjectType
- CGdiObject [MFC], GetSafeHandle
- CGdiObject [MFC], UnrealizeObject
- CGdiObject [MFC], m_hObject
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
ms.openlocfilehash: 0cd7a0e0ed500ee9394b00e8906640e9f950163b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373735"
---
# <a name="cgdiobject-class"></a>CGdiObject 클래스

비트맵, 영역, 브러시, 펜, 색상표와 글꼴 등 다양한 Windows GDI(그래픽 디바이스 인터페이스) 개체에 기본 클래스를 제공합니다.

## <a name="syntax"></a>구문

```
class CGdiObject : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CGdiObject::CGdiObject](#cgdiobject)|`CGdiObject` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CGdiObject::연결](#attach)|Windows GDI 개체를 개체에 연결합니다. `CGdiObject`|
|[CGdiObject::만들기스톡오브젝트](#createstockobject)|미리 정의된 스톡 펜, 브러시 또는 글꼴 중 하나에 대한 핸들을 검색합니다.|
|[CGdiObject::DeleteObject](#deleteobject)|개체와 연결된 모든 시스템 저장소를 해제하여 메모리에서 `CGdiObject` 개체에 연결된 Windows GDI 개체를 삭제합니다.|
|[CGdiObject::DeleteTempMap](#deletetempmap)|에서 만든 `CGdiObject` 임시 개체를 삭제합니다. `FromHandle`|
|[CGdiObject::D에타흐](#detach)|개체에서 `CGdiObject` Windows GDI 개체를 분리 하 고 Windows GDI 개체에 핸들을 반환 합니다.|
|[CGdiObject::From핸들](#fromhandle)|Windows GDI `CGdiObject` 개체에 핸들이 지정된 개체에 대한 포인터를 반환합니다.|
|[CGdiObject::GetObject](#getobject)|개체에 연결된 Windows GDI 개체를 설명하는 데이터로 `CGdiObject` 버퍼를 채웁니다.|
|[CGdiObject::GetObjectType](#getobjecttype)|GDI 개체의 형식을 검색합니다.|
|[CGdiObject::GetSafeHandle](#getsafehandle)|`m_hObject` **NULL이** 아니면 NULL이 반환됩니다.|
|[CGdiObject::실현되지 않은 대상](#unrealizeobject)|브러시의 원심을 재설정하거나 논리 팔레트를 재설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CGdiObject::연산자 !=](#operator_neq)|두 GDI 개체가 논리적으로 같지 않은지 확인합니다.|
|[CGdiObject::연산자 ==](#operator_eq_eq)|두 GDI 개체가 논리적으로 동일한지 확인합니다.|
|[CGdiObject::연산자 HGDIOBJ](#operator_hgdiobj)|연결된 Windows GDI 개체에 대한 핸들을 검색합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CGdiObject::m_hObject](#m_hobject)|이 개체에 연결된 HBITMAP, HPALETTE, HRGN, HBRUSH, HPEN 또는 HFONT를 포함하는 핸들입니다.|

## <a name="remarks"></a>설명

직접 만들지 `CGdiObject` 않습니다. 대신 `CPen` 또는 와 `CBrush`같은 파생 클래스 중 하나에서 개체를 만듭니다.

자세한 `CGdiObject`내용은 그래픽 [개체](../../mfc/graphic-objects.md)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CGdiObject`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cgdiobjectattach"></a><a name="attach"></a>CGdiObject::연결

Windows GDI 개체를 개체에 연결합니다. `CGdiObject`

```
BOOL Attach(HGDIOBJ hObject);
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
Windows GDI 개체에 대한 핸들(예: HPEN 또는 HBRUSH)입니다.

### <a name="return-value"></a>Return Value

첨부 파일이 성공하면 0이 아닙니다. 그렇지 않으면 0.

## <a name="cgdiobjectcgdiobject"></a><a name="cgdiobject"></a>CGdiObject::CGdiObject

`CGdiObject` 개체를 생성합니다.

```
CGdiObject();
```

### <a name="remarks"></a>설명

직접 만들지 `CGdiObject` 않습니다. 대신 `CPen` 또는 와 `Cbrush`같은 파생 클래스 중 하나에서 개체를 만듭니다.

## <a name="cgdiobjectcreatestockobject"></a><a name="createstockobject"></a>CGdiObject::만들기스톡오브젝트

미리 정의된 스톡 Windows GDI 펜, 브러쉬 또는 글꼴 중 하나에 대한 핸들을 검색하고 `CGdiObject` GDI 개체를 개체에 연결합니다.

```
BOOL CreateStockObject(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
원하는 스톡 개체의 유형을 지정하는 상수입니다. 적절한 값에 대한 설명은 Windows SDK의 [GetStockObject에](/windows/win32/api/wingdi/nf-wingdi-getstockobject) 대한 매개 변수 *fnObject를* 참조하십시오.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수를 Stock 펜과 같은 `CPen` Windows GDI 개체 유형에 해당하는 파생 클래스 중 하나를 사용하여 호출합니다.

## <a name="cgdiobjectdeleteobject"></a><a name="deleteobject"></a>CGdiObject::DeleteObject

Windows GDI 개체와 연결된 모든 시스템 저장소를 해제하여 메모리에서 연결된 Windows GDI 개체를 삭제합니다.

```
BOOL DeleteObject();
```

### <a name="return-value"></a>Return Value

GDI 개체가 성공적으로 삭제된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

`CGdiObject` 개체와 연결된 저장소는 이 호출의 영향을 받지 않습니다. 응용 프로그램은 현재 `DeleteObject` 장치 `CGdiObject` 컨텍스트로 선택된 개체를 호출해서는 안 됩니다.

패턴 브러시가 삭제되면 브러시와 연결된 비트맵이 삭제되지 않습니다. 비트맵은 독립적으로 삭제해야 합니다.

## <a name="cgdiobjectdeletetempmap"></a><a name="deletetempmap"></a>CGdiObject::DeleteTempMap

`CWinApp` 유휴 시간 처리기에 의해 `DeleteTempMap` 자동으로 호출되어 `CGdiObject` `FromHandle`에서 만든 임시 개체를 삭제합니다.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>설명

`DeleteTempMap`개체를 삭제하기 전에 임시 `CGdiObject` 개체에 연결된 Windows GDI 개체를 분리합니다. `CGdiObject`

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]

## <a name="cgdiobjectdetach"></a><a name="detach"></a>CGdiObject::D에타흐

개체에서 `CGdiObject` Windows GDI 개체를 분리 하 고 Windows GDI 개체에 핸들을 반환 합니다.

```
HGDIOBJ Detach();
```

### <a name="return-value"></a>Return Value

A를 `HANDLE` Windows GDI 개체에 분리; 그렇지 않으면 GDI 개체가 연결되지 않은 경우 NULL입니다.

## <a name="cgdiobjectfromhandle"></a><a name="fromhandle"></a>CGdiObject::From핸들

Windows GDI `CGdiObject` 개체에 핸들이 지정된 개체에 대한 포인터를 반환합니다.

```
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```

### <a name="parameters"></a>매개 변수

*h개체*<br/>
Windows GDI 개체에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

일시적이거나 `CGdiObject` 영구적일 수 있는 포인터입니다.

### <a name="remarks"></a>설명

개체가 `CGdiObject` Windows GDI 개체에 아직 연결되어 있지 `CGdiObject` 않으면 임시 개체가 만들어지고 첨부됩니다.

이 `CGdiObject` 임시 개체는 다음에 응용 프로그램이 이벤트 루프에서 유휴 시간을 가지며 모든 임시 그래픽 개체가 삭제될 때까지만 유효합니다. 이 것을 말하는 또 다른 방법은 임시 개체가 하나의 창 메시지를 처리하는 동안에만 유효하다는 것입니다.

## <a name="cgdiobjectgetobject"></a><a name="getobject"></a>CGdiObject::GetObject

지정된 개체를 정의하는 데이터로 버퍼를 채웁니다.

```
int GetObject(
    int nCount,
    LPVOID lpObject) const;
```

### <a name="parameters"></a>매개 변수

*nCount*<br/>
*lpObject* 버퍼에 복사할 바이트 수를 지정합니다.

*lpObject*<br/>
정보를 수신할 사용자 제공 버퍼를 가리킵니다.

### <a name="return-value"></a>Return Value

검색된 바이트 수입니다. 그렇지 않으면 0오류가 발생하는 경우.

### <a name="remarks"></a>설명

함수는 다음 목록에서 볼 수 있는 그래픽 개체의 형식에 따라 형식이 달라지는 데이터 구조를 검색합니다.

|Object|버퍼 유형|
|------------|-----------------|
|`CPen`|[로그펜 (것)과 함께](/windows/win32/api/Wingdi/ns-wingdi-logpen)|
|`CBrush`|[로그 브러시](/windows/win32/api/wingdi/ns-wingdi-logbrush)|
|`CFont`|[Logfont](/windows/win32/api/wingdi/ns-wingdi-logfontw)|
|`CBitmap`|[비트맵](/windows/win32/api/wingdi/ns-wingdi-bitmap)|
|`CPalette`|WORD|
|`CRgn`|지원 안 함|

개체가 개체인 `CBitmap` 경우 `GetObject` 비트맵의 너비, 높이 및 색상 형식 정보만 반환합니다. 실제 비트는 [CBitmap::GetBitmapBits를](../../mfc/reference/cbitmap-class.md#getbitmapbits)사용하여 검색할 수 있습니다.

개체가 개체인 `CPalette` 경우 `GetObject` 팔레트의 항목 수를 지정하는 WORD를 검색합니다. 이 함수는 팔레트를 정의하는 [LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette) 구조를 검색하지 않습니다. 응용 프로그램은 [CPalette::GetPaletteEntry를](../../mfc/reference/cpalette-class.md#getpaletteentries)호출하여 팔레트 항목에 대한 정보를 얻을 수 있습니다.

## <a name="cgdiobjectgetobjecttype"></a><a name="getobjecttype"></a>CGdiObject::GetObjectType

GDI 개체의 형식을 검색합니다.

```
UINT GetObjectType() const;
```

### <a name="return-value"></a>Return Value

성공한 경우 개체의 형식입니다. 그렇지 않으면 0. 이 값은

- OBJ_BITMAP 비트맵

- OBJ_BRUSH 브러쉬

- OBJ_FONT 글꼴

- OBJ_PAL 팔레트

- OBJ_PEN 펜

- OBJ_EXTPEN 확장 펜

- OBJ_REGION Region

- 장치 컨텍스트 OBJ_DC

- OBJ_MEMDC 메모리 장치 컨텍스트

- OBJ_METAFILE 메타파일

- OBJ_METADC 메타파일 장치 컨텍스트

- 향상된 메타파일 OBJ_ENHMETAFILE

- 향상된 메타파일 장치 컨텍스트OBJ_ENHMETADC

## <a name="cgdiobjectgetsafehandle"></a><a name="getsafehandle"></a>CGdiObject::GetSafeHandle

`m_hObject` **NULL이** 아니면 NULL이 반환됩니다.

```
HGDIOBJ GetSafeHandle() const;
```

### <a name="return-value"></a>Return Value

연결된 Windows GDI 개체에 대한 핸들; 그렇지 않으면 개체가 연결되지 않은 경우 NULL입니다.

### <a name="remarks"></a>설명

이는 일반적인 핸들 인터페이스 패러다임의 일부이며 NULL이 핸들에 대해 유효하거나 특별한 값인 경우에 유용합니다.

### <a name="example"></a>예제

  [CWnd::IsWindowEnabled에](../../mfc/reference/cwnd-class.md#iswindowenabled)대한 예제를 참조하십시오.

## <a name="cgdiobjectm_hobject"></a><a name="m_hobject"></a>CGdiObject::m_hObject

이 개체에 연결된 HBITMAP, HRGN, HBRUSH, HPEN, HPALETTE 또는 HFONT를 포함하는 핸들입니다.

```
HGDIOBJ m_hObject;
```

## <a name="cgdiobjectoperator-"></a><a name="operator_neq"></a>CGdiObject::연산자 !=

두 GDI 개체가 논리적으로 같지 않은지 확인합니다.

```
BOOL operator!=(const CGdiObject& obj) const;
```

### <a name="parameters"></a>매개 변수

*obj*<br/>
기존 `CGdiObject`에 대한 포인터입니다.

### <a name="remarks"></a>설명

왼쪽의 GDI 객체가 오른쪽의 GDI 오브젝트와 같지 않은지 확인합니다.

## <a name="cgdiobjectoperator-"></a><a name="operator_eq_eq"></a>CGdiObject::연산자 ==

두 GDI 개체가 논리적으로 동일한지 확인합니다.

```
BOOL operator==(const CGdiObject& obj) const;
```

### <a name="parameters"></a>매개 변수

*obj*<br/>
기존 `CGdiObject`에 대한 참조입니다.

### <a name="remarks"></a>설명

왼쪽에 있는 GDI 객체가 오른쪽에 있는 GDI 오브젝트와 같은지 결정합니다.

## <a name="cgdiobjectoperator-hgdiobj"></a><a name="operator_hgdiobj"></a>CGdiObject::연산자 HGDIOBJ

연결된 Windows GDI 개체에 대한 핸들을 검색합니다. 그렇지 않으면 개체가 연결되지 않은 경우 NULL입니다.

```
operator HGDIOBJ() const;
```

## <a name="cgdiobjectunrealizeobject"></a><a name="unrealizeobject"></a>CGdiObject::실현되지 않은 대상

브러시의 원심을 재설정하거나 논리 팔레트를 재설정합니다.

```
BOOL UnrealizeObject();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

클래스의 멤버 `UnrealizeObject` 함수이지만 개체 `CBrush` 또는 `CPalette` 개체에서만 호출해야 합니다. `CGdiObject`

개체의 `CBrush` `UnrealizeObject` 경우 다음에 장치 컨텍스트로 선택할 때 지정된 브러시의 원점을 재설정하도록 시스템을 지시합니다. 개체가 개체인 `CPalette` 경우 `UnrealizeObject` 이전에 실현되지 않은 것처럼 팔레트를 실현하도록 시스템을 지시합니다. 다음에 응용 프로그램이 지정된 팔레트에 대해 [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) 함수를 호출할 때 시스템은 논리 팔레트를 시스템 팔레트에 완전히 다시 매핑합니다.

이 `UnrealizeObject` 함수는 스톡 개체와 함께 사용해서는 안 됩니다. 새 `UnrealizeObject` 브러시 원점이 설정될 때마다 이 함수를 호출해야 합니다(CDC:SetBrushOrg 함수). [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) 현재 `UnrealizeObject` 선택된 브러시 또는 현재 선택된 디스플레이 컨텍스트 팔레트에 대해 함수를 호출해서는 안 됩니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C비트맵 클래스](../../mfc/reference/cbitmap-class.md)<br/>
[C브러시 클래스](../../mfc/reference/cbrush-class.md)<br/>
[C폰트 클래스](../../mfc/reference/cfont-class.md)<br/>
[C팔레트 클래스](../../mfc/reference/cpalette-class.md)<br/>
[CPen 클래스](../../mfc/reference/cpen-class.md)<br/>
[CRgn 클래스](../../mfc/reference/crgn-class.md)
