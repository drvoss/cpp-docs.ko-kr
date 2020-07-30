---
title: 컴파일러 오류 C3386
ms.date: 11/04/2016
f1_keywords:
- C3386
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
ms.openlocfilehash: 0cb6235f1b6bc868655cc6a6ba301be1308402cd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221083"
---
# <a name="compiler-error-c3386"></a>컴파일러 오류 C3386

' type ': __declspec (dllexport)/ \_ _declspec (dllimport)을 (를) 관리 되는 또는 WinRTtype에 적용할 수 없습니다.

`dllimport`및 [dllexport](../../cpp/dllexport-dllimport.md) **`__declspec`** c ' * * 한정자는 관리 되는 형식 또는 Windows 런타임 형식에 사용할 수 없습니다.

다음 샘플에서는 C3386 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C3386.cpp
// compile with: /clr /c
ref class __declspec(dllimport) X1 {   // C3386
// try the following line instead
// ref class X1 {
};
```
