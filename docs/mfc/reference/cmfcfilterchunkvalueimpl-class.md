---
title: CMFCFilterChunkValueImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl
- AFXWIN/CMFCFilterChunkValueImpl::Clear
- AFXWIN/CMFCFilterChunkValueImpl::CopyChunk
- AFXWIN/CMFCFilterChunkValueImpl::CopyFrom
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkGUID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkPID
- AFXWIN/CMFCFilterChunkValueImpl::GetChunkType
- AFXWIN/CMFCFilterChunkValueImpl::GetString
- AFXWIN/CMFCFilterChunkValueImpl::GetValue
- AFXWIN/CMFCFilterChunkValueImpl::GetValueNoAlloc
- AFXWIN/CMFCFilterChunkValueImpl::IsValid
- AFXWIN/CMFCFilterChunkValueImpl::SetBoolValue
- AFXWIN/CMFCFilterChunkValueImpl::SetDwordValue
- AFXWIN/CMFCFilterChunkValueImpl::SetFileTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetInt64Value
- AFXWIN/CMFCFilterChunkValueImpl::SetIntValue
- AFXWIN/CMFCFilterChunkValueImpl::SetLongValue
- AFXWIN/CMFCFilterChunkValueImpl::SetSystemTimeValue
- AFXWIN/CMFCFilterChunkValueImpl::SetTextValue
- AFXWIN/CMFCFilterChunkValueImpl::SetChunk
helpviewer_keywords:
- CMFCFilterChunkValueImpl [MFC], CMFCFilterChunkValueImpl
- CMFCFilterChunkValueImpl [MFC], Clear
- CMFCFilterChunkValueImpl [MFC], CopyChunk
- CMFCFilterChunkValueImpl [MFC], CopyFrom
- CMFCFilterChunkValueImpl [MFC], GetChunkGUID
- CMFCFilterChunkValueImpl [MFC], GetChunkPID
- CMFCFilterChunkValueImpl [MFC], GetChunkType
- CMFCFilterChunkValueImpl [MFC], GetString
- CMFCFilterChunkValueImpl [MFC], GetValue
- CMFCFilterChunkValueImpl [MFC], GetValueNoAlloc
- CMFCFilterChunkValueImpl [MFC], IsValid
- CMFCFilterChunkValueImpl [MFC], SetBoolValue
- CMFCFilterChunkValueImpl [MFC], SetDwordValue
- CMFCFilterChunkValueImpl [MFC], SetFileTimeValue
- CMFCFilterChunkValueImpl [MFC], SetInt64Value
- CMFCFilterChunkValueImpl [MFC], SetIntValue
- CMFCFilterChunkValueImpl [MFC], SetLongValue
- CMFCFilterChunkValueImpl [MFC], SetSystemTimeValue
- CMFCFilterChunkValueImpl [MFC], SetTextValue
- CMFCFilterChunkValueImpl [MFC], SetChunk
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
ms.openlocfilehash: c89d41f7db43d9504bfc22cbf35a59fcceb511e2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752368"
---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl 클래스

청크 및 속성 값 쌍 논리를 단순화 하는 클래스입니다.

## <a name="syntax"></a>구문

