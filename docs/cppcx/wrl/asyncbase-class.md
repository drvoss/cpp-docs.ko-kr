---
title: AsyncBase 클래스
ms.date: 10/08/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase
- async/Microsoft::WRL::AsyncBase::AsyncBase
- async/Microsoft::WRL::AsyncBase::Cancel
- async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
- async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall
- async/Microsoft::WRL::AsyncBase::Close
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
- async/Microsoft::WRL::AsyncBase::CurrentStatus
- async/Microsoft::WRL::AsyncBase::ErrorCode
- async/Microsoft::WRL::AsyncBase::FireCompletion
- async/Microsoft::WRL::AsyncBase::FireProgress
- async/Microsoft::WRL::AsyncBase::get_ErrorCode
- async/Microsoft::WRL::AsyncBase::get_Id
- async/Microsoft::WRL::AsyncBase::get_Status
- async/Microsoft::WRL::AsyncBase::GetOnComplete
- async/Microsoft::WRL::AsyncBase::GetOnProgress
- async/Microsoft::WRL::AsyncBase::OnCancel
- async/Microsoft::WRL::AsyncBase::OnClose
- async/Microsoft::WRL::AsyncBase::OnStart
- async/Microsoft::WRL::AsyncBase::put_Id
- async/Microsoft::WRL::AsyncBase::PutOnComplete
- async/Microsoft::WRL::AsyncBase::PutOnProgress
- async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
helpviewer_keywords:
- Microsoft::WRL::AsyncBase class
- Microsoft::WRL::AsyncBase::AsyncBase, constructor
- Microsoft::WRL::AsyncBase::Cancel method
- Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall method
- Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall method
- Microsoft::WRL::AsyncBase::Close method
- Microsoft::WRL::AsyncBase::ContinueAsyncOperation method
- Microsoft::WRL::AsyncBase::CurrentStatus method
- Microsoft::WRL::AsyncBase::ErrorCode method
- Microsoft::WRL::AsyncBase::FireCompletion method
- Microsoft::WRL::AsyncBase::FireProgress method
- Microsoft::WRL::AsyncBase::get_ErrorCode method
- Microsoft::WRL::AsyncBase::get_Id method
- Microsoft::WRL::AsyncBase::get_Status method
- Microsoft::WRL::AsyncBase::GetOnComplete method
- Microsoft::WRL::AsyncBase::GetOnProgress method
- Microsoft::WRL::AsyncBase::OnCancel method
- Microsoft::WRL::AsyncBase::OnClose method
- Microsoft::WRL::AsyncBase::OnStart method
- Microsoft::WRL::AsyncBase::put_Id method
- Microsoft::WRL::AsyncBase::PutOnComplete method
- Microsoft::WRL::AsyncBase::PutOnProgress method
- Microsoft::WRL::AsyncBase::TryTransitionToCompleted method
- Microsoft::WRL::AsyncBase::TryTransitionToError method
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
ms.openlocfilehash: 0254aa4dc243eeffa43850c437a833a6530c01e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371866"
---
# <a name="asyncbase-class"></a>AsyncBase 클래스

Windows 런타임 비동기 상태 컴퓨터를 구현합니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename TComplete,
    typename TProgress = Details::Nil,
    AsyncResultType resultType = SingleResult
>
class AsyncBase : public AsyncBase<TComplete, Details::Nil, resultType>;

template <typename TComplete, AsyncResultType resultType>
class AsyncBase<TComplete, Details::Nil, resultType> :
    public Microsoft::WRL::Implements<IAsyncInfo>;
