---
title: 컴파일러 오류 C3116
ms.date: 11/04/2016
f1_keywords:
- C3116
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
ms.openlocfilehash: b336588d732fca2fd45b753429a563360f575912
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223449"
---
# <a name="compiler-error-c3116"></a>컴파일러 오류 C3116

' storage 지정자 ': 인터페이스 메서드에 대 한 저장소 클래스가 잘못 되었습니다.

**`typedef`**, 또는를 **`register`** **`static`** 인터페이스 메서드의 저장소 클래스로 사용 했습니다. 이러한 저장소 클래스는 인터페이스 멤버에서 허용 되지 않습니다.

다음 샘플에서는 C3116를 생성 합니다.

```cpp
// C3116.cpp
__interface ImyInterface
{
   static void myFunc();   // C3116
};
```
