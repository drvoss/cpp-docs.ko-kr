---
title: 'multiset:: find (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::multiset::find
dev_langs:
- C++
helpviewer_keywords:
- find member [STL/CLR]
ms.assetid: 162c9002-fb34-44f9-8e42-6bacecd0ebbc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 84a04f31c0833222d4bbef598a463d35efc816fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="multisetfind-stlclr"></a>multiset::find(STL/CLR)
지정된 키와 일치하는 요소를 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>매개 변수  
 key  
 검색할 키 값입니다.  
  
## <a name="remarks"></a>설명  
 동일 하 게 정렬 된 제어 되는 시퀀스에 요소가 하나 이상 있으면 `key`, 이러한 요소 중 하나를 지정 하는 반복기를 반환 하는 멤버 함수, 그렇지 않으면 반환 [multiset:: end (STL/CLR)](../dotnet/multiset-end-stl-clr.md) `()`. 지정된 된 키와 일치 하는 제어 된 시퀀스의 현재 요소를 찾을 수 사용 합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_multiset_find.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
find A = False  
find b = b  
find C = False  
```  
  
## <a name="description"></a>설명  
 `find` 발견 하는 여러 가지 요소는 보장 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset:: equal_range (STL/CLR)](../dotnet/multiset-equal-range-stl-clr.md)   
 [multiset:: lower_bound (STL/CLR)](../dotnet/multiset-lower-bound-stl-clr.md)   
 [multiset::upper_bound(STL/CLR)](../dotnet/multiset-upper-bound-stl-clr.md)