---
title: 링커 도구 경고 LNK4092
ms.date: 11/04/2016
f1_keywords:
- LNK4092
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
ms.openlocfilehash: 706ab843f4b079b507033af76a7f407816fce820
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183360"
---
# <a name="linker-tools-warning-lnk4092"></a>링커 도구 경고 LNK4092

쓰기 가능한 공유 섹션 ' section '에 재배치가 있습니다. 이미지가 올바르게 실행 되지 않을 수 있습니다.

링커가 잠재적으로 심각한 문제를 경고 하는 공유 섹션이 있을 때마다이 경고를 내보냅니다.

여러 프로세스 간에 데이터를 공유 하는 한 가지 방법은 섹션을 "공유 됨"으로 표시 하는 것입니다. 그러나 섹션을 공유로 표시 하면 문제가 발생할 수 있습니다. 예를 들어 공유 데이터 섹션에 다음과 같은 선언을 포함 하는 DLL이 있습니다.

```
int var = 1;
int *pvar = &var;
```

해당 값이 DLL이 메모리에 로드 된 위치에 따라 달라 지므로 링커는 `pvar`을 확인할 수 없습니다. 따라서 DLL에 재배치 레코드가 삽입 됩니다. DLL이 메모리에 로드 되 면 `var`의 주소를 확인 하 고 할당할 `pvar` 있습니다. 다른 프로세스가 동일한 DLL을 로드 하지만 동일한 주소에 로드할 수 없는 경우 두 번째 프로세스에 대 한 `var` 주소의 재배치가 업데이트 되 고 첫 번째 프로세스의 주소 공간은 잘못 된 주소를 가리킵니다.
