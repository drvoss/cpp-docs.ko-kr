---
title: 링커 도구 경고 LNK4237
ms.date: 11/04/2016
f1_keywords:
- LNK4237
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
ms.openlocfilehash: aaa26393f1ce76d3e1bc40e5ba4978d1bcdb4fc9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193760"
---
# <a name="linker-tools-warning-lnk4237"></a>링커 도구 경고 LNK4237

' Dll '에서 가져올 때/SUBSYSTEM: NATIVE가 지정 되었습니다. /SUBSYSTEM: CONSOLE 또는/SUBSYSTEM: WINDOWS를 사용 합니다.

[/SUBSYSTEM: NATIVE](../../build/reference/subsystem-specify-subsystem.md) 는 다음 중 하나 이상을 직접 사용 하는 Windows (Win32) 응용 프로그램을 빌드할 때 지정 되었습니다.

- kernel32.dll

- gdi32.dll

- user32.dll

- msvcrt.lib\* dll 중 하나입니다.

**/SUBSYSTEM: NATIVE**를 지정 하지 않고이 경고를 해결 합니다.
