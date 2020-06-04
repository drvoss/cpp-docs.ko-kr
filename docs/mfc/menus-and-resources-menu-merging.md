---
title: '메뉴 및 리소스: 메뉴 병합'
ms.date: 11/04/2016
helpviewer_keywords:
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- coordinating menu layouts [MFC]
- OLE containers [MFC], menus and resources
- toolbars [MFC], OLE document applications
- merging toolbar and status bar [MFC]
- menus [MFC], OLE document applications
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
ms.openlocfilehash: 149af83bd53b7a97fd264bd6b18701fc9f64ea1f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364765"
---
# <a name="menus-and-resources-menu-merging"></a>메뉴 및 리소스: 메뉴 병합

이 문서에서는 시각적 편집 및 내부 활성화를 제대로 처리하는 OLE 문서 응용 프로그램에 필요한 단계를 자세히 설명합니다. 내부 활성화는 컨테이너 및 서버(구성 요소) 응용 프로그램 모두에 문제가 됩니다. 사용자는 컨테이너 문서의 컨텍스트 내에서 동일한 프레임 창에 남아 있지만 실제로 다른 응용 프로그램(서버)을 실행합니다. 이를 위해서는 컨테이너와 서버 응용 프로그램의 리소스 간에 조정이 필요합니다.

이 문서에서 다루는 주제는 다음과 같습니다.

- [메뉴 레이아웃](#_core_menu_layouts)

- [도구 모음 및 상태 표시줄](#_core_toolbars_and_status_bars)

## <a name="menu-layouts"></a><a name="_core_menu_layouts"></a>메뉴 레이아웃

첫 번째 단계는 메뉴 레이아웃을 조정하는 것입니다. 컨테이너 응용 프로그램은 포함된 항목이 활성화된 경우에만 사용할 새 메뉴를 만들어야 합니다. 최소한 이 메뉴는 나열된 순서대로 다음으로 구성되어야 합니다.

1. 파일이 열려 있을 때 사용된 것과 동일한 파일 메뉴입니다. (일반적으로 다음 항목 앞에 다른 메뉴 항목이 배치되지 않습니다.)

1. 두 개의 연속 분리기.

1. 파일이 열려 있을 때 사용한 것과 동일한 창 메뉴입니다(MDI 응용 프로그램의 컨테이너 응용 프로그램인 경우에만). 일부 응용 프로그램에는 포함된 항목이 활성화될 때 메뉴에 남아 있는 이 그룹에 속하는 옵션 메뉴와 같은 다른 메뉴가 있을 수 있습니다.

    > [!NOTE]
    >  확대/축소와 같은 컨테이너 문서보기에 영향을 주는 다른 메뉴가 있을 수 있습니다. 이러한 컨테이너 메뉴는 이 메뉴 리소스의 두 구분 기호 사이에 나타납니다.

서버(구성 요소) 응용 프로그램은 내부 활성화를 위해 특별히 새 메뉴를 만들어야 합니다. 파일이 열려 있을 때 사용되는 메뉴와 같아야 하지만 데이터 대신 서버 문서를 조작하는 파일 및 창과 같은 메뉴 항목이 없어야 합니다. 일반적으로 이 메뉴는 다음으로 구성됩니다.

1. 파일을 열 때 사용한 메뉴와 동일한 메뉴를 편집합니다.

1. 구분선입니다.

1. 낙서 샘플 응용 프로그램의 펜 메뉴와 같은 개체 편집 메뉴입니다.

1. 구분선입니다.

1. 도움말 메뉴.

예를 들어 컨테이너 및 서버에 대한 일부 샘플 내부 메뉴의 레이아웃을 살펴봅니다. 예제를 명확하게 하기 위해 각 메뉴 항목의 세부 정보가 제거되었습니다. 컨테이너의 현재 위치에는 다음과 같은 항목이 있습니다.

```
IDR_CONTAINERTYPE_CNTR_IP MENU PRELOAD DISCARDABLE
BEGIN
    POPUP "&File C1"
    MENUITEM SEPARATOR
    POPUP "&Zoom C2"
    MENUITEM SEPARATOR
    POPUP "&Options C3"
    POPUP "&Window C3"
END
```

연속 구분 기호는 서버 메뉴의 첫 번째 부분이 어디로 가야 하는지 나타냅니다. 이제 서버의 현재 설정 메뉴를 살펴보십시오.

```
IDR_SERVERTYPE_SRVR_IP MENU PRELOAD DISCARDABLE
BEGIN
    POPUP "&Edit S1"
    MENUITEM SEPARATOR
    POPUP "&Format S2"
    MENUITEM SEPARATOR
    POPUP "&Help S3"
END
```

여기서 구분 기호는 컨테이너 메뉴 항목의 두 번째 그룹이 이동해야 하는 위치를 나타냅니다. 이 서버의 개체가 이 컨테이너 내부에서 활성화될 때 결과 메뉴 구조는 다음과 같습니다.

```
BEGIN
    POPUP "&File C1"
    POPUP "&Edit S1"
    POPUP "&Zoom C2"
    POPUP "&Format S2"
    POPUP "&Options C3
    POPUP "&Window C3"
    POPUP "&Help S3"
END
```

보시다시피 구분 기호는 각 응용 프로그램 메뉴의 다른 그룹으로 대체되었습니다.

현재 메뉴와 연결된 액셀러레이터 테이블도 서버 응용 프로그램에서 제공해야 합니다. 컨테이너는 자체 가속기 테이블에 통합합니다.

포함된 항목이 활성화되면 프레임워크는 내부 메뉴를 로드합니다. 그런 다음 서버 응용 프로그램에 내부 활성화를 위해 메뉴를 요청하고 구분 기호가 있는 위치에 삽입합니다. 이것이 메뉴가 결합되는 방법입니다. 파일 및 창 배치에서 작동하기 위한 컨테이너에서 메뉴를 얻고 서버에서 항목을 작동하기 위한 메뉴를 가져옵니다.

## <a name="toolbars-and-status-bars"></a><a name="_core_toolbars_and_status_bars"></a>도구 모음 및 상태 표시줄

서버 응용 프로그램은 새 도구 모음을 만들고 비트맵을 별도의 파일에 저장해야 합니다. 응용 프로그램 마법사에서 생성된 응용 프로그램은 이 비트맵을 ITOOLBAR라는 파일에 저장합니다. Bmp. 새 도구 모음은 서버의 항목이 활성화될 때 컨테이너 응용 프로그램의 도구 모음을 대체하며 일반 도구 모음과 동일한 항목을 포함해야 하지만 파일 및 창 메뉴의 항목을 나타내는 아이콘을 제거합니다.

이 도구 모음은 `COleIPFrameWnd`응용 프로그램 마법사에 의해 만들어집니다 -derived 클래스에 로드 됩니다. 상태 표시줄은 컨테이너 응용 프로그램에서 처리됩니다. 현재 프레임 창 구현에 대한 자세한 내용은 [서버: 서버 구현](../mfc/servers-implementing-a-server.md)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[메뉴 및 리소스(OLE)](../mfc/menus-and-resources-ole.md)<br/>
[활성화](../mfc/activation-cpp.md)<br/>
[서버](../mfc/servers.md)<br/>
[컨테이너](../mfc/containers.md)
