---
title: "심각한 오류 C1311 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a0d798ea53ebbbfe850b77b4b8176b35e2040ed8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1311"></a>심각한 오류 C1311
COFF 형식은 'var' 숫자 바이트의 주소를 사용으로 정적으로 초기화할 수 없습니다.  
  
 해당 형식의 4 바이트 보다 작은 저장소가 변수에 값을 갖는 컴파일 타임에 알려지지 않은 주소를 정적으로 할당할 수 없습니다.  
  
 이 오류 코드는 다른 방법에 유효한 c + +입니다.  
  
 다음 코드 예제는 C1311을 일으킬 수 있는 한 가지 조건을 보여줍니다.  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```