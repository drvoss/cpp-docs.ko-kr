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
ms.openlocfilehash: edbeb187e568b833673d91ef70ff57fbd460659c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179057"
---
# <a name="results-of-calling-example"></a>호출 예제 결과

**Microsoft 전용**

## <a name="__cdecl"></a>__cdecl

C 데코레이팅된 함수 이름을 `_MyFunc`합니다.

![CDECL 호출 규칙](../cpp/media/vc37i01.gif "CDECL 호출 규칙") <br/>
**__Cdecl** 호출 규칙

## <a name="__stdcall-and-thiscall"></a>__stdcall 및 thiscall

C 데코레이팅된 이름 ( **__stdcall**)은 `_MyFunc@20`입니다. C 데코레이팅된 이름은 상표로 보호받고 있습니다.

![&#95;&#95;stdcall 및 thiscall 호출 규칙](../cpp/media/vc37i02.gif "&#95;&#95;stdcall 및 thiscall 호출 규칙") <br/>
__stdcall 및 thiscall 호출 규칙

## <a name="__fastcall"></a>__fastcall

C 데코레이팅된 이름 ( **__fastcall**)은 `@MyFunc@20`입니다. C 데코레이팅된 이름은 상표로 보호받고 있습니다.

![Fastcall에 대 &#95; &#95;한 호출 규칙](../cpp/media/vc37i03.gif "Fastcall에 대 &#95; &#95;한 호출 규칙") <br/>
__fastcall 호출 규칙

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[호출 예제: 함수 프로토타입 및 호출](../cpp/calling-example-function-prototype-and-call.md)
