---
title: 컴파일러 오류 C2891
ms.date: 11/04/2016
f1_keywords:
- C2891
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
ms.openlocfilehash: 2544cfc9e8cff283a7c3e0ace499408bb84cd046
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201641"
---
# <a name="compiler-error-c2891"></a>컴파일러 오류 C2891

' parameter ': 템플릿 매개 변수의 주소를 가져올 수 없습니다.

Lvalue가 아닌 경우 템플릿 매개 변수의 주소를 가져올 수 없습니다. 형식 매개 변수는 주소가 없으므로 lvalue가 아닙니다. Lvalue가 아닌 템플릿 매개 변수 목록에서 형식이 아닌 값에도 주소가 없습니다. 이는 템플릿 매개 변수로 전달 된 값이 템플릿 인수의 컴파일러 생성 복사본 이기 때문에 컴파일러 오류 C2891를 발생 시킨 코드의 예입니다.

```
template <int i> int* f() { return &i; }
```

참조 형식과 같은 lvalues에 해당 하는 템플릿 매개 변수는 해당 주소를 가져올 수 있습니다.

```
template <int& r> int* f() { return &r; }
```

이 오류를 해결 하려면 lvalue가 아닌 경우 템플릿 매개 변수의 주소를 사용 하지 마십시오.
