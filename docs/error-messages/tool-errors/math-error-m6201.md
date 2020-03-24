---
title: 수학 오류 M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 0b1cd0d3fcd86a2174b19da41176dd97f547a295
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193708"
---
# <a name="math-error-m6201"></a>수학 오류 M6201

' function ': _DOMAIN 오류

지정 된 함수에 대 한 인수는 해당 함수에 대 한 유효한 입력 값의 도메인 밖에 있습니다.

## <a name="example"></a>예제

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

이 오류는 함수 이름, 해당 인수 및 오류 유형을 사용 하 여 `_matherr` 함수를 호출 합니다. `_matherr` 함수를 다시 작성 하 여 특정 런타임 부동 소수점 수학 오류에 대 한 처리를 사용자 지정할 수 있습니다.
