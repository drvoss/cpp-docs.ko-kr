---
title: __declspec(dllimport)을 사용하여 데이터 가져오기
ms.date: 11/04/2016
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: c9dce798572a91bcb9721f022393abb669970131
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440453"
---
# <a name="importing-data-using-__declspecdllimport"></a>__declspec(dllimport)을 사용하여 데이터 가져오기

데이터의 경우 **dllimport (__declspec)** 를 사용 하는 것은 간접 참조 계층을 제거 하는 편리한 항목입니다. DLL에서 데이터를 가져올 때 가져오기 주소 테이블을 계속 진행 해야 합니다. **__Declspec (dllimport)** 이전에는 DLL에서 내보낸 데이터에 액세스할 때 추가 수준의 간접 참조를 수행 해야 했습니다.

```
// project.h
#ifdef _DLL   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

그런 다음에서 데이터를 내보냅니다. DEF 파일:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

그리고 DLL 외부에서 액세스 합니다.

```
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

데이터를 **__declspec (dllimport)** 로 표시 하면 컴파일러가 자동으로 간접 코드를 생성 합니다. 더 이상 위의 단계를 걱정 하지 않아도 됩니다. 앞에서 설명한 것 처럼 DLL을 빌드할 때 데이터에 대해 **dllimport (__declspec)** 선언을 사용 하지 마십시오. DLL 내의 함수는 가져오기 주소 테이블을 사용 하 여 데이터 개체에 액세스 하지 않습니다. 따라서 추가 수준의 간접 참조가 표시 되지 않습니다.

DLL에서 데이터를 자동으로 내보내려면 다음 선언을 사용 합니다.

```
__declspec(dllexport) ULONG ulDataInDLL;
```

## <a name="see-also"></a>참고 항목

[애플리케이션으로 가져오기](importing-into-an-application.md)
