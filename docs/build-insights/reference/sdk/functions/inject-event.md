---
title: 인젝스 이벤트
description: C++ 빌드 인사이트 SDK InjectEvent 함수 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c82aad5923eff60e5c72ceccaa39aa136f942665
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324046"
---
# <a name="injectevent"></a>인젝스 이벤트

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

이 `InjectEvent` 함수는 [IRelogger](../other-types/irelogger-class.md) 인터페이스를 구현하는 리로거 내에서 호출됩니다. 리로깅 세션의 출력 추적 파일에 ETW(Windows용 이벤트 추적) 이벤트를 작성하는 데 사용됩니다.

## <a name="syntax"></a>구문

```cpp
void InjectEvent(
    const void* relogSession,
    LPCGUID providerId,
    PCEVENT_DESCRIPTOR eventDescriptor,
    unsigned long processId,
    unsigned long threadId,
    unsigned short processorIndex,
    long long timestamp,
    unsigned char* data,
    unsigned long byteCount);
```

### <a name="parameters"></a>매개 변수

*다시 로그세션*\
리로깅 세션에 대한 포인터입니다. 인터페이스를 구현하는 리로거에 리로깅 `IRelogger` 세션이 제공됩니다. 자세한 내용은 [IRelogger](../other-types/irelogger-class.md).

*공급자ID*\
ETW 이벤트가 다시 기록되는 WINDOWS용 이벤트 추적(ETW) 공급자 GUID입니다.

*이벤트 설명자*\
다시 기록된 ETW 이벤트에 대한 ETW 이벤트 설명자입니다.

*프로세스 ID*\
다시 기록된 ETW 이벤트에 대한 프로세스 식별자(PID)입니다.

*스레드 ID*\
다시 로깅된 ETW 이벤트의 스레드 식별자(TID)입니다.

*프로세서 인덱스*\
다시 기록된 ETW 이벤트의 프로세서 인덱스입니다.

*타임 스탬프*\
다시 기록된 ETW 이벤트의 타임스탬프입니다.

*데이터*\
다시 기록된 ETW 이벤트에 포함해야 하는 데이터에 대한 포인터입니다.

*바이트 카운트*\
데이터 로 가리키는 바이트의 데이터 *크기입니다.*

## <a name="remarks"></a>설명

*공급자 GUID* 및 *이벤트 설명자와*같은 ETW 개념에 대한 자세한 내용은 [ETW 설명서를](/windows/win32/etw/about-event-tracing)참조하십시오. C++ 빌드 인사이트 SDK로 리로깅 세션을 시작하는 방법에 대한 자세한 내용은 [Relog](relog.md)를 참조하십시오.

::: moniker-end