```
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC필터청크밸류임플::~CMFC필터청크밸류심플](#_dtorcmfcfilterchunkvalueimpl)|개체를 소멸시입니다.|
|[CMFC필터청크밸류임플::CMFC필터청크밸류임플](#cmfcfilterchunkvalueimpl)|개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC필터청크밸류임플::클리어](#clear)|청크밸값을 지웁히 바웁습니다.|
|[CMFC필터청크밸류임플::카피청크](#copychunk)|이 청크를 청크의 특성을 설명하는 구조에 복사합니다.|
|[CMFC필터청크밸류임플::복사에서](#copyfrom)|이 청크 값을 다른 값에서 초기화합니다.|
|[CMFC필터청크밸류임플::겟청크GUID](#getchunkguid)|청크 GUID를 검색합니다.|
|[CMFC필터청크밸류임플::겟청크피드](#getchunkpid)|청크 PID(속성 ID)를 검색합니다.|
|[CMFC필터청크밸류임플::겟청크타입](#getchunktype)|청크 유형을 가져옵니다.|
|[CMFC필터청크밸류임플::겟스트링](#getstring)|문자열 값을 검색합니다.|
|[CMFC필터청크밸류임플::겟값](#getvalue)|할당된 propvariant으로 값을 검색합니다.|
|[CMFC필터청크밸류임플::겟밸류노알록](#getvaluenoalloc)|할당되지 않은(내부 값) 값을 반환합니다.|
|[CMFC필터청크밸류임플::유효하지 않음](#isvalid)|이 속성 값이 유효한지 여부를 확인합니다.|
|[CMFC필터청크밸류임플::세트불밸류](#setboolvalue)|오버로드되었습니다. 부울에 대한 키로 속성을 설정합니다.|
|[CMFC필터청크밸류임플::세트워드밸류](#setdwordvalue)|DWORD에 키로 속성을 설정합니다.|
|[CMFC필터청크밸류임플::세트파일타임값](#setfiletimevalue)|파일 시간으로 키별로 속성을 설정합니다.|
|[CMFC필터청크밸류임플::SetInt64Value](#setint64value)|int64에 키로 속성을 설정합니다.|
|[CMFC필터청크밸류임플::셋인트밸류](#setintvalue)|int에 키로 속성을 설정합니다.|
|[CMFC필터청크밸류임플::세트롱값](#setlongvalue)|속성키를 LONG으로 설정합니다.|
|[CMFC필터청크밸류임플::셋시스템타임값](#setsystemtimevalue)|SystemTime에 키로 속성을 설정합니다.|
|[CMFC필터청크밸류임플::세트텍스트값](#settextvalue)|유니코드 문자열에 대한 키별로 속성을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC필터청크밸류임플::세트청크](#setchunk)|청크의 공통 속성을 설정하는 도우미 함수입니다.|

## <a name="remarks"></a>설명

사용하려면 올바른 종류의 CMFCFilterChunkValueImpl 클래스를 생성하기만 하면 됩니다.

예:

CMFC필터청크블심플청크;

hr = 청크. SetBoolValue (PKEY_IsAttachment, true);

또는

hr = 청크. SetFileTimeValue (PKEY_ItemDate, ftLastModified);

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ATL::IFilterChunkValue`

