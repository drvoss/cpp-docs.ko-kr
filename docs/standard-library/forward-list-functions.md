---
title: "&lt;forward_list&gt; 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: ce66354d2377e52043830925c3f4f880de996663
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt; 함수
||  
|-|  
|[swap](#swap)|  
  
##  <a name="swap"></a>  swap  
 두 정방향 목록의 요소를 교환합니다.  
  
```
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|`forward_list` 형식의 개체입니다.|  
|`right`|`forward_list` 형식의 개체입니다.|  
  
### <a name="remarks"></a>설명  
 이 템플릿 함수는 `left.swap(right)`를 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [<forward_list>](../standard-library/forward-list.md)



