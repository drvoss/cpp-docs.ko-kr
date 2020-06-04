---
title: WeakReference 클래스
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::Resolve
- implements/Microsoft::WRL::Details::WeakReference::SetUnknown
- implements/Microsoft::WRL::Details::WeakReference::~WeakReference
- implements/Microsoft::WRL::Details::WeakReference::WeakReference
helpviewer_keywords:
- Microsoft::WRL::Details::WeakReference class
- Microsoft::WRL::Details::WeakReference::DecrementStrongReference method
- Microsoft::WRL::Details::WeakReference::IncrementStrongReference method
- Microsoft::WRL::Details::WeakReference::Resolve method
- Microsoft::WRL::Details::WeakReference::SetUnknown method
- Microsoft::WRL::Details::WeakReference::~WeakReference, destructor
- Microsoft::WRL::Details::WeakReference::WeakReference, constructor
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
ms.openlocfilehash: a80c0ec14da2a955a95ac84dd3975212ef20ae04
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374212"
---
# <a name="weakreference-class"></a>WeakReference 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
class WeakReference;
```

## <a name="remarks"></a>설명

Windows 런타임 또는 클래식 COM과 함께 사용할 수 있는 *약한 참조를* 나타냅니다. 약한 참조는 액세스할 수 있거나 액세스할 수 없는 개체를 나타냅니다.

개체는 `WeakReference` 개체에 대한 포인터인 *강력한 참조와* `Resolve()` 메서드에 의해 분산된 강력한 *참조의*복사본 수인 강력한 참조 수를 유지 관리합니다. 강력한 참조 수는 0이 아닌 반면 강력한 참조는 유효하며 개체에 액세스할 수 있습니다. 강력한 참조 수가 0이 되면 강력한 참조가 유효하지 않으며 개체에 액세스할 수 없습니다.

`WeakReference` 개체는 일반적으로 외부 스레드 또는 응용 프로그램에 의해 존재가 제어되는 개체를 나타내는 데 사용됩니다. 예를 들어 참조에서 `WeakReference` 파일 개체로 개체를 생성합니다. 파일이 열려 있는 동안 강력한 참조는 유효합니다. 그러나 파일이 닫히면 강력한 참조는 유효하지 않게 됩니다.

메서드는 `WeakReference` 스레드에서 안전합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                                  | Description
----------------------------------------------------- | ---------------------------------------------------------------------------
[약점 참조::약한 참조](#weakreference)        | `WeakReference` 클래스의 새 인스턴스를 초기화합니다.
[약점 참조::~약한 참조](#tilde-weakreference) | 클래스의 현재 인스턴스를 초기화(소멸)합니다. `WeakReference`

### <a name="public-methods"></a>Public 메서드

속성                                                                 | Description
-------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[약한 참조::Decrement강한 참조](#decrementstrongreference) | 현재 `WeakReference` 개체의 강력한 참조 수를 감소시입니다.
[약점 참조::증분강한 참조](#incrementstrongreference) | 현재 `WeakReference` 개체의 강력한 참조 수를 증가시입니다.
[약점 참조::해결](#resolve)                                   | 강력한 참조 수가 0이 아닌 경우 지정된 포인터를 현재 강력한 참조 값으로 설정합니다.
[약점 참조::설정알 수 없음](#setunknown)                             | 현재 `WeakReference` 개체의 강력한 참조를 지정된 인터페이스 포인터로 설정합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`WeakReference`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="weakreferenceweakreference"></a><a name="tilde-weakreference"></a>약점 참조::~약한 참조

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
virtual ~WeakReference();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

클래스의 현재 인스턴스를 초기화합니다. `WeakReference`

## <a name="weakreferencedecrementstrongreference"></a><a name="decrementstrongreference"></a>약한 참조::Decrement강한 참조

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
ULONG DecrementStrongReference();
```

### <a name="remarks"></a>설명

현재 `WeakReference` 개체의 강력한 참조 수를 감소시입니다.

강력한 참조 수가 0이 되면 강력한 참조가 로 `nullptr`설정됩니다.

### <a name="return-value"></a>Return Value

감소된 강력한 참조 수입니다.

## <a name="weakreferenceincrementstrongreference"></a><a name="incrementstrongreference"></a>약점 참조::증분강한 참조

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
ULONG IncrementStrongReference();
```

### <a name="return-value"></a>Return Value

증가된 강력한 참조 수입니다.

### <a name="remarks"></a>설명

현재 `WeakReference` 개체의 강력한 참조 수를 증가시입니다.

## <a name="weakreferenceresolve"></a><a name="resolve"></a>약점 참조::해결

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
STDMETHOD(Resolve)
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*ppvObject*<br/>
이 작업이 완료되면 강력한 참조 수가 0이 아닌 경우 현재 강력한 참조의 복사본입니다.

### <a name="return-value"></a>Return Value

- 이 작업이 성공하고 강력한 참조 수가 0인지 S_OK. *ppvObject* 매개 변수가 `nullptr`로 설정됩니다.

- 이 작업이 성공하고 강력한 참조 수가 0이 아닌지 S_OK. *ppvObject* 매개 변수는 강력한 참조로 설정됩니다.

- 그렇지 않으면 이 작업이 실패한 이유를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

강력한 참조 수가 0이 아닌 경우 지정된 포인터를 현재 강력한 참조 값으로 설정합니다.

## <a name="weakreferencesetunknown"></a><a name="setunknown"></a>약점 참조::설정알 수 없음

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
void SetUnknown(
   _In_ IUnknown* unk
);
```

### <a name="parameters"></a>매개 변수

*언크 (것)와 같은*<br/>
개체의 인터페이스에 대한 `IUnknown` 포인터입니다.

### <a name="remarks"></a>설명

현재 `WeakReference` 개체의 강력한 참조를 지정된 인터페이스 포인터로 설정합니다.

## <a name="weakreferenceweakreference"></a><a name="weakreference"></a>약점 참조::약한 참조

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
WeakReference();
```

### <a name="remarks"></a>설명

`WeakReference` 클래스의 새 인스턴스를 초기화합니다.

개체에 `WeakReference` 대한 강력한 참조 포인터가 `nullptr`초기화되고 강력한 참조 수가 1로 초기화됩니다.
