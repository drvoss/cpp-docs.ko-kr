---
title: 심각한 오류 C1054
ms.date: 11/04/2016
f1_keywords:
- C1054
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
ms.openlocfilehash: d094d0892d43a5f9894f03538f72e59b57bad6db
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204466"
---
# <a name="fatal-error-c1054"></a>심각한 오류 C1054

컴파일러 한계: 이니셜라이저가 너무 많이 중첩 되었습니다.

코드는 초기화 되는 형식의 조합에 따라 이니셜라이저의 중첩 한도 (10-15 수준)를 초과 합니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. 초기화 되는 데이터 형식을 단순화 하 여 중첩을 줄입니다.

1. 선언 후 별도의 문에서 변수를 초기화 합니다.
