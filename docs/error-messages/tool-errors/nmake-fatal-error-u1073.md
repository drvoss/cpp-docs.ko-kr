---
title: NMAKE 심각한 오류 U1073
ms.date: 11/04/2016
f1_keywords:
- U1073
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
ms.openlocfilehash: 97d44594540d18bf008757506a9e36e6d16d2cd7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182697"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE 심각한 오류 U1073

' targetname '을 만드는 방법을 모릅니다.

지정 된 대상이 존재 하지 않습니다. 실행할 명령이 나 적용할 유추 규칙이 없습니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면

1. 대상 이름의 철자를 확인 합니다.

1. Targetname이 의사 ( *targetname* ) 인 경우 다른 설명 블록의 대상으로 지정 합니다.

1. *Targetname* 이 매크로 호출이 면 null 문자열로 확장 되지 않아야 합니다.
