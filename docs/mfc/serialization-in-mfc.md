---
title: MFC의 Serialization
ms.date: 11/04/2016
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
ms.openlocfilehash: eca4d0357977bc7ef21063718c738ae5bd8e7431
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372743"
---
# <a name="serialization-in-mfc"></a>MFC의 Serialization

이 문서에서는 MFC(Microsoft Foundation Class Library)에 제공된 직렬화 메커니즘을 설명하여 프로그램이 실행되는 동안 개체가 유지되도록 합니다.

직렬화는 디스크 파일과 같은 영구 저장소 매체에서 개체를 쓰거나 읽는 프로세스입니다. 직렬화는 프로그램을 실행하는 동안 또는 후에 구조화된 데이터(예: C++ 클래스 또는 구조)의 상태를 유지하려는 경우에 이상적입니다. MFC에서 제공하는 직렬화 개체를 사용하면 이러한 작업을 표준적이고 일관된 방식으로 수행할 수 있으므로 사용자가 직접 파일 작업을 수행할 필요가 없습니다.

MFC는 클래스의 `CObject`직렬화를 위한 기본 제공 지원을 제공합니다. 따라서, 에서 `CObject` 파생된 모든 클래스는 `CObject`'직렬화 프로토콜'을 활용할 수 있다.

직렬화의 기본 개념은 개체가 일반적으로 멤버 변수의 값으로 표시된 현재 상태를 영구 저장소에 쓸 수 있어야 한다는 것입니다. 나중에 저장소에서 개체의 상태를 읽거나 직렬화하여 개체를 다시 만들 수 있습니다. 직렬화는 개체 포인터의 모든 세부 정보와 개체를 직렬화할 때 사용되는 개체에 대한 순환 참조를 처리합니다. 요점은 개체 자체가 자체 상태를 읽고 쓰는 책임이 있다는 것입니다. 따라서 클래스를 직렬화할 수 있도록 기본 직렬화 작업을 구현해야 합니다. 아티클의 직렬화 그룹에 표시된 것처럼 이 기능을 클래스에 쉽게 추가할 수 있습니다.

MFC는 직렬화할 `CArchive` 개체와 저장소 매체 사이의 중개자로 클래스의 개체를 사용합니다. 이 개체는 항상 `CFile` 파일 이름 및 요청된 작업이 읽기 또는 쓰기인지 여부를 포함하여 직렬화에 필요한 정보를 가져오는 개체와 연결됩니다. 직렬화 작업을 수행하는 개체는 `CArchive` 저장소 매체의 특성에 관계없이 개체를 사용할 수 있습니다.

개체는 `CArchive` 오버로드된 삽입**<**() 및**>>** 추출 () 연산자 쓰기 및 읽기 작업을 수행 합니다. 자세한 내용은 문서 직렬화: 개체 직렬화의 [아카이브를 통해 CObjects 저장 및 로드를](../mfc/storing-and-loading-cobjects-via-an-archive.md) 참조하십시오.

> [!NOTE]
> 형식이 지정된 `CArchive` 텍스트에만 사용할 수 있는 범용 iostream 클래스와 클래스를 혼동하지 마십시오. 클래스는 `CArchive` 이진 형식의 직렬화된 개체에 대한 것입니다.

원하는 경우 MFC 직렬화를 우회하여 영구 데이터 저장소에 대한 고유한 메커니즘을 만들 수 있습니다. 사용자 명령에서 직렬화를 시작하는 클래스 멤버 함수를 재정의해야 합니다. ID_FILE_OPEN, ID_FILE_SAVE 및 표준 명령의 [기술 참고 22에서](../mfc/tn022-standard-commands-implementation.md) 설명 ID_FILE_SAVE_AS 참조하십시오.

다음 문서에서는 직렬화에 필요한 두 가지 주요 작업을 다룹니다.

- [Serialization: Serialize 가능한 클래스 만들기](../mfc/serialization-making-a-serializable-class.md)

- [Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)

문서 [직렬화: 직렬화 와 데이터베이스 입력/출력은](../mfc/serialization-serialization-vs-database-input-output.md) 직렬화가 데이터베이스 응용 프로그램에서 적절한 입력/출력 기술인 경우를 설명합니다.

## <a name="see-also"></a>참고 항목

[개념](../mfc/mfc-concepts.md)<br/>
[일반 MFC 항목](../mfc/general-mfc-topics.md)<br/>
[CArchive 클래스](../mfc/reference/carchive-class.md)<br/>
[CObject 클래스](../mfc/reference/cobject-class.md)<br/>
[C문서 클래스](../mfc/reference/cdocument-class.md)<br/>
[CFile 클래스](../mfc/reference/cfile-class.md)
