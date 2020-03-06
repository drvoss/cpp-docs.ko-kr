---
title: 기호 이름 클래스
description: C++ BUILD Insights SDK 기호 이름 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SymbolName
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b5e9a9b22db99c099b9f7dc1813fb335358a83e8
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334549"
---
# <a name="symbolname-class"></a>기호 이름 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`SymbolName` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 이를 사용 하 여 [SYMBOL_NAME](../event-table.md#symbol-name) 이벤트를 일치 시킵니다.

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

[SimpleEvent](simple-event.md) 기본 클래스에서 상속 된 멤버와 함께 `SymbolName` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[기호 이름](#symbol-name)

### <a name="functions"></a>함수

[키](#key)
[이름](#name)

## <a name="key"></a>키인지

```cpp
const unsigned long long& Key() const;
```

### <a name="return-value"></a>반환 값

이 기호가 나타내는 형식의 숫자 식별자입니다. 이 식별자는 컴파일러 프런트 엔드 패스 내에서 고유 합니다.

## <a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>반환 값

기호가 나타내는 형식의 이름으로, u t f-8로 인코딩됩니다.

## <a name="symbol-name"></a>기호 이름

```cpp
SymbolName(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
[SYMBOL_NAME](../event-table.md#symbol-name) 이벤트입니다.

::: moniker-end
