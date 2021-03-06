---
title: "Invokehelper:: Invokehelper 생성자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
dev_langs:
- C++
helpviewer_keywords:
- InvokeHelper, constructor
ms.assetid: 0223c574-abc3-4fc0-99e6-38626ba79243
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e7016ce1c0a3e9c4a327f5db66903461e6748176
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="invokehelperinvokehelper-constructor"></a>InvokeHelper::InvokeHelper 생성자
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
explicit InvokeHelper(  
   TCallback callback  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `callback`  
 이벤트 처리기입니다.  
  
## <a name="remarks"></a>설명  
 InvokeHelper 클래스의 새 인스턴스를 초기화합니다.  
  
 `TCallback` 템플릿 매개 변수는 이벤트 처리기의 유형을 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [InvokeHelper 구조체](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)