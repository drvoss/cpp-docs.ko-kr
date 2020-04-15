---
title: GDI 리소스 할당
ms.date: 06/03/2019
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
ms.openlocfilehash: 149aefeade6f99c294b12bfb294cdf1addb9e5e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370846"
---
# <a name="allocating-gdi-resources"></a>GDI 리소스 할당

이 문서에서는 인쇄에 필요한 Windows GDI(그래픽 디바이스 인터페이스) 개체를 할당 및 할당 취소하는 방법을 설명합니다.

> [!NOTE]
> 자세한 내용은 [GDI+ SDK 문서를](/windows/win32/gdiplus/-gdiplus-gdi-start)참조하십시오.

화면 표시가 아니라 인쇄를 위해 특정 글꼴, 펜 또는 기타 GDI 개체를 사용해야 한다고 가정합니다. 필요한 메모리 때문에 애플리케이션이 시작될 때 이러한 개체를 할당하는 것은 비효율적입니다. 애플리케이션이 문서를 인쇄하지 않는 경우 해당 메모리가 다른 용도에 필요할 수 있습니다. 인쇄가 시작될 때 할당한 후 인쇄가 끝나면 삭제하는 것이 좋습니다.

이러한 GDI 개체를 할당하려면 [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) 멤버 함수를 재정의합니다. 이 함수는 두 가지 이유로 이 용도에 적합합니다: 프레임워크는 각 인쇄 작업의 시작 부분에 이 함수를 한 번 호출하고 [OnPreparePrinting와](../mfc/reference/cview-class.md#onprepareprinting)달리 이 함수는 프린터 장치 드라이버를 나타내는 [CDC](../mfc/reference/cdc-class.md) 개체에 액세스할 수 있습니다. GDI 객체(예: `CFont *` 멤버 등)를 가리키는 뷰 클래스의 멤버 변수를 정의하여 인쇄 작업 중에 사용할 개체를 저장할 수 있습니다.

만든 GDI 개체를 사용하려면 [OnPrint](../mfc/reference/cview-class.md#onprint) 멤버 기능의 프린터 장치 컨텍스트에 이 개체를 선택합니다. 문서의 다른 페이지에 대해 다른 GDI 개체가 필요한 `m_nCurPage` 경우 [CPrintInfo](../mfc/reference/cprintinfo-structure.md) 구조의 멤버를 검사하고 그에 따라 GDI 개체를 선택할 수 있습니다. 연속하는 여러 페이지에 대한 GDI 개체가 필요한 경우 Windows에서 `OnPrint`가 호출될 때마다 디바이스 컨텍스트로 선택해야 합니다.

이러한 GDI 개체를 할당 할당 하려면 [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) 멤버 함수를 재정의 합니다. 각 인쇄 작업이 끝날 때 프레임워크에서 이 함수를 호출하여, 애플리케이션이 다른 작업에 반환되기 전에 인쇄와 관련된 GDI 개체 할당을 취소할 수 있는 기회를 제공합니다.

## <a name="see-also"></a>참고 항목

[인쇄](../mfc/printing.md)<br/>
[기본 인쇄가 수행되는 방법](../mfc/how-default-printing-is-done.md)
