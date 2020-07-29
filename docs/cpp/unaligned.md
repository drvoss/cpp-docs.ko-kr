---
title: __unaligned
ms.date: 12/17/2018
f1_keywords:
- __unaligned_cpp
- __unaligned
- _unaligned
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
ms.openlocfilehash: 2ab94a44d08165ca6e8f394278e24d7c8d201398
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223501"
---
# <a name="__unaligned"></a>__unaligned

**Microsoft 전용**입니다. 한정자를 사용 하 여 포인터를 선언 하면 **`__unaligned`** 컴파일러에서 포인터가 정렬 되지 않은 데이터를 처리 한다고 가정 합니다. 따라서 플랫폼에 맞게 코드를 생성 하 여 포인터를 통해 정렬 되지 않은 읽기와 쓰기를 처리 합니다.

## <a name="remarks"></a>설명

이 한정자는 포인터로 주소가 지정 된 데이터의 맞춤을 설명 합니다. 포인터 자체는 정렬 된 것으로 간주 됩니다.

키워드의 필요성은 **`__unaligned`** 플랫폼과 환경에 따라 달라 집니다. 데이터를 적절 하 게 표시 하지 못하면 성능 저하부터 하드웨어 오류로 인해 문제가 발생할 수 있습니다. **`__unaligned`** 한정자는 x86 플랫폼에 대해 유효 하지 않습니다.

이전 버전과의 호환성을 위해 **`_unaligned`** 는 **`__unaligned`** 컴파일러 옵션 [ `/Za` \( 언어 확장 사용 안 함](../build/reference/za-ze-disable-language-extensions.md) 을 지정 하지 않는 경우의 동의어입니다.

정렬에 대한 자세한 내용은 다음을 참조하십시오.

- [`align`](../cpp/align-cpp.md)

- [`alignof`연산자](../cpp/alignof-operator.md)

- [`pack`](../preprocessor/pack.md)

- [`/Zp`(구조체 멤버 맞춤)](../build/reference/zp-struct-member-alignment.md)

- [구조체 맞춤 예제](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>참고 항목

[C++ 키워드](../cpp/keywords-cpp.md)
