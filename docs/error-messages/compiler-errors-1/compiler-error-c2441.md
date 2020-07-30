---
title: 컴파일러 오류 C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: aa55392e9f58caa4292cf5f96ef97f65a53bf913
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207955"
---
# <a name="compiler-error-c2441"></a>컴파일러 오류 C2441

> '*variable*': __declspec (process)로 선언 된 기호는/clr: pure 모드에서 const 여야 합니다.

## <a name="remarks"></a>설명

**/Clr: pure** 및 **/clr: safe** 컴파일러 옵션은 visual studio 2015에서 더 이상 사용 되지 않으며 visual studio 2017에서는 지원 되지 않습니다.

기본적으로 변수는 **/clr: pure**아래의 응용 프로그램 도메인 별로 있습니다. `__declspec(process)` **/Clr: pure** 로 표시 된 변수는 한 응용 프로그램 도메인에서 수정 되 고 다른 응용 프로그램 도메인에서 읽을 경우 오류가 발생 하기 쉽습니다.

따라서 컴파일러는 프로세스 당 변수를 **`const`** **/clr: pure**아래에 적용 하므로 모든 응용 프로그램 도메인에서 읽기 전용으로 설정 됩니다.

자세한 내용은 [process](../../cpp/process.md) and [/Clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C2441를 생성 합니다.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```
