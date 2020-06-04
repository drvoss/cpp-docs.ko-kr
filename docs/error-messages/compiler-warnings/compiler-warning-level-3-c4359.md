---
title: 컴파일러 경고(수준 3) C4359
ms.date: 11/04/2016
f1_keywords:
- C4359
helpviewer_keywords:
- C4359
ms.assetid: d8fe993c-ef82-45a0-a43d-c29f9d1bacdb
ms.openlocfilehash: 5cb65bab1f6490d1c39b20bfba2b3ecc68da664d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198694"
---
# <a name="compiler-warning-level-3-c4359"></a>컴파일러 경고(수준 3) C4359

' type ': 실제 맞춤 (8)이 __declspec (align ())에 지정 된 값 보다 큽니다.

형식에 지정 된 맞춤이 해당 데이터 멤버 중 하나의 형식에 대 한 맞춤 보다 낮습니다.  자세한 내용은 [align](../../cpp/align-cpp.md)을 참조 하십시오.

## <a name="example"></a>예제

다음 샘플에서는 C4359를 생성 합니다.

```cpp
// C4359.cpp
// compile with: /W3 /c
struct __declspec(align(8)) C8 { __int64 i; };
struct __declspec(align(4)) C4  { C8 m8; };   // C4359
struct __declspec(align(8)) C8_b  { C8 m8; };   // OK
struct __declspec(align(16)) C16  { C8 m8; };   // OK
```
