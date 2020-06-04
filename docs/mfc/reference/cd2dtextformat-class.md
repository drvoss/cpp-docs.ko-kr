---
title: CD2DTextFormat 클래스
ms.date: 03/27/2019
f1_keywords:
- CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::Create
- AFXRENDERTARGET/CD2DTextFormat::Destroy
- AFXRENDERTARGET/CD2DTextFormat::Get
- AFXRENDERTARGET/CD2DTextFormat::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextFormat::GetLocaleName
- AFXRENDERTARGET/CD2DTextFormat::IsValid
- AFXRENDERTARGET/CD2DTextFormat::ReCreate
- AFXRENDERTARGET/CD2DTextFormat::m_pTextFormat
helpviewer_keywords:
- CD2DTextFormat [MFC], CD2DTextFormat
- CD2DTextFormat [MFC], Create
- CD2DTextFormat [MFC], Destroy
- CD2DTextFormat [MFC], Get
- CD2DTextFormat [MFC], GetFontFamilyName
- CD2DTextFormat [MFC], GetLocaleName
- CD2DTextFormat [MFC], IsValid
- CD2DTextFormat [MFC], ReCreate
- CD2DTextFormat [MFC], m_pTextFormat
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
ms.openlocfilehash: f7310fd3ca2ac34df7cc1a99cd5527ea8ba709c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369041"
---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat 클래스

