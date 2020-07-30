---
title: 컴파일러 오류 C2410
ms.date: 11/04/2016
f1_keywords:
- C2410
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
ms.openlocfilehash: 7e6e07fb90827fb28fcdde2f723a36c4529a1868
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225490"
---
# <a name="compiler-error-c2410"></a>컴파일러 오류 C2410

' identifier ': ' context '의 멤버 이름이 모호 합니다.

식별자가이 컨텍스트에서 둘 이상의 구조체 또는 공용 구조체의 멤버입니다.

오류를 발생 시킨 피연산자에서 구조체 또는 공용 구조체 지정자를 사용 합니다. 구조체 또는 공용 구조체 지정자는 형식의 식별자 또는 **`struct`** **`union`** **`typedef`** 참조 되는 구조체 또는 공용 구조체와 동일한 형식의 이름 또는 변수입니다. 피연산자를 사용 하려면 지정자는 첫 번째 멤버 선택 연산자 (.)의 왼쪽 피연산자 여야 합니다.
