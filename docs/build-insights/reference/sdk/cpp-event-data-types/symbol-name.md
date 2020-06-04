---
title: 기호 이름 클래스
description: C++ 빌드 인사이트 SDK 기호 Name 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SymbolName
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1306fb43d6c2140a75b36c5f142532916cf26ae4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324349"
---
# <a name="symbolname-class"></a>기호 이름 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `SymbolName` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [SYMBOL_NAME](../event-table.md#symbol-name) 이벤트를 일치시키기 위해 사용합니다.

## <a name="syntax"></a>구문

```cpp
class SymbolName : public SimpleEvent
{
public:
    SymbolName(const RawEvent& event);

    const unsigned long long&  Key() const;
    const char*                Name() const;
};
```

## <a name="members"></a>멤버

[SimpleEvent](simple-event.md) 기본 클래스에서 상속된 멤버와 `SymbolName` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[기호 이름](#symbol-name)

### <a name="functions"></a>Functions

[키](#key)
[이름](#name)

## <a name="key"></a><a name="key"></a>키

```cpp
const unsigned long long& Key() const;
```

### <a name="return-value"></a>Return Value

이 기호로 표시되는 형식에 대한 숫자 식별자입니다. 이 식별자는 컴파일러 프런트 엔드 패스 내에서 고유합니다.

## <a name="name"></a><a name="name"></a>이름

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Return Value

UTF-8로 인코딩된 기호로 표시되는 형식의 이름입니다.

## <a name="symbolname"></a><a name="symbol-name"></a>기호 이름

```cpp
SymbolName(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[SYMBOL_NAME](../event-table.md#symbol-name) 이벤트입니다.

::: moniker-end
