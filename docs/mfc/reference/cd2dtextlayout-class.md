---
title: CD2DTextLayout 클래스
ms.date: 03/27/2019
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
helpviewer_keywords:
- CD2DTextLayout [MFC], CD2DTextLayout
- CD2DTextLayout [MFC], Create
- CD2DTextLayout [MFC], Destroy
- CD2DTextLayout [MFC], Get
- CD2DTextLayout [MFC], GetFontFamilyName
- CD2DTextLayout [MFC], GetLocaleName
- CD2DTextLayout [MFC], IsValid
- CD2DTextLayout [MFC], ReCreate
- CD2DTextLayout [MFC], SetFontFamilyName
- CD2DTextLayout [MFC], SetLocaleName
- CD2DTextLayout [MFC], m_pTextLayout
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
ms.openlocfilehash: 9be4c1134e2f82ceb3af31cbeb1a7d55f4071777
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369033"
---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout 클래스

IDWrite텍스트레이아웃을 위한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D텍스트레이아웃:CD2D텍스트레이아웃](#cd2dtextlayout)|CD2DTextLayout 개체를 생성합니다.|
|[CD2D텍스트레이아웃::~CD2D텍스트레이아웃](#_dtorcd2dtextlayout)|소멸자입니다. D2D 텍스트 레이아웃 개체가 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D텍스트레이아웃:만들기](#create)|CD2D텍스트레이아웃을 만듭니다. [(CD2DResource::만들기](../../mfc/reference/cd2dresource-class.md#create)재정의.)|
|[CD2D텍스트레이아웃::D에스트로이](#destroy)|CD2DTextLayout 개체를 삭제합니다. [(CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy)재정의.)|
|[CD2D텍스트레이아웃::Get](#get)|IDWriteText레이아웃 인터페이스 반환|
|[CD2D텍스트레이아웃:겟폰트패밀리네임](#getfontfamilyname)|지정된 위치에 텍스트의 글꼴 패밀리 이름을 복사합니다.|
|[CD2D텍스트레이아웃:GetLocaleName](#getlocalename)|지정된 위치에서 텍스트의 로캘 이름을 가져옵니다.|
|[CD2D텍스트레이아웃:유효하지 않음](#isvalid)|리소스 유효성 [검사(CD2DResource 재정의::유효합니다.)](../../mfc/reference/cd2dresource-class.md#isvalid)|
|[CD2D텍스트레이아웃::다시 만들기](#recreate)|CD2DText레이아웃을 다시 만듭니다. [(CD2D리소스 재정의::다시 만들기.)](../../mfc/reference/cd2dresource-class.md#recreate)|
|[CD2D텍스트레이아웃:셋폰트패밀리네임](#setfontfamilyname)|지정된 텍스트 범위 내에서 텍스트에 대해 null 종료글꼴 패밀리 이름을 설정합니다.|
|[CD2D텍스트레이아웃::SetLocaleName](#setlocalename)|지정된 텍스트 범위 내에서 텍스트의 로캘 이름을 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2D텍스트레이아웃::연산자 IDWrite텍스트레이아웃*](#operator_idwritetextlayout_star)|IDWriteText레이아웃 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D텍스트레이아웃:m_pTextLayout](#m_ptextlayout)|IDWriteText레이아웃에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

[CD2D텍스트레이아웃](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="_dtorcd2dtextlayout"></a>CD2D텍스트레이아웃::~CD2D텍스트레이아웃

소멸자입니다. D2D 텍스트 레이아웃 개체가 소멸될 때 호출됩니다.

```
virtual ~CD2DTextLayout();
```

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="cd2dtextlayout"></a>CD2D텍스트레이아웃:CD2D텍스트레이아웃

CD2DTextLayout 개체를 생성합니다.

```
CD2DTextLayout(
    CRenderTarget* pParentTarget,
    const CString& strText,
    CD2DTextFormat& textFormat,
    const CD2DSizeF& sizeMax,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*strText*<br/>
새 CD2DTextLayout 개체를 만드는 문자열을 포함 하는 CString 개체입니다.

*textFormat*<br/>
문자열에 적용할 형식을 포함하는 CString 개체입니다.

*크기 최대*<br/>
레이아웃 상자의 크기입니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

## <a name="cd2dtextlayoutcreate"></a><a name="create"></a>CD2D텍스트레이아웃:만들기

CD2D텍스트레이아웃을 만듭니다.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dtextlayoutdestroy"></a><a name="destroy"></a>CD2D텍스트레이아웃::D에스트로이

CD2DTextLayout 개체를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dtextlayoutget"></a><a name="get"></a>CD2D텍스트레이아웃::Get

IDWriteText레이아웃 인터페이스 반환

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 IDWriteTextLayout 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dtextlayoutgetfontfamilyname"></a><a name="getfontfamilyname"></a>CD2D텍스트레이아웃:겟폰트패밀리네임

지정된 위치에 텍스트의 글꼴 패밀리 이름을 복사합니다.

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>매개 변수

*현재 위치*<br/>
검사할 텍스트의 위치입니다.

*Textrange*<br/>
현재위치에 의해 지정된 위치에서 텍스트와 동일한 서식이 있는 텍스트 의 범위입니다. 즉, 실행에는 글꼴 패밀리 이름을 포함하되 이에 국한되지 않는 지정된 위치로 정확한 서식이 있습니다.

### <a name="return-value"></a>Return Value

현재 글꼴 패밀리 이름을 포함하는 CString 개체입니다.

## <a name="cd2dtextlayoutgetlocalename"></a><a name="getlocalename"></a>CD2D텍스트레이아웃:GetLocaleName

지정된 위치에서 텍스트의 로캘 이름을 가져옵니다.

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>매개 변수

*현재 위치*<br/>
검사할 텍스트의 위치입니다.

*Textrange*<br/>
현재위치에 의해 지정된 위치에서 텍스트와 동일한 서식이 있는 텍스트 의 범위입니다. 즉, run은 로캘 이름을 포함하되 이에 국한되지 않는 지정된 위치로 정확한 서식이 있습니다.

### <a name="return-value"></a>Return Value

현재 로캘 이름을 포함하는 CString 개체입니다.

## <a name="cd2dtextlayoutisvalid"></a><a name="isvalid"></a>CD2D텍스트레이아웃:유효하지 않음

리소스 유효성 검사

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Return Value

TRUE 리소스가 유효한 경우; 그렇지 않으면 거짓.

## <a name="cd2dtextlayoutm_ptextlayout"></a><a name="m_ptextlayout"></a>CD2D텍스트레이아웃:m_pTextLayout

IDWriteText레이아웃에 대한 포인터입니다.

```
IDWriteTextLayout* m_pTextLayout;
```

## <a name="cd2dtextlayoutoperator-idwritetextlayout"></a><a name="operator_idwritetextlayout_star"></a>CD2D텍스트레이아웃::연산자 IDWrite텍스트레이아웃*

IDWriteText레이아웃 인터페이스 반환

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 IDWriteTextLayout 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dtextlayoutrecreate"></a><a name="recreate"></a>CD2D텍스트레이아웃::다시 만들기

CD2DText레이아웃을 다시 만듭니다.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dtextlayoutsetfontfamilyname"></a><a name="setfontfamilyname"></a>CD2D텍스트레이아웃:셋폰트패밀리네임

지정된 텍스트 범위 내에서 텍스트에 대해 null 종료글꼴 패밀리 이름을 설정합니다.

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>매개 변수

*pwzFont패밀리네임*<br/>
textRange에 의해 지정된 범위 내의 전체 텍스트 문자열에 적용되는 글꼴 패밀리 이름

*Textrange*<br/>
이 변경이 적용되는 텍스트 범위

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="cd2dtextlayoutsetlocalename"></a><a name="setlocalename"></a>CD2D텍스트레이아웃::SetLocaleName

지정된 텍스트 범위 내에서 텍스트의 로캘 이름을 설정합니다.

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>매개 변수

*pwzLocaleName*<br/>
null-종료된 로캘 이름 문자열

*Textrange*<br/>
이 변경이 적용되는 텍스트 범위

### <a name="return-value"></a>Return Value

메서드가 성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
