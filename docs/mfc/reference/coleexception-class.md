---
title: "COleException 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
dev_langs:
- C++
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e895e893c6032a8f8d7db0549f872c82cd0d9b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="coleexception-class"></a>COleException 클래스
OLE 작업과 관련된 예외 조건을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleException : public CException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleException::Process](#process)|예외가 OLE 반환 코드로 변환합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|예외에 대 한 이유를 나타내는 상태 코드를 포함 합니다.|  
  
## <a name="remarks"></a>설명  
 `COleException` 클래스는 예외에 대 한 이유를 나타내는 상태 코드를 보유 하는 공용 데이터 멤버를 포함 합니다.  
  
 일반적으로 만들면 안 한 `COleException` 개체 직접; 대신 호출 해야 [AfxThrowOleException](exception-processing.md#afxthrowoleexception)합니다.  
  
 예외에 대 한 자세한 내용은 문서를 참조 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md) 및 [예외: OLE 예외](../../mfc/exceptions-ole-exceptions.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
##  <a name="m_sc"></a>COleException::m_sc  
 이 데이터 멤버는 예외에 대 한 이유를 나타내는 OLE 상태 코드를 보유 합니다.  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>설명  
 이 변수 값을 설정한 [AfxThrowOleException](exception-processing.md#afxthrowoleexception)합니다.  
  
 대 한 자세한 내용은 `SCODE`, 참조 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="process"></a>COleException::Process  
 호출 된 **프로세스** 예외가 OLE 상태 코드로 변환 하는 멤버 함수입니다.  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>매개 변수  
 *pAnyException*  
 포인터 예외가 검색 되었습니다.  
  
### <a name="return-value"></a>반환 값  
 OLE 상태 코드입니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 함수는 **정적**합니다.  
  
 대 한 자세한 내용은 `SCODE`, 참조 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
  예를 참조 [coledispatchdriver:: Createdispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CALCDRIV MFC 샘플](../../visual-cpp-samples.md)   
 [CException 클래스](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



