---
title: "이중 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.dual
dev_langs:
- C++
helpviewer_keywords:
- dual attribute
ms.assetid: 5d4a9069-d819-42cd-ba56-bbcda17157d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e5ea633ca0d6e9f654e5462f8cebded18d9b9f99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dual"></a>dual
.Idl 파일에는 이중 인터페이스로 인터페이스를 배치합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[dual]  
  
```  
  
## <a name="remarks"></a>설명  
 경우는 **이중** c + + 특성 인터페이스 앞, 생성된 된.idl 파일에 있는 라이브러리 블록 안에 배치 될 인터페이스를 수행 합니다.  
  
## <a name="example"></a>예  
 다음 코드는를 사용 하는 특성 블록 **이중** 인터페이스 정의 하기 전에:  
  
```  
// cpp_attr_ref_dual.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), dual]  
  
__interface IStatic : IDispatch   
{  
   HRESULT Func1(int i);  
   [   propget,   
      id(1),   
      bindable,   
      displaybind,   
      defaultbind,   
      requestedit  
   ]   
   HRESULT P1([out, retval] long *nSize);  
   [   propput,   
      id(1),   
      bindable,   
      displaybind,   
      defaultbind,   
      requestedit  
   ]   
   HRESULT P1([in] long nSize);      
};  
  
[cpp_quote("#include file.h")];  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|`interface`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|**dispinterface**|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [용도별 특성](../windows/attributes-by-usage.md)   
 [사용자 지정](../windows/custom-cpp.md)   
 [dispinterface](../windows/dispinterface.md)   
 [object](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   
