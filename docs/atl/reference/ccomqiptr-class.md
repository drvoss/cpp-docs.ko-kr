---
title: CComQIPtr 클래스
ms.date: 11/04/2016
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
ms.openlocfilehash: 2b1d8b92fbc5e95a5061956bafc4922d249a6f18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327426"
---
# <a name="ccomqiptr-class"></a>CComQIPtr 클래스

COM 인터페이스 포인터를 관리하기 위한 스마트 포인터 클래스입니다.

## <a name="syntax"></a>구문

```
template<class T, const IID* piid= &__uuidof(T)>
class CComQIPtr: public CComPtr<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
저장할 포인터 유형을 지정하는 COM 인터페이스입니다.

*piid*<br/>
*T.*

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComQIPtr:::CComQIPtr](#ccomqiptr)|생성자입니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CComQIPtr::연산자 =](#operator_eq)|멤버 포인터에 포인터를 할당합니다.|

## <a name="remarks"></a>설명

ATL은 `CComQIPtr` Com 인터페이스 포인터를 관리하기 위해 [CComPtr을](../../atl/reference/ccomptr-class.md) 사용하고 있으며, 둘 다 [CComPtrBase에서](../../atl/reference/ccomptrbase-class.md)파생됩니다. 두 클래스 모두 에 대한 `AddRef` `Release`호출 및 를 통해 자동 참조 계산을 수행합니다. 오버로드된 연산자는 포인터 작업을 처리합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

[CComPtr](../../atl/reference/ccomptr-class.md)

`CComQIPtr`

## <a name="requirements"></a>요구 사항

**헤더:** atlcomcli.h

## <a name="ccomqiptrccomqiptr"></a><a name="ccomqiptr"></a>CComQIPtr:::CComQIPtr

생성자입니다.

```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```

### <a name="parameters"></a>매개 변수

*Lp 로*<br/>
인터페이스 포인터를 초기화하는 데 사용됩니다.

*T*<br/>
COM 인터페이스입니다.

*piid*<br/>
*T.*

## <a name="ccomqiptroperator-"></a><a name="operator_eq"></a>CComQIPtr::연산자 =

할당 연산자입니다.

```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```

### <a name="parameters"></a>매개 변수

*Lp 로*<br/>
인터페이스 포인터를 초기화하는 데 사용됩니다.

*T*<br/>
COM 인터페이스입니다.

*piid*<br/>
*T.*

### <a name="return-value"></a>Return Value

업데이트된 `CComQIPtr` 개체에 대한 포인터를 반환합니다.

## <a name="see-also"></a>참고 항목

[CComPtr:::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)<br/>
[CComQIPtr:::CComQIPtr](#ccomqiptr)<br/>
[CComPtrBase 클래스](../../atl/reference/ccomptrbase-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CComQIPtrElementTraits 클래스](../../atl/reference/ccomqiptrelementtraits-class.md)
