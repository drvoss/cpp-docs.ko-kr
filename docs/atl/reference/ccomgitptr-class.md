---
title: CComGITPtr 클래스
ms.date: 11/04/2016
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
ms.openlocfilehash: 230eeb1577189d2057e530e1df8ef99c611fb32b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327835"
---
# <a name="ccomgitptr-class"></a>CComGITPtr 클래스

이 클래스는 인터페이스 포인터와 GIT(전역 인터페이스 테이블)를 처리하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
GIT에 저장할 인터페이스 포인터의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComGITPtr:::CComGITPtr](#ccomgitptr)|생성자입니다.|
|[CComGITPtr::~CComGITPtr](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComGITPtr::연결](#attach)|이 메서드를 호출하여 GIT(전역 인터페이스 테이블)에 인터페이스 포인터를 등록합니다.|
|[CComGITPtr::복사](#copyto)|이 메서드를 호출하여 GIT(전역 인터페이스 테이블)에서 전달된 포인터로 인터페이스를 복사합니다.|
|[CComGITPtr::D에타흐](#detach)|이 메서드를 호출하여 개체에서 `CComGITPtr` 인터페이스를 연결 해제합니다.|
|[CComGITPtr::GetCookie](#getcookie)|개체에서 쿠키를 반환 하려면이 메서드를 호출 합니다. `CComGITPtr`|
|[CComGITPTR::취소](#revoke)|이 메서드를 호출하여 GIT(전역 인터페이스 테이블)에서 인터페이스를 제거합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CComGITPtr::연산자 DWORD](#operator_dword)|개체에서 쿠키를 `CComGITPtr` 반환합니다.|
|[CComGITPtr::연산자 =](#operator_eq)|대입 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComGITPtr::m_dwCookie](#m_dwcookie)|쿠키입니다.|

## <a name="remarks"></a>설명

자유 스레드 마샬러를 집계하고 다른 개체에서 가져온 인터페이스 포인터를 사용해야 하는 개체는 인터페이스가 올바르게 마샬링되었는지 확인하기 위해 추가 단계를 수행해야 합니다. 일반적으로 GIT에 인터페이스 포인터를 저장하고 GIT를 사용할 때마다 GIT에서 포인터를 가져오는 작업이 포함됩니다. 클래스는 `CComGITPtr` GIT에 저장된 인터페이스 포인터를 사용하는 데 도움이 됩니다.

> [!NOTE]
> 전역 인터페이스 테이블 기능은 DCOM 버전 1.1 이상, Windows 98, 서비스 팩 3 이상, Windows 2000이 있는 Windows 95에서만 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccomgitptrattach"></a><a name="attach"></a>CComGITPtr::연결

이 메서드를 호출하여 GIT(전역 인터페이스 테이블)에 인터페이스 포인터를 등록합니다.

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
GIT에 추가할 인터페이스 포인터입니다.

*dwCookie*<br/>
인터페이스 포인터를 식별하는 데 사용되는 쿠키입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 GIT가 유효하지 않거나 쿠키가 NULL과 같으면 어설션 오류가 발생합니다.

## <a name="ccomgitptrccomgitptr"></a><a name="ccomgitptr"></a>CComGITPtr:::CComGITPtr

생성자입니다.

```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```

### <a name="parameters"></a>매개 변수

*P*<br/>
【인】 GIT(전역 인터페이스 테이블)에 저장할 인터페이스 포인터입니다.

*Git*<br/>
【인】 기존 `CComGITPtr` 개체에 대한 참조입니다.

*dwCookie*<br/>
【인】 인터페이스 포인터를 식별하는 데 사용되는 쿠키입니다.

*Rv*<br/>
【인】 데이터를 `CComGITPtr` 이동할 원본 개체입니다.

### <a name="remarks"></a>설명

선택적으로 `CComGITPtr` 기존 `CComGITPtr` 개체를 사용하여 새 개체를 만듭니다.

*rv를* 활용하는 생성자는 이동 생성자입니다. 데이터는 원본, *rv에서*이동한 다음 *rv가* 지워집니다.

## <a name="ccomgitptrccomgitptr"></a><a name="dtor"></a>CComGITPtr::~CComGITPtr

소멸자입니다.

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>설명

[CComGITPtr::해지를](#revoke)사용하여 GIT(전역 인터페이스 테이블)에서 인터페이스를 제거합니다.

## <a name="ccomgitptrcopyto"></a><a name="copyto"></a>CComGITPtr::복사

이 메서드를 호출하여 GIT(전역 인터페이스 테이블)에서 전달된 포인터로 인터페이스를 복사합니다.

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>매개 변수

*Pp*<br/>
인터페이스를 수신하는 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

GIT의 인터페이스가 전달된 포인터에 복사됩니다. 포인터가 더 이상 필요하지 않을 때 호출자는 포인터를 해제해야 합니다.

## <a name="ccomgitptrdetach"></a><a name="detach"></a>CComGITPtr::D에타흐

이 메서드를 호출하여 개체에서 `CComGITPtr` 인터페이스를 연결 해제합니다.

```
DWORD Detach() throw();
```

### <a name="return-value"></a>Return Value

개체에서 쿠키를 `CComGITPtr` 반환합니다.

### <a name="remarks"></a>설명

[CComGITPtr::해지를](#revoke)사용하여 GIT에서 인터페이스를 제거하는 것은 호출자의 것입니다.

## <a name="ccomgitptrgetcookie"></a><a name="getcookie"></a>CComGITPtr::GetCookie

개체에서 쿠키를 반환 하려면이 메서드를 호출 합니다. `CComGITPtr`

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>Return Value

쿠키를 반환합니다.

### <a name="remarks"></a>설명

쿠키는 인터페이스와 해당 위치를 식별하는 데 사용되는 변수입니다.

## <a name="ccomgitptrm_dwcookie"></a><a name="m_dwcookie"></a>CComGITPtr::m_dwCookie

쿠키입니다.

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>설명

쿠키는 인터페이스와 해당 위치를 식별하는 데 사용되는 멤버 변수입니다.

## <a name="ccomgitptroperator-"></a><a name="operator_eq"></a>CComGITPtr::연산자 =

할당 연산자입니다.

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>매개 변수

*P*<br/>
【인】 인터페이스에 대한 포인터입니다.

*Git*<br/>
[in] `CComGITPtr` 개체에 대한 참조입니다.

*dwCookie*<br/>
【인】 인터페이스 포인터를 식별하는 데 사용되는 쿠키입니다.

*Rv*<br/>
【인】 에서 `CComGITPtr` 데이터를 이동할 수 있습니다.

### <a name="return-value"></a>Return Value

업데이트된 `CComGITPtr` 개체를 반환합니다.

### <a name="remarks"></a>설명

기존 개체또는 참조에서 `CComGITPtr` 전역 인터페이스 테이블에 대한 참조에서 개체에 새 값을 할당합니다.

## <a name="ccomgitptroperator-dword"></a><a name="operator_dword"></a>CComGITPtr::연산자 DWORD

개체와 연결된 쿠키를 반환합니다. `CComGITPtr`

```
operator DWORD() const;
```

### <a name="remarks"></a>설명

쿠키는 인터페이스와 해당 위치를 식별하는 데 사용되는 변수입니다.

## <a name="ccomgitptrrevoke"></a><a name="revoke"></a>CComGITPTR::취소

이 메서드를 호출하여 GIT(전역 인터페이스 테이블)에서 현재 인터페이스를 제거합니다.

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

GIT에서 인터페이스를 제거합니다.

## <a name="see-also"></a>참고 항목

[무료 스레드 마샬러](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[아파트 간 인터페이스 액세스](/windows/win32/com/accessing-interfaces-across-apartments)<br/>
[전역 인터페이스 테이블을 사용할 시기](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
