---
title: 리소스 컴파일러 오류 RC2101
ms.date: 11/04/2016
f1_keywords:
- RC2101
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
ms.openlocfilehash: 3fb576758e447c54e4ddfe7ddb024a1fd35a65f2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191654"
---
# <a name="resource-compiler-error-rc2101"></a>리소스 컴파일러 오류 RC2101

전처리 된 RC 파일의 지시문이 잘못 되었습니다.

리소스 컴파일러 파일에 **#pragma** 지시문이 포함 되어 있습니다.

리소스 컴파일러가 포함 파일을 처리할 때 정의 하는 RC_INVOKED 상수를 사용 하 여 **#ifndef** 전처리기 지시문을 사용 합니다. RC_INVOKED 상수가 정의 될 때 처리 되지 않은 코드 블록 안에 **#pragma** 지시문을 추가 합니다. 블록의 코드는 리소스 컴파일러가 아니라 C/C++ 컴파일러에 의해서만 처리 됩니다. 다음 샘플 코드에서는이 기법을 보여 줍니다.

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma** 전처리기 지시문은에서 의미가 없습니다. RC 파일. **#Include** 전처리기 지시문은에서 자주 사용 됩니다. 헤더 파일 (프로젝트 기반 사용자 지정 헤더 파일 또는 제품 중 하나를 사용 하 여 Microsoft에서 제공 하는 표준 헤더 파일)을 포함 하는 RC 파일 이러한 포함 파일 중 일부에는 **#pragma** 지시문이 포함 되어 있습니다. 헤더 파일에는 하나 이상의 다른 헤더 파일이 포함 될 수 있기 때문에 잘못 된 **#pragma** 지시어를 포함 하는 파일은 바로 명확 하지 않을 수 있습니다.

**#Ifndef** RC_INVOKED 기술은 프로젝트 기반 헤더 파일의 헤더 파일을 포함 하 여 제어할 수 있습니다.
