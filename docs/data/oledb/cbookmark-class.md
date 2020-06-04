---
title: CBookmark 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
- ATL.CBookmark<0>.GetBuffer
- ATL.CBookmark.GetBuffer
- ATL::CBookmark<0>::GetBuffer
- ATL::CBookmark::GetBuffer
- CBookmark.GetBuffer
- ATL::CBookmark<nSize>::GetBuffer
- ATL.CBookmark<nSize>.GetBuffer
- CBookmark<0>.GetBuffer
- CBookmark<nSize>::GetBuffer
- CBookmark<0>::GetBuffer
- CBookmark<nSize>.GetBuffer
- CBookmark::GetBuffer
- CBookmark::GetSize
- ATL.CBookmark<nSize>.GetSize
- CBookmark<nSize>.GetSize
- CBookmark.GetSize
- ATL::CBookmark::GetSize
- CBookmark<0>::GetSize
- ATL::CBookmark<nSize>::GetSize
- ATL.CBookmark<0>.GetSize
- ATL::CBookmark<0>::GetSize
- ATL.CBookmark.GetSize
- CBookmark<0>.GetSize
- CBookmark<nSize>::GetSize
- CBookmark<0>::SetBookmark
- ATL.CBookmark<0>.SetBookmark
- CBookmark<0>.SetBookmark
- SetBookmark
- ATL::CBookmark::SetBookmark
- ATL::CBookmark<0>::SetBookmark
- CBookmark.SetBookmark
- ATL.CBookmark.SetBookmark
- CBookmark::SetBookmark
- CBookmark<0>::operator=
- CBookmark<0>.operator=
- ATL.CBookmark.operator=
- CBookmark::operator=
- ATL.CBookmark<0>.operator=
- ATL::CBookmark<0>::operator=
- CBookmark.operator=
- ATL::CBookmark::operator=
helpviewer_keywords:
- CBookmark class
- CBookmark class, constructor
- GetBuffer method
- GetSize method
- SetBookmark method
- = operator, with OLE DB templates
- operator =, bookmarks
- operator=, bookmarks
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
ms.openlocfilehash: d3d82ea09b7ed2c1cbaf325906b4f9b480e1eb4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359328"
---
# <a name="cbookmark-class"></a>CBookmark 클래스

책갈피 값을 버퍼에 보유합니다.

## <a name="syntax"></a>구문

```cpp
template < DBLENGTH nSize = 0 >
class CBookmark : public CBookmarkBase

template <>
class CBookmark< 0 > : public CBookmarkBase
```

### <a name="parameters"></a>매개 변수

*nSize*<br/>
책갈피 버퍼의 크기입니다. *nSize가* 0이면 책갈피 버퍼는 런타임에 동적으로 생성됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[C북마크](#cbookmark)|생성자|
|[GetBuffer](#getbuffer)|버퍼에 대한 포인터를 검색합니다.|
|[GetSize](#getsize)|버퍼 크기를 바이트로 검색합니다.|
|[세트북마크](#setbookmark)|책갈피 값을 설정합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 =](#operator)|한 `CBookmark` 클래스를 다른 클래스에 할당합니다.|

## <a name="remarks"></a>설명

`CBookmark<0>`의 템플릿 `CBookmark`전문화입니다. 버퍼는 런타임에 동적으로 생성됩니다.

## <a name="cbookmarkcbookmark"></a><a name="cbookmark"></a>C북마크:::C북마크

생성자입니다.

### <a name="syntax"></a>구문

```cpp
CBookmark();
CBookmark(DBLENGTH nSize);
```

#### <a name="parameters"></a>매개 변수

*nSize*<br/>
【인】 책갈피 버퍼의 크기(바이트)입니다.

### <a name="remarks"></a>설명

첫 번째 함수는 버퍼를 NULL로 설정하고 버퍼 크기를 0으로 설정합니다. 두 번째 함수는 버퍼 크기를 *nSize로*설정하고 버퍼를 *nSize* 바이트의 바이트 배열로 설정합니다.

> [!NOTE]
> 이 함수는 에서만 `CBookmark<0>`사용할 수 있습니다.

## <a name="cbookmarkgetbuffer"></a><a name="getbuffer"></a>C북마크::GetBuffer

책갈피 버퍼에 대한 포인터를 검색합니다.

### <a name="syntax"></a>구문

```cpp
virtual BYTE* GetBuffer() const throw();
```

### <a name="return-value"></a>Return Value

책갈피 버퍼에 대한 포인터입니다.

## <a name="cbookmarkgetsize"></a><a name="getsize"></a>C북마크::겟사이즈

책갈피 버퍼의 크기를 검색합니다.

### <a name="syntax"></a>구문

```cpp
virtual DBLENGTH GetSize() const throw();
```

### <a name="return-value"></a>Return Value

버퍼 크기(바이트)입니다.

## <a name="cbookmarksetbookmark"></a><a name="setbookmark"></a>C북마크:::세트북마크

*pBuffer에서* 참조하는 책갈피 값을 `CBookmark` 버퍼에 복사하고 버퍼 크기를 *nSize로*설정합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();
```

#### <a name="parameters"></a>매개 변수

*nSize*<br/>
【인】 책갈피 버퍼의 크기입니다.

*pBuffer*<br/>
【인】 책갈피 값을 포함하는 바이트 배열에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT.

### <a name="remarks"></a>설명

이 함수는 에서만 `CBookmark<0>`사용할 수 있습니다.

## <a name="cbookmarkoperator-"></a><a name="operator"></a>C북마크::연산자 =

개체를 `CBookmark` 다른 개체에 할당합니다.

### <a name="syntax"></a>구문

```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();
```

### <a name="remarks"></a>설명

이 연산자는 `CBookmark<0>`에서만 필요합니다.

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)
