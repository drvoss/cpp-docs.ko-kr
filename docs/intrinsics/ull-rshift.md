---
title: __ull_rshift
ms.date: 09/02/2019
f1_keywords:
- __ull_rshift
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
ms.openlocfilehash: bf9fe7775cee1c774c097a1b6bd371721c9fa34f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80074984"
---
# <a name="__ull_rshift"></a>__ull_rshift

**Microsoft 전용**

x 64에서는 첫 번째 매개 변수로 지정 된 64 비트 값을 두 번째 매개 변수로 지정 된 비트 수 만큼 오른쪽으로 이동 합니다.

## <a name="syntax"></a>구문

```C
unsigned __int64 __ull_rshift(
   unsigned __int64 mask,
   int nBit
);
```

### <a name="parameters"></a>매개 변수

*마스크*\
진행 오른쪽으로 이동할 64 비트 정수 값입니다.

*n 비트*\
진행 X 64에서 이동할 비트 수, x86의 모듈로 32, x 64의 경우 모듈로 64

## <a name="return-value"></a>반환 값

`nBit` 비트로 이동 하는 마스크입니다.

## <a name="requirements"></a>요구 사항

|Intrinsic|아키텍처|
|---------------|------------------|
|`__ull_rshift`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>주의

두 번째 매개 변수가 x 86의 31 (x64에서 63) 보다 큰 경우 해당 숫자는 이동할 비트 수를 결정 하는 모듈로 32 (x 64의 경우 64)로 간주 됩니다. 이름에 `ull`은 `unsigned long long (unsigned __int64)`을 나타냅니다.

## <a name="example"></a>예제

```cpp
// ull_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ull_rshift)

int main()
{
   unsigned __int64 mask = 0x100;
   int nBit = 8;
   mask = __ull_rshift(mask, nBit);
   cout << hex << mask << endl;
}
```

```Output
1
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ll_rshift](../intrinsics/ll-rshift.md)\
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
