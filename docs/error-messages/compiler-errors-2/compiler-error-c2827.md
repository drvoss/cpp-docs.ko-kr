---
title: 컴파일러 오류 C2827
ms.date: 11/04/2016
f1_keywords:
- C2827
helpviewer_keywords:
- C2827
ms.assetid: cb3e5814-0c92-40e4-b620-98578ae3003a
ms.openlocfilehash: 8da60b895ad5dab0713d736142225053d14301c1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201944"
---
# <a name="compiler-error-c2827"></a>컴파일러 오류 C2827

' operator operator '는 단항 형식으로 전역으로 재정의할 수 없습니다.

연산자는 개체 외부에 단항 형식을 사용할 수 없습니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. 오버 로드 된 연산자를 개체의 로컬으로 만듭니다.

1. 오버 로드할 적절 한 단항 연산자를 선택 합니다.
