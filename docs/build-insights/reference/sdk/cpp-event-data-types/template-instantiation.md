---
title: 템플릿 인스턴스화 클래스
description: C++ 빌드 인사이트 SDK 템플릿 인스턴스화 클래스 참조.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ba8fd10efc6a536c9160f10b19e19e17bfaaad98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324227"
---
# <a name="templateinstantiation-class"></a>템플릿 인스턴스화 클래스

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

클래스는 `TemplateInstantiation` [매치 이벤트,](../functions/match-event.md) [매치 이벤트인멤버기능,](../functions/match-event-in-member-function.md) [매치이벤트스택](../functions/match-event-stack.md)및 [매치이벤트스택](../functions/match-event-stack-in-member-function.md) 기능과 함께 사용된다. [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) 이벤트와 일치하는 데 사용합니다.

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

[활동](activity.md) 기본 클래스의 상속된 멤버와 `TemplateInstantiation` 함께 클래스에는 다음 멤버가 포함됩니다.

### <a name="constructors"></a>생성자

[템플릿 인스턴스화](#template-instantiation)

### <a name="functions"></a>Functions

[종류](#kind)
[기본 템플릿 기호키](#primary-template-symbol-key)
[전문화 기호키키](#specialization-symbol-key)

## <a name="kind"></a><a name="kind"></a>종류

```cpp
Kind Kind() const;
```

### <a name="return-value"></a>Return Value

수행된 템플릿 인스턴스화 유형을 설명하는 코드입니다.

## <a name="primarytemplatesymbolkey"></a><a name="primary-template-symbol-key"></a>기본 템플릿 기호키

```cpp
const unsigned long long& PrimaryTemplateSymbolKey() const;
```

### <a name="return-value"></a>Return Value

특수화된 템플릿 형식에 대한 숫자 식별자입니다. 이 식별자는 컴파일러 프런트 엔드 패스 내에서 고유합니다.

## <a name="specializationsymbolkey"></a><a name="specialization-symbol-key"></a>전문화 기호키

```cpp
const unsigned long long& SpecializationSymbolKey() const;
```

### <a name="return-value"></a>Return Value

특수화 유형의 숫자 식별자입니다. 이 식별자는 컴파일러 프런트 엔드 패스 내에서 고유합니다.

## <a name="templateinstantiation"></a><a name="template-instantiation"></a>템플릿 인스턴스화

```cpp
TemplateInstantiation(const RawEvent& event);
```

### <a name="parameters"></a>매개 변수

*이벤트*\
[TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) 이벤트.

::: moniker-end
