---
title: 함수 클래스
description: C++ 빌드 인사이트 SDK 함수 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Function
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 69acbe4d6630de37120aec89a24a9f33d447009e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324718"
---
# <a name="function-class"></a>함수 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `Function` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [함수](../event-table.md#function) 이벤트와 일치하는 데 사용합니다.

## <a name="syntax"></a>구문

```cpp
class Function : public Activity
{
public:
    Function(const RawEvent& event);

    const char* Name() const;
};
```

## <a name="members"></a>멤버

[활동](activity.md) 기본 클래스의 상속된 멤버와 `Function` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[기능](#function)

### <a name="functions"></a>Functions

[이름](#name)

## <a name="function"></a><a name="function"></a>함수

```cpp
Function(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[함수](../event-table.md#function) 이벤트입니다.

## <a name="name"></a><a name="name"></a>이름

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Return Value

UTF-8로 인코딩된 함수의 이름입니다.

::: moniker-end
