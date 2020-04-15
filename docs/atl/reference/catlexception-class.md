---
title: CAtlException 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
ms.openlocfilehash: 6da56e4d6c443520eb6f857624a5923e71a1e580
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319001"
---
# <a name="catlexception-class"></a>CAtlException 클래스

이 클래스는 ATL 예외를 정의합니다.

## <a name="syntax"></a>구문

```
class CAtlException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[카틀예외::카틀예외](#catlexception)|생성자입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CAtlException::연산자 HRESULT](#operator_hresult)|현재 오브젝트를 HRESULT 값으로 캐스팅합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[카틀예외::m_hr](#m_hr)|개체에 의해 생성되고 오류 조건을 저장하는 데 사용되는 HRESULT 형식의 변수입니다.|

## <a name="remarks"></a>설명

개체는 `CAtlException` ATL 작업과 관련된 예외 조건을 나타냅니다. 클래스에는 `CAtlException` 예외 이유를 나타내는 상태 코드를 저장하는 공용 데이터 멤버와 예외를 HRESULT인 것처럼 처리할 수 있는 캐스트 연산자가 포함됩니다.

일반적으로 개체를 직접 `AtlThrow` 만드는 대신 `CAtlException` 호출합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlexcept.h

## <a name="catlexceptioncatlexception"></a><a name="catlexception"></a>카틀예외::카틀예외

생성자입니다.

```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>매개 변수

*Hr*<br/>
HRESULT 오류 코드입니다.

## <a name="catlexceptionoperator-hresult"></a><a name="operator_hresult"></a>CAtlException::연산자 HRESULT

현재 오브젝트를 HRESULT 값으로 캐스팅합니다.

```
operator HRESULT() const throw ();
```

## <a name="catlexceptionm_hr"></a><a name="m_hr"></a>카틀예외::m_hr

HRESULT 데이터 멤버입니다.

```
HRESULT m_hr;
```

### <a name="remarks"></a>설명

오류 조건을 저장하는 데이터 멤버입니다. HRESULT 값은 생성자, [CAtlException::CAtlException에](#catlexception)의해 설정됩니다.

## <a name="see-also"></a>참고 항목

[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
