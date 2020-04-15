---
title: CComEnumImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CComEnumImpl
- ATLCOM/ATL::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::Clone
- ATLCOM/ATL::CComEnumImpl::Init
- ATLCOM/ATL::CComEnumImpl::Next
- ATLCOM/ATL::CComEnumImpl::Reset
- ATLCOM/ATL::CComEnumImpl::Skip
- ATLCOM/ATL::CComEnumImpl::m_begin
- ATLCOM/ATL::CComEnumImpl::m_dwFlags
- ATLCOM/ATL::CComEnumImpl::m_end
- ATLCOM/ATL::CComEnumImpl::m_iter
- ATLCOM/ATL::CComEnumImpl::m_spUnk
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
ms.openlocfilehash: 965e0a8bf6c890882754b60e2785832933d1c52c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327858"
---
# <a name="ccomenumimpl-class"></a>CComEnumImpl 클래스

이 클래스는 열거되는 항목이 배열에 저장되는 COM 열거자 인터페이스에 대한 구현을 제공합니다.

## <a name="syntax"></a>구문

```
template <class Base,
    const IID* piid, class T, class Copy>
class ATL_NO_VTABLE CComEnumImpl : public Base
```

#### <a name="parameters"></a>매개 변수

*기본*<br/>
COM 열거자 인터페이스입니다. 예는 [IEnumString을](/windows/win32/api/objidl/nn-objidl-ienumstring) 참조하십시오.

*piid*<br/>
열거자 인터페이스의 인터페이스 ID에 대한 포인터입니다.

*T*<br/>
열거자 인터페이스에서 노출되는 항목의 유형입니다.

