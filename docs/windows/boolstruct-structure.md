---
title: "BoolStruct 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
dev_langs:
- C++
helpviewer_keywords:
- BoolStruct structure
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7daa7527c8eea2cfca3b8933b9c3e1f042883e2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="boolstruct-structure"></a>BoolStruct 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct BoolStruct;  
```  
  
## <a name="remarks"></a>설명  
 BoolStruct 구조체 ComPtr 인터페이스의 개체 수명을 관리 하 고 있는지 여부를 정의 합니다. BoolStruct 내부적으로 사용 되는 [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) 연산자입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[BoolStruct::Member 데이터 멤버](../windows/boolstruct-member-data-member.md)|지정 하는 [ComPtr](../windows/comptr-class.md) 되었거나 인터페이스의 개체 수명 관리 되지 않습니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `BoolStruct`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtr::operator Microsoft::WRL::Details::BoolType 연산자](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)