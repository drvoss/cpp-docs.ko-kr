---
title: CommandLine 클래스
description: C++ BUILD Insights SDK CommandLine 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ff16646920fe77f7f3b4cb8a194a38984c3e6c32
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334987"
---
# <a name="commandline-class"></a>CommandLine 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`CommandLine` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 이를 사용 하 여 [COMMAND_LINE](../event-table.md#command-line) 이벤트를 일치 시킵니다.

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

[SimpleEvent](simple-event.md) 기본 클래스에서 상속 된 멤버와 함께 `CommandLine` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[Ds](#command-line)

### <a name="functions"></a>함수

[값](#value)

## <a name="command-line"></a>Ds

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
[COMMAND_LINE](../event-table.md#command-line) 이벤트입니다.

## <a name="value"></a>기본값

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>반환 값

명령줄을 포함 하는 문자열입니다. 이 값에는 지시 파일에서 가져온 인수와 CL, \_CL\_, 링크 및 \_링크\_같은 환경 변수를 포함 합니다.

::: moniker-end
