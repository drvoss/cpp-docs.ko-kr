---
title: jitintrinsic
ms.date: 11/04/2016
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
ms.openlocfilehash: cecadcad15ee65a44ad5a8245efdb69903c89459
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233706"
---
# <a name="jitintrinsic"></a>jitintrinsic

64비트 공용 언어 런타임에 중요한 항목으로 함수를 표시합니다. 이는 Microsoft에서 제공하는 라이브러리의 특정 함수에서 사용됩니다.

## <a name="syntax"></a>구문

```
__declspec(jitintrinsic)
```

## <a name="remarks"></a>설명

**`jitintrinsic`** 함수 시그니처에 MODOPT ( <xref:System.Runtime.CompilerServices.IsJitIntrinsic> )를 추가 합니다.

예기치 않은 결과가 발생할 수 있으므로 사용자는이 한정자를 사용 하지 않는 것이 좋습니다 **`__declspec`** .

## <a name="see-also"></a>참고 항목

[__declspec](../cpp/declspec.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)
