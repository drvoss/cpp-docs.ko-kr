---
title: __thiscall
ms.date: 11/04/2016
f1_keywords:
- __thiscall
- __thiscall_cpp
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
ms.openlocfilehash: 8772159dca71bb7605af5e5919425065423d503d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188157"
---
# <a name="__thiscall"></a>__thiscall

**Microsoft 전용**

**__Thiscall** 호출 규칙은 멤버 함수에서 사용 되며, 변수 인수를 사용 하지 않는 멤버 C++ 함수에서 사용 되는 기본 호출 규칙입니다. **__Thiscall**에서 호출 수신자는 스택을 정리 합니다 .이는 `vararg` 함수에서 사용할 수 없습니다. 인수는 오른쪽에서 왼쪽으로 스택에 푸시됩니다. **이** 포인터는 x86 아키텍처의 스택이 아니라 레지스터 ECX를 통해 전달 됩니다.

**__Thiscall** 사용 하는 한 가지 이유는 멤버 함수가 기본적으로 `__clrcall`를 사용 하는 클래스에 있습니다. 이 경우 **__thiscall** 를 사용 하 여 네이티브 코드에서 개별 멤버 함수를 호출할 수 있게 만들 수 있습니다.

[/Clr: pure](../build/reference/clr-common-language-runtime-compilation.md)를 사용 하 여 컴파일하는 경우 별도로 지정 하지 않으면 모든 함수와 함수 포인터가 `__clrcall` 됩니다. **/Clr: pure** 및 **/clr: safe** 컴파일러 옵션은 visual studio 2015에서 더 이상 사용 되지 않으며 visual studio 2017에서는 지원 되지 않습니다.

Visual Studio 2005 이전 릴리스에서는 **__thiscall** 키워드가 아니므로 프로그램에서 **__thiscall** 호출 규칙을 명시적으로 지정할 수 없습니다.

`vararg` 멤버 함수는 **__cdecl** 호출 규칙을 사용 합니다. 모든 함수 인수는 스택에 푸시되 고 **이** 포인터는 마지막 스택에 배치 됩니다.

이 호출 규칙은에 C++만 적용 되므로 C 이름 데코레이션 체계가 없습니다.

ARM 및 x64 컴퓨터에서 **__thiscall** 는 컴파일러에서 허용 되 고 무시 됩니다.

비정적 클래스 함수의 경우 함수가 아웃오브 라인으로 정의되면 호출 규칙 한정자를 아웃오브 라인 정의에서 지정하지 않아도 됩니다. 즉, 클래스 비정적 멤버 메서드의 경우 선언하는 동안 지정된 호출 규칙이 정의 시 가정됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)
