---
title: __declspec(dllimport)을 사용하여 함수 호출 가져오기
description: DLL 데이터 및 함수를 호출할 때 __declspec (dllimport)를 사용 하는 방법 및 이유
ms.date: 05/03/2020
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
ms.openlocfilehash: 515fbdb2824c1eaf41e822adeae1a16d3072eec4
ms.sourcegitcommit: 8a01ae145bc65f5bc90d6e47b4a1bdf47b073ee7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82765723"
---
# <a name="importing-function-calls-using-__declspecdllimport"></a>를 사용 하 여 함수 호출 가져오기`__declspec(dllimport)`

를 **`__declspec(dllimport)`** 사용 하 여 호출에 주석을 추가 하면 더 빠르게 만들 수 있습니다. **`__declspec(dllimport)`** 는 내보낸 DLL 데이터에 액세스 하는 데 항상 필요 합니다.

## <a name="import-a-function-from-a-dll"></a>DLL에서 함수 가져오기

다음 코드 예제에서는를 사용 **`__declspec(dllimport)`** 하 여 DLL의 함수 호출을 응용 프로그램으로 가져오는 방법을 보여 줍니다. `func1` 는 **main** 함수를 포함 하는 실행 파일과는 별도의 DLL에 있는 함수 라고 가정 합니다.

을 **`__declspec(dllimport)`** 사용 하지 않는 경우 다음 코드가 제공 됩니다.

```C
int main(void)
{
   func1();
}
```

컴파일러는 다음과 같은 코드를 생성 합니다.

```asm
call func1
```

그리고 링커는 호출을 다음과 같이 변환 합니다.

```asm
call 0x4000000         ; The address of 'func1'.
```

가 `func1` 다른 DLL에 있는 경우 링커에서는의 `func1` 주소가 무엇 인지 알 수 없기 때문에이 주소를 직접 확인할 수 없습니다. 32 비트 및 64 비트 환경에서 링커는 알려진 주소에서 썽크를 생성 합니다. 32 비트 환경에서 썽크는 다음과 같습니다.

```asm
0x40000000:    jmp DWORD PTR __imp_func1
```

다음 `__imp_func1` 은 실행 파일의 가져오기 `func1` 주소 테이블에서 슬롯에 대 한 주소입니다. 이러한 모든 주소는 링커에 알려집니다. 로더는 로드 시 실행 파일의 가져오기 주소 테이블을 업데이트 하 여 모든 것이 제대로 작동 하도록 해야 합니다.

이러한 이유로를 사용 **`__declspec(dllimport)`** 하는 것이 더 좋습니다. 링커가 필요 하지 않은 경우에는 썽크를 생성 하지 않기 때문입니다. 썽크를 사용 하면 코드를 더 크게 만들 수 있습니다 (RISC 시스템에서 몇 가지 명령을 사용할 수 있음). 그러면 캐시 성능이 저하 될 수 있습니다. 컴파일러가 DLL에 있는 함수를 알려 주는 경우 간접 호출을 생성할 수 있습니다.

이제이 코드는 다음과 같습니다.

```C
__declspec(dllimport) void func1(void);
int main(void)
{
   func1();
}
```

다음 명령을 생성 합니다.

```asm
call DWORD PTR __imp_func1
```

썽크는 없으며 `jmp` 명령이 없으므로 코드가 더 작고 빠릅니다. 또한 전체 프로그램 최적화를 사용 하지 않고도 **`__declspec(dllimport)`** 동일한 효과를 얻을 수 있습니다. 자세한 내용은 [/GL(전체 프로그램 최적화)](reference/gl-whole-program-optimization.md)을 참조하세요.

DLL 내에서 함수 호출의 경우 간접 호출을 사용 하지 않으려고 합니다. 링커에서 함수 주소를 이미 알고 있습니다. 간접 호출 전에 함수 주소를 로드 하 고 저장 하는 데 추가 시간과 공간이 필요 합니다. 직접 호출은 항상 더 빠르고 작아야 합니다. Dll 자체 외부에서 DLL **`__declspec(dllimport)`** 함수를 호출 하는 경우에만를 사용 합니다. Dll을 **`__declspec(dllimport)`** 빌드할 때 dll 내에서 함수를 사용 하지 마세요.

## <a name="see-also"></a>참고 항목

[응용 프로그램으로 가져오기](importing-into-an-application.md)
