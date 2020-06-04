---
title: 커맨드라인 클래스
description: C++ 빌드 인사이트 SDK 명령줄 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b35d688acf06579cc27f2fee053ef58032e204e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325056"
---
# <a name="commandline-class"></a>커맨드라인 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `CommandLine` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [COMMAND_LINE](../event-table.md#command-line) 이벤트와 일치하는 데 사용합니다.

## <a name="syntax"></a>구문

```cpp
class CommandLine : public SimpleEvent
{
public:
    CommandLine(const RawEvent& event);

    const wchar_t* Value() const;
};
```

## <a name="members"></a>멤버

[SimpleEvent](simple-event.md) 기본 클래스에서 상속된 멤버와 `CommandLine` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[명령줄](#command-line)

### <a name="functions"></a>Functions

[값](#value)

## <a name="commandline"></a><a name="command-line"></a>명령줄

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[COMMAND_LINE](../event-table.md#command-line) 이벤트입니다.

## <a name="value"></a><a name="value"></a> 값

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Return Value

명령줄이 포함된 문자열입니다. \_이 값에는 CL, CL,\_Link 및 LINK와 \_\_같은 응답 파일 및 환경 변수에서 얻은 인수가 포함됩니다.

::: moniker-end
