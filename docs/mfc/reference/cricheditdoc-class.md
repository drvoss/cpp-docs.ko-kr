---
title: "CRichEditDoc 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
dev_langs:
- C++
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c427dc034a37bf3b0686b0fd95e62c3b718fbaea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cricheditdoc-class"></a>CRichEditDoc 클래스
와 [CRichEditView](../../mfc/reference/cricheditview-class.md) 및 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), MFC의 문서 뷰 아키텍처 컨텍스트 내에서 rich edit 컨트롤의 기능을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CRichEditDoc : public COleServerDoc  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](#createclientitem)|문서의 정리를 수행 하도록 호출 됩니다.|  
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|스트림 입력 및 출력 서식 지정 정보에 포함 되는지 여부를 나타냅니다.|  
|[CRichEditDoc::GetView](#getview)|연결 된 검색 [CRichEditView](../../mfc/reference/cricheditview-class.md) 개체입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[Cricheditdoc:: M_brtf](#m_brtf)|스트림 I/O 서식 지정이 포함 되는지 여부를 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 "Rich edit 컨트롤"는 사용자 입력 수 있으며 텍스트를 편집 하는 창입니다. 텍스트 문자 및 단락 서식을 할당할 수 있으며 포함 된 OLE 개체를 포함할 수 있습니다. Rich edit 컨트롤 텍스트의 서식을 지정 하기 위한 프로그래밍 인터페이스를 제공 합니다. 그러나 응용 프로그램 사용자에 게 형식 지정 작업을 제공 하는 데 필요한 사용자 인터페이스 구성 요소를 구현 해야 합니다.  
  
 `CRichEditView`텍스트 및 텍스트의 서식 특성을 유지 관리합니다. `CRichEditDoc`보기에 있는 클라이언트 항목의 목록을 유지 관리 합니다. `CRichEditCntrItem`컨테이너 쪽 OLE 클라이언트 항목에 대 한 액세스를 제공합니다.  
  
 이 Windows 공용 컨트롤 (및 따라서는 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 되는 프로그램에만 사용할 수는 있습니다.  
  
 MFC 응용 프로그램에서 서식 있는 편집 문서를 사용 하는 예제를 참조 하십시오.는 [워드 패드](../../visual-cpp-samples.md) 샘플 응용 프로그램입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrich.h  
  
##  <a name="createclientitem"></a>CRichEditDoc::CreateClientItem  
 이 함수를 만드는 호출는 `CRichEditCntrItem` 이 문서에 추가 합니다.  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 *preo*  
 에 대 한 포인터는 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE 항목에 설명 하는 구조입니다. 새 `CRichEditCntrItem` 이 OLE 항목 주위에 개체 생성 합니다. 경우 *preo* 은 **NULL**, 새 클라이언트 항목이 비어 있습니다.  
  
### <a name="return-value"></a>반환 값  
 새에 대 한 포인터 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 이 문서에 추가 된 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 모든 OLE 초기화를 수행 하지 않습니다.  
  
 자세한 내용은 참조는 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Windows SDK에는 구조입니다.  
  
##  <a name="getstreamformat"></a>CRichEditDoc::GetStreamFormat  
 서식 있는 편집 내용을 스트리밍에 대 한 텍스트 형식을 결정 하려면이 함수를 호출 합니다.  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>반환 값  
 다음과 같은 플래그 중 하나입니다.  
  
- `SF_TEXT`Rich edit 컨트롤 서식 지정 정보를 유지 하지 않는 것을 나타냅니다.  
  
- `SF_RTF`Rich edit 컨트롤 서식 지정 정보를 유지 관리지 않습니다 나타냅니다.  
  
### <a name="remarks"></a>설명  
 반환 값은 기반는 [m_bRTF](#m_brtf) 데이터 멤버입니다. 이 함수는 반환 `SF_RTF` 경우 `m_bRTF` 은 **TRUE**, 그렇지 않으면 `SF_TEXT`합니다.  
  
##  <a name="getview"></a>CRichEditDoc::GetView  
 에 액세스 하려면이 함수 호출의 [CRichEditView](../../mfc/reference/cricheditview-class.md) 이 연관 된 개체 `CRichEditDoc` 개체입니다.  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CRichEditView` 문서와 연결 된 개체입니다.  
  
### <a name="remarks"></a>설명  
 텍스트 및 서식 지정 정보에 포함 된는 `CRichEditView` 개체입니다. `CRichEditDoc` 개체는 serialization에 대 한 OLE 항목을 유지 합니다. 하나만 있어야 `CRichEditView` 각 `CRichEditDoc`합니다.  
  
##  <a name="m_brtf"></a>Cricheditdoc:: M_brtf  
 때 **TRUE**, 나타냅니다 [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) 및 [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) 단락 및 문자 서식 특성을 저장 해야 합니다.  
  
```  
BOOL m_bRTF;  
```  
  
## <a name="see-also"></a>참고 항목  
 [워드 패드 MFC 샘플](../../visual-cpp-samples.md)   
 [COleServerDoc 클래스](../../mfc/reference/coleserverdoc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRichEditView 클래스](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem 클래스](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument 클래스](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl 클래스](../../mfc/reference/cricheditctrl-class.md)
