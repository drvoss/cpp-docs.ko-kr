---
title: CFileTimeSpan 클래스
description: 활성 템플릿 라이브러리(ATL) 및 Microsoft 파운데이션 클래스(MFC) CFileTimeSpan 클래스는 FILETIME 단위의 시간 간격을 관리합니다.
ms.date: 01/10/2020
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
ms.openlocfilehash: 87737ea1c778660a68510b484bcdfa3a4670e8ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317849"
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan 클래스

이 클래스는 파일과 연결된 상대 날짜 및 시간 값을 관리하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```cpp
class CFileTimeSpan
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C파일 타임스팬::CFile타임스팬](#cfiletimespan)|생성자입니다.|

### <a name="public-methods"></a>public 메서드

|속성|Description|
|----------|-----------------|
|[C파일 타임스팬::GetTimeSpan](#gettimespan)|이 메서드를 호출하여 개체에서 `CFileTimeSpan` 시간 범위를 검색합니다.|
|[C파일 타임스팬::설정 시간 범위](#settimespan)|이 메서드를 호출하여 개체의 `CFileTimeSpan` 시간 범위를 설정합니다.|

### <a name="public-operators"></a>공공 사업자

|속성|Description|
|----------|-----------------|
|[CFile 시간 범위::연산자 -](#operator_-)|개체에 대한 `CFileTimeSpan` 빼기 를 수행합니다.|
|[CFile 시간 범위::연산자 !=](#operator_neq)|두 `CFileTimeSpan` 개체가 다른지 비교합니다.|
|[CFile 시간 범위::연산자 +](#operator_add)|개체에 대한 `CFileTimeSpan` 추가를 수행합니다.|
|[CFile 시간 범위::연산자 +=](#operator_add_eq)|개체에 대한 `CFileTimeSpan` 추가를 수행하고 결과를 현재 개체에 할당합니다.|
|[CFile 시간 범위:연산자&lt;](#operator_lt)|두 `CFileTimeSpan` 개체를 비교하여 더 작은 개체를 결정합니다.|
|[CFile 시간 범위:연산자&lt;=](#operator_lt_eq)|두 `CFileTimeSpan` 개체를 비교하여 같음 또는 더 낮은 개체를 결정합니다.|
|[CFile 시간 범위::연산자 =](#operator_eq)|할당 연산자입니다.|
|[CFile 시간 범위::연산자 -=](#operator_-_eq)|`CFileTimeSpan` 개체에 대한 빼기를 수행하고 결과를 현재 개체에 할당합니다.|
|[CFile 시간 범위::연산자 ==](#operator_eq_eq)|두 `CFileTimeSpan` 개체가 같은지 비교합니다.|
|[CFile 시간 범위:연산자&gt;](#operator_gt)|두 `CFileTimeSpan` 개체를 비교하여 더 큰 개체를 결정합니다.|
|[CFile 시간 범위:연산자&gt;=](#operator_gt_eq)|두 `CFileTimeSpan` 개체를 비교하여 같음 또는 더 큰 개체를 결정합니다.|

## <a name="remarks"></a>설명

클래스는 `CFileTimeSpan` 파일 시스템에서 사용하는 단위로 상대 적인 기간을 처리하는 메서드를 제공합니다. 이러한 단위는 파일이 만들어지거나 마지막으로 액세스되거나 마지막으로 수정된 경우와 같이 파일 작업에 자주 사용됩니다. 이 클래스의 메서드는 [CFileTime 클래스](../../atl-mfc-shared/reference/cfiletime-class.md) 개체와 함께 자주 사용 됩니다.

## <a name="example"></a>예제

[CFileTime::밀리초의](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond)예제를 참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** 아틀타임.h

## <a name="cfiletimespancfiletimespan"></a><a name="cfiletimespan"></a>C파일 타임스팬::CFile타임스팬

생성자입니다.

```cpp
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
기존 `CFileTimeSpan` 개체입니다.

*n스팬 (것)과 함께*\
FILETIME 단위의 기간입니다.

### <a name="remarks"></a>설명

객체는 `CFileTimeSpan` 기존 `CFileTimeSpan` 객체를 사용하여 만들거나 100나노초 FILETIME 단위로 64비트 값으로 표현할 수 있습니다. 자세한 내용은 [CFileTime](cfiletime-class.md)을 참조하십시오. 기본 생성자는 시간 범위를 0으로 설정합니다.

## <a name="cfiletimespangettimespan"></a><a name="gettimespan"></a>C파일 타임스팬::GetTimeSpan

이 메서드를 호출하여 개체에서 `CFileTimeSpan` 시간 범위를 검색합니다.

