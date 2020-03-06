---
title: LinkerPass 클래스
description: C++ BUILD Insights SDK LinkerPass 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 49a46b57d82391f4c253128c14b1b81d52945eae
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334723"
---
# <a name="linkerpass-class"></a>LinkerPass 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`LinkerPass` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. [Pass1.log](../event-table.md#pass1) 또는 [PASS2](../event-table.md#pass2) 이벤트를 일치 시키는 데 사용 합니다.

## <a name="syntax"></a>구문

```cpp
class LinkerPass : public Activity
{
public:
    LinkerPass(const RawEvent& event);
};
```

## <a name="members"></a>멤버

[작업](activity.md) 기본 클래스의 상속 된 멤버와 함께 `LinkerPass` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[LinkerPass](#linker-pass)

## <a name="linker-pass"></a>LinkerPass

```cpp
LinkerPass(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
[Pass1.log](../event-table.md#pass1) 또는 [PASS2](../event-table.md#pass2) 이벤트입니다.

::: moniker-end
