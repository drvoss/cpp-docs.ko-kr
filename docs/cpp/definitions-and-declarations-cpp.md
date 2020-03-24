---
title: 선언 및 정의 (C++)
ms.date: 11/04/2016
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
ms.openlocfilehash: 20683f3d2e12f7ffead573cbac46fdd4e106c383
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189379"
---
# <a name="definitions-and-declarations-c"></a>선언 및 정의 (C++)

**Microsoft 전용**

DLL 인터페이스는 시스템의 일부 프로그램에서 내보내지는 것으로 알려진 모든 항목 (함수 및 데이터)을 참조 합니다. 즉, **dllimport** 또는 **dllexport**로 선언 된 모든 항목입니다. DLL 인터페이스에 포함 된 모든 선언은 **dllimport** 또는 **dllexport** 특성을 지정 해야 합니다. 그러나 정의는 **dllexport** 특성만 지정 해야 합니다. 예를 들어, 다음 함수 정의는 컴파일러 오류를 생성합니다.

```
__declspec( dllimport ) int func() {   // Error; dllimport
                                       // prohibited on definition.
   return 1;
}
```

다음 코드도 오류를 생성합니다.

```
__declspec( dllimport ) int i = 10;  // Error; this is a definition.
```

그러나 다음은 올바른 구문입니다.

```
__declspec( dllexport ) int i = 10;  // Okay--export definition
```

**Dllexport** 를 사용 하는 경우 정의를 암시 하는 반면 **dllimport** 는 선언을 의미 합니다. 선언을 강제로 실행 하려면 **dllexport** 와 함께 **extern** 키워드를 사용 해야 합니다. 그렇지 않으면 정의가 암시 됩니다. 따라서 다음 예제는 올바릅니다.

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllExport int k; // These are both correct and imply a
DllImport int j;        // declaration.
```

다음 예제를 보면 위의 예제를 쉽게 이해할 수 있습니다.

```
static __declspec( dllimport ) int l; // Error; not declared extern.

void func() {
    static __declspec( dllimport ) int s;  // Error; not declared
                                           // extern.
    __declspec( dllimport ) int m;         // Okay; this is a
                                           // declaration.
    __declspec( dllexport ) int n;         // Error; implies external
                                           // definition in local scope.
    extern __declspec( dllimport ) int i;  // Okay; this is a
                                           // declaration.
    extern __declspec( dllexport ) int k;  // Okay; extern implies
                                           // declaration.
    __declspec( dllexport ) int x = 5;     // Error; implies external
                                           // definition in local scope.
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[dllexport, dllimport](../cpp/dllexport-dllimport.md)
