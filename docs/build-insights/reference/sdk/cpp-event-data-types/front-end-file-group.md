---
title: 프론트 엔드 파일 그룹 클래스
description: C++ 빌드 인사이트 SDK 프런트엔드파일그룹 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFileGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d2eebb650e59e750e5ebde74914dca5f0ef4779d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324768"
---
# <a name="frontendfilegroup-class"></a>프론트 엔드 파일 그룹 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `FrontEndFileGroup` [매치이벤트스택](../functions/match-event-stack.md) 및 [매치이벤트스택InMemberFunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용된다. [FRONT_END_FILE](../event-table.md#front-end-file) 이벤트 그룹을 일치시키기 위해 사용합니다.

## <a name="syntax"></a>구문

```cpp
class FrontEndFileGroup : public EventGroup<FrontEndFile>
{
public:
    FrontEndFileGroup(std::deque<FrontEndFile>&& group);
};
```

## <a name="members"></a>멤버

[EventGroup\<\> FrontEndFile](event-group.md) 기본 클래스에서 상속된 멤버와 함께 `FrontEndFileGroup` 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[프론트 엔드 파일 그룹](#front-end-file-group)

## <a name="frontendfilegroup"></a><a name="front-end-file-group"></a>프론트 엔드 파일 그룹

```cpp
FrontEndFileGroup(std::deque<FrontEndFile>&& group);
```

### <a name="parameters"></a>매개 변수

*그룹*\
[FRONT_END_FILE](../event-table.md#front-end-file) 이벤트 그룹입니다.

::: moniker-end
