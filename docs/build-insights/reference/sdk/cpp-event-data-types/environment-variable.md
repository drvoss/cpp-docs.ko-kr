---
title: 환경변수 클래스
description: C++ 빌드 인사이트 SDK 환경변수 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EnvironmentVariable
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 963c52e0ea9e048448c6f2b3ac62d9938817467e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325012"
---
# <a name="environmentvariable-class"></a>환경변수 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `EnvironmentVariable` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) 이벤트를 일치시키기 위해 사용합니다.

## <a name="syntax"></a>구문

```cpp
class EnvironmentVariable : public SimpleEvent
{
public:
    EnvironmentVariable(const RawEvent& event);

    const wchar_t* Name() const;
    const wchar_t* Value() const;
};
```

## <a name="members"></a>멤버

[SimpleEvent](simple-event.md) 기본 클래스에서 상속된 멤버와 `EnvironmentVariable` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[EnvironmentVariable](#environment-variable)

### <a name="functions"></a>Functions

[이름](#name)
[값](#value)

## <a name="environmentvariable"></a><a name="environment-variable"></a>환경 변수

```cpp
EnvironmentVariable(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) 이벤트입니다.

## <a name="name"></a><a name="name"></a>이름

```cpp
const wchar_t Name() const;
```

### <a name="return-value"></a>Return Value

환경 변수의 이름입니다.

## <a name="value"></a><a name="value"></a> 값

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>Return Value

환경 변수의 값입니다.

::: moniker-end
