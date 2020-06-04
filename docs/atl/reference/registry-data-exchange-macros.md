---
title: 레지스트리 데이터 교환 매크로
ms.date: 11/04/2016
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
ms.openlocfilehash: a7d580e4907cec40f97c0cead616665fff7b8a01
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326064"
---
# <a name="registry-data-exchange-macros"></a>레지스트리 데이터 교환 매크로

이러한 매크로는 레지스트리 데이터 교환 작업을 수행합니다.

|||
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|레지스트리 데이터 교환 맵의 시작 부분을 표시합니다.|
|[END_RDX_MAP](#end_rdx_map)|레지스트리 데이터 교환 맵의 끝을 표시합니다.|
|[RDX_BINARY](#rdx_binary)|지정된 레지스트리 항목을 BYTE 형식의 지정된 멤버 변수와 연결합니다.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|지정된 레지스트리 항목을 CString 형식의 지정된 멤버 변수와 연결합니다.|
|[RDX_DWORD](#rdx_dword)|지정된 레지스트리 항목을 DWORD 형식의 지정된 멤버 변수와 연결합니다.|
|[RDX_TEXT](#rdx_text)|지정된 레지스트리 항목을 TCHAR 형식의 지정된 멤버 변수와 연결합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlplus.h

## <a name="begin_rdx_map"></a><a name="begin_rdx_map"></a>BEGIN_RDX_MAP

레지스트리 데이터 교환 맵의 시작 부분을 표시합니다.

```
BEGIN_RDX_MAP
```

### <a name="remarks"></a>설명

다음 매크로는 레지스트리 데이터 교환 맵 내에서 시스템 레지스트리의 항목을 읽고 작성하는 데 사용됩니다.

|매크로|Description|
|-----------|-----------------|
|[RDX_BINARY](#rdx_binary)|지정된 레지스트리 항목을 BYTE 형식의 지정된 멤버 변수와 연결합니다.|
|[RDX_DWORD](#rdx_dword)|지정된 레지스트리 항목을 DWORD 형식의 지정된 멤버 변수와 연결합니다.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|지정된 레지스트리 항목을 CString 형식의 지정된 멤버 변수와 연결합니다.|
|[RDX_TEXT](#rdx_text)|지정된 레지스트리 항목을 TCHAR 형식의 지정된 멤버 변수와 연결합니다.|

전역 함수 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)또는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로에 의해 생성된 동일한 이름의 멤버 함수는 코드가 시스템 레지스트리와 RDX 맵에 지정된 변수 간에 데이터를 교환해야 할 때마다 사용해야 합니다.

## <a name="end_rdx_map"></a><a name="end_rdx_map"></a>END_RDX_MAP

레지스트리 데이터 교환 맵의 끝을 표시합니다.

```
END_RDX_MAP
```

## <a name="rdx_binary"></a><a name="rdx_binary"></a>RDX_BINARY

지정된 레지스트리 항목을 BYTE 형식의 지정된 멤버 변수와 연결합니다.

```
RDX_BINARY(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>매개 변수

*루트키*<br/>
레지스트리 키 루트입니다.

*하위*<br/>
레지스트리 하위 키입니다.

*값 이름*<br/>
레지스트리 키입니다.

*멤버*<br/>
지정된 레지스트리 항목과 연결할 멤버 변수입니다.

*member_size*<br/>
멤버 변수의 크기(바이트)입니다.

### <a name="remarks"></a>설명

이 매크로는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로와 함께 멤버 변수를 지정된 레지스트리 항목과 연결하는 데 사용됩니다. 전역 함수 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)또는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로에 의해 생성된 동일한 이름의 멤버 함수는 RDX 맵의 시스템 레지스트리와 멤버 변수 간의 데이터 교환을 수행하는 데 사용해야 합니다.

## <a name="rdx_cstring_text"></a><a name="rdx_cstring_text"></a>RDX_CSTRING_TEXT

지정된 레지스트리 항목을 CString 형식의 지정된 멤버 변수와 연결합니다.

```
RDX_CSTRING_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>매개 변수

*루트키*<br/>
레지스트리 키 루트입니다.

*하위*<br/>
레지스트리 하위 키입니다.

*값 이름*<br/>
레지스트리 키입니다.

*멤버*<br/>
지정된 레지스트리 항목과 연결할 멤버 변수입니다.

*member_size*<br/>
멤버 변수의 크기(바이트)입니다.

### <a name="remarks"></a>설명

이 매크로는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로와 함께 멤버 변수를 지정된 레지스트리 항목과 연결하는 데 사용됩니다. 전역 함수 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)또는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로에 의해 생성된 동일한 이름의 멤버 함수는 RDX 맵의 시스템 레지스트리와 멤버 변수 간의 데이터 교환을 수행하는 데 사용해야 합니다.

## <a name="rdx_dword"></a><a name="rdx_dword"></a>RDX_DWORD

지정된 레지스트리 항목을 DWORD 형식의 지정된 멤버 변수와 연결합니다.

```
RDX_DWORD(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>매개 변수

*루트키*<br/>
레지스트리 키 루트입니다.

*하위*<br/>
레지스트리 하위 키입니다.

*값 이름*<br/>
레지스트리 키입니다.

*멤버*<br/>
지정된 레지스트리 항목과 연결할 멤버 변수입니다.

*member_size*<br/>
멤버 변수의 크기(바이트)입니다.

### <a name="remarks"></a>설명

이 매크로는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로와 함께 멤버 변수를 지정된 레지스트리 항목과 연결하는 데 사용됩니다. 전역 함수 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)또는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로에 의해 생성된 동일한 이름의 멤버 함수는 RDX 맵의 시스템 레지스트리와 멤버 변수 간의 데이터 교환을 수행하는 데 사용해야 합니다.

## <a name="rdx_text"></a><a name="rdx_text"></a>RDX_TEXT

지정된 레지스트리 항목을 TCHAR 형식의 지정된 멤버 변수와 연결합니다.

```
RDX_TEXT(
    rootkey,
    subkey,
    valuename,
    member,
    member_size )
```

### <a name="parameters"></a>매개 변수

*루트키*<br/>
레지스트리 키 루트입니다.

*하위*<br/>
레지스트리 하위 키입니다.

*값 이름*<br/>
레지스트리 키입니다.

*멤버*<br/>
지정된 레지스트리 항목과 연결할 멤버 변수입니다.

*member_size*<br/>
멤버 변수의 크기(바이트)입니다.

### <a name="remarks"></a>설명

이 매크로는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로와 함께 멤버 변수를 지정된 레지스트리 항목과 연결하는 데 사용됩니다. 전역 함수 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)또는 BEGIN_RDX_MAP 및 END_RDX_MAP 매크로에 의해 생성된 동일한 이름의 멤버 함수는 RDX 맵의 시스템 레지스트리와 멤버 변수 간의 데이터 교환을 수행하는 데 사용해야 합니다.

## <a name="see-also"></a>참고 항목

[매크로](../../atl/reference/atl-macros.md)<br/>
[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)
