---
title: ANALYSIS_DESCRIPTOR 구조체
description: C++ BUILD Insights SDK ANALYSIS_DESCRIPTOR 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fc11ce11e1faaae02edb36aac447c18ea8107e35
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334105"
---
# <a name="analysis_descriptor-structure"></a>ANALYSIS_DESCRIPTOR 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`ANALYSIS_DESCRIPTOR` 구조는 [AnalyzeA](../functions/analyze-a.md) 및 [AnalyzeW](../functions/analyze-w.md) 함수와 함께 사용 됩니다. ETW(Windows용 이벤트 추적) (ETW) 추적을 분석 하는 방법을 설명 합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct ANALYSIS_DESCRIPTOR_TAG
{
    unsigned                NumberOfPasses;
    ANALYSIS_CALLBACKS      Callbacks;
    void*                   Context;
} ANALYSIS_DESCRIPTOR;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `NumberOfPasses` | ETW 추적을 통해 수행 해야 하는 분석 패스의 수입니다. |
| `Callbacks` | 분석 세션 중에 호출할 함수를 지정 하는 [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 개체입니다. |
| `Context` | 에 지정 된 모든 콜백 함수에 인수로 전달 되는 사용자 제공 컨텍스트입니다 `Callbacks` |

## <a name="remarks"></a>주의

`Callbacks` 구조체는 비멤버 함수에 대 한 포인터만 허용 합니다. `Context`를 개체 포인터로 설정 하면 이러한 제한을 해결할 수 있습니다. 이 개체 포인터는 모든 멤버가 아닌 콜백 함수에 인수로 전달 됩니다. 멤버가 아닌 콜백 함수 내에서 멤버 함수를 호출 하려면이 포인터를 사용 합니다.

::: moniker-end
