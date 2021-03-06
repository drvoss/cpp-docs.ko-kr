---
title: "방법: 종료 프로세스 시작 여부 확인 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- .NET Framework, shutdown
- shutdown
- termination
- applications [C++], shutdown
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4d89fa475c997e0842ef9de5a21c26e664f25d78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-determine-if-shutdown-has-started-ccli"></a>방법: 종료 프로세스 시작 여부 확인(C++/CLI)
다음 코드 예제에서는 응용 프로그램 또는.NET Framework 현재 종료 여부를 확인 하는 방법을 보여 줍니다. 이 종료 하는 동안 이러한 구문 시스템에 의해 종료 하 고 안정적으로 사용할 수 없습니다 하기 때문에.NET Framework의 정적 요소에 액세스 하는 데 유용 합니다. 선택 하 여는 <xref:System.Environment.HasShutdownStarted%2A> 속성 먼저 이러한 요소에 액세스 하지 않으므로 발생할 수 있는 오류를 방지할 수 있습니다.  
  
## <a name="example"></a>예  
  
```  
// check_shutdown.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   if (Environment::HasShutdownStarted)  
      Console::WriteLine("Shutting down.");  
   else  
      Console::WriteLine("Not shutting down.");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Windows 작업 (C + + /cli CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)