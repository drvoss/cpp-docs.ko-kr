---
title: "연습: MFC를 사용 하 여 리본 응용 프로그램 만들기 | Microsoft Docs"
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
- ribbon application, creating (MFC)
- creating a ribbon aplication (MFC)
ms.assetid: e61393e2-1d6b-4594-a7ce-157d3d1b0d9f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfad78b64f72b9ee9a896832e008039aa241e2ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-creating-a-ribbon-application-by-using-mfc"></a>연습: MFC를 사용하여 리본 응용 프로그램 만들기
이 연습에서는 사용 하는 방법을 보여 줍니다.는 **MFC 응용 프로그램 마법사** 기본적으로 리본 메뉴를 포함 하는 응용 프로그램을 만들려고 합니다. 추가 하 여 리본 메뉴를 확장 한 다음는 **사용자 지정** 있는 리본 범주는 **즐겨찾기** 리본 패널 및 다음 자주 사용 되는 일부 패널에 명령을 추가 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습에서는 설정 가정 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 사용할 **일반 개발 설정**합니다. 다른 설정을 사용할 경우, 다음 지침에서 참조되는 UI(사용자 인터페이스) 요소 중 일부가 표시되지 않을 수도 있습니다. 설정을 변경 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 사용자 기본 설정](http://msdn.microsoft.com/en-us/c95c51be-e609-4769-abba-65e6beedec76)합니다.  
  
### <a name="to-create-an-mfc-application-that-has-a-ribbon"></a>리본 메뉴를 포함하고 있는 MFC 응용 프로그램을 만들려면  
  
1.  사용 하 여는 **MFC 응용 프로그램 마법사** 리본 메뉴가 있는 MFC 응용 프로그램을 만들려고 합니다. 마법사를 실행 하는 **파일** 메뉴에서 **새로**, 클릭 하 고 **프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **Visual c + +** 노드 아래의 **설치 된 템플릿**선택, **MFC**를 선택한 후  **MFC 응용 프로그램**합니다. 예를 들어 프로젝트에 대 한 이름을 입력 `MFCRibbonApp`, 클릭 하 고 **확인**합니다.  
  
3.  첫 번째 페이지에는 **MFC 응용 프로그램 마법사**, 클릭 **다음**합니다.  
  
4.  에 **응용 프로그램 종류** 페이지의 **비주얼 스타일과 색**선택, **Office 2007 (파랑 테마)**합니다. 다른 설정은 그대로 둡니다. **다음**을 클릭합니다.  
  
5.  에 **복합 문서 지원** 페이지에서 다음 사항을 확인 **None** 을 선택 하 고 클릭 **다음**합니다.  
  
6.  에 **문서 템플릿 속성** 페이지는 **파일 확장명** 상자 예를 들어이 응용 프로그램에서 문서에 대 한 파일 이름 확장명을 입력 합니다 `mfcrbnapp`합니다. **다음**을 클릭합니다.  
  
7.  에 **데이터베이스 지원** 페이지에서 다음 사항을 확인 **None** 을 선택 하 고 클릭 **다음**합니다.  
  
8.  에 **사용자 인터페이스 기능** 페이지에서 다음 사항을 확인 **리본 메뉴를 사용 하 여** 을 선택 합니다. **다음**을 클릭합니다.  
  
9. 기본적으로는 **MFC 응용 프로그램 마법사** 여러 도킹 창에 대 한 지원을 추가 합니다. 이 연습에서는 리본 메뉴만을 설명하기 때문에, 응용 프로그램에서 이러한 옵션을 제거할 수 있습니다. 에 **고급 기능** 페이지에서 모든 옵션의 선택을 취소 합니다. **다음**을 클릭합니다.  
  
10. 에 **생성 된 클래스** 페이지에서 클릭 **마침** MFC 응용 프로그램을 만듭니다.  
  
11. 응용 프로그램이 만들어졌는지 확인하기 위하여, 응용 프로그램을 빌드하고 실행합니다. 에 응용 프로그램을 작성 하는 **빌드** 메뉴를 클릭 하 여 **솔루션 빌드**합니다. 응용 프로그램이 성공적으로 빌드되면, 클릭 하 여 실행 **디버깅 시작** 에 **디버그** 메뉴.  
  
     자동으로 만듭니다는 명명 된 리본 범주 하나를 가진 리본 **홈**합니다. 이 리본에 이름이 지정 된 세 가지 리본 패널이 포함 되어 **클립보드**, **보기**, 및 **창**합니다.  
  
### <a name="to-add-a-category-and-panel-to-the-ribbon"></a>리본 메뉴에 범주와 패널을 추가하려면  
  
1.  마법사에서 만든 리본 리소스를 열려면는 **보기** 메뉴에서 **다른 창** 클릭 하 고 **리소스 뷰**합니다. **리소스 뷰**, 클릭 **리본** 두 번 클릭 하 고 **IDR_RIBBON**합니다.  
  
2.  먼저 두 번 클릭 하 여 리본 메뉴를 사용자 지정 범주를 추가 **범주** 에 **도구 상자**합니다.  
  
     캡션이 있는 범주인 **Category1** 만들어집니다. 기본적으로 범주에는 하나의 패널이 포함되어 있습니다.  
  
     마우스 오른쪽 단추로 클릭 **Category1** 클릭 하 고 **속성**합니다. 에 **속성** 창 변경 **캡션** 를 `Custom`합니다.  
  
     **큰 이미지** 및 **작은 이미지** 속성이 범주의 리본 요소에 대 한 아이콘으로 사용 되는 비트맵을 지정 합니다. 이 연습 범위에서는 사용자 지정 비트맵 만들기를 다루지 않기 때문에, 마법사에서 만든 비트맵을 다시 사용합니다. 작은 비트맵은 16 x 16 픽셀입니다. 작은 이미지의 경우 리소스 ID IDB_FILESMALL로 액세스할 수 있는 비트맵을 사용합니다. 큰 비트맵은 32 x 32 픽셀입니다. 큰 이미지의 경우 리소스 ID IDB_FILELARGE로 액세스할 수 있는 비트맵을 사용합니다.  
  
    > [!NOTE]
    >  HDPI 디스플레이에서는 HDPI 버전의 이미지가 자동으로 사용됩니다.  
  
3.  다음으로, 패널을 사용자 지정합니다. 패널은 논리적으로 연관된 항목들을 그룹화하는 데 사용됩니다. 예를 들어에 **홈** 탭이 응용이 프로그램의는 **잘라내기**, **복사**, 및 **붙여넣기** 에 있는 명령을  **클립보드** 패널입니다. 패널을 사용자 지정 하려면 마우스 오른쪽 단추로 클릭 **패널 1** 클릭 하 고 **속성**합니다. 에 **속성** 창 변경 **캡션** 를 `Favorites`합니다.  
  
     지정할 수는 **이미지 인덱스:** 패널에 대 한 합니다. 리본 패널에 추가 된 경우 표시 되는 아이콘을 지정 하는이 숫자는 **빠른 실행 도구 모음**합니다. 이 아이콘은 리본 패널 자체에 표시되지 않습니다.  
  
4.  리본 컨트롤 미리 보기를 통해 리본 범주와 패널이 생성되었는지 확인합니다. 에 **Ribbon 편집기 도구 모음**, 클릭는 **Ribbon 테스트** 단추입니다. A **사용자 지정** 탭 및 **즐겨찾기** 패널 리본 메뉴에 표시 되어야 합니다.  
  
### <a name="to-add-elements-to-the-ribbon-panels"></a>리본 패널에 요소를 추가하려면  
  
1.  이전 절차에서 만든 패널에 요소를 추가 하려면 컨트롤을 끌어 옵니다는 **Ribbon 편집기** 섹션은 **도구 상자** 디자인 뷰에서 패널에 있습니다.  
  
2.  먼저 추가 하는 **인쇄** 단추입니다. **인쇄** 단추를 포함 하는 하위 메뉴 갖습니다는 **빠른 인쇄** 기본 프린터를 사용 하 여 인쇄 명령입니다. 이 두 명령은 모두 이 응용 프로그램에 이미 정의되어 있고, 응용 프로그램 메뉴에 있습니다.  
  
     만들려는 **인쇄** 단추에서 패널 단추 도구를 끕니다.  
  
     에 **속성** 창에서 변경 된 **ID** 속성을 **ID_FILE_PRINT**, 정의 이미 해야 합니다. 변경 **캡션** 를 `Print`합니다. 변경 **이미지 인덱스** 를 `4`합니다.  
  
     만들려는 **빠른 인쇄** 단추 속성 값 열 옆에 클릭 **메뉴 항목**, 줄임표를 클릭 한 다음 (**...** ). 에 **항목 편집기**를 클릭 하 여 레이블이 지정 되지 않은 **추가** 메뉴 항목을 만드는 단추입니다. 에 **속성** 창 변경 **캡션** 를 `Quick Print`, **ID** 를 `ID_FILE_PRINT_DIRECT`, 및 **이미지** 를 `5` . 이미지 속성은 IDB_FILESMALL 비트맵 리소스의 빠른 인쇄 아이콘을 지정합니다.  
  
3.  리본 패널에 단추가 추가되었는지 확인하기 위해 응용 프로그램을 빌드하고 실행합니다. 에 응용 프로그램을 작성 하는 **빌드** 메뉴를 클릭 하 여 **솔루션 빌드**합니다. 응용 프로그램이 성공적으로 빌드되면를 클릭 하 여 응용 프로그램을 실행 **디버깅 시작** 에 **디버그** 메뉴. **인쇄** 단추와 콤보 상자에 **즐겨찾기** 패널에 **사용자 지정** 리본 메뉴의 탭을 표시 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 [방법: 빠른 실행 도구 모음 사용자 지정](../mfc/how-to-customize-the-quick-access-toolbar.md)  
  
 [방법: 응용 프로그램 단추 사용자 지정](../mfc/how-to-customize-the-application-button.md)  
  
 종단 간 샘플 [샘플 (MFC 기능 팩)](../visual-cpp-samples.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습](../mfc/walkthroughs-mfc.md)   
 [샘플 (MFC 기능 팩)](../visual-cpp-samples.md)

