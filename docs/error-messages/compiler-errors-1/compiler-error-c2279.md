---
title: "컴파일러 오류 C2279 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2279
dev_langs:
- C++
helpviewer_keywords:
- C2279
ms.assetid: 1b5c88ef-2336-49b8-9ddb-d61f97c73e14
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e140bc7b9cf417f5c18d77444ac3c90c478829f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2279"></a>컴파일러 오류 C2279
형식 정의 선언에 예외 사양이 나타날 수 없습니다.  
  
 아래 **/Za**, [예외 사양](../../cpp/exception-specifications-throw-cpp.md) 형식 정의 선언에 사용할 수 없습니다.  
  
 다음 샘플에서는 C2279 오류가 생성 됩니다.  
  
```  
// C2279.cpp  
// compile with: /Za /c  
typedef int (*xy)() throw(...);   // C2279  
typedef int (*xyz)();   // OK  
```