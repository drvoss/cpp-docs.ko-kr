---
title: "컴파일러 오류 C2461 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2461
dev_langs:
- C++
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e5e1593e37bd3a02897d023e308593e23d3d73b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2461"></a>컴파일러 오류 C2461
  
> '*클래스*': 생성자 구문에 정식 매개 변수가 없습니다.  
  
 클래스에 대 한 생성자는 모든 형식 매개 변수를 지정 하지 않습니다. 생성자의 선언에 정식 매개 변수 목록을 지정 해야 합니다. 목록은 비어 있을 수 있습니다.  
  
이 문제를 해결 하려면의 선언 뒤에 괄호 쌍을 추가 *클래스*:: **클래스*합니다.  
  
## <a name="example"></a>예  
  
다음 샘플 C2461를 수정 하는 방법을 보여 줍니다.  
  
```cpp  
// C2461.cpp  
// compile with: /c  
class C {  
   C::C;     // C2461  
   C::C();   // OK  
};  
```