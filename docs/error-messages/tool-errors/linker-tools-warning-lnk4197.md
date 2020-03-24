---
title: 링커 도구 경고 LNK4197
ms.date: 09/05/2018
f1_keywords:
- LNK4197
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
ms.openlocfilehash: 92702864a00455e4b70f00dfc9988bfb754e2e64
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183282"
---
# <a name="linker-tools-warning-lnk4197"></a>링커 도구 경고 LNK4197

> '*exportname*' 내보내기가 여러 번 지정 되었습니다. 첫 번째 사양 사용

내보내기는 여러 가지 방법으로 지정 됩니다. 링커에서는 첫 번째 사양을 사용 하 고 나머지는 무시 합니다.

C 런타임 라이브러리를 다시 작성 하는 경우이 메시지를 무시할 수 있습니다.

내보내기를 정확히 동일한 방식으로 여러 번 지정 하면 링커에서 경고가 발생 하지 않습니다.

예를 들어 .def 파일의 다음 내용이이 경고를 발생 시킵니다.

```
EXPORTS
   functioname      NONAME
   functioname      @10
```

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 명령줄에 동일한 내보내기가 지정 됩니다 (내보내기:). .def 파일에 있습니다.

2. 동일한 내보내기가 .def 파일에서 서로 다른 특성을 사용 하 여 두 번 나열 됩니다.
