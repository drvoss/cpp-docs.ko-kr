---
title: "컴파일러 오류 C2378 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2378
dev_langs:
- C++
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6cfaa376a3576933d47c737e0e1c6889d7bde666
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2378"></a>컴파일러 오류 C2378
'identifier': 재정의. 형식 정의를 사용하여 기호를 오버로드할 수 없습니다.  
  
 식별자가 `typedef`로 다시 정의되었습니다.  
  
 다음 샘플에서는 C2378을 생성합니다.  
  
```  
// C2378.cpp  
// compile with: /c  
int i;  
typedef int i;   // C2378  
typedef int b;   // OK  
```