---
title: "컴파일러 경고 (수준 4) C4682 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4682
dev_langs:
- C++
helpviewer_keywords:
- C4682
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d367203113ea8fad20cd914d381b4c941856d6b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4682"></a>컴파일러 경고(수준 4) C4682
'parameter': 방향 매개 변수 특성을 지정하지 않았으므로 기본적으로 [in]이 사용됩니다.  
  
 특성을 가진 인터페이스 매개 변수에 대한 메서드에 방향 특성( [in](../../windows/in-cpp.md) 또는 [out](../../windows/out-cpp.md))이 없습니다. 매개 변수의 기본값은 in입니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.  
  
 다음 샘플에서는 C4682를 생성합니다.  
  
```  
// C4682.cpp  
// compile with: /W4  
#pragma warning(default : 4682)  
#include <windows.h>  
[module(name="MyModule")];  
  
[ library_block, object, uuid("c54ad59d-d516-41dd-9acd-afda17565c2b") ]  
__interface IMyIface : IUnknown  
{  
   HRESULT f1(int i, int *pi); // C4682  
   // try the following line  
   // HRESULT f1([in] int i, [in] int *pi);  
};  
  
int main()  
{  
}  
```