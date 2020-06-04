---
title: 인라인 어셈블리에서 C++ 함수 호출
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
ms.openlocfilehash: f16e466ebb5f31231411eaaf9a1a85bfcc46a34d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169580"
---
# <a name="calling-c-functions-in-inline-assembly"></a>인라인 어셈블리에서 C++ 함수 호출

**Microsoft 전용**

`__asm` 블록은 오버로드되지 않은 전역 C++ 함수만 호출할 수 있습니다. 오버로드된 전역 C++ 함수 또는 C++ 멤버 함수를 호출하면 컴파일러에서 오류가 발생합니다.

**Extern "C"** 링크로 선언 된 함수를 호출할 수도 있습니다. 이렇게 하면 모든 표준 헤더 파일에서 C++ **extern "C"** 링크가 포함 되도록 라이브러리 함수를 선언 하기 때문에 프로그램 내의 `__asm` 블록이 C 라이브러리 함수를 호출할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[인라인 어셈블러](../../assembler/inline/inline-assembler.md)<br/>
