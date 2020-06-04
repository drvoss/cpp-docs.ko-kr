---
title: '데이터 개체 및 데이터 소스: 조작'
ms.date: 11/04/2016
helpviewer_keywords:
- data objects [MFC], manipulating
- data sources [MFC], data operations
- data sources [MFC], inserting data
- Clipboard [MFC], determining available formats
- OLE [MFC], data objects
- Clipboard [MFC], passing format information
- data sources [MFC], determining available formats
- delayed rendering [MFC]
- OLE [MFC], data sources
ms.assetid: f7f27e77-bb5d-4131-b819-d71bf929ebaf
ms.openlocfilehash: a08b6ff274c73d301c156d65aa56fbecca49128c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370546"
---
# <a name="data-objects-and-data-sources-manipulation"></a>데이터 개체 및 데이터 소스: 조작

데이터 개체 또는 데이터 원본을 만든 후 데이터 삽입 및 제거, 데이터의 형식 열거 등과 같은 여러 가지 일반적인 작업을 수행할 수 있습니다. 이 문서에서는 가장 일반적인 작업을 완료하는 데 필요한 기술을 설명합니다. 다룰 주제는 다음과 같습니다.

- [데이터 원본에 데이터 삽입](#_core_inserting_data_into_a_data_source)

- [데이터 개체에서 사용할 수 있는 형식 결정](#_core_determining_the_formats_available_in_a_data_object)

- [데이터 개체에서 데이터 검색](#_core_retrieving_data_from_a_data_object)

## <a name="inserting-data-into-a-data-source"></a><a name="_core_inserting_data_into_a_data_source"></a>데이터 원본에 데이터 삽입

데이터가 데이터 원본에 삽입되는 방법은 데이터가 즉시 제공되는지 또는 필요에 따라 제공되는지 여부와 데이터가 제공되는 매체에 따라 달라집니다. 가능성은 다음과 같습니다.

### <a name="supplying-data-immediately-immediate-rendering"></a>즉시 데이터 제공(즉시 렌더링)

- 데이터를 `COleDataSource::CacheGlobalData` 제공하는 모든 클립보드 형식에 대해 반복적으로 호출합니다. 사용할 클립보드 형식, 데이터를 포함하는 메모리에 핸들을 전달하고, 선택적으로 데이터를 설명하는 **FORMATETC** 구조를 전달합니다.

     또는

- **STGMEDIUM** 구조로 직접 작업하려면 위의 `COleDataSource::CacheData` 옵션 `COleDataSource::CacheGlobalData` 대신 호출합니다.

### <a name="supplying-data-on-demand-delayed-rendering"></a>주문형 데이터 제공(렌더링 지연)

이 항목은 고급 항목입니다.

- 데이터를 `COleDataSource::DelayRenderData` 제공하는 모든 클립보드 형식에 대해 반복적으로 호출합니다. 사용할 클립보드 형식과 선택적으로 데이터를 설명하는 **FORMATETC** 구조를 전달합니다. 데이터가 요청되면 프레임워크에서 재정의해야 하는 을 호출합니다. `COleDataSource::OnRenderData`

     또는

- 개체를 `CFile` 사용하여 데이터를 제공하는 경우 `COleDataSource::DelayRenderFileData` 이전 `COleDataSource::DelayRenderData` 옵션 대신 호출합니다. 데이터가 요청되면 프레임워크에서 재정의해야 하는 을 호출합니다. `COleDataSource::OnRenderFileData`

## <a name="determining-the-formats-available-in-a-data-object"></a><a name="_core_determining_the_formats_available_in_a_data_object"></a>데이터 개체에서 사용할 수 있는 형식 결정

응용 프로그램에서 사용자가 데이터를 붙여넣기를 허용하기 전에 Clipboard에 처리할 수 있는 형식이 있는지 알아야 합니다. 이렇게 하려면 응용 프로그램에서 다음을 수행해야 합니다.

1. `COleDataObject` 개체및 **FORMATETC** 구조를 만듭니다.

1. 데이터 개체의 `AttachClipboard` 멤버 함수를 호출하여 데이터 개체를 Clipboard의 데이터와 연결합니다.

1. 다음 중 하나를 수행합니다.

   - 필요한 형식이 하나 `IsDataAvailable` 또는 두 개만 있는 경우 데이터 개체의 멤버 함수를 호출합니다. 이렇게 하면 Clipboard의 데이터가 응용 프로그램보다 훨씬 더 많은 형식을 지원하는 경우 시간을 절약할 수 있습니다.

     \-또는-

   - 데이터 개체의 `BeginEnumFormats` 멤버 함수를 호출하여 Clipboard에서 사용할 수 있는 형식의 예인을 시작합니다. 그런 `GetNextFormat` 다음 Clipboard가 응용 프로그램에서 지원하는 형식을 반환하거나 더 이상 형식이 없을 때까지 호출합니다.

**ON_UPDATE_COMMAND_UI**사용하는 경우 이제 붙여넣기를 활성화하고 편집 메뉴에서 특수 항목을 붙여칠 수 있습니다. 이렇게 하려면 `CMenu::EnableMenuItem` 또는 `CCmdUI::Enable`에 전화하십시오. 컨테이너 응용 프로그램이 메뉴 항목으로 수행해야 하는 항목 및 시기에 대한 자세한 내용은 [메뉴 및 리소스: 컨테이너 추가 를](../mfc/menus-and-resources-container-additions.md)참조하십시오.

## <a name="retrieving-data-from-a-data-object"></a><a name="_core_retrieving_data_from_a_data_object"></a>데이터 개체에서 데이터 검색

데이터 형식을 결정한 후에는 데이터 개체에서 데이터를 검색하기만 하면 됩니다. 이렇게 하려면 사용자가 데이터를 넣을 위치를 결정하고 응용 프로그램이 적절한 함수를 호출합니다. 데이터는 다음 매체 중 하나에서 사용할 수 있습니다.

|중간|호출 함수|
|------------|----------------------|
|글로벌 메모리`HGLOBAL`()|`COleDataObject::GetGlobalData`|
|파일`CFile`()|`COleDataObject::GetFileData`|
|**STGMEDIUM** 구조`IStorage`()|`COleDataObject::GetData`|

일반적으로 미디어는 클립보드 형식과 함께 지정됩니다. 예를 들어 **CF_EMBEDDEDSTRUCT** 개체는 항상 `IStorage` **STGMEDIUM** 구조를 필요로 하는 매체에 있습니다. 따라서 `GetData` **STGMEDIUM** 구조를 받아들일 수 있는 이러한 함수 중 하나이기 때문에 사용합니다.

클립보드 `IStream` 형식이 또는 `HGLOBAL` 보통인 경우 프레임워크는 데이터를 `CFile` 참조하는 포인터를 제공할 수 있습니다. 그런 다음 응용 프로그램은 파일 읽기를 사용하여 파일에서 데이터를 가져올 수 있는 것과 거의 동일한 방식으로 데이터를 가져올 수 있습니다. 기본적으로 이것은 데이터 원본의 `OnRenderData` 및 `OnRenderFileData` 루틴에 대한 클라이언트 측 인터페이스입니다.

이제 사용자는 동일한 형식의 다른 데이터와 마찬가지로 문서에 데이터를 삽입할 수 있습니다.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [드래그 앤 드롭](../mfc/drag-and-drop-ole.md)

- [클립보드](../mfc/clipboard.md)

## <a name="see-also"></a>참고 항목

[데이터 개체 및 데이터 소스(OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[콜레데이터오브젝트 클래스](../mfc/reference/coledataobject-class.md)<br/>
[콜레데이터소스 클래스](../mfc/reference/coledatasource-class.md)
