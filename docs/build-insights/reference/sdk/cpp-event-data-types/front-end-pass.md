---
title: 프론트엔드패스 클래스
description: C++ 빌드 인사이트 SDK 프론엔드패스 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 137f553f1e495b7658ae89e69a48cec6b1988a81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324735"
---
# <a name="frontendpass-class"></a>프론트엔드패스 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `FrontEndPass` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [FRONT_END_PASS](../event-table.md#front-end-pass) 이벤트와 일치하는 데 사용합니다.

## <a name="syntax"></a>구문

```cpp
class FrontEndPass : public CompilerPass
{
public:
    FrontEndPass(const RawEvent& event);
};
```

## <a name="members"></a>멤버

[CompilerPass](compiler-pass.md) 기본 클래스에서 상속된 멤버와 `FrontEndPass` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[프론트엔드패스](#front-end-pass)

## <a name="frontendpass"></a><a name="front-end-pass"></a>프론트엔드패스

```cpp
FrontEndPass(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[FRONT_END_PASS](../event-table.md#front-end-pass) 이벤트입니다.

::: moniker-end
