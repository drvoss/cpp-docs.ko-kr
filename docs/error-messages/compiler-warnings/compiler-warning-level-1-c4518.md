---
title: 컴파일러 경고(수준 1) C4518
ms.date: 11/04/2016
f1_keywords:
- C4518
helpviewer_keywords:
- C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
ms.openlocfilehash: 76761d9e0a260a05acef01bc451ad411aac517c7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186519"
---
# <a name="compiler-warning-level-1-c4518"></a>컴파일러 경고(수준 1) C4518

' 지정자 ': 예기치 않은 저장소 클래스 또는 형식 지정자입니다. 무시

다음 샘플에서는 C4518를 생성 합니다.

```cpp
// C4518.cpp
// compile with: /c /W1
_declspec(dllexport) extern "C" void MyFunction();   // C4518

extern "C" void MyFunction();   // OK
```
