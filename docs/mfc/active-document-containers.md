---
title: 액티브 문서 컨테이너
ms.date: 11/19/2018
helpviewer_keywords:
- active documents [MFC], containers
- active document containers [MFC]
- containers [MFC], active document
- MFC COM, active document containment
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
ms.openlocfilehash: e2005ffed592fa1de278e0f6339d94687a20fd06
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377391"
---
# <a name="active-document-containers"></a>액티브 문서 컨테이너

Microsoft Office 바인더 또는 Internet Explorer와 같은 활성 문서 컨테이너를 사용하면 각 문서 유형에 대해 여러 응용 프로그램 프레임을 만들고 사용하도록 강제하는 대신 단일 프레임 내에서 여러 응용 프로그램 유형의 여러 문서로 작업할 수 있습니다.

MFC는 클래스의 활성 문서 `COleDocObjectItem` 컨테이너에 대한 전체 지원을 제공합니다. MFC 응용 프로그램 마법사를 사용하여 MFC 응용 프로그램 마법사의 복합 문서 **지원** 페이지에서 활성 문서 컨테이너 확인란을 선택하여 활성 **문서 컨테이너를** 만들 수 있습니다. 자세한 내용은 [활성 문서 컨테이너 응용 프로그램 만들기를](../mfc/creating-an-active-document-container-application.md)참조하십시오.

활성 문서 컨테이너에 대한 자세한 내용은 다음을 참조하십시오.

