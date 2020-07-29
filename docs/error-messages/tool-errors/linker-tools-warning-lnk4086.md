---
title: 링커 도구 경고 LNK4086
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: f692f848825cd3d8e5e1fc042cb94d7cce8ea6bf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87195813"
---
# <a name="linker-tools-warning-lnk4086"></a>링커 도구 경고 LNK4086

' function ' entrypoint는 ' number ' 바이트의 인수를 사용 하 여 __stdcall 하지 않습니다. 이미지가 실행 되지 않을 수 있습니다.

DLL에 대 한 진입점은 이어야 합니다 **`__stdcall`** . [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) 옵션을 사용 하 여 함수를 다시 컴파일하거나 **`__stdcall`** 함수를 정의할 때 또는 WINAPI를 지정 합니다.
