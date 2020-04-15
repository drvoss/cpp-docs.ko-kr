---
title: '컨테이너: 복합 파일'
ms.date: 11/04/2016
helpviewer_keywords:
- compound files [MFC]
- compound documents
- containers [MFC], compound files
- OLE documents [MFC], compound files
- performance [MFC], compound files
- files [MFC], compound
- standardized file structure compound files
- documents [MFC], compound
- documents [MFC], OLE
- OLE containers [MFC], compound files
- access modes for files [MFC]
ms.assetid: 8b83cb3e-76c8-4bbe-ba16-737092b36f49
ms.openlocfilehash: 98166a355fd267ecbec0a7f0cc1d18fd0b2e7cd0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353581"
---
# <a name="containers-compound-files"></a>컨테이너: 복합 파일

이 문서에서는 복합 파일의 구성 요소 및 구현과 OLE 응용 프로그램에서 복합 파일을 사용할 때의 장점과 단점에 대해 설명합니다.

복합 파일은 OLE의 필수적인 부분입니다. 데이터 전송 및 OLE 문서 저장을 용이하게 하는 데 사용됩니다. 복합 파일은 Active 구조화 저장소 모델의 구현입니다. 저장소, 스트림 또는 파일 개체에 대한 직렬화를 지원하는 일관된 인터페이스가 있습니다. 복합 파일은 Microsoft Foundation 클래스 라이브러리에서 `COleStreamFile` `COleDocument`클래스 및 .

> [!NOTE]
> 복합 파일을 사용한다고 해서 정보가 OLE 문서 나 복합 문서에서 온다는 의미는 아닙니다. 복합 파일은 복합 문서, OLE 문서 및 기타 데이터를 저장하는 방법 중 하나일 뿐입니다.

## <a name="components-of-a-compound-file"></a><a name="_core_components_of_a_compound_file"></a>복합 파일의 구성요소

복합 파일의 OLE 구현은 스트림 개체, 저장소 개체 `ILockBytes` 및 개체의 세 가지 개체 유형을 사용합니다. 이러한 개체는 다음과 같은 방법으로 표준 파일 시스템의 구성 요소와 유사합니다.

- 파일과 같은 개체를 스트리밍하면 모든 유형의 데이터가 저장됩니다.

- 디렉터리와 같은 저장소 개체에는 다른 저장소 및 스트림 개체가 포함될 수 있습니다.

- `LockBytes`개체는 저장소 개체와 물리적 하드웨어 간의 인터페이스를 나타냅니다. 하드 드라이브 나 전역 메모리 영역과 같이 `LockBytes` 개체가 액세스하는 모든 저장 장치에 실제 바이트가 기록되는 방법을 결정합니다. 개체 및 `LockBytes` 인터페이스에 `ILockBytes` 대한 자세한 내용은 *OLE 프로그래머의 참조*를 참조하십시오.

## <a name="advantages-and-disadvantages-of-compound-files"></a><a name="_core_advantages_and_disadvantages_of_compound_files"></a>복합 파일의 장점과 단점

복합 파일은 이전 파일 저장소 방법에서 사용할 수 없는 이점을 제공합니다. 해당 기능은 아래와 같습니다.

- 증분 파일 액세스.

- 파일 액세스 모드.

- 파일 구조의 표준화.

플로피 디스크의 저장소와 관련된 큰 크기 및 성능 문제와 같은 복합 파일의 잠재적인 단점은 응용 프로그램에서 사용할지 여부를 결정할 때 고려해야 합니다.

### <a name="incremental-access-to-files"></a><a name="_core_incremental_access_to_files"></a>파일에 대한 증분 액세스

파일에 대한 증분 액세스는 복합 파일을 사용할 때 자동으로 이점을 얻을 수 있습니다. 복합 파일은 "파일 내의 파일 시스템"으로 볼 수 있으므로 전체 파일을 로드할 필요 없이 스트림 또는 저장소와 같은 개별 개체 유형에 액세스할 수 있습니다. 이렇게 하면 응용 프로그램이 사용자가 편집하기 위해 새 개체에 액세스하는 데 필요한 시간을 크게 줄일 수 있습니다. 동일한 개념에 따라 증분 업데이트는 유사한 이점을 제공합니다. OLE는 한 개체에 변경한 내용을 저장하기 위해 전체 파일을 저장하는 대신 사용자가 편집한 스트림 또는 저장소 개체만 저장합니다.

