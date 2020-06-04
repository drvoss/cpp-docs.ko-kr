---
title: 컴파일러 경고 C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: c125fa84119c62e3090611c9a841f46eee759711
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165212"
---
# <a name="compiler-warning-c4439"></a>컴파일러 경고 C4439

' function ': 시그니처에 관리 되는 형식이 있는 함수 정의에는 __clrcall 호출 규칙이 있어야 합니다.

컴파일러는 호출 규칙을 [__clrcall](../../cpp/clrcall.md)로 암시적으로 바꿉니다. 이 경고를 해결 하려면 `__cdecl` 또는 `__stdcall` 호출 규칙을 제거 합니다.

C4439는 항상 오류로 실행 됩니다. `#pragma warning` 또는 **/wd**를 사용 하 여이 경고를 해제할 수 있습니다. 자세한 내용은 [warning](../../preprocessor/warning.md) 또는 [/w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/Wall,/wd,/we,/wo,/Wv,/Wx (경고 수준)](../../build/reference/compiler-option-warning-level.md) 를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4439를 생성 합니다.

```cpp
// C4439.cpp
// compile with: /clr
void __stdcall f( System::String^ arg ) {}   // C4439
void __clrcall f2( System::String^ arg ) {}   // OK
void f3( System::String^ arg ) {}   // OK
```
