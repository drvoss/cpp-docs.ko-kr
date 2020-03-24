---
title: 명령줄 경고 D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: 46ed5750bd1f315f20658ace9b83fac532fbbabb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196680"
---
# <a name="command-line-warning-d9027"></a>명령줄 경고 D9027

소스 파일 '\<파일 이름 > '이 (가) 무시 됨

CL.EXE에서 입력 원본 파일을 무시 했습니다.

이 경고는/Fo 옵션과/c 옵션을 사용 하 여 명령줄의 출력 파일 이름 사이에 공백을 사용 하 여 발생할 수 있습니다. 다음은 그 예입니다.

```
cl /c /Fo output.obj input.c
```

/Fo와 `output.obj`사이에 공백이 있으므로 CL.EXE는 입력 파일 이름으로 `output.obj`를 사용 합니다. 문제를 해결 하려면 다음 공간을 제거 합니다.

```
cl /c /Fooutput.obj input.c
```
