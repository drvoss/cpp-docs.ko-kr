---
title: 'hash_set:: equal_range (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_set::equal_range
dev_langs:
- C++
helpviewer_keywords:
- equal_range member [STL/CLR]
ms.assetid: 502af4c5-f71e-44cf-a180-21e9da4b50ff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5ece51c952cacb629a2d0ce2fdecc104a54c7cf6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hashsetequalrange-stlclr"></a>hash_set::equal_range(STL/CLR)
지정된 키와 일치하는 범위를 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### <a name="parameters"></a>매개 변수  
 key  
 검색할 키 값입니다.  
  
## <a name="remarks"></a>설명  
 멤버 함수는 한 쌍의 반복기를 반환 `cliext::pair<iterator, iterator>(` [hash_set:: lower_bound (STL/CLR)](../dotnet/hash-set-lower-bound-stl-clr.md) `(key),` [hash_set:: upper_bound (STL/CLR)](../dotnet/hash-set-upper-bound-stl-clr.md)`(key))`합니다. 지정된 된 키와 일치 하는 제어 된 시퀀스의 현재 요소의 범위를 확인 하려면 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_hash_set_equal_range.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
typedef Myhash_set::pair_iter_iter Pairii;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" {0}", *pair1.first);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
equal_range(L'x') empty = True  
 b  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set:: count (STL/CLR)](../dotnet/hash-set-count-stl-clr.md)   
 [hash_set:: find (STL/CLR)](../dotnet/hash-set-find-stl-clr.md)   
 [hash_set:: lower_bound (STL/CLR)](../dotnet/hash-set-lower-bound-stl-clr.md)   
 [hash_set::upper_bound(STL/CLR)](../dotnet/hash-set-upper-bound-stl-clr.md)