---
title: 파일로/파일에서 데이터 Serialize
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], serialization
- documents [MFC], saving
- saving documents
- deserialization [MFC]
- serialization [MFC], role of document
- serialization [MFC], role of data
- data [MFC]
- data [MFC], serializing
- document data [MFC]
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
ms.openlocfilehash: 043ba019c6b5ad79db2cedb6314c9e65f14b14b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376928"
---
# <a name="serializing-data-to-and-from-files"></a>파일로/파일에서 데이터 Serialize

지속성의 기본 개념은 개체가 멤버 변수의 값으로 표시된 현재 상태를 영구 저장소에 쓸 수 있어야 한다는 것입니다. 나중에 영구 저장소에서 개체의 상태를 읽거나 "역직렬화"하여 개체를 다시 만들 수 있습니다. 여기서 중요한 점은 개체 자체가 자체 상태를 읽고 쓰는 책임이 있다는 것입니다. 따라서 클래스가 지속되려면 기본 직렬화 작업을 구현해야 합니다.

프레임워크는 파일 메뉴에서 As 저장 명령에 대한 응답으로 문서를 디스크 파일에 저장하고 열기 명령에 대한 응답으로 디스크 파일에서 문서를 로드하기 위한 기본 구현을 제공합니다. 작업이 거의 없는 경우 파일에서 데이터를 작성하고 읽을 수 있는 문서 기능을 구현할 수 있습니다. 가장 중요한 일은 문서 클래스의 [Serialize](../mfc/reference/cobject-class.md#serialize) 멤버 함수를 재정의하는 것입니다.

MFC 응용 프로그램 마법사는 멤버 함수가 `CDocument` 만드는 `Serialize` 문서 클래스에 멤버 함수의 골격 재정의를 배치합니다. 응용 프로그램의 멤버 변수를 구현한 후 데이터에 연결된 `Serialize` "아카이브 개체"로 데이터를 보내는 코드로 재정의를 채울 수 있습니다. [CArchive](../mfc/reference/carchive-class.md) 개체는 C++ iostream 라이브러리의 **cin** 및 **cout** 입력/출력 개체와 유사합니다. 그러나 `CArchive` 서식이 지정된 텍스트가 아닌 이진 형식을 쓰고 읽습니다.

## <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [Serialization](../mfc/serialization-in-mfc.md)

- [직렬화에서 문서의 역할](#_core_the_document.92.s_role_in_serialization)

- [직렬화에서 데이터의 역할](#_core_the_data.92.s_role_in_serialization)

- [직렬화 메커니즘 우회](../mfc/bypassing-the-serialization-mechanism.md)

## <a name="the-documents-role-in-serialization"></a><a name="_core_the_document.92.s_role_in_serialization"></a>직렬화에서 문서의 역할

프레임워크는 파일 메뉴의 열기, 저장 및 저장 명령에 자동으로 응답하여 문서의 `Serialize` 멤버 함수를 호출하여 구현됩니다. 예를 들어 ID_FILE_OPEN 명령은 응용 프로그램 개체에서 처리기 함수를 호출합니다. 이 과정에서 사용자는 파일 열기 대화 상자를 보고 응답하며 프레임워크는 사용자가 선택한 파일 이름을 가져옵니다. 프레임워크는 문서에 `CArchive` 데이터를 로드하기 위해 설정된 개체를 만들고 `Serialize`아카이브를 에 전달합니다. 프레임워크가 이미 파일을 열었습니다. 문서의 멤버 함수의 `Serialize` 코드는 아카이브를 통해 데이터를 읽고 필요에 따라 데이터 개체를 재구성합니다. 직렬화에 대한 자세한 내용은 [일련화를](../mfc/serialization-in-mfc.md)참조하십시오.

## <a name="the-datas-role-in-serialization"></a><a name="_core_the_data.92.s_role_in_serialization"></a>직렬화에서 데이터의 역할

일반적으로 클래스 형식 데이터는 자체적으로 직렬화할 수 있어야 합니다. 즉, 개체를 아카이브에 전달할 때 개체는 아카이브에 자신을 작성하는 방법과 아카이브에서 자신을 읽는 방법을 알아야 합니다. MFC는 이러한 방식으로 클래스를 직렬화할 수 있도록 지원합니다. 데이터 형식을 정의하는 클래스를 디자인하고 해당 형식의 데이터를 직렬화하려는 경우 직렬화를 위해 디자인합니다.

## <a name="see-also"></a>참고 항목

[문서 사용](../mfc/using-documents.md)
