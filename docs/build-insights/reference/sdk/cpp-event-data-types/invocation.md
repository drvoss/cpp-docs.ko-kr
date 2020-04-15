---
title: 호출 클래스
description: C++ 빌드 인사이트 SDK 호출 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Invocation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fcb087d46ea445251b0108f811545a44c26f421e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324633"
---
# <a name="invocation-class"></a>호출 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `Invocation` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [컴파일러](../event-table.md#compiler) 또는 [LINKER](../event-table.md#linker) 이벤트와 일치하는 데 사용합니다.

## <a name="syntax"></a>구문

```cpp
class Invocation : public Activity
{
    const INVOCATION_DATA* data_;

public:
    enum class Type
    {
        CL      = MSVC_TOOL_CODE_CL,
        LINK    = MSVC_TOOL_CODE_LINK
    };

    Invocation(const RawEvent& event);

    Type             Type() const;
    const char*      ToolVersionString() const;
    const wchar_t*   WorkingDirectory() const;
    const wchar_t*   ToolPath() const;

    const INVOCATION_VERSION_DATA& ToolVersion() const;
};
```

## <a name="members"></a>멤버

[활동](activity.md) 기본 클래스의 상속된 멤버와 `Invocation` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[호출](#invocation)

### <a name="functions"></a>Functions

[도구 경로](#tool-path)
[도구버전](#tool-version)
[도구버전스트링](#tool-version-string)
[유형](#type)
[작업디렉토리](#working-directory)

## <a name="invocation"></a><a name="invocation"></a>호출

```cpp
Invocation(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[컴파일러](../event-table.md#compiler) 또는 [링커](../event-table.md#linker) 이벤트입니다.

## <a name="toolpath"></a><a name="tool-path"></a>공구 경로

```cpp
const wchar_t* ToolPath() const;
```

### <a name="return-value"></a>Return Value

호출된 도구에 대한 절대 경로입니다.

## <a name="toolversion"></a><a name="tool-version"></a>공구 버전

```cpp
const INVOCATION_VERSION_DATA& ToolVersion() const;
```

### <a name="return-value"></a>Return Value

[INVOCATION_VERSION_DATA](../c-event-data-types/invocation-version-data-struct.md) 참조로 호출된 도구의 버전입니다.

## <a name="toolversionstring"></a><a name="tool-version-string"></a>도구버전스트링

```cpp
const char* ToolVersionString() const;
```

### <a name="return-value"></a>Return Value

ANSI 문자열로 호출된 도구의 버전입니다.

## <a name="type"></a><a name="type"></a> 형식

```cpp
Type Type() const;
```

### <a name="return-value"></a>Return Value

호출된 도구를 나타내는 코드입니다.

## <a name="workingdirectory"></a><a name="working-directory"></a>작업 디렉토리

```cpp
const wchar_t* WorkingDirectory() const;
```

### <a name="return-value"></a>Return Value

도구가 호출된 디렉터리로의 절대 경로입니다.

::: moniker-end
