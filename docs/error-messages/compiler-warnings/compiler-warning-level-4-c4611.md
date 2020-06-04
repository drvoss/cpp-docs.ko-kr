---
title: 컴파일러 경고(수준 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: 7de4cdf0eacb1b9848a4350f1d223da1fd47d1fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198304"
---
# <a name="compiler-warning-level-4-c4611"></a>컴파일러 경고(수준 4) C4611

' function '과 C++ 개체 소멸 사이의 상호 작용이 이식 가능 하지 않습니다.

일부 플랫폼에서 **catch** 를 포함 하는 함수는 범위 C++ 를 벗어난 경우 소멸의 개체 의미 체계를 지원 하지 않을 수 있습니다.

예기치 않은 동작을 방지 하려면 생성자와 소멸자가 있는 함수에서 **catch** 를 사용 하지 마십시오.

이 경고는 한 번만 실행 됩니다. [pragma warning](../../preprocessor/warning.md)을 참조 하십시오.