*복사*<br/>
균일 한 [복사 정책 클래스입니다.](../../atl/atl-copy-policy-classes.md)

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|생성자입니다.|
|[CComEnumImpl:::~CComEnumImpl](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComEnumImpl::클론](#clone)|**복제** 인터페이스 메서드의 구현입니다.|
|[CComEnumImpl::Init](#init)|열거자를 초기화합니다.|
|[CComEnumImpl::다음](#next)|**다음**의 구현 .|
|[CComEnumImpl::재설정](#reset)|**재설정**의 구현 .|
|[CComEnumImpl::건너뛰기](#skip)|**건너뛰기**의 구현 .|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComEnumImpl::m_begin](#m_begin)|배열의 첫 번째 항목에 대한 포인터입니다.|
|[CComEnumImpl::m_dwFlags](#m_dwflags)|를 통과한 `Init`복사 플래그입니다.|
|[CComEnumImpl::m_end](#m_end)|배열의 마지막 항목 바로 너머의 위치에 대한 포인터입니다.|
|[CComEnumImpl::m_iter](#m_iter)|배열의 현재 항목에 대한 포인터입니다.|
|[CComEnumImpl::m_spUnk](#m_spunk)|수집을 제공하는 개체의 `IUnknown` 포인터가 포함됩니다.|

## <a name="remarks"></a>설명

메서드 구현의 예는 [IEnumString을](/windows/win32/api/objidl/nn-objidl-ienumstring) 참조하십시오. `CComEnumImpl`은 열거되는 항목이 배열에 저장되는 COM 열거체 인터페이스에 대한 구현을 제공합니다. 이 클래스는 C++ 표준 라이브러리 컨테이너를 `IEnumOnSTLImpl` 기반으로 열거자 인터페이스의 구현을 제공하는 클래스와 유사합니다.

> [!NOTE]
> 및 `CComEnumImpl` `IEnumOnSTLImpl`의 추가 차이점에 대한 자세한 내용은 [CComEnumImpl::Init](#init)을 참조하십시오.

일반적으로 이 인터페이스 구현에서 파생하여 고유한 열거자 클래스를 만들 필요가 *없습니다.* 배열을 기반으로 ATL 제공 열거체를 사용하려는 경우 [CComEnum](../../atl/reference/ccomenum-class.md)의 인스턴스를 만드는 것이 더 일반적입니다.

그러나 사용자 지정 열거자(예: 열거자 인터페이스 외에 인터페이스를 노출하는 열거체)를 제공해야 하는 경우 이 클래스에서 파생할 수 있습니다. 이 경우 자체 구현을 제공 하려면 [CComEnumImpl::복제](#clone) 메서드를 재정의 해야 합니다.

자세한 내용은 [ATL 컬렉션 및 열거자를](../../atl/atl-collections-and-enumerators.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComEnumImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomenumimplccomenumimpl"></a><a name="ccomenumimpl"></a>CComEnumImpl::CComEnumImpl

생성자입니다.

```
CComEnumImpl();
```

## <a name="ccomenumimplccomenumimpl"></a><a name="dtor"></a>CComEnumImpl:::~CComEnumImpl

소멸자입니다.

```
~CComEnumImpl();
```

## <a name="ccomenumimplinit"></a><a name="init"></a>CComEnumImpl::Init

모든 클라이언트에 다시 열거자 인터페이스에 포인터를 전달 하기 전에이 메서드를 호출 해야 합니다.

```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```

### <a name="parameters"></a>매개 변수

*시작*<br/>
열거할 항목을 포함하는 배열의 첫 번째 요소에 대한 포인터입니다.

*end*<br/>
열거할 항목을 포함하는 배열의 마지막 요소를 벗어난 위치에 대한 포인터입니다.

*pUnk*<br/>
【인】 열거자의 수명 동안 살아 있어야 하는 개체의 `IUnknown` 포인터입니다. 이러한 개체가 없는 경우 NULL을 전달합니다.

*플래그*<br/>
열거자가 배열의 소유권을 가져가거나 복사본을 만들어야 하는지 여부를 지정하는 플래그입니다. 가능한 값은 아래에 설명되어 있습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 메서드를 한 번만 호출합니다 - 열거체를 초기화하고 사용한 다음 버리지 않습니다.

다른 개체에 있는 배열의 항목에 대한 포인터를 전달하는 경우(열거체에게 데이터를 복사하도록 요청하지 않는 경우) *pUnk* 매개 변수를 사용하여 열거자가 필요로 하는 한 해당 개체와 배열을 사용할 수 있도록 할 수 있습니다. 열거자는 단순히 살아 있는 상태로 유지하기 위해 개체에 COM 참조를 보유합니다. COM 참조는 열거자가 소멸되면 자동으로 해제됩니다.

*플래그* 매개 변수를 사용하면 열거자가 전달된 배열 요소를 처리하는 방법을 지정할 수 있습니다. *플래그는* 아래 `CComEnumFlags` 열거형의 값 중 하나를 취할 수 있습니다.

```
enum CComEnumFlags
   {
   AtlFlagNoCopy = 0,
   AtlFlagTakeOwnership = 2, // BitOwn
   AtlFlagCopy = 3           // BitOwn | BitCopy
   };
```

`AtlFlagNoCopy`즉, 배열의 수명이 열거형에 의해 제어되지 않음을 의미합니다. 이 경우 배열이 정적이거나 *pUnk로* 식별된 개체가 더 이상 필요하지 않을 때 배열을 해제해야 합니다.

`AtlFlagTakeOwnership`즉, 배열의 소멸은 열거자가 제어해야 한다는 것을 의미합니다. 이 경우 배열은 **새**을 사용하여 동적으로 할당되어 있어야 합니다. 열거자는 소멸자에서 배열을 삭제합니다. 일반적으로 어떤 이유로 열거자의 파괴에 대한 알림을 받아야하는 경우 유효한 포인터를 통과 할 수 있지만 *pUnk에*대해 NULL을 전달합니다.

`AtlFlagCopy`에 전달된 배열을 복사하여 새 배열을 `Init`만들어야 한다는 의미입니다. 새 배열의 수명은 열거자가 제어해야 합니다. 열거자는 소멸자에서 배열을 삭제합니다. 일반적으로 어떤 이유로 열거자의 파괴에 대한 알림을 받아야하는 경우 유효한 포인터를 통과 할 수 있지만 *pUnk에*대해 NULL을 전달합니다.

> [!NOTE]
> 이 메서드의 프로토타입은 배열 요소를 클래스에 `T`대한 `T` 템플릿 매개 변수로 정의된 형식의 요소로 지정합니다. 이것은 COM 인터페이스 방법 [CComEnumImpl::Next를](#next)통해 노출되는 것과 동일한 형식입니다. 이는 [IEnumOnSTLImpl과](../../atl/reference/ienumonstlimpl-class.md)달리 이 클래스는 다른 저장소 및 노출된 데이터 형식을 지원하지 않는다는 의미입니다. 배열의 요소의 데이터 형식은 COM 인터페이스를 통해 노출된 데이터 형식과 같아야 합니다.

## <a name="ccomenumimplclone"></a><a name="clone"></a>CComEnumImpl::클론

이 메서드는 형식의 **Clone** `CComEnum`개체를 만들고 현재 개체에서 사용하는 동일한 배열 및 반복기로 초기화하고 새로 만든 개체에서 인터페이스를 반환하여 복제 메서드의 구현을 제공합니다.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>매개 변수

*ppEnum*<br/>
【아웃】 새로 생성된 개체의 열거자 인터페이스가 현재 열거체에서 복제되었습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

복제된 열거자는 원래 열거자가 사용하는 데이터의 자체 복사본(또는 소유권을 가져가지 않습니다)을 만들지 않습니다. 필요한 경우 복제된 열거자는 원래 열거자를 COM 참조를 사용하여 살아 있게 유지하여 필요한 기간 동안 데이터를 사용할 수 있도록 합니다.

## <a name="ccomenumimplm_spunk"></a><a name="m_spunk"></a>CComEnumImpl::m_spUnk

이 스마트 포인터는 [CComEnumImpl::Init에](#init)전달된 개체에 대한 참조를 유지관리하여 열거자의 수명 동안 살아 있게 합니다.

```
CComPtr<IUnknown> m_spUnk;
```

## <a name="ccomenumimplm_begin"></a><a name="m_begin"></a>CComEnumImpl::m_begin

열거할 항목을 포함하는 배열의 마지막 요소를 벗어난 위치에 대한 포인터입니다.

```
T* m_begin;
```

## <a name="ccomenumimplm_end"></a><a name="m_end"></a>CComEnumImpl::m_end

열거할 항목을 포함하는 배열의 첫 번째 요소에 대한 포인터입니다.

```
T* m_end;
```

## <a name="ccomenumimplm_iter"></a><a name="m_iter"></a>CComEnumImpl::m_iter

열거할 항목을 포함하는 배열의 현재 요소에 대한 포인터입니다.

```
T* m_iter;
```

## <a name="ccomenumimplm_dwflags"></a><a name="m_dwflags"></a>CComEnumImpl::m_dwFlags

플래그는 [CComEnumImpl에 전달 ::Init](#init).

```
DWORD m_dwFlags;
```

## <a name="ccomenumimplnext"></a><a name="next"></a>CComEnumImpl::다음

이 메서드는 **Next** 메서드의 구현을 제공합니다.

```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```

### <a name="parameters"></a>매개 변수

*celt*<br/>
【인】 요청된 요소 수입니다.

*rgelt*<br/>
【아웃】 요소로 채워질 배열입니다.

*pceltFetched*<br/>
【아웃】 실제로 *rgelt로*반환된 요소의 수입니다. 켈트 원소보다 적은 수의 *셀트* 원소가 목록에 남아 있는 경우 이는 *셀트보다* 적을 수 있습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="ccomenumimplreset"></a><a name="reset"></a>CComEnumImpl::재설정

이 메서드는 **재설정** 메서드의 구현을 제공합니다.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="ccomenumimplskip"></a><a name="skip"></a>CComEnumImpl::건너뛰기

이 메서드는 **건너뛰기** 메서드의 구현을 제공합니다.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>매개 변수

*celt*<br/>
【인】 건너뛸 요소 의 수입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

*셀트가* 0이면 E_INVALIDARG 반환되고, *셀트* 원보다 S_FALSE 반환되고, 그렇지 않으면 반환S_OK 반환합니다.

## <a name="see-also"></a>참고 항목

[IEnumOnSTLImpl 클래스](../../atl/reference/ienumonstlimpl-class.md)<br/>
[CComEnum 클래스](../../atl/reference/ccomenum-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
