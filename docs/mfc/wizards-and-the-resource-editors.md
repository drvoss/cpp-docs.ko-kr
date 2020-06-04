---
title: 마법사 및 리소스 편집기
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and MFC
- MFC, resource editors
- resource editors, MFC
- MFC Application Wizard
- editors [MFC], resource
- wizards [MFC]
- wizards [MFC], MFC programming
- MFC, wizards
- Class View tool, managing Windows messages
ms.assetid: f5dd4d13-9dc1-4a49-b6bf-5b3cb45fa8ba
ms.openlocfilehash: 04d9f2cf615636b151af93a3c3880f7357496048
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365272"
---
# <a name="wizards-and-the-resource-editors"></a>마법사 및 리소스 편집기

Visual C++에는 많은 통합 리소스 편집기와 함께 MFC 프로그래밍에 사용할 수 있는 여러 마법사가 포함되어 있습니다. ActiveX 컨트롤 프로그래밍의 경우 [ActiveX 컨트롤 마법사는](../mfc/reference/mfc-activex-control-wizard.md) MFC 응용 프로그램 마법사와 매우 유사하게 사용됩니다. 이러한 도구의 대부분없이 MFC 응용 프로그램을 작성할 수 있지만, 도구는 크게 단순화하고 작업을 가속화.

## <a name="use-the-mfc-application-wizard-to-create-an-mfc-application"></a><a name="_core_use_appwizard_to_create_an_mfc_application"></a>MFC 응용 프로그램 마법사를 사용하여 MFC 응용 프로그램 만들기

[MFC 응용 프로그램 마법사를](../mfc/reference/mfc-application-wizard.md) 사용하여 OLE 및 데이터베이스 지원을 포함할 수 있는 Visual C++에서 MFC 프로젝트를 만듭니다. 프로젝트의 파일에는 응용 프로그램, 문서, 보기 및 프레임 창 클래스가 포함됩니다. 메뉴 및 선택적 도구 모음을 포함한 표준 리소스; 다른 필요한 윈도우 파일; 및 프로그램 도움말 파일을 만들기 위해 수정하고 보강할 수 있는 표준 Windows 도움말 항목이 포함된 .rtf 파일(옵션)을 선택 사항으로 제공합니다.

## <a name="use-class-view-to-manage-classes-and-windows-messages"></a><a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a>클래스 보기를 사용하여 클래스 및 Windows 메시지 관리

클래스 보기를 사용하면 Windows 메시지 및 명령에 대한 처리기 함수를 만들고, 클래스를 만들고 관리하고, 클래스 멤버 변수를 만들고, 자동화 메서드 및 속성을 만들고, 데이터베이스 클래스를 만드는 등의 기능을 사용할 수 있습니다.

> [!NOTE]
> 클래스 보기를 사용하면 MFC 클래스에서 가상 함수를 재정의할 수도 있습니다. 재정의할 클래스와 가상 함수를 선택합니다. 나머지 프로세스는 다음 단락에 설명된 대로 메시지 처리와 유사합니다.

Windows에서 실행되는 응용 프로그램은 [메시지 기반입니다.](../mfc/message-handling-and-mapping.md) 실행 중인 프로그램에서 발생하는 사용자 작업 및 기타 이벤트로 인해 Windows는 프로그램의 창에 메시지를 보냅니다. 예를 들어 사용자가 창에서 마우스를 클릭하면 왼쪽 마우스 단추를 누를 때 Windows는 WM_LBUTTONDOWN 메시지를 보내고 단추를 해제할 때 WM_LBUTTONUP 메시지를 보냅니다. 또한 Windows는 사용자가 메뉴 모음에서 명령을 선택할 때 WM_COMMAND 메시지를 보냅니다.

MFC 프레임워크에서 문서, 뷰, 프레임 창, 문서 템플릿 및 응용 프로그램 개체와 같은 다양한 개체는 메시지를 "처리"할 수 있습니다. 이러한 개체는 멤버 함수 중 하나로 "처리기 함수"를 제공 하며 프레임 워크는 들어오는 메시지를 처리기에 매핑합니다.

프로그래밍 작업의 큰 부분은 어떤 객체에 매핑할 메시지를 선택한 다음 해당 매핑을 구현하는 것입니다. 이렇게 하려면 클래스 보기 및 [클래스 마법사를](reference/mfc-class-wizard.md)사용합니다.

[클래스 마법사는](reference/mfc-class-wizard.md) 빈 메시지 처리기 멤버 함수를 만들고 소스 코드 편집기를 사용하여 처리기의 본문을 구현합니다. 또한 클래스 보기를 사용하여 클래스(MFC 클래스에서 파생되지 않은 고유한 클래스 포함)와 해당 멤버를 만들거나 편집할 수도 있습니다. 클래스 보기 사용 및 프로젝트에 코드를 추가하는 마법사에 대한 자세한 내용은 [코드 마법사를 사용하여 기능 추가를](../ide/adding-functionality-with-code-wizards-cpp.md)참조하십시오.

## <a name="use-the-resource-editors-to-create-and-edit-resources"></a><a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a>리소스 편집기를 사용하여 리소스 만들기 및 편집

Visual C++ [리소스 편집기를](../windows/resource-editors.md) 사용하여 메뉴, 대화 상자, 사용자 지정 컨트롤, 가속기 키, 비트맵, 아이콘, 커서, 문자열 및 버전 리소스를 만들고 편집할 수 있습니다. Visual C++ 버전 4.0을 사용하면 도구 모음 편집기에서 도구 모음을 훨씬 쉽게 만들 수 있습니다.

더 많은 도움을 주기 위해 Microsoft 재단 클래스 라이브러리는 COMMON이라는 파일을 제공합니다. RES, 당신은 공통에서 복사 할 수있는 "클립 아트"자원을 포함. RES를 사용하여 사용자 고유의 리소스 파일에 붙여넣습니다. 일반적인. RES에는 도구 모음 단추, 일반적인 커서, 아이콘 등이 포함됩니다. 응용 프로그램에서 이러한 리소스를 사용, 수정 및 재배포할 수 있습니다. COMMON에 대한 자세한 내용은 RES, [클립아트 샘플을](../overview/visual-cpp-samples.md)참조하십시오.

MFC 응용 프로그램 마법사, Visual C++ 마법사, 리소스 편집기 및 MFC 프레임워크는 많은 작업을 수행하며 코드를 훨씬 쉽게 관리할 수 있습니다. 응용 프로그램별 코드의 대부분은 문서 및 보기 클래스에 있습니다.

## <a name="see-also"></a>참고 항목

[클래스를 사용하여 Windows 애플리케이션 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)
