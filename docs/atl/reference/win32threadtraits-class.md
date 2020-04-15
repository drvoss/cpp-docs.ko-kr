---
title: Win32ThreadTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
ms.openlocfilehash: 64f02293508894a70f36c29d5032c9ba8f250c38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325795"
---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits 클래스

이 클래스는 Windows 스레드에 대한 만들기 함수를 제공합니다. 스레드에서 CRT 함수를 사용하지 않는 경우 이 클래스를 사용합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class Win32ThreadTraits
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[Win32스레드 특성::만들기스레드](#createthread)|(정적) CRT 함수를 사용 하지 않아야 하는 스레드를 만들려면이 함수를 호출 합니다.|

## <a name="remarks"></a>설명

스레드 특성은 특정 유형의 스레드에 대한 생성 함수를 제공하는 클래스입니다. 생성 함수에는 Windows [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) 함수와 동일한 시그니처 및 의미 체계가 있습니다.

스레드 특성은 다음 클래스에서 사용됩니다.

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [워커스레드](../../atl/reference/cworkerthread-class.md)

스레드가 CRT 함수를 사용하는 경우 대신 [CRTThreadTraits를](../../atl/reference/crtthreadtraits-class.md) 사용합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="win32threadtraitscreatethread"></a><a name="createthread"></a>Win32스레드 특성::만들기스레드

CRT 함수를 사용 하지 않아야 하는 스레드를 만들려면이 함수를 호출 합니다.

```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```

### <a name="parameters"></a>매개 변수

*lpsa*<br/>
새 스레드에 대한 보안 특성입니다.

*dw스택사이즈*<br/>
새 스레드의 스택 크기입니다.

*pfn스레드프로크*<br/>
새 스레드의 스레드 프로시저입니다.

*pvParam*<br/>
스레드 프로시저에 전달할 매개 변수입니다.

*dw크리에이션 플래그*<br/>
생성 플래그(0 또는 CREATE_SUSPENDED).

*pdwThreadId*<br/>
【아웃】 성공 시 새로 생성된 스레드의 스레드 ID를 수신하는 DWORD 변수의 주소입니다.

### <a name="return-value"></a>Return Value

실패 시 새로 생성된 스레드 또는 NULL에 핸들을 반환합니다. [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 호출하여 확장 오류 정보를 가져옵니다.

### <a name="remarks"></a>설명

이 함수에 대한 매개 변수에 대한 자세한 내용은 [CreateThread를](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) 참조하십시오.

이 함수는 스레드를 만들기 위해 호출합니다. `CreateThread`

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
