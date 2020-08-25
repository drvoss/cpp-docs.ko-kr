---
title: _locking 상수
ms.date: 11/04/2016
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
ms.openlocfilehash: 8cfc1f933179e043f464a69f3ac5cf4ca25763e0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830828"
---
# <a name="_locking-constants"></a>_locking 상수

## <a name="syntax"></a>구문

```
#include <sys/locking.h>
```

## <a name="remarks"></a>설명

`_locking` 함수 호출에서 *mode* 인수는 수행할 잠금 작업을 지정합니다.

*mode* 인수는 다음 매니페스트 상수 중 하나여야 합니다.

|값|설명|
|-|-|
| `_LK_LOCK`  | 지정된 바이트를 잠급니다. 바이트를 잠글 수 없는 경우 이 함수는 1초 후 다시 시도합니다. 10번 시도 후에도 바이트를 잠글 수 없으면 이 함수는 오류를 반환합니다.  |
| `_LK_RLCK`  | `_LK_LOCK`와 동일합니다.  |
|`_LK_NBLCK`  | 지정된 바이트를 잠급니다. 바이트를 잠글 수 없으면 이 함수는 오류를 반환합니다.  |
| `_LK_NBRLCK`  | `_LK_NBLCK`와 동일합니다.  |
| `_LK_UNLCK`  | 지정된 바이트의 잠금을 해제합니다. (해당 바이트는 이전에 잠겼을 것입니다.)  |

## <a name="see-also"></a>참고 항목

[_locking](../c-runtime-library/reference/locking.md)<br/>
[전역 상수](../c-runtime-library/global-constants.md)
