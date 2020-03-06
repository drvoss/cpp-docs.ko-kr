---
title: TEMPLATE_INSTANTIATION_DATA 구조체
description: C++ BUILD Insights SDK TEMPLATE_INSTANTIATION_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9aa669d715dbe56ce7e889330f46f307f520710f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335083"
---
# <a name="template_instantiation_data-structure"></a>TEMPLATE_INSTANTIATION_DATA 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`TEMPLATE_INSTANTIATION_DATA` 구조는 템플릿 인스턴스화를 설명 합니다.

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
| `SpecializationSymbolKey` | 템플릿 특수화 형식의 키입니다. 이 값은 분석 중인 추적 내에서 고유 합니다. |
| `PrimaryTemplateSymbolKey` | 특수화 된 기본 템플릿 형식에 대 한 키입니다. 이 값은 분석 중인 추적 내에서 고유 합니다. |
| `KindCode` | 템플릿 인스턴스화의 형식입니다. 자세한 내용은 [TEMPLATE_INSTANTIATION_KIND_CODE](template-instantiation-kind-code-enum.md)를 참조 하세요. |

## <a name="remarks"></a>주의

`TEMPLATE_INSTANTIATION_DATA` 구조의 키는 분석 중인 추적 내에서 고유 합니다. 그러나 서로 다른 컴파일러 프런트 엔드 패스에서 제공 되는 두 개의 서로 다른 두 키는 동일한 형식을 가리킬 수 있습니다. 여러 컴파일러 프런트 엔드의 `TEMPLATE_INSTANTIATION_DATA` 정보를 사용 하는 경우 [SYMBOL_NAME](../event-table.md#symbol-name) 이벤트를 사용 하 여 두 형식이 동일한 지 확인 합니다. 모든 템플릿 인스턴스화가 발생 한 후에는 컴파일러 프런트 엔드 패스의 끝에 `SymbolName` 이벤트를 내보냅니다.

::: moniker-end
