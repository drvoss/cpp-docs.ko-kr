---
title: InjectEvent
description: C++ BUILD Insights SDK InjectEvent 함수 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7b53eb71cf7a2ae40d04dbc3f8b5829f2737aba4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334417"
---
# <a name="injectevent"></a>InjectEvent

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`InjectEvent` 함수는 [irelogger](../other-types/irelogger-class.md) 인터페이스를 구현 하는 재로 거 거 내에서 호출 됩니다. 이는 relogging 세션의 출력 추적 파일에 ETW(Windows용 이벤트 추적) (ETW) 이벤트를 작성 하는 데 사용 됩니다.

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

*Relogsession*\
재 로깅 세션에 대 한 포인터입니다. 다시 로깅 세션은 `IRelogger` 인터페이스를 구현 하는 relogging 제공 됩니다. 자세한 내용은 [Irelogger](../other-types/irelogger-class.md)를 참조 하세요.

*providerId*\
Etw 이벤트를 relogged 하는 ETW (ETW(Windows용 이벤트 추적)) 공급자 GUID입니다.

*Eventdescriptor*\
Relogged ETW 이벤트에 대 한 ETW 이벤트 설명자입니다.

*processId*\
Relogged ETW 이벤트에 대 한 PID (프로세스 식별자)입니다.

*threadId*\
Relogged ETW 이벤트의 TID (스레드 식별자)입니다.

*processorIndex*\
Relogged ETW 이벤트의 프로세서 인덱스입니다.

*타임 스탬프*\
Relogged ETW 이벤트의 타임 스탬프입니다.

*데이터*\
Relogged ETW 이벤트에 포함 되어야 하는 데이터에 대 한 포인터입니다.

*byteCount*\
데이터가 가리키는 데이터의 크기 (바이트) *입니다.*

## <a name="remarks"></a>주의

*공급자 GUID* 및 *이벤트 설명자*와 같은 etw 개념에 대 한 자세한 내용은 [etw 설명서](/windows/win32/etw/about-event-tracing)를 참조 하십시오. C++ BUILD Insights SDK를 사용 하 여 relogging 세션을 시작 하는 방법에 대 한 자세한 내용은 [Relog](relog.md)를 참조 하세요.

::: moniker-end
