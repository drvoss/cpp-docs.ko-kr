---
title: 'hash_set:: const_reference (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_set::const_reference
dev_langs:
- C++
helpviewer_keywords:
- const_reference member [STL/CLR]
ms.assetid: 12e79114-91b6-4df8-9b5d-a92731d93f6a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c89d4e5017537253f808af0fbb587fff03348242
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hashsetconstreference-stlclr"></a>hash_set::const_reference(STL/CLR)
요소에 대한 상수 참조의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef value_type% const_reference;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 요소에 대 한 상수 참조를 설명 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_hash_set_const_reference.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    Myhash_set::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        Myhash_set::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set:: reference (STL/CLR)](../dotnet/hash-set-reference-stl-clr.md)   
 [hash_set::value_type(STL/CLR)](../dotnet/hash-set-value-type-stl-clr.md)