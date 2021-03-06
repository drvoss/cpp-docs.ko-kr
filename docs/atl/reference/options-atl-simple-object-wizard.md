---
title: "옵션, ATL 단순 개체 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.simple.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Simple Object Wizard, options
ms.assetid: 125fe179-942d-4181-8b82-33e92e1fd779
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37341dc23f95e1863aeae4a1b57c01d24d6ad365
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="options-atl-simple-object-wizard"></a>옵션, ATL 단순 개체 마법사
ATL 단순 개체 마법사의이 페이지를 사용 하 여 효율성과 개체에 대 한 오류 지원에 대 한 디자인 합니다.  
  
 ATL 프로젝트와 ATL COM 클래스에 대 한 자세한 내용은 참조 하십시오. [ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)합니다.  
  
 **스레딩 모델**  
 스레드를 관리 하기 위한 메서드를 나타냅니다. 기본적으로 프로젝트에서는 **아파트** 스레딩 합니다.  
  
 참조 [프로젝트의 스레딩 모델 지정](../../atl/specifying-the-threading-model-for-a-project-atl.md) 자세한 정보에 대 한 합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|`Single`|개체가 기본 COM 스레드에서 항상 실행 되도록 지정 합니다. 참조 [스레드 아파트](http://msdn.microsoft.com/library/windows/desktop/ms680112) 및 [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) 자세한 정보에 대 한 합니다.|  
|**아파트**|개체가 아파트 스레딩을 사용 하도록 지정 합니다. 단일 같음 스레드 아파트 합니다. 아파트 스레드 구성 요소의 각 개체는 개체의 수명에 대 한 해당 스레드에 대 한 아파트 할당 그러나 여러 개체에 대해 여러 스레드를 사용할 수 있습니다. 각 아파트는 특정 스레드에 연결 되었으며 Windows 메시지 펌프 (기본값).<br /><br /> 참조 [스레드 아파트](http://msdn.microsoft.com/library/windows/desktop/ms680112) 자세한 정보에 대 한 합니다.|  
|**둘 다**|개체는 사용할 수 있도록 지정 아파트 이거나 자유 스레딩 만든 스레드의 종류에 따라 합니다.|  
|**무료**|개체가 자유 스레딩을 사용 하도록 지정 합니다. 자유 스레딩은 다중 스레드 아파트 모델입니다. 참조 [다중 스레드 아파트](http://msdn.microsoft.com/library/windows/desktop/ms693421) 자세한 정보에 대 한 합니다.|  
|**Neutral**|개체는 다중 스레드 아파트에 대 한 지침을 따라 하지만 모든 종류의 스레드에서 실행 될 수를 지정 합니다.|  
  
 **집계**  
 개체를 사용할지 여부를 나타내는 [집계](http://msdn.microsoft.com/library/windows/desktop/ms686558)합니다. 집계 개체를 클라이언트에서 노출할 인터페이스를 선택 하 고 집계 개체에서 구현 된 것 처럼 인터페이스 노출 됩니다. 집계 개체의 클라이언트는 집계 개체와만 통신합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|예|개체를 집계할 수 있도록 지정 합니다. 기본값입니다.|  
|아니요|개체가 집계 되지 않은 것을 지정 합니다.|  
|만|개체가 해야 집계할 수 있도록 지정 합니다.|  
  
 **Interface**  
 개체가 지 원하는 인터페이스의 형식을 나타냅니다. 기본적으로 개체는 이중 인터페이스를 지원합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**Dual**|개체는 이중 인터페이스를 지원 하도록 지정 (해당 vtable에 인터페이스를 사용자 지정 함수 및 런타임에 바인딩 `IDispatch` 메서드). 수 있도록 두 COM 클라이언트 및 [자동화 컨트롤러](../../mfc/automation-clients.md) 개체에 액세스할 수 있습니다. 기본값입니다.|  
|**사용자 지정**|개체는 사용자 지정 인터페이스 (사용자 지정 인터페이스 함수)를 지원 하는지 지정 합니다. 프로세스 경계를 넘어 사용자 지정 인터페이스는 이중 인터페이스 보다 빠를 수 있습니다.<br /><br /> -   **자동화 호환** 허용 자동화 컨트롤러 사용자 지정 인터페이스 지 원하는 개체에 액세스 합니다.|  
  
 **지원**  
 개체에 대 한 추가 지원을 나타냅니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**ISupportErrorInfo**|에 대 한 지원 만듭니다는 [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) 인터페이스 개체는 클라이언트에 오류 정보를 반환할 수 있도록 합니다.|  
|**연결 지점**|개체의 클래스에서 파생 하 여 개체에 대 한 연결점을 사용 하면 [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)합니다.|  
|**자유 스레드된 마샬러**|동일한 프로세스에서 스레드 간에 효율적으로 marshal 인터페이스 포인터에 대 한 자유 스레드된 마샬러 개체를 만듭니다. 지정 하는 개체를 사용할 수 있는 **둘 다** 스레딩 모델로 합니다.|  
|**IObjectWithSite (IE 개체 지원)**|구현 [IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md), 컨테이너에 있는 개체와 해당 사이트 간의 통신을 지원 하는 간단한 방법을 제공 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [ATL 단순 개체 마법사](../../atl/reference/atl-simple-object-wizard.md)   
 [ATL 단순 개체](../../atl/reference/adding-an-atl-simple-object.md)   
 [프로세스 서버 스레딩 문제](http://msdn.microsoft.com/library/windows/desktop/ms687205)

