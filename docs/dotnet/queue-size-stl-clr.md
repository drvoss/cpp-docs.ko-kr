---
title: 'queue:: size (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::queue::size
dev_langs:
- C++
helpviewer_keywords:
- size member [STL/CLR]
ms.assetid: 864510ef-5a00-4377-b286-1e73f237e359
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 46f1eec77c1a4b030b412e21709dff0c2300712d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="queuesize-stlclr"></a>queue::size(STL/CLR)
요소 수를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_type size();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 제어되는 시퀀스의 길이를 반환합니다. 제어 되는 시퀀스의 현재 요소 수를 확인 하려면 사용 합니다. 모든 경우에 중요 한 여부 시퀀스 크기가 0이 아닌 참조 [queue:: empty (STL/CLR)](../dotnet/queue-empty-stl-clr.md)`()`합니다.  
  
## <a name="example"></a>예  
  
```  
// cliext_queue_size.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// pop an item and reinspect   
    c1.pop();   
    System::Console::WriteLine("size() = {0} after popping", c1.size());   
  
// add two elements and reinspect   
    c1.push(L'a');   
    c1.push(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3 starting with 3  
size() = 2 after popping  
size() = 4 after adding 2  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/queue >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [queue (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::empty(STL/CLR)](../dotnet/queue-empty-stl-clr.md)