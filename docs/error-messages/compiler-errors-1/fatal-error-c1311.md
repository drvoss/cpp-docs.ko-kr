---
title: 심각한 오류 C1311
ms.date: 11/04/2016
f1_keywords:
- C1311
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
ms.openlocfilehash: e57e4e0899a5f9d81e87a203b1b699cef0884f0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203270"
---
# <a name="fatal-error-c1311"></a>심각한 오류 C1311

COFF 형식은 주소의 number 바이트를 사용 하 여 ' v a r '을 정적으로 초기화할 수 없습니다.

컴파일 시간에 값을 알 수 없는 주소는 해당 형식의 저장소가 4 바이트 미만인 변수에 정적으로 할당 될 수 없습니다.

이 오류는 유효 C++하지 않은 코드에서 발생할 수 있습니다.

다음 코드 예제는 C1311을 일으킬 수 있는 한 가지 조건을 보여줍니다.

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```
