---
title: 리소스 정리
description: 구조화 된 예외 처리를 위해 종료 처리기에서 리소스를 해제 하는 방법입니다.
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
ms.openlocfilehash: dae92a515db25b9985a890d7d08cc213f88ecfea
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898439"
---
# <a name="cleaning-up-resources"></a>리소스 정리

종료 처리기를 실행 하는 동안 종료 처리기가 호출 되기 전에 획득 한 리소스를 알 수 없습니다. 모든 리소스 **`__try`** 를 획득 하기 전에 문 블록이 중단 되었을 수 있으므로 모든 리소스가 열리지 않습니다.

안전을 위해서는 종료 처리 정리를 진행 하기 전에 어떤 리소스가 열려 있는지 확인 해야 합니다. 권장 절차는 다음과 같습니다.

1. 핸들을 NULL로 초기화합니다.

1. **`__try`** 문 블록에서 리소스를 가져옵니다. 리소스를 획득 하면 핸들이 양수 값으로 설정 됩니다.

1. **`__finally`** 문 블록에서 해당 핸들 또는 플래그 변수가 0이 아니거나 NULL이 아닌 각 리소스를 해제 합니다.

## <a name="example"></a>예

예를 들어 다음 코드에서는 종료 처리기를 사용 하 여 세 개의 파일을 닫고 메모리 블록을 해제 합니다. 이러한 리소스는 문 블록에서 가져온 것 **`__try`** 입니다. 리소스를 정리 하기 전에 코드는 먼저 리소스를 가져왔는지 확인 합니다.

```cpp
// exceptions_Cleaning_up_Resources.cpp
#include <stdlib.h>
#include <malloc.h>
#include <stdio.h>
#include <windows.h>

void fileOps() {
   FILE  *fp1 = NULL,
         *fp2 = NULL,
         *fp3 = NULL;
   LPVOID lpvoid = NULL;
   errno_t err;

   __try {
      lpvoid = malloc( BUFSIZ );

      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );
      err = fopen_s(&fp3, "CARS.DAT", "w+" );
   }
   __finally {
      if ( fp1 )
         fclose( fp1 );
      if ( fp2 )
         fclose( fp2 );
      if ( fp3 )
         fclose( fp3 );
      if ( lpvoid )
         free( lpvoid );
   }
}

int main() {
   fileOps();
}
```

## <a name="see-also"></a>참조

[종료 처리기 작성](../cpp/writing-a-termination-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)
