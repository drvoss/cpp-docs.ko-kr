---
title: 템플릿 인스턴스화 클래스
description: C++ BUILD Insights SDK 템플릿 인스턴스화 클래스 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2c94f8d3a4613e072c03f6dd4c846798d3d2122b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334525"
---
# <a name="templateinstantiation-class"></a>템플릿 인스턴스화 클래스

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`TemplateInstantiation` 클래스는 [Matchevent](../functions/match-event.md), [matcheventinmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)및 [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) 함수와 함께 사용 됩니다. 이를 사용 하 여 [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) 이벤트를 일치 시킵니다.

## <a name="syntax"></a>구문

```cpp
class TemplateInstantiation : public Activity
{
public:
    enum class Kind
    {
        CLASS       = TEMPLATE_INSTANTIATION_KIND_CODE_CLASS,
        FUNCTION    = TEMPLATE_INSTANTIATION_KIND_CODE_FUNCTION,
        VARIABLE    = TEMPLATE_INSTANTIATION_KIND_CODE_VARIABLE,
        CONCEPT     = TEMPLATE_INSTANTIATION_KIND_CODE_CONCEPT
    };

    TemplateInstantiation(const RawEvent& event);

    const unsigned long long& SpecializationSymbolKey() const;
    const unsigned long long& PrimaryTemplateSymbolKey() const;

    Kind Kind() const;
};
```

## <a name="members"></a>멤버

[작업](activity.md) 기본 클래스의 상속 된 멤버와 함께 `TemplateInstantiation` 클래스에는 다음 멤버가 포함 됩니다.

### <a name="constructors"></a>생성자

[템플릿 인스턴스화](#template-instantiation)

### <a name="functions"></a>함수

[Kind](#kind)
[Primary템플릿 Ymbolkey](#primary-template-symbol-key)
[SpecializationSymbolKey](#specialization-symbol-key)

## <a name="kind"></a>종류로

```cpp
Kind Kind() const;
```

### <a name="return-value"></a>반환 값

수행 된 템플릿 인스턴스화의 형식을 설명 하는 코드입니다.

## <a name="primary-template-symbol-key"></a>Primary템플릿 Ymbolkey

```cpp
const unsigned long long& PrimaryTemplateSymbolKey() const;
```

### <a name="return-value"></a>반환 값

특수화 된 템플릿 형식에 대 한 숫자 식별자입니다. 이 식별자는 컴파일러 프런트 엔드 패스 내에서 고유 합니다.

## <a name="specialization-symbol-key"></a>SpecializationSymbolKey

```cpp
const unsigned long long& SpecializationSymbolKey() const;
```

### <a name="return-value"></a>반환 값

특수화 형식에 대 한 숫자 식별자입니다. 이 식별자는 컴파일러 프런트 엔드 패스 내에서 고유 합니다.

## <a name="template-instantiation"></a>템플릿 인스턴스화

```cpp
TemplateInstantiation(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*event*\
[TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) 이벤트입니다.

::: moniker-end
