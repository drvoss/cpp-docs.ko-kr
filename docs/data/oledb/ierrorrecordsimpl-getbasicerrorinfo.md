---
title: 'Ierrorrecordsimpl:: Getbasicerrorinfo | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IErrorRecordsImpl::GetBasicErrorInfo
- IErrorRecordsImpl::GetBasicErrorInfo
- GetBasicErrorInfo
- ATL.IErrorRecordsImpl.GetBasicErrorInfo
- IErrorRecordsImpl.GetBasicErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- GetBasicErrorInfo method
ms.assetid: d0b4dec3-f32a-4aaa-8365-524f2e7c8395
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 787cbeaea106d33b276458c75251ec5850e51550
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ierrorrecordsimplgetbasicerrorinfo"></a>IErrorRecordsImpl::GetBasicErrorInfo
반환 코드 및 공급자 특정 오류 번호와 같은 오류에 대 한 기본 정보를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,  
   ERRORINFO *pErrorInfo);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IErrorRecordsImpl 클래스](../../data/oledb/ierrorrecordsimpl-class.md)