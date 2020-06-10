---
title: treat_as_floating_point 구조체
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
ms.openlocfilehash: add69179b23a953a937458cbfa55254b21c5ea37
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685106"
---
# <a name="treat_as_floating_point-structure"></a>treat_as_floating_point 구조체

`Rep`가 부동 소수점 형식으로 처리될 수 있는지를 지정합니다.

## <a name="syntax"></a>구문

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>주의


`Rep`는 `treat_as_floating_point<Rep>` 특수화가 [true_type](../standard-library/type-traits-typedefs.md#true_type)에서 파생되는 경우에만 부동 소수점 형식으로 처리할 수 있습니다. 클래스 템플릿은 사용자 정의 형식에 대해 특수화될 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<chrono>

**네임스페이스:** std::chrono

## <a name="see-also"></a>참조

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
