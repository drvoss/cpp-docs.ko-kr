---
title: "공유 (OpenMP) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Shared
dev_langs:
- C++
helpviewer_keywords:
- shared OpenMP clause
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 90491e6e8b415c79e21b4fa518f7e60327ac823e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="shared-openmp"></a>shared (OpenMP)
하나 이상의 변수 모든 스레드 간에 공유 되지 않아야 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
shared(var)  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `var`  
 공유를 하나 더 자세한 변수입니다. 둘 이상의 변수를 지정 하는 경우 변수 이름을 쉼표로 구분 합니다.  
  
## <a name="remarks"></a>설명  
 다른 스레드 간에 변수를 공유 방법은 [copyprivate](../../../parallel/openmp/reference/copyprivate.md) 절.  
  
 `shared` 다음과 같은 지시문에 적용 됩니다.  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 참조 [공유 2.7.2.4](../../../parallel/openmp/2-7-2-4-shared.md)합니다.  
  
## <a name="example"></a>예  
 참조 [개인](../../../parallel/openmp/reference/private-openmp.md) 사용 하는 예제에 대 한 `shared`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절](../../../parallel/openmp/reference/openmp-clauses.md)