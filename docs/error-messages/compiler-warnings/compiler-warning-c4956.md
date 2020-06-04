---
title: 컴파일러 경고 C4956
ms.date: 11/04/2016
f1_keywords:
- C4956
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
ms.openlocfilehash: 474bdfa6eb670f39a2876b0c1490e7254cf216e7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164907"
---
# <a name="compiler-warning-c4956"></a>컴파일러 경고 C4956

> '*type*':이 형식은 확인할 수 없습니다.

## <a name="remarks"></a>설명

이 경고는 [/clr: safe](../../build/reference/clr-common-language-runtime-compilation.md) 가 지정되고 코드에 확인할 수 없는 형식이 포함된 경우 생성됩니다. **/Clr: safe** 컴파일러 옵션은 visual studio 2015에서 더 이상 사용 되지 않으며 visual studio 2017에서는 지원 되지 않습니다.

자세한 내용은 [순수형 및 안정형 코드C++(/cli)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)를 참조 하세요.

이 경고는 오류로 발생하며 [warning](../../preprocessor/warning.md) pragma 또는 [/wd](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션과 함께 사용하지 않도록 설정할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4956을 생성합니다.

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```
