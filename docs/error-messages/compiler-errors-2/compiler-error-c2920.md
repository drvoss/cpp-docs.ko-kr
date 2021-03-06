---
title: "컴파일러 오류 C2920 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2920
dev_langs:
- C++
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba5a7706dc4607897cb2ef71f2072209e0516f53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2920"></a>컴파일러 오류 C2920
재정의: 'class' : 클래스 템플릿 또는 제네릭이(가) 이미 'type'(으)로 선언되었습니다.  
  
 제네릭 또는 템플릿 클래스에 동일하지 않은 선언이 여러 개 있습니다. 이 오류를 해결하려면 형식에 따라 다른 이름을 사용하거나 형식 이름의 재정의를 제거하세요.  
  
 다음 샘플에서는 C2920을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2920.cpp  
// compile with: /c  
typedef int TC1;  
template <class T>   
struct TC1 {};   // C2920  
struct TC2 {};   // OK - fix by using a different name  
```  
  
 C2920은 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2920b.cpp  
// compile with: /clr /c  
typedef int GC1;  
generic <class T>   
ref struct GC1 {};   // C2920  
ref struct GC2 {};   // OK - fix by using a different name  
```