---
title: 컴파일러 오류 C2692
ms.date: 11/04/2016
f1_keywords:
- C2692
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
ms.openlocfilehash: 7ce57cd50e9ec83cf80ec64e14f49eb9714f9208
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177094"
---
# <a name="compiler-error-c2692"></a>컴파일러 오류 C2692

' function_name ': C 컴파일러에 '/clr ' 옵션으로 완전히 프로토타입화 된 함수가 필요 합니다.

.NET 관리 코드를 컴파일하는 경우 C 컴파일러에는 ANSI 함수 선언이 필요 합니다. 또한 함수에서 매개 변수를 사용 하지 않는 경우 명시적으로 `void`를 매개 변수 형식으로 선언 해야 합니다.
