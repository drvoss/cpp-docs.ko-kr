---
title: 컴파일러 오류 C2439
ms.date: 11/04/2016
f1_keywords:
- C2439
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
ms.openlocfilehash: 99f3644869f6c5395684643f0e7802f3a01baa62
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205363"
---
# <a name="compiler-error-c2439"></a>컴파일러 오류 C2439

' identifier ': 멤버를 초기화할 수 없습니다.

클래스, 구조체 또는 공용 구조체 멤버를 초기화할 수 없습니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 간접 기본 클래스 또는 구조체를 초기화 하는 중입니다.

1. 클래스 또는 구조체의 상속 된 멤버를 초기화 하려고 합니다. 상속 된 멤버는 클래스 또는 구조체의 생성자에 의해 초기화 되어야 합니다.
