---
title: NMAKE 심각한 오류 U1070
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: 008d49df3460cb7cf760e4b278db20da444555fe
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182775"
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE 심각한 오류 U1070

' macroname ' 매크로 정의에서 순환 됩니다.

지정 된 매크로 정의에 지정 된 매크로가 포함 된 정의를 포함 하는 매크로가 포함 되어 있습니다. 순환 매크로 정의가 잘못 되었습니다.

## <a name="example"></a>예제

다음 매크로 정의

```
ONE=$(TWO)
TWO=$(ONE)
```

다음 오류가 발생 합니다.

```
cycle in macro definition 'TWO'
```
