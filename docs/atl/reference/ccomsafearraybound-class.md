---
title: CComSafeArrayBound 클래스
ms.date: 05/06/2019
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
ms.openlocfilehash: 2c2f8b787e5366ec893538a88049f6f53dc35caf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327377"
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound 클래스

이 클래스는 [SAFEARRAYBOUND](/windows/win32/api/oaidl/ns-oaidl-safearraybound) 구조의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CComSafeArrayBound](#ccomsafearraybound)|생성자입니다.|
|[GetCount](#getcount)|요소 수를 반환하려면 이 메서드를 호출합니다.|
|[겟로어바운드](#getlowerbound)|하한을 반환하려면 이 메서드를 호출합니다.|
|[겟어퍼바운드](#getupperbound)|이 메서드를 호출하여 상한을 반환합니다.|
|[세트 카운트](#setcount)|요소 수를 설정하려면 이 메서드를 호출합니다.|
|[설정하바운드](#setlowerbound)|하한을 설정하려면 이 메서드를 호출합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 =](#operator_eq)|을 `CComSafeArrayBound` 새 값으로 설정합니다.|

## <a name="remarks"></a>설명

이 클래스는 `SAFEARRAYBOUND` [CComSafeArray에서](../../atl/reference/ccomsafearray-class.md)사용하는 구조에 대한 래퍼입니다. `CComSafeArray` 개체의 단일 차원과 포함된 요소 수의 상한및 하한을 쿼리하고 설정하는 메서드를 제공합니다. 다차원 `CComSafeArray` 개체는 각 `CComSafeArrayBound` 차원에 대해 하나씩 개체 배열을 사용합니다. 따라서 [GetCount와](#getcount)같은 메서드를 사용할 때는 이 메서드가 다차원 배열의 총 요소 수를 반환하지 않습니다.

**헤더:** atlsafe.h

## <a name="requirements"></a>요구 사항

**헤더:** atlsafe.h

## <a name="ccomsafearrayboundccomsafearraybound"></a><a name="ccomsafearraybound"></a>CComSafeArray바운드::CComSafeArraybound

생성자입니다.

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>매개 변수

*울카운트*<br/>
배열의 요소 수입니다.

*로어바운드*<br/>
배열에 번호가 매겨진 하한입니다.

### <a name="remarks"></a>설명

C++ 프로그램에서 배열에 액세스하려면 하한을 0으로 정의하는 것이 좋습니다. 배열을 Visual Basic과 같은 다른 언어와 함께 사용하는 경우 다른 하한 값을 사용하는 것이 좋습니다.

## <a name="ccomsafearrayboundgetcount"></a><a name="getcount"></a>CComSafeArray바운드::겟카운트

요소 수를 반환하려면 이 메서드를 호출합니다.

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>Return Value

요소 수를 반환합니다.

### <a name="remarks"></a>설명

연결된 `CComSafeArray` 개체가 다차원 배열을 나타내는 경우 이 메서드는 가장 오른쪽 차원의 총 요소 수만 반환합니다. [CComSafeArray::GetCount를](../../atl/reference/ccomsafearray-class.md#getcount) 사용하여 총 요소 수를 가져옵니다.

## <a name="ccomsafearrayboundgetlowerbound"></a><a name="getlowerbound"></a>CComSafeArray바운드::겟로어바운드

하한을 반환하려면 이 메서드를 호출합니다.

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>Return Value

개체의 하한을 `CComSafeArrayBound` 반환합니다.

## <a name="ccomsafearrayboundgetupperbound"></a><a name="getupperbound"></a>CComSafeArray바운드::겟어퍼바운드

이 메서드를 호출하여 상한을 반환합니다.

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>Return Value

개체의 상한을 `CComSafeArrayBound` 반환합니다.

### <a name="remarks"></a>설명

상한은 요소 수와 하한 값에 따라 달라집니다. 예를 들어 하한이 0이고 요소 수가 10이면 상한이 자동으로 9로 설정됩니다.

## <a name="ccomsafearrayboundoperator-"></a><a name="operator_eq"></a>CComSafeArray바운드::연산자 =

을 `CComSafeArrayBound` 새 값으로 설정합니다.

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>매개 변수

*바인딩됨*<br/>
`CComSafeArrayBound` 개체입니다.

*울카운트*<br/>
요소의 수입니다.

### <a name="return-value"></a>Return Value

개체에 대한 `CComSafeArrayBound` 포인터를 반환합니다.

### <a name="remarks"></a>설명

객체는 `CComSafeArrayBound` 기존 `CComSafeArrayBound`을 사용하거나 요소 수를 제공하여 할당할 수 있으며, 이 경우 하한은 기본적으로 0으로 설정됩니다.

## <a name="ccomsafearrayboundsetcount"></a><a name="setcount"></a>CComSafeArray바운드::세트카운트

요소 수를 설정하려면 이 메서드를 호출합니다.

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>매개 변수

*울카운트*<br/>
요소의 수입니다.

### <a name="return-value"></a>Return Value

개체의 요소 수를 `CComSafeArrayBound` 반환합니다.

## <a name="ccomsafearrayboundsetlowerbound"></a><a name="setlowerbound"></a>CComSafe어레이바운드::세트로바운드바운드

하한을 설정하려면 이 메서드를 호출합니다.

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>매개 변수

*로어바운드*<br/>
하한입니다.

### <a name="return-value"></a>Return Value

개체의 새 하한을 반환합니다. `CComSafeArrayBound`

### <a name="remarks"></a>설명

Visual C++ 프로그램에서 배열에 액세스하려면 하한을 0으로 정의하는 것이 좋습니다. 배열을 Visual Basic과 같은 다른 언어와 함께 사용하는 경우 다른 하한 값을 사용하는 것이 좋습니다.

상한은 요소 수와 하한 값에 따라 달라집니다. 예를 들어 하한이 0이고 요소 수가 10이면 상한이 자동으로 9로 설정됩니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
