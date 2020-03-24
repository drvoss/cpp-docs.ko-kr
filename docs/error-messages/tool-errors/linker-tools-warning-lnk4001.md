---
title: 링커 도구 경고 LNK4001
ms.date: 11/04/2016
f1_keywords:
- LNK4001
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
ms.openlocfilehash: d9659b0cf372ff8ebc225b890fb68866872bb3d6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194410"
---
# <a name="linker-tools-warning-lnk4001"></a>링커 도구 경고 LNK4001

개체 파일을 지정 하지 않았습니다. 사용 되는 라이브러리

링커가 하나 이상의 .lib 파일을 전달 했지만 .obj 파일은 전달 되지 않았습니다.

링커가 .obj 파일에서 액세스할 수 있는 .lib 파일의 정보에 액세스할 수 없기 때문에이 경고는 다른 링커 옵션을 명시적으로 지정 해야 함을 나타냅니다. 예를 들어 [/MACHINE](../../build/reference/machine-specify-target-platform.md), [/out](../../build/reference/out-output-file-name.md)또는 [/entry](../../build/reference/entry-entry-point-symbol.md) 옵션을 지정 해야 할 수 있습니다.
