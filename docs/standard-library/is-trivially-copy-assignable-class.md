---
title: "is_trivially_copy_assignable 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8fe1f72d609c30dbd7abf9fb0d0ca6803d90a29
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable 클래스
형식에 Trivial 복사 할당 연산자가 있는지 여부를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Ty>
struct is_trivially_copy_assignable;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 형식 `T`가 Trivial 복사 할당 연산자를 가진 클래스인 경우 true이고 그렇지 않은 경우 false입니다.  
  
 `T` 클래스에 대한 할당 생성자는 암시적으로 제공되고, `T` 클래스에 가상 함수가 없고, `T` 클래스에 가상 기본이 없고, 클래스 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 대입 연산자가 있으며, 클래스 배열 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 대입 연산자가 있는 경우 trivial입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)



