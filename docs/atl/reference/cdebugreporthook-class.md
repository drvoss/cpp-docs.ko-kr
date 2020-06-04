---
title: CDebugReport후크 클래스
ms.date: 11/04/2016
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
ms.openlocfilehash: 8380556bbe007326156bf0ec0eefc23052e8e056
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747726"
---
# <a name="cdebugreporthook-class"></a>CDebugReport후크 클래스

이 클래스를 사용하여 디버그 보고서를 명명된 파이프로 보냅니다.

## <a name="syntax"></a>구문

```
class CDebugReportHook
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C데버그리포트후크::C데버그리포트후크](#cdebugreporthook)|[SetPipeName,](#setpipename) [setTimeout](#settimeout)및 [SetHook을](#sethook)호출합니다.|
|[CDebug보고서 후크::~CDebugReport후크](#dtor)|[CDebugReport후크 호출::제거 후크](#removehook).|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDebug보고서 후크::C데버그리포트후크프로크](#cdebugreporthookproc)|(정적) C 런타임 디버그 보고 프로세스에 연결되는 사용자 지정 보고 함수입니다.|
|[CDebugReport후크::리크후크](#removehook)|이 메서드를 호출하여 명명된 파이프에 디버그 보고서를 보내는 것을 중지하고 이전 보고서 후크를 복원합니다.|
|[CDebug보고서 후크::세트후크](#sethook)|이 메서드를 호출하여 명명된 파이프에 디버그 보고서를 보내기 시작합니다.|
|[CDebugReport후크::세트파이프이름](#setpipename)|이 메서드를 호출하여 디버그 보고서가 전송될 파이프의 컴퓨터와 이름을 설정합니다.|
|[CDebugReport후크::설정 시간 제한](#settimeout)|이 메서드를 호출하여 이 클래스가 명명된 파이프를 사용할 수 있게 될 때까지 기다릴 시간을 밀리초 단위로 설정합니다.|

## <a name="remarks"></a>설명

서비스 또는 응용 프로그램의 디버그 빌드에서 이 클래스의 인스턴스를 만들어 명명된 파이프에 디버그 보고서를 보냅니다. 디버그 보고서는 [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 호출하거나 [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) 및 [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) 매크로와 같은 이 함수에 래퍼를 사용하여 생성됩니다.

이 클래스를 사용하면 비대화형 [창 스테이션에서](/windows/win32/winstation/window-stations)실행되는 구성 요소를 대화형으로 디버깅할 수 있습니다.

디버그 보고서는 스레드의 기본 보안 컨텍스트를 사용하여 전송됩니다. 웹 응용 프로그램과 같이 권한이 낮은 사용자의 가장이 이루어지는 상황에서 디버그 보고서를 볼 수 있도록 가장이 일시적으로 비활성화됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlutil.h

## <a name="cdebugreporthookcdebugreporthook"></a><a name="cdebugreporthook"></a>C데버그리포트후크::C데버그리포트후크

[SetPipeName,](#setpipename) [setTimeout](#settimeout)및 [SetHook을](#sethook)호출합니다.

```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```

### <a name="parameters"></a>매개 변수

*szMachineName*<br/>
디버그 출력을 보낼 컴퓨터의 이름입니다. 로컬 컴퓨터의 기본값입니다.

*szPipeName*<br/>
디버그 출력을 보낼 명명된 파이프의 이름입니다.

*dw타임아웃*<br/>
이 클래스가 명명된 파이프를 사용할 수 있게 될 때까지 기다리는 시간(밀리초)입니다.

## <a name="cdebugreporthookcdebugreporthook"></a><a name="dtor"></a>CDebug보고서 후크::~CDebugReport후크

[CDebugReport후크 호출::제거 후크](#removehook).

```
~CDebugReportHook() throw();
```

## <a name="cdebugreporthookcdebugreporthookproc"></a><a name="cdebugreporthookproc"></a>CDebug보고서 후크::C데버그리포트후크프로크

C 런타임 디버그 보고 프로세스에 연결되는 사용자 지정 보고 함수입니다.

```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```

### <a name="parameters"></a>매개 변수

*보고서유형*<br/>
보고서 유형(_CRT_WARN, _CRT_ERROR 또는 _CRT_ASSERT).

*message*<br/>
메시지 문자열입니다.

*반환값*<br/>
[_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)반환해야 하는 값입니다.

### <a name="return-value"></a>Return Value

후크가 문제의 메시지를 완전히 처리하는 경우 FALSE를 반환하여 추가 보고가 필요하지 않습니다. 정상적인 방법으로 `_CrtDbgReport` 메시지를 보고해야 하는 경우 TRUE를 반환합니다.

### <a name="remarks"></a>설명

보고 함수는 명명된 파이프를 열고 다른 쪽 끝에서 프로세스와 통신하려고 시도합니다. 파이프가 사용 중이면 보고 기능이 파이프가 사용 중이거나 시간 시간이 만료될 때까지 기다립니다. 시간 제한은 생성자 또는 [CDebugReportHook::SetTimeout에](#settimeout)대한 호출에 의해 설정할 수 있습니다.

이 함수의 코드는 호출 스레드의 기본 보안 컨텍스트에서 실행됩니다.

## <a name="cdebugreporthookremovehook"></a><a name="removehook"></a>CDebugReport후크::리크후크

이 메서드를 호출하여 명명된 파이프에 디버그 보고서를 보내는 것을 중지하고 이전 보고서 후크를 복원합니다.

```cpp
void RemoveHook() throw();
```

### <a name="remarks"></a>설명

이전 보고서 후크를 복원하려면 [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) 호출합니다.

## <a name="cdebugreporthooksethook"></a><a name="sethook"></a>CDebug보고서 후크::세트후크

이 메서드를 호출하여 명명된 파이프에 디버그 보고서를 보내기 시작합니다.

```cpp
void SetHook() throw();
```

### <a name="remarks"></a>설명

_CrtSetReportHook2 [호출은](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) [CDebugReportHookProc을](#cdebugreporthookproc) 통해 명명된 파이프로 라우팅된 디버그 보고서를 갖습니다. 이 클래스는 [RemoveHook이](#removehook) 호출될 때 복원할 수 있도록 이전 보고서 후크를 추적합니다.

## <a name="cdebugreporthooksetpipename"></a><a name="setpipename"></a>CDebugReport후크::세트파이프이름

이 메서드를 호출하여 디버그 보고서가 전송될 파이프의 컴퓨터와 이름을 설정합니다.

```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```

### <a name="parameters"></a>매개 변수

*szMachineName*<br/>
디버그 출력을 보낼 컴퓨터의 이름입니다.

*szPipeName*<br/>
디버그 출력을 보낼 명명된 파이프의 이름입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

## <a name="cdebugreporthooksettimeout"></a><a name="settimeout"></a>CDebugReport후크::설정 시간 제한

이 메서드를 호출하여 이 클래스가 명명된 파이프를 사용할 수 있게 될 때까지 기다릴 시간을 밀리초 단위로 설정합니다.

```cpp
void SetTimeout(DWORD dwTimeout);
```

### <a name="parameters"></a>매개 변수

*dw타임아웃*<br/>
이 클래스가 명명된 파이프를 사용할 수 있게 될 때까지 기다리는 시간(밀리초)입니다.

## <a name="see-also"></a>참조

[클래스](../../atl/reference/atl-classes.md)
