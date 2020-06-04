---
title: TEMPLATE_INSTANTIATION_DATA 구조
description: C++ 빌드 인사이트 SDK TEMPLATE_INSTANTIATION_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a38d19368e7c0a9912907f1da6e7a2e31ffe8d90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325322"
---
# <a name="template_instantiation_data-structure"></a>TEMPLATE_INSTANTIATION_DATA 구조

::: moniker range="<=vs-2015"

C++ 빌드 인사이트 SDK는 Visual Studio 2017 이상과 호환됩니다. 이러한 버전에 대한 설명서를 보려면 이 문서의 Visual Studio **버전** 선택기 컨트롤을 Visual Studio 2017 또는 Visual Studio 2019로 설정합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end
::: moniker range=">=vs-2017"

구조는 `TEMPLATE_INSTANTIATION_DATA` 템플릿 인스턴스화를 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct TEMPLATE_INSTANTIATION_DATA_TAG
{
    unsigned long long  SpecializationSymbolKey;
    unsigned long long  PrimaryTemplateSymbolKey;
    int                 KindCode;

} TEMPLATE_INSTANTIATION_DATA;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `SpecializationSymbolKey` | 템플릿 특수화 유형의 키입니다. 이 값은 분석중인 추적 내에서 고유합니다. |
| `PrimaryTemplateSymbolKey` | 특수화된 기본 템플릿 형식의 키입니다. 이 값은 분석중인 추적 내에서 고유합니다. |
| `KindCode` | 템플릿 인스턴스화 유형입니다. 자세한 내용은 [TEMPLATE_INSTANTIATION_KIND_CODE](template-instantiation-kind-code-enum.md)를 참조하십시오. |

## <a name="remarks"></a>설명

구조의 `TEMPLATE_INSTANTIATION_DATA` 키는 분석되는 추적 내에서 고유합니다. 그러나 서로 다른 컴파일러 프런트 엔드 패스에서 오는 두 개의 서로 다른 키는 두 개의 동일한 형식을 가리킬 수 있습니다. 여러 `TEMPLATE_INSTANTIATION_DATA` 컴파일러 프런트 엔드 패스의 정보를 사용할 때 [SYMBOL_NAME](../event-table.md#symbol-name) 이벤트를 사용하여 두 형식이 동일한지 확인합니다. `SymbolName`이벤트는 모든 템플릿 인스턴스화가 발생한 후 컴파일러 프런트 엔드 패스의 끝에서 내보내게 됩니다.

::: moniker-end
