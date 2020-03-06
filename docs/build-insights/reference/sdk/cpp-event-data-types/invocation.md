---
title: 호출 클래스
description: C++ BUILD Insights SDK 호출 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Invocation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 0c4698300a3eeaf77210ad74f84b0c0cd219b457
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334747"
---
# <a name="invocation-class"></a>호출 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`Invocation` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 이를 사용 하 여 [컴파일러](../event-table.md#compiler) 또는 [링커](../event-table.md#linker) 이벤트를 일치 시킵니다.

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

[작업](activity.md) 기본 클래스의 상속 된 멤버와 함께 `Invocation` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[호출](#invocation)

### <a name="functions"></a>함수

[공구 경로](#tool-path)
[Toolversion](#tool-version)
[toolversionstring](#tool-version-string)
[형식](#type)
[WorkingDirectory](#working-directory)

## <a name="invocation"></a>호출

```cpp
Invocation(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
[컴파일러](../event-table.md#compiler) 또는 [링커](../event-table.md#linker) 이벤트입니다.

## <a name="tool-path"></a>머시닝

```cpp
const wchar_t* ToolPath() const;
```

### <a name="return-value"></a>반환 값

호출 된 도구의 절대 경로입니다.

## <a name="tool-version"></a>ToolVersion

```cpp
const INVOCATION_VERSION_DATA& ToolVersion() const;
```

### <a name="return-value"></a>반환 값

호출 된 도구의 버전 [INVOCATION_VERSION_DATA](../c-event-data-types/invocation-version-data-struct.md) 참조입니다.

## <a name="tool-version-string"></a>ToolVersionString

```cpp
const char* ToolVersionString() const;
```

### <a name="return-value"></a>반환 값

호출 된 도구의 버전 (ANSI 문자열)입니다.

## <a name="type"></a>입력할

```cpp
Type Type() const;
```

### <a name="return-value"></a>반환 값

호출 된 도구를 나타내는 코드입니다.

## <a name="working-directory"></a>WorkingDirectory

```cpp
const wchar_t* WorkingDirectory() const;
```

### <a name="return-value"></a>반환 값

도구가 호출 된 디렉터리의 절대 경로입니다.

::: moniker-end
