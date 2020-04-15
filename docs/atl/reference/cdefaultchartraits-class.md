---
title: CDefaultCharTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
ms.openlocfilehash: 40c4d107d05e6d7b610e7c46be920d91d8fe6086
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327101"
---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits 클래스

이 클래스는 대문자와 소문자 간에 문자를 변환하기 위한 두 가지 정적 함수를 제공합니다.

## <a name="syntax"></a>구문

```
template <typename T>
class CDefaultCharTraits
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDefaultCharTraits:::차토로워](#chartolower)|(정적) 이 함수를 호출하여 문자를 대문자로 변환합니다.|
|[CDefaultCharTraits::CharToupper](#chartoupper)|(정적) 문자를 소문자로 변환하려면 이 함수를 호출합니다.|

## <a name="remarks"></a>설명

이 클래스는 [클래스 CStringElementTraitsI에서](../../atl/reference/cstringelementtraitsi-class.md)사용하는 함수를 제공합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="cdefaultchartraitschartolower"></a><a name="chartolower"></a>CDefaultCharTraits:::차토로워

문자를 소문자로 변환하려면 이 함수를 호출합니다.

```
static wchar_t CharToLower(wchar_t x);
static char CharToLower(char x);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
소문자로 변환할 문자입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

## <a name="cdefaultchartraitschartoupper"></a><a name="chartoupper"></a>CDefaultCharTraits::CharToupper

이 함수를 호출하여 문자를 대문자로 변환합니다.

```
static wchar_t CharToUpper(wchar_t x);
static char CharToUpper(char x);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
대문자로 변환할 문자입니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
