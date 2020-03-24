---
title: 컴파일러 경고(수준 4) C4057
ms.date: 11/04/2016
f1_keywords:
- C4057
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
ms.openlocfilehash: 45d2db56a7b0fc871de60743954012faf0f5c366
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185388"
---
# <a name="compiler-warning-level-4-c4057"></a>컴파일러 경고(수준 4) C4057

'operator': 'identifier1'은 약간 다른 기본 형식에 대한 간접 참조가 'identifier2'와 다릅니다.

두 포인터 식은 다른 기본 형식을 참조합니다. 식을 변환하지 않고 사용합니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 부호 있는 형식과 부호 없는 형식을 혼합합니다.

1. **short** 및 **long** 형식을 혼합합니다.
