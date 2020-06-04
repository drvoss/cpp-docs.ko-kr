---
title: IEnumOnSTLImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
ms.openlocfilehash: 2fbe6ccfbea2836c42a054da7ea9ebeac4e1555d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329708"
---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl 클래스

이 클래스는 C++ 표준 라이브러리 컬렉션을 기반으로 열거자 인터페이스를 정의합니다.

## <a name="syntax"></a>구문

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```

#### <a name="parameters"></a>매개 변수

*기본*<br/>
COM 열거자. 예는 [IEnumString을](/windows/win32/api/objidl/nn-objidl-ienumstring) 참조하십시오.

*piid*<br/>
열거자 인터페이스의 인터페이스 ID에 대한 포인터입니다.

*T*<br/>
열거자 인터페이스에서 노출되는 항목의 유형입니다.

*복사*<br/>
[복사 정책 클래스](../../atl/atl-copy-policy-classes.md).

*CollType*<br/>
C++ 표준 라이브러리 컨테이너 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IEnumOnSTLImpl::Clone](#clone)|**복제의**구현 .|
|[IEnumOnSTLImpl::Init](#init)|열거자를 초기화합니다.|
|[이에넘온스틀임플::다음](#next)|**다음**의 구현 .|
|[IEnumOnSTLImpl::재설정](#reset)|**재설정**의 구현 .|
|[IEnumOnSTLImpl::건너뛰기](#skip)|**건너뛰기**의 구현 .|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[IEnumOnSTLImpl::m_iter](#m_iter)|컬렉션 내에서 열거자의 현재 위치를 나타내는 반복기입니다.|
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|항목을 열어두는 C++ 표준 라이브러리 컨테이너에 대한 포인터입니다.|
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|컬렉션을 `IUnknown` 제공하는 개체의 포인터입니다.|

## <a name="remarks"></a>설명

`IEnumOnSTLImpl`은 열거되는 항목이 C++ 표준 라이브러리 호환 컨테이너에 저장되는 COM 열거체 인터페이스에 대한 구현을 제공합니다. 이 클래스는 배열을 기반으로 하는 열거형 인터페이스에 대한 구현을 제공하는 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) 클래스와 유사합니다.

> [!NOTE]
> `CComEnumImpl` 및 `IEnumOnSTLImpl` 간의 추가 차이점에 대한 자세한 내용은 [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init)를 참조하십시오.

일반적으로 이 인터페이스 구현에서 파생하여 고유한 열거자 클래스를 만들 필요가 *없습니다.* C++ 표준 라이브러리 컨테이너를 기반으로 ATL 제공 열거자를 사용 하려는 경우 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)의 인스턴스를 만들거나 [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)에서 파생 하 여 열거자를 반환 하는 컬렉션 클래스를 만드는 것이 더 일반적입니다.

그러나 사용자 지정 열거자(예: 열거자 인터페이스 외에 인터페이스를 노출하는 열거체)를 제공해야 하는 경우 이 클래스에서 파생할 수 있습니다. 이 경우 고유한 구현을 제공 하려면 [복제](#clone) 메서드를 재정의 해야 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ienumonstlimplinit"></a><a name="init"></a>이에넘온스틀임플::이니트

열거자를 초기화합니다.

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>매개 변수

*pUnkForRelease*<br/>
【인】 열거자의 수명 동안 살아 있어야 하는 개체의 `IUnknown` 포인터입니다. 이러한 개체가 없는 경우 NULL을 전달합니다.

*컬렉션*<br/>
축축한 항목을 보유하는 C++ 표준 라이브러리 컨테이너에 대한 참조입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

다른 개체에 있는 컬렉션에 대한 참조를 전달하는 `Init` 경우 *pUnkForRelease* 매개 변수를 사용하여 개체와 개체가 보유한 컬렉션을 열거자가 필요로 하는 기간 동안 사용할 수 있는지 확인할 수 있습니다.

모든 클라이언트에 다시 열거자 인터페이스에 포인터를 전달 하기 전에이 메서드를 호출 해야 합니다.

## <a name="ienumonstlimplclone"></a><a name="clone"></a>이에넘온스틀임플::클론

이 메서드는 형식의 **Clone** `CComEnumOnSTL`개체를 만들고 현재 개체에서 사용하는 동일한 컬렉션 및 반복기로 초기화하고 새로 만든 개체에서 인터페이스를 반환하여 복제 메서드의 구현을 제공합니다.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>매개 변수

*ppEnum*<br/>
【아웃】 새로 생성된 개체의 열거자 인터페이스가 현재 열거체에서 복제되었습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="ienumonstlimplm_spunk"></a><a name="m_spunk"></a>이에넘온스틀임플::m_spUnk

컬렉션을 `IUnknown` 제공하는 개체의 포인터입니다.

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>설명

이 스마트 포인터는 [IEnumOnSTLImpl::Init에](#init)전달된 개체에 대한 참조를 유지관리하여 열거자의 수명 동안 살아 있게 합니다.

## <a name="ienumonstlimplm_pcollection"></a><a name="m_pcollection"></a>이에넘온스틀임플::m_pcollection

이 멤버는 열거형 인터페이스의 구현을 구동하는 데이터를 제공하는 컬렉션을 가리킵니다.

```
CollType* m_pcollection;
```

### <a name="remarks"></a>설명

이 멤버는 [IEnumOnSTLImpl::Init에](#init)대한 호출로 초기화됩니다.

## <a name="ienumonstlimplm_iter"></a><a name="m_iter"></a>이에넘온스틀임플::m_iter

이 멤버는 컬렉션 내의 현재 위치를 표시하고 후속 요소로 이동하는 데 사용되는 반복기를 보유합니다.

```
CollType::iterator m_iter;
```

## <a name="ienumonstlimplnext"></a><a name="next"></a>이에넘온스틀임플::다음

이 메서드는 **Next** 메서드의 구현을 제공합니다.

```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```

### <a name="parameters"></a>매개 변수

*celt*<br/>
【인】 요청된 요소 수입니다.

*rgelt*<br/>
【아웃】 요소로 채울 배열입니다.

*pceltFetched*<br/>
【아웃】 실제로 *rgelt로*반환된 요소의 수입니다. 켈트 원소보다 적은 수의 *셀트* 요소가 목록에 남아 있는 경우 *셀트보다* 적을 수 있습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="ienumonstlimplreset"></a><a name="reset"></a>IEnumOnSTLImpl::재설정

이 메서드는 **재설정** 메서드의 구현을 제공합니다.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="ienumonstlimplskip"></a><a name="skip"></a>IEnumOnSTLImpl::건너뛰기

이 메서드는 **건너뛰기** 메서드의 구현을 제공합니다.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>매개 변수

*celt*<br/>
【인】 건너뛸 요소 의 수입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
