---
title: 'Cdataconnection:: Copy | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataConnection.Copy
- ATL.CDataConnection.Copy
- ATL::CDataConnection::Copy
- CDataConnection::Copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method
ms.assetid: a3dbd70d-36be-49e0-a527-00e3910a7a56
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 043874f9c6047317b29156c957ce99d263dfeca2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnectioncopy"></a>CDataConnection::Copy
기존 데이터 연결의 복사본을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      CDataConnection& Copy(const CDataConnection & ds) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ds`  
 [in] 복사할 기존 데이터 연결에 대 한 참조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)