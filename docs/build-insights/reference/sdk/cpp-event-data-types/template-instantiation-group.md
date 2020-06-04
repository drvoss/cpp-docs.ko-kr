---
title: 템플릿 인스턴스화 그룹 클래스
description: C++ 빌드 인사이트 SDK 템플릿 인스턴스화 그룹 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 18dd48219c7c68ce152c381eb505fe37b19ec8dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324268"
---
# <a name="templateinstantiationgroup-class"></a>템플릿 인스턴스화 그룹 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `TemplateInstantiationGroup` [매치이벤트스택](../functions/match-event-stack.md) 및 [매치이벤트스택InMemberFunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용된다. [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) 이벤트 그룹을 일치시키기 위해 사용합니다.

## <a name="syntax"></a>구문

```cpp
class TemplateInstantiationGroup : public EventGroup<TemplateInstantiation>
{
public:
    TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
};
```

## <a name="members"></a>멤버

[해당 EventGroup\<Template인스턴스화\> ](event-group.md) 기본 클래스에서 상속된 멤버와 함께 `TemplateInstantiationGroup` 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[템플릿 인스턴스화 그룹](#template-instantiation-group)

## <a name="templateinstantiationgroup"></a><a name="template-instantiation-group"></a>템플릿 인스턴스화 그룹

```cpp
TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
```

### <a name="parameters"></a>매개 변수

*그룹*\
[TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) 이벤트 그룹입니다.

::: moniker-end
