---
title: 컴파일러 오류 C3166
ms.date: 11/04/2016
f1_keywords:
- C3166
helpviewer_keywords:
- C3166
ms.assetid: ec3e330d-c15d-4158-8268-09101486c566
ms.openlocfilehash: 1915d58f73ce8d16135951b359c3f0fd48aea3ac
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230872"
---
# <a name="compiler-error-c3166"></a>컴파일러 오류 C3166

> ' pointer ': 내부 __gc 포인터에 대 한 포인터를 ' type '의 멤버로 선언할 수 없습니다.

컴파일러가 잘못 된 포인터 선언 ( **`__nogc`** 포인터에 대 한 포인터)을 발견 했습니다. **`__gc`**

C3166는 사용 되지 않는 컴파일러 옵션을 사용 하 여 연결할 수 **`/clr:oldSyntax`** 있습니다.
