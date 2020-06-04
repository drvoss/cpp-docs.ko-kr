---
title: __declspec(dllimport)을 사용하여 함수 호출 가져오기
description: DLL 데이터 및 함수를 호출할 때 __declspec(dllimport)를 사용하는 방법 및 이유.
ms.date: 05/03/2020
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
ms.openlocfilehash: 515fbdb2824c1eaf41e822adeae1a16d3072eec4
ms.sourcegitcommit: 8a01ae145bc65f5bc90d6e47b4a1bdf47b073ee7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82765723"
---
# <a name="importing-function-calls-using-__declspecdllimport"></a>`__declspec(dllimport)`을 사용해 함수 호출 가져오기

**`__declspec(dllimport)`** 을 사용하여 호출에 주석을 달면 호출이 더 빨라질 수 있습니다. **`__declspec(dllimport)`** 은 내보낸 DLL 데이터에 액세스할 때 항상 필요합니다.

## <a name="import-a-function-from-a-dll"></a>DLL에서 함수 가져오기

다음 코드 예제에서는 **`__declspec(dllimport)`** 을 사용하여 DLL의 함수 호출을 애플리케이션으로 가져오는 방법을 보여줍니다. `func1`은 **main** 함수를 포함하는 실행 파일과는 별도의 DLL에 있는 함수라고 가정합니다.

이 코드에서 **`__declspec(dllimport)`** 이 없는 경우:

```C
int main(void)
{
   func1();
}
```

컴파일러는 다음과 같은 코드를 생성합니다.

```asm
call func1
```

그리고 링커는 호출을 다음과 같이 변환합니다.

```asm
call 0x4000000         ; The address of 'func1'.
```

다른 DLL에 `func1`이 있으면 링커는 `func1`의 주소를 알 수 없기 때문에 이 주소를 직접 확인할 수 없습니다. 32비트 및 64비트 환경에서 링커는 알려진 주소에 썽크를 생성합니다. 32비트 환경에서 썽크는 다음과 같습니다.

```asm
0x40000000:    jmp DWORD PTR __imp_func1
```

여기서 `__imp_func1`은 실행 파일의 가져오기 주소 테이블에 있는 `func1` 슬롯의 주소입니다. 이러한 모든 주소는 링커에게 알려집니다. 모든 것이 제대로 작동하도록 로더는 로드 시 실행 파일의 가져오기 주소 테이블을 업데이트하기만 하면 됩니다.

따라서 **`__declspec(dllimport)`** 을 사용하는 것이 좋습니다. 썽크가 필요 없는 경우에는 링커가 썽크를 생성하지 않기 때문입니다. 썽크로 인해 코드가 더 커져(RISC 시스템에서는 몇 가지 명령일 수 있음) 캐시 성능이 저하될 수 있습니다. 컴파일러에게 이 함수가 DLL에 있음을 알려주면 컴파일러가 간접 호출을 생성할 수 있습니다.

따라서 이 코드는

```C
__declspec(dllimport) void func1(void);
int main(void)
{
   func1();
}
```

이러한 명령을 생성합니다.

```asm
call DWORD PTR __imp_func1
```

썽크가 없고 `jmp` 명령이 없으므로 코드가 더 작고 더 빠릅니다. 전체 프로그램 최적화를 사용하여 **`__declspec(dllimport)`** 없이 동일한 효과를 얻을 수도 있습니다. 자세한 내용은 [/GL(전체 프로그램 최적화)](reference/gl-whole-program-optimization.md)을 참조하세요.

DLL 내 함수 호출의 경우 사용자는 간접 호출을 사용하지 않아도 되기를 바랍니다. 링커는 함수의 주소를 이미 알고 있습니다. 간접 호출 전에 함수의 주소를 로드하고 저장하는 데 추가 시간 및 공간이 필요합니다. 직접 호출은 항상 더 빠르고 더 작아야 합니다. 사용자는 DLL 자체의 외부에서 DLL 함수를 호출하는 경우에만 **`__declspec(dllimport)`** 를 사용하기를 원합니다. DLL을 빌드할 때 해당 DLL 내 함수에 **`__declspec(dllimport)`** 을 사용하지 마세요.

## <a name="see-also"></a>참조

[애플리케이션으로 가져오기](importing-into-an-application.md)
