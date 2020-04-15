---
title: 인쇄 미리 보기 아키텍처
ms.date: 11/04/2016
helpviewer_keywords:
- print preview [MFC], process
- previewing printing
- print preview [MFC], architecture
- printing [MFC], print preview
- print preview [MFC], modifications to MFC
ms.assetid: 0efc87e6-ff8d-43c5-9d72-9b729a169115
ms.openlocfilehash: 5943edc22cd48ed10d152f72624467ff87104b96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375939"
---
# <a name="print-preview-architecture"></a>인쇄 미리 보기 아키텍처

이 문서에서는 MFC 프레임워크에서 인쇄 미리 보기 기능을 구현하는 방법을 설명합니다. 다음 내용을 다룹니다.

- [인쇄 미리 보기 프로세스](#_core_the_print_preview_process)

- [인쇄 미리 보기 수정](#_core_modifying_print_preview)

인쇄 미리 보기는 화면 표시 및 인쇄와는 다소 다릅니다. 디바이스에 이미지를 직접 그리는 대신 애플리케이션이 화면을 사용해서 프린터를 시뮬레이션해야 하기 때문입니다. 이를 수용하기 위해 Microsoft 재단 클래스 라이브러리는 [CDC 클래스에서](../mfc/reference/cdc-class.md)파생된 특수(문서화되지 않은) 클래스를 정의합니다. `CPreviewDC` 또는 `CDC` 개체는 두 개의 디바이스 컨텍스트를 포함하지만 일반적으로 동일합니다. `CPreviewDC` 개체에서 서로 다릅니다: 첫 번째는 시뮬레이션 중인 프린터를 나타내고 두 번째는 출력이 실제로 표시되는 화면을 나타냅니다.

## <a name="the-print-preview-process"></a><a name="_core_the_print_preview_process"></a>인쇄 미리 보기 프로세스

사용자가 **파일** 메뉴에서 미리 보기 인쇄 명령을 선택하면 프레임워크에서 개체가 `CPreviewDC` 만들어집니다. 애플리케이션이 프린터 디바이스 컨텍스트의 특성을 설정하는 작업을 수행할 때마다 프레임워크도 화면 디바이스 컨텍스트에서 비슷한 작업을 수행합니다. 예를 들어 애플리케이션이 인쇄 글꼴을 선택하면, 프레임워크도 프린터 글꼴을 시뮬레이션하는 화면 표시를 위해 글꼴을 선택합니다. 애플리케이션이 프린터에 출력을 보낼 때마다 프레임워크는 대신 출력을 화면으로 전송합니다.

인쇄 미리 보기는 또한 문서의 페이지를 그리는 순서도 인쇄와 다릅니다. 인쇄 중에는 특정 페이지 범위가 렌더링될 때까지 프레임워크가 인쇄 루프를 계속 수행합니다. 인쇄 미리 보기 중에는 언제라도 1~2개의 페이지가 표시되며, 애플리케이션은 대기 상태입니다. 사용자의 반응이 있기 전까지는 추가 페이지가 표시되지 않습니다. 인쇄 미리 보기 중에 응용 프로그램은 일반 화면 표시 때와 마찬가지로 WM_PAINT 메시지에도 응답해야 합니다.

[CView::OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 기능은 인쇄 작업의 시작 부분과 마찬가지로 미리 보기 모드가 호출될 때 호출됩니다. 함수에 전달된 [CPrintInfo 구조체에는](../mfc/reference/cprintinfo-structure.md) 인쇄 미리 보기 작업의 특정 특성을 조정하도록 설정할 수 있는 값을 포함하는 여러 멤버가 포함되어 있습니다. 예를 들어 *m_nNumPreviewPages* 멤버를 설정하여 문서를 한 페이지 또는 2페이지 모드에서 미리 볼지 여부를 지정할 수 있습니다.

## <a name="modifying-print-preview"></a><a name="_core_modifying_print_preview"></a>인쇄 미리 보기 수정

인쇄 미리 보기의 동작과 모양은 여러 가지 방법으로 비교적 쉽게 수정할 수 있습니다. 예를 들어, 다음과 같은 작업이 가능합니다.

- 인쇄 미리 보기 창에 문서의 특정 페이지에 쉽게 액세스할 수 있는 스크롤 막대를 표시합니다.

- 인쇄 미리 보기를 표시할 때 현재 페이지를 먼저 표시하여 문서에서 사용자의 위치를 유지합니다.

- 인쇄 미리 보기 및 인쇄를 위해 서로 다른 초기화를 수행합니다.

- 인쇄 미리 보기에서 사용자의 고유 형식으로 페이지 번호를 표시합니다.

문서가 얼마나 긴지 알고 있고 적합한 값을 사용해서 `SetMaxPage`를 호출하면 프레임 워크가 인쇄 중은 물론 미리 보기 모드에서도 이 정보를 사용할 수 있습니다. 프레임워크가 문서 길이를 알게 되면, 미리 보기 창에 스크롤 막대를 제공하여 사용자가 미리 보기 모드에서 문서의 앞/뒤로 이동할 수 있습니다. 문서 길이를 설정하지 않은 경우에는 프레임워크가 현재 위치를 나타내는 스크롤 상자 위치를 결정할 수 없으므로, 프레임워크가 스크롤 막대를 추가하지 않습니다. 이 경우, 문서에서 페이지를 이동하려면 미리 보기 창의 컨트롤 막대에서 다음 페이지 및 이전 페이지 단추를 사용해야 합니다.

인쇄 미리 보기의 경우 일반 인쇄에서는 값을 *m_nCurPage* 할당하지 `CPrintInfo`않더라도 m_nCurPage 멤버에 값을 할당하는 것이 유용할 수 있습니다. 일반적인 인쇄의 경우, 이 멤버는 프레임워크에서 뷰 클래스로 정보를 전달합니다. 이를 통해 프레임워크는 인쇄할 페이지를 뷰에 알려줍니다.

반대로 인쇄 미리 보기 모드가 시작되면 *m_nCurPage* 멤버는 뷰에서 프레임워크까지 반대 방향으로 정보를 전달합니다. 프레임워크는 이 멤버의 값을 사용해서 먼저 미리 보기로 표시할 페이지를 결정합니다. 이 멤버의 기본값은 1이므로 문서의 첫 번째 페이지가 처음에 표시됩니다. 인쇄 미리 보기 명령이 호출될 때 표시할 페이지 번호로 이 멤버를 설정하도록 `OnPreparePrinting`을 재정의할 수 있습니다. 이렇게 하면 애플리케이션이 일반적인 표시 모드에서 인쇄 미리 보기 모드로 이동할 때 사용자의 현재 위치를 유지할 수 있습니다.

일부 경우에는 인쇄 작업 또는 인쇄 미리 보기를 위해 호출되었는지 여부에 따라 `OnPreparePrinting`이 다른 초기화를 수행하도록 해야 할 수 있습니다. 구조에서 *m_bPreview* 멤버 변수를 검사하여 `CPrintInfo` 이를 확인할 수 있습니다. 이 멤버는 인쇄 미리 보기가 호출될 때 **TRUE로** 설정됩니다.

또한 `CPrintInfo` 구조에는 *m_strPageDesc라는*멤버가 포함되어 있으며, 이 문자열은 화면 하단에 표시되는 문자열을 단일 페이지 및 여러 페이지 모드로 서식을 지정하는 데 사용됩니다. 기본적으로 이러한 문자열은 "Page *n"* 및 "Page *n* - *m"이라는*형식이지만 `OnPreparePrinting` 내부에서 *m_strPageDesc* 수정하고 문자열을 보다 정교한 형식으로 설정할 수 있습니다. 자세한 내용은 *MFC 참조의* [CPrintInfo 구조를](../mfc/reference/cprintinfo-structure.md) 참조하십시오.

## <a name="see-also"></a>참고 항목

[인쇄 및 인쇄 미리 보기](../mfc/printing-and-print-preview.md)<br/>
[인쇄](../mfc/printing.md)<br/>
[CView 클래스](../mfc/reference/cview-class.md)<br/>
[CDC 클래스](../mfc/reference/cdc-class.md)
