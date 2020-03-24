---
title: 컴파일러 경고(수준 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: 9b38e9670157fd15dc7c4b6a96ced7ad40c43e34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185999"
---
# <a name="compiler-warning-level-1-c4606"></a>컴파일러 경고(수준 1) C4606

\#pragma warning: ' warning_number '이 (가) 무시 되었습니다. 코드 분석 경고가 경고 수준과 연결 되어 있지 않습니다.

코드 분석 경고의 경우 `error`, `once`및 `default`는 [warning](../../preprocessor/warning.md) pragma로만 지원 됩니다.

## <a name="example"></a>예제

다음 샘플에서는 C4606를 생성 합니다.

```cpp
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```
