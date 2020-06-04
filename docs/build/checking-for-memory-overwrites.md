---
title: 메모리 덮어쓰기 확인
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: 2c59cb96d640df6dcd96b9e0eafbcd325ed475f5
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342249"
---
# <a name="checking-for-memory-overwrites"></a>메모리 덮어쓰기 확인

힙 조작 함수 호출 시 액세스 위반이 발생되면 프로그램이 힙을 손상했을 가능성이 있습니다. 해당하는 경우의 일반적인 증상은 다음과 같습니다.

```
Access Violation in _searchseg
```

[_heapchk](../c-runtime-library/reference/heapchk.md) 함수는 디버그 빌드와 릴리스 빌드(Windows NT에만 해당) 모두에서 런타임 라이브러리 힙의 무결성을 확인하는 데 사용할 수 있습니다. `_heapchk`는 `AfxCheckMemory` 함수를 사용하여 힙 덮어쓰기를 확인하는 것과 같은 방법으로 사용할 수 있습니다. 예를 들면 다음과 같습니다.

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

이 함수가 실패하는 경우에는 힙이 손상된 시점을 확인해야 합니다.

## <a name="see-also"></a>참조

[릴리스 빌드 문제 해결](fixing-release-build-problems.md)
