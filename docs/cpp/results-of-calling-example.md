---
title: 호출 예제 결과
ms.date: 11/19/2018
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
ms.openlocfilehash: 1bf5fe62b8ef2b7a37bf72b7a40e5d47af3f3961
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225880"
---
# <a name="results-of-calling-example"></a>호출 예제 결과

**Microsoft 전용**

## <a name="__cdecl"></a>__cdecl

C 데코레이팅된 함수 이름은 `_MyFunc` 입니다.

![CDECL 호출 규칙](../cpp/media/vc37i01.gif "CDECL 호출 규칙") <br/>
**`__cdecl`** 호출 규칙

## <a name="__stdcall-and-thiscall"></a>__stdcall 및 thiscall

C 데코레이팅된 이름 ( **`__stdcall`** )은 `_MyFunc@20` 입니다. C + + 데코레이팅된 이름은 구현 별로 다릅니다.

![&#95;&#95;stdcall 및 thiscall 호출 규칙](../cpp/media/vc37i02.gif "&#95;&#95;stdcall 및 thiscall 호출 규칙") <br/>
__stdcall 및 thiscall 호출 규칙

## <a name="__fastcall"></a>__fastcall

C 데코레이팅된 이름 ( **`__fastcall`** )은 `@MyFunc@20` 입니다. C + + 데코레이팅된 이름은 구현 별로 다릅니다.

![ &#95;&#95;fastcall에 대 한 호출 규칙](../cpp/media/vc37i03.gif " &#95;&#95;fastcall에 대 한 호출 규칙") <br/>
__fastcall 호출 규칙

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[호출 예제: 함수 프로토타입 및 호출](../cpp/calling-example-function-prototype-and-call.md)
