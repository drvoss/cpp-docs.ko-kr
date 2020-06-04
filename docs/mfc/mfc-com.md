---
title: MFC COM
ms.date: 09/12/2018
f1_keywords:
- MFC COM (MFC)
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
ms.openlocfilehash: 514251475050e728be1959417ead1dbdf96e4800
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358190"
---
# <a name="mfc-com"></a>MFC COM

MFC의 하위 집합은 COM을 지원하도록 설계되었으며 대부분의 활성 템플릿 라이브러리(ATL)는 COM 프로그래밍용으로 설계되었습니다. 이 항목 섹션에서는 COM에 대한 MFC의 지원에 대해 설명합니다.

활성 기술(예: ActiveX 컨트롤, 활성 문서 포함, OLE 등)은 COM(구성 요소 개체 모델)을 사용하여 소프트웨어 구성 요소가 생성된 언어에 관계없이 네트워크 환경에서 서로 상호 작용할 수 있도록 합니다. 활성 기술을 사용하여 데스크톱 또는 인터넷에서 실행되는 응용 프로그램을 만들 수 있습니다. 자세한 내용은 [COM](../atl/introduction-to-com.md) 또는 [구성 요소 개체 모델 소개를](/windows/win32/com/the-component-object-model)참조하십시오.

활성 기술에는 다음을 포함한 클라이언트 및 서버 기술이 모두 포함됩니다.

- ActiveX 컨트롤은 웹 사이트와 같은 컨테이너에서 사용할 수 있는 대화형 개체입니다. ActiveX 컨트롤에 대한 자세한 내용은 다음을 참조하십시오.

  - [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

  - [인터넷의 ActiveX 컨트롤](../mfc/activex-controls-on-the-internet.md)

  - [개요: 인터넷](../mfc/mfc-internet-programming-basics.md)

  - [인터넷에서 사용할 기존 ActiveX 컨트롤 업그레이드](../mfc/upgrading-an-existing-activex-control.md)

  - [액티브X 컨트롤 디버깅](/visualstudio/debugger/how-to-debug-an-activex-control)

- 활성 스크립팅은 브라우저 또는 서버에서 하나 이상의 ActiveX 컨트롤의 통합 동작을 제어합니다. 활성 스크립팅에 대한 자세한 내용은 [인터넷의 활성 기술을](../mfc/active-technology-on-the-internet.md)참조하십시오.

- [자동화(이전의](../mfc/automation.md) OLE 자동화)를 사용하면 한 응용 프로그램에서 다른 응용 프로그램에서 구현된 개체를 조작하거나 개체를 "노출"하여 조작할 수 있습니다.

   자동화된 개체는 로컬 또는 원격(네트워크를 통해 액세스할 수 있는 다른 컴퓨터에서)일 수 있습니다. 자동화는 OLE 및 COM 개체 모두에 대해 사용할 수 있습니다.

- 이 섹션에서는 [연결 지점과](../mfc/connection-points.md)같은 MFC를 사용하여 COM 구성 요소를 작성하는 방법에 대한 정보도 제공합니다.

여전히 OLE라고 하는 것과 현재 활성 기술이라고 불리는 기술에 대한 설명은 [OLE](../mfc/ole-in-mfc.md)의 항목을 참조하십시오.

## <a name="in-this-section"></a>섹션 내용

[액티브 문서 포함](../mfc/active-document-containment.md)

[Automation](../mfc/automation.md)

[연결 지점](../mfc/connection-points.md)

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>참고 항목

[개념](../mfc/mfc-concepts.md)
