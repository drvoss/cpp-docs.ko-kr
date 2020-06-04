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
ms.openlocfilehash: 4626ba82d1d24582951bbffd8e6be687007d390f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178190"
---
# <a name="jitintrinsic"></a>jitintrinsic

64비트 공용 언어 런타임에 중요한 항목으로 함수를 표시합니다. 이는 Microsoft에서 제공하는 라이브러리의 특정 함수에서 사용됩니다.

## <a name="syntax"></a>구문

```
__declspec(jitintrinsic)
```

## <a name="remarks"></a>주의

**jitintrinsic** 함수 시그니처에 MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>)를 추가 합니다.

예기치 않은 결과가 발생할 수 있으므로 사용자는이 **__declspec** 한정자를 사용 하지 않는 것이 좋습니다.

## <a name="see-also"></a>참고 항목

[__declspec](../cpp/declspec.md)<br/>
[키워드](../cpp/keywords-cpp.md)
