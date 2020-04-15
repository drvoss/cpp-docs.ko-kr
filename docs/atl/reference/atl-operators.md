---
title: ATL 연산자
ms.date: 11/04/2016
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
ms.openlocfilehash: 8c15daa1d2b12c58323ef5ef75559a2ab911ad93
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319229"
---
# <a name="atl-operators"></a>ATL 연산자

이 섹션에는 ATL 전역 연산자에 대한 참조 항목이 포함되어 있습니다.

|연산자|Description|
|--------------|-----------------|
|[연산자 ==](#operator_eq_eq)|두 `CSid` 개체 또는 `SID` 구조를 비교하여 같음입니다.|
|[연산자 !=](#operator_neq)|두 `CSid` 개체 또는 `SID` 구조를 비교하여 부등값입니다.|
|[연산자 <](#operator_lt)|연산자의 `CSid` 왼쪽에 있는 개체 또는 `SID` 구조가 오른쪽의 `CSid` 개체 또는 `SID` 구조보다 적은지 테스트합니다(C++ 표준 라이브러리 호환성의 경우).|
|[연산자 >](#operator_gt)|연산자의 `CSid` 왼쪽에 있는 개체 또는 `SID` 구조가 오른쪽의 `CSid` 개체 또는 `SID` 구조보다 큰지 테스트합니다(C++ 표준 라이브러리 호환성의 경우).|
|[연산자 <=](#operator_lt__eq)|연산자의 `CSid` 왼쪽에 있는 개체 또는 `SID` 구조가 오른쪽의 `CSid` 개체 또는 `SID` 구조보다 적거나 같는지 테스트합니다(C++ 표준 라이브러리 호환성의 경우).|
|[연산자 >=](#operator_gt__eq)|연산자의 `CSid` 왼쪽에 있는 개체 또는 `SID` 구조가 오른쪽의 `CSid` 개체 또는 `SID` 구조보다 크거나 같는지 테스트합니다(C++ 표준 라이브러리 호환성의 경우).|

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h.

## <a name="operator-"></a><a name="operator_eq_eq"></a>연산자 ==

`CSid` 개체 또는 `SID` (보안 식별자) 구조를 같음으로 비교합니다.

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 `CSid` 첫 `SID` 번째 개체 또는 구조입니다.

*rhs*<br/>
비교할 `CSid` 두 `SID` 번째 개체 또는 구조체입니다.

### <a name="return-value"></a>Return Value

개체가 같으면 TRUE를 반환하고 FALSE는 같지 않은 경우 반환합니다.

## <a name="operator-"></a><a name="operator_neq"></a>연산자 !=

`CSid` 개체 또는 `SID` (보안 식별자) 구조를 비교하여 부등값에 대해 비교합니다.

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 `CSid` 첫 `SID` 번째 개체 또는 구조입니다.

*rhs*<br/>
비교할 `CSid` 두 `SID` 번째 개체 또는 구조체입니다.

### <a name="return-value"></a>Return Value

개체가 같지 않은 경우 TRUE를 반환하고 FALSE를 반환합니다.

## <a name="operator-"></a><a name="operator_lt"></a>연산자 <

연산자의 `CSid` 왼쪽에 있는 개체 또는 `SID` 구조가 오른쪽의 `CSid` 개체 또는 `SID` 구조보다 적은지 테스트합니다(C++ 표준 라이브러리 호환성의 경우).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 `CSid` 첫 `SID` 번째 개체 또는 구조입니다.

*rhs*<br/>
비교할 `CSid` 두 `SID` 번째 개체 또는 구조체입니다.

### <a name="return-value"></a>Return Value

*lhs* 개체의 주소가 rhs 개체의 주소보다 적으면 *TRUE를* 반환합니다.

### <a name="remarks"></a>설명

이 연산자는 `CSid` 개체 또는 `SID` 구조의 주소에 따라 작동하며 C++ 표준 라이브러리 컬렉션 클래스와의 호환성을 제공하기 위해 구현됩니다.

## <a name="operator-"></a><a name="operator_gt"></a>연산자 >

연산자의 `CSid` 왼쪽에 있는 개체 또는 `SID` 구조가 오른쪽의 `CSid` 개체 또는 `SID` 구조보다 큰지 테스트합니다(C++ 표준 라이브러리 호환성의 경우).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 `CSid` 첫 `SID` 번째 개체 또는 구조입니다.

*rhs*<br/>
비교할 `CSid` 두 `SID` 번째 개체 또는 구조체입니다.

### <a name="return-value"></a>Return Value

*lhs의* 주소가 *rhs의*주소보다 큰 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 연산자는 `CSid` 개체 또는 `SID` 구조의 주소에 따라 작동하며 C++ 표준 라이브러리 컬렉션 클래스와의 호환성을 제공하기 위해 구현됩니다.

## <a name="operator-"></a><a name="operator_lt__eq"></a>연산자 <=

연산자의 `CSid` 왼쪽에 있는 개체 또는 `SID` 구조가 오른쪽의 `CSid` 개체 또는 `SID` 구조보다 적거나 같는지 테스트합니다(C++ 표준 라이브러리 호환성의 경우).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 `CSid` 첫 `SID` 번째 개체 또는 구조입니다.

*rhs*<br/>
비교할 `CSid` 두 `SID` 번째 개체 또는 구조체입니다.

### <a name="return-value"></a>Return Value

*lhs의* 주소가 *rhs의*주소보다 적거나 같으면 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 연산자는 `CSid` 개체 또는 `SID` 구조의 주소에 따라 작동하며 C++ 표준 라이브러리 컬렉션 클래스와의 호환성을 제공하기 위해 구현됩니다.

## <a name="operator-"></a><a name="operator_gt__eq"></a>연산자 >=

연산자의 `CSid` 왼쪽에 있는 개체 또는 `SID` 구조가 오른쪽의 `CSid` 개체 또는 `SID` 구조보다 크거나 같는지 테스트합니다(C++ 표준 라이브러리 호환성의 경우).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*Lhs*<br/>
비교할 `CSid` 첫 `SID` 번째 개체 또는 구조입니다.

*rhs*<br/>
비교할 `CSid` 두 `SID` 번째 개체 또는 구조체입니다.

### <a name="return-value"></a>Return Value

*lhs의* 주소가 *rhs의*주소보다 크거나 같으면 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 연산자는 `CSid` 개체 또는 `SID` 구조의 주소에 따라 작동하며 C++ 표준 라이브러리 컬렉션 클래스와의 호환성을 제공하기 위해 구현됩니다.
