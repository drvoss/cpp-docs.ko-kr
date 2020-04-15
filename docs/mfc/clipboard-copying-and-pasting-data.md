---
title: '클립보드: 데이터 복사 및 붙여넣기'
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
ms.openlocfilehash: 74348dd3e790cceada9aafd718464694997316ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374564"
---
# <a name="clipboard-copying-and-pasting-data"></a>클립보드: 데이터 복사 및 붙여넣기

이 항목에서는 OLE 응용 프로그램의 클립보드에서 복사 및 붙여넣기를 구현하는 데 필요한 최소 작업에 대해 설명합니다. 계속하기 전에 데이터 [개체 및 데이터 원본(OLE)](../mfc/data-objects-and-data-sources-ole.md) 항목을 읽는 것이 좋습니다.

복사 또는 붙여넣기를 구현하기 전에 먼저 편집 메뉴에서 복사, 잘라내기 및 붙여넣기 옵션을 처리하는 함수를 제공해야 합니다.

## <a name="copying-or-cutting-data"></a><a name="_core_copying_or_cutting_data"></a>데이터 복사 또는 절단

#### <a name="to-copy-data-to-the-clipboard"></a>데이터를 클립보드에 복사하려면

1. 복사할 데이터가 네이티브 데이터인지 아니면 포함된 항목인지 또는 연결된 항목인지 확인합니다.

   - 데이터가 포함되거나 링크된 경우 선택한 `COleClientItem` 개체에 대한 포인터를 가져옵니다.

   - 데이터가 네이티브이고 응용 프로그램이 서버인 경우 선택한 데이터를 포함하는 `COleServerItem` 데서 파생된 새 개체를 만듭니다. 그렇지 않으면 `COleDataSource` 데이터에 대한 개체를 만듭니다.

1. 선택한 항목의 멤버 `CopyToClipboard` 함수를 호출합니다.

1. 사용자가 복사 작업 대신 잘라내기 작업을 선택한 경우 응용 프로그램에서 선택한 데이터를 삭제합니다.

이 시퀀스의 예를 보려면 `OnEditCut` MFC OLE 샘플 프로그램 `OnEditCopy` [OCLIENT](../overview/visual-cpp-samples.md) 및 [HIERSVR의](../overview/visual-cpp-samples.md)기능 및 기능을 참조하십시오. 이러한 샘플은 현재 선택된 데이터에 대한 포인터를 유지하므로 1단계는 이미 완료되었습니다.

## <a name="pasting-data"></a><a name="_core_pasting_data"></a>데이터 붙여넣기

데이터를 응용 프로그램에 붙여넣을 때 사용할 형식을 선택해야 하기 때문에 데이터를 복사하는 것보다 데이터 붙여넣기가 더 복잡합니다.

#### <a name="to-paste-data-from-the-clipboard"></a>클립보드에서 데이터를 붙여넣습니다.

1. 뷰 클래스에서 편집 `OnEditPaste` 메뉴에서 붙여넣기 옵션을 선택한 사용자를 처리하도록 구현합니다.

1. 함수에서 `OnEditPaste` 개체를 `COleDataObject` 만들고 해당 `AttachClipboard` 멤버 함수를 호출하여 이 개체를 Clipboard의 데이터에 연결합니다.

1. 호출하여 `COleDataObject::IsDataAvailable` 특정 형식을 사용할 수 있는지 확인합니다.

   또는 응용 프로그램에 `COleDataObject::BeginEnumFormats` 가장 적합한 형식을 찾을 때까지 다른 형식을 찾는 데 사용할 수 있습니다.

1. 형식의 붙여넣기를 수행합니다.

이 작동 방식의 예는 MFC `OnEditPaste` OLE 샘플 프로그램 [OCLIENT](../overview/visual-cpp-samples.md) 및 [HIERSVR에](../overview/visual-cpp-samples.md)정의된 뷰 클래스에서 멤버 함수의 구현을 참조하십시오.

> [!TIP]
> 붙여넣기 작업을 자체 함수로 분리하는 주요 이점은 끌어서 놓기 작업 중에 응용 프로그램에서 데이터를 삭제할 때 동일한 붙여넣기 코드를 사용할 수 있다는 것입니다. OCLIENT 및 HIERSVR에서와 `OnDrop` 마찬가지로 함수는 붙여넣기 작업을 구현하기 위해 작성된 코드를 다시 사용하여 호출할 `DoPasteItem`수도 있습니다.

편집 메뉴에서 특수 붙여넣기 옵션을 처리하려면 [OLE의 대화 상자](../mfc/dialog-boxes-in-ole.md)항목을 참조하십시오.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [다른 형식 추가](../mfc/clipboard-adding-other-formats.md)

- [OLE 데이터 개체 및 데이터 원본 및 균일한 데이터 전송](../mfc/data-objects-and-data-sources-ole.md)

- [OLE 끌어서 놓기](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>참고 항목

[클립보드: OLE 클립보드 메커니즘 사용](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)
