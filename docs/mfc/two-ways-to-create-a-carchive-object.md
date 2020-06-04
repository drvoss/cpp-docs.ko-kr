---
title: CArchive 개체를 만드는 두 가지 방법
ms.date: 11/04/2016
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
ms.openlocfilehash: 71592584d4ecdd3169ad894861a97fa668c04ee8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370951"
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive 개체를 만드는 두 가지 방법

개체를 만드는 방법에는 `CArchive` 두 가지가 있습니다.

- [프레임워크를 통해 CArchive 개체의 암시적 생성](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [CArchive 개체의 명시적 생성](#_core_explicit_creation_of_a_carchive_object)

## <a name="implicit-creation-of-a-carchive-object-via-the-framework"></a><a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a>프레임워크를 통해 CArchive 개체의 암시적 생성

가장 일반적이고 쉬운 방법은 파일 메뉴에서 저장, 현재 저장 및 열기 명령을 대신하여 프레임워크에서 문서에 대한 `CArchive` 개체를 만들도록 하는 것입니다.

다음은 응용 프로그램의 사용자가 파일 메뉴에서 As로 저장 명령을 실행하면 프레임워크가 수행하는 작업의 내용입니다.

1. 로 **저장** 대화 상자를 지정 하고 사용자로부터 파일 이름을 가져옵니다.

1. 사용자가 개체로 명명한 파일을 `CFile` 엽니다.

1. 이 `CFile` `CArchive` 개체를 가리키는 개체를 만듭니다. 개체를 `CArchive` 만들 때 프레임워크는 "로드"(읽기, 역직렬화)가 아닌 모드를 "저장"(쓰기, serialize)으로 설정합니다.

1. -derived 클래스에 정의된 `Serialize` 함수를 호출하여 `CArchive` 개체에 대한 참조를 전달합니다. `CDocument`

그런 다음 `Serialize` 문서의 함수는 `CArchive` 곧 설명된 대로 개체에 데이터를 씁니다. `Serialize` 함수에서 돌아오면 프레임워크는 개체와 `CArchive` 개체를 `CFile` 파괴합니다.

따라서 프레임워크에서 문서의 개체를 `CArchive` 만들도록 허용하면 아카이브에서 쓰고 읽는 문서의 `Serialize` 함수를 구현하기만 하면 됩니다. 또한 문서의 `Serialize` `Serialize` 함수가 `CObject`직렬화하는 파생 개체에 대해서도 직접 또는 간접적으로 구현해야 합니다.

## <a name="explicit-creation-of-a-carchive-object"></a><a name="_core_explicit_creation_of_a_carchive_object"></a>CArchive 개체의 명시적 생성

프레임워크를 통해 문서를 직렬화하는 것 외에도 개체가 `CArchive` 필요할 수 있는 경우도 있습니다. 예를 들어 개체로 표시되는 Clipboard에서 데이터를 직렬화할 `CSharedFile` 수 있습니다. 또는 프레임워크에서 제공하는 것과 다른 파일을 저장하기 위해 사용자 인터페이스를 사용할 수 있습니다. 이 경우 개체를 `CArchive` 명시적으로 만들 수 있습니다. 다음 절차를 사용하여 프레임워크와 동일한 방식으로 이 작업을 수행합니다.

#### <a name="to-explicitly-create-a-carchive-object"></a>CArchive 개체를 명시적으로 만들려면

1. 에서 `CFile` 파생된 개체 또는 `CFile`개체를 생성합니다.

1. 다음 `CFile` 예제와 같이 에 `CArchive`대한 생성자에 개체를 전달합니다.

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   `CArchive` 생성자의 두 번째 인수는 아카이브가 파일로 또는 파일에서 데이터를 저장하거나 로드하는 데 사용할지 여부를 지정하는 나열된 값입니다. 개체의 함수는 `Serialize` 아카이브 개체에 `IsStoring` 대한 함수를 호출하여 이 상태를 확인합니다.

개체에 대한 데이터 저장 또는 로드가 `CArchive` 완료되면 닫힙습니다. `CArchive` (및) `CFile`개체가 아카이브(및 파일)를 자동으로 닫지만 오류로부터 쉽게 복구할 수 있으므로 명시적으로 닫는 것이 좋습니다. 오류 처리에 대한 자세한 내용은 [예외: 예외 catch 및 삭제 예외](../mfc/exceptions-catching-and-deleting-exceptions.md)를 참조하십시오.

#### <a name="to-close-the-carchive-object"></a>CArchive 개체를 닫려면

1. 다음 예제에서는 개체를 닫는 `CArchive` 방법을 보여 줍니다.

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>참고 항목

[Serialization: 개체 Serialize](../mfc/serialization-serializing-an-object.md)
