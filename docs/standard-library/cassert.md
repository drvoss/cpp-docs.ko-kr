---
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: 58ebd91fb4fa32cf31d2c49429d0445b92fe0c82
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449917"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

C 표준 라이브러리 헤더 \<assert.h>를 포함하고 `std` 네임스페이스에 연결된 이름을 추가합니다. 이 헤더를 포함하면 C 표준 라이브러리 헤더에서 외부 링크를 사용하여 선언한 이름이 `std` 네임스페이스에 선언됩니다.

> [!NOTE]
> \<assert. h >는 `static_assert` 매크로를 정의하지 않습니다.

## <a name="syntax"></a>구문

```cpp
#include <cassert>
```

## <a name="macros"></a>매크로

```cpp
#define assert(E)
```

### <a name="remarks"></a>설명

`assert(E)`는 마지막으로 `assert`가 정의되거나 재정의된 NDEBUG가 정의되어 있거나, 부울로 변환된 *E*가 **true**로 평가되는 경우만 상수입니다.

## <a name="see-also"></a>참고자료

[assert Macro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)\
[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
