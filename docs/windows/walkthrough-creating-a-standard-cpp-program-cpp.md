---
title: "연습: 만들기 표준 c + + 프로그램 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords:
- vcfirstapp
- vccreatefirst
dev_langs:
- C++
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 52066be1d67bddb7173841e9df6c5013c86ac0dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>연습: 만들기 표준 c + + 프로그램 (c + +)
표준 c + + 프로그램을 만들어 Visual Studio 통합된 개발 환경 (IDE)에서 Visual c + +를 사용할 수 있습니다. 이 연습 단계를 수행 하 여 프로젝트를 만들에 추가할 수 있습니다 새 파일을 프로젝트에 c + + 코드를 추가 하 고 다음 컴파일 및 사용 하 여 프로그램을 실행 하려면 파일을 수정 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]합니다.  
  
 C + + 프로그램을 직접 입력 하거나 샘플 프로그램 중 하나를 사용할 수 있습니다. 이 연습에서는 샘플 프로그램은 콘솔 응용 프로그램입니다. 이 응용 프로그램 사용은 `set` c + + 표준 라이브러리의 컨테이너입니다.  
  
 Visual c + + 2003 c + + 표준 주요 예외가 준수: 2 단계 이름 조회, 예외 사양 및 내보내기. 또한 Visual c + + 람다 식, auto, static_assert, rvalue 참조 및 extern template 예를 들어 몇 가지 C + + 0x 기능을 지원합니다.  
  
> [!NOTE]
>  표준 준수가 필요한 경우 사용 된 **/Za** 컴파일러 옵션을 표준에 대 한 Microsoft 확장을 사용 하지 않도록 설정 합니다. 자세한 내용은 참조 [/Za, /Ze (언어 확장명 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 C++ 언어의 기본적인 사항을 알고 있어야 합니다.  
  
### <a name="to-create-a-project-and-add-a-source-file"></a>프로젝트를 만들고 소스 파일을 추가 하려면  
  
1.  가리켜 프로젝트 만들기 **새로** 에 **파일** 메뉴에서을 클릭 한 다음 **프로젝트**합니다.  
  
2.  에 **Visual c + +** 프로젝트 형식 창, 클릭 **Win32**, 클릭 하 고 **Win32 콘솔 응용 프로그램**합니다.  
  
3.  프로젝트에 대 한 이름을 입력 합니다.  
  
     기본적으로 프로젝트를 포함 하는 솔루션에 프로젝트와 동일한 이름이 되지만 다른 이름을 입력할 수 있습니다. 프로젝트에 대 한 다른 위치를 입력할 수 있습니다.  
  
     클릭 **확인** 프로젝트를 만듭니다.  
  
4.  에 **Win32 응용 프로그램 마법사**, 클릭 **다음**선택, **빈 프로젝트**, 클릭 하 고 **마침**합니다.  
  
5.  경우 **솔루션 탐색기** 표시 되지 않으면에 **보기** 메뉴를 클릭 **솔루션 탐색기**합니다.  
  
6.  다음과 같이 새 소스 파일을 프로젝트에 추가 합니다.  
  
    1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 **소스 파일** 폴더를 가리키도록 **추가**, 클릭 하 고 **새 항목**합니다.  
  
    2.  에 **코드** 노드를 클릭 **c + + 파일 (.cpp)**파일 이름을 입력 한 다음 클릭 **추가**합니다.  
  
     .Cpp 파일의 원본 파일 폴더에 나타납니다 **솔루션 탐색기**, Visual Studio 편집기에서 파일이 열립니다.  
  
7.  편집기에서 파일을에서 c + + 표준 라이브러리를 사용 하는 올바른 c + + 프로그램 입력 샘플 프로그램 중 하나를 복사 하는 파일에 붙여 넣습니다.  
  
8.  파일을 저장합니다.  
  
9. **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     **출력** 창 컴파일 진행률, 빌드 로그 및 빌드 상태를 나타내는 메시지의 예를 들어 위치에 대 한 정보를 표시 합니다.  
  
10. 에 **디버그** 메뉴를 클릭 하 여 **디버깅 하지 않고 시작**합니다.  
  
     샘플 프로그램을 사용 하는 경우 명령 창을 표시 되 고 집합에 특정 정수 찾았는지를 보여 줍니다.  
  
## <a name="next-steps"></a>다음 단계  
 **이전:** [콘솔 Visual c + +에서 응용 프로그램](../windows/console-applications-in-visual-cpp.md)합니다. **다음:**[연습: 명령줄에서 네이티브 c + + 프로그램 컴파일](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)