---
title: IThreadPool구성 인터페이스
ms.date: 11/04/2016
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
ms.openlocfilehash: e4b90534fa89ef2aeffe4cd682d92efc16452487
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326352"
---
# <a name="ithreadpoolconfig-interface"></a>IThreadPool구성 인터페이스

이 인터페이스는 스레드 풀을 구성하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[GetSize](#getsize)|풀의 스레드 수를 얻으려면 이 메서드를 호출합니다.|
|[GetTimeout](#gettimeout)|스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 최대 시간을 밀리초 단위로 얻으려면 이 메서드를 호출합니다.|
|[Setsize](#setsize)|풀의 스레드 수를 설정하려면 이 메서드를 호출합니다.|
|[Settimeout](#settimeout)|스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 최대 시간을 밀리초 단위로 설정하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 [CThreadPool](../../atl/reference/cthreadpool-class.md)에 의해 구현됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="ithreadpoolconfiggetsize"></a><a name="getsize"></a>IThread풀 구성::GetSize

풀의 스레드 수를 얻으려면 이 메서드를 호출합니다.

```
STDMETHOD(GetSize)(int* pnNumThreads);
```

### <a name="parameters"></a>매개 변수

*pnNum스레드*<br/>
【아웃】 성공 시 풀의 스레드 수를 받는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]

## <a name="ithreadpoolconfiggettimeout"></a><a name="gettimeout"></a>IThread풀 구성::GetTimeout

스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 최대 시간을 밀리초 단위로 얻으려면 이 메서드를 호출합니다.

```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```

### <a name="parameters"></a>매개 변수

*pdwMaxWait*<br/>
【아웃】 성공 시 스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 최대 시간을 밀리초 단위로 받는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="example"></a>예제

[IThreadPoolConfig::GetSize](#getsize)를 참조하십시오.

## <a name="ithreadpoolconfigsetsize"></a><a name="setsize"></a>IThread풀 구성::세트크기

풀의 스레드 수를 설정하려면 이 메서드를 호출합니다.

```
STDMETHOD(SetSize)int nNumThreads);
```

### <a name="parameters"></a>매개 변수

*nNumThreads*<br/>
풀에서 요청된 스레드 수입니다.

*nNumThreads가* 음수이면 절대 값에 총 스레드 수를 얻기 위해 컴퓨터의 프로세서 수를 곱합니다.

*nNumThreads가* 0이면 ATLS_DEFAULT_THREADSPERPROC 컴퓨터의 프로세서 수에 총 스레드 수를 곱합니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="example"></a>예제

[IThreadPoolConfig::GetSize](#getsize)를 참조하십시오.

## <a name="ithreadpoolconfigsettimeout"></a><a name="settimeout"></a>IThread풀 구성::설정 시간 설정

스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 최대 시간을 밀리초 단위로 설정하려면 이 메서드를 호출합니다.

```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```

### <a name="parameters"></a>매개 변수

*드맥스웨이트*<br/>
스레드 풀이 스레드가 종료될 때까지 기다릴 수 있는 요청된 최대 시간(밀리초)입니다.

### <a name="return-value"></a>Return Value

성공 시 S_OK 반환하거나 오류 에러 HRESULT를 반환합니다.

### <a name="example"></a>예제

[IThreadPoolConfig::GetSize](#getsize)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스](../../atl/reference/atl-classes.md)<br/>
[C스레드풀 클래스](../../atl/reference/cthreadpool-class.md)
