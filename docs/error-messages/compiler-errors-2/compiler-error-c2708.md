---
title: 컴파일러 오류 C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: a1d3379a0da42c5aabd38cffbf6f6a3f340ef3b9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202373"
---
# <a name="compiler-error-c2708"></a>컴파일러 오류 C2708

' identifier ': 실제 매개 변수 길이 (바이트)가 이전 호출 또는 참조와 다릅니다.

[__Stdcall](../../cpp/stdcall.md) 함수는 프로토타입 뒤에와 야 합니다. 그렇지 않으면 컴파일러는 함수에 대 한 첫 번째 호출을 프로토타입으로 해석 하며, 컴파일러에서와 일치 하지 않는 호출을 발견할 때이 오류가 발생 합니다.

이 오류를 해결 하려면 함수 프로토타입을 추가 합니다.