```

### <a name="parameters"></a>매개 변수

*TComplete*<br/>
비동기 작업이 완료될 때 호출되는 이벤트 처리기입니다.

*TProgress*<br/>
실행 중인 비동기 작업이 작업의 현재 진행 률을 보고할 때 호출되는 이벤트 처리기입니다.

*결과 유형*<br/>
[AsyncResultType](asyncresulttype-enumeration.md) 열거 형 열거 값 중 하나입니다. 기본적으로 `SingleResult`입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

속성                               | Description
---------------------------------- | -------------------------------------------------
[비동기 베이스::비동기 베이스](#asyncbase) | `AsyncBase` 클래스의 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

속성                                         | Description
-------------------------------------------- | -------------------------------------------------------------------------------------
[비동기 베이스::취소](#cancel)                 | 비동기 작업을 취소합니다.
[비동기 베이스::닫기](#close)                   | 비동기 작업을 닫습니다.
[비동기 기반::화재 완료](#firecompletion) | 완료 이벤트 처리기를 호출하거나 내부 진행률 대리자를 다시 설정합니다.
[비동기 기지::화재 진행상황](#fireprogress)     | 현재 진행률 이벤트 처리기를 호출합니다.
[비동기 베이스::get_ErrorCode](#get-errorcode)   | 현재 비동기 작업에 대한 오류 코드를 검색합니다.
[비동기 베이스::get_Id](#get-id)                 | 비동기 작업의 핸들을 검색합니다.
[비동기 베이스:get_Status](#get-status)         | 비동기 작업의 상태를 나타내는 값을 검색합니다.
[비동기 베이스::GetOnComplete](#getoncomplete)   | 현재 완료 이벤트 처리기의 주소를 지정된 변수에 복사합니다.
[비동기 베이스::GetonProgress](#getonprogress)   | 현재 진행률 이벤트 처리기의 주소를 지정된 변수에 복사합니다.
[비동기베이스::put_Id](#put-id)                 | 비동기 작업의 핸들을 설정합니다.
[비동기베이스::PutonComplete](#putoncomplete)   | 완료 이벤트 처리기의 주소를 지정된 값으로 설정합니다.
[비동기베이스::PutonProgress](#putonprogress)   | 진행률 이벤트 처리기의 주소를 지정된 값으로 설정합니다.

### <a name="protected-methods"></a>Protected 메서드

속성                                                                         | Description
---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[비동기 베이스::체크유효상태ForDelegate호출](#checkvalidstatefordelegatecall) | 현재 비동기 상태에서 대리자 속성을 수정할 수 있는지 여부를 테스트합니다.
[비동기 베이스::체크유효상태검사결과콜](#checkvalidstateforresultscall)   | 비동기 작업의 결과를 현재 비동기 상태에서 수집할 수 있는지 여부를 테스트합니다.
[비동기 베이스::계속동기 작업](#continueasyncoperation)                 | 비동기 작업이 처리를 계속해야 하는지 아니면 중지해야 하는지 여부를 결정합니다.
[비동기 베이스::현재 상태](#currentstatus)                                   | 현재 비동기 작업의 상태를 검색합니다.
[비동기 베이스::오류 코드](#errorcode)                                           | 현재 비동기 작업에 대한 오류 코드를 검색합니다.
[비동기 베이스::온취소](#oncancel)                                             | 파생 클래스에서 재정의하면 비동기 작업이 취소됩니다.
[비동기 베이스::온클로즈](#onclose)                                               | 파생 클래스에서 재정의하면 비동기 작업이 닫힙됩니다.
[비동기 베이스::시작 시](#onstart)                                               | 파생 클래스에서 재정의하면 비동기 작업이 시작됩니다.
[비동기 베이스::시작](#start)                                                   | 비동기 작업을 시작합니다.
[비동기 베이스::시도전환완료](#trytransitiontocompleted)             | 현재 비동기 작업이 완료되었는지 여부를 나타냅니다.
[비동기 기반::tryTransitionToError](#trytransitiontoerror)                     | 지정된 오류 코드가 내부 오류 상태를 수정할 수 있는지 여부를 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>요구 사항

**헤더:** 비동기.h

**네임스페이스:** Microsoft::WRL

## <a name="asyncbaseasyncbase"></a><a name="asyncbase"></a>비동기 베이스::비동기 베이스

`AsyncBase` 클래스의 인스턴스를 초기화합니다.

```cpp
AsyncBase();
```

## <a name="asyncbasecancel"></a><a name="cancel"></a>비동기 베이스::취소

비동기 작업을 취소합니다.

```cpp
STDMETHOD(
   Cancel
)(void);
```

### <a name="return-value"></a>Return Value

기본적으로 항상 S_OK 반환합니다.

### <a name="remarks"></a>설명

`Cancel()`은 의 기본 `IAsyncInfo::Cancel`구현이며 실제 작업을 수행하지 않습니다. 실제로 비동기 작업을 취소하려면 순수 가상 `OnCancel()` 메서드를 재정의합니다.

## <a name="asyncbasecheckvalidstatefordelegatecall"></a><a name="checkvalidstatefordelegatecall"></a>비동기 베이스::체크유효상태ForDelegate호출

현재 비동기 상태에서 대리자 속성을 수정할 수 있는지 여부를 테스트합니다.

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

### <a name="return-value"></a>Return Value

S_OK 대리자 속성을 수정할 수 있는지 를 지정합니다. 그렇지 않으면, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasecheckvalidstateforresultscall"></a><a name="checkvalidstateforresultscall"></a>비동기 베이스::체크유효상태검사결과콜

비동기 작업의 결과를 현재 비동기 상태에서 수집할 수 있는지 여부를 테스트합니다.

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

### <a name="return-value"></a>Return Value

결과를 수집할 수 있는지 S_OK; 그렇지 않으면, E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseclose"></a><a name="close"></a>비동기 베이스::닫기

비동기 작업을 닫습니다.

```cpp
STDMETHOD(
   Close
)(void) override;
```

### <a name="return-value"></a>Return Value

작업이 닫히거나 이미 닫혔는지 S_OK. 그렇지 않으면, E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>설명

`Close()`은 의 기본 `IAsyncInfo::Close`구현이며 실제 작업을 수행하지 않습니다. 실제로 비동기 작업을 닫려면 순수 가상 `OnClose()` 메서드를 재정의합니다.

## <a name="asyncbasecontinueasyncoperation"></a><a name="continueasyncoperation"></a>비동기 베이스::계속동기 작업

비동기 작업이 처리를 계속해야 하는지 아니면 중지해야 하는지 여부를 결정합니다.

```cpp
inline bool ContinueAsyncOperation();
```

### <a name="return-value"></a>Return Value

**true** 는 비동기 작업의 현재 상태가 *시작되는*경우 작업을 계속해야 한다는 것을 의미합니다. 그렇지 않으면 **false는**작업이 중지되어야 한다는 것을 의미합니다.

## <a name="asyncbasecurrentstatus"></a><a name="currentstatus"></a>비동기 베이스::현재 상태

현재 비동기 작업의 상태를 검색합니다.

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
이 작업이 현재 상태를 저장하는 위치입니다.

### <a name="remarks"></a>설명

이 작업은 스레드에서 안전합니다.

## <a name="asyncbaseerrorcode"></a><a name="errorcode"></a>비동기 베이스::오류 코드

현재 비동기 작업에 대한 오류 코드를 검색합니다.

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>매개 변수

*error*<br/>
이 작업이 현재 오류 코드를 저장하는 위치입니다.

### <a name="remarks"></a>설명

이 작업은 스레드에서 안전합니다.

## <a name="asyncbasefirecompletion"></a><a name="firecompletion"></a>비동기 기반::화재 완료

완료 이벤트 처리기를 호출하거나 내부 진행률 대리자를 다시 설정합니다.

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

### <a name="remarks"></a>설명

첫 번째 `FireCompletion()` 버전의 재설정은 내부 진행률 대리자 변수입니다. 두 번째 버전은 비동기 작업이 완료되면 완료 이벤트 처리기를 호출합니다.

## <a name="asyncbasefireprogress"></a><a name="fireprogress"></a>비동기 기지::화재 진행상황

현재 진행률 이벤트 처리기를 호출합니다.

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>매개 변수

*Arg*<br/>
호출할 이벤트 처리기 메서드입니다.

### <a name="remarks"></a>설명

`ProgressTraits`[ArgTraits도움말 구조에서](argtraitshelper-structure.md)파생됩니다.

## <a name="asyncbaseget_errorcode"></a><a name="get-errorcode"></a>비동기 베이스::get_ErrorCode

현재 비동기 작업에 대한 오류 코드를 검색합니다.

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>매개 변수

*errorCode*<br/>
현재 오류 코드가 저장되는 위치입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 현재 비동기 작업이 닫혀 있는지 E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseget_id"></a><a name="get-id"></a>비동기 베이스::get_Id

비동기 작업의 핸들을 검색합니다.

```cpp
STDMETHOD(
   get_Id
)(unsigned int *id) override;
```

### <a name="parameters"></a>매개 변수

*id*<br/>
핸들을 저장할 위치입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면, E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>설명

이 메서드는 `IAsyncInfo::get_Id`를 구현합니다.

## <a name="asyncbaseget_status"></a><a name="get-status"></a>비동기 베이스:get_Status

비동기 작업의 상태를 나타내는 값을 검색합니다.

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
상태를 저장할 위치입니다. 자세한 내용은 열거를 참조하십시오. `Windows::Foundation::AsyncStatus`

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면, E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>설명

이 메서드는 `IAsyncInfo::get_Status`를 구현합니다.

## <a name="asyncbasegetoncomplete"></a><a name="getoncomplete"></a>비동기 베이스::GetOnComplete

현재 완료 이벤트 처리기의 주소를 지정된 변수에 복사합니다.

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>매개 변수

*전체 처리기*<br/>
현재 완료 이벤트 처리기의 주소가 저장되는 위치입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasegetonprogress"></a><a name="getonprogress"></a>비동기 베이스::GetonProgress

현재 진행률 이벤트 처리기의 주소를 지정된 변수에 복사합니다.

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>매개 변수

*진행률 처리기*<br/>
현재 진행률 이벤트 처리기의 주소가 저장되는 위치입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseoncancel"></a><a name="oncancel"></a>비동기 베이스::온취소

파생 클래스에서 재정의하면 비동기 작업이 취소됩니다.

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="asyncbaseonclose"></a><a name="onclose"></a>비동기 베이스::온클로즈

파생 클래스에서 재정의하면 비동기 작업이 닫힙됩니다.

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="asyncbaseonstart"></a><a name="onstart"></a>비동기 베이스::시작 시

파생 클래스에서 재정의하면 비동기 작업이 시작됩니다.

```cpp
virtual HRESULT OnStart(
   void
) = 0;
```

## <a name="asyncbaseput_id"></a><a name="put-id"></a>비동기베이스::put_Id

비동기 작업의 핸들을 설정합니다.

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>매개 변수

*id*<br/>
제로가 아닌 핸들입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면 E_INVALIDARG 또는 E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseputoncomplete"></a><a name="putoncomplete"></a>비동기베이스::PutonComplete

완료 이벤트 처리기의 주소를 지정된 값으로 설정합니다.

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>매개 변수

*전체 처리기*<br/>
완료 이벤트 처리기가 설정된 주소입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseputonprogress"></a><a name="putonprogress"></a>비동기베이스::PutonProgress

진행률 이벤트 처리기의 주소를 지정된 값으로 설정합니다.

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>매개 변수

*진행률 처리기*<br/>
진행률 이벤트 처리기가 설정된 주소입니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK; 그렇지 않으면, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasestart"></a><a name="start"></a>비동기 베이스::시작

비동기 작업을 시작합니다.

```cpp
STDMETHOD(
   Start
)(void);
```

### <a name="return-value"></a>Return Value

작업이 시작되었는지 또는 이미 시작된 지 S_OK. 그렇지 않으면, E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>설명

`Start()`는 호출자에게 돌아가기 전에 비동기 작업이 "핫 스타트"이기 때문에 외부에 표시되지 않는 보호된 메서드입니다.

## <a name="asyncbasetrytransitiontocompleted"></a><a name="trytransitiontocompleted"></a>비동기 베이스::시도전환완료

현재 비동기 작업이 완료되었는지 여부를 나타냅니다.

```cpp
bool TryTransitionToCompleted(
   void
);
```

### <a name="return-value"></a>Return Value

비동기 작업이 완료된 경우 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="asyncbasetrytransitiontoerror"></a><a name="trytransitiontoerror"></a>비동기 기반::tryTransitionToError

지정된 오류 코드가 내부 오류 상태를 수정할 수 있는지 여부를 나타냅니다.

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>매개 변수

*error*<br/>
오류 HRESULT.

### <a name="return-value"></a>Return Value

내부 오류 상태가 변경된 경우 **true입니다.** 그렇지 **않으면, 거짓**.

### <a name="remarks"></a>설명

이 작업은 오류 상태가 이미 S_OK 설정된 경우에만 오류 상태를 수정합니다. 오류 상태가 이미 오류, 취소, 완료 또는 닫힌 경우 이 작업은 영향을 주지 않습니다.
