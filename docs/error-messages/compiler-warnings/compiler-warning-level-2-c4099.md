---
title: 컴파일러 경고 (수준 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: 97ead14dc9771dc02ad722843ec9fe1a8056e3f6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174286"
---
# <a name="compiler-warning-level-2-c4099"></a>컴파일러 경고 (수준 2) C4099

' identifier ': ' objecttype1 '를 사용 하 여 먼저 ' objecttype2 '를 사용 하 여 표시 한 형식 이름입니다.

구조체로 선언 된 개체가 클래스로 정의 되거나 클래스로 선언 된 개체가 구조체로 정의 됩니다. 컴파일러는 정의에 지정 된 형식을 사용 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4099를 생성 합니다.

```cpp
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```
