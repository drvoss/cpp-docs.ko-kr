---
title: "_locking 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
dev_langs:
- C++
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4231235fc35a8b6d22f49e2ba05db337a619713
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="locking-constants"></a>_locking 상수
## <a name="syntax"></a>구문  
  
```  
  
#include <sys/locking.h>  
  
```  
  
## <a name="remarks"></a>설명  
 `_locking` 함수 호출에서 *mode* 인수는 수행할 잠금 작업을 지정합니다.  
  
 *mode* 인수는 다음 매니페스트 상수 중 하나여야 합니다.  
  
 `_LK_LOCK`  
 지정된 바이트를 잠급니다. 바이트를 잠글 수 없는 경우 이 함수는 1초 후 다시 시도합니다. 10번 시도 후에도 바이트를 잠글 수 없으면 이 함수는 오류를 반환합니다.  
  
 `_LK_RLCK`  
 `_LK_LOCK`와 동일합니다.  
  
 `_LK_NBLCK`  
 지정된 바이트를 잠급니다. 바이트를 잠글 수 없으면 이 함수는 오류를 반환합니다.  
  
 `_LK_NBRLCK`  
 `_LK_NBLCK`와 동일합니다.  
  
 `_LK_UNLCK`  
 지정된 바이트의 잠금을 해제합니다. (해당 바이트는 이전에 잠겼을 것입니다.)  
  
## <a name="see-also"></a>참고 항목  
 [_locking](../c-runtime-library/reference/locking.md)   
 [전역 상수](../c-runtime-library/global-constants.md)