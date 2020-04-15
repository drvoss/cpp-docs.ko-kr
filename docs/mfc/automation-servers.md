---
title: 자동화 서버
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
ms.openlocfilehash: 391cb2f6ff5673296f40e21113e3a6510f71d475
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370833"
---
# <a name="automation-servers"></a>자동화 서버

자동화를 사용하면 응용 프로그램에서 다른 응용 프로그램에서 구현된 개체를 조작하거나 개체를 노출하여 조작할 수 있습니다. 자동화 서버는 프로그래밍 가능한 개체(자동화 개체라고 함)를 다른 응용 [프로그램(자동화 클라이언트라고](../mfc/automation-clients.md)함)에 노출시키는 응용 프로그램입니다. 자동화 서버를 자동화 구성 요소라고도 합니다.

자동화 개체를 노출하면 클라이언트가 서버에서 사용할 수 있는 개체 및 기능에 직접 액세스하여 특정 프로시저를 자동화할 수 있습니다. 응용 프로그램이 다른 응용 프로그램에 유용한 기능을 제공할 때 이러한 방식으로 개체를 노출하는 것이 유용합니다. 예를 들어 워드 프로세서는 다른 프로그램에서 사용할 수 있도록 맞춤법 검사 기능을 노출할 수 있습니다. 따라서 공급업체는 개체를 노출하여 다른 응용 프로그램의 기성 기능을 사용하여 응용 프로그램의 기능을 향상시킬 수 있습니다.

이러한 자동화 개체에는 외부 인터페이스로서의 속성 및 메서드가 있습니다. 속성은 자동화 개체의 특성으로 지정됩니다. 속성은 C++ 클래스의 데이터 멤버와 같습니다. 메서드는 자동화 개체에서 작동하는 함수입니다. 메서드는 C++ 클래스의 공용 멤버 함수와 같습니다.

> [!NOTE]
> 속성은 C++ 데이터 멤버와 비슷하지만 직접 액세스할 수는 없습니다. 투명한 액세스를 제공하려면 자동화 개체에 액세스하는 get/set 멤버 함수 쌍을 사용하여 내부 변수를 설정합니다.

Automation은 잘 정의된 공통 인터페이스를 통해 응용 프로그램 기능을 노출함으로써 다양한 응용 프로그램별 매크로 언어대신 Microsoft Visual Basic과 같은 단일 일반 프로그래밍 언어로 응용 프로그램을 빌드할 수 있습니다.

## <a name="support-for-automation-servers"></a><a name="_core_support_for_automation_servers"></a>자동화 서버 지원

Visual C++와 MFC 프레임워크는 자동화 서버에 대한 광범위한 지원을 제공합니다. 자동화 서버를 만드는 데 관련된 많은 오버헤드를 처리하므로 응용 프로그램의 기능에 집중할 수 있습니다.

자동화를 지원하기 위한 프레임워크의 주요 메커니즘은 디스패치 맵으로, 선언으로 확장되는 매크로 집합과 OLE에 대한 메서드 및 속성을 노출하는 데 필요한 호출입니다. 일반적인 디스패치 맵은 다음과 같습니다.

[!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]

[클래스 마법사](reference/mfc-class-wizard.md) 및 클래스 보기는 디스패치 맵을 유지 관리하는 데 도움이 됩니다. 클래스에 새 메서드 또는 속성을 추가하면 Visual Studio는 클래스 이름, 메서드 또는 속성의 외부 및 내부 이름 및 데이터 형식을 나타내는 매개 변수가 있는 해당 `DISP_FUNCTION` 또는 `DISP_PROPERTY` 매크로를 추가합니다.

또한 **클래스 추가** 대화 상자는 자동화 클래스의 선언과 해당 속성 및 작업의 관리를 단순화합니다. 클래스 추가 대화 상자를 사용하여 프로젝트에 클래스를 추가하는 경우 기본 클래스를 지정합니다. 기본 클래스에서 자동화를 허용하는 경우 클래스 추가 대화 상자는 새 클래스가 자동화를 지원해야 하는지 여부, "OLE creatable"(즉, COM 클라이언트의 요청에 따라 클래스의 개체를 만들 수 있는지 여부) 및 COM 클라이언트의 외부 이름을 지정하는 데 사용하는 컨트롤을 표시합니다.

그런 다음 **클래스 추가** 대화 상자는 지정한 OLE 기능에 적합한 매크로를 포함하여 클래스 선언을 만듭니다. 또한 클래스의 멤버 함수를 구현하기 위한 스켈레톤 코드도 추가됩니다.

MFC 응용 프로그램 마법사는 자동화 서버 응용 프로그램을 처음부터 제거하는 데 관련된 단계를 단순화합니다. **고급 기능** 페이지에서 **자동화** 확인란을 선택하면 MFC 응용 프로그램 마법사가 `InitInstance` 자동화 개체를 등록하고 응용 프로그램을 자동화 서버로 실행하는 데 필요한 호출을 응용 프로그램 기능에 추가합니다.

### <a name="what-do-you-want-to-do"></a>뭘 하고 싶으세요

- [자동화 클라이언트에 대해 알아보기](../mfc/automation-clients.md)

- [클래스 CCmdTarget에 대해 자세히 알아보기](../mfc/reference/ccmdtarget-class.md)

- [클래스 COleDispatchDriver에 대해 자세히 알아보기](../mfc/reference/coledispatchdriver-class.md)

## <a name="see-also"></a>참고 항목

[Automation](../mfc/automation.md)<br/>
[MFC 애플리케이션 마법사](../mfc/reference/mfc-application-wizard.md)
