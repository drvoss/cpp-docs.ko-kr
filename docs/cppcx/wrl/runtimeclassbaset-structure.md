---
title: RuntimeClassBaseT 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
helpviewer_keywords:
- Microsoft::WRL::Details::RuntimeClassBaseT structure
- Microsoft::WRL::Details::RuntimeClassBaseT::AsIID method
- Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS method
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
ms.openlocfilehash: 06a9f73e00d541b0e5bcbe20c57befe4a67c5132
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375729"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <unsigned int RuntimeClassTypeT>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>매개 변수

*런타임클래스TypeT*<br/>
하나 이상의 [RuntimeClassType](runtimeclasstype-enumeration.md) 열거형을 지정하는 플래그 필드입니다.

## <a name="remarks"></a>설명

`QueryInterface` 작업 및 인터페이스 아이디 를 가져오는 도우미 메서드를 제공합니다.

## <a name="members"></a>멤버

### <a name="protected-methods"></a>Protected 메서드

속성                                                         | Description
------------------------------------------------------------ | -----------------------------------------------------------------------------
[런타임클래스베이스:::아시ID](#asiid)                           | 지정된 인터페이스 ID에 대한 포인터를 검색합니다.
[런타임클래스베이스T::Get구현IIDS](#getimplementediids) | 지정된 형식에 의해 구현되는 인터페이스 아이디의 배열을 검색합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`RuntimeClassBaseT`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="runtimeclassbasetasiid"></a><a name="asiid"></a>런타임클래스베이스:::아시ID

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
template<typename T>
__forceinline static HRESULT AsIID(
   _In_ T* implements,
   REFIID riid,
   _Deref_out_ void **ppvObject
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
매개 변수 *riid에*의해 지정된 인터페이스 ID를 구현하는 형식입니다.

*구현*<br/>
템플릿 매개 변수 *T에*의해 지정된 형식의 변수입니다.

*riid*<br/>
검색할 인터페이스 ID입니다.

*ppvObject*<br/>
이 작업이 성공하면 매개 변수 *riid로*지정된 인터페이스에 대한 포인터 대 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류를 설명하는 HRESULT입니다.

### <a name="remarks"></a>설명

지정된 인터페이스 ID에 대한 포인터를 검색합니다.

## <a name="runtimeclassbasetgetimplementediids"></a><a name="getimplementediids"></a>런타임클래스베이스T::Get구현IIDS

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
template<typename T>
__forceinline static HRESULT GetImplementedIIDS(
   _In_ T* implements,
   _Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
구현 매개 변수의 *형식입니다.*

*구현*<br/>
매개 변수 *T*.

*이드 카운트*<br/>
검색할 최대 인터페이스 아이디 수입니다.

*아이드 (이드)*<br/>
이 작업이 성공적으로 완료되면 *T*유형으로 구현된 인터페이스 ID의 배열입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 오류를 설명하는 HRESULT입니다.

### <a name="remarks"></a>설명

지정된 형식에 의해 구현되는 인터페이스 아이디의 배열을 검색합니다.
