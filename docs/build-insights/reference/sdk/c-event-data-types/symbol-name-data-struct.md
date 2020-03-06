---
title: SYMBOL_NAME_DATA 구조체
description: C++ BUILD Insights SDK SYMBOL_NAME_DATA 구조 참조입니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SYMBOL_NAME_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 618e84f198c20aa089dc7e06e1e6c09b96b6d273
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335095"
---
# <a name="symbol_name_data-structure"></a>SYMBOL_NAME_DATA 구조체

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`SYMBOL_NAME_DATA` 구조체는 컴파일러 프런트 엔드 기호를 설명 합니다.

## <a name="syntax"></a>구문

```cpp
typedef struct SYMBOL_NAME_DATA_TAG
{
    unsigned long long  Key;
    const char*         Name;

} SYMBOL_NAME_DATA;
```

## <a name="members"></a>멤버

|  |  |
|--|--|
| `Key` | 기호의 키입니다. 이 값은 분석 중인 추적 내에서 고유 합니다. |
| `Name` | 기호 이름입니다. |

## <a name="remarks"></a>주의

서로 다른 두 컴파일러 프런트 엔드 패스에서 오는 기호는 동일한 이름을 갖지만 다른 키를 가질 수 있습니다. 이 경우 기호 이름을 사용 하 여 두 형식이 동일한 지 확인 합니다.

::: moniker-end
