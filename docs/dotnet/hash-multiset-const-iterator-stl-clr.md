---
title: 'hash_multiset:: const_iterator (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::const_iterator
dev_langs:
- C++
helpviewer_keywords:
- const_iterator member [STL/CLR]
ms.assetid: a923b3f2-37c7-4e30-9b45-82ee2588f072
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 715784b9bd777e70c594adb47a88fd68509baeeb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultisetconstiterator-stlclr"></a>hash_multiset::const_iterator(STL/CLR)
제어되는 시퀀스에 대한 상수 반복기의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef T2 const_iterator;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 지정 되지 않은 형식의 개체를 설명 `T2` 제어 되는 시퀀스에 대 한 양방향 상수 반복기로 사용할 수 있는 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_hash_multiset_const_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Myhash_multiset::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
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
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::iterator(STL/CLR)](../dotnet/hash-multiset-iterator-stl-clr.md)