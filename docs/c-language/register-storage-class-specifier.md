---
title: "register 저장소 클래스 지정자 | Microsoft Docs"
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
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7faced0e92db07a937237a82acf6f0fb9ecd6810
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="register-storage-class-specifier"></a>register 저장소 클래스 지정자
**Microsoft 전용**  
  
 Microsoft C/C++ 컴파일러는 레지스터 변수에 대한 사용자 요청을 고려하지 않습니다. 하지만 이식성을 위해 **register** 키워드와 연결된 다른 모든 의미 체계는 컴파일러에서 적용됩니다. 예를 들어 단항 address-of 연산자(**&**)를 register 개체에 적용할 수 없거나 배열에서 **register** 키워드를 사용할 수 없습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [내부 수준 선언에 대한 저장소 클래스 지정자](../c-language/storage-class-specifiers-for-internal-level-declarations.md)