[CMFC필터청크블밸류임플](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cmfcfilterchunkvalueimplclear"></a><a name="clear"></a>CMFC필터청크밸류임플::클리어

청크밸값을 지웁히 바웁습니다.

```cpp
void Clear();
```

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="cmfcfilterchunkvalueimpl"></a>CMFC필터청크밸류임플::CMFC필터청크밸류임플

개체를 생성합니다.

```
CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="_dtorcmfcfilterchunkvalueimpl"></a>CMFC필터청크밸류임플::~CMFC필터청크밸류심플

개체를 소멸시입니다.

```
virtual ~CMFCFilterChunkValueImpl();
```

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplcopychunk"></a><a name="copychunk"></a>CMFC필터청크밸류임플::카피청크

이 청크를 청크의 특성을 설명하는 구조에 복사합니다.

```
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```

### <a name="parameters"></a>매개 변수

*pStat청크*<br/>
청크의 특성을 설명하는 대상 값에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplcopyfrom"></a><a name="copyfrom"></a>CMFC필터청크밸류임플::복사에서

이 청크 값을 다른 값에서 초기화합니다.

```cpp
void CopyFrom (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
복사할 소스 값을 지정합니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplgetchunkguid"></a><a name="getchunkguid"></a>CMFC필터청크밸류임플::겟청크GUID

청크 GUID를 검색합니다.

```
REFGUID GetChunkGUID() const;
```

### <a name="return-value"></a>Return Value

청크를 식별하는 GUID에 대한 참조입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplgetchunkpid"></a><a name="getchunkpid"></a>CMFC필터청크밸류임플::겟청크피드

청크 PID(속성 ID)를 검색합니다.

```
DWORD GetChunkPID() const;
```

### <a name="return-value"></a>Return Value

속성 ID를 포함하는 DWORD 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplgetchunktype"></a><a name="getchunktype"></a>CMFC필터청크밸류임플::겟청크타입

청크 유형을 검색합니다.

```
CHUNKSTATE GetChunkType() const;
```

### <a name="return-value"></a>Return Value

현재 청크가 텍스트 형식 속성인지 값 형식 속성인지를 지정하는 CHUNKSTATE 를 유의한 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplgetstring"></a><a name="getstring"></a>CMFC필터청크밸류임플::겟스트링

문자열 값을 검색합니다.

```
CString &GetString();
```

### <a name="return-value"></a>Return Value

청크 값을 포함하는 문자열입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplgetvalue"></a><a name="getvalue"></a>CMFC필터청크밸류임플::겟값

할당된 propvariant으로 값을 검색합니다.

```
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```

### <a name="parameters"></a>매개 변수

*ppPropVariant*<br/>
함수가 반환되면 이 매개 변수에는 청크 값이 포함됩니다.

### <a name="return-value"></a>Return Value

propVARIANT이 성공적으로 할당되고 청크 값이 *ppPropVariant에*성공적으로 복사된 경우 S_OK. 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplgetvaluenoalloc"></a><a name="getvaluenoalloc"></a>CMFC필터청크밸류임플::겟밸류노알록

할당되지 않은(내부 값) 값을 반환합니다.

```
PROPVARIANT GetValueNoAlloc ();
```

### <a name="return-value"></a>Return Value

현재 청크 값을 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplisvalid"></a><a name="isvalid"></a>CMFC필터청크밸류임플::유효하지 않음

이 속성 값이 유효한지 여부를 확인합니다.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Return Value

TRUE 현재 청크 값이 유효한 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplsetboolvalue"></a><a name="setboolvalue"></a>CMFC필터청크밸류임플::세트불밸류

오버로드되었습니다. 부울에 대한 키로 속성을 설정합니다.

```
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,
    VARIANT_BOOL bVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*b발 (것)들*<br/>
설정할 청크 값을 지정합니다.

*청크 타입*<br/>
플래그는 이 청크에 텍스트 형식 또는 값 형식 속성이 포함되어 있는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져온 값입니다.

*locale*<br/>
텍스트 청크와 관련된 언어 및 하위 언어입니다. 청크 로캘은 문서 인덱서에서 텍스트의 적절한 단어 나누기를 수행하는 데 사용됩니다. 청크가 텍스트 형식이나 데이터 형식VT_LPWSTR VT_LPSTR 또는 VT_BSTR 있는 값 형식이 아니면 이 필드는 무시됩니다.

*cwcLen소스*<br/>
현재 청크가 파생된 원본 텍스트의 문자 길이입니다. 0 값은 원본 텍스트와 파생 된 텍스트 간의 문자별 대응을 의미합니다. 영하지 않은 값은 그러한 직접적인 대응이 존재하지 않는다는 것을 의미합니다.

*cwcStartSource*<br/>
파생 된 청크에 대 한 소스 텍스트가 소스 청크에서 시작 되는 오프셋입니다.

*청크브레이크 타입*<br/>
이전 청크와 현재 청크를 구분하는 나누기 유형입니다. 값은 CHUNK_BREAKTYPE 열거형에서 나온 값입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplsetchunk"></a><a name="setchunk"></a>CMFC필터청크밸류임플::세트청크

청크의 공통 속성을 설정하는 도우미 함수입니다.

```
HRESULT SetChunk(
    REFPROPERTYKEY pkey,
    CHUNKSTATE chunkType=CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*청크 타입*<br/>
플래그는 이 청크에 텍스트 형식 또는 값 형식 속성이 포함되어 있는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져온 값입니다.

*locale*<br/>
텍스트 청크와 관련된 언어 및 하위 언어입니다. 청크 로캘은 문서 인덱서에서 텍스트의 적절한 단어 나누기를 수행하는 데 사용됩니다. 청크가 텍스트 형식이나 데이터 형식VT_LPWSTR VT_LPSTR 또는 VT_BSTR 있는 값 형식이 아니면 이 필드는 무시됩니다.

*cwcLen소스*<br/>
현재 청크가 파생된 원본 텍스트의 문자 길이입니다. 0 값은 원본 텍스트와 파생 된 텍스트 간의 문자별 대응을 의미합니다. 영하지 않은 값은 그러한 직접적인 대응이 존재하지 않는다는 것을 의미합니다.

*cwcStartSource*<br/>
파생 된 청크에 대 한 소스 텍스트가 소스 청크에서 시작 되는 오프셋입니다.

*청크브레이크 타입*<br/>
이전 청크와 현재 청크를 구분하는 나누기 유형입니다. 값은 CHUNK_BREAKTYPE 열거형에서 나온 값입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류 코드.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplsetdwordvalue"></a><a name="setdwordvalue"></a>CMFC필터청크밸류임플::세트워드밸류

DWORD에 키로 속성을 설정합니다.

```
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,
    DWORD dwVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*dwVal*<br/>
설정할 청크 값을 지정합니다.

*청크 타입*<br/>
플래그는 이 청크에 텍스트 형식 또는 값 형식 속성이 포함되어 있는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져온 값입니다.

*locale*<br/>
텍스트 청크와 관련된 언어 및 하위 언어입니다. 청크 로캘은 문서 인덱서에서 텍스트의 적절한 단어 나누기를 수행하는 데 사용됩니다. 청크가 텍스트 형식이나 데이터 형식VT_LPWSTR VT_LPSTR 또는 VT_BSTR 있는 값 형식이 아니면 이 필드는 무시됩니다.

*cwcLen소스*<br/>
현재 청크가 파생된 원본 텍스트의 문자 길이입니다. 0 값은 원본 텍스트와 파생 된 텍스트 간의 문자별 대응을 의미합니다. 영하지 않은 값은 그러한 직접적인 대응이 존재하지 않는다는 것을 의미합니다.

*cwcStartSource*<br/>
파생 된 청크에 대 한 소스 텍스트가 소스 청크에서 시작 되는 오프셋입니다.

*청크브레이크 타입*<br/>
이전 청크와 현재 청크를 구분하는 나누기 유형입니다. 값은 CHUNK_BREAKTYPE 열거형에서 나온 값입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplsetfiletimevalue"></a><a name="setfiletimevalue"></a>CMFC필터청크밸류임플::세트파일타임값

파일 시간으로 키별로 속성을 설정합니다.

```
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,
    FILETIME dtVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*dtVal*<br/>
설정할 청크 값을 지정합니다.

*청크 타입*<br/>
플래그는 이 청크에 텍스트 형식 또는 값 형식 속성이 포함되어 있는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져온 값입니다.

*locale*<br/>
텍스트 청크와 관련된 언어 및 하위 언어입니다. 청크 로캘은 문서 인덱서에서 텍스트의 적절한 단어 나누기를 수행하는 데 사용됩니다. 청크가 텍스트 형식이나 데이터 형식VT_LPWSTR VT_LPSTR 또는 VT_BSTR 있는 값 형식이 아니면 이 필드는 무시됩니다.

*cwcLen소스*<br/>
현재 청크가 파생된 원본 텍스트의 문자 길이입니다. 0 값은 원본 텍스트와 파생 된 텍스트 간의 문자별 대응을 의미합니다. 영하지 않은 값은 그러한 직접적인 대응이 존재하지 않는다는 것을 의미합니다.

*cwcStartSource*<br/>
파생 된 청크에 대 한 소스 텍스트가 소스 청크에서 시작 되는 오프셋입니다.

*청크브레이크 타입*<br/>
이전 청크와 현재 청크를 구분하는 나누기 유형입니다. 값은 CHUNK_BREAKTYPE 열거형에서 나온 값입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplsetint64value"></a><a name="setint64value"></a>CMFC필터청크밸류임플::SetInt64Value

int64에 키로 속성을 설정합니다.

```
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,
    __int64 nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*n발 (것)*<br/>
설정할 청크 값을 지정합니다.

*청크 타입*<br/>
플래그는 이 청크에 텍스트 형식 또는 값 형식 속성이 포함되어 있는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져온 값입니다.

*locale*<br/>
텍스트 청크와 관련된 언어 및 하위 언어입니다. 청크 로캘은 문서 인덱서에서 텍스트의 적절한 단어 나누기를 수행하는 데 사용됩니다. 청크가 텍스트 형식이나 데이터 형식VT_LPWSTR VT_LPSTR 또는 VT_BSTR 있는 값 형식이 아니면 이 필드는 무시됩니다.

*cwcLen소스*<br/>
현재 청크가 파생된 원본 텍스트의 문자 길이입니다. 0 값은 원본 텍스트와 파생 된 텍스트 간의 문자별 대응을 의미합니다. 영하지 않은 값은 그러한 직접적인 대응이 존재하지 않는다는 것을 의미합니다.

*cwcStartSource*<br/>
파생 된 청크에 대 한 소스 텍스트가 소스 청크에서 시작 되는 오프셋입니다.

*청크브레이크 타입*<br/>
이전 청크와 현재 청크를 구분하는 나누기 유형입니다. 값은 CHUNK_BREAKTYPE 열거형에서 나온 값입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplsetintvalue"></a><a name="setintvalue"></a>CMFC필터청크밸류임플::셋인트밸류

속성키로 int로 설정합니다.

```
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,
    int nVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*n발 (것)*<br/>
설정할 청크 값을 지정합니다.

*청크 타입*<br/>
플래그는 이 청크에 텍스트 형식 또는 값 형식 속성이 포함되어 있는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져온 값입니다.

*locale*<br/>
텍스트 청크와 관련된 언어 및 하위 언어입니다. 청크 로캘은 문서 인덱서에서 텍스트의 적절한 단어 나누기를 수행하는 데 사용됩니다. 청크가 텍스트 형식이나 데이터 형식VT_LPWSTR VT_LPSTR 또는 VT_BSTR 있는 값 형식이 아니면 이 필드는 무시됩니다.

*cwcLen소스*<br/>
현재 청크가 파생된 원본 텍스트의 문자 길이입니다. 0 값은 원본 텍스트와 파생 된 텍스트 간의 문자별 대응을 의미합니다. 영하지 않은 값은 그러한 직접적인 대응이 존재하지 않는다는 것을 의미합니다.

*cwcStartSource*<br/>
파생 된 청크에 대 한 소스 텍스트가 소스 청크에서 시작 되는 오프셋입니다.

*청크브레이크 타입*<br/>
이전 청크와 현재 청크를 구분하는 나누기 유형입니다. 값은 CHUNK_BREAKTYPE 열거형에서 나온 값입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplsetlongvalue"></a><a name="setlongvalue"></a>CMFC필터청크밸류임플::세트롱값

키로 속성을 LONG으로 설정합니다.

```
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,
    long lVal,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*lVal*<br/>
설정할 청크 값을 지정합니다.

*청크 타입*<br/>
플래그는 이 청크에 텍스트 형식 또는 값 형식 속성이 포함되어 있는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져온 값입니다.

*locale*<br/>
텍스트 청크와 관련된 언어 및 하위 언어입니다. 청크 로캘은 문서 인덱서에서 텍스트의 적절한 단어 나누기를 수행하는 데 사용됩니다. 청크가 텍스트 형식이나 데이터 형식VT_LPWSTR VT_LPSTR 또는 VT_BSTR 있는 값 형식이 아니면 이 필드는 무시됩니다.

*cwcLen소스*<br/>
현재 청크가 파생된 원본 텍스트의 문자 길이입니다. 0 값은 원본 텍스트와 파생 된 텍스트 간의 문자별 대응을 의미합니다. 영하지 않은 값은 그러한 직접적인 대응이 존재하지 않는다는 것을 의미합니다.

*cwcStartSource*<br/>
파생 된 청크에 대 한 소스 텍스트가 소스 청크에서 시작 되는 오프셋입니다.

*청크브레이크 타입*<br/>
이전 청크와 현재 청크를 구분하는 나누기 유형입니다. 값은 CHUNK_BREAKTYPE 열거형에서 나온 값입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplsetsystemtimevalue"></a><a name="setsystemtimevalue"></a>CMFC필터청크밸류임플::셋시스템타임값

SystemTime에 키로 속성을 설정합니다.

```
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,
    const SYSTEMTIME& systemTime,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale=0,
    DWORD cwcLenSource=0,
    DWORD cwcStartSource=0,
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*Systemtime*<br/>
설정할 청크 값을 지정합니다.

*청크 타입*<br/>
플래그는 이 청크에 텍스트 형식 또는 값 형식 속성이 포함되어 있는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져온 값입니다.

*locale*<br/>
텍스트 청크와 관련된 언어 및 하위 언어입니다. 청크 로캘은 문서 인덱서에서 텍스트의 적절한 단어 나누기를 수행하는 데 사용됩니다. 청크가 텍스트 형식이나 데이터 형식VT_LPWSTR VT_LPSTR 또는 VT_BSTR 있는 값 형식이 아니면 이 필드는 무시됩니다.

*cwcLen소스*<br/>
현재 청크가 파생된 원본 텍스트의 문자 길이입니다. 0 값은 원본 텍스트와 파생 된 텍스트 간의 문자별 대응을 의미합니다. 영하지 않은 값은 그러한 직접적인 대응이 존재하지 않는다는 것을 의미합니다.

*cwcStartSource*<br/>
파생 된 청크에 대 한 소스 텍스트가 소스 청크에서 시작 되는 오프셋입니다.

*청크브레이크 타입*<br/>
이전 청크와 현재 청크를 구분하는 나누기 유형입니다. 값은 CHUNK_BREAKTYPE 열거형에서 나온 값입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="cmfcfilterchunkvalueimplsettextvalue"></a><a name="settextvalue"></a>CMFC필터청크밸류임플::세트텍스트값

유니코드 문자열에 대한 키별로 속성을 설정합니다.

```
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,
    LPCTSTR pszValue,
    CHUNKSTATE chunkType = CHUNK_VALUE,
    LCID locale = 0,
    DWORD cwcLenSource = 0,
    DWORD cwcStartSource = 0,
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```

### <a name="parameters"></a>매개 변수

*pkey*<br/>
속성 키를 지정합니다.

*psz값*<br/>
설정할 청크 값을 지정합니다.

*청크 타입*<br/>
플래그는 이 청크에 텍스트 형식 또는 값 형식 속성이 포함되어 있는지 여부를 나타냅니다. 플래그 값은 CHUNKSTATE 열거형에서 가져온 값입니다.

*locale*<br/>
텍스트 청크와 관련된 언어 및 하위 언어입니다. 청크 로캘은 문서 인덱서에서 텍스트의 적절한 단어 나누기를 수행하는 데 사용됩니다. 청크가 텍스트 형식이나 데이터 형식VT_LPWSTR VT_LPSTR 또는 VT_BSTR 있는 값 형식이 아니면 이 필드는 무시됩니다.

*cwcLen소스*<br/>
현재 청크가 파생된 원본 텍스트의 문자 길이입니다. 0 값은 원본 텍스트와 파생 된 텍스트 간의 문자별 대응을 의미합니다. 영하지 않은 값은 그러한 직접적인 대응이 존재하지 않는다는 것을 의미합니다.

*cwcStartSource*<br/>
파생 된 청크에 대 한 소스 텍스트가 소스 청크에서 시작 되는 오프셋입니다.

*청크브레이크 타입*<br/>
이전 청크와 현재 청크를 구분하는 나누기 유형입니다. 값은 CHUNK_BREAKTYPE 열거형에서 나온 값입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)
