---
title: ObjOutput 클래스
description: C++ 빌드 인사이트 SDK ObjOutput 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ObjOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 194253e8995401114e2529b868b36c9823510a4f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324502"
---
# <a name="objoutput-class"></a>ObjOutput 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `ObjOutput` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [OBJ_OUTPUT](../event-table.md#obj-output) 이벤트를 일치시키기 위해 사용합니다.

## <a name="syntax"></a>구문

```cpp
class ObjOutput : public FileOutput
{
public:
    ObjOutput(const RawEvent& event);
};
```

## <a name="members"></a>멤버

[FileOutput](file-output.md) 기본 클래스의 상속된 멤버와 `ObjOutput` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[Obj출력](#obj-output)

## <a name="objoutput"></a><a name="obj-output"></a>Obj출력

```cpp
ObjOutput(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[OBJ_OUTPUT](../event-table.md#obj-output) 이벤트입니다.

::: moniker-end
