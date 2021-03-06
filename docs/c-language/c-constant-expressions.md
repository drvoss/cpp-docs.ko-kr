---
title: "C 상수 식 | Microsoft Docs"
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
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 596f558ea5c22f1850800d95b0d4ad0b5edd6a8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="c-constant-expressions"></a>C 상수 식
상수 식은 런타임이 아닌 컴파일 타임에 계산되며, 상수를 사용할 수 있는 모든 위치에서 사용될 수 있습니다. 상수 식은 해당 형식에 대한 표현 가능한 값의 범위에 있는 상수로 계산되어야 합니다. 상수 식의 피연산자는 정수 상수, 문자 상수, 부동 소수점 상수, 열거형 상수, 형식 캐스트, `sizeof` 식 및 기타 상수 식일 수 있습니다.  
  
## <a name="syntax"></a>구문  
 *constant-expression*:  
 *conditional-expression*  
  
 *conditional-expression*:  
 *logical-OR-expression*  
  
 *logical-OR-expression* **?**  *expression* **:**  *conditional-expression*  
  
 *expression*:  
 *assignment-expression*  
  
 *expression* **,**  *assignment-expression*  
  
 *assignment-expression*:  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator*: 다음 중 하나  
 **= \*= /= %= += -= <\<= >>= &= ^= &#124;=**  
  
 구조체 선언자, 열거자, 직접 선언자, 직접 추상 선언자 및 레이블 문의 비단말에는 *onstant-expression* 비단말이 포함됩니다.  
  
 정수 상수 식은 구조체의 비트 필드 멤버 크기, 열거형 상수의 값, 배열의 크기 또는 **case** 상수의 값을 지정하는 데 사용해야 합니다.  
  
 전처리기 지시문에서 사용된 상수 식에는 제한이 추가로 적용됩니다. 따라서 이러한 상수 식을 "제한된 상수 식"이라고 합니다. 제한된 상수 식은 `sizeof` 식, 열거형 상수, 모든 형식에 대한 형식 캐스트 또는 부동 형식 상수를 포함할 수 없습니다. 그러나 특수 상수 식인 `defined (`*identifier*`)`를 포함할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [피연산자 및 식](../c-language/operands-and-expressions.md)