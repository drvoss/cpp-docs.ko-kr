---
title: __declspec(dllimport)을 사용하여 함수 호출 가져오기
ms.date: 11/04/2016
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
ms.openlocfilehash: 1743cbba8c3046ef844f16be8e78d43c61f62606
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442514"
---
# <a name="importing-function-calls-using-__declspecdllimport"></a>__declspec(dllimport)을 사용하여 함수 호출 가져오기

다음 코드 예제에서는 **_declspec (dllimport)** 를 사용 하 여 DLL의 함수 호출을 응용 프로그램으로 가져오는 방법을 보여 줍니다. `func1`가 **main** 함수를 포함 하는 .exe 파일과는 별도의 DLL에 있는 함수 라고 가정 합니다.

이 코드에서는 **__declspec (dllimport)** 를 사용 하지 않습니다.

```
int main(void)
{
   func1();
}
```

컴파일러는 다음과 같은 코드를 생성 합니다.

```
call func1
```

그리고 링커는 호출을 다음과 같이 변환 합니다.

```
call 0x4000000         ; The address of 'func1'.
```

다른 DLL에 `func1` 있으면 링커가 `func1`의 주소를 알 수 없기 때문에이 작업을 직접 해결할 수 없습니다. 16 비트 환경에서 링커는 로더가 런타임에 올바른 주소를 사용 하 여 패치를 적용할 .exe 파일의 목록에이 코드 주소를 추가 합니다. 32 비트 및 64 비트 환경에서 링커는 주소를 알고 있는 썽크를 생성 합니다. 32 비트 환경에서 썽크는 다음과 같습니다.

```
0x40000000:    jmp DWORD PTR __imp_func1
```

여기서 `imp_func1`는 .exe 파일의 가져오기 주소 테이블에서 `func1` 슬롯에 대 한 주소입니다. 따라서 모든 주소가 링커에 알려집니다. 로더는 로드 시에만 .exe 파일의 가져오기 주소 테이블을 업데이트 하 여 모든 것이 제대로 작동 하도록 해야 합니다.

따라서 필요 하지 않은 경우에는 링커가 썽크를 생성 하지 않으므로 **dllimport (__declspec)** 를 사용 하는 것이 더 좋습니다. 썽크를 사용 하면 코드를 더 크게 만들 수 있습니다 (RISC 시스템에서 몇 가지 명령을 사용할 수 있음). 그러면 캐시 성능이 저하 될 수 있습니다. 컴파일러가 DLL에 있는 함수를 알려 주는 경우 간접 호출을 생성할 수 있습니다.

이제이 코드는 다음과 같습니다.

```
__declspec(dllimport) void func1(void);
int main(void)
{
   func1();
}
```

다음 명령을 생성 합니다.

```
call DWORD PTR __imp_func1
```

썽크는 없으며 `jmp` 명령이 없으므로 코드가 더 작고 더 빠릅니다.

반면에 DLL 내에서 함수를 호출 하는 경우 간접 호출을 사용 하지 않으려고 합니다. 함수의 주소를 이미 알고 있습니다. 간접 호출 전에 함수 주소를 로드 하 고 저장 하는 데 시간과 공간이 필요 하기 때문에 직접 호출은 항상 더 빠르고 작아집니다. Dll 자체 외부에서 DLL 함수를 호출 하는 경우에만 **__declspec (dllimport)** 를 사용 하려고 합니다. 해당 DLL을 빌드할 때 DLL 내 함수에서 **__declspec (dllimport)** 를 사용 하지 마십시오.

## <a name="see-also"></a>참고 항목

[애플리케이션으로 가져오기](importing-into-an-application.md)
