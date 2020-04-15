---
title: 컴파일러패스 클래스
description: C++ 빌드 인사이트 SDK 컴파일러패스 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CompilerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 11af981b647d5183f88dad024d90c0ef4f8a28bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325037"
---
# <a name="compilerpass-class"></a>컴파일러패스 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `CompilerPass` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [BACK_END_PASS](../event-table.md#back-end-pass) 또는 [FRONT_END_PASS](../event-table.md#front-end-pass) 이벤트와 일치하는 데 사용합니다.

## <a name="syntax"></a>구문

```cpp
class CompilerPass : public Activity
{
public:
    enum class PassCode
    {
        FRONT_END,
        BACK_END
    };

    CompilerPass(const RawEvent& event);

    PassCode       PassCode() const;
    const wchar_t* InputSourcePath() const;
    const wchar_t* OutputObjectPath() const;
};
```

## <a name="members"></a>멤버

[활동](activity.md) 기본 클래스의 상속된 멤버와 `CompilerPass` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[컴파일러 패스](#compiler-pass)

### <a name="enums"></a>열거형

#### <a name="passcode"></a>암호

|||
|-|-|
|FRONT_END|프론트 엔드 패스.|
|BACK_END|백 엔드 패스.|

### <a name="functions"></a>Functions

[입력 소스 패스](#input-source-path)\
[출력 개체 경로](#output-object-path)\
[암호](#pass-code)\

## <a name="compilerpass"></a><a name="compiler-pass"></a>컴파일러 패스

```cpp
CompilerPass(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[BACK_END_PASS](../event-table.md#back-end-pass) 또는 [FRONT_END_PASS](../event-table.md#front-end-pass) 이벤트입니다.

## <a name="inputsourcepath"></a><a name="input-source-path"></a>입력 소스 패스

```cpp
const wchar_t* InputSourcePath() const;
```

### <a name="return-value"></a>Return Value

이 컴파일러에서 처리하는 입력 소스 파일에 대한 절대 경로입니다.

## <a name="outputobjectpath"></a><a name="output-object-path"></a>출력 개체 경로

```cpp
const wchar_t* OutputObjectPath() const;
```

### <a name="return-value"></a>Return Value

이 컴파일러 패스에서 생성된 출력 개체 파일에 대한 절대 경로입니다.

## <a name="passcode"></a><a name="pass-code"></a>암호

```cpp
PassCode PassCode() const;
```

### <a name="return-value"></a>Return Value

이 컴파일러패스 개체로 표시되는 컴파일러 패스를 나타내는 코드입니다.

::: moniker-end
