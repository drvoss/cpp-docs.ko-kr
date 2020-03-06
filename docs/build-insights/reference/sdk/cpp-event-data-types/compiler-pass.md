---
title: CompilerPass 클래스
description: C++ BUILD Insights SDK CompilerPass 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CompilerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3c2fa1c2c4be8aaf5bec77b383f93a4b033ca8e3
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334957"
---
# <a name="compilerpass-class"></a>CompilerPass 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`CompilerPass` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 이를 사용 하 여 [BACK_END_PASS](../event-table.md#back-end-pass) 또는 [FRONT_END_PASS](../event-table.md#front-end-pass) 이벤트를 일치 시킵니다.

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

[작업](activity.md) 기본 클래스의 상속 된 멤버와 함께 `CompilerPass` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[CompilerPass](#compiler-pass)

### <a name="enums"></a>열거형

#### <a name="passcode"></a>적음

|||
|-|-|
|FRONT_END|프런트 엔드 패스입니다.|
|BACK_END|백 엔드 패스입니다.|

### <a name="functions"></a>함수

[Inputsourcepath](#input-source-path)\
[OutputObjectPath](#output-object-path)\
[암호](#pass-code)\

## <a name="compiler-pass"></a>CompilerPass

```cpp
CompilerPass(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
[BACK_END_PASS](../event-table.md#back-end-pass) 또는 [FRONT_END_PASS](../event-table.md#front-end-pass) 이벤트입니다.

## <a name="input-source-path"></a>InputSourcePath

```cpp
const wchar_t* InputSourcePath() const;
```

### <a name="return-value"></a>반환 값

이 컴파일러 통과에서 처리 한 입력 소스 파일의 절대 경로입니다.

## <a name="output-object-path"></a>OutputObjectPath

```cpp
const wchar_t* OutputObjectPath() const;
```

### <a name="return-value"></a>반환 값

이 컴파일러에서 생성 된 출력 개체 파일의 절대 경로입니다.

## <a name="pass-code"></a>적음

```cpp
PassCode PassCode() const;
```

### <a name="return-value"></a>반환 값

이 CompilerPass 개체가 나타내는 컴파일러 pass를 나타내는 코드입니다.

::: moniker-end
