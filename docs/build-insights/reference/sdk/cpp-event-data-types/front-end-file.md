---
title: 프런트 엔드 파일 클래스
description: C++ 빌드 인사이트 SDK 프런트엔드파일 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFile
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c40137724279ea2fd615729db39f0ac5c907b79e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324755"
---
# <a name="frontendfile-class"></a>프런트 엔드 파일 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `FrontEndFile` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [FRONT_END_FILE](../event-table.md#front-end-file) 이벤트를 일치시키기 위해 사용합니다.

## <a name="syntax"></a>구문

```cpp
class FrontEndFile : public Activity
{
public:
    FrontEndFile(const RawEvent& event);

    const char* Path() const;
};
```

## <a name="members"></a>멤버

[활동](activity.md) 기본 클래스의 상속된 멤버와 `FrontEndFile` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[프론트 엔드 파일](#front-end-file)

### <a name="functions"></a>Functions

[경로](#path)

## <a name="frontendfile"></a><a name="front-end-file"></a>프론트 엔드 파일

```cpp
FrontEndFile(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[FRONT_END_FILE](../event-table.md#front-end-file) 이벤트입니다.

## <a name="path"></a><a name="path"></a>경로

```cpp
const char* Path() const;
```

### <a name="return-value"></a>Return Value

UTF-8로 인코딩된 파일에 대한 절대 경로입니다.

::: moniker-end
