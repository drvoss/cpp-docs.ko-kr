---
title: FrontEndFileGroup 클래스
description: C++ BUILD Insights SDK FrontEndFileGroup 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFileGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 343a5a0d798d6c719088bd49668e70b10fba6d1a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334831"
---
# <a name="frontendfilegroup-class"></a>FrontEndFileGroup 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`FrontEndFileGroup` 클래스는 [Matcheventstack](../functions/match-event-stack.md) 및 [Matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. [FRONT_END_FILE](../event-table.md#front-end-file) 이벤트 그룹을 일치 시키는 데 사용 합니다.

## <a name="syntax"></a>구문

```cpp
class FrontEndFileGroup : public EventGroup<FrontEndFile>
{
public:
    FrontEndFileGroup(std::deque<FrontEndFile>&& group);
};
```

## <a name="members"></a>멤버

[Eventgroup\<FrontEndFile\>](event-group.md) 기본 클래스의 상속 된 멤버와 함께 `FrontEndFileGroup` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[FrontEndFileGroup](#front-end-file-group)

## <a name="front-end-file-group"></a>FrontEndFileGroup

```cpp
FrontEndFileGroup(std::deque<FrontEndFile>&& group);
```

### <a name="parameters"></a>매개 변수

*그룹*\
[FRONT_END_FILE](../event-table.md#front-end-file) 이벤트 그룹입니다.

::: moniker-end
