---
title: 컴파일러 경고(수준 1) C4788
ms.date: 11/04/2016
f1_keywords:
- C4788
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
ms.openlocfilehash: 76a33b24446debffb2c00bf1b0497cfc86022ce0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175143"
---
# <a name="compiler-warning-level-1-c4788"></a>컴파일러 경고(수준 1) C4788

' identifier ': 식별자가 ' number ' 자로 잘렸습니다.

컴파일러는 함수 이름에 허용 되는 최대 길이를 제한 합니다. 컴파일러가 EH/SEH 코드에 대해 funclets를 생성할 때 함수 이름 앞에 "__catch", "\__unwind" 또는 다른 문자열 등의 텍스트를 사용 하 여 funclet 이름을 형성 합니다.

결과 funclet 이름이 너무 길면 컴파일러가이를 자르고 C4788을 생성 합니다.

이 경고를 해결 하려면 원래 함수 이름을 줄입니다. 함수가 C++ 템플릿 함수 또는 메서드인 경우 이름 부분에 대 한 typedef를 사용 합니다. 다음은 그 예입니다.

```cpp
C1<x, y, z<T>>::C2<a,b,c>::f
```

다음으로 바꿀 수 있습니다.

```cpp
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;
new_class::f
```

이 경고는 x64 컴파일러 에서만 발생 합니다.
