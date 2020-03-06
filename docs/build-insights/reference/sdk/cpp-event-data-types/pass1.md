---
title: Pass1.log 클래스
description: C++ BUILD Insights SDK pass1.log 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass1
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d81a933e21f6976624808be358230305459e4992
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334627"
---
# <a name="pass1-class"></a>Pass1.log 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`Pass1` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 이를 사용 하 여 [pass1.log](../event-table.md#pass1) 이벤트를 일치 시킵니다.

## <a name="syntax"></a>구문

```cpp
class Pass1 : public LinkerPass
{
public:
    Pass1(const RawEvent& event);
};
```

## <a name="members"></a>멤버

[Linkerpass](linker-pass.md) 기본 클래스의 상속 된 멤버와 함께 `Pass1` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[Pass1.log](#pass1)

## <a name="pass1"></a>Pass1.log

```cpp
Pass1(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
[Pass1.log](../event-table.md#pass1) 이벤트입니다.

::: moniker-end
