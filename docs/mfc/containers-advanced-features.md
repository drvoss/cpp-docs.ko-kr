---
title: '컨테이너: 고급 기능'
ms.date: 11/04/2016
helpviewer_keywords:
- links [MFC], to embedded OLE objects
- containers [MFC], links to embedded OLE objects
- containers [MFC], advanced features
- container/server applications [MFC]
- embedded objects [MFC]
- OLE controls [MFC], containers
- OLE containers [MFC], advanced features
- server/container applications [MFC]
- containers [MFC], container applications
ms.assetid: 221fd99c-b138-40fa-ad6a-974e3b3ad1f8
ms.openlocfilehash: cf130bf8dead5c59548821658b979785c4d54726
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376491"
---
# <a name="containers-advanced-features"></a>컨테이너: 고급 기능

이 문서에서는 선택적 고급 기능을 기존 컨테이너 응용 프로그램에 통합하는 데 필요한 단계를 설명합니다. 이러한 기능은 다음과 같습니다.

- [컨테이너와 서버 모두인 응용 프로그램](#_core_creating_a_container_server_application)

- [포함된 개체에 대한 OLE 링크](#_core_links_to_embedded_objects)

## <a name="creating-a-containerserver-application"></a><a name="_core_creating_a_container_server_application"></a>컨테이너/서버 응용 프로그램 만들기

컨테이너/서버 응용 프로그램은 컨테이너와 서버 역할을 모두 하는 응용 프로그램입니다. 윈도우에 대한 마이크로 소프트 워드는이의 예입니다. 다른 응용 프로그램에서 Windows용 Word 문서를 포함할 수 있으며 Windows용 Word 문서에 항목을 포함할 수도 있습니다. 컨테이너 응용 프로그램을 컨테이너와 전체 서버로 수정하는 프로세스(조합 컨테이너/미니 서버 응용 프로그램을 만들 수 없음)는 전체 서버를 만드는 프로세스와 유사합니다.

이 문서 [서버: 서버 구현에는 서버](../mfc/servers-implementing-a-server.md) 응용 프로그램을 구현하는 데 필요한 여러 작업이 나열됩니다. 컨테이너 응용 프로그램을 컨테이너/서버 응용 프로그램으로 변환하는 경우 동일한 작업 중 일부를 수행하여 컨테이너에 코드를 추가해야 합니다. 다음은 고려해야 할 중요한 사항들을 나열합니다.

- 응용 프로그램 마법사에서 만든 컨테이너 코드는 이미 OLE 하위 시스템을 초기화합니다. 해당 지원을 위해 아무 것도 변경하거나 추가할 필요가 없습니다.

- 문서 클래스의 기본 클래스가 `COleDocument`있는 모든 위치에 `COleServerDoc`는 기본 클래스를 로 변경합니다.

- 서버 `COleClientItem::CanActivate` 자체가 제자리에서 편집하는 데 사용되는 동안 항목을 수정하지 않도록 재정의합니다.

   예를 들어 MFC OLE 샘플 [OCLIENT에는](../overview/visual-cpp-samples.md) 컨테이너/서버 응용 프로그램에서 만든 항목이 포함되어 있습니다. OCLIENT 응용 프로그램을 열고 컨테이너/서버 응용 프로그램에서 만든 항목을 편집합니다. 응용 프로그램의 항목을 편집하는 동안 MFC OLE 샘플 [HIERSVR에서](../overview/visual-cpp-samples.md)만든 항목을 포함하기로 결정합니다. 이렇게 하려면 내부 활성화를 사용할 수 없습니다. 이 항목을 활성화하려면 HIERSVR을 완전히 열어야 합니다. Microsoft Foundation 클래스 라이브러리는 이 OLE 기능을 `COleClientItem::CanActivate` 지원하지 않으므로 재정의를 통해 이 상황을 확인하고 응용 프로그램에서 가능한 런타임 오류를 방지할 수 있습니다.

새 응용 프로그램을 만들고 컨테이너/서버 응용 프로그램으로 작동하려는 경우 응용 프로그램 마법사의 OLE 옵션 대화 상자에서 해당 옵션을 선택하면 이 지원이 자동으로 만들어집니다. 자세한 내용은 문서 [개요: ActiveX 제어 컨테이너 만들기를](../mfc/reference/creating-an-mfc-activex-control-container.md)참조하세요. MFC 샘플에 대한 자세한 내용은 [MFC 샘플을](../overview/visual-cpp-samples.md#mfc-samples)참조하십시오.

MDI 응용 프로그램을 자체적으로 삽입할 수 없습니다. 컨테이너/서버인 응용 프로그램은 SDI 응용 프로그램이 아니면 자체적으로 삽입할 수 없습니다.

## <a name="links-to-embedded-objects"></a><a name="_core_links_to_embedded_objects"></a>포함된 객체에 대한 링크

임베디드 개체에 대한 링크 기능을 사용하면 컨테이너 응용 프로그램 내에 포함된 개체에 대한 OLE 링크가 있는 문서를 만들 수 있습니다. 예를 들어 포함된 스프레드시트가 포함된 워드 프로세서에서 문서를 만듭니다. 응용 프로그램에서 포함된 개체에 대한 링크를 지원하는 경우 워드 프로세서의 문서에 포함된 스프레드시트에 대한 링크를 붙여칠 수 있습니다. 이 기능을 사용하면 응용 프로그램에서 워드 프로세서가 원래 위치를 알지 못하고 스프레드시트에 포함된 정보를 사용할 수 있습니다.

#### <a name="to-link-to-embedded-objects-in-your-application"></a>응용 프로그램에서 포함된 개체에 연결하려면

1. 에서 문서 클래스를 `COleLinkingDoc` `COleDocument`파생합니다.

1. OLE 개발 도구에 포함된 클래스 ID 생성기를 사용하여 응용 프로그램에 대한 OLE 클래스**ID(CLSID)를**만듭니다.

1. OLE로 응용 프로그램을 등록합니다.

1. 개체를 `COleTemplateServer` 응용 프로그램 클래스의 멤버로 만듭니다.

1. 응용 프로그램 클래스의 `InitInstance` 멤버 함수에서 다음을 수행합니다.

   - 개체의 `COleTemplateServer` 멤버 함수를 호출하여 개체를 `ConnectTemplate` 문서 템플릿에 연결합니다.

   - 멤버 `COleTemplateServer::RegisterAll` 함수를 호출하여 OLE 시스템에 모든 클래스 개체를 등록합니다.

   - `COleTemplateServer::UpdateRegistry`을 호출합니다. 응용 프로그램이 `UpdateRegistry` "/Embedded" 스위치로 시작되지 않은 경우 유일한 매개 변수는 *OAT_CONTAINER* 합니다. 이렇게 하면 응용 프로그램이 포함된 개체에 대한 링크를 지원할 수 있는 컨테이너로 등록됩니다.

      응용 프로그램이 "/Embedded" 스위치로 시작되는 경우 서버 응용 프로그램과 유사한 기본 창이 표시되지 않아야 합니다.

MFC OLE 샘플 [OCLIENT는](../overview/visual-cpp-samples.md) 이 기능을 구현합니다. 이 작업을 수행하는 방법에 대한 예제는 `InitInstance` *OCLIENT의 함수를 참조하십시오. *이 샘플 응용 프로그램의 CPP 파일입니다.

## <a name="see-also"></a>참고 항목

[컨테이너](../mfc/containers.md)<br/>
[서버](../mfc/servers.md)
