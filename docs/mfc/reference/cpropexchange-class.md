---
title: 프롭익스체인지 클래스
ms.date: 11/04/2016
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
helpviewer_keywords:
- CPropExchange [MFC], ExchangeBlobProp
- CPropExchange [MFC], ExchangeFontProp
- CPropExchange [MFC], ExchangePersistentProp
- CPropExchange [MFC], ExchangeProp
- CPropExchange [MFC], ExchangeVersion
- CPropExchange [MFC], GetVersion
- CPropExchange [MFC], IsAsynchronous
- CPropExchange [MFC], IsLoading
ms.assetid: ed872180-e770-4942-892a-92139d501fab
ms.openlocfilehash: 7818b15e502bb32640d6b9dbfe1a6e4927c70650
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363982"
---
# <a name="cpropexchange-class"></a>프롭익스체인지 클래스

OLE 컨트롤의 지속성 구현을 지원합니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE CPropExchange
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPropExchange:::익스체인지블프롭](#exchangeblobprop)|BLOB(이진 대형 개체) 속성을 교환합니다.|
|[CPropExchange:::교환글꼴프롭](#exchangefontprop)|글꼴 속성을 교환합니다.|
|[CPropExchange:::교환 지속적 소품](#exchangepersistentprop)|컨트롤과 파일 간에 속성을 교환합니다.|
|[CPropExchange:::교환소품](#exchangeprop)|기본 제공 형식의 속성을 교환합니다.|
|[CPropExchange::교환버전](#exchangeversion)|OLE 컨트롤의 버전 번호를 교환합니다.|
|[CPropExchange::GetVersion](#getversion)|OLE 컨트롤의 버전 번호를 검색합니다.|
|[CPropExchange::이동기](#isasynchronous)|속성 교환이 비동기적으로 수행되는지 여부를 결정합니다.|
|[CPropExchange::로딩 중](#isloading)|속성이 컨트롤에 로드되는지 아니면 컨트롤에서 저장되는지 여부를 나타냅니다.|

## <a name="remarks"></a>설명

`CPropExchange`기본 클래스가 없습니다.

속성 교환의 컨텍스트와 방향을 설정합니다.

지속성은 컨트롤의 상태 정보를 교환하는 것으로, 일반적으로 컨트롤 자체와 미디어 간에 해당 속성으로 표시됩니다.

프레임워크는 OLE 컨트롤의 속성을 `CPropExchange` 로드하거나 영구 저장소에 저장해야 한다는 알림을 받을 때 파생된 개체를 생성합니다.

프레임워크는 이 `CPropExchange` 개체에 대한 포인터를 `DoPropExchange` 컨트롤의 함수에 전달합니다. 마법사를 사용하여 컨트롤의 시작 파일을 만든 경우 컨트롤의 `DoPropExchange` 함수가 호출됩니다. `COleControl::DoPropExchange` 기본 클래스 버전은 컨트롤의 주식 속성을 교환합니다. 파생 클래스의 버전을 수정하여 컨트롤에 추가한 속성을 교환합니다.

`CPropExchange`컨트롤의 속성을 직렬화하거나 컨트롤의 로드 또는 생성 시 컨트롤의 속성을 초기화하는 데 사용할 수 있습니다. `ExchangeProp` 의 `CPropExchange` `ExchangeFontProp` 및 멤버 함수는 다른 미디어에서 속성을 저장하고 로드할 수 있습니다.

사용에 `CPropExchange`대한 자세한 내용은 [MFC ActiveX 컨트롤: 속성 페이지를](../../mfc/mfc-activex-controls-property-pages.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CPropExchange`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="cpropexchangeexchangeblobprop"></a><a name="exchangeblobprop"></a>CPropExchange:::익스체인지블프롭

이진 큰 개체 (BLOB) 데이터를 저장 하는 속성을 직렬화 합니다.

```
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,
    HGLOBAL* phBlob,
    HGLOBAL hBlobDefault = NULL) = 0;
```

### <a name="parameters"></a>매개 변수

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*phBlob*<br/>
속성이 저장되는 위치를 가리키는 변수에 대한 포인터입니다(변수는 일반적으로 클래스의 멤버입니다).

*hBlobDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성의 값은 *phBlob*에서 참조하는 변수를 적절히 읽거나 작성합니다. *hBlobDefault를* 지정하면 속성의 기본값으로 사용됩니다. 이 값은 어떤 이유로든 컨트롤의 직렬화가 실패하는 경우에 사용됩니다.

함수 는 `CArchivePropExchange::ExchangeBlobProp` `CResetPropExchange::ExchangeBlobProp`이 `CPropsetPropExchange::ExchangeBlobProp` 순수 가상 함수를 재정의합니다.

## <a name="cpropexchangeexchangefontprop"></a><a name="exchangefontprop"></a>CPropExchange:::교환글꼴프롭

저장소 매체와 컨트롤 간에 글꼴 속성을 교환합니다.

```
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC* pFontDesc,
    LPFONTDISP pFontDispAmbient) = 0;
```

### <a name="parameters"></a>매개 변수

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*글꼴*<br/>
글꼴 속성을 포함하는 [CFontHolder](../../mfc/reference/cfontholder-class.md) 개체에 대한 참조입니다.

*pFontDesc*<br/>
*pFontDispAmbient가* NULL일 때 글꼴 속성의 기본 상태를 초기화하기 위한 값을 포함하는 [FONTDESC](/windows/win32/api/olectl/ns-olectl-fontdesc) 구조에 대한 포인터입니다.

*pFontDispAmbient*<br/>
글꼴 속성의 기본 상태를 초기화하는 데 사용할 글꼴 `IFontDisp` 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

글꼴 속성이 매체에서 컨트롤로 로드되는 경우 글꼴의 특성은 매체에서 `CFontHolder` 검색되고 *글꼴에서* 참조하는 개체가 초기화됩니다. 글꼴 속성이 저장되는 경우 글꼴 개체의 특성이 미디어에 기록됩니다.

함수 는 `CArchivePropExchange::ExchangeFontProp` `CResetPropExchange::ExchangeFontProp`이 `CPropsetPropExchange::ExchangeFontProp` 순수 가상 함수를 재정의합니다.

## <a name="cpropexchangeexchangepersistentprop"></a><a name="exchangepersistentprop"></a>CPropExchange:::교환 지속적 소품

컨트롤과 파일 간에 속성을 교환합니다.

```
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,
    LPUNKNOWN* ppUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault) = 0;
```

### <a name="parameters"></a>매개 변수

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*ppunk*<br/>
속성의 `IUnknown` 인터페이스에 대한 포인터를 포함하는 변수에 대한 포인터입니다(이 변수는 일반적으로 클래스의 멤버입니다).

*Iid*<br/>
컨트롤에서 사용할 속성에 있는 인터페이스의 인터페이스 ID입니다.

*pUnkDefault*<br/>
속성의 기본값입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성이 파일에서 컨트롤로 로드되는 경우 속성이 만들어지고 파일에서 초기화됩니다. 속성이 저장되는 경우 해당 값이 파일에 기록됩니다.

함수 는 `CArchivePropExchange::ExchangePersistentProp` `CResetPropExchange::ExchangePersistentProp`이 `CPropsetPropExchange::ExchangePersistentProp` 순수 가상 함수를 재정의합니다.

## <a name="cpropexchangeexchangeprop"></a><a name="exchangeprop"></a>CPropExchange:::교환소품

저장소 매체와 컨트롤 간에 속성을 교환합니다.

```
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,
    VARTYPE vtProp,
    void* pvProp,
    const void* pvDefault = NULL) = 0 ;
```

### <a name="parameters"></a>매개 변수

*pszPropName*<br/>
교환되는 숙소의 이름입니다.

*vtProp*<br/>
교환되는 속성의 유형을 지정하는 기호입니다. 가능한 값은 다음과 같습니다.

|기호|속성 유형|
|------------|-------------------|
|VT_I2|**short**|
|VT_I4|**긴**|
|VT_BOOL|**Bool**|
|VT_BSTR|`CString`|
|VT_CY|**CY**|
|VT_R4|**플 로트**|
|VT_R8|**double**|

*pvProp*<br/>
속성 값에 대한 포인터입니다.

*pvDefault*<br/>
속성의 기본값에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

교환이 성공한 경우 비영; 0이 실패하면

### <a name="remarks"></a>설명

속성이 매매체에서 컨트롤로 로드되는 경우 속성 값은 매체에서 검색되어 *pvProp이*가리키는 개체에 저장됩니다. 속성이 매체에 저장되는 경우 *pvProp이* 가리키는 개체의 값이 매체에 기록됩니다.

함수 는 `CArchivePropExchange::ExchangeProp` `CResetPropExchange::ExchangeProp`이 `CPropsetPropExchange::ExchangeProp` 순수 가상 함수를 재정의합니다.

## <a name="cpropexchangeexchangeversion"></a><a name="exchangeversion"></a>CPropExchange::교환버전

버전 번호의 지속성을 처리하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,
    DWORD dwVersionDefault,
    BOOL bConvert);
```

### <a name="parameters"></a>매개 변수

*dw버전로드*<br/>
로드되는 영구 데이터의 버전 번호가 저장되는 변수를 참조합니다.

*dwVersionDefault*<br/>
컨트롤의 현재 버전 번호입니다.

*bConvert*<br/>
영구 데이터를 현재 버전으로 변환할지 아니면 로드된 것과 동일한 버전으로 유지할지 여부를 나타냅니다.

### <a name="return-value"></a>Return Value

함수가 성공한 경우 비영; 0 그렇지 않으면.

## <a name="cpropexchangegetversion"></a><a name="getversion"></a>CPropExchange::GetVersion

이 함수를 호출하여 컨트롤의 버전 번호를 검색합니다.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Return Value

컨트롤의 버전 번호입니다.

## <a name="cpropexchangeisasynchronous"></a><a name="isasynchronous"></a>CPropExchange::이동기

속성 교환이 비동기적으로 수행되는지 여부를 결정합니다.

```
BOOL IsAsynchronous();
```

### <a name="return-value"></a>Return Value

속성이 비동기적으로 교환되는 경우 TRUE를 반환합니다( 그렇지 않으면 FALSE).

## <a name="cpropexchangeisloading"></a><a name="isloading"></a>CPropExchange::로딩 중

이 함수를 호출하여 속성이 컨트롤에 로드되는지 아니면 컨트롤에서 저장되는지 확인합니다.

```
BOOL IsLoading();
```

### <a name="return-value"></a>Return Value

속성이 로드되는 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)
