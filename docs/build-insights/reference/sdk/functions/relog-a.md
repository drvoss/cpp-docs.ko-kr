---
title: RelogA
description: Build C++ Insights SDK는 함수 참조를 다시 log합니다.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c4427aa0ac85e34bfb9d569913a8ccf6ab264f52
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334321"
---
# <a name="reloga"></a>RelogA

::: moniker range="<=vs-2015"

C++ BUILD Insights SDK는 Visual Studio 2017 이상 버전과 호환 됩니다. 이러한 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2017 또는 Visual studio 2019로 설정 합니다.

::: moniker-end
::: moniker range=">=vs-2017"

`RelogA` 함수는 ETW (ETW(Windows용 이벤트 추적)) 추적에서 MSVC 이벤트를 읽고 수정 된 새 ETW 추적에 기록 하는 데 사용 됩니다.

## <a name="syntax"></a>구문

```cpp
enum RESULT_CODE RelogA(
    const char*             inputLogFile,
    const char*             outputLogFile,
    const RELOG_DESCRIPTOR* relogDescriptor);
```

### <a name="parameters"></a>매개 변수

*Inputlogfile*\
이벤트를 읽으려고 하는 입력 ETW 추적입니다.

*Outputlogfile*\
새 이벤트를 쓸 파일입니다.

*Relogdescriptor*\
[RELOG_DESCRIPTOR](../other-types/relog-descriptor-struct.md) 개체에 대 한 포인터입니다. 이 개체를 사용 하 여 relogging 세션을 구성할 수 있습니다.

### <a name="return-value"></a>반환 값

[RESULT_CODE](../other-types/result-code-enum.md) 열거형의 결과 코드입니다.

::: moniker-end
