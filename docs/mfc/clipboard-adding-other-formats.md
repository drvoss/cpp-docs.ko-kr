---
title: '클립보드: 기타 서식 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
ms.openlocfilehash: 6f4e159cc1b6918843d4a164dcca88500eb7b038
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374601"
---
# <a name="clipboard-adding-other-formats"></a>클립보드: 기타 서식 추가

이 항목에서는 특히 OLE 지원에 대해 지원되는 형식 목록을 확장하는 방법을 설명합니다. [클립보드: 데이터 복사 및 붙여넣기](../mfc/clipboard-copying-and-pasting-data.md) 항목에서는 클립보드에서 복사 및 붙여넣기를 지원하는 데 필요한 최소 구현에 대해 설명합니다. 이 모든 것을 구현하는 경우 클립보드에 배치된 유일한 형식은 **CF_METAFILEPICT,** **CF_EMBEDSOURCE**, **CF_OBJECTDESCRIPTOR**및 **CF_LINKSOURCE**. 대부분의 응용 프로그램은 이 세 가지보다 클립보드에 더 많은 형식이 필요합니다.

## <a name="registering-custom-formats"></a><a name="_core_registering_custom_formats"></a>사용자 지정 형식 등록

사용자 지정 형식을 만들려면 사용자 지정 클립보드 형식을 등록할 때 사용하는 것과 동일한 절차를 따르십시오: **FormatClipboardFormat** 함수에 형식이름을 전달하고 반환 값을 형식 ID로 사용합니다.

## <a name="placing-formats-on-the-clipboard"></a><a name="_core_placing_formats_on_the_clipboard"></a>클립보드에 형식 배치

클립보드에 배치된 형식에 더 많은 형식을 추가하려면 `OnGetClipboardData` 복사할 데이터가 네이티브인지 여부에 `COleClientItem` `COleServerItem` 따라 파생된 클래스의 함수를 재정의해야 합니다. 이 함수에서는 다음 절차를 사용해야 합니다.

#### <a name="to-place-formats-on-the-clipboard"></a>클립보드에 형식을 배치하려면

1. `COleDataSource` 개체를 만듭니다.

1. 을 호출하여 `COleDataSource::CacheGlobalData`지원되는 형식 목록에 기본 데이터 형식을 추가하는 함수에 이 데이터 원본을 전달합니다.

1. 지원하려는 각 표준 `COleDataSource::CacheGlobalData` 형식을 호출하여 표준 형식을 추가합니다.

이 기술은 MFC OLE 샘플 프로그램 [HIERSVR(CServerItem](../overview/visual-cpp-samples.md) **CServerItem** 클래스의 `OnGetClipboardData` 멤버 함수 검사)에 사용됩니다. 이 샘플의 유일한 차이점은 HIERSVR이 다른 표준 형식을 지원하지 않기 때문에 3단계가 구현되지 않는다는 것입니다.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [OLE 데이터 개체 및 데이터 원본 및 균일한 데이터 전송](../mfc/data-objects-and-data-sources-ole.md)

- [OLE 끌어서 놓기](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>참고 항목

[클립보드: OLE 클립보드 메커니즘 사용](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
