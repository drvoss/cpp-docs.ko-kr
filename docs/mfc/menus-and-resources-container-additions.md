---
title: "메뉴 및 리소스: 컨테이너 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDP_OLE_INIT_FAILED
- IDP_FAILED_TO_CREATE
- VK_ESCAPE
dev_langs:
- C++
helpviewer_keywords:
- application accelerator table [MFC]
- VK_ESCAPE key [MFC]
- IDP_FAILED_TO_CREATE macro [MFC]
- visual editing, application menus and resources
- OLE containers [MFC], menus and resources
- accelerator tables [MFC], container applications
- IDP_OLE_INIT_FAILED macro [MFC]
- CONTAIN tutorial [MFC]
- Links menu item [MFC]
ms.assetid: 425448be-8ca0-412e-909a-a3a9ce845288
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 654efeaacd08e0d2c8c51cee012fd58dcbf071ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="menus-and-resources-container-additions"></a>메뉴 및 리소스: 컨테이너 추가
이 문서에서는 메뉴 및 기타 시각적 편집 컨테이너 응용 프로그램 리소스에 적용 하는 변경 사항을 설명 합니다.  
  
 컨테이너 응용 프로그램에서는 두 가지 유형의 변경 해야 할: OLE 비주얼 편집 및 내부 활성화에 사용 되는 새 리소스의 추가 지원 하도록 기존 리소스를 수정 합니다. 컨테이너 응용 프로그램을 만들 응용 프로그램 마법사를 사용 하는 경우 다음이 단계를 수행 됩니다 하지만 일부 사용자 지정 해야 합니다.  
  
 응용 프로그램 마법사를 사용 하지 않는 경우에 OCLIENT 확인 하는 것이 좋습니다. RC, OCLIENT 샘플 응용 프로그램을 이러한 변경 내용을 구현 하는 방법 참조에 대 한 리소스 스크립트입니다. MFC OLE 샘플 [OCLIENT](../visual-cpp-samples.md)합니다.  
  
 이 문서에서 다루는 항목은 다음과 같습니다.  
  
-   [컨테이너 메뉴 추가](#_core_container_menu_additions)  
  
-   [액셀러레이터 키 테이블 추가](#_core_container_application_accelerator_table_additions)  
  
-   [문자열 테이블 추가](#_core_string_table_additions_for_container_applications)  
  
##  <a name="_core_container_menu_additions"></a>컨테이너 메뉴 추가  
 편집 메뉴에 다음 항목을 추가 해야 합니다.  
  
|항목|용도|  
|----------|-------------|  
|**새 개체를 삽입 합니다.**|문서에 연결 되거나 포함 된 항목을 삽입 하려면 OLE 개체 삽입 대화 상자를 엽니다.|  
|**연결 하 여 붙여넣기**|문서에는 항목 링크를를 클립보드에 붙여 넣습니다.|  
|**OLE 동사**|선택한 항목의 기본 동사를 호출합니다. 선택한 항목의 기본 동사에 맞게이 메뉴 항목 변경의 텍스트입니다.|  
|**Links**|기존 연결 된 항목을 변경 하려면 OLE 편집 링크 대화 상자를 엽니다.|  
  
 이 문서에 나열 된 변경 내용을 외에도 소스 파일 AFXOLECL 포함 해야 합니다. Microsoft Foundation Class 라이브러리 구현에 필요한 RC 새 개체 삽입에 필요한 유일한 메뉴 추가입니다. 다른 항목을 추가할 수 있지만 여기에 나와 있는 가장 일반적인 것입니다.  
  
 포함 된 항목의 내부 활성화를 지원 하려는 경우 컨테이너 응용 프로그램에 대 한 새 메뉴를 만들어야 합니다. 이 메뉴는 같은 파일 메뉴 및 이들 사이 배치 하는 두 개의 구분 기호에 있지만 파일을 열 때 사용 되는 창 팝업 메뉴 구성 됩니다. 이러한 구분 기호는 서버 (구성 요소) 항목 (응용 프로그램)에 활성화 될 때 해당 메뉴를 배치 해야 나타내는 데 사용 됩니다. 이 메뉴 병합 하는 방법에 대 한 자세한 내용은 참조 하십시오. [메뉴 및 리소스: 메뉴 병합](../mfc/menus-and-resources-menu-merging.md)합니다.  
  
##  <a name="_core_container_application_accelerator_table_additions"></a>컨테이너 응용 프로그램 액셀러레이터 키 테이블 추가  
 컨테이너 응용 프로그램의 액셀러레이터 키 테이블 리소스를 작은 변경이 내부 활성화를 지 원하는 경우에 필요 합니다. 첫 번째 변경 (ESC) 내부 편집 모드를 취소 하려면 esc 키를 눌러야 수 있습니다. 기본 액셀러레이터 키 테이블에 다음 항목을 추가 합니다.  
  
|ID|Key|형식|  
|--------|---------|----------|  
|**ID_CANCEL_EDIT_CNTR**|VK_ESCAPE|**VIRTKEY**|  
  
 두 번째 변경 사항에는 내부 활성화에 대해 만든 새 메뉴 리소스에 해당 하는 새 액셀러레이터 키 테이블을 만드는 것입니다. 이 테이블 외에 파일 및 창 메뉴에 대 한 항목에는 **VK_ESCAPE** 위의 항목입니다. 다음 예제는 MFC 샘플에서에 내부 활성화에 대해 만든 액셀러레이터 키 테이블 [컨테이너](../visual-cpp-samples.md):  
  
|ID|Key|형식|  
|--------|---------|----------|  
|`ID_FILE_NEW`|Ctrl+N|**VIRTKEY**|  
|`ID_FILE_OPEN`|Ctrl+O|**VIRTKEY**|  
|**ID_FILE_SAVE**|Ctrl+S|**VIRTKEY**|  
|**ID_FILE_PRINT**|Ctrl+P|**VIRTKEY**|  
|**ID_NEXT_PANE**|VK_F6|**VIRTKEY**|  
|**ID_PREV_PANE**|SHIFT + VK_F6|**VIRTKEY**|  
|**ID_CANCEL_EDIT_CNTR**|VK_ESCAPE|**VIRTKEY**|  
  
##  <a name="_core_string_table_additions_for_container_applications"></a>컨테이너 응용 프로그램에 대 한 문자열 테이블 추가  
 에 설명 된 추가 메뉴 항목에 해당 하는 대부분의 컨테이너 응용 프로그램에 대 한 문자열 테이블 내용 [컨테이너 메뉴 추가](#_core_container_menu_additions)합니다. 이러한 각 메뉴 항목 표시 되 면 상태 표시줄에 표시 되는 텍스트를 제공 합니다. 다음은 예를 들어, 응용 프로그램 마법사에서 생성 하는 문자열 테이블 항목입니다.  
  
|ID|문자열|  
|--------|------------|  
|**IDP_OLE_INIT_FAILED**|OLE 초기화 하지 못했습니다. OLE 라이브러리 버전이 올바른지 확인 합니다.|  
|**IDP_FAILED_TO_CREATE**|개체를 만들지 못했습니다. 개체가 시스템 레지스트리에 입력 되어 있는지 확인 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [메뉴 및 리소스 (OLE)](../mfc/menus-and-resources-ole.md)   
 [메뉴 및 리소스: 서버 추가](../mfc/menus-and-resources-server-additions.md)

