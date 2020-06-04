---
title: CW2CWEX 클래스
ms.date: 11/04/2016
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
ms.openlocfilehash: 07dd0319586054403d8ed0c8efc813b4061e355a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330441"
---
# <a name="cw2cwex-class"></a>CW2CWEX 클래스

이 클래스는 문자열 변환 매크로 CW2CTEX 및 CT2CWEX 및 형식 DEF CW2W에서 사용됩니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<int t_nBufferLength = 128>
class CW2CWEX
```

#### <a name="parameters"></a>매개 변수

*t_nBufferLength*<br/>
변환 프로세스에 사용되는 버퍼의 크기입니다. 기본 길이는 128바이트입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CW2CWEX::CW2CWEX](#cw2cwex)|생성자입니다.|
|[CW2CWEX::~CW2CWEX](#dtor)|소멸자입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CW2CWEX::연산자 LPCWSTR](#operator_lpcwstr)|변환 연산자.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CW2CWEX::m_psz](#m_psz)|원본 문자열을 저장하는 데이터 멤버입니다.|

## <a name="remarks"></a>설명

추가 기능이 필요하지 않는 한 코드에서 CW2CTEX, CT2CWEX 또는 CW2W를 사용합니다.

이 클래스는 루프에서 사용하기에 안전하며 스택이 오버플로되지 않습니다. 기본적으로 ATL 변환 클래스와 매크로는 변환을 위해 현재 스레드의 ANSI 코드 페이지를 사용합니다.

다음 매크로는 이 클래스를 기반으로 합니다.

- CW2CTEX

- CT2CWEX

다음 typedef는 이 클래스를 기반으로 합니다.

- CW2W

이러한 텍스트 변환 매크로에 대한 설명은 [ATL 및 MFC 문자열 변환 매크로를](string-conversion-macros.md)참조하십시오.

## <a name="example"></a>예제

이러한 문자열 변환 매크로를 사용하는 예는 [ATL 및 MFC 문자열 변환 매크로를](string-conversion-macros.md) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlconv.h

## <a name="cw2cwexcw2cwex"></a><a name="cw2cwex"></a>CW2CWEX::CW2CWEX

생성자입니다.

```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2CWEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
변환할 텍스트 문자열입니다.

*n코드 페이지*<br/>
코드 페이지입니다. 이 클래스에서는 사용되지 않습니다.

### <a name="remarks"></a>설명

변환 프로세스에 사용된 버퍼를 할당합니다.

## <a name="cw2cwexcw2cwex"></a><a name="dtor"></a>CW2CWEX::~CW2CWEX

소멸자입니다.

```
~CW2CWEX() throw();
```

### <a name="remarks"></a>설명

할당된 버퍼를 해제합니다.

## <a name="cw2cwexm_psz"></a><a name="m_psz"></a>CW2CWEX::m_psz

원본 문자열을 저장하는 데이터 멤버입니다.

```
LPCWSTR m_psz;
```

## <a name="cw2cwexoperator-lpcwstr"></a><a name="operator_lpcwstr"></a>CW2CWEX::연산자 LPCWSTR

변환 연산자.

```
operator LPCWSTR() const throw();
```

### <a name="return-value"></a>Return Value

텍스트 문자열을 LPCWSTR 유형으로 반환합니다.

## <a name="see-also"></a>참고 항목

[CA2AEX 클래스](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX 클래스](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX 클래스](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX 클래스](../../atl/reference/cw2aex-class.md)<br/>
[CW2WEX 클래스](../../atl/reference/cw2wex-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