```cpp
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>반환 값

100나노초 FILETIME 단위로 시간 범위를 반환합니다. 자세한 내용은 [CFileTime](cfiletime-class.md)을 참조하십시오.

## <a name="cfiletimespanoperator--"></a><a name="operator_-"></a>CFile 시간 범위::연산자 -

개체에 대한 `CFileTimeSpan` 빼기 를 수행합니다.

```cpp
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

두 `CFileTimeSpan` 시간 범위 간의 차이의 결과를 나타내는 개체를 반환합니다.

## <a name="cfiletimespanoperator-"></a><a name="operator_neq"></a>CFile 시간 범위::연산자 !=

두 `CFileTimeSpan` 개체가 다른지 비교합니다.

```cpp
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

비교 중인 항목이 개체와 같지 않은 `CFileTimeSpan` 경우 TRUE를 반환합니다. 그렇지 않으면 거짓.

## <a name="cfiletimespanoperator-"></a><a name="operator_add"></a>CFile 시간 범위::연산자 +

개체에 대한 `CFileTimeSpan` 추가를 수행합니다.

```cpp
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

두 `CFileTimeSpan` 시간 범위의 합계를 포함하는 객체를 반환합니다.

## <a name="cfiletimespanoperator-"></a><a name="operator_add_eq"></a>CFile 시간 범위::연산자 +=

개체에 대한 `CFileTimeSpan` 추가를 수행하고 결과를 현재 개체에 할당합니다.

```cpp
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

두 시간 `CFileTimeSpan` 범위의 합계를 포함하는 업데이트된 개체를 반환합니다.

## <a name="cfiletimespanoperator-lt"></a><a name="operator_lt"></a>CFile 시간 범위:연산자&lt;

두 `CFileTimeSpan` 개체를 비교하여 더 작은 개체를 결정합니다.

```cpp
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체가 두 번째 개체보다 적으면 TRUE를 반환합니다(즉, 짧은 기간), 그렇지 않으면 FALSE입니다.

## <a name="cfiletimespanoperator-lt"></a><a name="operator_lt_eq"></a>CFile 시간 범위:연산자&lt;=

두 `CFileTimeSpan` 개체를 비교하여 같음 또는 더 낮은 개체를 결정합니다.

```cpp
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체가 더 작은 경우 TRUE를 반환합니다(즉, 더 짧은 기간을 나타내거나 두 번째 개체와 같거나 FALSE).

## <a name="cfiletimespanoperator-"></a><a name="operator_eq"></a>CFile 시간 범위::연산자 =

할당 연산자입니다.

```cpp
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

업데이트된 `CFileTimeSpan` 개체를 반환합니다.

## <a name="cfiletimespanoperator--"></a><a name="operator_-_eq"></a>CFile 시간 범위::연산자 -=

`CFileTimeSpan` 개체에 대한 빼기를 수행하고 결과를 현재 개체에 할당합니다.

```cpp
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

업데이트된 `CFileTimeSpan` 개체를 반환합니다.

## <a name="cfiletimespanoperator-"></a><a name="operator_eq_eq"></a>CFile 시간 범위::연산자 ==

두 `CFileTimeSpan` 개체가 같은지 비교합니다.

```cpp
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

개체가 같으면 TRUE를 반환합니다( 그렇지 않으면 FALSE).

## <a name="cfiletimespanoperator-gt"></a><a name="operator_gt"></a>CFile 시간 범위:연산자&gt;

두 `CFileTimeSpan` 개체를 비교하여 더 큰 개체를 결정합니다.

```cpp
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체가 두 번째 개체보다 큰 경우 TRUE를 반환합니다(즉, 더 긴 기간), 그렇지 않으면 FALSE입니다.

## <a name="cfiletimespanoperator-gt"></a><a name="operator_gt_eq"></a>CFile 시간 범위:연산자&gt;=

두 `CFileTimeSpan` 개체를 비교하여 같음 또는 더 큰 개체를 결정합니다.

```cpp
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*범위*\
비교할 `CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체가 더 큰 경우 TRUE를 반환합니다(즉, 더 긴 기간을 나타내거나 두 번째 개체와 같거나 FALSE).

## <a name="cfiletimespansettimespan"></a><a name="settimespan"></a>C파일 타임스팬::설정 시간 범위

이 메서드를 호출하여 개체의 `CFileTimeSpan` 시간 범위를 설정합니다.

```cpp
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>매개 변수

*n스팬 (것)과 함께*\
100나노초 FILETIME 단위의 시간 범위에 대한 새 값입니다. 자세한 내용은 [CFileTime](cfiletime-class.md)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[Filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime)\
[CFileTime 클래스](cfiletime-class.md)\
[계층 구조 차트](../../mfc/hierarchy-chart.md)\
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
