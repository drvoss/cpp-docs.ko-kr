---
title: 컴파일러 오류 C2834
ms.date: 11/04/2016
f1_keywords:
- C2834
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
ms.openlocfilehash: a6a7bc0591fd51c808c303e94eeaaffd6111ffcd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201931"
---
# <a name="compiler-error-c2834"></a>컴파일러 오류 C2834

' operator operator '는 전역적으로 정규화 되어야 합니다.

`new` 및 `delete` 연산자는 상주 하는 클래스에 연결 됩니다. 범위 확인은 다른 클래스에서 `new` 또는 `delete` 버전을 선택 하는 데 사용할 수 없습니다. 여러 형식의 `new` 또는 `delete` 연산자를 구현 하려면 추가 정식 매개 변수를 사용 하 여 연산자의 버전을 만듭니다.
