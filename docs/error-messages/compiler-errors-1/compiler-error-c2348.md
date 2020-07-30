---
title: 컴파일러 오류 C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 716fdf244f19fa8f0960a0279da3c39af1546178
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218262"
---
# <a name="compiler-error-c2348"></a>컴파일러 오류 C2348

' type name ': C 스타일 집합체가 아니므로 포함 IDL에서 내보낼 수 없습니다.

내보내기 특성을 사용 하 여을 **`struct`** .idl 파일에 [export](../../windows/export.md) 추가 하려면에 데이터만 **`struct`** 포함 되어야 합니다.

다음 샘플에서는 C2348를 생성 합니다.

```cpp
// C2348.cpp
// C2348 error expected
[ module(name="SimpleMidlTest") ];

[export]
struct Point {
   // Delete the following two lines to resolve.
   Point() : m_i(0), m_j(0) {}
   Point(int i, int j) : m_i(i), m_j(j) {}

   int m_i;
   int m_j;
};
```
