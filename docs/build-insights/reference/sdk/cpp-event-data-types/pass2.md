---
title: 패스2 클래스
description: C++ 빌드 인사이트 SDK Pass2 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass2
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 89b775c60b1d136c33dbaf2c4e39f247be7bb0bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324410"
---
# <a name="pass2-class"></a>패스2 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `Pass2` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [PASS2](../event-table.md#pass2) 이벤트와 일치하는 데 사용합니다.

## <a name="syntax"></a>구문

```cpp
class Pass2 : public LinkerPass
{
public:
    Pass2(const RawEvent& event);
};
```

## <a name="members"></a>멤버

[LinkerPass](linker-pass.md) 기본 클래스의 상속된 멤버와 `Pass2` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[패스 2](#pass2)

## <a name="pass2"></a><a name="pass2"></a>패스 2

```cpp
Pass2(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[PASS2](../event-table.md#pass2) 이벤트.

::: moniker-end
