---
title: "생성자 (c + +) 없이 클래스 및 구조체 초기화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c65bc0adb32d61cef76e02aa944826eaf866c7c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-classes-and-structs-without-constructors-c"></a>생성자 없이 클래스 및 구조체 초기화(C++)
클래스, 특히 비교적 간단한 클래스에 대해 항상 생성자를 정의할 필요는 없습니다. 사용자는 다음 예제와 같이 균일 초기화를 사용하여 클래스 또는 구조체의 개체를 초기화할 수 있습니다.  
  
```  
#include "stdafx.h"  
#include <Windows.h>  
  
// No constructor  
struct TempData  
{  
    int StationId;  
    time_t time;  
    double current;  
    double maxTemp;  
    double minTemp;  
};  
  
// Has a constructor  
struct TempData2  
{  
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :  
       minTemp(minimum), maxTemp(maximum), current(cur), stationId(id), time(t) {}  
    int stationId;  
    time_t time;  
    double current;  
    double maxTemp;  
    double minTemp;  
};  
  
int main()  
{  
    // Member initialization (in order of declaration):  
    TempData td{ 45978, GetCurrentTime(), 28.9, 37.0, 16.7 };  
  
    // Default initialization = {0,0,0,0,0}  
    TempData td_default{};  
  
    //Error C4700 uninitialized local variable  
    TempData td_noInit;  
  
    // Member declaration (in order of ctor parameters)  
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, GetCurrentTime() };  
  
    return 0;  
}  
  
```  
  
 클래스 또는 구조체에 생성자가 없을 경우 제공 하는 클래스에는 멤버는 선언 순서에서 목록 요소 참고 합니다. 클래스에 있는 경우 생성자가 매개 변수 순서 대로 요소를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 및 구조체](../cpp/classes-and-structs-cpp.md)   
 [생성자](../cpp/constructors-cpp.md)