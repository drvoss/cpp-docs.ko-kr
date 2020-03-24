---
title: 명령줄 경고 D9026
ms.date: 11/04/2016
f1_keywords:
- D9026
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
ms.openlocfilehash: 59dfcdc97fb9caf60a018cb20583ee6fca3dcb27
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196705"
---
# <a name="command-line-warning-d9026"></a>명령줄 경고 D9026

옵션이 전체 명령줄에 적용 됩니다.

파일 이름을 지정한 후 명령에 옵션을 지정 했습니다. 옵션이 앞에 있는 파일에 적용 되었습니다.

예를 들어, 명령에서

```
CL verdi.c /G5 puccini.c
```

VERDI. c 파일은/G5 기본값이 아닌/G5 옵션을 사용 하 여 컴파일됩니다.

이 동작은 파일 이름 앞에 지정 된 옵션만 적용 한 일부 이전 버전의 경우와 다르며,이로 인해/G5c를 사용 하 여 PUCCINI 및/G4 및를 사용 하 여 컴파일되는 VERDI. c를 사용 합니다.
