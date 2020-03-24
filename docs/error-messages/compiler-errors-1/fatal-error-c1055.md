---
title: 심각한 오류 C1055
ms.date: 11/04/2016
f1_keywords:
- C1055
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
ms.openlocfilehash: c349c09b4931c0a303e7619b364ab237394bd4fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204453"
---
# <a name="fatal-error-c1055"></a>심각한 오류 C1055

컴파일러 한계: 키가 부족 합니다.

소스 파일에 기호가 너무 많습니다. 컴파일러에서 기호 테이블에 대 한 해시 키가 부족 합니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. 소스 파일을 더 작은 파일로 분할 합니다.

1. 불필요 한 헤더 파일을 제거 합니다.

1. 새 변수를 만드는 대신 임시 및 전역 변수를 다시 사용 합니다.