IDWriteTextFormat에 대한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DTextFormat : public CD2DResource;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CD2D텍스트형식::CD2D텍스트형식](#cd2dtextformat)|CD2DTextFormat 개체를 생성합니다.|
|[CD2D텍스트형식::~CD2D텍스트형식](#_dtorcd2dtextformat)|소멸자입니다. D2D 텍스트 형식 개체가 소멸될 때 호출됩니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CD2D텍스트형식::만들기](#create)|CD2DTextFormat을 만듭니다. [(CD2DResource::만들기](../../mfc/reference/cd2dresource-class.md#create)재정의.)|
|[CD2D텍스트형식::D에스트로이](#destroy)|CD2DTextFormat 개체를 삭제합니다. [(CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy)재정의.)|
|[CD2D텍스트 형식::Get](#get)|IDWriteTextFormat 인터페이스 반환|
|[CD2D텍스트 형식::겟폰트패밀리네임](#getfontfamilyname)|글꼴 패밀리 이름의 복사본을 가져옵니다.|
|[CD2D텍스트 형식::GetLocaleName](#getlocalename)|로캘 이름의 복사본을 가져옵니다.|
|[CD2D텍스트 형식::유효하지 않음](#isvalid)|리소스 유효성 [검사(CD2DResource 재정의::유효합니다.)](../../mfc/reference/cd2dresource-class.md#isvalid)|
|[CD2D텍스트형식::다시 만들기](#recreate)|CD2DTextFormat을 다시 만듭니다. [(CD2D리소스 재정의::다시 만들기.)](../../mfc/reference/cd2dresource-class.md#recreate)|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CD2D텍스트형식::연산자 IDWrite텍스트형식*](#operator_idwritetextformat_star)|IDWriteTextFormat 인터페이스 반환|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CD2D텍스트형식:m_pTextFormat](#m_ptextformat)|IDWriteTextFormat에 대한 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2D자원](../../mfc/reference/cd2dresource-class.md)

[CD2D텍스트형식](../../mfc/reference/cd2dtextformat-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

## <a name="cd2dtextformatcd2dtextformat"></a><a name="_dtorcd2dtextformat"></a>CD2D텍스트형식::~CD2D텍스트형식

소멸자입니다. D2D 텍스트 형식 개체가 소멸될 때 호출됩니다.

```
virtual ~CD2DTextFormat();
```

## <a name="cd2dtextformatcd2dtextformat"></a><a name="cd2dtextformat"></a>CD2D텍스트형식::CD2D텍스트형식

CD2DTextFormat 개체를 생성합니다.

```
CD2DTextFormat(
    CRenderTarget* pParentTarget,
    const CString& strFontFamilyName,
    FLOAT fontSize,
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,
    const CString& strFontLocale = _T(""),
    IDWriteFontCollection* pFontCollection = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*p부모 대상*<br/>
렌더 대상에 대한 포인터입니다.

*스트폰트패밀리네임*<br/>
글꼴 패밀리의 이름을 포함하는 CString 개체입니다.

*Fontsize*<br/>
DIP("장치 독립적 픽셀") 단위의 글꼴의 논리적 크기입니다. DIP는 1/96 인치와 동일합니다.

*Fontweight*<br/>
텍스트 개체의 글꼴 가중치를 나타내는 값입니다.

*Fontstyle*<br/>
텍스트 개체의 글꼴 스타일을 나타내는 값입니다.

*Fontstretch*<br/>
텍스트 개체의 글꼴 스트레치를 나타내는 값입니다.

*스트폰트 로컬*<br/>
로캘 이름을 포함하는 CString 개체입니다.

*p글꼴 컬렉션*<br/>
글꼴 컬렉션 개체에 대한 포인터입니다. NULL이면 시스템 글꼴 컬렉션을 나타냅니다.

*b오토파괴*<br/>
개체가 소유자(pParentTarget)에 의해 소멸됨을 나타냅니다.

## <a name="cd2dtextformatcreate"></a><a name="create"></a>CD2D텍스트형식::만들기

CD2DTextFormat을 만듭니다.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="cd2dtextformatdestroy"></a><a name="destroy"></a>CD2D텍스트형식::D에스트로이

CD2DTextFormat 개체를 삭제합니다.

```
virtual void Destroy();
```

## <a name="cd2dtextformatget"></a><a name="get"></a>CD2D텍스트 형식::Get

IDWriteTextFormat 인터페이스 반환

```
IDWriteTextFormat* Get();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 IDWriteTextFormat 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dtextformatgetfontfamilyname"></a><a name="getfontfamilyname"></a>CD2D텍스트 형식::겟폰트패밀리네임

글꼴 패밀리 이름의 복사본을 가져옵니다.

```
CString GetFontFamilyName() const;
```

### <a name="return-value"></a>Return Value

현재 글꼴 패밀리 이름을 포함하는 CString 개체입니다.

## <a name="cd2dtextformatgetlocalename"></a><a name="getlocalename"></a>CD2D텍스트 형식::GetLocaleName

로캘 이름의 복사본을 가져옵니다.

```
CString GetLocaleName() const;
```

### <a name="return-value"></a>Return Value

현재 로캘 이름을 포함하는 CString 개체입니다.

## <a name="cd2dtextformatisvalid"></a><a name="isvalid"></a>CD2D텍스트 형식::유효하지 않음

리소스 유효성 검사

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Return Value

TRUE 리소스가 유효한 경우; 그렇지 않으면 거짓.

## <a name="cd2dtextformatm_ptextformat"></a><a name="m_ptextformat"></a>CD2D텍스트형식:m_pTextFormat

IDWriteTextFormat에 대한 포인터입니다.

```
IDWriteTextFormat* m_pTextFormat;
```

## <a name="cd2dtextformatoperator-idwritetextformat"></a><a name="operator_idwritetextformat_star"></a>CD2D텍스트형식::연산자 IDWrite텍스트형식*

IDWriteTextFormat 인터페이스 반환

```
operator IDWriteTextFormat*();
```

### <a name="return-value"></a>Return Value

개체가 아직 초기화되지 않은 경우 IDWriteTextFormat 인터페이스 또는 NULL에 대한 포인터입니다.

## <a name="cd2dtextformatrecreate"></a><a name="recreate"></a>CD2D텍스트형식::다시 만들기

CD2DTextFormat을 다시 만듭니다.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Return Value

메서드가 성공하면 S_OK가 반환되고, 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

## <a name="see-also"></a>참고 항목

[클래스](../../mfc/reference/mfc-classes.md)
