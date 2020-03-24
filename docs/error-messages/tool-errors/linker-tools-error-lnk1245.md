---
title: 링커 도구 오류 LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 19e3f820b5bd7fdd8eac2f7b5a96fb5923ae0b92
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183802"
---
# <a name="linker-tools-error-lnk1245"></a>링커 도구 오류 LNK1245

' subsystem ' 하위 시스템을 잘못 지정 했습니다. /SUBSYSTEM는 WINDOWS, WINDOWSCE 또는 CONSOLE 이어야 합니다.

[/clr](../../build/reference/clr-common-language-runtime-compilation.md) 을 사용 하 여 개체를 컴파일하고 다음 조건 중 하나에 해당 하는 경우

- 사용자 지정 진입점이 정의 되었습니다.[즉,](../../build/reference/entry-entry-point-symbol.md)링커가 하위 시스템을 유추할 수 없습니다.

- /Clr 개체에 대해 유효 하지 않은 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) 링커 옵션에 값이 전달 되었습니다.

두 경우 모두 해결 방법은/SUBSYSTEM 링커 옵션에 대 한 유효한 값을 지정 하는 것입니다.
