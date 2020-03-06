---
title: C1DLL 클래스
description: C++ BUILD INSIGHTS SDK C1DLL 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- C1DLL
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f843e7dcd14dc9e9649317933008b575ff4eddf0
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335005"
---
# <a name="c1dll-class"></a>C1DLL 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`C1DLL` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 이를 사용 하 여 [C1_DLL](../event-table.md#c1-dll) 이벤트를 일치 시킵니다.

## <a name="syntax"></a>구문

```cpp
class C1DLL : public Activity
{
public:
    C1DLL(const RawEvent& event);
};
```

## <a name="members"></a>멤버

[작업](activity.md) 기본 클래스의 상속 된 멤버와 함께 `C1DLL` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[C1DLL](#c1-dll)

## <a name="c1-dll"></a>C1DLL

```cpp
C1DLL(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
[C1_DLL](../event-table.md#c1-dll) 이벤트입니다.

::: moniker-end
