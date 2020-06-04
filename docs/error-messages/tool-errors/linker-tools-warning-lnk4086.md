---
title: 링커 도구 경고 LNK4086
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: 6e012ceb5e20855353c69bbcde85fb78afad2011
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183425"
---
# <a name="linker-tools-warning-lnk4086"></a>링커 도구 경고 LNK4086

' function ' entrypoint는 ' number ' 바이트의 인수를 사용 하 여 __stdcall 하지 않습니다. 이미지가 실행 되지 않을 수 있습니다.

DLL에 대 한 진입점은 `__stdcall`이어야 합니다. [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) 옵션을 사용 하 여 함수를 다시 컴파일하거나 함수를 정의할 때 `__stdcall` 또는 WINAPI를 지정 합니다.