### <a name="file-access-modes"></a><a name="_core_file_access_modes"></a>파일 액세스 모드

복합 파일의 개체변경이 디스크에 커밋되는 시기를 확인할 수 있다는 것은 복합 파일을 사용하는 또 다른 이점입니다. 파일에 액세스하는 모드는 트랜잭션 또는 직접 변경 이 커밋되는 시기를 결정합니다.

- 트랜잭션 모드는 2단계 커밋 작업을 사용하여 복합 파일의 개체를 변경하여 사용자가 변경 내용을 저장하거나 취소하도록 선택할 때까지 문서의 이전 복사본과 새 복사본을 모두 사용할 수 있도록 합니다.

- 직접 모드는 나중에 문서를 취소할 수 없는 변경 내용을 문서에 포함합니다.

액세스 모드에 대한 자세한 내용은 *OLE 프로그래머의 참조*를 참조하십시오.

### <a name="standardization"></a><a name="_core_standardization"></a>표준화

복합 파일의 표준화된 구조를 통해 다른 OLE 응용 프로그램이 실제로 파일을 만든 응용 프로그램에 대한 지식 없이 OLE 응용 프로그램에서 만든 복합 파일을 탐색할 수 있습니다.

### <a name="size-and-performance-considerations"></a><a name="_core_size_and_performance_considerations"></a>크기 및 성능 고려 사항

복합 파일 저장 구조의 복잡성과 데이터를 점진적으로 저장하는 기능으로 인해 이 형식을 사용하는 파일은 구조화되지 않은 파일 또는 "플랫 파일" 저장소를 사용하는 다른 파일보다 큰 경향이 있습니다. 응용 프로그램에서 파일을 자주 로드하고 저장하는 경우 복합 파일을 사용하면 비복합 파일보다 파일 크기가 훨씬 빠르게 증가할 수 있습니다. 복합 파일이 커질 수 있으므로 플로피 디스크에 저장되고 로드된 파일에 대한 액세스 시간이 영향을 받아 파일에 대한 액세스 속도가 느려질 수 있습니다.

성능에 영향을 주는 또 다른 문제는 복합 파일 조각화입니다. 복합 파일의 크기는 파일에서 사용하는 첫 번째 디스크 섹터와 마지막 디스크 섹터 간의 차이에 의해 결정됩니다. 조각난 파일에는 데이터를 포함하지 않지만 크기를 계산할 때 계산되는 많은 여유 공간 영역이 포함될 수 있습니다. 복합 파일의 수명 동안 이러한 영역은 저장소 개체의 삽입 또는 삭제에 의해 만들어집니다.

## <a name="using-compound-files-format-for-your-data"></a><a name="_core_using_compound_files_format_for_your_data"></a>데이터에 복합 파일 형식 사용

에서 `COleDocument`파생된 문서 클래스가 있는 응용 프로그램을 성공적으로 만든 후 `EnableCompoundFile`기본 문서 생성자가 호출해야 합니다. 응용 프로그램 마법사에서 OLE 컨테이너 응용 프로그램을 만들 때 이 호출이 삽입됩니다.

OLE *프로그래머의 참조에서* [IStream](/windows/win32/api/objidl/nn-objidl-istream), [IStorage](/windows/win32/api/objidl/nn-objidl-istorage)및 [ILockBytes](/windows/win32/api/objidl/nn-objidl-ilockbytes)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[컨테이너](../mfc/containers.md)<br/>
[컨테이너: 사용자 인터페이스 문제](../mfc/containers-user-interface-issues.md)<br/>
[코올스트림파일 클래스](../mfc/reference/colestreamfile-class.md)<br/>
[콜레문서 클래스](../mfc/reference/coledocument-class.md)