- [컨테이너 요구 사항](#container_requirements)

- [문서 사이트 개체](#document_site_objects)

- [사이트 객체 보기](#view_site_objects)

- [프레임 개체](#frame_object)

- [도움말 메뉴 병합](../mfc/help-menu-merging.md)

- [프로그래밍 방식 인쇄](../mfc/programmatic-printing.md)

- [명령 대상](../mfc/message-handling-and-command-targets.md)

## <a name="container-requirements"></a><a name="container_requirements"></a>컨테이너 요구 사항

활성 문서 컨테이너의 활성 문서 지원은 인터페이스 구현 그 이상을 의미합니다. 활성 문서 확장에도 마찬가지입니다.

활성 문서를 통합하는 활성 문서 컨테이너는 다음을 수행해야 합니다.

- `IPersistStorage` 인터페이스를 통해 개체 저장소를 처리할 수 있어야 합니다. `IStorage`

- OLE 문서의 기본 임베딩 기능을 지원하여 구현및 `IOleClientSite` `IAdviseSink`을 구현하는 "사이트" 개체(문서 또는 임베딩당 하나)가 필요합니다.

- 포함된 개체 또는 활성 문서의 내부 활성화를 지원합니다. 컨테이너의 사이트 개체는 `IOleInPlaceSite` 구현해야 하며 컨테이너의 프레임 `IOleInPlaceFrame`개체는 을 제공해야 합니다.

- 컨테이너가 문서와 통신할 `IOleDocumentSite` 수 있는 메커니즘을 제공하도록 구현하여 활성 문서의 확장을 지원합니다. 선택적으로 컨테이너는 활성 문서 인터페이스를 `IOleCommandTarget` `IContinueCallback` 구현하고 인쇄 또는 저장과 같은 간단한 명령을 선택할 수 있습니다.

프레임 개체, 뷰 개체 및 컨테이너 개체는 `IOleCommandTarget` [명령 대상에서](../mfc/message-handling-and-command-targets.md)설명한 대로 특정 명령의 디스패치를 지원하기 위해 선택적으로 구현할 수 있습니다. 보기 및 컨테이너 개체는 `IPrint` 프로그래밍 `IContinueCallback`방식 인쇄에서 설명한 대로 프로그래밍 방식 인쇄를 지원하기 위해 선택적으로 구현할 수 있습니다. [Programmatic Printing](../mfc/programmatic-printing.md)

다음 그림은 컨테이너와 해당 구성 요소(왼쪽) 및 활성 문서와 뷰(오른쪽) 간의 개념적 관계를 보여 주습니다. 활성 문서는 저장소 및 데이터를 관리하며 뷰는 해당 데이터를 표시하거나 선택적으로 인쇄합니다. 굵게 표시된 인터페이스는 활성 문서 참여에 필요한 인터페이스입니다. 이러한 굵게 및 기울임꼴은 선택 사항입니다. 다른 모든 인터페이스가 필요합니다.

![활성 문서 컨테이너 인터페이스](../mfc/media/vc37gj1.gif "활성 문서 컨테이너 인터페이스")

단일 뷰만 지원하는 문서는 단일 콘크리트 클래스에서 뷰 및 문서 구성 요소(즉, 해당 인터페이스)를 모두 구현할 수 있습니다. 또한 한 번에 하나의 뷰만 지원하는 컨테이너 사이트는 문서 사이트와 뷰 사이트를 단일 콘크리트 사이트 클래스로 결합할 수 있습니다. 그러나 컨테이너의 프레임 개체는 뚜렷하게 유지되어야 하며 컨테이너의 문서 구성 요소는 아키텍처에 대한 전체 그림을 제공하기 위해 여기에 포함됩니다. 활성 문서 제약 아키텍처의 영향을 받지 않습니다.

## <a name="document-site-objects"></a><a name="document_site_objects"></a>문서 사이트 개체

활성 문서 제약 아키텍처에서 문서 사이트는 `IOleDocument` 인터페이스가 추가된 OLE 문서의 클라이언트 사이트 개체와 동일합니다.

```cpp
interface IOleDocumentSite : IUnknown
{
    HRESULT ActivateMe(IOleDocumentView *pViewToActivate);
}
```

문서 사이트는 개념적으로 하나 이상의 "뷰 사이트" 개체에 대한 컨테이너입니다. 각 뷰 사이트 개체는 문서 사이트에서 관리하는 문서의 개별 뷰 개체와 연결됩니다. 컨테이너가 문서 사이트당 단일 보기만 지원하는 경우 문서 사이트와 뷰 사이트를 단일 콘크리트 클래스로 구현할 수 있습니다.

## <a name="view-site-objects"></a><a name="view_site_objects"></a>사이트 객체 보기

컨테이너의 뷰 사이트 객체는 문서의 특정 뷰에 대한 표시 공간을 관리합니다. 뷰 사이트는 표준 `IOleInPlaceSite` 인터페이스를 지원하는 것 외에도 일반적으로 `IContinueCallback` 프로그래밍 방식의 인쇄 제어를 구현합니다. 뷰 개체는 컨테이너가 원하는 `IContinueCallback` 모든 개체에서 실제로 구현할 수 있도록 쿼리하지 않습니다.

여러 뷰를 지원하는 컨테이너는 문서 사이트 내에서 여러 뷰 사이트 개체를 만들 수 있어야 합니다. 이렇게 하면 을 통해 `IOleInPlaceSite`제공되는 별도의 활성화 및 비활성화 서비스가 각 보기를 제공합니다.

## <a name="frame-object"></a><a name="frame_object"></a>프레임 오브젝트

컨테이너의 프레임 개체는 대부분의 경우 OLE 문서에서 내부 활성화에 사용되는 프레임, 즉 메뉴 및 도구 모음 협상을 처리하는 프레임입니다. 뷰 개체는 이 프레임 개체에 액세스할 수 있으며 `IOleInPlaceSite::GetWindowContext`컨테이너 문서를 나타내는 컨테이너 개체(창 수준 도구 모음 협상 및 포함된 개체 열거를 처리할 수 있음)에 대한 액세스도 제공합니다.

활성 문서 컨테이너는 을 추가하여 `IOleCommandTarget`프레임을 보강할 수 있습니다. 이렇게 하면 이 인터페이스에서 컨테이너가 동일한 명령을 보낼 수 있는 것과 같은 방식으로 활성 문서의 사용자 인터페이스에서 시작된 명령을 받을 수 있습니다(예: **파일 새로** **시작됨**, 로 저장 으로 **저장**: **인쇄;** **복사,** **붙여넣기,** **수행 취소**및 기타)를 활성 문서로 편집합니다. 자세한 내용은 [명령 대상](../mfc/message-handling-and-command-targets.md)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[액티브 문서 포함](../mfc/active-document-containment.md)
