---
title: IWorker스레드클라이언트 인터페이스
ms.date: 11/04/2016
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
ms.openlocfilehash: 6a68f25f153a0ad2cf42ebfaa374ff63c5746fcd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326304"
---
# <a name="iworkerthreadclient-interface"></a>IWorker스레드클라이언트 인터페이스

`IWorkerThreadClient`은 [CWorkerThread](../../atl/reference/cworkerthread-class.md) 클래스의 클라이언트에서 구현한 인터페이스입니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
__interface IWorkerThreadClient
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[닫기 핸들](#closehandle)|이 메서드를 구현하여 이 개체와 연결된 핸들을 닫습니다.|
|[Execute](#execute)|이 개체와 연결된 핸들이 신호가 표시될 때 코드를 실행하려면 이 메서드를 구현합니다.|

## <a name="remarks"></a>설명

신호가 되는 핸들에 대한 응답으로 작업자 스레드에서 실행해야 하는 코드가 있는 경우 이 인터페이스를 구현합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a>IWorker스레드 클라이언트::닫기 핸들

이 메서드를 구현하여 이 개체와 연결된 핸들을 닫습니다.

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>매개 변수

*h핸들*<br/>
닫을 핸들입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드에 전달 된 핸들은 이전에 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)에 대 한 호출에 의해이 개체와 연결 되었습니다.

### <a name="example"></a>예제

다음 코드는 의 `IWorkerThreadClient::CloseHandle`간단한 구현을 보여 주며 의 구현을 보여 주며 있습니다.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a>IWorker스레드 클라이언트::실행

이 개체와 연결된 핸들이 신호가 표시될 때 코드를 실행하려면 이 메서드를 구현합니다.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>매개 변수

*dwParam*<br/>
사용자 매개 변수입니다.

*h개체*<br/>
신호가 된 핸들입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="remarks"></a>설명

이 메서드에 전달 된 핸들 및 DWORD/포인터는 이전에 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)에 대 한 호출에 의해이 개체와 연결 되었습니다.

### <a name="example"></a>예제

다음 코드는 의 `IWorkerThreadClient::Execute`간단한 구현을 보여 주며 의 구현을 보여 주며 있습니다.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>참고 항목

[클래스](../../atl/reference/atl-classes.md)<br/>
[CWorkerThread 클래스](../../atl/reference/cworkerthread-class.md)
