---
title: EventTargetArray 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
- event/Microsoft::WRL::Details::EventTargetArray::Begin
- event/Microsoft::WRL::Details::EventTargetArray::End
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::Length
- event/Microsoft::WRL::Details::EventTargetArray::~EventTargetArray
helpviewer_keywords:
- Microsoft::WRL::Details::EventTargetArray class
- Microsoft::WRL::Details::EventTargetArray::AddTail method
- Microsoft::WRL::Details::EventTargetArray::Begin method
- Microsoft::WRL::Details::EventTargetArray::End method
- Microsoft::WRL::Details::EventTargetArray::EventTargetArray, constructor
- Microsoft::WRL::Details::EventTargetArray::Length method
- Microsoft::WRL::Details::EventTargetArray::~EventTargetArray, destructor
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
ms.openlocfilehash: 9ea8800aa22a6b5cae0b3342cf337786fb53fc76
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371491"
---
# <a name="eventtargetarray-class"></a>EventTargetArray 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
class EventTargetArray :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<ClassicCom>,
        IUnknown
    >;
```

## <a name="remarks"></a>설명

이벤트 처리기의 배열을 나타냅니다.

[EventSource](eventsource-class.md) 개체와 연결된 이벤트 처리기는 보호된 `EventTargetArray` 데이터 멤버에 저장됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                                                           | Description
-------------------------------------------------------------- | -----------------------------------------------------------
[이벤트 대상 배열::이벤트 대상 배열](#eventtargetarray)        | `EventTargetArray` 클래스의 새 인스턴스를 초기화합니다.
[이벤트 대상 배열::~이벤트 대상 배열](#tilde-eventtargetarray) | 현재 `EventTargetArray` 클래스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                                  | Description
------------------------------------- | ---------------------------------------------------------------------------------------
[이벤트 대상 배열::추가 꼬리](#addtail) | 지정된 이벤트 처리기를 이벤트 처리기의 내부 배열 끝에 부가합니다.
[이벤트 대상 배열::시작](#begin)     | 이벤트 처리기의 내부 배열에서 첫 번째 요소의 주소를 가져옵니다.
[이벤트 대상 배열::종료](#end)         | 이벤트 처리기의 내부 배열에서 마지막 요소의 주소를 가져옵니다.
[이벤트 대상 배열::길이](#length)   | 이벤트 처리기의 내부 배열에 있는 요소의 현재 수를 가져옵니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`EventTargetArray`

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** 마이크로소프트::WRL::D테일

## <a name="eventtargetarrayeventtargetarray"></a><a name="tilde-eventtargetarray"></a>이벤트 대상 배열::~이벤트 대상 배열

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>설명

현재 `EventTargetArray` 클래스를 초기화합니다.

## <a name="eventtargetarrayaddtail"></a><a name="addtail"></a>이벤트 대상 배열::추가 꼬리

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>매개 변수

*요소*<br/>
이벤트 처리기에 대한 포인터를 더합니다.

### <a name="remarks"></a>설명

지정된 이벤트 처리기를 이벤트 처리기의 내부 배열 끝에 부가합니다.

`AddTail()`을 사용하려면 내부적으로 클래스만 `EventSource` 사용할 수 있습니다.

## <a name="eventtargetarraybegin"></a><a name="begin"></a>이벤트 대상 배열::시작

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>Return Value

이벤트 처리기의 내부 배열에서 첫 번째 요소의 주소입니다.

### <a name="remarks"></a>설명

이벤트 처리기의 내부 배열에서 첫 번째 요소의 주소를 가져옵니다.

## <a name="eventtargetarrayend"></a><a name="end"></a>이벤트 대상 배열::종료

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>Return Value

이벤트 처리기의 내부 배열에 있는 마지막 요소의 주소입니다.

### <a name="remarks"></a>설명

이벤트 처리기의 내부 배열에서 마지막 요소의 주소를 가져옵니다.

## <a name="eventtargetarrayeventtargetarray"></a><a name="eventtargetarray"></a>이벤트 대상 배열::이벤트 대상 배열

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>매개 변수

*Hr*<br/>
이 생성자 작업 후 매개 변수 *hr* 배열의 할당 성공 또는 실패 여부를 나타냅니다. 다음 목록은 *hr에*대한 가능한 값을 보여 주며 있습니다.

- S_OK<br/>
  작업에 성공했습니다.

- E_OUTOFMEMORY<br/>
  어레이에 메모리를 할당할 수 없습니다.

- S_FALSE<br/>
  매개 변수 *항목은* 0보다 적거나 같습니다.

*항목*<br/>
할당할 배열 요소의 수입니다.

### <a name="remarks"></a>설명

`EventTargetArray` 클래스의 새 인스턴스를 초기화합니다.

`EventTargetArray`는 `EventSource` 이벤트 처리기의 배열을 개체에 유지하는 데 사용됩니다.

## <a name="eventtargetarraylength"></a><a name="length"></a>이벤트 대상 배열::길이

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
size_t Length();
```

### <a name="return-value"></a>Return Value

이벤트 처리기의 내부 배열의 현재 요소 수입니다.

### <a name="remarks"></a>설명

이벤트 처리기의 내부 배열에 있는 요소의 현재 수를 가져옵니다.
