---
title: 컴파일러 오류 C2779
ms.date: 11/04/2016
f1_keywords:
- C2779
helpviewer_keywords:
- C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
ms.openlocfilehash: cf2a59726e87f5cd2cdb82129db2677bf6a69d29
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220238"
---
# <a name="compiler-error-c2779"></a>컴파일러 오류 C2779

' 선언 ': 속성 메서드는 비정적 데이터 멤버와만 연결 될 수 있습니다.

**`property`** 확장 특성이 정적 데이터 멤버에 잘못 적용 되었습니다.

다음 샘플에서는 C2779를 생성 합니다.

```cpp
// C2779.cpp
struct A {
   static __declspec(property(put=PutProp))
   // try the following line instead
   __declspec(property(put=PutProp))
      int prop;   // C2779
   int PutProp(void);
};
```
