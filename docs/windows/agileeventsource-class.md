---
title: AgileEventSource 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- AgileEventSource class
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d025fc2be86fb5b59107d1deee39962c3c6db04
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="agileeventsource-class"></a>AgileEventSource 클래스
Agile 이벤트를 나타냅니다. 상속 [EventSource](eventsource-class.md) 재정의 `Add` agile 이벤트를 호출 하는 방법에 대 한 옵션을 지정 하기 위한 추가 형식 매개 변수가 있는 멤버 함수입니다.
  
## <a name="syntax"></a>구문  
  
```  
template<typename TDelegateInterface, typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>>
class AgileEventSource
    : public Microsoft::WRL::EventSource<TDelegateInterface, TEventSourceOptions>;
```  
  
#### <a name="parameters"></a>매개 변수  
 `TDelegateInterface`  
 인터페이스는 이벤트 처리기를 나타내는 대리자입니다.

 `TEventSourceOptions` [InvokeModeOptions](invokemodeoptions-structure.md) 인 invokeMode 필드가로 설정 된 구조체 `InvokeMode::StopOnFirstError` 또는 `InvokeMode::FireAll`합니다.

## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[AgileEventSource::Add 메서드](#add)|집합의 현재 AgileEventSource 개체에 대 한 이벤트 처리기에 지정한 대리자 인터페이스를 나타내는 민첩 한 이벤트 처리기를 추가 합니다.|  

## <a name="add"></a> AgileEventSource::Add 메서드

현재 EventSource 개체에 대 한 이벤트 처리기의 집합에 지정 된 대리자 인터페이스를 나타내는 이벤트 처리기를 추가 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);
```

### <a name="parameters"></a>매개 변수

*delegateInterface*

이벤트 처리기를 나타내는 대리자 개체를 인터페이스입니다.

*토큰* 이 작업이 완료 될 때, 이벤트를 나타내는 하는 핸들입니다. Remove () 메서드를 매개 변수로이 토큰을 사용 하 여 이벤트 처리기를 삭제 합니다.

### <a name="return-value"></a>반환 값
성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="inheritance-hierarchy"></a>상속 계층  
 `EventSource`  
 `AgileEventSource`
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)