---
title: CW2AEX 클래스
ms.date: 11/04/2016
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
ms.openlocfilehash: 849cbe5c26d7c7af7a8925a26057b5777554471d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330450"
---
# <a name="cw2aex-class"></a>CW2AEX 클래스

이 클래스는 문자열 변환 매크로 CT2AEX, CW2TEX, CW2CTEX 및 CT2CAEX 및 형식 DEF CW2A에서 사용됩니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<int t_nBufferLength = 128>
class CW2AEX
```

#### <a name="parameters"></a>매개 변수

*t_nBufferLength*<br/>
변환 프로세스에 사용되는 버퍼의 크기입니다. 기본 길이는 128바이트입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CW2AEX::CW2AEX](#cw2aex)|생성자입니다.|
|[CW2AEX::~CW2AEX](#dtor)|소멸자입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CW2AEX::연산자 LPSTR](#operator_lpstr)|변환 연산자.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CW2AEX:m_psz](#m_psz)|원본 문자열을 저장하는 데이터 멤버입니다.|
|[CW2AEX:m_szBuffer](#m_szbuffer)|변환된 문자열을 저장하는 데 사용되는 정적 버퍼입니다.|

## <a name="remarks"></a>설명

추가 기능이 필요하지 않는 한 코드에서 CT2AEX, CW2TEX, CW2CTEX, CT2CAEX 또는 CW2A를 사용합니다.

이 클래스에는 변환 결과를 저장하는 데 사용되는 고정 크기 정적 버퍼가 포함되어 있습니다. 결과가 너무 커서 정적 버퍼에 맞지 않으면 클래스는 **malloc을**사용하여 메모리를 할당하여 개체가 범위를 벗어날 때 메모리를 해제합니다. 이렇게 하면 이전 버전의 ATL에서 사용할 수 있는 텍스트 변환 매크로와 달리 이 클래스는 루프에서 사용할 수 있으며 스택이 오버플로되지 않습니다.

클래스가 힙에 메모리를 할당하려고 시도하고 실패하면 E_OUTOFMEMORY `AtlThrow` 인수를 호출합니다.

기본적으로 ATL 변환 클래스와 매크로는 변환을 위해 현재 스레드의 ANSI 코드 페이지를 사용합니다. 특정 변환에 대해 해당 동작을 재정의하려면 코드 페이지를 클래스의 생성자에 대한 두 번째 매개 변수로 지정합니다.

다음 매크로는 이 클래스를 기반으로 합니다.

- CT2AEX

- CW2TEX

- CW2CTEX

- CT2CAEX

다음 typedef는 이 클래스를 기반으로 합니다.

- CW2A

이러한 텍스트 변환 매크로에 대한 설명은 [ATL 및 MFC 문자열 변환 매크로를](string-conversion-macros.md)참조하십시오.

## <a name="example"></a>예제

이러한 문자열 변환 매크로를 사용하는 예는 [ATL 및 MFC 문자열 변환 매크로를](string-conversion-macros.md) 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** atlconv.h

## <a name="cw2aexcw2aex"></a><a name="cw2aex"></a>CW2AEX::CW2AEX

생성자입니다.

```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2AEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
변환할 텍스트 문자열입니다.

*n코드 페이지*<br/>
변환을 수행하는 데 사용되는 코드 페이지입니다. 자세한 내용은 Windows SDK 기능 [MultiByteToWideChar에](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar) 대한 코드 페이지 매개 변수 토론을 참조하십시오.

### <a name="remarks"></a>설명

변환 프로세스에 사용된 버퍼를 할당합니다.

## <a name="cw2aexcw2aex"></a><a name="dtor"></a>CW2AEX::~CW2AEX

소멸자입니다.

```
~CW2AEX() throw();
```

### <a name="remarks"></a>설명

할당된 버퍼를 해제합니다.

## <a name="cw2aexm_psz"></a><a name="m_psz"></a>CW2AEX:m_psz

원본 문자열을 저장하는 데이터 멤버입니다.

```
LPSTR m_psz;
```

## <a name="cw2aexm_szbuffer"></a><a name="m_szbuffer"></a>CW2AEX:m_szBuffer

변환된 문자열을 저장하는 데 사용되는 정적 버퍼입니다.

```
char m_szBuffer[t_nBufferLength];
```

## <a name="cw2aexoperator-lpstr"></a><a name="operator_lpstr"></a>CW2AEX::연산자 LPSTR

변환 연산자.

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>Return Value

텍스트 문자열을 LPSTR 유형으로 반환합니다.

## <a name="see-also"></a>참고 항목

[CA2AEX 클래스](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX 클래스](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX 클래스](../../atl/reference/ca2wex-class.md)<br/>
[CW2CWEX 클래스](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX 클래스](../../atl/reference/cw2wex-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
