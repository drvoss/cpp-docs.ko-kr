---
title: 범위 읽기
ms.date: 11/04/2016
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
ms.openlocfilehash: 86bb24647084d8bdc452960bab631587c2413276
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343144"
---
# <a name="reading-ranges"></a>범위 읽기

**ANSI 4.9.6.2**`fscanf` 함수에서 % [ 변환을 위한 scanlist의 첫 번째 문자도 아니고 마지막 문자도 아닌 대시(–) 문자의 해석

다음 줄

```
fscanf( fileptr, "%[A-Z]", strptr);
```

에서는 A–Z 범위에 속한 문자의 개수를 `strptr`이 가리키는 문자열로 읽습니다.

## <a name="see-also"></a>참조

[라이브러리 함수](../c-language/library-functions.md)
