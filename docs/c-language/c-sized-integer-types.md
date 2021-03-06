---
title: "C 크기 조정 정수 형식 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 609d932b92d40fd4e080d12d13a8872417b56440
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="c-sized-integer-types"></a>C 크기 조정 정수 형식
**Microsoft 전용**  
  
 Microsoft C는 크기가 지정된 정수 형식을 지원합니다. __int*n* 형식 지정자를 사용하여 8비트, 16비트, 32비트 또는 64비트 정수 변수를 선언할 수 있습니다. 여기서 *n*은 정수 변수의 비트 크기입니다. *n*의 값은 8, 16, 32 또는 64입니다. 다음 예제에서는 네 가지 형식의 크기가 지정된 정수 각각의 변수 하나를 선언합니다.  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 처음 세 가지 형식의 크기가 지정된 정수는 크기가 같은 ANSI 형식에 대한 동의어이며 여러 플랫폼에서 동일하게 동작하는 이식 가능한 코드 작성에 유용합니다. __int8 데이터 형식은 char 형식과 동의어이고, \__int16은 short 형식과 동의어이며, \__int32는 int 형식과 동의어입니다. \__int64 형식에는 해당 ANSI 유형이 없습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [기본 형식의 저장소](../c-language/storage-of-basic-types.md)