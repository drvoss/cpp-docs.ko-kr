---
title: CW2WEX 클래스
ms.date: 11/04/2016
f1_keywords:
- CW2WEX
- ATLCONV/ATL::CW2WEX
- ATLCONV/ATL::CW2WEX::CW2WEX
- ATLCONV/ATL::CW2WEX::m_psz
- ATLCONV/ATL::CW2WEX::m_szBuffer
helpviewer_keywords:
- CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
ms.openlocfilehash: b116775a595f9fb3612d46e19526cf1396f85002
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330342"
---
# <a name="cw2wex-class"></a>CW2WEX 클래스

이 클래스는 문자열 변환 매크로 CW2TEX 및 CT2WEX 및 형식 def CW2W에서 사용됩니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <int t_nBufferLength = 128>
class CW2WEX
```

#### <a name="parameters"></a>매개 변수

*t_nBufferLength*<br/>
변환 프로세스에 사용되는 버퍼의 크기입니다. 기본 길이는 128바이트입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CW2WEX::CW2WEX](#cw2wex)|생성자입니다.|
|[CW2WEX ::~CW2WEX](#dtor)|소멸자입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CW2WEX ::연산자 LPWSTR](#operator_lpwstr)|변환 연산자.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CW2WEX:m_psz](#m_psz)|원본 문자열을 저장하는 데이터 멤버입니다.|
|[CW2WEX:m_szBuffer](#m_szbuffer)|변환된 문자열을 저장하는 데 사용되는 정적 버퍼입니다.|

## <a name="remarks"></a>설명

추가 기능이 필요하지 않으면 코드에서 CW2TEX, CT2WEX 또는 CW2W를 사용합니다.

이 클래스에는 변환 결과를 저장하는 데 사용되는 고정 크기 정적 버퍼가 포함되어 있습니다. 결과가 너무 커서 정적 버퍼에 맞지 않으면 클래스는 **malloc을**사용하여 메모리를 할당하여 개체가 범위를 벗어날 때 메모리를 해제합니다. 이렇게 하면 이전 버전의 ATL에서 사용할 수 있는 텍스트 변환 매크로와 달리 이 클래스는 루프에서 사용할 수 있으며 스택이 오버플로되지 않습니다.

클래스가 힙에 메모리를 할당하려고 시도하고 실패하면 E_OUTOFMEMORY `AtlThrow` 인수를 호출합니다.

기본적으로 ATL 변환 클래스와 매크로는 변환을 위해 현재 스레드의 ANSI 코드 페이지를 사용합니다.

다음 매크로는 이 클래스를 기반으로 합니다.

- CW2TEX

- CT2WEX

다음 typedef는 이 클래스를 기반으로 합니다.

- CW2W

이러한 텍스트 변환 매크로에 대한 설명은 [ATL 및 MFC 문자열 변환 매크로를](string-conversion-macros.md)참조하십시오.

## <a name="example"></a>예제

이러한 문자열 변환 매크로를 사용하는 예는 [ATL 및 MFC 문자열 변환 매크로를](string-conversion-macros.md) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlconv.h

## <a name="cw2wexcw2wex"></a><a name="cw2wex"></a>CW2WEX::CW2WEX

생성자입니다.

```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
변환할 텍스트 문자열입니다.

*n코드 페이지*<br/>
코드 페이지입니다. 이 클래스에서는 사용되지 않습니다.

### <a name="remarks"></a>설명

변환에 필요한 버퍼를 만듭니다.

## <a name="cw2wexcw2wex"></a><a name="dtor"></a>CW2WEX ::~CW2WEX

소멸자..

```
~CW2WEX() throw();
```

### <a name="remarks"></a>설명

할당된 버퍼를 해제합니다.

## <a name="cw2wexm_psz"></a><a name="m_psz"></a>CW2WEX:m_psz

원본 문자열을 저장하는 데이터 멤버입니다.

```
LPWSTR m_psz;
```

## <a name="cw2wexm_szbuffer"></a><a name="m_szbuffer"></a>CW2WEX:m_szBuffer

변환된 문자열을 저장하는 데 사용되는 정적 버퍼입니다.

```
wchar_t m_szBuffer[t_nBufferLength];
```

## <a name="cw2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a>CW2WEX ::연산자 LPWSTR

캐스트 연산자.

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Return Value

텍스트 문자열을 LPWSTR 유형으로 반환합니다.

## <a name="see-also"></a>참고 항목

[CA2AEX 클래스](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX 클래스](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX 클래스](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX 클래스](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX 클래스](../../atl/reference/cw2cwex-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
