---
title: 컴파일러 오류 C2410
ms.date: 11/04/2016
f1_keywords:
- C2410
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
ms.openlocfilehash: e4d30ff0fbca7428fb1dcf252bcad50bd53488d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205705"
---
# <a name="compiler-error-c2410"></a>컴파일러 오류 C2410

' identifier ': ' context '의 멤버 이름이 모호 합니다.

식별자가이 컨텍스트에서 둘 이상의 구조체 또는 공용 구조체의 멤버입니다.

오류를 발생 시킨 피연산자에서 구조체 또는 공용 구조체 지정자를 사용 합니다. 구조체 또는 공용 구조체 지정자는 참조 되는 구조체 또는 공용 구조체와 동일한 형식의 `typedef` 이름 또는 변수 `struct` 또는 `union`의 식별자입니다. 피연산자를 사용 하려면 지정자는 첫 번째 멤버 선택 연산자 (.)의 왼쪽 피연산자 여야 합니다.
