---
title: Microsoft 확장명
ms.date: 11/04/2016
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
ms.openlocfilehash: a2d0846e55122f177b4868c2e80c4f1d27267f5e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179408"
---
# <a name="microsoft-extensions"></a>Microsoft 확장명

*asm 문*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__asm***어셈블리 명령* **;** <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__asm {** *어셈블리-명령 목록* **};** <sub>opt</sub>

*어셈블리-명령 목록*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*어셈블리 명령* **;** <sub>opt</sub> <br/>
&nbsp;&nbsp; *&nbsp;&nbsp;어셈블리* **;** *명령* **;** 입니다. <sub>opt</sub>

*microsoft-modifier 목록*:<br/>
&nbsp;&nbsp; *&nbsp;&nbsp;ms-수정자* *목록*<sub>옵트인</sub>

*ms-한정자*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__cdecl**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__fastcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__stdcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__syscall** (이후 구현을 위해 예약 됨)<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__oldcall** (이후 구현을 위해 예약 됨)<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__unaligned** (이후 구현을 위해 예약 됨)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*기반-한정자*

*기반-한정자*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__based (** *기반 형식* **)**

*기반 형식*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*이름*
