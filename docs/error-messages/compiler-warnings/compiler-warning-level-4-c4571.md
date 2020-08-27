---
title: 컴파일러 경고(수준 4) C4571
description: Microsoft c + + 컴파일러 경고 C4571를 문서화 합니다.
ms.date: 08/24/2020
f1_keywords:
- C4571
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
ms.openlocfilehash: 35f2b30a8ab7cfcc27ed7aae3aedd9bc81efacc8
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898553"
---
# <a name="compiler-warning-level-4-c4571"></a>컴파일러 경고(수준 4) C4571

> 알림: `catch(...)` Visual C++ 7.1 이후 의미 체계가 변경 되었습니다. 구조적 예외 (SEH)는 더 이상 catch 되지 않습니다.

컴파일러 옵션을 지정 하면 모든 블록에 대해 C4571이 생성 됩니다 `catch(...)` **`/EHs`** .

## <a name="remarks"></a>설명

**`/EHs`** 컴파일러 옵션을 지정 하는 경우 `catch(...)` 블록은 구조적 예외를 catch 하지 않습니다. (예: 0으로 나누기 또는 null 포인터 예외입니다.) `catch(...)` 블록은 명시적으로 throw 된 c + + 예외를 catch 합니다. 자세한 내용은 [예외 처리](../../cpp/exception-handling-in-visual-cpp.md)를 참조하세요.

기본적으로 이 경고는 해제되어 있습니다.  블록을 사용 하 여 컴파일할 때 구조적 예외를 catch 하지 않도록이 경고를 설정 **`/EHs`** `catch (...)` 합니다. 자세한 내용은 [기본적으로 해제 되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조 하세요.

다음 방법 중 하나로 C4571를 해결할 수 있습니다.

- **`/EHa`** `catch(...)` 블록에서 구조적 예외를 catch 하려면를 사용 하 여 컴파일합니다.

- 블록에서 구조화 된 예외를 catch 하지 `catch(...)` 않고 여전히 블록을 사용 하려면 C4571를 사용 하도록 설정 하지 마세요 `catch(...)` .  구조적 예외 처리 키워드 ( **`__try`** , 및)를 사용 하 여 구조적 예외를 여전히 catch 할 수 있습니다 **`__except`** **`__finally`** .  그러나를 사용 하 여 컴파일된 경우에 **`/EHs`** 는 SEH 예외가 발생할 때가 아닌 c + + 예외가 throw 될 때만 소멸자가 호출 됩니다.

- `catch(...)`블록을 특정 c + + 예외에 대 한 catch 블록으로 바꾸고 필요에 따라 c + + 예외 처리 ( **`__try`** , 및)를 중심으로 구조적 예외 처리를 추가 **`__except`** **`__finally`** 합니다.   자세한 내용은 [구조적 예외 처리 (C/c + +)](../../cpp/structured-exception-handling-c-cpp.md) 및 [ `/EH` (예외 처리 모델)](../../build/reference/eh-exception-handling-model.md)를 참조 하세요.

## <a name="example"></a>예

다음 샘플에서는 C4571를 생성 합니다.

```cpp
// C4571.cpp
// compile with: /EHs /W4 /c
#pragma warning(default : 4571)
int main() {
   try {
      int i = 0, j = 1;
      j /= i;   // this will throw a SE (divide by zero)
   }
   catch(...) {}   // C4571 warning
}
```
