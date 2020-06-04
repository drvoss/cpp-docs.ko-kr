---
title: DeferrableEventArgs 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
ms.openlocfilehash: 066918bf2c76b17f06871ee08be674be9b36c161
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032462"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs 클래스

지연에 대한 이벤트 인수 형식에 사용되는 템플릿 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <typename TEventArgsInterface, typename TEventArgsClass>
class DeferrableEventArgs : public TEventArgsInterface;
```

### <a name="parameters"></a>매개 변수

*TEventArgs인터페이스*<br/>
지연된 이벤트에 대한 인수를 선언하는 인터페이스 형식입니다.

*TEventArgsClass*<br/>
*TEventArgsInterface를*구현하는 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

| 속성 | Description |
|--|--|
| [추론 가능한 EventArgs::GetDeferral](#getdeferral) | 지연된 이벤트를 나타내는 [Deferral](/uwp/api/windows.foundation.deferral) 개체에 대한 참조를 가져옵니다. |
| [추론 가능한 이벤트아르그::호출모든 완료](#invokeallfinished) | 지연된 이벤트를 처리하는 모든 처리가 완료되었음을 나타내기 위해 호출됩니다. |

## <a name="remarks"></a>설명

이 클래스의 인스턴스는 지연된 이벤트에 대한 이벤트 처리기에 전달됩니다. 템플릿 매개 변수는 특정 형식의 지연된 이벤트에 대한 이벤트 인수 세부 정보를 정의하는 인터페이스 및 해당 인터페이스를 구현하는 클래스를 나타냅니다.

클래스는 지연된 이벤트에 대한 이벤트 처리기에 첫 번째 인수로 표시됩니다. [GetDeferral](#getdeferral) 메서드를 호출하여 지연 된 이벤트에 대한 모든 정보를 얻을 수있는 [지연](/uwp/api/windows.foundation.deferral) 개체를 얻을 수 있습니다. 이벤트 처리를 완료한 후 Deferral 개체에 대해 Complete를 호출해야 합니다. 그런 다음 이벤트 처리기 메서드끝에 [InvokeAllFinished를](#invokeallfinished) 호출하여 지연된 모든 이벤트의 완료가 제대로 전달되도록 해야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** Microsoft::WRL

## <a name="deferrableeventargsgetdeferral"></a><a name="getdeferral"></a>추론 가능한 EventArgs::GetDeferral

지연된 이벤트를 나타내는 [Deferral](/uwp/api/windows.foundation.deferral) 개체에 대한 참조를 가져옵니다.

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)
```

### <a name="parameters"></a>매개 변수

*결과*<br/>
호출이 완료될 때 [Deferral](/uwp/api/windows.foundation.deferral) 개체를 참조하는 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="deferrableeventargsinvokeallfinished"></a><a name="invokeallfinished"></a>추론 가능한 이벤트아르그::호출모든 완료

지연된 이벤트를 처리하는 모든 처리가 완료되었음을 나타내기 위해 호출됩니다.

```cpp
void InvokeAllFinished()
```

### <a name="remarks"></a>설명

이벤트 소스가 [InvokeAll](eventsource-class.md#invokeall)을 호출한 후 이 메서드를 호출해야 합니다. 이 메서드를 호출하면 추가 지연이 수행되지 않고, 수행된 지연이 없을 경우 완료 처리기가 강제로 실행됩니다.
