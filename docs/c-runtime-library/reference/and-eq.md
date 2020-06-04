---
title: and_eq
ms.date: 11/04/2016
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- and_eq
- std.and_eq
- std::and_eq
helpviewer_keywords:
- and_eq macro
ms.assetid: 11091772-e359-4c2b-95c6-00841ac04354
ms.openlocfilehash: f505faa561dafc5ba0f929f94676e0ee81a32199
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170919"
---
# <a name="and_eq"></a>and_eq

&= 연산자에 대한 대안입니다.

## <a name="syntax"></a>구문

```C
#define and_eq &=
```

## <a name="remarks"></a>주의

매크로가 &= 연산자를 생성합니다.

## <a name="example"></a>예제

```cpp
// iso646_and_eq.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   int a = 3, b = 2, result;

   result= a &= b;
   cout << result << endl;

   result= a and_eq b;
   cout << result << endl;
}
```

```Output
2
2
```

## <a name="requirements"></a>요구 사항

**헤더:** \<iso646 >
