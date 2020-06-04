---
title: CComPtrBase 클래스
ms.date: 11/04/2016
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
ms.openlocfilehash: 9c62cc912b3fea3ea68390882bdda37cbfb25a7e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747765"
---
# <a name="ccomptrbase-class"></a>CComPtrBase 클래스

이 클래스는 COM 기반 메모리 루틴을 사용하는 스마트 포인터 클래스의 기초를 제공합니다.

## <a name="syntax"></a>구문

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
스마트 포인터에서 참조할 개체 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComPtrBase::~CComPtrBase](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComPtrBase::조언](#advise)|이 메서드를 호출하여 `CComPtrBase`연결 지점과 클라이언트의 싱크 사이에 연결을 만듭니다.|
|[CComPtrBase::연결](#attach)|이 메서드를 호출하여 기존 포인터의 소유권을 가져가 십시오.|
|[CComPtrBase::공동 만들기 인스턴스](#cocreateinstance)|지정된 클래스 ID 또는 프로그램 ID와 연결된 클래스의 개체를 만들려면 이 메서드를 호출합니다.|
|[CComPtrBase::복사](#copyto)|포인터를 `CComPtrBase` 다른 포인터 변수에 복사하려면 이 메서드를 호출합니다.|
|[CComPtrBase::D에타흐](#detach)|포인터의 소유권을 해제하려면 이 메서드를 호출합니다.|
|[CComPtrBase::이등엄](#isequalobject)|이 메서드를 호출하여 `IUnknown` 지정된 점이 `CComPtrBase` 개체와 연결된 동일한 개체를 가리키는지 확인합니다.|
|[CComPtrBase::쿼리 인터페이스](#queryinterface)|지정된 인터페이스에 대한 포인터를 반환하려면 이 메서드를 호출합니다.|
|[CComPtrBase::릴리스](#release)|인터페이스를 해제하려면 이 메서드를 호출합니다.|
|[CComPtrBase::세트사이트](#setsite)|이 메서드를 호출하여 `CComPtrBase` 개체의 사이트를 `IUnknown` 상위 개체의 사이트로 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CComPtrBase::연산자 T*](#operator_t_star)|캐스트 연산자입니다.|
|[CComPtrBase::연산자!](#operator_not)|NOT 연산자입니다.|
|[CComPtrBase::연산자 &](#operator_amp)|& 연산자|
|[CComPtrBase::연산자 *](#operator_star)|\* 연산자|
|[CComPtrBase::연산자 <](#ccomptrbase__operator lt)|연산자 미만입니다.|
|[CComPtrBase::연산자 ==](#operator_eq_eq)|같음 연산자입니다.|
|[CComPtrBase::연산자 ->](#operator_ptr)|구성원간 포인터 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComPtrBase::p](#p)|포인터 데이터 멤버 변수입니다.|

## <a name="remarks"></a>설명

이 클래스는 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 및 [CComPtr과](../../atl/reference/ccomptr-class.md)같은 COM 메모리 관리 루틴을 사용하는 다른 스마트 포인터에 대한 기초를 제공합니다. 파생 된 클래스는 자체 생성자 및 연산자 추가 하지만 `CComPtrBase`에서 제공 하는 메서드에 의존 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcomcli.h

## <a name="ccomptrbaseadvise"></a><a name="advise"></a>CComPtrBase::조언

이 메서드를 호출하여 `CComPtrBase`연결 지점과 클라이언트의 싱크 사이에 연결을 만듭니다.

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
클라이언트의 에 대한 `IUnknown`포인터입니다.

*Iid*<br/>
연결 지점의 GUID입니다. 일반적으로 이는 연결 점에서 관리하는 나가는 인터페이스와 동일합니다.

*Pdw*<br/>
연결을 고유하게 식별하는 쿠키에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 [AtlAdvise를](connection-point-global-functions.md#atladvise) 참조하십시오.

## <a name="ccomptrbaseattach"></a><a name="attach"></a>CComPtrBase::연결

이 메서드를 호출하여 기존 포인터의 소유권을 가져가 십시오.

```cpp
void Attach(T* p2) throw();
```

### <a name="parameters"></a>매개 변수

*p2*<br/>
개체는 `CComPtrBase` 이 포인터의 소유권을 차지합니다.

### <a name="remarks"></a>설명

`Attach`[CComPtrBase::기존](#release) [CComPtrBase::p](#p) 멤버 변수에서 릴리스를 호출한 `CComPtrBase::p`다음 *p2를* 에 할당합니다. 개체가 `CComPtrBase` 포인터의 소유권을 가져가면 개체의 `Release` 참조 수가 0으로 이동하면 포인터와 할당된 데이터를 삭제하는 포인터가 자동으로 호출됩니다.

## <a name="ccomptrbaseccomptrbase"></a><a name="dtor"></a>CComPtrBase::~CComPtrBase

소멸자입니다.

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>설명

가리키는 인터페이스를 `CComPtrBase`놓습니다.

## <a name="ccomptrbasecocreateinstance"></a><a name="cocreateinstance"></a>CComPtrBase::공동 만들기 인스턴스

지정된 클래스 ID 또는 프로그램 ID와 연결된 클래스의 개체를 만들려면 이 메서드를 호출합니다.

```
HRESULT CoCreateInstance(
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```

### <a name="parameters"></a>매개 변수

*szProgID*<br/>
CLSID를 복구하는 데 사용되는 ProgID에 대한 포인터입니다.

*pUnkOuter*<br/>
NULL인 경우 개체가 집계의 일부로 만들어지지 않음을 나타냅니다. NULL이 아닌 경우 집계 개체의 `IUnknown` 인터페이스(제어)에 `IUnknown`대한 포인터입니다.

*dwClsContext*<br/>
새로 만든 개체를 관리하는 코드가 실행되는 컨텍스트입니다.

*rclsid*<br/>
개체를 만드는 데 사용할 데이터 및 코드와 연결된 CLSID입니다.

### <a name="return-value"></a>Return Value

성공 또는 REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING 또는 실패 시 E_NOINTERFACE S_OK 반환합니다. 이러한 오류에 대한 설명은 [CoCreateClass 및](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) [CLSIDFromProgID를](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) 참조하십시오.

### <a name="remarks"></a>설명

메서드의 첫 번째 형식이 호출되는 경우 [CLSIDFromProgID는](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) CLSID를 복구하는 데 사용됩니다. 그런 다음 두 양식 모두 [CoCreateClassInstance를](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)호출합니다.

디버그 빌드에서 [CComPtrBase::p](#p) NULL과 같지 않은 경우 어설션 오류가 발생합니다.

## <a name="ccomptrbasecopyto"></a><a name="copyto"></a>CComPtrBase::복사

포인터를 `CComPtrBase` 다른 포인터 변수에 복사하려면 이 메서드를 호출합니다.

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>매개 변수

*Ppt*<br/>
포인터를 받을 변수의 `CComPtrBase` 주소입니다.

### <a name="return-value"></a>Return Value

실패에 E_POINTER 성공, S_OK 반환합니다.

### <a name="remarks"></a>설명

포인터를 `CComPtrBase` *ppT로*복사합니다. [CComPtrBase::p](#p) 멤버 변수의 참조 수는 증가합니다.

*ppT가* NULL과 같으면 오류 HRESULT가 반환됩니다. 디버그 빌드에서 *ppT가* NULL과 같으면 어설션 오류가 발생합니다.

## <a name="ccomptrbasedetach"></a><a name="detach"></a>CComPtrBase::D에타흐

포인터의 소유권을 해제하려면 이 메서드를 호출합니다.

```
T* Detach() throw();
```

### <a name="return-value"></a>Return Value

포인터의 복사본을 반환합니다.

### <a name="remarks"></a>설명

포인터의 소유권을 해제하고 [CComPtrBase::p](#p) 데이터 멤버 변수를 NULL로 설정하고 포인터의 복사본을 반환합니다.

## <a name="ccomptrbaseisequalobject"></a><a name="isequalobject"></a>CComPtrBase::이등엄

이 메서드를 호출하여 `IUnknown` 지정된 점이 `CComPtrBase` 개체와 연결된 동일한 개체를 가리키는지 확인합니다.

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>매개 변수

*p기타*<br/>
비교할 `IUnknown *`입니다.

### <a name="return-value"></a>Return Value

객체가 동일할 경우 true를 반환합니다.

## <a name="ccomptrbaseoperator-"></a><a name="operator_not"></a>CComPtrBase::연산자!

NOT 연산자입니다.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Return Value

포인터가 NULL과 같으면 true를 `CComHeapPtr` 반환합니다.

## <a name="ccomptrbaseoperator-amp"></a><a name="operator_amp"></a>CComPtrBase::연산자&amp;

& 연산자

```
T** operator&() throw();
```

### <a name="return-value"></a>Return Value

개체가 가리키는 개체의 주소를 `CComPtrBase` 반환합니다.

## <a name="ccomptrbaseoperator-"></a><a name="operator_star"></a>CComPtrBase::연산자\*

\* 연산자

```
T& operator*() const throw();
```

### <a name="return-value"></a>Return Value

[CComPtrBase::p](#p)값을 반환합니다. 즉, 개체에서 참조하는 개체에 `CComPtrBase` 대한 포인터입니다.

디버그빌드하는 경우 [CComPtrBase::p NULL과](#p) 같지 않은 경우 어설션 오류가 발생합니다.

## <a name="ccomptrbaseoperator-"></a><a name="operator_eq_eq"></a>CComPtrBase::연산자 ==

같음 연산자입니다.

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>매개 변수

*Pt*<br/>
개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

trueif를 `CComPtrBase` 반환하고 *pT가* 동일한 객체를 가리키고 그렇지 않으면 false를 가리킵니다.

## <a name="ccomptrbaseoperator--gt"></a><a name="operator_ptr"></a>CComPtrBase::연산자 -&gt;

구성원간 포인터 연산자입니다.

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>Return Value

[CComPtrBase::p](#p) 데이터 멤버 변수의 값을 반환합니다.

### <a name="remarks"></a>설명

이 연산자를 사용하여 개체가 가리키는 `CComPtrBase` 클래스의 메서드를 호출합니다. 디버그 빌드에서 `CComPtrBase` 데이터 멤버가 NULL을 가리키는 경우 어설션 오류가 발생합니다.

## <a name="ccomptrbaseoperator-lt"></a><a name="operator_lt"></a>CComPtrBase::연산자&lt;

연산자 미만입니다.

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>매개 변수

*Pt*<br/>
개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

현재 개체에서 관리하는 포인터가 비교중인 포인터보다 적으면 true를 반환합니다.

## <a name="ccomptrbaseoperator-t"></a><a name="operator_t_star"></a>CComPtrBase::연산자 T\*

캐스트 연산자입니다.

```
operator T*() const throw();
```

### <a name="remarks"></a>설명

클래스 템플릿에 정의된 개체 데이터 형식에 대한 포인터를 반환합니다.

## <a name="ccomptrbasep"></a><a name="p"></a>CComPtrBase::p

포인터 데이터 멤버 변수입니다.

```
T* p;
```

### <a name="remarks"></a>설명

이 멤버 변수에는 포인터 정보가 있습니다.

## <a name="ccomptrbasequeryinterface"></a><a name="queryinterface"></a>CComPtrBase::쿼리 인터페이스

지정된 인터페이스에 대한 포인터를 반환하려면 이 메서드를 호출합니다.

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>매개 변수

*Q*<br/>
인터페이스 포인터가 필요한 개체 유형입니다.

*Pp*<br/>
요청된 인터페이스 포인터를 받는 출력 변수의 주소입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 실패시 E_NOINTERFACE.

### <a name="remarks"></a>설명

이 메서드는 [IUnknown::QueryInterface 를 호출합니다.](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))

디버그 빌드에서 *pp가* NULL과 같지 않은 경우 어설션 오류가 발생합니다.

## <a name="ccomptrbaserelease"></a><a name="release"></a>CComPtrBase::릴리스

인터페이스를 해제하려면 이 메서드를 호출합니다.

```cpp
void Release() throw();
```

### <a name="remarks"></a>설명

인터페이스가 릴리스되고 [CComPtrBase::p](#p) NULL로 설정됩니다.

## <a name="ccomptrbasesetsite"></a><a name="setsite"></a>CComPtrBase::세트사이트

이 메서드를 호출하여 `CComPtrBase` 개체의 사이트를 `IUnknown` 상위 개체의 사이트로 설정합니다.

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>매개 변수

*펑크 부모*<br/>
부모의 인터페이스에 `IUnknown` 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 [AtlSetChildSite를](composite-control-global-functions.md#atlsetchildsite)호출합니다.

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)
