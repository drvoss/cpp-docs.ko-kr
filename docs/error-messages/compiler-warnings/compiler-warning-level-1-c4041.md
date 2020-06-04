---
title: 컴파일러 경고(수준 1) C4041
ms.date: 11/04/2016
f1_keywords:
- C4041
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
ms.openlocfilehash: 14ea6d9cae3b490107b656153bb68815026971e1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164237"
---
# <a name="compiler-warning-level-1-c4041"></a>컴파일러 경고(수준 1) C4041

컴파일러 한계 : 브라우저 출력을 종료하고 있습니다.

브라우저 정보가 컴파일러 한계를 초과했습니다.

[/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (지역 변수를 포함하는 브라우저 정보)을 사용하여 컴파일하면 이 경고가 발생할 수 있습니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. /Fr(지역 변수 없는 브라우저 정보)을 사용하여 컴파일합니다.

1. 브라우저 출력을 사용하지 않도록 설정합니다(/FR 또는 /Fr 없이 컴파일).
